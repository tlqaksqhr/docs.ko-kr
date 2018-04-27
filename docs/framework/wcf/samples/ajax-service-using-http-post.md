---
title: AJAX Service Using HTTP POST
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1446fadeb249d91f0eb3e65b1155f00090441a5a
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="ajax-service-using-http-post"></a><span data-ttu-id="8a466-102">AJAX Service Using HTTP POST</span><span class="sxs-lookup"><span data-stu-id="8a466-102">AJAX Service Using HTTP POST</span></span>
<span data-ttu-id="8a466-103">이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하여 HTTP POST를 사용하는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] AJAX(Asynchronous JavaScript and XML) 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-103">This sample demonstrates how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to create an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Asynchronous JavaScript and XML (AJAX) service that uses HTTP POST.</span></span> <span data-ttu-id="8a466-104">AJAX 서비스는 웹 브라우저 클라이언트에서 기본 JavaScript 코드를 사용하여 액세스할 수 있는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-104">An AJAX service is one that you can access by using basic JavaScript code from a Web browser client.</span></span> <span data-ttu-id="8a466-105">기반으로 하는이 샘플은 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플; 두 개의 샘플 간의 유일한 차이점은 HTTP POST HTTP GET 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample; the only difference between the two samples is the use of HTTP POST instead of HTTP GET.</span></span>  
  
 <span data-ttu-id="8a466-106">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 AJAX 지원은 `ScriptManager` 컨트롤을 통해 ASP.NET AJAX와 함께 사용되도록 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-106">AJAX support in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="8a466-107">사용 하는 예제에 대 한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET AJAX와 함께 참조는 [Ajax 샘플과](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-107">For an example of using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see the [Ajax Samples](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a466-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8a466-109">다음 샘플의 서비스는 AJAX 특정 코드가 없는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-109">The service in the following sample is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service with no AJAX-specific code.</span></span>  
  
 <span data-ttu-id="8a466-110">경우는 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성은 작업에서 적용 또는 <xref:System.ServiceModel.Web.WebGetAttribute> 특성이 적용 되지 않으면, 기본 HTTP 동사 ("POST")가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-110">If the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute is applied on an operation, or the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="8a466-111">POST 요청이 GET 요청보다 구성하기 어렵지만 해당 요청은 캐시되지 않습니다. 캐싱이 적절하지 않은 모든 작업에 POST 요청을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a466-111">POST requests are harder to construct than GET requests, but they are not cached; use POST requests for all operations where caching is not appropriate.</span></span>  

```csharp
[ServiceContract(Namespace = "PostAjaxService")]  
public interface ICalculator  
{
    [WebInvoke]  
    double Add(double n1, double n2);  
    //Other operations omitted…  
}
```

 <span data-ttu-id="8a466-112">기본 AJAX 서비스 샘플에서와 마찬가지로, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 사용하여 서비스에 AJAX 끝점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-112">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="8a466-113">GET 요청과 달리 브라우저에서 POST 서비스를 호출할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-113">Unlike GET requests, you cannot invoke POST services from the browser.</span></span> <span data-ttu-id="8a466-114">예를 들어,로 이동 http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 POST 서비스에서는 때문에 실행 하면 오류가 발생은 `n1` 및 `n2` 메시지 본문에 보내야 하는 매개 변수-JSON 형식에서-URL에서가 아니라 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-114">For example, navigating to http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 results in an error, because the POST service expects the `n1` and `n2` parameters to be sent in the message body—in the JSON format—and not in the URL.</span></span>  
  
 <span data-ttu-id="8a466-115">클라이언트 웹 페이지 PostAjaxClientPage.aspx에는 사용자가 페이지에 있는 작업 단추 중 하나를 클릭할 때마다 서비스를 호출하는 ASP.NET 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-115">The client Web page PostAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="8a466-116">서비스는 응답에서 동일한 방법으로 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md) GET 요청으로 샘플에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-116">The service responds in the same way as in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, with the GET request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8a466-117">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8a466-118">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8a466-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8a466-119">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="8a466-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8a466-120">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8a466-121">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="8a466-121">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8a466-122">설치 지침을 수행 하도록 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-122">Ensure that you perform the setup instructions [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8a466-123">에 설명 된 대로 PostAjaxService.sln 솔루션을 구축 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8a466-123">Build the solution PostAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8a466-124">로 이동 http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (브라우저에서 프로젝트 디렉터리에서 PostAjaxClientPage.aspx를 열지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="8a466-124">Navigate to http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (do not open PostAjaxClientPage.aspx in the browser from the project directory).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a466-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a466-125">See Also</span></span>
