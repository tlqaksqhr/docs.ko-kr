---
title: 보안 유효성 검사
ms.date: 03/30/2017
ms.assetid: 48dcd496-0c4f-48ce-8b9b-0e25b77ffa58
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: f77b01633f214d3a8c4ad8d7226375c3ed2368fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33504386"
---
# <a name="security-validation"></a>보안 유효성 검사
이 샘플에서는 사용자 지정 동작을 통해 컴퓨터에 있는 서비스의 유효성을 검사하여 특정 기준을 충족하는지 확인하는 방법을 보여 줍니다. 이 샘플에서는 서비스의 각 끝점을 검사하여 보안 바인딩 요소가 포함되어 있는지 확인하는 방식으로 사용자 지정 동작을 통해 서비스의 유효성을 검사합니다. 이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
## <a name="endpoint-validation-custom-behavior"></a>끝점 유효성 검사 사용자 지정 동작  
 `Validate` 인터페이스에 포함된 <xref:System.ServiceModel.Description.IServiceBehavior> 메서드에 사용자 코드를 추가함으로써 서비스 또는 끝점에 사용자 지정 동작을 제공하여 사용자 정의 작업을 수행할 수 있습니다. 다음 코드는 서비스에 포함된 각 끝점을 루프하여 바인딩 컬렉션에서 보안 바인딩을 검색하는 데 사용됩니다.  
  
```  
public void Validate(ServiceDescription serviceDescription,   
                                       ServiceHostBase serviceHostBase)  
{  
    // Loop through each endpoint individually gathering their    
       binding elements.  
    foreach (ServiceEndpoint endpoint in serviceDescription.Endpoints)  
    {  
        secureElementFound = false;  
  
        // Retrieve the endpoint's binding element collection.  
        BindingElementCollection bindingElements =   
            endpoint.Binding.CreateBindingElements();  
  
        // Look to see if the binding elements collection contains any   
        // secure binding elements. Transport, Asymmetric, and Symmetric      
        // binding elements are all derived from SecurityBindingElement.  
        if ((bindingElements.Find<SecurityBindingElement>() != null) || (bindingElements.Find<HttpsTransportBindingElement>() != null) || (bindingElements.Find<WindowsStreamSecurityBindingElement>() != null) || (bindingElements.Find<SslStreamSecurityBindingElement>() != null))  
        {  
            secureElementFound = true;  
        }  
  
    // Send a message to the system event viewer when an endpoint is deemed insecure.  
    if (!secureElementFound)  
        throw new Exception(System.DateTime.Now.ToString() + ": The endpoint \"" + endpoint.Name + "\" has no secure bindings.");  
    }  
}  
```  
  
 Web.config 파일에 다음 코드를 추가하면 서비스가 인식할 수 있는 `serviceValidate` 동작 확장이 추가됩니다.  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="endpointValidate" type="Microsoft.ServiceModel.Samples.EndpointValidateElement, endpointValidate, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </behaviorExtensions>  
    </extensions>  
...  
```  
  
 동작 확장이 서비스에 추가되었으면 Web.config 파일의 동작 목록과 서비스에 `endpointValidate` 동작을 추가할 수 있습니다.  
  
```xml  
<behaviors>  
    <serviceBehaviors>  
        <behavior name="CalcServiceSEB1">  
            <serviceMetadata httpGetEnabled="true" />  
            <endpointValidate />  
        </behavior>  
    </serviceBehaviors>  
</behaviors>  
```  
  
 Web.config 파일에 추가된 동작 및 동작 확장은 개별 서비스에 동작을 적용하며, Machine.config 파일에 추가된 경우에는 컴퓨터의 모든 활성 서비스에 동작을 적용합니다.  
  
> [!NOTE]
>  모든 서비스에 동작을 추가할 경우에는 내용을 변경하기 전에 Machine.config 파일을 백업하는 것이 좋습니다.  
  
 이제 이 샘플의 client\bin 디렉터리에 제공된 클라이언트를 실행합니다. 예외는 다음 메시지와 함께 발생: "요청 된 서비스 'http://localhost/servicemodelsamples/service.svc' 활성화할 수 없습니다." 이 예외는 동작의 유효성을 검사하는 끝점에 의해 끝점이 안전하지 않은 것으로 간주되어 서비스가 시작하지 못하도록 하기 때문에 발생합니다. 이 동작은 또한 안전하지 않은 끝점을 설명하는 내부 예외를 throw하고 시스템 이벤트 뷰어의 "System.ServiceModel 4.0.0.0" 소스 및 "WebHost" 범주 아래에 메시지를 씁니다. 또한 이 샘플에서 서비스에 대한 추적을 켤 수 있습니다. 이 경우 사용자는 Service Trace Viewer 도구에서 결과 서비스 추적을 열어 동작의 유효성을 검사하는 끝점에서 throw한 예외를 볼 수 있습니다.  
  
#### <a name="to-view-failed-endpoint-validation-exception-messages-in-the-event-viewer"></a>이벤트 뷰어에서 실패한 끝점 유효성 검사 예외 메시지를 보려면  
  
1.  클릭는 **시작** 메뉴와 선택 **실행...** .  
  
2.  형식 `eventvwr` 클릭 **확인**합니다.  
  
3.  이벤트 뷰어 창에서 클릭 **응용 프로그램**합니다.  
  
4.  "WebHost" 범주 아래에서 최근에 추가 된 "System.ServiceModel 4.0.0.0" 이벤트를 두 번의 **응용 프로그램** 창 안전 하지 않은 끝점 메시지를 확인 합니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ServiceValidation`  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 모니터링 샘플](http://go.microsoft.com/fwlink/?LinkId=193959)
