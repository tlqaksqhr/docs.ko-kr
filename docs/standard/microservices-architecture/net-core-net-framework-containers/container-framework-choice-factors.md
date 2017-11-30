---
title: "의사 결정 테이블입니다. Docker에 사용할.NET 프레임 워크"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 의사 결정 테이블, Docker에 사용할.NET 프레임 워크"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 4889662c4d887bebd320389e3ced6aae1c93133b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a><span data-ttu-id="a987a-105">의사 결정 테이블: Docker에 사용할.NET 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="a987a-105">Decision table: .NET frameworks to use for Docker</span></span>

<span data-ttu-id="a987a-106">다음은.NET Framework 또는.NET Core 및 Windows 또는 Linux 컨테이너를 사용할지 여부를 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-106">The following summarizes whether to use .NET Framework or .NET Core, and Windows or Linux containers.</span></span> <span data-ttu-id="a987a-107">Linux 컨테이너에 대 한 사항에 유의 하 고 (Vm 또는 서버)에 Linux 기반 Docker 호스트가 필요 하면 Docker 호스트 (Vm 또는 서버)를 기반으로 Windows 컨테이너에 대 한 Windows 서버가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-107">Remember that for Linux containers, you need Linux-based Docker hosts (VMs or servers) and that for Windows Containers you need Windows Server based Docker hosts (VMs or servers).</span></span>

<span data-ttu-id="a987a-108">응용 프로그램의 결정에 영향을 주는 몇 가지 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-108">There are several features of your application that affect your decision.</span></span> <span data-ttu-id="a987a-109">결정을 내릴 때 중요도의 이러한 기능을 저울질 해봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-109">You should weigh the importance of these features when making your decision.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a987a-110">개발 컴퓨터에는 하나의 Docker 호스트, Linux 또는 Windows 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-110">Your development machines will run one Docker host, either Linux or Windows.</span></span> <span data-ttu-id="a987a-111">실행 하 고 하나의 솔루션에 함께 테스트 관련된 microservices 모두 동일한 컨테이너 플랫폼에서 실행 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-111">Related microservices that you want to run and test together in one solution will all need to run on the same container platform.</span></span>

* <span data-ttu-id="a987a-112">응용 프로그램 아키텍처 선택은 **컨테이너에 Microservices**합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-112">Your application architecture choice is **Microservices on containers**.</span></span>
    - <span data-ttu-id="a987a-113">.NET 구현 선택 이어야 *.NET Core*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-113">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="a987a-114">컨테이너 플랫폼 선택 될 수 있습니다 *Linux 컨테이너* 또는 *Windows 컨테이너*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-114">Your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
* <span data-ttu-id="a987a-115">응용 프로그램 아키텍처 선택은는 **모놀리식 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-115">Your application architecture choice is a **Monolithic application**.</span></span>
    - <span data-ttu-id="a987a-116">.NET 구현 선택 될 수 있습니다 *.NET Core* 또는 *.NET Framework*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-116">Your .NET implementation choice can be either *.NET Core* or *.NET Framework*.</span></span>
    - <span data-ttu-id="a987a-117">선택한 경우 *.NET Core*, 컨테이너 플랫폼 선택 될 수 있습니다 *Linux 컨테이너* 또는 *Windows 컨테이너*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-117">If you have chosen *.NET Core*, your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
    - <span data-ttu-id="a987a-118">선택한 경우 *.NET Framework*, 컨테이너 플랫폼 선택 해야 *Windows 컨테이너*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-118">If you have chosen *.NET Framework*, your container platform choice must be *Windows containers*.</span></span>
* <span data-ttu-id="a987a-119">응용 프로그램은 한 **새 컨테이너 기반 개발 ("필드 녹색")**합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-119">Your application is a  **New container-based development ("green-field")**.</span></span>
    - <span data-ttu-id="a987a-120">.NET 구현 선택 이어야 *.NET Core*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-120">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="a987a-121">컨테이너 플랫폼 선택 될 수 있습니다 *Linux 컨테이너* 또는 *Windows 컨테이너*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-121">Your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
* <span data-ttu-id="a987a-122">응용 프로그램은 한 **Windows Server 컨테이너를 마이그레이션하는 레거시 응용 프로그램 ("필드 brown")**</span><span class="sxs-lookup"><span data-stu-id="a987a-122">Your application is a **Windows Server legacy app ("brown-field") migration to containers**</span></span>
    - <span data-ttu-id="a987a-123">.NET 구현 선택은 *.NET Framework* 프레임 워크 종속성에 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-123">Your .NET implementation choice is *.NET Framework* based on framework dependency.</span></span>
    - <span data-ttu-id="a987a-124">컨테이너 플랫폼 선택 해야 *Windows 컨테이너* .NET Framework 종속성으로 인해 합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-124">Your container platform choice must be *Windows containers* because of the .NET Framework dependency.</span></span>
* <span data-ttu-id="a987a-125">응용 프로그램의 디자인 목표는 **클래스에서 최상의 성능 및 확장성**합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-125">Your application's design goal is **Best-in-class performance and scalability**.</span></span>
    - <span data-ttu-id="a987a-126">.NET 구현 선택 이어야 *.NET Core*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-126">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="a987a-127">컨테이너 플랫폼 선택 될 수 있습니다 *Linux 컨테이너* 또는 *Windows 컨테이너*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-127">Your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
* <span data-ttu-id="a987a-128">사용 하 여 응용 프로그램을 빌드한 **ASP.NET Core**합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-128">You built your application using **ASP.NET Core**.</span></span>
    - <span data-ttu-id="a987a-129">.NET 구현 선택 이어야 *.NET Core*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-129">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="a987a-130">사용할 수는 *.NET Framework* 구현에서 다른 프레임 워크 종속성이 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="a987a-130">You can use the *.NET Framework* implementation, if you have other framework dependencies.</span></span>
    - <span data-ttu-id="a987a-131">선택한 경우 *.NET Core*, 컨테이너 플랫폼 선택 될 수 있습니다 *Linux 컨테이너* 또는 *Windows 컨테이너*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-131">If you have chosen *.NET Core*, your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
    - <span data-ttu-id="a987a-132">선택한 경우 *.NET Framework*, 컨테이너 플랫폼 선택 해야 *Windows 컨테이너*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-132">If you have chosen *.NET Framework*, your container platform choice must be *Windows containers*.</span></span>
* <span data-ttu-id="a987a-133">사용 하 여 응용 프로그램을 빌드한 **ASP.NET 4 (MVC 5, Web API 2 및 Web Forms)**합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-133">You built your application using **ASP.NET 4 (MVC 5, Web API 2, and Web Forms)**.</span></span>
    - <span data-ttu-id="a987a-134">.NET 구현 선택은 *.NET Framework* 프레임 워크 종속성에 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-134">Your .NET implementation choice is *.NET Framework* based on framework dependency.</span></span>
    - <span data-ttu-id="a987a-135">컨테이너 플랫폼 선택 해야 *Windows 컨테이너* .NET Framework 종속성으로 인해 합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-135">Your container platform choice must be *Windows containers* because of the .NET Framework dependency.</span></span>
* <span data-ttu-id="a987a-136">응용 프로그램 사용 **SignalR 서비스**합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-136">Your application uses **SignalR services**.</span></span>
    - <span data-ttu-id="a987a-137">.NET 구현을 선택할 수 있습니다. *.NET Framework*, 또는 *.NET Core 2.1 (릴리스된 경우) 또는 이후*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-137">Your .NET implementation choice can be *.NET Framework*, or *.NET Core 2.1 (when released) or later*.</span></span>
    - <span data-ttu-id="a987a-138">컨테이너 플랫폼 선택 해야 *Windows 컨테이너* .NET Framework의 SignalR 구현을 선택 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="a987a-138">Your container platform choice must be *Windows containers* if you chose the SignalR implementation in .NET Framework.</span></span>
    - <span data-ttu-id="a987a-139">컨테이너 플랫폼 선택 (릴리스된 경우) 이상 버전에서.NET Core 2.1 SignalR 구현을 선택 하는 경우 Linux 컨테이너 또는 Windows 컨테이너 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-139">Your container platform choice can be either Linux containers or Windows containers if you chose the SignalR implementation in .NET Core 2.1 or later (when released).</span></span>  
    - <span data-ttu-id="a987a-140">때 **SignalR 서비스** 에서 실행 *.NET Core*를 사용할 수 있습니다 *Linux 컨테이너 또는 Windows 컨테이너*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-140">When **SignalR services** run on *.NET Core*, you can use *Linux containers or Windows Containers*.</span></span>
* <span data-ttu-id="a987a-141">응용 프로그램 사용 **WCF, WF, 및 기타 레거시 프레임 워크**합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-141">Your application uses **WCF, WF, and other legacy frameworks**.</span></span>
    - <span data-ttu-id="a987a-142">.NET 구현 선택은 *.NET Framework*, 또는 *(이후 버전에 대 한 로드맵)에서.NET Core*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-142">Your .NET implementation choice is *.NET Framework*, or *.NET Core (in the roadmap for a future release)*.</span></span>
    - <span data-ttu-id="a987a-143">컨테이너 플랫폼 선택 해야 *Windows 컨테이너* .NET Framework 종속성으로 인해 합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-143">Your container platform choice must be *Windows containers* because of the .NET Framework dependency.</span></span>
* <span data-ttu-id="a987a-144">응용 프로그램에 **소비의 Azure 서비스**합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-144">Your application involves **Consumption of Azure services**.</span></span>
    - <span data-ttu-id="a987a-145">.NET 구현 선택은 *.NET Framework*, 또는 *.NET Core (최종적 모든 Azure 서비스 클라이언트 Sdk를 제공할.NET Core)*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-145">Your .NET implementation choice is *.NET Framework*, or *.NET Core (eventually all Azure services will provide client SDKs for .NET Core)*.</span></span>
    - <span data-ttu-id="a987a-146">컨테이너 플랫폼 선택 해야 *Windows 컨테이너* .NET Framework 클라이언트 Api를 사용 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="a987a-146">Your container platform choice must be *Windows containers* if you use .NET Framework client APIs.</span></span>
    - <span data-ttu-id="a987a-147">클라이언트에 사용할 수 있는 Api를 사용 하는 경우 *.NET Core*, 또한 선택할 수 있는 *Linux 컨테이너와 Windows 컨테이너*합니다.</span><span class="sxs-lookup"><span data-stu-id="a987a-147">If you use client APIs available for *.NET Core*, you can also choose between *Linux containers and Windows containers*.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="a987a-148">[이전] (net-프레임 워크-컨테이너-scenarios.md) [다음] (net-컨테이너-os-targets.md)</span><span class="sxs-lookup"><span data-stu-id="a987a-148">[Previous] (net-framework-container-scenarios.md) [Next] (net-container-os-targets.md)</span></span>
