---
title: System.Web.Routing 통합
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: 5bd405d66dcad597bbe6f452703d25372fdb7682
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498025"
---
# <a name="systemwebrouting-integration"></a><span data-ttu-id="5aef8-102">System.Web.Routing 통합</span><span class="sxs-lookup"><span data-stu-id="5aef8-102">System.Web.Routing Integration</span></span>
<span data-ttu-id="5aef8-103">Windows Communication Foundation (WCF) 서비스를 인터넷 정보 서비스 (IIS)에서 호스트할 때 가상 디렉터리에.svc 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aef8-103">When hosting a Windows Communication Foundation (WCF) service in Internet Information Service (IIS) you place a .svc file in the virtual directory.</span></span> <span data-ttu-id="5aef8-104">이 .svc 파일은 사용할 서비스 호스트 팩터리와 함께 서비스를 구현하는 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5aef8-104">This .svc file specifies the service host factory to use as well as the class that implements the service.</span></span> <span data-ttu-id="5aef8-105">때 서비스에 대 한 요청.svc 파일의에서 지정 된 URI, 예: http://contoso.com/EmployeeServce.svc합니다.</span><span class="sxs-lookup"><span data-stu-id="5aef8-105">When making requests to the service you specify the .svc file in the URI, for example: http://contoso.com/EmployeeServce.svc.</span></span> <span data-ttu-id="5aef8-106">REST 서비스를 작성하는 프로그래머에게는 이러한 유형의 URI가 적합하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5aef8-106">For programmers writing REST services this type of URI is not optimal.</span></span> <span data-ttu-id="5aef8-107">REST 서비스의 URI는 특정 리소스를 지정하며 일반적으로 확장명을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5aef8-107">URIs for REST services specify a specific resource and normally do not have any extensions.</span></span> <span data-ttu-id="5aef8-108"><xref:System.Web.Routing> 통합 기능을 사용 하면 확장이 없는 Uri에 응답 하는 WCF REST 서비스를 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5aef8-108">The <xref:System.Web.Routing> integration feature allows you to host a WCF REST service that responds to URIs without an extension.</span></span> <span data-ttu-id="5aef8-109">라우팅 참조에 대 한 자세한 내용은 [ASP.NET 라우팅](http://go.microsoft.com/fwlink/?LinkId=184660) 및 [AspNetRouteIntegration](../../../../docs/framework/wcf/samples/aspnetrouteintegration.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="5aef8-109">For more information about routing see [ASP.NET Routing](http://go.microsoft.com/fwlink/?LinkId=184660) and the [AspNetRouteIntegration](../../../../docs/framework/wcf/samples/aspnetrouteintegration.md) sample.</span></span>  
  
## <a name="using-systemwebrouting-integration"></a><span data-ttu-id="5aef8-110">System.Web.Routing 통합 사용</span><span class="sxs-lookup"><span data-stu-id="5aef8-110">Using System.Web.Routing Integration</span></span>  
 <span data-ttu-id="5aef8-111"><xref:System.Web.Routing> 통합 기능을 사용하려면 <xref:System.ServiceModel.Activation.ServiceRoute> 클래스를 사용하여 하나 이상의 경로를 만들어 Global.asax 파일의 <xref:System.Web.Routing.RouteTable>에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5aef8-111">To use the <xref:System.Web.Routing> integration feature, you use the <xref:System.ServiceModel.Activation.ServiceRoute> class to create one or more routes and add them to the <xref:System.Web.Routing.RouteTable> in a Global.asax file.</span></span> <span data-ttu-id="5aef8-112">이러한 경로는 서비스가 응답하는 상대 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5aef8-112">These routes specify the relative URIs that the service responds to.</span></span> <span data-ttu-id="5aef8-113">다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5aef8-113">The following example shows how to do this.</span></span>  
  
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
  
 <span data-ttu-id="5aef8-114">그러면 Customers로 시작하는 상대 URI가 있는 모든 요청이 `Service` 서비스에 라우트됩니다.</span><span class="sxs-lookup"><span data-stu-id="5aef8-114">This routes all requests with a relative URI that begins with Customers to the `Service` service.</span></span>  
  
 <span data-ttu-id="5aef8-115">Web.config 파일에서는 다음 예제와 같이 `System.Web.Routing.UrlRoutingModule` 모듈을 설정하고, `runAllManagedModulesForAllRequests` 특성을 `true`로 설정하고, `UrlRoutingHandler` 요소에 `<system.webServer>` 처리기를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aef8-115">In your Web.config file you must add the `System.Web.Routing.UrlRoutingModule` module, set the `runAllManagedModulesForAllRequests` attribute to `true`, and add the `UrlRoutingHandler` handler to the `<system.webServer>` element as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="5aef8-116">그러면 라우팅에 필요한 모듈과 처리기가 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="5aef8-116">This loads a module and handler required for routing.</span></span> <span data-ttu-id="5aef8-117">자세한 내용은 [라우팅](../../../../docs/framework/wcf/feature-details/routing.md)을 참고하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="5aef8-117">For more information, see [Routing](../../../../docs/framework/wcf/feature-details/routing.md).</span></span> <span data-ttu-id="5aef8-118">또한 다음 예제와 같이 `aspNetCompatibilityEnabled` 요소의 `true` 특성도 `<serviceHostingEnvironment>`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aef8-118">You must also set the `aspNetCompatibilityEnabled` attribute to `true` in the `<serviceHostingEnvironment>` element as shown in the following example.</span></span>  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 <span data-ttu-id="5aef8-119">서비스를 구현하는 클래스에서는 다음 예제와 같이 ASP.NET 호환성 요구 사항을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5aef8-119">The class that implements the service must enable ASP.NET compatibility requirements as shown in the following example.</span></span>  
  
```  
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="5aef8-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5aef8-120">See Also</span></span>  
 [<span data-ttu-id="5aef8-121">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="5aef8-121">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="5aef8-122">ASP.NET 라우팅</span><span class="sxs-lookup"><span data-stu-id="5aef8-122">ASP.NET Routing</span></span>](http://go.microsoft.com/fwlink/?LinkId=184660)
