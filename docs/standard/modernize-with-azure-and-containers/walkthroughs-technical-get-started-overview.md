---
title: "연습 및 technical 시작된 개요 가져오기"
description: "기존.NET 응용 프로그램을 Azure 클라우드 및 Windows 컨테이너를 최신식 | 연습 및 technical 시작된 개요 가져오기"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ead28fe1ffe1e002af73642a1c3b2e72479520f4
ms.sourcegitcommit: bf8a3ba647252010bdce86dd914ac6c61b5ba89d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2018
---
# <a name="walkthroughs-and-technical-get-started-overview"></a><span data-ttu-id="92c86-103">연습 및 technical 시작된 개요 가져오기</span><span class="sxs-lookup"><span data-stu-id="92c86-103">Walkthroughs and technical get started overview</span></span> 

<span data-ttu-id="92c86-104">이 전자책 (영문)의 크기를 제한 하려면 만들었고 추가 기술 설명서 및 전체 연습 GitHub 리포지토리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-104">To limit the size of this e-book, we've made additional technical documentation and the full walkthroughs available in a GitHub repo.</span></span> <span data-ttu-id="92c86-105">온라인 일련의이 장에서 설명 하는 연습에서는 Windows 컨테이너와 Azure로 배포를 기반으로 하는 여러 환경 설치 하는 단계별 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-105">The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.</span></span>

<span data-ttu-id="92c86-106">다음 섹션에서는 각 연습 란에 대 한 해당 목표, 상위 수준 비전-하 고 관련 된 작업에 대 한 다이어그램을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-106">The following sections explain what each walkthrough is about-its objectives, its high-level vision-and provides a diagram of the tasks that are involved.</span></span> <span data-ttu-id="92c86-107">자체의 연습을 얻을 수에 *eShopModernizing* 앱 GitHub 리포지토리에 wiki에서 [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki)합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-107">You can get the walkthroughs themselves in the *eShopModernizing* apps GitHub repo wiki at [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki).</span></span>

# <a name="technical-walkthrough-list"></a><span data-ttu-id="92c86-108">기술 연습 목록</span><span class="sxs-lookup"><span data-stu-id="92c86-108">Technical walkthrough list</span></span>

<span data-ttu-id="92c86-109">다음 started 연습 리프트 하 및 컨테이너를 사용 하 여 이동 하 고 다음 Azure에서 배포의 여러 선택 항목을 사용 하 여 이동할 수 있는 샘플 응용 프로그램에 일관 되 고 포괄적인 기술 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-109">The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.</span></span>

<span data-ttu-id="92c86-110">다음 연습 중 각각의 새 샘플 eShopLegacy 및 eShopModernizing 앱의 경우에 GitHub에서 사용할 수 있는 사용 하 여 [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing)합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-110">Each of the following walkthroughs uses the new sample eShopLegacy and eShopModernizing apps, which are available on GitHub at [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

-   <span data-ttu-id="92c86-111">**둘러보기의 eShop 레거시 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="92c86-111">**Tour of eShop legacy apps**</span></span>

-   <span data-ttu-id="92c86-112">**Windows 컨테이너를 기존.NET 응용 프로그램을 컨테이너 화합니다**</span><span class="sxs-lookup"><span data-stu-id="92c86-112">**Containerize your existing .NET applications with Windows Containers**</span></span>

-   <span data-ttu-id="92c86-113">**Azure Vm에 Windows 컨테이너 기반 앱 배포**</span><span class="sxs-lookup"><span data-stu-id="92c86-113">**Deploy your Windows Containers-based app to Azure VMs**</span></span>

-   <span data-ttu-id="92c86-114">**Azure 컨테이너 서비스에서 Kubernetes에 Windows 컨테이너 기반 앱 배포**</span><span class="sxs-lookup"><span data-stu-id="92c86-114">**Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service**</span></span>

-   <span data-ttu-id="92c86-115">**Azure 서비스 패브릭에 Windows 컨테이너 기반 앱 배포**</span><span class="sxs-lookup"><span data-stu-id="92c86-115">**Deploy your Windows Containers-based apps to Azure Service Fabric**</span></span>

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a><span data-ttu-id="92c86-116">EShop 레거시 응용 프로그램 연습 1: 둘러보기</span><span class="sxs-lookup"><span data-stu-id="92c86-116">Walkthrough 1: Tour of eShop legacy apps</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="92c86-117">기술 연습 가용성</span><span class="sxs-lookup"><span data-stu-id="92c86-117">Technical walkthrough availability</span></span>

<span data-ttu-id="92c86-118">전체 기술 eShopModernizing GitHub 리포지토리에 wiki에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-118">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="92c86-119">https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code</span><span class="sxs-lookup"><span data-stu-id="92c86-119">https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

### <a name="overview"></a><span data-ttu-id="92c86-120">개요</span><span class="sxs-lookup"><span data-stu-id="92c86-120">Overview</span></span>

<span data-ttu-id="92c86-121">이 연습에서는 두 개의 샘플 레거시 응용 프로그램의 초기 구현을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-121">In this walkthrough, you can explore the initial implementation of two sample legacy applications.</span></span> <span data-ttu-id="92c86-122">두 샘플 앱은 모놀리식 아키텍처 및 기존 ASP.NET을 사용 하 여 만든 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-122">Both sample apps have a monolithic architecture, and were created by using classic ASP.NET.</span></span> <span data-ttu-id="92c86-123">ASP.NET을 기반으로 한 응용 프로그램은 4.x MVC; 두 번째 응용 프로그램은 ASP.NET 4.x Web Forms를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-123">One application is based on ASP.NET 4.x MVC; the second application is based on ASP.NET 4.x Web Forms.</span></span> <span data-ttu-id="92c86-124">응용 프로그램은 모두에 [eShopModernizing GitHub 리포지토리](https://github.com/dotnet-architecture/eShopModernizing)합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-124">Both applications are in the [eShopModernizing GitHub repo](https://github.com/dotnet-architecture/eShopModernizing).</span></span>

<span data-ttu-id="92c86-125">두 샘플 앱을 컨테이너 화할 수, 하는 방식과 비슷하게 수 컨테이너 화할 때는 기존 [Windows Communication Foundation](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) (WCF) 응용 프로그램을 데스크톱 응용 프로그램으로 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-125">You can containerize both sample apps, similar to the way you can containerize a classic [Windows Communication Foundation](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) (WCF) application to be consumed as a desktop application.</span></span> <span data-ttu-id="92c86-126">예를 들어 참조 [eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms)합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-126">For an example, see [eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms).</span></span>

### <a name="goals"></a><span data-ttu-id="92c86-127">목표</span><span class="sxs-lookup"><span data-stu-id="92c86-127">Goals</span></span>

<span data-ttu-id="92c86-128">이 연습에서는 주요 목표는 단순히 코드 및 구성 하 고 이러한 앱을 친숙 해지기 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-128">The main goal of this walkthrough is simply to get familiar with these apps, and with their code and configuration.</span></span> <span data-ttu-id="92c86-129">생성 하 고 모의 데이터를 사용 하 여 테스트 목적으로 SQL 데이터베이스를 사용 하지 않고 있음을 앱을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-129">You can configure the apps so that they generate and use mock data, without using the SQL database, for testing purposes.</span></span> <span data-ttu-id="92c86-130">이 선택적 구성은 분리 된 방식으로 종속성 주입을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-130">This optional config is based on dependency injection, in a decoupled way.</span></span>

### <a name="scenario"></a><span data-ttu-id="92c86-131">시나리오</span><span class="sxs-lookup"><span data-stu-id="92c86-131">Scenario</span></span>

<span data-ttu-id="92c86-132">그림 5-1 원래 레거시 응용 프로그램의 간단한 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-132">Figure 5-1 shows the simple scenario of the original legacy applications.</span></span>

> ![원래 레거시 응용 프로그램의 간단한 아키텍처 시나리오](./media/image5-1.png)
>
> <span data-ttu-id="92c86-134">**그림 5-1입니다.**</span><span class="sxs-lookup"><span data-stu-id="92c86-134">**Figure 5-1.**</span></span> <span data-ttu-id="92c86-135">원래 레거시 응용 프로그램의 간단한 아키텍처 시나리오</span><span class="sxs-lookup"><span data-stu-id="92c86-135">Simple architecture scenario of the original legacy applications</span></span>

<span data-ttu-id="92c86-136">비즈니스 도메인 관점에서 두 앱 모두 동일한 카탈로그 관리 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-136">From a business domain perspective, both apps offer the same catalog management features.</span></span> <span data-ttu-id="92c86-137">EShop 엔터프라이즈 팀의 멤버를 보고 편집할 제품 카탈로그 응용 프로그램을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-137">Members of the eShop enterprise team would use the app to view and edit the product catalog.</span></span> <span data-ttu-id="92c86-138">그림 5-2에는 초기 앱 스크린 샷을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-138">Figure 5-2 shows the initial app screenshots.</span></span>

![ASP.NET MVC와 ASP.NET Web Forms 응용 프로그램 (기존/레거시 technologies)](./media/image5-2.png)

> <span data-ttu-id="92c86-140">**그림 5-2입니다.**</span><span class="sxs-lookup"><span data-stu-id="92c86-140">**Figure 5-2.**</span></span> <span data-ttu-id="92c86-141">ASP.NET MVC와 ASP.NET Web Forms 응용 프로그램 (기존/레거시 technologies)</span><span class="sxs-lookup"><span data-stu-id="92c86-141">ASP.NET MVC and ASP.NET Web Forms applications (existing/legacy technologies)</span></span>

<span data-ttu-id="92c86-142">이들은 탐색 및 카탈로그 항목을 수정 하는 데 사용 되는 웹 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-142">These are web applications that are used to browse and modify catalog entries.</span></span> <span data-ttu-id="92c86-143">두 앱 모두 동일한 비즈니스 기능/기능을 제공 하는 팩트는 단순히 비교 목적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-143">The fact that both apps deliver the same business/functional features is simply for comparison purposes.</span></span> <span data-ttu-id="92c86-144">ASP.NET Web Forms 및 ASP.NET MVC 프레임 워크를 사용 하 여 만든 앱에 대 한 비슷한 현대화 프로세스를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-144">You can see a similar modernization process for apps that were created by using the ASP.NET MVC and ASP.NET Web Forms frameworks.</span></span>

<span data-ttu-id="92c86-145">종속성에 ASP.NET 4.x 또는 이전 버전 (또는 MVC에 대 한 Web Forms에 대 한) 의미 이러한 응용 프로그램 코드는 ASP.NET Core MVC를 사용 하 여 완전히 다시 작성 하지 않으면.NET Core에서 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-145">Dependencies in ASP.NET 4.x or earlier versions (either for MVC or for Web Forms) means that these applications won't run on .NET Core unless the code is fully rewritten by using ASP.NET Core MVC.</span></span> <span data-ttu-id="92c86-146">이 코드를 다시 작성 하거나 다시 설계 않으려면 고 수 있는 기존 응용 프로그램을 컨테이너 화할 계속 동일한.NET 기술 및 동일한 코드를 사용 하 여 지점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-146">This demonstrates the point that if you don't want to re-architect or rewrite code, you can containerize existing applications, and still use the same .NET technologies and the same code.</span></span> <span data-ttu-id="92c86-147">레거시 코드를 변경 하지 않고 컨테이너에서 이러한 응용 프로그램을 실행 하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-147">You can see how you can run applications like these in containers, without any changes to legacy code.</span></span>

### <a name="benefits"></a><span data-ttu-id="92c86-148">이점</span><span class="sxs-lookup"><span data-stu-id="92c86-148">Benefits</span></span>

<span data-ttu-id="92c86-149">이 연습에서는 이점은 간단한: 종속성 주입에 따라 코드 및 응용 프로그램 구성에 잘 알고 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-149">The benefits of this walkthrough are simple: Just get familiar with the code and application configuration, based on dependency injection.</span></span> <span data-ttu-id="92c86-150">그런 다음 컨테이너 화할 나중에 여러 환경에 배포할 때는이 접근 방식으로 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-150">Then, you can experiment with this approach when you containerize and deploy to multiple environments in the future.</span></span>

### <a name="next-steps"></a><span data-ttu-id="92c86-151">다음 단계</span><span class="sxs-lookup"><span data-stu-id="92c86-151">Next steps</span></span>

<span data-ttu-id="92c86-152">GitHub wiki에서이 콘텐츠를 더 자세히 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-152">Explore this content more in-depth on the GitHub wiki:</span></span>

[<span data-ttu-id="92c86-153">https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code</span><span class="sxs-lookup"><span data-stu-id="92c86-153">https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a><span data-ttu-id="92c86-154">연습 2: Windows 컨테이너를 기존.NET 응용 프로그램을 컨테이너 화합니다</span><span class="sxs-lookup"><span data-stu-id="92c86-154">Walkthrough 2: Containerize your existing .NET applications with Windows Containers</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="92c86-155">기술 연습 가용성</span><span class="sxs-lookup"><span data-stu-id="92c86-155">Technical walkthrough availability</span></span>

<span data-ttu-id="92c86-156">전체 기술 eShopModernizing GitHub 리포지토리에 wiki에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-156">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

[<span data-ttu-id="92c86-157">https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker</span><span class="sxs-lookup"><span data-stu-id="92c86-157">https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker</span></span>](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)

### <a name="overview"></a><span data-ttu-id="92c86-158">개요</span><span class="sxs-lookup"><span data-stu-id="92c86-158">Overview</span></span>

<span data-ttu-id="92c86-159">Windows 컨테이너를 사용 하 여 MVC, Web Forms, WCF, 프로덕션, 개발 및 테스트 환경에 기반 하는 것과 같은 기존.NET 응용 프로그램의 배포를 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-159">Use Windows Containers to improve deployment of existing .NET applications, like those based on MVC, Web Forms, or WCF, to production, development, and test environments.</span></span>

### <a name="goals"></a><span data-ttu-id="92c86-160">목표</span><span class="sxs-lookup"><span data-stu-id="92c86-160">Goals</span></span>

<span data-ttu-id="92c86-161">이 연습의 목표 containerizing 기존.NET Framework 응용 프로그램에 대 한 몇 가지 옵션을 표시 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-161">The goal of this walkthrough is to show you several options for containerizing an existing .NET Framework application.</span></span> <span data-ttu-id="92c86-162">다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-162">You can:</span></span>

-   <span data-ttu-id="92c86-163">사용 하 여 응용 프로그램을 컨테이너 화할 [Docker 용 Visual Studio 2017 도구](https://docs.microsoft.com/dotnet/core/docker/visual-studio-tools-for-docker) (Visual Studio 2017 또는 이후 버전).</span><span class="sxs-lookup"><span data-stu-id="92c86-163">Containerize your application by using [Visual Studio 2017 Tools for Docker](https://docs.microsoft.com/dotnet/core/docker/visual-studio-tools-for-docker) (Visual Studio 2017 or later versions).</span></span>

-   <span data-ttu-id="92c86-164">수동으로 추가 하 여 응용 프로그램을 컨테이너 화할는 [Dockerfile](https://docs.docker.com/engine/reference/builder/)를 사용 하 여는 [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-164">Containerize your application by manually adding a [Dockerfile](https://docs.docker.com/engine/reference/builder/), and then using the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/).</span></span>

-   <span data-ttu-id="92c86-165">사용 하 여 응용 프로그램을 컨테이너 화할는 [Img2Docker](https://github.com/docker/communitytools-image2docker-win) 도구 (Docker에서 오픈 소스 도구).</span><span class="sxs-lookup"><span data-stu-id="92c86-165">Containerize your application by using the [Img2Docker](https://github.com/docker/communitytools-image2docker-win) tool (an open-source tool from Docker).</span></span>

<span data-ttu-id="92c86-166">이 연습에서는 Visual Studio 2017 Tools for Docker 접근 방식에 중점을 두고 있지만 Dockerfile을 사용 하 여 시에서 다른 두 가지 방법으로 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-166">This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the other two approaches are fairly similar in regards to using Dockerfiles.</span></span>

### <a name="scenario"></a><span data-ttu-id="92c86-167">시나리오</span><span class="sxs-lookup"><span data-stu-id="92c86-167">Scenario</span></span>

<span data-ttu-id="92c86-168">그림 5-3 색인화 eShop 레거시 응용 프로그램에 대 한 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-168">Figure 5-3 shows the scenario for containerized eShop legacy applications.</span></span>

> ![개발 환경에서 화 된 응용 프로그램의 간소화 된 아키텍처 다이어그램](./media/image5-3.png)
>
> <span data-ttu-id="92c86-170">**그림 5-3입니다.**</span><span class="sxs-lookup"><span data-stu-id="92c86-170">**Figure 5-3.**</span></span> <span data-ttu-id="92c86-171">개발 환경에서 화 된 응용 프로그램의 간소화 된 아키텍처 다이어그램</span><span class="sxs-lookup"><span data-stu-id="92c86-171">Simplified architecture diagram of containerized applications in a development environment</span></span>

### <a name="benefits"></a><span data-ttu-id="92c86-172">이점</span><span class="sxs-lookup"><span data-stu-id="92c86-172">Benefits</span></span>

<span data-ttu-id="92c86-173">컨테이너에서 단일 응용 프로그램을 실행 하는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-173">There are advantages to running your monolithic application in a container.</span></span> <span data-ttu-id="92c86-174">먼저, 응용 프로그램에 대 한 이미지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-174">First, you create an image for the application.</span></span> <span data-ttu-id="92c86-175">해당 시점부터 모든 배포가 동일한 환경에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-175">From that point on, every deployment runs in the same environment.</span></span> <span data-ttu-id="92c86-176">모든 컨테이너 동일한 운영 체제 버전을 사용 하 여, 설치 하는 종속성의 버전은, 동일한.NET framework 버전을 사용 하 여 및 동일한 프로세스를 사용 하 여 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-176">Every container uses the same OS version, has the same version of dependencies installed, uses the same .NET framework version, and is built by using the same process.</span></span> <span data-ttu-id="92c86-177">기본적으로, Docker 이미지를 사용 하 여 응용 프로그램의 종속성을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-177">Basically, you control the dependencies of your application by using a Docker image.</span></span> <span data-ttu-id="92c86-178">종속성의 컨테이너를 배포할 때 응용 프로그램으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-178">The dependencies travel with the application when you deploy the containers.</span></span>

<span data-ttu-id="92c86-179">또 다른 이점은 개발자가 Windows 컨테이너에서 제공 되는 일관 된 환경에서 응용 프로그램을 실행할 수입니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-179">An additional benefit is that developers can run the application in the consistent environment that's provided by Windows Containers.</span></span> <span data-ttu-id="92c86-180">특정 버전으로 표시 하는 문제 스테이징 또는 프로덕션 환경에는 대신 즉시 발견 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-180">Issues that appear only with certain versions can be spotted immediately, instead of surfacing in a staging or production environment.</span></span> <span data-ttu-id="92c86-181">개발 팀의 멤버에서 사용 하는 개발 환경의 차이점 중요 응용 프로그램 컨테이너에서 실행 하는 경우 작습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-181">Differences in development environments used by members of the development team matter less when applications run in containers.</span></span>

<span data-ttu-id="92c86-182">컨테이너 화 된 응용 프로그램에 볼록한 확장 곡선을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-182">Containerized applications also have a flatter scale-out curve.</span></span> <span data-ttu-id="92c86-183">컨테이너 화 된 응용 프로그램 VM 또는 물리적 컴퓨터 컴퓨터당 일반 응용 프로그램 배포에 비해 더 많은 응용 프로그램 및 서비스 인스턴스 (컨테이너에 기반)를 사용할 수 있습니다를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-183">Containerized apps enable you to have more application and service instances (based on containers) in a VM or physical machine compared to regular application deployments per machine.</span></span> <span data-ttu-id="92c86-184">이 명령은 더 높은 밀도 필요한 적은으로 해석 orchestrators Kubernetes 서비스 패브릭 등을 사용 하는 경우에 특히 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-184">This translates to higher density and fewer required resources, especially when you use orchestrators like Kubernetes or Service Fabric.</span></span>

<span data-ttu-id="92c86-185">컨테이너 화 이상적인 상황에서 응용 프로그램 코드를 변경한 필요 하지 않습니다 (C\#).</span><span class="sxs-lookup"><span data-stu-id="92c86-185">Containerization, in ideal situations, does not require making any changes to the application code (C\#).</span></span> <span data-ttu-id="92c86-186">대부분의 시나리오에서 하기만 하면 Docker 배포 메타 데이터 파일 (Dockerfiles 및 Docker Compose 파일).</span><span class="sxs-lookup"><span data-stu-id="92c86-186">In most scenarios, you just need the Docker deployment metadata files (Dockerfiles and Docker Compose files).</span></span>

### <a name="next-steps"></a><span data-ttu-id="92c86-187">다음 단계</span><span class="sxs-lookup"><span data-stu-id="92c86-187">Next steps</span></span>

<span data-ttu-id="92c86-188">GitHub wiki에서이 콘텐츠를 더 자세하게 탐색할: [https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)</span><span class="sxs-lookup"><span data-stu-id="92c86-188">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)</span></span>

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a><span data-ttu-id="92c86-189">Azure Vm에 Windows 컨테이너 기반 앱을 배포 하는 연습 3:</span><span class="sxs-lookup"><span data-stu-id="92c86-189">Walkthrough 3: Deploy your Windows Containers-based app to Azure VMs</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="92c86-190">기술 연습 가용성</span><span class="sxs-lookup"><span data-stu-id="92c86-190">Technical walkthrough availability</span></span>

<span data-ttu-id="92c86-191">전체 기술 eShopModernizing GitHub 리포지토리에 wiki에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-191">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="92c86-192">[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="92c86-192">[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span></span>

### <a name="overview"></a><span data-ttu-id="92c86-193">개요</span><span class="sxs-lookup"><span data-stu-id="92c86-193">Overview</span></span>

<span data-ttu-id="92c86-194">Azure에서 Windows Server 2016 VM에서 Docker 호스트에 배포 하는 개발/테스트/스테이징 환경을 신속 하 게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-194">Deploying to a Docker host on a Windows Server 2016 VM in Azure lets you quickly set up dev/test/staging environments.</span></span> <span data-ttu-id="92c86-195">또한, 테스터 또는 비즈니스 사용자가 유효성을 검사할 앱에 대 한 공통 위치를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-195">It also gives you a common place for testers or business users to validate the app.</span></span> <span data-ttu-id="92c86-196">Vm 유효한 IaaS 프로덕션 환경 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-196">VMs also can be valid IaaS production environments.</span></span>

### <a name="goals"></a><span data-ttu-id="92c86-197">목표</span><span class="sxs-lookup"><span data-stu-id="92c86-197">Goals</span></span>

<span data-ttu-id="92c86-198">이 연습의 목표는 Windows Server 2016 또는 이상 버전을 기반으로 하는 Azure Vm에 Windows 컨테이너를 배포할 때 사용할 수 있는 여러 대체 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-198">The goal of this walkthrough is to show you the multiple alternatives you have when you deploy Windows Containers to Azure VMs that are based on Windows Server 2016 or later versions.</span></span>

### <a name="scenarios"></a><span data-ttu-id="92c86-199">시나리오</span><span class="sxs-lookup"><span data-stu-id="92c86-199">Scenarios</span></span>

<span data-ttu-id="92c86-200">몇 가지 시나리오는이 연습에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-200">Several scenarios are covered in this walkthrough.</span></span>

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a><span data-ttu-id="92c86-201">Docker 엔진 연결을 통해 dev PC에서에서 Azure VM 배포 시나리오 a:</span><span class="sxs-lookup"><span data-stu-id="92c86-201">Scenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection</span></span>

![Docker 엔진 연결을 통해 개발 PC에서에서 Azure VM에 배포](./media/image5-4.png)

> <span data-ttu-id="92c86-203">**그림 5-4입니다.**</span><span class="sxs-lookup"><span data-stu-id="92c86-203">**Figure 5-4.**</span></span> <span data-ttu-id="92c86-204">Docker 엔진 연결을 통해 개발 PC에서에서 Azure VM에 배포</span><span class="sxs-lookup"><span data-stu-id="92c86-204">Deploy to an Azure VM from a dev PC through a Docker Engine connection</span></span>

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a><span data-ttu-id="92c86-205">Docker 레지스트리를 통해 Azure VM에 배포 시나리오 b:</span><span class="sxs-lookup"><span data-stu-id="92c86-205">Scenario B: Deploy to an Azure VM through a Docker Registry</span></span>

![Docker 레지스트리를 통해 Azure VM에 배포](./media/image5-5.png)

> <span data-ttu-id="92c86-207">**그림 5-5입니다.**</span><span class="sxs-lookup"><span data-stu-id="92c86-207">**Figure 5-5.**</span></span> <span data-ttu-id="92c86-208">Docker 레지스트리를 통해 Azure VM에 배포</span><span class="sxs-lookup"><span data-stu-id="92c86-208">Deploy to an Azure VM through a Docker Registry</span></span>

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a><span data-ttu-id="92c86-209">Visual Studio Team Services에서 CI/CD 파이프라인에서 Azure VM에 시나리오 c: 배포</span><span class="sxs-lookup"><span data-stu-id="92c86-209">Scenario C: Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

![Visual Studio Team Services에서 CI/CD 파이프라인에서 Azure VM에 배포](./media/image5-6.png)

> <span data-ttu-id="92c86-211">**그림 5-6입니다.**</span><span class="sxs-lookup"><span data-stu-id="92c86-211">**Figure 5-6.**</span></span> <span data-ttu-id="92c86-212">Visual Studio Team Services에서 CI/CD 파이프라인에서 Azure VM에 배포</span><span class="sxs-lookup"><span data-stu-id="92c86-212">Deploy to an Azure VM from CI/CD pipelines in Visual Studio Team Services</span></span>

### <a name="azure-vms-for-windows-containers"></a><span data-ttu-id="92c86-213">Windows 컨테이너에 대 한 azure Vm</span><span class="sxs-lookup"><span data-stu-id="92c86-213">Azure VMs for Windows Containers</span></span>

<span data-ttu-id="92c86-214">Windows 컨테이너에 대 한 azure Vm은 Windows Server 2016, Windows 10을 기반으로 하는 Vm 하기만 하면 또는 이상 버전에서 모두 Docker 엔진으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-214">Azure VMs for Windows Containers are simply VMs that are based on Windows Server 2016, Windows 10, or later versions, both with Docker Engine set up.</span></span> <span data-ttu-id="92c86-215">대부분의 경우에서 Azure Vm에서 Windows Server 2016을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-215">In most cases, you will use Windows Server 2016 in the Azure VMs.</span></span>

<span data-ttu-id="92c86-216">Azure에서 현재 V 제공 **컨테이너와 Windows Server 2016**합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-216">Azure currently provides a VM named **Windows Server 2016 with Containers**.</span></span> <span data-ttu-id="92c86-217">Windows Server Core 또는 Windows Nano Server과 함께 새로운 Windows Server 컨테이너 기능을 사용 하려면이 VM을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-217">You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="92c86-218">컨테이너 OS 이미지 설치 되 고 VM은 Docker에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-218">Container OS images are installed, and then the VM is ready to use with Docker.</span></span>

### <a name="benefits"></a><span data-ttu-id="92c86-219">이점</span><span class="sxs-lookup"><span data-stu-id="92c86-219">Benefits</span></span>

<span data-ttu-id="92c86-220">Azure에 배포할 Windows 컨테이너를 온-프레미스 Windows Server 2016 Vm으로 배포할 수 있지만 Windows Server 컨테이너 Vm이 즉시 사용을 시작 하는 쉬운 방법이 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-220">Although Windows Containers can be deployed to on-premises Windows Server 2016 VMs, when you deploy to Azure, you get an easier way to get started, with ready-to-use Windows Server Container VMs.</span></span> <span data-ttu-id="92c86-221">테스터 및 Azure VM 크기 집합을 통해 자동 확장성에 액세스할 수 있는 공통 온라인 위치를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-221">You also get a common online location that’s accessible to testers, and automatic scalability through Azure VM scale sets.</span></span>

### <a name="next-steps"></a><span data-ttu-id="92c86-222">다음 단계</span><span class="sxs-lookup"><span data-stu-id="92c86-222">Next steps</span></span>

<span data-ttu-id="92c86-223">GitHub wiki에서이 콘텐츠를 더 자세히 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-223">Explore this content more in-depth on the GitHub wiki:</span></span>

<span data-ttu-id="92c86-224">[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="92c86-224">[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))</span></span>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a><span data-ttu-id="92c86-225">Azure 컨테이너 서비스에서 Kubernetes에 Windows 컨테이너 기반 응용 프로그램을 배포 하는 연습 4:</span><span class="sxs-lookup"><span data-stu-id="92c86-225">Walkthrough 4: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="92c86-226">기술 연습 가용성</span><span class="sxs-lookup"><span data-stu-id="92c86-226">Technical walkthrough availability</span></span>

<span data-ttu-id="92c86-227">전체 기술 eShopModernizing GitHub 리포지토리에 wiki에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-227">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="92c86-228">[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span><span class="sxs-lookup"><span data-stu-id="92c86-228">[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span></span>

### <a name="overview"></a><span data-ttu-id="92c86-229">개요</span><span class="sxs-lookup"><span data-stu-id="92c86-229">Overview</span></span>

<span data-ttu-id="92c86-230">Windows 컨테이너를 기반으로 하는 응용 프로그램 더욱 해소 IaaS Vm에서 다른 페이지로 이동 하는 플랫폼에서 사용 하 여 신속 하 게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-230">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="92c86-231">이 쉽게 높은 확장성을 달성 하는 데 필요한 및 더 잘 자동화 확장성, 고 크게 향상에 대 한 배포 및 버전 관리를 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-231">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="92c86-232">Orchestrator를 사용 하 여 이러한 목표를 달성할 수 [Kubernetes](https://kubernetes.io/)에서 사용할 수 있는, [Azure 컨테이너 서비스](https://azure.microsoft.com/services/container-service/)합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-232">You can achieve these goals by using the orchestrator [Kubernetes](https://kubernetes.io/), available in [Azure Container Services](https://azure.microsoft.com/services/container-service/).</span></span>

### <a name="goals"></a><span data-ttu-id="92c86-233">목표</span><span class="sxs-lookup"><span data-stu-id="92c86-233">Goals</span></span>

<span data-ttu-id="92c86-234">Windows 컨테이너 기반 응용 프로그램 Kubernetes 배포 하는 방법에 알아보려면이 연습의 목표는 (호출 또한 *K8s*) Azure 컨테이너 서비스의 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-234">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to Kubernetes (also called *K8s*) in Azure Container Service.</span></span> <span data-ttu-id="92c86-235">처음부터 Kubernetes에 배포은 두 단계로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-235">Deploying to Kubernetes from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="92c86-236">Azure 컨테이너 서비스를 Kubernetes 클러스터를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-236">Deploy a Kubernetes cluster to Azure Container Service.</span></span>

2.  <span data-ttu-id="92c86-237">Kubernetes 클러스터에 응용 프로그램 및 관련된 리소스를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-237">Deploy the application and related resources to the Kubernetes cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="92c86-238">시나리오</span><span class="sxs-lookup"><span data-stu-id="92c86-238">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a><span data-ttu-id="92c86-239">시나리오 a: Kubernetes 클러스터에 직접 배포 하는 개발 환경에서</span><span class="sxs-lookup"><span data-stu-id="92c86-239">Scenario A: Deploy directly to a Kubernetes cluster from a dev environment</span></span>

![개발 환경에서 Kubernetes 클러스터에 직접 배포 합니다.](./media/image5-7.png)

> <span data-ttu-id="92c86-241">**그림 5-7입니다.**</span><span class="sxs-lookup"><span data-stu-id="92c86-241">**Figure 5-7.**</span></span> <span data-ttu-id="92c86-242">개발 환경에서 Kubernetes 클러스터에 직접 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-242">Deploy directly to a Kubernetes cluster from a development environment</span></span>

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="92c86-243">Team Services에서 파이프라인 CI/CD에서 Kubernetes 클러스터 시나리오 b: 배포</span><span class="sxs-lookup"><span data-stu-id="92c86-243">Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

![Team Services에서 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포 합니다.](./media/image5-8.png)

> <span data-ttu-id="92c86-245">**그림 5-8입니다.**</span><span class="sxs-lookup"><span data-stu-id="92c86-245">**Figure 5-8.**</span></span> <span data-ttu-id="92c86-246">Team Services에서 CI/CD 파이프라인에서 Kubernetes 클러스터에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-246">Deploy to a Kubernetes cluster from CI/CD pipelines in Team Services</span></span>

### <a name="benefits"></a><span data-ttu-id="92c86-247">이점</span><span class="sxs-lookup"><span data-stu-id="92c86-247">Benefits</span></span>

<span data-ttu-id="92c86-248">Kubernetes에 있는 클러스터를 배포 하는 다음과 같은 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-248">There are many benefits to deploying to a cluster in Kubernetes.</span></span> <span data-ttu-id="92c86-249">가장 큰 장점은 적용 되는 즉시 환경 있는 있습니다 수 확장 (내부 확장성의 기존 노드에서에서)를 사용 하 고 클러스터 (에서 노드 또는 Vm의 수에 따라 컨테이너 인스턴스 수에 따라 응용 프로그램을 가져올 전역 확장성 클러스터의)입니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-249">The biggest benefit is that you get a production-ready environment in which you can scale-out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="92c86-250">Azure 컨테이너 서비스 인기 있는 오픈 소스 도구와 기술을 Azure에 맞게 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-250">Azure Container Service optimizes popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="92c86-251">사용자 컨테이너 및 응용 프로그램 구성에 대 한 이식성을 제공 하는 열린 솔루션 가져오기</span><span class="sxs-lookup"><span data-stu-id="92c86-251">You get an open solution that offers portability, both for your containers and for your application configuration.</span></span> <span data-ttu-id="92c86-252">크기, 호스트의 수를 선택 하 고 다른 모든 항목을 처리 하는 orchestrator 도구-컨테이너 서비스 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-252">You select the size, the number of hosts, and the orchestrator tools-Container Service handles everything else.</span></span>

<span data-ttu-id="92c86-253">Kubernetes와 개발자가 수에서 진행 상황 실제 및 가상 컴퓨터에 대 한 다음과 같은 기능 중 일부를 용이 하 게 하는 컨테이너 중심 인프라 계획:</span><span class="sxs-lookup"><span data-stu-id="92c86-253">With Kubernetes, developers can progress from thinking about physical and virtual machines, to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

-   <span data-ttu-id="92c86-254">여러 컨테이너를 기반으로 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="92c86-254">Applications based on multiple containers</span></span>

-   <span data-ttu-id="92c86-255">컨테이너 인스턴스를 복제 하는 가로 자동 크기 조정</span><span class="sxs-lookup"><span data-stu-id="92c86-255">Replicating container instances and horizontal autoscaling</span></span>

-   <span data-ttu-id="92c86-256">이름 지정 및 검색 (예를 들어 내부 DNS)</span><span class="sxs-lookup"><span data-stu-id="92c86-256">Naming and discovering (for example, internal DNS)</span></span>

-   <span data-ttu-id="92c86-257">로드 균형 조정</span><span class="sxs-lookup"><span data-stu-id="92c86-257">Balancing loads</span></span>

-   <span data-ttu-id="92c86-258">롤링 업데이트</span><span class="sxs-lookup"><span data-stu-id="92c86-258">Rolling updates</span></span>

-   <span data-ttu-id="92c86-259">암호를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-259">Distributing secrets</span></span>

-   <span data-ttu-id="92c86-260">응용 프로그램 상태 확인</span><span class="sxs-lookup"><span data-stu-id="92c86-260">Application health checks</span></span>

## <a name="next-steps"></a><span data-ttu-id="92c86-261">다음 단계</span><span class="sxs-lookup"><span data-stu-id="92c86-261">Next steps</span></span>

<span data-ttu-id="92c86-262">GitHub wiki에서이 콘텐츠를 더 자세하게 탐색할: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-드 ( Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span><span class="sxs-lookup"><span data-stu-id="92c86-262">Explore this content more in-depth on the GitHub wiki: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))</span></span>

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a><span data-ttu-id="92c86-263">Azure 서비스 패브릭에 Windows 컨테이너 기반 응용 프로그램을 배포 하는 연습 5:</span><span class="sxs-lookup"><span data-stu-id="92c86-263">Walkthrough 5: Deploy your Windows Containers-based apps to Azure Service Fabric</span></span>

### <a name="technical-walkthrough-availability"></a><span data-ttu-id="92c86-264">기술 연습 가용성</span><span class="sxs-lookup"><span data-stu-id="92c86-264">Technical walkthrough availability</span></span>

<span data-ttu-id="92c86-265">전체 기술 eShopModernizing GitHub 리포지토리에 wiki에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-265">The full technical walkthrough is available in the eShopModernizing GitHub repo wiki:</span></span>

<span data-ttu-id="92c86-266">[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="92c86-266">[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))</span></span>

### <a name="overview"></a><span data-ttu-id="92c86-267">개요</span><span class="sxs-lookup"><span data-stu-id="92c86-267">Overview</span></span>

<span data-ttu-id="92c86-268">Windows 컨테이너를 기반으로 하는 응용 프로그램 더욱 해소 IaaS Vm에서 다른 페이지로 이동 하는 플랫폼에서 사용 하 여 신속 하 게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-268">An application that's based on Windows Containers will quickly need to use platforms, moving even further away from IaaS VMs.</span></span> <span data-ttu-id="92c86-269">이 쉽게 높은 확장성을 달성 하는 데 필요한 및 더 잘 자동화 확장성, 고 크게 향상에 대 한 배포 및 버전 관리를 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-269">This is needed to easily achieve high scalability and better automated scalability, and for a significant improvement in automated deployments and versioning.</span></span> <span data-ttu-id="92c86-270">다른 공용 클라우드 또는 Azure 클라우드에서 사용할 수 있지만 가능 온-프레미스를 사용 하는 Azure 서비스 패브릭 orchestrator를 사용 하 여 이러한 목표를 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-270">You can achieve these goals by using the orchestrator Azure Service Fabric, which is available in the Azure cloud, but also available to use on-premises, or even in a different public cloud.</span></span>

### <a name="goals"></a><span data-ttu-id="92c86-271">목표</span><span class="sxs-lookup"><span data-stu-id="92c86-271">Goals</span></span>

<span data-ttu-id="92c86-272">이 연습의 목표는 azure에서 서비스 패브릭 클러스터에 Windows 컨테이너-> 기반 응용 프로그램을 배포 하는 방법에 알아보려면입니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-272">The goal of this walkthrough is to learn how to deploy a Windows Container–based application to a Service Fabric cluster in Azure.</span></span> <span data-ttu-id="92c86-273">서비스 패브릭을 처음부터 새로 배포은 두 단계로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-273">Deploying to Service Fabric from scratch is a two-step process:</span></span>

1.  <span data-ttu-id="92c86-274">Azure로 (또는 다른 환경에) 서비스 패브릭 클러스터를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-274">Deploy a Service Fabric cluster to Azure (or to a different environment).</span></span>

2.  <span data-ttu-id="92c86-275">서비스 패브릭 클러스터에 응용 프로그램 및 관련된 리소스를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-275">Deploy the application and related resources to the Service Fabric cluster.</span></span>

### <a name="scenarios"></a><span data-ttu-id="92c86-276">시나리오</span><span class="sxs-lookup"><span data-stu-id="92c86-276">Scenarios</span></span>

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a><span data-ttu-id="92c86-277">개발 환경에서 서비스 패브릭 클러스터에 직접 시나리오 a: 배포</span><span class="sxs-lookup"><span data-stu-id="92c86-277">Scenario A: Deploy directly to a Service Fabric cluster from a dev environment</span></span>

![개발 환경에서 서비스 패브릭 클러스터에 직접 배포 합니다.](./media/image5-9.png)

> <span data-ttu-id="92c86-279">**그림 5-9입니다.**</span><span class="sxs-lookup"><span data-stu-id="92c86-279">**Figure 5-9.**</span></span> <span data-ttu-id="92c86-280">개발 환경에서 서비스 패브릭 클러스터에 직접 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-280">Deploy directly to a Service Fabric cluster from a development environment</span></span>

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a><span data-ttu-id="92c86-281">Team Services에서 파이프라인 CI/CD에서 서비스 패브릭 클러스터를 시나리오 b: 배포</span><span class="sxs-lookup"><span data-stu-id="92c86-281">Scenario B: Deploy to a Service Fabric cluster from CI/CD pipelines in Team Services</span></span>

![Visual Studio Team Services에서 CI/CD 파이프라인에서 서비스 패브릭 클러스터를 배포](./media/image5-10.png)

> <span data-ttu-id="92c86-283">**그림 5-10입니다.**</span><span class="sxs-lookup"><span data-stu-id="92c86-283">**Figure 5-10.**</span></span> <span data-ttu-id="92c86-284">Visual Studio Team Services에서 CI/CD 파이프라인에서 서비스 패브릭 클러스터를 배포</span><span class="sxs-lookup"><span data-stu-id="92c86-284">Deploy to a Service Fabric cluster from CI/CD pipelines in Visual Studio Team Services</span></span>

## <a name="benefits"></a><span data-ttu-id="92c86-285">이점</span><span class="sxs-lookup"><span data-stu-id="92c86-285">Benefits</span></span>

<span data-ttu-id="92c86-286">서비스 패브릭 클러스터에 배포의 이점을 Kubernetes 사용의 이점와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-286">The benefits of deploying to a cluster in Service Fabric are similar to the benefits of using Kubernetes.</span></span> <span data-ttu-id="92c86-287">그러나 한 가지 차이점 서비스 패브릭 Windows 응용 프로그램의 Windows 컨테이너에 대 한 미리 보기 초기까지 2017의 대체 된 있는 Kubernetes에 비해 매우 성숙한 프로덕션 환경 된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-287">One difference, though, is that Service Fabric is a very mature production environment for Windows applications compared to Kubernetes, which was in preview for Windows Containers until early fall of 2017.</span></span> <span data-ttu-id="92c86-288">(Kubernetes는 Linux 용 더 성숙한 환경)입니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-288">(Kubernetes is a more mature environment for Linux).</span></span> 

<span data-ttu-id="92c86-289">Azure Service Fabric을 사용 하 여의 주요 장점은 적용 되는 즉시 환경 있는 있습니다 수 확장 (내부 확장성의 기존 노드에서에서)를 사용 하 고의 수에 따라 컨테이너 인스턴스 수에 따라 응용 프로그램을 가져올 노드 또는 클러스터 (클러스터의 전역 확장성)에서 Vm입니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-289">The main benefit of using Azure Service Fabric is that you get a production-ready environment in which you can scale-out the application based on the number of container instances you want to use (inner-scalability in the existing nodes), and based on the number of nodes or VMs in the cluster (global scalability of the cluster).</span></span>

<span data-ttu-id="92c86-290">Azure 서비스 패브릭 응용 프로그램 구성에 대 한 및 사용자 컨테이너에 대 한 이식성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-290">Azure Service Fabric offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="92c86-291">서비스 패브릭 클러스터에 Azure에서 또는 자체 데이터 센터에서 온-프레미스 설치를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-291">You can have a Service Fabric cluster in Azure, or install it on-premises in your own datacenter.</span></span> <span data-ttu-id="92c86-292">다른 클라우드에서 서비스 패브릭 클러스터 같은 설치도 [AWS Amazon](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/)합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-292">You can even install a Service Fabric cluster in a different cloud, like [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).</span></span>

<span data-ttu-id="92c86-293">서비스 패브릭 개발자 수에서 진행 상황 실제 및 가상 컴퓨터에 대 한 다음과 같은 기능 중 일부를 용이 하 게 하는 컨테이너 중심 인프라 계획:</span><span class="sxs-lookup"><span data-stu-id="92c86-293">With Service Fabric, developers can progress from thinking about physical and virtual machines to planning a container-centric infrastructure that facilitates the following capabilities, among others:</span></span>

-   <span data-ttu-id="92c86-294">여러 컨테이너를 기반으로 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-294">Applications based on multiple containers.</span></span>

-   <span data-ttu-id="92c86-295">가로 크기 자동 조정 및 컨테이너 인스턴스를 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-295">Replicating container instances and horizontal autoscaling.</span></span>

-   <span data-ttu-id="92c86-296">이름 지정 및 (예를 들어 내부 DNS)를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-296">Naming and discovering (for example, internal DNS).</span></span>

-   <span data-ttu-id="92c86-297">로드 균형 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-297">Balancing loads.</span></span>

-   <span data-ttu-id="92c86-298">롤링 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-298">Rolling updates.</span></span>

-   <span data-ttu-id="92c86-299">비밀을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-299">Distributing secrets.</span></span>

-   <span data-ttu-id="92c86-300">응용 프로그램 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-300">Application health checks.</span></span>

<span data-ttu-id="92c86-301">다음과 같은 기능 (다른 orchestrators 비교) 서비스 패브릭에서 배타적 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-301">The following capabilities are exclusive in Service Fabric (compared to other orchestrators):</span></span>

-   <span data-ttu-id="92c86-302">신뢰할 수 있는 서비스 응용 프로그램 모델을 통해 상태 저장 서비스 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-302">Stateful services capability, through the Reliable Services application model.</span></span>

-   <span data-ttu-id="92c86-303">Reliable Actors 응용 프로그램 모델을 통해 actor 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-303">Actors pattern, through the Reliable Actors application model.</span></span>

-   <span data-ttu-id="92c86-304">Windows 또는 Linux 컨테이너 외에도 본 운영 체제 미 설치 프로세스를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-304">Deploy bare-bone processes, in addition to Windows or Linux containers.</span></span>

-   <span data-ttu-id="92c86-305">고급 롤링 업데이트 및 상태 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-305">Advanced rolling updates and health checks.</span></span>

### <a name="next-steps"></a><span data-ttu-id="92c86-306">다음 단계</span><span class="sxs-lookup"><span data-stu-id="92c86-306">Next steps</span></span>

<span data-ttu-id="92c86-307">GitHub wiki에서이 콘텐츠를 더 자세히 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="92c86-307">Explore this content more in-depth on the GitHub wiki:</span></span>

<span data-ttu-id="92c86-308">[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))</span><span class="sxs-lookup"><span data-stu-id="92c86-308">[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="92c86-309">[이전](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[다음](conclusions.md)</span><span class="sxs-lookup"><span data-stu-id="92c86-309">[Previous](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Next](conclusions.md)</span></span>
