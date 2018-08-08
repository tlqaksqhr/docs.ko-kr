---
title: AJAX Service Using HTTP POST
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: f904a26d87a21a931035b45261dbcd970f7d63a1
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33804110"
---
# <a name="ajax-service-using-http-post"></a><span data-ttu-id="c7728-102">AJAX Service Using HTTP POST</span><span class="sxs-lookup"><span data-stu-id="c7728-102">AJAX Service Using HTTP POST</span></span>
<span data-ttu-id="c7728-103">이 샘플에서는 만들려면 Windows Communication Foundation (WCF)를 사용 하는 방법을 보여 줍니다.는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Asynchronous JavaScript and XML (AJAX) HTTP POST를 사용 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Asynchronous JavaScript and XML (AJAX) service that uses HTTP POST.</span></span> <span data-ttu-id="c7728-104">AJAX 서비스는 웹 브라우저 클라이언트에서 기본 JavaScript 코드를 사용하여 액세스할 수 있는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-104">An AJAX service is one that you can access by using basic JavaScript code from a Web browser client.</span></span> <span data-ttu-id="c7728-105">기반으로 하는이 샘플은 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플; 두 개의 샘플 간의 유일한 차이점은 HTTP POST HTTP GET 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample; the only difference between the two samples is the use of HTTP POST instead of HTTP GET.</span></span>  
  
 <span data-ttu-id="c7728-106">Windows Communication Foundation (WCF)에서 AJAX 지원을 통해 ASP.NET AJAX와 함께 사용 되도록 최적화 되었습니다는 `ScriptManager` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-106">AJAX support in Windows Communication Foundation (WCF) is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="c7728-107">ASP.NET AJAX와 함께 WCF를 사용 하는 예제를 참조 하십시오.는 [Ajax 샘플과](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-107">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7728-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="c7728-109">다음 샘플의 서비스는 AJAX 특정 코드가 없는 WCF 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-109">The service in the following sample is a WCF service with no AJAX-specific code.</span></span>  
  
 <span data-ttu-id="c7728-110">경우는 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성은 작업에서 적용 또는 <xref:System.ServiceModel.Web.WebGetAttribute> 특성이 적용 되지 않으면, 기본 HTTP 동사 ("POST")가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-110">If the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute is applied on an operation, or the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="c7728-111">POST 요청이 GET 요청보다 구성하기 어렵지만 해당 요청은 캐시되지 않습니다. 캐싱이 적절하지 않은 모든 작업에 POST 요청을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7728-111">POST requests are harder to construct than GET requests, but they are not cached; use POST requests for all operations where caching is not appropriate.</span></span>  

```csharp
[ServiceContract(Namespace = "PostAjaxService")]  
public interface ICalculator  
{
    [WebInvoke]  
    double Add(double n1, double n2);  
    //Other operations omitted…  
}
```

 <span data-ttu-id="c7728-112">기본 AJAX 서비스 샘플에서와 마찬가지로, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 사용하여 서비스에 AJAX 끝점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-112">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="c7728-113">GET 요청과 달리 브라우저에서 POST 서비스를 호출할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-113">Unlike GET requests, you cannot invoke POST services from the browser.</span></span> <span data-ttu-id="c7728-114">예를 들어,로 이동 http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 POST 서비스에서는 때문에 실행 하면 오류가 발생은 `n1` 및 `n2` 메시지 본문에 보내야 하는 매개 변수-JSON 형식에서-URL에서가 아니라 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-114">For example, navigating to http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 results in an error, because the POST service expects the `n1` and `n2` parameters to be sent in the message body—in the JSON format—and not in the URL.</span></span>  
  
 <span data-ttu-id="c7728-115">클라이언트 웹 페이지 PostAjaxClientPage.aspx에는 사용자가 페이지에 있는 작업 단추 중 하나를 클릭할 때마다 서비스를 호출하는 ASP.NET 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-115">The client Web page PostAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="c7728-116">서비스는 응답에서 동일한 방법으로 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md) GET 요청으로 샘플에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-116">The service responds in the same way as in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, with the GET request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c7728-117">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c7728-118">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c7728-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c7728-119">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="c7728-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c7728-120">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c7728-121">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c7728-121">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="c7728-122">설치 지침을 수행 하도록 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-122">Ensure that you perform the setup instructions [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="c7728-123">에 설명 된 대로 PostAjaxService.sln 솔루션을 구축 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7728-123">Build the solution PostAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="c7728-124">로 이동 http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (브라우저에서 프로젝트 디렉터리에서 PostAjaxClientPage.aspx를 열지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="c7728-124">Navigate to http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx (do not open PostAjaxClientPage.aspx in the browser from the project directory).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7728-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7728-125">See Also</span></span>
