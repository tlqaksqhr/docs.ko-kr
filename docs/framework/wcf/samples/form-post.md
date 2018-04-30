---
title: 폼 게시
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa6f84f9-2e07-4e3c-92d0-a245308b7dff
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 31d2ebbdb6f899390d7b3af485c1583fb80ae6dc
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="form-post"></a><span data-ttu-id="56116-102">폼 게시</span><span class="sxs-lookup"><span data-stu-id="56116-102">Form Post</span></span>
<span data-ttu-id="56116-103">이 샘플에서는 WCF REST 프로그래밍 모델을 확장하여 들어오는 요청의 새로운 형식을 지원하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56116-103">This sample demonstrates how to extend the WCF REST programming model to support new incoming request formats.</span></span> <span data-ttu-id="56116-104">이 샘플에는 HTML 폼 게시의 요청을 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식으로 deserialize할 수 있는 포맷터의 구현도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56116-104">The sample also includes an implementation of a formatter that can deserialize a request from an HTML form post into a [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] type.</span></span> <span data-ttu-id="56116-105">또한 이 샘플에서는 T4 템플릿을 사용하여 사용자가 다시 WCF REST 서비스에 게시할 수 있는 HTML 폼을 제공하는 HTML 페이지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="56116-105">In addition, the sample uses a T4 Template to return an HTML page, which provides the HTML form that users can post back to the WCF REST service.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="56116-106">세부 항목</span><span class="sxs-lookup"><span data-stu-id="56116-106">Demonstrates</span></span>  
  
-   <span data-ttu-id="56116-107">들어오는 요청 형식에 대한 지원 확장</span><span class="sxs-lookup"><span data-stu-id="56116-107">Extending support for incoming request formats.</span></span>  
  
-   <span data-ttu-id="56116-108">T4 템플릿 통합</span><span class="sxs-lookup"><span data-stu-id="56116-108">Integrating T4 templates.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="56116-109">토론</span><span class="sxs-lookup"><span data-stu-id="56116-109">Discussion</span></span>  
 <span data-ttu-id="56116-110">이 샘플은 두 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56116-110">This sample consists of two projects.</span></span> <span data-ttu-id="56116-111">한 프로젝트는 HTML 폼 게시를 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식으로 deserialize할 수 있는 사용자 지정 요청 포맷터가 포함된 HtmlFormProcessing 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="56116-111">One project is the HtmlFormProcessing library that includes a custom request formatter that can deserialize HTML form posts into [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types.</span></span> <span data-ttu-id="56116-112">다른 프로젝트는 Basic Resource Service 샘플을 확장하여 HtmlFormProcessing 라이브러리의 사용자 지정 요청 포맷터를 사용하는 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="56116-112">The second project is a console application that extends the Basic Resource Service sample to use the custom request formatter of the HtmlFormProcessing library.</span></span>  
  
 <span data-ttu-id="56116-113">HTML 폼 게시(HtmlFormRequestDispatchFormatter)를 deserialize할 수 있는 사용자 지정 포맷터는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]를 사용하여 문자열에서 변환할 수 있는 <xref:System.ServiceModel.Dispatcher.QueryStringConverter> 형식과 QueryStringConverter를 사용하여 문자열에서 변환할 수 있는 멤버만 있으며 <xref:System.Runtime.Serialization.DataContractAttribute>로 표시된 형식을 모두 받아들입니다.</span><span class="sxs-lookup"><span data-stu-id="56116-113">The custom formatter that can deserialize HTML form posts (HtmlFormRequestDispatchFormatter) accepts both [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types that can be converted from a string using the <xref:System.ServiceModel.Dispatcher.QueryStringConverter> and types marked with <xref:System.Runtime.Serialization.DataContractAttribute> that only have members that can be converted from a string using the QueryStringConverter.</span></span>  
  
 <span data-ttu-id="56116-114">HtmlFormProcessing 라이브러리 프로젝트에는 다른 사용자 지정 요청 포맷터를 만드는 데 사용할 수 있는 추상 기본 클래스인 `RequestBodyDispatchFormatter`도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56116-114">The HtmlFormProcessing library project also includes an abstract base class, `RequestBodyDispatchFormatter`, which can be used to create other custom request formatters.</span></span> <span data-ttu-id="56116-115">`RequestBodyDispatchFormatter`에서 파생 클래스를 만들면 개발자는 기본 클래스에서 URI 템플릿 매개 변수를 작업의 메서드 매개 변수에 매핑할 수 있게 해 주는 요청 본문 deserialization 논리에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56116-115">Deriving from the `RequestBodyDispatchFormatter` allows a developer to focus on the request body deserialization logic, which allows the base class to map the URI template parameters to the operation’s method parameters.</span></span> <span data-ttu-id="56116-116">또한 HtmlFormProcessing 라이브러리 프로젝트에는 `HtmlFormProcessingBehavior`에서 파생 클래스를 만들어 기본 요청 포맷터를 사용자 지정 요청 포맷터로 대체하는 방법을 보여 주는 <xref:System.ServiceModel.Description.WebHttpBehavior> 클래스도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56116-116">Also in the HtmlFormProcessing library project is the `HtmlFormProcessingBehavior` class, which demonstrates how to derive from the <xref:System.ServiceModel.Description.WebHttpBehavior> to replace the default request formatter with a custom request formatter.</span></span>  
  
 <span data-ttu-id="56116-117">이 콘솔 응용 프로그램 프로젝트에서 확장 된 [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="56116-117">This console application project extends the [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) sample.</span></span> <span data-ttu-id="56116-118">Basic Resource Service 샘플에서는 WCF REST 프로그래밍 모델을 사용하는 방식으로 리소스를 노출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56116-118">The Basic Resource Service sample demonstrates how to expose a resource in a manner that uses the WCF REST programming model.</span></span> <span data-ttu-id="56116-119">Basic Resource Service 샘플에서는 고객 컬렉션 리소스가 노출되므로 컬렉션의 고객을 만들고, 검색하고, 업데이트하고, 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56116-119">In the Basic Resource Service sample, a customer collection resource is exposed such that customers in the collection can be created, retrieved, updated and deleted.</span></span> <span data-ttu-id="56116-120">Basic Resource Service 샘플에서는 기본적으로 지원되는 들어오는 요청 형식인 XML과 JSON만 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="56116-120">The Basic Resource Service sample only uses the two natively supported incoming request formats, XML and JSON.</span></span>  
  
 <span data-ttu-id="56116-121">이 Form Post 샘플의 콘솔 응용 프로그램에서는 HtmlFormProcessing 라이브러리의 사용자 지정 포맷터를 사용합니다. 이 사용자 지정 포맷터를 사용하면 사용자가 브라우저를 사용하여 HTML 폼 게시에서 요청을 보내는 방법으로 고객을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56116-121">The console application in this Form Post sample utilizes the custom formatter in the HtmlFormProcessing library, which allows users to create customers by sending a request from an HTML form post using a browser.</span></span> <span data-ttu-id="56116-122">이 콘솔 응용 프로그램에서는 서비스에 다시 게시할 폼이 포함된 HTML 페이지를 반환하는 작업도 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="56116-122">It also adds an operation that returns an HTML page, which includes the form to be posted back to the service.</span></span> <span data-ttu-id="56116-123">이 HTML 페이지는 .tt 파일과 자동 생성된 .cs 파일로 구성된 전처리된 T4 템플릿을 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="56116-123">This HTML page is generated using a preprocessed T4 template, which consists of a .tt file and an auto-generated .cs file.</span></span> <span data-ttu-id="56116-124">개발자는 .tt 파일을 사용하여 변수 및 제어 구조가 포함된 템플릿 폼에 응답을 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56116-124">The .tt file allows a developer to write a response in a template form that contains variables and control structures.</span></span> <span data-ttu-id="56116-125">T4에 대 한 자세한 내용은 참조 [생성 아티팩트 템플릿을 사용 하 여 텍스트](http://go.microsoft.com/fwlink/?LinkId=178139)합니다.</span><span class="sxs-lookup"><span data-stu-id="56116-125">For more information about T4, see [Generating Artifacts By Using Text Templates](http://go.microsoft.com/fwlink/?LinkId=178139).</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="56116-126">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="56116-126">To run the sample</span></span>  
  
1.  <span data-ttu-id="56116-127">Form Post 샘플의 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="56116-127">Open the solution for the Form Post Sample.</span></span> <span data-ttu-id="56116-128">관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 시작해야 샘플이 제대로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="56116-128">When launching [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], you must run as an administrator to execute the sample successfully.</span></span> <span data-ttu-id="56116-129">마우스 오른쪽 단추로 클릭 하 여이 작업을 수행는 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 아이콘 및 상황에 맞는 메뉴에서 "관리자 권한으로 실행"을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="56116-129">Do this by right-clicking the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] icon and choosing "Run as Administrator" from the context menu.</span></span>  
  
2.  <span data-ttu-id="56116-130">Ctrl+Shift+B를 눌러 솔루션을 빌드한 다음 Ctrl+F5를 눌러 콘솔 응용 프로그램 FormPost 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="56116-130">Press CTRL+SHIFT+B to build the solution and then press CTRL+F5 to run the console application FormPost project.</span></span>  
  
3.  <span data-ttu-id="56116-131">콘솔 창이 나타나고 실행 중인 서비스의 URI와 실행 중인 서비스에 대한 HTML 도움말 페이지의 URI가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="56116-131">The console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span>  
  
4.  <span data-ttu-id="56116-132">샘플이 실행되면 클라이언트에서는 고객을 추가, 업데이트, 삭제 중인지 서비스에서 현재 고객 목록을 가져오는 중인지 등의 현재 활동 상태를 콘솔 창에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="56116-132">As the sample runs, the client writes the status of the current activity, whether it be adding a customer, updating a customer, deleting a customer or getting a list of current customers from the service to the console window.</span></span>  
  
5.  <span data-ttu-id="56116-133">그런 다음 고객 폼의 URI로 이동할지 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56116-133">You are then prompted to browse to the URI of the customer form.</span></span> <span data-ttu-id="56116-134">브라우저를 열고 지정된 URI로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="56116-134">Open a browser and browse to the given URI.</span></span> <span data-ttu-id="56116-135">이름 및 고객과 클릭에 대 한 주소에 입력 된 **전송** 단추 합니다.</span><span class="sxs-lookup"><span data-stu-id="56116-135">Type in a name and address for the customer and click the **Submit** button.</span></span>  
  
6.  <span data-ttu-id="56116-136">콘솔 창에서 아무 키나 눌러 샘플을 계속 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="56116-136">Press any key for the console window to continue running the sample.</span></span>  
  
7.  <span data-ttu-id="56116-137">샘플이 완료되면 브라우저를 사용하여 만든 고객이 최종 고객 목록에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="56116-137">As the sample completes, notice that the customer you created using the browser is included in the final list of customers.</span></span>  
  
8.  <span data-ttu-id="56116-138">아무 키나 눌러 샘플을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="56116-138">Press any key to terminate the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="56116-139">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56116-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="56116-140">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="56116-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="56116-141">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="56116-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="56116-142">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56116-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Web\FormPost`
