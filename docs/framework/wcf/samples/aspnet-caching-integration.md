---
title: "ASP.NET 캐싱 통합"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d56c435088be383821d17250e230cae848d2bab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="aspnet-caching-integration"></a><span data-ttu-id="f42d7-102">ASP.NET 캐싱 통합</span><span class="sxs-lookup"><span data-stu-id="f42d7-102">ASP.NET Caching Integration</span></span>
<span data-ttu-id="f42d7-103">이 샘플에서는 WCF 웹 HTTP 프로그래밍 모델을 사용하여 ASP.NET 출력 캐시를 활용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-103">This sample demonstrates how to utilize the ASP.NET output cache with the WCF WEB HTTP programming model.</span></span> <span data-ttu-id="f42d7-104">참조 하십시오는 [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) 자체 호스팅 버전 심층에서 서비스 구현에 나와 있는이 시나리오의 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-104">Please see the [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) sample for a self-hosted version of this scenario that discusses the service implementation in depth.</span></span> <span data-ttu-id="f42d7-105">이 항목에서는 ASP.NET 출력 캐시 통합 기능을 중점적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-105">This topic focuses on the ASP.NET output cache integration feature.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="f42d7-106">세부 항목</span><span class="sxs-lookup"><span data-stu-id="f42d7-106">Demonstrates</span></span>  
 <span data-ttu-id="f42d7-107">ASP.NET 출력 캐시와 통합</span><span class="sxs-lookup"><span data-stu-id="f42d7-107">Integration with the ASP.NET Output Cache</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f42d7-108">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f42d7-109">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f42d7-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f42d7-110">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="f42d7-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f42d7-111">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`  
  
## <a name="discussion"></a><span data-ttu-id="f42d7-112">토론</span><span class="sxs-lookup"><span data-stu-id="f42d7-112">Discussion</span></span>  
 <span data-ttu-id="f42d7-113">이 샘플에서는 <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>를 사용하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스에 ASP.NET 출력 캐싱을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-113">The sample uses the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> to utilize ASP.NET output caching with the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service.</span></span> <span data-ttu-id="f42d7-114"><xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>는 서비스 작업에 적용되며, 구성 파일에서 지정된 작업의 응답에 적용해야 하는 캐시 프로필의 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-114">The <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> is applied to service operations, and provides the name of a cache profile in a configuration file that should be applied to responses from the given operation.</span></span>  
  
 <span data-ttu-id="f42d7-115">샘플 Service 프로젝트의 Service.cs 파일에서 모두는 `GetCustomer` 및 `GetCustomers` 작업으로 표시 됩니다는 <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, 캐시 프로필 이름 "CacheFor60Seconds"를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-115">In the Service.cs file of the sample Service project, both the `GetCustomer` and `GetCustomers` operations are marked with the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, which provides the cache profile name "CacheFor60Seconds".</span></span> <span data-ttu-id="f42d7-116">서비스 프로젝트의 Web.config 파일에서 캐시 프로필 "CacheFor60Seconds" 제공 하지 않습니다는 <`caching`> 요소의 <`system.web`> 합니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-116">In the Web.config file of the Service project, the cache profile "CacheFor60Seconds" is provided under the <`caching`> element of <`system.web`>.</span></span> <span data-ttu-id="f42d7-117">이 캐시 프로필의 값에는 `duration` 특성 이므로 "60"이이 프로필에 연결 된 응답은 60 초 동안 ASP.NET 출력 캐시에 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-117">For this cache profile, the value of the `duration` attribute is "60", so responses associated with this profile are cached in the ASP.NET output cache for 60 seconds.</span></span> <span data-ttu-id="f42d7-118">또한이 캐시 프로필에 대 한는 `varmByParam` 특성이 너무 요청에 대 한 값이 서로 다른 "format"으로 설정 되어는 `format` 쿼리 문자열 매개 변수에서는 응답이 별도로 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-118">Also, for this cache profile, the `varmByParam` attribute is set to "format" so requests with different values for the `format` query string parameter have their responses cached separately.</span></span> <span data-ttu-id="f42d7-119">마지막으로 캐시 프로필의 `varyByHeader` 있으므로 Accept 헤더 값이 다른 요청에서는 응답이 별도로 캐시 특성이 "Accept"로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-119">Lastly, the cache profile’s `varyByHeader` attribute is set to "Accept", so requests with different Accept header values have their responses cached separately.</span></span>  
  
 <span data-ttu-id="f42d7-120">Client 프로젝트의 Program.cs에서는 <xref:System.Net.HttpWebRequest>를 사용하여 이러한 클라이언트를 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-120">Program.cs in the Client project demonstrates how such a client can be authored using <xref:System.Net.HttpWebRequest>.</span></span> <span data-ttu-id="f42d7-121">이 방법은 WCF 서비스에 액세스하는 여러 방법 중 하나일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-121">Note that this is just one way to access a WCF service.</span></span> <span data-ttu-id="f42d7-122">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 채널 팩터리 및 <xref:System.Net.WebClient>와 같은 다른 .NET Framework 클래스를 사용하여 서비스에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-122">It is also possible to access the service using other .NET Framework classes like the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] channel factory and <xref:System.Net.WebClient>.</span></span> <span data-ttu-id="f42d7-123">SDK의 다른 샘플 (같은 [기본 HTTP 서비스](../../../../docs/framework/wcf/samples/basic-http-service.md) 샘플 및 [선택 영역 자동 서식](../../../../docs/framework/wcf/samples/automatic-format-selection.md) 샘플)와 통신 하려면 이러한 클래스를 사용 하는 방법을 보여는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-123">Other samples in the SDK (such as the [Basic HTTP Service](../../../../docs/framework/wcf/samples/basic-http-service.md) sample and the [Automatic Format Selection](../../../../docs/framework/wcf/samples/automatic-format-selection.md) sample) illustrate how to use these classes to communicate with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
## <a name="to-run-the-sample"></a><span data-ttu-id="f42d7-124">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="f42d7-124">To run the sample</span></span>  
 <span data-ttu-id="f42d7-125">이 샘플은 다음의 세 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-125">The sample consists of three projects:</span></span>  
  
-   <span data-ttu-id="f42d7-126">**서비스**: ASP.NET에서 호스팅되는 WCF HTTP 서비스가 포함 된 웹 응용 프로그램 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-126">**Service**: A Web Application project that includes a WCF HTTP service hosted in ASP.NET.</span></span>  
  
-   <span data-ttu-id="f42d7-127">**클라이언트**: 콘솔 응용 프로그램 프로젝트 서비스에 대 한 호출입니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-127">**Client**: A console application project that makes calls to the service.</span></span>  
  
-   <span data-ttu-id="f42d7-128">**일반적인**: 클라이언트 및 서비스에 의해 사용 되는 고객 형식을 포함 하는 공유 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-128">**Common**: A shared library that contains the Customer type used by the client and service.</span></span>  
  
 <span data-ttu-id="f42d7-129">Client 콘솔 응용 프로그램이 실행되면 클라이언트에서는 서비스로 요청을 보내고 응답의 관련 정보를 콘솔 창에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-129">As the Client console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="f42d7-130">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="f42d7-130">To run the sample</span></span>  
  
1.  <span data-ttu-id="f42d7-131">ASP.NET Caching Integration 샘플의 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-131">Open the solution for the ASP.NET Caching Integration Sample.</span></span>  
  
2.  <span data-ttu-id="f42d7-132">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-132">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="f42d7-133">경우는 **솔루션 탐색기** 창이 아직 열려 있지 않으면, CTRL + W + S를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-133">If the **Solution Explorer** window is not already open, press CTRL+W+S.</span></span>  
  
4.  <span data-ttu-id="f42d7-134">**솔루션 탐색기** 창을 마우스 오른쪽 단추로 클릭은 **서비스** 프로젝트를 마우스 선택 **새 인스턴스 시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-134">From the **Solution Explorer** window, right click the **Service** project and select **Start New Instance**.</span></span> <span data-ttu-id="f42d7-135">그러면 ASP.NET Development Server가 시작되어 서비스를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-135">This launches the ASP.NET development server, which hosts the service.</span></span>  
  
5.  <span data-ttu-id="f42d7-136">**솔루션 탐색기** 창을 마우스 오른쪽 단추로 클릭은 **클라이언트** 프로젝트를 마우스 선택 **새 인스턴스 시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-136">From the **Solution Explorer** window, right click the **Client** project and select **Start New Instance**.</span></span>  
  
6.  <span data-ttu-id="f42d7-137">클라이언트 콘솔 창이 나타나고 실행 중인 서비스의 URI와 실행 중인 서비스에 대한 HTML 도움말 페이지의 URI가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-137">The client console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="f42d7-138">언제든지 브라우저에서 HTML 도움말 페이지의 URI를 입력하면 해당 도움말 페이지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-138">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span>  
  
7.  <span data-ttu-id="f42d7-139">샘플이 실행되면 클라이언트에서는 현재 활동의 상태를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-139">As the sample runs, the client writes the status of the current activity.</span></span>  
  
8.  <span data-ttu-id="f42d7-140">아무 키나 눌러 클라이언트 콘솔 응용 프로그램을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-140">Press any key to terminate the client console application.</span></span>  
  
9. <span data-ttu-id="f42d7-141">Shift+F5를 눌러 서비스 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-141">Press SHIFT+F5 to stop debugging the service.</span></span>  
  
10. <span data-ttu-id="f42d7-142">Windows 알림 영역에서 ASP.NET 개발 서버 아이콘을 마우스 오른쪽 단추로 클릭 하 고 선택 **중지**합니다.</span><span class="sxs-lookup"><span data-stu-id="f42d7-142">In the Windows Notification Area, right click the ASP.NET development server icon and select **Stop**.</span></span>
