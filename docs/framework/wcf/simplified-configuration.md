---
title: 단순화된 구성
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: 9f35a5f4fa4ae6be63bd75a24f58b56dd236ee9c
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33808512"
---
# <a name="simplified-configuration"></a>단순화된 구성
Windows Communication Foundation (WCF) 서비스를 구성 하는 복잡 한 작업일 수 있습니다. 다양한 옵션이 있을 수 있고 경우에 따라 필요한 설정을 확인하는 것이 쉽지 않을 수도 있습니다. 구성 파일 WCF 서비스의 유연성을 높이고, 하는 동안 문제를 발견 하기 어려운 대부분의 원본 서로입니다. [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]에서는 이러한 문제를 해결하고 서비스 구성의 크기와 복잡성을 줄일 수 있는 방법을 제공합니다.  
  
## <a name="simplified-configuration"></a>단순화된 구성  
 WCF 서비스 구성 파일에는 <`system.serviceModel`> 섹션에 포함 되어는 <`service`> 호스트 된 각 서비스에 대 한 요소입니다. <`service`> 요소에는 각 서비스에 대해 노출된 끝점을 지정하고 선택적으로 일련의 서비스 동작도 지정하는 <`endpoint`> 요소의 컬렉션이 포함되어 있습니다. <`endpoint`> 요소는 끝점에서 노출하는 주소, 바인딩 및 계약을 지정하고 선택적으로 바인딩 구성과 끝점 동작도 지정합니다. <`system.serviceModel`> 섹션에는 서비스 또는 끝점 동작을 지정할 수 있는 <`behaviors`> 요소도 포함되어 있습니다. 다음 예제에서는 구성 파일의 <`system.serviceModel`> 섹션을 보여 줍니다.  
  
```  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true">  
        <serviceDebug includeExceptionDetailInFaults="false">  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <bindings>  
   <basicHttpBinding>  
      <binding name=MyBindingConfig"  
               maxBufferSize="100"  
               maxReceiveBufferSize="100" />  
   </basicHttpBinding>  
   </bindings>   <services>  
    <service behaviorConfiguration="MyServiceBehavior"  
             name="MyService">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                contract="ICalculator"  
                bindingConfiguration="MyBindingConfig" />  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange"/>  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 에 대 한 요구 사항을 제거 하 여 WCF 서비스를 보다 쉽게 구성할 수 있게 된 <`service`> 요소입니다. 사용자가 <`service`> 섹션을 추가하지 않거나 <`service`> 섹션에 끝점을 추가하지도 않고 서비스에 의해 프로그래밍 방식으로 끝점이 정의되지도 않으면 각 서비스 기준 주소와 서비스에 의해 구현되는 각 계약마다 하나씩 기본 끝점 집합이 서비스에 자동으로 추가됩니다. 이러한 각 끝점에서 끝점 주소는 기본 주소에 해당하고, 바인딩은 기본 주소 스키마에 의해 결정되며, 계약은 서비스에 의해 구현되는 계약입니다. 끝점 또는 서비스 동작을 지정하지 않아도 되거나 바인딩 설정을 변경하지 않아도 되는 경우에는 서비스 구성 파일을 지정하지 않아도 됩니다. 서비스에서 두 개의 계약을 구현하고 호스트에서 HTTP 전송과 TCP 전송을 둘 다 사용하는 경우 서비스 호스트에서 각 전송을 사용하여 각 계약마다 하나씩 네 개의 기본 끝점을 만듭니다. 기본 끝점을 만들려면 서비스 호스트에서 사용할 바인딩을 알고 있어야 합니다. 이러한 설정은 <`protocolMappings`> 섹션 내의 <`system.serviceModel`> 섹션에 지정됩니다. <`protocolMappings`> 섹션에는 바인딩 형식에 매핑된 전송 프로토콜 스키마의 목록이 들어 있습니다. 서비스 호스트는 이 목록에 전달된 기본 주소를 사용하여 사용할 바인딩을 결정합니다. 다음 예제에서는 <`protocolMappings`> 요소를 사용합니다.  
  
> [!WARNING]
>  바인딩 또는 동작과 같은 기본 구성 요소를 변경하면 구성 계층 구조의 낮은 수준에서 정의된 서비스에서 이러한 기본 바인딩 및 동작을 사용할 수도 있기 때문에 해당 서비스에 영향을 줄 수도 있습니다. 따라서 기본 바인딩 및 동작을 변경하는 경우 이러한 변경이 계층 구조의 다른 서비스에 영향을 줄 수도 있다는 점을 명심해야 합니다.  
  
> [!NOTE]
>  IIS(인터넷 정보 서비스)나 WAS(Windows Process Activation Service)에서 호스트된 서비스는 가상 디렉터리를 기본 주소로 사용합니다.  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 이전 예제에서 "http" 체계로 시작하는 기본 주소를 가진 끝점은 <xref:System.ServiceModel.BasicHttpBinding>을 사용하고, "net.tcp" 체계로 시작하는 기본 주소를 가진 있는 끝점은 <xref:System.ServiceModel.NetTcpBinding>을 사용합니다. 로컬 App.config 또는 Web.config 파일의 설정은 재정의할 수 있습니다.  
  
 <`protocolMappings`> 섹션 내의 각 요소는 스키마와 바인딩을 지정해야 하며, 필요에 따라 구성 파일의 <`bindingConfiguration`> 섹션 내에서 바인딩 구성을 지정하는 `bindings` 특성을 지정할 수도 있습니다. `bindingConfiguration`을 지정하지 않으면 해당 바인딩 형식의 익명 바인딩 구성이 사용됩니다.  
  
 서비스 동작은 <`behavior`> 섹션 내의 익명 <`serviceBehaviors`> 섹션을 사용하여 기본 끝점에 대해 구성됩니다. <`behavior`> 내의 명명되지 않은 <`serviceBehaviors`> 요소는 서비스 동작을 구성하는 데 사용됩니다. 예를 들어 다음 구성 파일은 호스트 내의 모든 서비스에 대한 서비스 메타데이터 게시를 사용하도록 설정합니다.  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <!-- No <service> tag is necessary. Default endpoints are added to the service -->  
    <!-- The service behavior with name="" is picked up by the service -->  
 </system.serviceModel>  
```  
  
 끝점 동작은 <`behavior`> 섹션 내의 익명 <`serviceBehaviors`> 섹션을 사용하여 구성됩니다.  
  
 다음 예제에서는 이 항목의 시작 부분에 나온 구성 파일이 단순화된 구성 모델을 사용하는 것을 보여 줍니다.  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="false"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <bindings>  
       <basicHttpBinding>  
          <binding maxBufferSize="100"  
                   maxReceiveBufferSize="100" />  
       </basicHttpBinding>  
    </bindings>    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->  
    <!-- The service behavior with name="" will be picked up by the service -->  
    <protocolMapping>  
      <add scheme="http"     binding="basicHttpBinding" / </protocolMapping>  
  </system.serviceModel>  
```  
  
> [!IMPORTANT]
>  이 기능은 클라이언트 구성이 아닌 WCF 서비스 구성에만 관련이 있습니다. 대부분, WCF 클라이언트 구성은 Visual Studio에서 서비스 참조를 추가하거나 svcutil.exe와 같은 도구에 의해 생성될 것입니다. WCF 클라이언트를 수동으로 구성 하는 경우 추가 해야 합니다는 \<클라이언트 > 구성 요소 호출 하려는 끝점을 지정 하 고 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [구성 파일을 사용하여 서비스 구성](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 [서비스에 대한 바인딩 구성](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)  
 [시스템 제공 바인딩 구성](../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [서비스 구성](../../../docs/framework/wcf/configuring-services.md)  
 [Windows Communication Foundation 응용 프로그램 구성](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 [코드로 WCF 서비스 구성](../../../docs/framework/wcf/configuring-wcf-services-in-code.md)
