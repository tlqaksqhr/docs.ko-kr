---
title: "컨테이너 화 된 응용 프로그램 서비스를 모니터링 합니다."
description: "Microsoft 플랫폼 및 도구와 Docker 컨테이너 화 된 응용 프로그램 수명 주기"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 3e4a78eb47d0e6712919c89b6f52ec8e4248fb23
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2017
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="7008e-104">컨테이너 화 된 응용 프로그램 서비스를 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-104">Monitor containerized application services</span></span>

<span data-ttu-id="7008e-105">것은 응용 프로그램으로 여러 컨테이너 및 microservices 분할을 모니터링 하 고 응용 프로그램의 동작을 분석 하는 방법이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-105">It is critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the application.</span></span>

## <a name="microsoft-application-insights"></a><span data-ttu-id="7008e-106">Microsoft Application Insights</span><span class="sxs-lookup"><span data-stu-id="7008e-106">Microsoft Application Insights</span></span>

<span data-ttu-id="7008e-107">[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) 는 라이브 응용 프로그램을 모니터링 하는 확장 가능한 분석 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-107">[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="7008e-108">검색 및 성능 문제를 진단 하 고 사용자가 실제로 수행할 작업을 앱과 이해 수 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-108">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="7008e-109">개발자는 지속적으로 성능을 향상 시킬 수의 의도 및 서비스 또는 응용 프로그램의 유용성을 위해 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-109">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="7008e-110">Application Insights.NET, Java, Node.js 및 기타 다양 한 플랫폼 온-프레미스 호스트와 같은 플랫폼 또는 클라우드에서 다양 한 응용 프로그램 웹/서비스와 독립 실행형으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-110">Application Insights works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a><span data-ttu-id="7008e-111">Application Insights를 사용 하 여 QA 환경에서 Docker 응용 프로그램 분석</span><span class="sxs-lookup"><span data-stu-id="7008e-111">Analyzing Docker apps in QA environments using Application Insights</span></span>

<span data-ttu-id="7008e-112">Docker, 관련 된 수명 주기 이벤트 및 Docker 컨테이너에 Application Insights에서 성능 카운터 차트 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-112">As it pertains to Docker, you can chart life-cycle events and performance counters from Docker containers on Application Insights.</span></span> <span data-ttu-id="7008e-113">실행 해야는 [응용 프로그램 통찰력 Docker 이미지](https://hub.docker.com/r/microsoft/applicationinsights/) 하며 호스트와 컨테이너는 Docker 이미지 뿐만 아니라 호스트에 대 한 성능 카운터에 표시 되므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-113">You just need to run the [Application Insights Docker image](https://hub.docker.com/r/microsoft/applicationinsights/) as a container in your host, and it will display performance counters for the host as well as for the other Docker images.</span></span> <span data-ttu-id="7008e-114">이 응용 프로그램 통찰력 Docker 이미지 (그림 6-1)를 사용 하면 컨테이너 화 된 응용 프로그램 성능 및 Docker 호스트 (즉, Linux Vm), Docker 컨테이너 및 실행 중인 응용 프로그램의 동작에 대 한 원격 분석을 수집 하 여 모니터링 내 합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-114">This Application Insights Docker image (Figure 6-1) helps you to monitor your containerized applications by collecting telemetry about the performance and activity of your Docker host (that is, your Linux VMs), Docker containers and the applications running within them.</span></span>

![예제](./media/image1.png)

<span data-ttu-id="7008e-116">그림 6-1: Application Insights Docker 호스트와 컨테이너를 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-116">Figure 6-1: Application Insights monitoring Docker hosts and containers</span></span>

<span data-ttu-id="7008e-117">실행 하는 경우는 [응용 프로그램 통찰력 Docker 이미지](https://hub.docker.com/r/microsoft/applicationinsights/) Docker 호스트에서 다음 중 하나를 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-117">When you run the [Application Insights Docker image](https://hub.docker.com/r/microsoft/applicationinsights/) on your Docker host, you benefit from the following:</span></span>

-   <span data-ttu-id="7008e-118">호스트에서 실행 중인 모든 컨테이너에 대 한 원격 분석 수명 주기-시작, 중지 및 등입니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-118">Life-cycle telemetry about all the containers running on the host—start, stop, and so on.</span></span>

-   <span data-ttu-id="7008e-119">모든 컨테이너에 대 한 성능 카운터: CPU, 메모리, 네트워크 사용 등입니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-119">Performance counters for all the containers: CPU, memory, network usage, and more.</span></span>

-   <span data-ttu-id="7008e-120">도 설치 되어 있으면 [Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) 컨테이너에서 실행 중인 앱에서이 앱의 모든 원격 분석 컨테이너와 호스트 컴퓨터를 식별 하는 추가 속성이 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-120">If you also installed [Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) in the apps running in the containers, all the telemetry of those apps will have additional properties identifying the container and host machine.</span></span> <span data-ttu-id="7008e-121">따라서 예를 들어 둘 이상의 호스트에서 실행 되는 앱의 인스턴스를 설정한 경우 쉽게 수 있습니다 호스트에 의해 앱 원격 분석을 필터링 할 합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-121">So, for example, if you have instances of an app running in more than one host, you'll easily be able to filter your app telemetry by host.</span></span>

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a><span data-ttu-id="7008e-122">응용 프로그램 Docker 및 Docker 호스트를 모니터링 하려면 Application Insights 설정</span><span class="sxs-lookup"><span data-stu-id="7008e-122">Setting up Application Insights to monitor Docker applications and Docker hosts</span></span>

<span data-ttu-id="7008e-123">Application Insights 리소스를 만들려면 뒤에 오는 목록에 표시 되는 문서에 대 한 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="7008e-123">To create an Application Insights resource, follow the instructions in the articles presented in the list that follows.</span></span> <span data-ttu-id="7008e-124">Azure 포털에서 필요한 스크립트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-124">Azure Portal will create the necessary script for you.</span></span>

-   <span data-ttu-id="7008e-125">**Application Insights에서 Docker 응용 프로그램 모니터링:**[https://docs.microsoft.com/azure/application-insights/app-insights-docker  ](https://docs.microsoft.com/azure/application-insights/app-insights-docker)</span><span class="sxs-lookup"><span data-stu-id="7008e-125">**Monitor Docker applications in Application Insights:**  [https://docs.microsoft.com/azure/application-insights/app-insights-docker](https://docs.microsoft.com/azure/application-insights/app-insights-docker)</span></span>

-   <span data-ttu-id="7008e-126">**Docker 허브 및 Github에서 응용 프로그램 통찰력 Docker 이미지:**</span><span class="sxs-lookup"><span data-stu-id="7008e-126">**Application Insights Docker image at Docker Hub and Github:**</span></span>  
<span data-ttu-id="7008e-127">[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) 및 <https://github.com/Microsoft/ApplicationInsights-Docker></span><span class="sxs-lookup"><span data-stu-id="7008e-127">[https://hub.docker.com/r/microsoft/applicationinsights/](https://hub.docker.com/r/microsoft/applicationinsights/) and <https://github.com/Microsoft/ApplicationInsights-Docker></span></span>

-   <span data-ttu-id="7008e-128">**ASP.NET 용 Application Insights를 설정 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7008e-128">**Set up Application Insights for ASP.NET:**</span></span>  
[<span data-ttu-id="7008e-129">https://docs.microsoft.com/azure/application-insights/app-insights-asp-net</span><span class="sxs-lookup"><span data-stu-id="7008e-129">https://docs.microsoft.com/azure/application-insights/app-insights-asp-net</span></span>](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)

-   <span data-ttu-id="7008e-130">**웹 페이지 용 application Insights:**</span><span class="sxs-lookup"><span data-stu-id="7008e-130">**Application Insights for web pages:**</span></span>  
<span data-ttu-id="7008e-131"><https://docs.microsoft.com/azure/application-insights/app-insights-javascript></span><span class="sxs-lookup"><span data-stu-id="7008e-131"><https://docs.microsoft.com/azure/application-insights/app-insights-javascript></span></span>

## <a name="microsoft-operations-management-suite"></a><span data-ttu-id="7008e-132">Microsoft 작업 관리 도구 모음</span><span class="sxs-lookup"><span data-stu-id="7008e-132">Microsoft Operations Management Suite</span></span>

<span data-ttu-id="7008e-133">[Operations Management Suite](http://microsoft.com/oms) 은 로그 분석, 자동화, 백업 및 사이트 복구를 제공 하는 간소화 된 IT 관리 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-133">[Operations Management Suite](http://microsoft.com/oms) is a simplified IT management solution that provides log analytics, automation, backup, and site recovery.</span></span> <span data-ttu-id="7008e-134">에 따라 [쿼리](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/) 발생 시킬 수 Operations Management Suite에 [경고](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts) 재구성을 통해 설정 [Azure 자동화](https://docs.microsoft.com/azure/automation/)합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-134">Based on [queries](https://blogs.technet.microsoft.com/msoms/2016/01/21/easy-microsoft-operations-management-suite-search-queries/) in Operations Management Suite, you can raise [alerts](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-monitoring-alerts) and set remediation via [Azure Automation](https://docs.microsoft.com/azure/automation/).</span></span> <span data-ttu-id="7008e-135">단일 유리 창 뷰를 제공 하 여 기존 관리 솔루션과 원활 하 게 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-135">It also seamlessly integrates with your existing management solutions to provide a single pane-of-glass view.</span></span> <span data-ttu-id="7008e-136">Operations Management Suite를 사용 하면 관리 하 고 보호할 온-프레미스 및 클라우드 인프라 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-136">Operations Management Suite helps you to manage and protect your on-premises and cloud infrastructure.</span></span>

### <a name="operations-management-suitehttpmicrosoftcomoms-container-solution-for-docker"></a><span data-ttu-id="7008e-137">[Operations Management Suite](http://microsoft.com/oms) Docke에 대 한 컨테이너 솔루션</span><span class="sxs-lookup"><span data-stu-id="7008e-137">[Operations Management Suite](http://microsoft.com/oms) Container Solution for Docker</span></span>

<span data-ttu-id="7008e-138">자체적으로 중요 한 서비스를 제공할 뿐 아니라 Operations Management Suite 컨테이너 솔루션 관리 및 모니터링할 수 Docker 호스트와 컨테이너에 컨테이너와 컨테이너 호스트는에 대 한 정보를 표시 하 여 컨테이너는 실행 되는 실패, 또는 및 Docker 디먼 및 컨테이너 로그로 전송 *stdout* 및 *stderr*합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-138">In addition to providing valuable services on its own, the Operations Management Suite Container Solution can manage and monitor Docker hosts and containers by showing information about where your containers and container hosts are, which containers are running or failed, and Docker daemon and container logs sent to *stdout* and *stderr*.</span></span> <span data-ttu-id="7008e-139">또한 CPU, 메모리, 네트워크 및 저장소 컨테이너 및 문제를 해결 하 고 시끄러운 이웃 컨테이너를 찾을 수 있도록 호스트와 같은 성능 메트릭을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-139">It also shows performance metrics such as CPU, memory, network, and storage for the container and hosts to help you troubleshoot and find noisy neighbor containers.</span></span>

![](./media/image2.png)

<span data-ttu-id="7008e-140">Operations Management Suite로 표시 된 Docker 컨테이너에 대 한 그림 6-2: 정보</span><span class="sxs-lookup"><span data-stu-id="7008e-140">Figure 6-2: Information about Docker containers shown by Operations Management Suite</span></span>

<span data-ttu-id="7008e-141">Application Insights 및 Operations Management Suite 작업 모니터링에 집중 그러나 Application Insights에 주안점을 두 응용 프로그램 내에서 실행 되는 SDK 덕분에 앱을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-141">Application Insights and Operations Management Suite both focus on monitoring activities; however, Application Insights focuses more on monitoring the apps themselves thanks to its SDK running within the app.</span></span> <span data-ttu-id="7008e-142">그러나 Operations Management Suite는 호스트, 주위 인프라 훨씬 더 중점적 플러스 매우 유연한 데이터 기반 검색/쿼리 시스템을 제공 하는 동안 규모에 로그에 심층 분석을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-142">However, Operations Management Suite focuses much more on the infrastructure around the hosts, plus it offers deep analysis on logs at scale while providing a very flexible data-driven search/query system.</span></span>

<span data-ttu-id="7008e-143">Operations Management Suite를 클라우드 기반 서비스로 구현 되므로 빠르게 사용할 수 있습니다이 실행 되 고 인프라 서비스에 최소한만 투자 하면서 합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-143">Because Operations Management Suite is implemented as a cloud-based service, you can have it up and running quickly with minimal investment in infrastructure services.</span></span> <span data-ttu-id="7008e-144">새로운 기능이 자동적으로 전달 되므로 지속적인 유지 관리에서 절약 및 업그레이드 비용이 절감 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-144">New features are delivered automatically, saving you from ongoing maintenance and upgrade costs.</span></span>

<span data-ttu-id="7008e-145">Operations Management Suite 컨테이너 솔루션을 사용 하면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-145">Using Operations Management Suite Container Solution, you can do the following:</span></span>

-   <span data-ttu-id="7008e-146">중앙 집중화 하 고 및 수백만 규모에 Docker 컨테이너에서 로그의 상관 관계 지정</span><span class="sxs-lookup"><span data-stu-id="7008e-146">Centralize and correlate millions of logs from Docker containers at scale</span></span>

-   <span data-ttu-id="7008e-147">단일 위치에 있는 모든 컨테이너 호스트에 대 한 정보를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7008e-147">See information about all container hosts in a single location</span></span>

-   <span data-ttu-id="7008e-148">컨테이너를 실행 중인 어떤 이미지를 실행 및 실행 하는 위치</span><span class="sxs-lookup"><span data-stu-id="7008e-148">Know which containers are running, what image they're running, and where they're running</span></span>

-   <span data-ttu-id="7008e-149">컨테이너 호스트에서 문제가 발생할 수 있는 "시끄러운 이웃" 컨테이너를 신속 하 게 진단</span><span class="sxs-lookup"><span data-stu-id="7008e-149">Quickly diagnose "noisy neighbor" containers that can cause problems on container hosts</span></span>

-   <span data-ttu-id="7008e-150">컨테이너에서 작업에 대 한 감사 내역을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7008e-150">See an audit trail for actions on containers</span></span>

-   <span data-ttu-id="7008e-151">보기 및 Docker 호스트에 원격 없이 중앙 집중화 된 로그를 검색 하 여 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7008e-151">Troubleshoot by viewing and searching centralized logs without remoting to the Docker hosts</span></span>

-   <span data-ttu-id="7008e-152">"시끄러운 이웃" 및 과도 한 리소스는 호스트에서 소비 될 수 있는 컨테이너를 찾기</span><span class="sxs-lookup"><span data-stu-id="7008e-152">Find containers that might be "noisy neighbors" and consuming excess resources on a host</span></span>

-   <span data-ttu-id="7008e-153">중앙 집중식된 CPU, 메모리, 저장소 및 컨테이너에 대 한 네트워크 사용량 및 성능 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="7008e-153">View centralized CPU, memory, storage, and network usage and performance information for containers</span></span>

-   <span data-ttu-id="7008e-154">생성 Azure 자동화를 사용 하 여 Docker 컨테이너를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-154">Generate test Docker containers with Azure Automation</span></span>

<span data-ttu-id="7008e-155">형식이 같은 쿼리를 실행 하 여 성능 정보를 볼 수 = Perf, 그림 6-3에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-155">You can see performance information by running queries like Type=Perf, as shown in Figure 6-3.</span></span>

![DockerPerfMetricsView](./media/image3.png)<span data-ttu-id="7008e-157">{너비 높이 "5.78625에" = = "3.25"을 (를)</span><span class="sxs-lookup"><span data-stu-id="7008e-157">{width="5.78625in" height="3.25in"}</span></span>

<span data-ttu-id="7008e-158">Operations Management Suite로 표시 된 Docker 호스트의 그림 6-3: 성능 메트릭</span><span class="sxs-lookup"><span data-stu-id="7008e-158">Figure 6-3: Performance metrics of Docker hosts shown by Operations Management Suite</span></span>

<span data-ttu-id="7008e-159">쿼리를 저장할 Operations Management Suite의 표준 기능이 며 도와 유용 발견 한 및 시스템의 추세를 파악 하는 쿼리를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-159">Saving queries is also a standard feature in Operations Management Suite and can help you keep queries you've found useful and discover trends in your system.</span></span>

<span data-ttu-id="7008e-160">**자세한 내용은** 컨테이너 솔루션에 설치 하 고 Docker 구성 정보를 찾으려면 [Operations Management Suite](http://microsoft.com/oms)로 이동 <https://docs.microsoft.com/azure/ 로그-분석/로그-분석-컨테이너>합니다.</span><span class="sxs-lookup"><span data-stu-id="7008e-160">**More info** To find information on installing and configuring the Docker container solution in [Operations Management Suite](http://microsoft.com/oms), go to <https://docs.microsoft.com/azure/log-analytics/log-analytics-containers>.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="7008e-161">[이전] (관리-프로덕션-docker-environments.md) [다음] (... /key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="7008e-161">[Previous] (manage-production-docker-environments.md) [Next] (../key-takeaways/index.md)</span></span>
