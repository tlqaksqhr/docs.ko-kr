---
title: JSONP
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 02332e04f729abd125f43acdbe0883851004537e
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2018
---
# <a name="jsonp"></a><span data-ttu-id="bfb37-102">JSONP</span><span class="sxs-lookup"><span data-stu-id="bfb37-102">JSONP</span></span>
<span data-ttu-id="bfb37-103">이 샘플에서는 WCF REST 서비스에서 JSONP(JSON with Padding)를 지원하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-103">This sample demonstrates how to support JSON with Padding (JSONP) in WCF REST services.</span></span> <span data-ttu-id="bfb37-104">JSONP는 스크립트 태그를 현재 문서에서 생성함으로써 도메인의 제한 없이 스크립트를 호출하는 데 사용되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-104">JSONP is a convention used to invoke cross-domain scripts by generating script tags in the current document.</span></span> <span data-ttu-id="bfb37-105">결과는 지정된 콜백 함수를 통해 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-105">The result is returned in a specified callback function.</span></span> <span data-ttu-id="bfb37-106">와 같은 태그는 아이디어를 기반으로 하는 JSONP \<src = "http:/ /..." > 모든 도메인의에서 스크립트를 평가할 수 있으며 이러한 태그로 검색 된 스크립트는 다른 함수 이미 정의 되어 있을 수는 범위 내에서 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-106">JSONP is based on the idea that tags such as \<script src="http://..." > can evaluate scripts from any domain and the script retrieved by those tags is evaluated within a scope in which other functions may already be defined.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="bfb37-107">세부 항목</span><span class="sxs-lookup"><span data-stu-id="bfb37-107">Demonstrates</span></span>  
 <span data-ttu-id="bfb37-108">JSONP를 사용한 도메인 간 스크립팅</span><span class="sxs-lookup"><span data-stu-id="bfb37-108">Cross-domain scripting with JSONP.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="bfb37-109">토론</span><span class="sxs-lookup"><span data-stu-id="bfb37-109">Discussion</span></span>  
 <span data-ttu-id="bfb37-110">이 샘플에는 브라우저에 렌더링된 후 스크립트 블록을 동적으로 추가하는 웹 페이지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-110">The sample includes a Web page that dynamically adds a script block after the page has been rendered in the browser.</span></span> <span data-ttu-id="bfb37-111">이 스크립트 블록은 단일 작업 `GetCustomer`가 있는 WCF REST 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-111">This script block calls a WCF REST service that has a single operation, `GetCustomer`.</span></span> <span data-ttu-id="bfb37-112">WCF REST 서비스는 고객의 이름 및 주소를 콜백 함수 이름으로 래핑하여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-112">The WCF REST service returns a customer’s name and address wrapped in a callback function name.</span></span> <span data-ttu-id="bfb37-113">WCF REST 서비스가 응답하면 고객 데이터를 사용하여 웹 페이지에 대한 콜백 함수가 호출되며 이 콜백 함수는 웹 페이지에 데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-113">When the WCF REST service responds, the callback function on the Web page is invoked with the customer data and the callback function displays the data on the Web page.</span></span> <span data-ttu-id="bfb37-114">스크립트 태그의 삽입과 콜백 함수의 실행은 ASP.NET AJAX ScriptManager 컨트롤에서 자동으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-114">The injection of the script tag and the execution of the callback function is automatically handled by the ASP.NET AJAX ScriptManager control.</span></span> <span data-ttu-id="bfb37-115">이 사용 패턴은 모든 ASP.NET AJAX 프록시와 동일하지만 다음 코드와 같이 JSONP를 사용하도록 설정하기 위한 한 줄이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-115">The usage pattern is the same as with all ASP.NET AJAX proxies, with the addition of one line to enable JSONP, as shown in the following code:</span></span>  
  
```csharp  
var proxy = new JsonpAjaxService.CustomerService();  
proxy.set_enableJsonp(true);  
proxy.GetCustomer(onSuccess, onFail, null);  
```  
  
 <span data-ttu-id="bfb37-116">WCF REST 서비스에서는 <xref:System.ServiceModel.Description.WebScriptEndpoint>가 `crossDomainScriptAccessEnabled`로 설정된  `true`를 사용하므로 웹 페이지에서 이 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-116">The Web page can call the WCF REST service because the service is using the <xref:System.ServiceModel.Description.WebScriptEndpoint> with `crossDomainScriptAccessEnabled` set to `true`.</span></span> <span data-ttu-id="bfb37-117">이러한 구성은 모두은 아래에 있는 Web.config 파일에서 수행 된 \<system.serviceModel > 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-117">Both of these configurations are done in the Web.config file under the \<system.serviceModel> element.</span></span>  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
  <standardEndpoints>  
    <webScriptEndpoint>  
      <standardEndpoint name="" crossDomainScriptAccessEnabled="true"/>  
    </webScriptEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="bfb37-118">ScriptManager는 서비스와의 상호 작용을 관리하며 JSONP 액세스를 수동으로 구현하는 복잡한 과정을 단순하게 해 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-118">ScriptManager manages the interaction with the service and hides away the complexity of manually implementing JSONP access.</span></span> <span data-ttu-id="bfb37-119">`crossDomainScriptAccessEnabled`가 `true`로 설정되고 작업에 대한 응답 형식이 JSON인 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 인프라에서는 요청의 URI를 검사하여 콜백 쿼리 문자열 매개 변수를 확인하고 이 콜백 쿼리 문자열 매개 변수의 값으로 JSON 응답을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-119">When `crossDomainScriptAccessEnabled` is set to `true` and the response format for an operation is JSON, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure inspects the URI of the request for a callback query string parameter and wraps the JSON response with the value of the callback query string parameter.</span></span> <span data-ttu-id="bfb37-120">샘플의 웹 페이지에서는 다음 URI를 사용하여 WCF REST 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-120">In the sample, the Web page calls the WCF REST service with the following URI.</span></span>  
  
```  
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0  
```  
  
 <span data-ttu-id="bfb37-121">콜백 쿼리 문자열 매개 변수에는 `JsonPCallback` 값이 있으므로 WCF 서비스에서는 다음 예제와 같이 JSONP 응답을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-121">Because the callback query string parameter has a value of `JsonPCallback`, the WCF service returns a JSONP response shown in the following example.</span></span>  
  
```  
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});  
```  
  
 <span data-ttu-id="bfb37-122">이 JSONP 응답에는 JSON으로 형식이 지정되고 웹 페이지에서 요청한 콜백 함수 이름으로 래핑된 고객 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-122">This JSONP response includes the customer data formatted as JSON, wrapped with the callback function name that the Web page requested.</span></span> <span data-ttu-id="bfb37-123">ScriptManager는 스크립트 태그를 사용하는 이 콜백을 실행하여 도메인 간 요청을 수행한 다음 ASP.NET AJAX 프록시의 GetCustomer 작업에 전달된 onSuccess 처리기에 결과를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-123">ScriptManager will execute this callback using a script tag to accomplish the cross-domain request, and then pass the result to the onSuccess handler that was passed to the GetCustomer operation of the ASP.NET AJAX proxy.</span></span>  
  
 <span data-ttu-id="bfb37-124">이 샘플은 두 개의 ASP.NET 웹 응용 프로그램으로 구성되어 있습니다. 한 응용 프로그램에는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스만 포함되어 있고 다른 응용 프로그램에는 서비스를 호출하는 .aspx 웹 페이지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-124">The sample consists of two ASP.NET web applications: one contains just a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, and another one contains the .aspx webpage, which calls the service.</span></span> <span data-ttu-id="bfb37-125">솔루션을 실행할 때 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서는 두 웹 사이트를 서로 다른 포트에서 호스트하여 서비스와 클라이언트가 서로 다른 도메인에 있는 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-125">When running the solution, [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] will host the two websites on different ports, which creates an environment where the service and client live on different domains.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bfb37-126">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bfb37-127">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bfb37-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bfb37-128">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="bfb37-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bfb37-129">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="bfb37-130">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="bfb37-130">To run the sample</span></span>  
  
1.  <span data-ttu-id="bfb37-131">JSONP 샘플의 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-131">Open the solution for the JSONP Sample.</span></span>  
  
2.  <span data-ttu-id="bfb37-132">하이퍼링크 "눌러 http://localhost:26648/JSONPClientPage.aspx" 눌러 http://localhost:26648/JSONPClientPage.aspx 브라우저에서 시작 하려면 F5 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-132">Press F5 to launch  HYPERLINK "http://localhost:26648/JSONPClientPage.aspx" http://localhost:26648/JSONPClientPage.aspx in the browser.</span></span>  
  
3.  <span data-ttu-id="bfb37-133">공지는 페이지를 로드 한 후 "Name" 및 "Address"에 대 한 텍스트 입력 값으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-133">Notice that after the page loads, the text inputs for "Name" and "Address" are populated by values.</span></span>  <span data-ttu-id="bfb37-134">이러한 값은 브라우저에서 페이지 렌더링을 마친 후 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 대한 호출에서 제공된 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb37-134">These values were supplied from a call to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service after the browser finished rendering the page.</span></span>
