---
title: "방법: 구성에서 서비스 끝점 만들기"
ms.custom: 
ms.date: 06/16/2016
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f474e25d-2a27-4f31-84c5-395c442b8e70
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b96ccdb7e80faa35748a41947ed97f273cb330e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-service-endpoint-in-configuration"></a>방법: 구성에서 서비스 끝점 만들기
끝점은 클라이언트에게 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스가 제공하는 기능에 대한 액세스를 제공합니다. 상대 및 절대 끝점 주소 조합을 사용하여 끝점을 하나 이상 정의할 수 있으며, 서비스 끝점을 정의하지 않는 경우에는 런타임이 기본적으로 일부 끝점을 자동으로 제공합니다. 이 항목에서는 상대 주소와 절대 주소를 모두 포함하는 구성 파일을 사용해 끝점을 추가하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예  
 다음 서비스 구성에는 기본 주소와 5개의 끝점이 지정됩니다.  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <services>  
    <!-- This section is optional with the default configuration introduced  
         in .NET Framework 4. -->  
      <service  
          name="Microsoft.ServiceModel.Samples.CalculatorService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="/test"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="http://localhost:8001/hello/servicemodelsamples"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
                  binding="netTcpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is another relative address exposed at   
             http://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
## <a name="example"></a>예  
 기본 주소는 다음 샘플에서처럼 service/host/baseAddresses 아래 `add` 요소를 사용하여 지정합니다.  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
```  
  
## <a name="example"></a>예  
 다음 샘플에서처럼 첫 번째 끝점 정의는 끝점 주소가 기본 주소와 URI(Uniform Resource Identifier) 컴퍼지션 다음에 오는 상대 주소의 조합인 상대 주소를 지정합니다. 상대 주소가 비어 있으므로("") 끝점 주소는 기본 주소와 동일합니다. 실제 끝점 주소는 http://localhost:8000/servicemodelsamples/service입니다.  
  
```xml  
<endpoint address=""   
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>예  
 두 번째 끝점 정의도 다음 샘플 구성에서처럼 상대 주소를 지정합니다. 상대 주소 "test"가 기본 주소에 추가됩니다. 실제 끝점 주소는 http://localhost:8000/servicemodelsamples/service/test입니다.  
  
```xml  
<endpoint address="/test"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>예  
 세 번째 끝점 정의는 다음 샘플 구성에서처럼 절대 주소를 지정합니다. 주소에서 기본 주소는 아무런 역할도 하지 않습니다. 실제 끝점 주소는 http://localhost:8001/hello/servicemodelsamples입니다.  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>예  
 네 번째 끝점 주소는 절대 주소 및 다른 전송(TCP)을 지정합니다. 주소에서 기본 주소는 아무런 역할도 하지 않습니다. 실제 끝점 주소는 net.tcp://localhost:9000/servicemodelsamples/service입니다.  
  
```xml  
<endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
    binding="netTcpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>예  
 런타임에서 제공하는 기본 끝점을 사용하려면 코드나 구성 파일에 서비스 끝점을 지정하지 않으면 됩니다. 이 예제에서는 서비스를 열 때 런타임이 기본 끝점을 만듭니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]기본 끝점, 바인딩 및 동작, 참조 [단순화 된 구성](../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```
