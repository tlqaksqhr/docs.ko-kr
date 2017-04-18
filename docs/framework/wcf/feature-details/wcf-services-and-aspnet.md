---
title: "WCF 서비스 및 ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b980496a-f0b0-4319-8e55-a0f0fa32da70
caps.latest.revision: 24
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 24
---
# WCF 서비스 및 ASP.NET
이 항목에서는 ASP.NET과 함께 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 호스트하는 경우 및 ASP.NET 호환 모드에서 WCF 서비스를 호스트하는 경우에 대해 설명합니다.  
  
## ASP.NET과 함께 WCF 호스팅  
 IIS\(인터넷 정보 서비스\)에서 호스트되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 하나의 일반적인 응용 프로그램 도메인 내에 ASPX 웹 서비스 및 .ASPX 페이지와 함께 위치할 수 있습니다.  ASP.NET은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 ASP.NET HTTP 런타임 모두에 대해 AppDomain 관리 및 동적 컴파일과 같은 공통 인프라 서비스를 제공합니다.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 기본 구성은 ASP.NET과 함께 수행됩니다.  
  
 ![WCF 서비스 및 ASP.NET: 공유 상태](../../../../docs/framework/wcf/feature-details/media/hostingwcfwithaspnet.gif "HostingWCFwithASPNET")  
  
 ASP.NET HTTP 런타임은 ASP.NET 요청을 처리하지만 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 ASP.NET 내용과 동일한 AppDomain에서 호스트되더라도 이러한 서비스가 대상인 요청을 처리하는 작업에는 참여하지 않습니다.  대신 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 모델이 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 주소가 지정된 메시지를 가로채고 이러한 메시지를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 전송\/채널 스택을 통해 라우팅합니다.  
  
 동시 모델의 결과는 다음과 같습니다.  
  
-   ASP.NET 및 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 AppDomain 상태를 공유할 수 있습니다.  또한 두 개의 프레임워크가 동일한 AppDomain에 함께 있을 수 있기 때문에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 ASP.NET과 AppDomain 상태를 공유할 수 있습니다\(정적 변수, 이벤트 등 포함\).  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 호스팅 환경 및 전송과 독립적으로 일관성 있게 동작합니다.  ASP.NET HTTP 런타임은 IIS\/ASP.NET 호스팅 환경 및 HTTP 통신에 의도적으로 연결됩니다.  반대로, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 호스팅 환경에서 일관성 있게 동작하고\([!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 IIS 내부 및 외부 모두에서 일관성 있게 동작\) 전송을 통해 일관성 있게 동작하도록\(노출된 일부 끝점이 HTTP 이외의 프로토콜을 사용하더라도 IIS 7.0 이상에서 호스트되는 서비스는 노출된 모든 끝점에서 일관성 있게 동작\) 설계되었습니다.  
  
-   AppDomain 내에서 HTTP 런타임에 의해 구현되는 기능은 ASP.NET 내용에는 적용되지만 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에는 적용되지 않습니다.  ASP.NET 응용 프로그램 플랫폼의 많은 HTTP 관련 기능은 ASP.NET 내용이 포함된 AppDomain의 내부에서 호스트되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 적용되지 않습니다.  이러한 기능의 예는 다음과 같습니다.  
  
    -   HttpContext: <xref:System.Web.HttpContext.Current%2A>는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 내에서 액세스한 경우 항상 `null`입니다.  대신 <xref:System.ServiceModel.OperationContext.Current.RequestContext>를 사용하세요.  
  
    -   파일 기반 권한 부여: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 모델은 서비스 요청에 권한이 부여되어 있는지 여부를 확인할 때 서비스의 .svc 파일에 ACL\(액세스 제어 목록\)이 적용되는 것을 허용하지 않습니다.  
  
    -   구성 기반 URL 권한 부여: 마찬가지로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안 모델은 System.Web의 \<authorization\> 구성 요소에 지정된 URL 기반 권한 부여 규칙을 준수하지 않습니다.  이러한 설정은 서비스가 ASP.NET의 URL 권한 부여 규칙에 의해 보안이 유지되는 URL 공간에 있는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 요청에 대해 무시됩니다.  
  
    -   HttpModule 확장성: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 호스팅 인프라는 <xref:System.Web.HttpApplication.PostAuthenticateRequest> 이벤트가 발생하고 처리를 ASP.NET HTTP 파이프라인에 반환하지 않는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 요청을 가로챕니다.  파이프라인의 후반 단계에서 요청을 가로채도록 코딩된 모듈은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 요청을 가로채지 않습니다.  
  
    -   ASP.NET 가장: 기본적으로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 요청은 ASP.NET이 System.Web의 \<identity impersonate\=”true” \/\> 구성 옵션을 사용하여 가장을 활성화하도록 설정되더라도 항상 IIS 프로세스 ID로 실행됩니다.  
  
 이러한 제한 사항은 IIS 응용 프로그램에서 호스트되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에만 적용됩니다.  ASP.NET 내용의 동작은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 존재 유무에 영향을 받지 않습니다.  
  
 일반적으로 HTTP 파이프라인에서 제공되는 기능이 필요한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램은 다음과 같이 호스트 및 전송 독립적인 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 동일한 기능을 사용할지 고려해야 합니다.  
  
-   <xref:System.Web.HttpContext> 대신 <xref:System.ServiceModel.OperationContext> 사용  
  
-   ASP.NET의 File\/URL 권한 부여 대신 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> 사용  
  
-   HTTP 모듈 대신 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> 또는 사용자 지정 계층화된 채널 사용  
  
-   System.Web 가장 대신 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용하는 각 작업에 대한 가장 사용  
  
 또는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 ASP.NET 호환 모드에서 서비스를 실행할 것을 고려할 수 있습니다.  
  
## ASP.NET 호환 모드에서 WCF 서비스 호스팅  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 모델이 호스팅 환경 및 전송에서 일관성 있게 동작하도록 디자인되었지만 응용 프로그램이 이러한 수준의 유연성을 필요로 하지 않는 경우가 종종 있습니다.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 ASP.NET 호환 모드는 IIS 외부에서 호스트하거나 HTTP 이외의 프로토콜을 통해 통신하는 기능은 필요 없지만 ASP.NET 웹 응용 프로그램 플랫폼의 모든 기능을 사용하는 경우에 적합합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 호스팅 인프라가 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시지를 가로채고 HTTP 파이프라인에서 이러한 메시지를 라우트하는 기본 동시 구성과는 달리, ASP.NET 호환 모드에서 실행되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 ASP.NET HTTP 요청 수명에 완전히 참여합니다.  호환 모드에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 <xref:System.Web.IHttpHandler> 구현을 통해 HTTP 파이프라인을 사용하며, 이것은 ASPX 페이지 및 ASMX 웹 서비스의 요청이 처리되는 방법과 비슷합니다.  결과적으로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 다음 ASP.NET 기능과 관련하여 ASMX와 동일하게 동작합니다.  
  
-   <xref:System.Web.HttpContext>: ASP.NET 호환 모드에서 실행되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 <xref:System.Web.HttpContext.Current%2A> 및 연결된 상태에 액세스할 수 있습니다.  
  
-   파일 기반 권한 부여: ASP.NET 호환 모드에서 실행되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 파일 시스템 ACL\(액세스 제어 목록\)을 서비스의 .svc 파일에 첨부하여 보안을 유지할 수 있습니다.  
  
-   구성 가능한 URL 권한 부여: ASP.NET의 URL 권한 부여 규칙은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 ASP.NET 호환 모드에서 실행 중일 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 요청에 적용됩니다.  
  
-   <xref:System.Web.HttpModuleCollection> 확장성: ASP.NET 호환 모드에서 실행되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 ASP.NET HTTP 요청 수명에 완전히 참여하기 때문에 HTTP 파이프라인에서 구성된 모든 HTTP 모듈은 서비스 호출 이전 및 이후 모두 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 요청에 대해 작동할 수 있습니다.  
  
-   ASP.NET 가장: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 ASP.NET 가장 스레드의 현재 ID를 사용하여 실행되며, 이것은 ASP.NET 가장이 응용 프로그램에 대해 활성화된 경우 IIS 프로세스 ID와 다를 수 있습니다.  ASP.NET 가장 및 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 가장 모두 특정 서비스 작업에 대해 활성화되면 서비스 구현은 결국 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 가져온 ID를 사용하여 실행됩니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 ASP.NET 호환 모드는 다음 구성을 통해 응용 프로그램 수준에서 활성화됩니다\(응용 프로그램의 Web.config 파일에 위치\).  
  
```  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />  
</system.serviceModel>  
```  
  
 지정되지 않은 경우 이 기본값은 “`true`”로 설정됩니다.  이 값을 “`false`”로 설정하면 응용 프로그램에서 실행 중인 모든 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 ASP.NET 호환 모드에서 실행되지 않습니다.  
  
 ASP.NET 호환 모드는 기본적으로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 기본값과는 다른 요청 처리 의미 체계를 의미하기 때문에 개별 서비스 구현에는 ASP.NET 호환 모드가 활성화된 응용 프로그램 내에서 실행할지 여부를 제어하는 기능이 있습니다.  서비스는 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>를 사용하여 ASP.NET 호환 모드를 지원할지 여부를 나타낼 수 있습니다.  이 특성의 기본값은 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>입니다.  
  
 `[AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]`  
  
 `public class CalculatorService : ICalculatorSession`  
  
 `{//Implement calculator service methods.}`  
  
 다음 표에서는 응용 프로그램 수준의 호환 모드 설정이 개별 서비스에 명시된 지원 수준과 상호 작용하는 방법을 보여 줍니다.  
  
|응용 프로그램 수준의 호환 모드 설정|\[AspNetCompatibilityRequirementsMode\]<br /><br /> 설정|확인된 결과|  
|--------------------------|----------------------------------------------------|------------|  
|aspNetCompatibilityEnabled \= “`true`”|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>|서비스가 활성화됩니다.|  
|aspNetCompatibilityEnabled \= “`true`”|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>|서비스가 활성화됩니다.|  
|aspNetCompatibilityEnabled \= “`true`”|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>|서비스가 메시지를 수신할 때 활성화 오류가 발생합니다.|  
|aspNetCompatibilityEnabled \= “`false`”|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>|서비스가 메시지를 수신할 때 활성화 오류가 발생합니다.|  
|aspNetCompatibilityEnabled \= “`false`”|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>|서비스가 활성화됩니다.|  
|aspNetCompatibilityEnabled \= “`false`”|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>|서비스가 활성화됩니다.|  
  
> [!NOTE]
>  IIS 7.0 및 WAS를 사용하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 HTTP 이외의 프로토콜을 통해 통신할 수 있습니다.  그러나 ASP.NET 호환 모드를 사용하는 응용 프로그램에서 실행 중인 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 HTTP가 아닌 끝점을 노출할 수 없습니다.  이러한 구성은 서비스에서 첫 번째 메시지를 수신할 때 활성화 예외를 생성합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 대한 ASP.NET 호환 모드 사용에 대한 자세한 내용은 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> 및 [ASP.NET 호환성](../../../../docs/framework/wcf/samples/aspnet-compatibility.md) 샘플을 참조하세요.  
  
## 참고 항목  
 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>   
 [Windows Server App Fabric 호스팅 기능 \(영문\)](http://go.microsoft.com/fwlink/?LinkId=201276)