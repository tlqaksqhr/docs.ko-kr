---
title: "System.Web.Routing 통합 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# System.Web.Routing 통합
IIS\(인터넷 정보 서비스\)에서 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 호스팅하는 경우 가상 디렉터리에 .svc 파일을 저장합니다.이 .svc 파일은 사용할 서비스 호스트 팩터리와 함께 서비스를 구현하는 클래스를 지정합니다.서비스를 요청할 때는 http:\/\/contoso.com\/EmployeeServce.svc와 같은 URI를 사용하여 .svc 파일을 지정합니다.REST 서비스를 작성하는 프로그래머에게는 이러한 유형의 URI가 적합하지 않을 수 있습니다.REST 서비스의 URI는 특정 리소스를 지정하며 일반적으로 확장을 포함하지 않습니다.<xref:System.Web.Routing> 통합 기능을 사용하면 확장이 없는 URI에 응답하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST 서비스를 호스팅할 수 있습니다.라우팅에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [ASP.NET 라우팅](http://go.microsoft.com/fwlink/?LinkId=184660)\(영문 페이지일 수 있음\) 및 [AspNetRouteIntegration](../../../../docs/framework/wcf/samples/aspnetrouteintegration.md) 샘플을 참조하십시오.  
  
## System.Web.Routing 통합 사용  
 <xref:System.Web.Routing> 통합 기능을 사용하려면 <xref:System.ServiceModel.Activation.ServiceRoute> 클래스를 사용하여 하나 이상의 경로를 만들어 Global.asax 파일의 <xref:System.Web.Routing.RouteTable>에 추가합니다.이러한 경로는 서비스가 응답하는 상대 URI를 지정합니다.다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
```  
<%@ Application Language="C#" %>  
<%@ Import Namespace="System.Web.Routing" %>  
<%@ Import Namespace="System.ServiceModel.Activation" %>  
<%@ Import Namespace="System.ServiceModel.Web " %>  
  
<script RunAt="server">  
    void Application_Start(object sender, EventArgs e)  
    {  
        RegisterRoutes(RouteTable.Routes);  
    }  
  
    private void RegisterRoutes(RouteCollection routes)  
    {  
        routes.Add(new ServiceRoute("Customers", new WebServiceHostFactory(), typeof(Service)));   
   }  
</script>  
  
```  
  
 그러면 Customers로 시작하는 상대 URI가 있는 모든 요청이 `Service` 서비스에 라우트됩니다.  
  
 Web.config 파일에서는 다음 예제와 같이 `System.Web.Routing.UrlRoutingModule` 모듈을 설정하고, `runAllManagedModulesForAllRequests` 특성을 `true`로 설정하고, `<system.webServer>` 요소에 `UrlRoutingHandler` 처리기를 추가해야 합니다.  
  
```xml  
<system.webServer>  
      <modules runAllManagedModulesForAllRequests="true">  
        <add name="UrlRoutingModule" type="System.Web.Routing.UrlRoutingModule, System.Web, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" />  
      </modules>  
      <handlers>  
        <add name="UrlRoutingHandler" preCondition="integratedMode" verb="*" path="UrlRouting.axd"/>  
      </handlers>  
    </system.webServer>  
```  
  
 그러면 라우팅에 필요한 모듈과 처리기가 로드됩니다.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][라우팅](../../../../docs/framework/wcf/feature-details/routing.md).또한 다음 예제와 같이 `<serviceHostingEnvironment>` 요소의 `aspNetCompatibilityEnabled` 특성도 `true`로 설정해야 합니다.  
  
```  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 서비스를 구현하는 클래스에서는 다음 예제와 같이 ASP.NET 호환성 요구 사항을 사용하도록 설정해야 합니다.  
  
```  
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## 참고 항목  
 [WCF 웹 HTTP 프로그래밍 모델](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)   
 [ASP.NET 라우팅](http://go.microsoft.com/fwlink/?LinkId=184660)