---
title: "방법: 구성을 사용하지 않고 ASP.NET AJAX 끝점 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# 방법: 구성을 사용하지 않고 ASP.NET AJAX 끝점 추가
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 통해 클라이언트 웹 사이트의 JavaScript에서 호출할 수 있는 ASP.NET AJAX 사용 끝점을 노출하는 서비스를 만들 수 있습니다. 이와 같은 끝점을 만들려면 다른 모든 WCF 끝점에서처럼 구성 파일을 사용하거나 구성 요소가 필요하지 않은 메서드를 사용할 수 있습니다. 이 항목에서는 두 번째 접근 방법을 보여 줍니다.  
  
 구성 없이 ASP.NET AJAX 끝점을 사용하여 서비스를 만들려면 서비스는 IIS(인터넷 정보 서비스)에 의해 호스팅되어야 합니다. 이 방법을 사용 하 여 ASP.NET AJAX 끝점을 활성화 하려면 지정는 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 팩터리 매개 변수로 [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) .svc 파일에 지시문입니다. 이 사용자 지정 팩터리는 클라이언트 웹 사이트의 JavaScript에서 호출할 수 있도록 ASP.NET AJAX 끝점을 자동으로 구성하는 구성 요소입니다.  
  
 작업 예제를 참조 하십시오.는 [구성 하지 않고 AJAX 서비스](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md)합니다.  
  
 구성 요소를 사용 하 여 ASP.NET AJAX 끝점을 구성 하는 방법의 개요를 참조 하십시오. [하는 방법: 구성을 사용 하는 ASP.NET AJAX 끝점 추가](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)합니다.  
  
### <a name="to-create-a-basic-wcf-service"></a>기본 WCF 서비스를 만들려면  
  
1.  기본 정의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 으로 서비스 계약 인터페이스와 함께 표시는 <xref:System.ServiceModel.ServiceContractAttribute> 특성입니다. 표시 된 각 작업은 <xref:System.ServiceModel.OperationContractAttribute>합니다. 로 설정 해야는 <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> 속성입니다.  
  
    ```  
    [ServiceContract(Namespace = "MyService")]]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2.  `ICalculator`를 사용하여 `CalculatorService` 서비스 계약을 구현합니다.  
  
    ```  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3.  네임스페이스 블록에 `ICalculator` 및 `CalculatorService` 구현을 래핑하여 이러한 구현에 대한 네임스페이스를 정의합니다.  
  
    ```  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a>구성 없이 인터넷 정보 서비스에서 서비스를 호스팅하려면  
  
1.  응용 프로그램에서 .svc 확장명이 있는 service라는 새 파일을 만듭니다. 적절 한 추가 하 여이 파일을 편집 [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 서비스에 대 한 지시문 정보입니다. 지정 하는 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 에 사용 되는 [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 지시문을 자동으로 ASP.NET AJAX 끝점을 구성 합니다.  
  
    ```  
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2.  서비스를 빌드하고 클라이언트에서 호출합니다. 호출하면 IIS(인터넷 정보 서비스)가 해당 서비스를 활성화합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]IIS에서 호스팅 참조 [하는 방법: IIS에서 WCF 서비스 호스팅](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)합니다.  
  
### <a name="to-call-the-service"></a>서비스를 호출하려면  
  
1.  따라서 서비스를 사용할 수 있으며 요청을 보내서 전송 하 여 호출할 수 있습니다 끝점은.svc 파일을 기준으로 빈 주소에 구성 됩니다<> \</> \> service.svc/Add에 대 한 예는 `Add` 작업 합니다. 서비스 URL을 ASP.NET AJAX Script Manager 컨트롤의 스크립트 컬렉션에 입력하여 사용할 수 있습니다. 예를 들어 참조는 [구성 하지 않고 AJAX 서비스](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md)합니다.  
  
## <a name="example"></a>예제  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
 자동으로 구성된 끝점은 기본 URL을 기준으로 비어 있는 주소에 생성됩니다. 또한 구성 파일을 추가하여 이 접근 방법으로 사용할 수 있습니다. 구성 파일에 끝점 정의가 포함된 경우 이러한 끝점은 자동으로 구성된 끝점에 추가됩니다.  
  
 예를 들어, service.svc 사용는 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 서비스 디렉터리 사용 하 여 동일한 서비스에 대 한 끝점을 정의 하는 Web.config 파일을 포함 하 고는 <xref:System.ServiceModel.BasicHttpBinding> "soap" 상대 주소에 있습니다. 이 경우 서비스는 두 개의 끝점을 포함합니다. 한 끝점은 ASP.NET AJAX 요청에 응답하는 service.svc에 위치하고 다른 끝점은 SOAP 요청에 응답하는 service.svc/soap에 위치합니다.  
  
 구성 파일이 비어 있는 상대 주소에 끝점을 정의 하는 경우와 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 되는 예외가 throw 되 고 서비스가 시작 되지 않거나 사용 합니다.  
  
 구성을 사용하여 자동으로 구성된 끝점에서 설정을 수정할 수 없습니다. 모든 설정 (예: 판독기 할당량) 해야 하는 경우 수정에 사용 하면 안 구성 않는 접근 방법을 제거 하 여는 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 끝점에 대 한 구성 항목을 만들어.svc 파일에서.  
  
 서비스에 필요한 경우 ASP.NET 호환 모드-예를 들어 사용 하는 경우는 <xref:System.Web.HttpContext> 클래스 또는 ASP.NET 인증 메커니즘에서 구성 파일을이 모드를 설정 하는 데 필요 합니다. 필요한 구성 요소는 [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 요소를 다음과 같이 추가 되어야 합니다.  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled=”true” /> </system.serviceModel>`  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][WCF 서비스 및 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) 항목입니다.  
  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 클래스의 파생된 클래스는 <xref:System.ServiceModel.Activation.ServiceHostFactory>합니다. 서비스 호스트 팩터리 메커니즘에 대 한 자세한 내용은 참조 하십시오.는 [호스팅를 사용 하 여 ServiceHostFactory 확장](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) 항목입니다.  
  
## <a name="see-also"></a>참고 항목  
 [ASP.NET AJAX 용 WCF 서비스 만들기](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)   
 [방법: AJAX 사용 ASP.NET 웹 서비스를 WCF로 마이그레이션](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)