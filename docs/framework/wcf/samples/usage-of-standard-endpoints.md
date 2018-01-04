---
title: "표준 끝점 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecd6a62f-9619-4778-a497-6f888087a9ea
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ac8a9c639099e952f6030f5625958dd2bf84757
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="usage-of-standard-endpoints"></a>표준 끝점 사용
이 샘플에서는 서비스 구성 파일에서 표준 끝점을 사용하는 방법을 보여 줍니다. 표준 끝점을 사용하면 사용자는 주소, 바인딩 및 계약 조합을 설명하는 단일 속성과 끝점에 관련된 추가 속성을 사용하여 끝점 정의를 단순화할 수 있습니다. 이 샘플에서는 사용자 지정 표준 끝점을 정의 및 구현하는 방법과 끝점의 특정 속성을 정의하는 방법을 보여 줍니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 서비스 끝점은 주소, 바인딩 및 계약의 세 매개 변수를 제공하여 지정할 수 있습니다. 제공할 수 있는 다른 매개 변수로는 동작 구성, 헤더 및 수신 대기 URI 등이 있습니다. 일부 경우에는 주소, 바인딩 및 계약의 일부 또는 모두에 변경할 수 없는 값이 있을 수 있습니다. 이러한 이유로 표준 끝점을 사용할 수 있습니다. 이러한 끝점의 몇 가지 예로는 메타데이터 교환 끝점과 검색 끝점이 있습니다. 표준 끝점을 사용하면 고정 특성의 정보를 제공하거나 고유한 표준 끝점을 만들 필요 없이 서비스 끝점의 구성을 그대로 사용하여 유용성을 향상시킬 수도 있습니다. 예를 들어 적절한 기본값 집합을 제공하여 구성 파일의 복잡성을 줄임으로써 유용성을 향상시킬 수 있습니다.  
  
 이 샘플은 두 개의 표준 끝점을 정의하는 서비스 및 이 서비스와 통신하는 클라이언트의 두 프로젝트로 구성되어 있습니다. 구성 파일에서 서비스에 대한 표준 끝점이 정의되는 방법은 다음 예제와 같습니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <endpointExtensions>  
        <add name="customEndpoint" type="Microsoft.Samples.StandardEndpoints.CustomEndpointCollectionElement, service" />  
      </endpointExtensions>  
    </extensions>  
    <services>  
      <service name="Microsoft.Samples.StandardEndpoints.CalculatorService">  
        <endpoint address="http://localhost:8000/Samples/Service.svc/customEndpoint" contract="Microsoft.Samples.StandardEndpoints.ICalculator" kind="customEndpoint" />  
        <endpoint kind="mexEndpoint" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <standardEndpoints>  
      <customEndpoint>  
        <standardEndpoint property="True" />  
      </customEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
</configuration>  
```  
  
 서비스에 대해 정의되는 첫 번째 끝점은 `customEndpoint` 종류로, `<standardEndpoints>` 섹션에서 해당 정의를 볼 수 있으며 `property` 속성 값은 `true`로 지정됩니다. 이 끝점은 새 속성으로 사용자 지정된 끝점입니다. 두 번째 끝점은 주소, 바인딩 및 계약의 값이 고정된 메타데이터 끝점에 해당합니다.  
  
 표준 끝점 요소를 정의하려면 `StandardEndpointElement`에서 파생된 클래스를 만들어야 합니다. 이 샘플에서는 `CustomEndpointElement`가 다음 예제와 같이 정의되었습니다.  
  
```csharp  
public class CustomEndpointElement : StandardEndpointElement  
{  
    public bool Property  
    {  
        get { return (bool)base["property"]; }  
        set { base["property"] = value; }  
    }  
  
    protected override ConfigurationPropertyCollection Properties  
    {  
        get  
        {  
            ConfigurationPropertyCollection properties = base.Properties;  
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));  
            return properties;  
        }  
    }  
  
    protected override Type EndpointType  
    {  
        get { return typeof(CustomEndpoint); }  
    }  
  
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)  
    {  
        return new CustomEndpoint();  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
    {  
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;  
        customEndpoint.Property = this.Property;  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
    {  
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;  
        customEndpoint.Property = this.Property;  
    }  
  
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
    {  
    }  
}  
```  
  
 `CreateServiceEndpoint` 함수에서는 `CustomEndpoint` 개체가 만들어집니다. 해당 정의는 다음 예제와 같습니다.  
  
```  
public class CustomEndpoint : ServiceEndpoint  
    {  
        public CustomEndpoint()  
            : this(string.Empty)  
        {  
        }  
  
        public CustomEndpoint(string address)  
            : this(address, ContractDescription.GetContract(typeof(ICalculator)))  
        {  
        }  
  
        public CustomEndpoint(string address, ContractDescription contract)  
            : base(contract)  
        {  
            this.Binding = new BasicHttpBinding();  
            this.IsSystemEndpoint = false;  
        }  
  
        public bool Property  
        {  
            get;  
            set;  
        }  
    }  
```  
  
 서비스와 클라이언트 간의 통신을 수행하기 위해 서비스에 대한 서비스 참조가 클라이언트에 만들어집니다. 샘플이 빌드되어 실행되면 서비스가 실행되고 클라이언트가 서비스와 통신합니다. 서비스 참조는 서비스에 변경 사항이 있을 때마다 업데이트해야 합니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 StandardEndpoints.sln 파일을 엽니다.  
  
2.  여러 개의 프로젝트가 시작되도록 설정합니다.  
  
    1.  **솔루션 탐색기**을 Standard Endpoints 솔루션을 마우스 오른쪽 단추로 클릭 한 다음 선택 **속성**합니다.  
  
    2.  **공용 속성**선택, **시작 프로젝트**, 클릭 하 고 **여러 개의 시작 프로젝트**합니다.  
  
    3.  와 함께 서비스 프로젝트를 목록의 시작 부분으로 이동 된 **동작** 로 설정 **시작**합니다.  
  
    4.  와 함께 클라이언트 프로젝트를 Service 프로젝트 다음에 이동는 **동작** 로 설정 **시작**합니다.  
  
         이렇게 하면 Client 프로젝트가 Service 프로젝트 다음에 실행됩니다.  
  
3.  F5 키를 눌러 솔루션을 실행합니다.  
  
> [!NOTE]
>  이러한 단계가 제대로 수행되지 않으면 다음 단계를 따라 사용 환경이 올바르게 설정되었는지 확인하세요.  
>   
>  1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
> 2.  지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
> 3.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\StandardEndpoints`  
  
## <a name="see-also"></a>참고 항목
