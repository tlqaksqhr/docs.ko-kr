---
title: Basic AJAX Service
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d66d0c91-0109-45a0-a901-f3e4667c2465
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 540e7d2705dbdd3249a0519efb80de676428e92f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="basic-ajax-service"></a><span data-ttu-id="c8538-102">Basic AJAX Service</span><span class="sxs-lookup"><span data-stu-id="c8538-102">Basic AJAX Service</span></span>
<span data-ttu-id="c8538-103">이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하여 기본 ASP.NET AJAX(Asynchronous JavaScript and XML) 서비스(웹 브라우저 클라이언트에서 JavaScript 코드를 통해 액세스할 수 있는 서비스)를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-103">This sample demonstrates how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access using JavaScript code from a Web browser client).</span></span> <span data-ttu-id="c8538-104">이 서비스에서는 HTTP GET 요청에 응답하고 JSON(JavaScript Object Notation) 데이터 형식을 응답에 사용하도록 <xref:System.ServiceModel.Web.WebGetAttribute> 특성이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-104">The service uses the <xref:System.ServiceModel.Web.WebGetAttribute> attribute to ensure that the service responds to HTTP GET requests and is configured to use the JavaScript Object Notation (JSON) data format for responses.</span></span>  
  
 <span data-ttu-id="c8538-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 AJAX 지원은 `ScriptManager` 컨트롤을 통해 ASP.NET AJAX와 함께 사용되도록 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-105">AJAX support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="c8538-106">사용 하는 예제에 대 한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET AJAX와 함께 참조는 [AJAX 샘플과](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e)합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-106">For an example of using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see the [AJAX Samples](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8538-107">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-107">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="c8538-108">다음 코드에서는 서비스가 HTTP GET 요청에 응답하도록 <xref:System.ServiceModel.Web.WebGetAttribute> 특성이 `Add` 작업에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-108">In the following code, the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is applied to the `Add` operation to ensure that the service responds to HTTP GET requests.</span></span> <span data-ttu-id="c8538-109">이 코드에서는 간편하게 GET을 사용합니다. HTTP GET 요청은 모든 웹 브라우저에서 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-109">The code uses GET for simplicity (you can construct an HTTP GET request from any Web browser).</span></span> <span data-ttu-id="c8538-110">또한 GET을 사용하여 캐싱을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-110">You can also use GET to enable caching.</span></span> <span data-ttu-id="c8538-111">`WebGetAttribute` 특성이 없을 경우 HTTP POST가 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-111">HTTP POST is the default in the absence of the `WebGetAttribute` attribute.</span></span>  
  
```  
[ServiceContract(Namespace = "SimpleAjaxService")]  
public interface ICalculator  
{  
  
    [WebGet]  
    double Add(double n1, double n2);  
    //Other operations omitted…  
}  
```  
  
 <span data-ttu-id="c8538-112">샘플 .svc 파일은 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 표준 끝점을 서비스에 추가하는 <xref:System.ServiceModel.Description.WebScriptEndpoint>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-112">The sample .svc file uses <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, which adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> standard endpoint to the service.</span></span> <span data-ttu-id="c8538-113">끝점은 .svc 파일을 기준으로 빈 주소에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-113">The endpoint is configured at an empty address relative to the .svc file.</span></span> <span data-ttu-id="c8538-114">이는 작업 이름이 아닌 추가 접미사를 포함하지 않는 http://localhost/ServiceModelSamples/service.svc가 서비스의 주소라는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-114">This means that the address of the service is http://localhost/ServiceModelSamples/service.svc, with no additional suffixes other than the operation name.</span></span>  
  
```  
<%@ServiceHost language="C#" Debug="true" Service="Microsoft.Samples.SimpleAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory" %>  
```  
  
 <span data-ttu-id="c8538-115"><xref:System.ServiceModel.Description.WebScriptEndpoint>는 ASP.NET AJAX 클라이언트 페이지에서 서비스에 액세스할 수 있도록 하기 위해 미리 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-115">The <xref:System.ServiceModel.Description.WebScriptEndpoint> is pre-configured to make the service accessible from an ASP.NET AJAX client page.</span></span> <span data-ttu-id="c8538-116">Web.config의 다음 섹션은 끝점에 대한 추가 구성 변경 작업을 수행하는 데 사용할 수 있으며</span><span class="sxs-lookup"><span data-stu-id="c8538-116">The following section in Web.config can be used to make additional configuration changes to the endpoint.</span></span> <span data-ttu-id="c8538-117">추가 변경이 필요하지 않은 경우 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-117">It can be removed if no extra changes are required.</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webScriptEndpoint>  
      <!-- Use this element to configure the endpoint -->  
      <standardEndpoint name=""  />  
    </webScriptEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="c8538-118"><xref:System.ServiceModel.Description.WebScriptEndpoint>는 서비스의 기본 데이터 형식을 XML 대신 JSON으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-118">The <xref:System.ServiceModel.Description.WebScriptEndpoint> sets the default data format for the service to JSON instead of XML.</span></span> <span data-ttu-id="c8538-119">서비스를 호출하려면 이 항목의 뒷부분에 나오는 설치 및 빌드 단계를 완료한 후 http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-119">To invoke the service, navigate to http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200 after completing the set up and build steps shown later in this topic.</span></span> <span data-ttu-id="c8538-120">이 테스트 기능은 HTTP GET 요청을 사용해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-120">This testing functionality is enabled by the use of a HTTP GET request.</span></span>  
  
 <span data-ttu-id="c8538-121">클라이언트 웹 페이지 SimpleAjaxClientPage.aspx에는 사용자가 페이지에 있는 작업 단추 중 하나를 클릭할 때마다 서비스를 호출하는 ASP.NET 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-121">The client Web page SimpleAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="c8538-122">`ScriptManager` 컨트롤은 서비스에 대한 프록시를 JavaScript를 통해 액세스할 수 있게 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-122">The `ScriptManager` control is used to make a proxy to the service accessible through JavaScript.</span></span>  
  
```  
<asp:ScriptManager ID="ScriptManager" runat="server">  
    <Services>  
        <asp:ServiceReference Path="service.svc" />  
    </Services>  
</asp:ScriptManager>  
```  
  
 <span data-ttu-id="c8538-123">다음 JavaScript 코드를 사용하여 로컬 프록시가 인스턴스화되고 작업이 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-123">The local proxy is instantiated and operations are invoked using the following JavaScript code.</span></span>  
  
```  
// Code for extracting arguments n1 and n2 omitted…  
// Instantiate a service proxy  
var proxy = new SimpleAjaxService.ICalculator();  
// Code for selecting operation omitted…  
proxy.Add(parseFloat(n1), parseFloat(n2), onSuccess, onFail, null);  
```  
  
 <span data-ttu-id="c8538-124">서비스 호출에 성공할 경우 `onSuccess` 처리기가 호출되고 작업 결과가 텍스트 상자에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-124">If the service call succeeds, the code invokes the `onSuccess` handler and the result of the operation is displayed in a text box.</span></span>  
  
```  
function onSuccess(mathResult){  
     document.getElementById("result").value = mathResult;  
}  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="c8538-125">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c8538-126">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c8538-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c8538-127">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="c8538-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c8538-128">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\SimpleAjaxService`  
  
## <a name="see-also"></a><span data-ttu-id="c8538-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8538-129">See Also</span></span>
