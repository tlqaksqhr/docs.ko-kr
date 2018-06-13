---
title: SystemWebRouting Integration 샘플
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 52b908d354771cb2b351e339881647462340b716
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806528"
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="e9089-102">SystemWebRouting Integration 샘플</span><span class="sxs-lookup"><span data-stu-id="e9089-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="e9089-103">이 샘플에서는 호스팅 계층과 <xref:System.Web.Routing> 네임스페이스에 있는 클래스의 통합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="e9089-104"><xref:System.Web.Routing> 네임스페이스의 클래스를 사용하면 응용 프로그램에서 실제 리소스에 직접적으로 해당하지 않는 URL을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="e9089-105">웹 라우팅을 사용 하 여 개발자를 실제 WCF 서비스에 다시 매핑되는 HTTP에 대 한 가상 주소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual WCF services.</span></span> <span data-ttu-id="e9089-106">이렇게 하면 실제 파일 또는 리소스 없이 WCF 서비스를 호스트해야 하거나 .html 또는 .aspx와 같은 파일 확장명이 포함되지 않은 URL을 사용하여 서비스에 액세스해야 하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="e9089-107">이 샘플에서는 <xref:System.Web.Routing.RouteTable> 클래스를 사용하여 global.asax에 정의된 실행 중인 서비스에 매핑되는 가상 URI를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span> 

> [!NOTE]
>  <span data-ttu-id="e9089-108"><xref:System.Web.Routing> 네임스페이스의 클래스는 HTTP를 통해 호스트되는 서비스에 대해서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-108">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
<span data-ttu-id="e9089-109">이 예제에서는 WCF를 사용 하 여 두 개의 RSS 피드를 만듭니다:는 `movies` 피드 및 `channels` 피드입니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-109">This example uses WCF to create two RSS feeds: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="e9089-110">서비스를 활성화 하도록 Url 확장을 포함 하지 않으며에 등록 되어 있는 `Application_Start` 의 메서드는 `Global` 에서 파생 된 클래스는 <xref:System.Web.HttpApplication> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-110">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9089-111">이 샘플에만 인터넷 정보 서비스 (IIS) 7.0에서 작동 나중에 IIS 6.0으로 사용 하는 다른 방법을 확장명이 없는 Url을 지원 하기 위한 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-111">This sample only works in Internet Information Services (IIS) 7.0 and later, as IIS 6.0 uses a different method for supporting extension-less URLs.</span></span>  

#### <a name="to-download-this-sample"></a><span data-ttu-id="e9089-112">이 예제를 다운로드 하려면</span><span class="sxs-lookup"><span data-stu-id="e9089-112">To download this sample</span></span>
  
<span data-ttu-id="e9089-113">이 샘플 컴퓨터에 이미 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-113">This sample may already be installed on your computer.</span></span> <span data-ttu-id="e9089-114">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e9089-114">Check for the following (default) directory before continuing.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples`  
   
 <span data-ttu-id="e9089-115">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="e9089-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e9089-116">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-116">This sample is located in the following directory.</span></span>  
   
`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="e9089-117">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="e9089-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="e9089-118">WebRoutingIntegration.sln 파일을 열고 Visual Studio를 사용 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-118">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="e9089-119">F5 키를 눌러 솔루션을 실행하고 웹 개발 서버를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-119">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="e9089-120">샘플의 디렉터리 목록이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-120">A directory listing for the sample appears.</span></span> <span data-ttu-id="e9089-121">파일 확장명이 .svc인 파일은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-121">Note that there are no files with an .svc file extension.</span></span>  
  
3.  <span data-ttu-id="e9089-122">주소 표시줄에 추가 `movies` 한다는 표시 되도록 URL로 http://localhost:[port] / 영화 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-122">In the address bar, add `movies` to the URL, so that it reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="e9089-123">movies 피드가 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-123">The movies feed appears in the browser.</span></span>  
  
4.  <span data-ttu-id="e9089-124">주소 표시줄에 추가 `channels` URL로가 되도록 읽기 http://localhost:[port] / 채널 및 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-124">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="e9089-125">channels 피드가 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-125">The channels feed appears in the browser.</span></span>  
  
5.  <span data-ttu-id="e9089-126">Alt+F4를 눌러 웹 브라우저를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-126">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="e9089-127">개발 서버가 종료 되지 않은 경우 알림 영역 아이콘을 마우스 오른쪽 단추로 클릭 하 고 선택 **중지**합니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-127">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="e9089-128">IIS에서 호스트될 때 이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="e9089-128">To use this sample when hosted in IIS</span></span>  
  
1.  <span data-ttu-id="e9089-129">WebRoutingIntegration.sln 파일을 열고 Visual Studio를 사용 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-129">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="e9089-130">Ctrl+Shift+B를 눌러 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-130">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="e9089-131">IIS(인터넷 정보 서비스) 관리자에서 웹 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-131">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1.  <span data-ttu-id="e9089-132">IIS 관리자에서 마우스 오른쪽 단추로 클릭는 **기본 웹 사이트** 선택 **응용 프로그램 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-132">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2.  <span data-ttu-id="e9089-133">에 대 한는 **별칭**, 입력 `WebRoutingIntegration`합니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-133">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3.  <span data-ttu-id="e9089-134">에 대 한는 **실제 경로**, 프로젝트 내의 Service 폴더를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-134">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4.  <span data-ttu-id="e9089-135">Press **OK**.</span><span class="sxs-lookup"><span data-stu-id="e9089-135">Press **OK**.</span></span>  
  
4.  <span data-ttu-id="e9089-136">웹 응용 프로그램을 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 응용 프로그램을 시작 **응용 프로그램 관리** 차례로 **찾아보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-136">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5.  <span data-ttu-id="e9089-137">주소 표시줄에 추가 `movies` URL로가 되도록 읽기 http://localhost:[port] / 영화 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-137">In the address bar, add `movies` to the URL, so that is reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="e9089-138">movies 피드가 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-138">The movies feed appears in the browser.</span></span>  
  
6.  <span data-ttu-id="e9089-139">주소 표시줄에 추가 `channels` URL로가 되도록 읽기 http://localhost:[port] / 채널 및 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-139">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="e9089-140">channels 피드가 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-140">The channels feed appears in the browser.</span></span>  
  
7.  <span data-ttu-id="e9089-141">Alt+F4를 눌러 웹 브라우저를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-141">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="e9089-142">이 샘플에서는 HTTP를 통해 호스트되는 서비스의 요청을 라우트하기 위해 <xref:System.Web.Routing> 네임스페이스의 클래스를 사용하여 호스팅 계층을 작성할 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9089-142">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9089-143">기본 응용 프로그램 풀 버전을 업데이트 해야 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 버전 2로 설정 된 경우.</span><span class="sxs-lookup"><span data-stu-id="e9089-143">You must update the default application pool version to [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9089-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9089-144">See Also</span></span>  
 [<span data-ttu-id="e9089-145">AppFabric 호스팅 및 지 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="e9089-145">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
