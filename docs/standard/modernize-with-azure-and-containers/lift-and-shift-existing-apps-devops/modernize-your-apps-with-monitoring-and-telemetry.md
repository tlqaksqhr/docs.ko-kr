---
title: "모니터링 및 원격 분석을 사용 하 여 앱을 최신식"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 모니터링 및 원격 분석을 사용 하 여 앱을 최신식"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 03a6f2be9dc6c020cfe93a2597d1288943e527c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a><span data-ttu-id="07732-103">모니터링 및 원격 분석을 사용 하 여 앱을 최신식</span><span class="sxs-lookup"><span data-stu-id="07732-103">Modernize your apps with monitoring and telemetry</span></span>

<span data-ttu-id="07732-104">프로덕션 환경에서 응용 프로그램을 실행 하는 경우에 응용 프로그램은 수행 하는 방법에 대 한 통찰력을 해야 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-104">When you run an application in production, it's critical that you have insights about how your application is performing.</span></span> <span data-ttu-id="07732-105">상위 수준에서 수행 하는 것?</span><span class="sxs-lookup"><span data-stu-id="07732-105">Is it performing at a high level?</span></span> <span data-ttu-id="07732-106">사용자가 오류를 가져오는지 안정적이 고 신뢰할 수 있는 사용자가 응용 프로그램 또는?</span><span class="sxs-lookup"><span data-stu-id="07732-106">Are users getting errors, or is the application stable and reliable?</span></span> <span data-ttu-id="07732-107">풍부한 성능 모니터링, 강력한 경고 및 대시보드 응용 프로그램을 사용 가능 하 고 예상 대로 수행 되지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-107">You need rich performance monitoring, powerful alerting, and dashboards to help ensure that your application is available and performing as expected.</span></span> <span data-ttu-id="07732-108">문제가 있는지 신속 하 게 확인, 영향을 받는 하 고 찾고 문제를 해결 하는 근본 원인 분석을 수행 하는 얼마나 많은 고객을 결정 하는 작업을 할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-108">You also need to be able to see quickly if there's a problem, determine how many customers are affected, and perform a root-cause analysis to find and fix the issue.</span></span>

## <a name="monitor-your-application-with-application-insights"></a><span data-ttu-id="07732-109">Application Insights로 응용 프로그램을 모니터링합니다</span><span class="sxs-lookup"><span data-stu-id="07732-109">Monitor your application with Application Insights</span></span>

<span data-ttu-id="07732-110">Application Insights에는 여러 플랫폼에서 작업 하는 웹 개발자를 위한 확장 가능한 응용 프로그램 성능 관리 (APM) 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="07732-110">Application Insights is an extensible Application Performance Management (APM) service for web developers who work on multiple platforms.</span></span> <span data-ttu-id="07732-111">실시간 웹 응용 프로그램 모니터링을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-111">Use it to monitor your live web application.</span></span> <span data-ttu-id="07732-112">Application Insights 성능 예외를 자동으로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-112">Application Insights automatically detects performance anomalies.</span></span> <span data-ttu-id="07732-113">사용자가 실제로 수행할 작업을 앱과 쉽게 이해할 수 있도록 하 고 문제를 진단할 수 있도록 강력한 분석 도구를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-113">It includes powerful analytics tools to help you diagnose issues, and to help you understand what users actually do with your app.</span></span> <span data-ttu-id="07732-114">Application Insights는 성능과 유용성을 지속적으로 향상 시킬 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="07732-114">Application Insights is designed to help you continuously improve performance and usability.</span></span> <span data-ttu-id="07732-115">다양 한 플랫폼에서.NET, Node.js, 및 J2EE, 여부 등의 앱에 대 한 작동 온-프레미스 호스트 또는 클라우드입니다.</span><span class="sxs-lookup"><span data-stu-id="07732-115">It works for apps on a wide variety of platforms, including .NET, Node.js, and J2EE, whether hosted on-premises or in the cloud.</span></span> <span data-ttu-id="07732-116">Application Insights DevOps 프로세스와 통합 되어 있으며 다양 한 개발 도구에 대 한 연결 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="07732-116">Application Insights integrates with your DevOps processes, and has connection points to a variety of development tools.</span></span>

<span data-ttu-id="07732-117">그림 4-10에는 Application Insights에서 응용 프로그램을 모니터링 하는 방법 및 대시보드에 해당 insights 것 표시 방법의 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07732-117">Figure 4-10 shows an example of how Application Insights monitors your application and how it surfaces those insights to a dashboard.</span></span>

![Application Insights 대시보드 모니터링](./media/image10.png)

> <span data-ttu-id="07732-119">**그림 4-10입니다.**</span><span class="sxs-lookup"><span data-stu-id="07732-119">**Figure 4-10.**</span></span> <span data-ttu-id="07732-120">Application Insights 대시보드 모니터링</span><span class="sxs-lookup"><span data-stu-id="07732-120">Application Insights monitoring dashboard</span></span>

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a><span data-ttu-id="07732-121">로그 분석 워크 로드와 해당 컨테이너 모니터링 솔루션으로 Docker 인프라 모니터링</span><span class="sxs-lookup"><span data-stu-id="07732-121">Monitor your Docker infrastructure with Log Analytics and its Container Monitoring solution</span></span>

<span data-ttu-id="07732-122">[Azure 로그 분석](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) 의 일부는 [Microsoft Azure 모니터링 솔루션 전체](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) is part of the [Microsoft Azure overall monitoring solution](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span></span> <span data-ttu-id="07732-123">´ Â 서비스 [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-123">It's also a service in [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span> <span data-ttu-id="07732-124">로그 분석 모니터링 하는 클라우드 및 온-프레미스 환경 (온-프레미스에 대 한 OMS) 가용성과 성능을 유지 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-124">Log Analytics monitors cloud and on-premises environments (OMS for on-premises) to help maintain availability and performance.</span></span> <span data-ttu-id="07732-125">여러 원본에서 분석 기능을 제공 하려면 다른 모니터링 도구와 클라우드 및 온-프레미스 환경에서 리소스에 의해 생성 된 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-125">It collects data generated by resources in your cloud and on-premises environments and from other monitoring tools to provide analysis across multiple sources.</span></span>

<span data-ttu-id="07732-126">Azure 인프라 로그를 기준으로 로그 분석 Azure 서비스로 수집 다른 Azure 서비스의 로그 및 메트릭 데이터 (통해 [Azure 모니터](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure Vm, Docker 컨테이너 및 온-프레미스 또는 다른 클라우드 인프라입니다.</span><span class="sxs-lookup"><span data-stu-id="07732-126">In relation to Azure infrastructure logs, Log Analytics, as an Azure service, ingests log and metric data from other Azure services (via [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure VMs, Docker containers, and on-premises or other cloud infrastructures.</span></span> <span data-ttu-id="07732-127">로그 분석은 유연한 로그 검색 및이 데이터를 기반으로 아웃-기본 분석을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-127">Log Analytics offers flexible log search and out-of-the box analytics on top of this data.</span></span> <span data-ttu-id="07732-128">지정 된 조건에 따라 원본 간에 데이터를 분석 하는 데 사용할 수는 모든 로그에서 복잡 한 쿼리를 허용 및 사전 경고할 수 있습니다 풍부한 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-128">It provides rich tools that you can use to analyze data across sources, it allows complex queries across all logs, and it can proactively alert based on specified conditions.</span></span> <span data-ttu-id="07732-129">중앙 로그 분석 저장소를 쿼리 하 고 시각화할 수의 사용자 지정 데이터도 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07732-129">You can even collect custom data in the central Log Analytics repository, where you can query and visualize it.</span></span> <span data-ttu-id="07732-130">인프라의 기능 및 보안에 대 한 정보를 즉시 로그 분석 기본 제공 솔루션을 활용할도 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07732-130">You also can take advantage of the Log Analytics built-in solutions to immediately gain insights into the security and functionality of your infrastructure.</span></span>

<span data-ttu-id="07732-131">OMS 포털 또는 모든 브라우저에서 실행 하면 Azure 포털을 통해 로그 분석에 액세스할 수 있으며 구성 설정에 액세스할 수 있습니다 및 여러 도구 제공 분석 하 고 수집 된 데이터 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07732-131">You can access Log Analytics through the OMS portal or the Azure portal, which run in any browser, and provide you with access to configuration settings and multiple tools to analyze and act on collected data.</span></span>

<span data-ttu-id="07732-132">[컨테이너 모니터링 솔루션](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) 로그 분석을 통해에서 보기 있습니다 및이 단일 위치에 Docker 및 Windows 컨테이너 호스트를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-132">The [Container Monitoring solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics helps you view and manage your Docker and Windows Container hosts in a single location.</span></span> <span data-ttu-id="07732-133">솔루션을 보여 줍니다 컨테이너를 실행 하 고 컨테이너를 실행 하는 어떤 컨테이너 이미지를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-133">The solution shows which containers are running, what container image they're running, and where containers are running.</span></span> <span data-ttu-id="07732-134">컨테이너와 사용 중인 명령을 포함 한 자세한 감사 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07732-134">You can view detailed audit information, including commands that are being used with containers.</span></span> <span data-ttu-id="07732-135">보기 및 원격으로 Windows 또는 Docker 호스트를 보는 데 필요 없이 중앙 집중화 된 로그를 검색 하 여 컨테이너를 해결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07732-135">You also can troubleshoot containers by viewing and searching centralized logs, without needing to remotely view Docker or Windows hosts.</span></span> <span data-ttu-id="07732-136">호스트에서 초과 리소스 노이즈가 많고 소비 될 수 있는 컨테이너를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07732-136">You can find containers that might be noisy and consuming excess resources on a host.</span></span> <span data-ttu-id="07732-137">중앙 집중식된 CPU, 메모리, 저장소 및 네트워크 사용량 및 컨테이너에 대 한 성능 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07732-137">Additionally, you can view centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span> <span data-ttu-id="07732-138">Windows를 실행 하는 컴퓨터에 중앙 집중화 하 고 있고 Windows Server에서 로그를 비교 하이퍼-V 및 Docker 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="07732-138">On computers running Windows, you can centralize and compare logs from Windows Server, Hyper-V, and Docker containers.</span></span> <span data-ttu-id="07732-139">솔루션에는 다음과 같은 컨테이너 orchestrators 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-139">The solution supports the following container orchestrators:</span></span>

-   <span data-ttu-id="07732-140">Docker 웜</span><span class="sxs-lookup"><span data-stu-id="07732-140">Docker Swarm</span></span>

-   <span data-ttu-id="07732-141">DC/OS</span><span class="sxs-lookup"><span data-stu-id="07732-141">DC/OS</span></span>

-   <span data-ttu-id="07732-142">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="07732-142">Kubernetes</span></span>

-   <span data-ttu-id="07732-143">서비스 패브릭</span><span class="sxs-lookup"><span data-stu-id="07732-143">Service Fabric</span></span>

-   <span data-ttu-id="07732-144">Red Hat OpenShift</span><span class="sxs-lookup"><span data-stu-id="07732-144">Red Hat OpenShift</span></span>

<span data-ttu-id="07732-145">그림 4-11 다양 한 컨테이너 호스트와 에이전트와 OMS 간의 관계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="07732-145">Figure 4-11 shows the relationships between various container hosts and agents and OMS.</span></span>

![로그 분석 컨테이너 모니터링 솔루션](./media/image11.png)

> <span data-ttu-id="07732-147">**그림 4-11입니다.**</span><span class="sxs-lookup"><span data-stu-id="07732-147">**Figure 4-11.**</span></span> <span data-ttu-id="07732-148">로그 분석 컨테이너 모니터링 솔루션</span><span class="sxs-lookup"><span data-stu-id="07732-148">Log Analytics Container Monitoring solution</span></span>

<span data-ttu-id="07732-149">로그 분석 컨테이너 모니터링 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07732-149">You can use the Log Analytics Container Monitoring solution to:</span></span>

-   <span data-ttu-id="07732-150">단일 위치에 있는 모든 컨테이너 호스트에 대 한 정보를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="07732-150">See information about all container hosts in a single location.</span></span>

-   <span data-ttu-id="07732-151">컨테이너를를 실행 하 고 실행 중인 어떤 이미지를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-151">Know which containers are running, what image they're running, and where they're running.</span></span>

-   <span data-ttu-id="07732-152">컨테이너에 작업에 대 한 감사 내역을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="07732-152">See an audit trail for actions on containers.</span></span>

-   <span data-ttu-id="07732-153">보기 및 Docker 호스트에 대 한 원격 로그인 없이 중앙 집중화 된 로그를 검색 하 여이 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="07732-153">Troubleshoot by viewing and searching centralized logs without remote login to the Docker hosts.</span></span>

-   <span data-ttu-id="07732-154">호스트에 과도 한 리소스 사용 되 고 "시끄러운 이웃" 될 수 있는 컨테이너를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="07732-154">Find containers that might be "noisy neighbors," and be consuming excess resources on a host.</span></span>

-   <span data-ttu-id="07732-155">중앙 집중식된 CPU, 메모리, 저장소 및 네트워크 사용량 및 컨테이너에 대 한 성능 정보를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="07732-155">View centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="07732-156">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="07732-156">Additional resources</span></span>

-   <span data-ttu-id="07732-157">**Microsoft Azure에서 모니터링 개요**</span><span class="sxs-lookup"><span data-stu-id="07732-157">**Overview of monitoring in Microsoft Azure**</span></span>

[<span data-ttu-id="07732-158">https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview</span><span class="sxs-lookup"><span data-stu-id="07732-158">https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview</span></span>](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)

-   <span data-ttu-id="07732-159">**Application Insights 란?**</span><span class="sxs-lookup"><span data-stu-id="07732-159">**What is Application Insights?**</span></span>

[<span data-ttu-id="07732-160">https://docs.microsoft.com/azure/application-insights/app-insights-overview</span><span class="sxs-lookup"><span data-stu-id="07732-160">https://docs.microsoft.com/azure/application-insights/app-insights-overview</span></span>](https://docs.microsoft.com/azure/application-insights/app-insights-overview)

-   <span data-ttu-id="07732-161">**로그 분석 이란?**</span><span class="sxs-lookup"><span data-stu-id="07732-161">**What is Log Analytics?**</span></span>

[<span data-ttu-id="07732-162">https://docs.microsoft.com/azure/log-analytics/log-analytics-overview</span><span class="sxs-lookup"><span data-stu-id="07732-162">https://docs.microsoft.com/azure/log-analytics/log-analytics-overview</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)

-   <span data-ttu-id="07732-163">**로그 분석에서 컨테이너 모니터링 솔루션**</span><span class="sxs-lookup"><span data-stu-id="07732-163">**Container Monitoring solution in Log Analytics**</span></span>

[<span data-ttu-id="07732-164">https://docs.microsoft.com/azure/log-analytics/log-analytics-containers</span><span class="sxs-lookup"><span data-stu-id="07732-164">https://docs.microsoft.com/azure/log-analytics/log-analytics-containers</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)

-   <span data-ttu-id="07732-165">**Azure 모니터 개요**</span><span class="sxs-lookup"><span data-stu-id="07732-165">**Overview of Azure Monitor**</span></span>

[<span data-ttu-id="07732-166">https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor</span><span class="sxs-lookup"><span data-stu-id="07732-166">https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor</span></span>](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)

-   <span data-ttu-id="07732-167">**Operations Management Suite (OMS) 이란?**</span><span class="sxs-lookup"><span data-stu-id="07732-167">**What is Operations Management Suite (OMS)?**</span></span>

[<span data-ttu-id="07732-168">https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview</span><span class="sxs-lookup"><span data-stu-id="07732-168">https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview</span></span>](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

-   <span data-ttu-id="07732-169">**OMS와 함께 서비스 패브릭에서 Windows Server 컨테이너를 모니터링합니다.**</span><span class="sxs-lookup"><span data-stu-id="07732-169">**Monitoring Windows Server containers in Service Fabric with OMS**</span></span>

[<span data-ttu-id="07732-170">https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver</span><span class="sxs-lookup"><span data-stu-id="07732-170">https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver</span></span>](https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver)

>[!div class="step-by-step"]
<span data-ttu-id="07732-171">[이전](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[다음](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="07732-171">[Previous](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Next](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span></span>
