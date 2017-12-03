---
title: "방법: ASP.NET AJAX 끝점에 대해 HTTP POST 및 HTTP GET 요청 중에서 선택"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 340f06c760ec4af6427343578790a8dad2d5dd62
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a><span data-ttu-id="43d73-102">방법: ASP.NET AJAX 끝점에 대해 HTTP POST 및 HTTP GET 요청 중에서 선택</span><span class="sxs-lookup"><span data-stu-id="43d73-102">How to: Choose between HTTP POST and HTTP GET requests for ASP.NET AJAX Endpoints</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="43d73-103">를 통해 클라이언트 웹 사이트의 JavaScript에서 호출할 수 있는 ASP.NET AJAX 사용 끝점을 노출하는 서비스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-103"> allows you to create a service that exposes an ASP.NET AJAX-enabled endpoint that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="43d73-104">이러한 서비스를 구축 하기 위한 기본 절차에 대해서는 설명 [하는 방법: ASP.NET AJAX 끝점 추가를 사용 하 여 구성](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) 및 [하는 방법: ASP.NET AJAX 끝점 하지 않고 사용 하 여 구성을 추가](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-104">The basic procedures for building such services is discussed in [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) and [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>  
  
 <span data-ttu-id="43d73-105">ASP.NET AJAX는 HTTP POST 및 HTTP GET 동사를 사용하며 기본값이 HTTP POST인 작업을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-105">ASP.NET AJAX supports operations that use the HTTP POST and HTTP GET verbs, with HTTP POST being the default.</span></span> <span data-ttu-id="43d73-106">파생 작업이 없으며 거의 또는 절대 변경되지 않는 데이터를 반환하는 작업을 만드는 경우 대신 HTTP GET을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-106">When creating an operation that has no side effects and returns data that rarely or never changes, use HTTP GET instead.</span></span> <span data-ttu-id="43d73-107">GET 작업 결과를 캐시할 수 있습니다. 즉, 동일한 작업에 대해 여러 번 호출하더라도 서비스에 대해 하나의 요청만 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-107">Results of GET operations can be cached, which means that multiple calls to the same operation may result in only one request to your service.</span></span> <span data-ttu-id="43d73-108">캐싱은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 수행되지 않지만 모든 수준(사용자 브라우저, 프록시 서버 및 기타 수준)에서 수행될 수 있습니다. 캐싱은 서비스 성능을 향상시키려는 경우 유용하지만 데이터를 자주 변경하거나 작업에서 동작을 수행하는 경우 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-108">The caching is not done by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] but can take place at any level (in a user's browser, on a proxy server, and other levels.) Caching is advantageous if you want to increase service performance, but may not be acceptable if data changes frequently or if the operation performs some action.</span></span>  
  
 <span data-ttu-id="43d73-109">예를 들어, 사용자의 음악 라이브러리를 관리하기 위해 서비스를 디자인하는 경우 앨범 제목에 기초하여 아티스트를 조회하는 작업에서는 GET을 사용함으로써 이점을 얻을 수 있지만, 앨범을 사용자의 개인 컬렉션에 추가하는 작업에서는 POST를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-109">For example, if you are designing service to manage a user's music library, an operation that looks up the artist based on an album's title benefits from using GET, but an operation that adds an album to the user's personal collection must use POST.</span></span>  
  
 <span data-ttu-id="43d73-110">캐시 수명을 제어하려면 <xref:System.ServiceModel.Web.OutgoingWebResponseContext> 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-110">To control the lifetime of the cache, use the <xref:System.ServiceModel.Web.OutgoingWebResponseContext> type.</span></span> <span data-ttu-id="43d73-111">예를 들어, 시간별로 업데이트되는 일기 예보를 반환하는 서비스를 디자인하는 경우 GET을 사용할 수 있지만 캐시 기간을 1시간 이하로 제한하여 서비스 사용자가 오래된 데이터에 액세스하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-111">For example, when designing a service that returns weather forecasts updated hourly, you would use GET but limit the cache duration to an hour or less to prevent the users of the service from accessing stale data.</span></span>  
  
 <span data-ttu-id="43d73-112">Script Manager 컨트롤이 사용하는 ASP.NET AJAX 페이지에서 서비스를 사용하는 경우 작업에서 GET을 사용하든지 POST를 사용하든지 차이가 없습니다. 스크립트 관리자 메커니즘은 올바른 요청 형식이 발급되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-112">When using services from an ASP.NET AJAX page that use the Script Manager control, it makes no difference whether the operation uses GET or POST - the script manager mechanism ensures that the correct request type is issued.</span></span>  
  
 <span data-ttu-id="43d73-113">HTTP GET 작업은 복합 데이터 계약 형식을 비롯한 POST 작업에서 지원하는 입력 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-113">HTTP GET operations use any input parameters supported by POST operations, including complex data contract types.</span></span> <span data-ttu-id="43d73-114">그러나 대부분의 경우 캐싱 효율성이 떨어지기 때문에 너무 많은 매개 변수 또는 GET 작업에 있어서 너무 복잡한 매개 변수는 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-114">However, in most cases it is recommended to avoid too many parameters or parameters that are too complex in GET operations because it reduces caching efficiency.</span></span>  
  
 <span data-ttu-id="43d73-115">이 항목에서는 <xref:System.ServiceModel.Web.WebGetAttribute> 또는 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성을 서비스 계약의 관련 작업에 추가하여 GET과 POST 중에 하나를 선택하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-115">This topic demonstrates how to select between GET and POST by adding the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to the relevant operations in the service contract.</span></span> <span data-ttu-id="43d73-116">서비스를 실행하는 데 필요한 기타 단계(서비스 구현, 구성 및 호스팅)는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 ASP.NET AJAX 서비스에서 사용하는 단계와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-116">The other steps (to implement, configure and host the service) that are required to get the service running are similar to those used by any ASP.NET AJAX service in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="43d73-117"><xref:System.ServiceModel.Web.WebGetAttribute>로 표시된 작업은 항상 GET 요청을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-117">An operation marked with the <xref:System.ServiceModel.Web.WebGetAttribute> always uses a GET request.</span></span> <span data-ttu-id="43d73-118"><xref:System.ServiceModel.Web.WebInvokeAttribute>로 표시된 작업 또는 두 개의 특성으로 표시되지 않은 작업은 POST 요청을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-118">An operation marked with the <xref:System.ServiceModel.Web.WebInvokeAttribute>, or not marked with any of the two attributes, uses a POST request.</span></span> <span data-ttu-id="43d73-119"><xref:System.ServiceModel.Web.WebInvokeAttribute>를 사용하면 <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> 속성을 통해 GET과 POST 이외의 다른 HTTP 동사(예: PUT 및 DELETE)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-119">The <xref:System.ServiceModel.Web.WebInvokeAttribute> allows the use of other HTTP verbs, other than GET and POST (such as PUT and DELETE) through the <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> property.</span></span> <span data-ttu-id="43d73-120">그러나 이러한 동사는 ASP.NET AJAX에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-120">However, these verbs are not supported by ASP.NET AJAX.</span></span> <span data-ttu-id="43d73-121">Script Manager 컨트롤을 사용하여 ASP.NET 페이지에서 서비스를 사용하려면 <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> 속성을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="43d73-121">If you intend to use the service from ASP.NET pages using the Script Manager control, do not use the <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> property.</span></span>  
  
 <span data-ttu-id="43d73-122">GET으로 전환 하는 작업 예제를 참조 하십시오.는 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="43d73-122">For a working example of switching to GET, see the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="43d73-123">POST를 사용 하는 샘플에 대 한 참조는 [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="43d73-123">For a sample that uses POST, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) sample.</span></span>  
  
### <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a><span data-ttu-id="43d73-124">HTTP GET 또는 HTTP POST 요청에 대해 응답하는 WCF 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="43d73-124">To create a WCF service that responds to HTTP GET or HTTP POST requests</span></span>  
  
1.  <span data-ttu-id="43d73-125">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 특성으로 표시된 인터페이스를 사용하여 기본 <xref:System.ServiceModel.ServiceContractAttribute> 서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-125">Define a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="43d73-126">각 작업을 <xref:System.ServiceModel.OperationContractAttribute>로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-126">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="43d73-127"><xref:System.ServiceModel.Web.WebGetAttribute> 특성을 추가하여 작업이 HTTP GET 요청에 응답하도록 규정합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-127">Add the <xref:System.ServiceModel.Web.WebGetAttribute> attribute to stipulate that an operation should respond to HTTP GET requests.</span></span> <span data-ttu-id="43d73-128">또한 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성을 추가하여 명시적으로 HTTP POST를 지정할 수 있습니다. 특성을 지정하지 않으면 기본적으로 HTTP POST로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-128">You can also add the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute to explicitly specify HTTP POST, or not specify an attribute, which defaults to HTTP POST.</span></span>  
  
    ```  
    [ServiceContract]  
    public interface IMusicService  
    {  
        //This operation uses a GET method.  
        [OperationContract]  
        [WebGet]  
        string LookUpArtist(string album);  
  
        //This operation will use a POST method.  
        [OperationContract]  
        [WebInvoke]  
        void AddAlbum(string user, string album);  
  
        //This operation will use POST method by default  
        //since nothing else is explicitly specified.  
        [OperationContract]  
        string[] GetAlbums(string user);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2.  <span data-ttu-id="43d73-129">`IMusicService`를 사용하여 `MusicService` 서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-129">Implement the `IMusicService` service contract with a `MusicService`.</span></span>  
  
    ```  
    public class MusicService : IMusicService  
    {  
        public void AddAlbum(string user, string album)  
        {  
            //Add implementation here.  
        }  
  
         //Other operations omitted…  
    }  
    ```  
  
3.  <span data-ttu-id="43d73-130">응용 프로그램에서 .svc 확장명이 있는 service라는 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-130">Create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="43d73-131">적절 한 추가 하 여이 파일을 편집 [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 서비스에 대 한 지시문 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-131">Edit this file by adding the appropriate [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="43d73-132">지정 하는 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 에 사용 되는 [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 지시문을 자동으로 ASP.NET AJAX 끝점을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-132">Specify that the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is to be used in the [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive to automatically configure an ASP.NET AJAX endpoint.</span></span>  
  
    ```  
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
### <a name="to-call-the-service"></a><span data-ttu-id="43d73-133">서비스를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="43d73-133">To call the service</span></span>  
  
1.  <span data-ttu-id="43d73-134">브라우저를 사용하여 클라이언트 코드 없이 서비스의 GET 작업을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-134">You can test your service's GET operations without any client code, by using the browser.</span></span> <span data-ttu-id="43d73-135">예를 들어, 서비스가 "http://example.com/service.svc" 주소에 구성된 경우 브라우저 주소 표시줄에 "http://example.com/service.svc/LookUpArtist?album=SomeAlbum"을 입력하면 서비스가 호출되고 응답이 다운로드되거나 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-135">For example, if your service is configured at the "http://example.com/service.svc" address, then typing "http://example.com/service.svc/LookUpArtist?album=SomeAlbum" into the browser address bar invokes the service and causes the response to be downloaded or displayed.</span></span>  
  
2.  <span data-ttu-id="43d73-136">ASP.NET AJAX Script Manager 컨트롤의 스크립트 컬렉션에 서비스 URL을 입력하여 다른 ASP.NET AJAX 서비스와 동일한 방법으로 GET 작업을 통해 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-136">You can use services with GET operations in the same way as any other ASP.NET AJAX services - by entering the service URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="43d73-137">예를 들어 참조는 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="43d73-137">For an example, see the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43d73-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43d73-138">See Also</span></span>  
 [<span data-ttu-id="43d73-139">ASP.NET AJAX 용 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="43d73-139">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 [<span data-ttu-id="43d73-140">방법: AJAX 사용 ASP.NET 웹 서비스를 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="43d73-140">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
