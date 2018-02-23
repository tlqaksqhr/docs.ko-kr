---
title: "의사 결정 테이블. Docker에 사용할 .NET Framework"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 의사 결정 테이블, Docker에 사용할 .NET Framework"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 40e6a14e7e3515194185e1f4558c91ac29429108
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a><span data-ttu-id="eeb49-105">의사 결정 테이블: Docker에 사용할 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="eeb49-105">Decision table: .NET frameworks to use for Docker</span></span>

<span data-ttu-id="eeb49-106">다음은 .NET Framework 또는 .NET Core 중 무엇을, 그리고 Windows 또는 Linux 컨테이너 중 무엇을 사용할지 요약하는 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-106">The following summarizes whether to use .NET Framework or .NET Core, and Windows or Linux containers.</span></span> <span data-ttu-id="eeb49-107">Linux 컨테이너의 경우 Linux 기반 Docker 호스트(VM 또는 서버)가 필요하고, Windows 컨테이너의 경우 Windows Server 기반 Docker 호스트(VM 또는 서버)가 필요하다는 사실을 기억해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-107">Remember that for Linux containers, you need Linux-based Docker hosts (VMs or servers) and that for Windows Containers you need Windows Server based Docker hosts (VMs or servers).</span></span>

<span data-ttu-id="eeb49-108">의사 결정에 영향을 주는 몇 가지 응용 프로그램 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-108">There are several features of your application that affect your decision.</span></span> <span data-ttu-id="eeb49-109">의사를 결정할 때 이러한 기능의 중요도에 가중치를 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-109">You should weigh the importance of these features when making your decision.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eeb49-110">개발 컴퓨터에서 Docker 호스트(Linux 또는 Windows)를 하나 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-110">Your development machines will run one Docker host, either Linux or Windows.</span></span> <span data-ttu-id="eeb49-111">한 솔루션에서 함께 실행하고 테스트할 관련 마이크로 서비스가 전부 동일한 컨테이너 플랫폼에서 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-111">Related microservices that you want to run and test together in one solution will all need to run on the same container platform.</span></span>

* <span data-ttu-id="eeb49-112">응용 프로그램 아키텍처로 **컨테이너의 마이크로 서비스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-112">Your application architecture choice is **Microservices on containers**.</span></span>
    - <span data-ttu-id="eeb49-113">.NET 구현으로 *.NET Core*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-113">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="eeb49-114">컨테이너 플랫폼으로 *Linux 컨테이너*를 선택해도 되고 *Windows 컨테이너*를 선택해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-114">Your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
* <span data-ttu-id="eeb49-115">응용 프로그램 아키텍처로 **모놀리식 응용 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-115">Your application architecture choice is a **Monolithic application**.</span></span>
    - <span data-ttu-id="eeb49-116">.NET 구현으로 *.NET Core*를 선택해도 되고 *.NET Framework*를 선택해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-116">Your .NET implementation choice can be either *.NET Core* or *.NET Framework*.</span></span>
    - <span data-ttu-id="eeb49-117">*.NET Core*를 선택한 경우 컨테이너 플랫폼으로 *Linux 컨테이너*를 선택해도 되고 *Windows 컨테이너*를 선택해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-117">If you have chosen *.NET Core*, your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
    - <span data-ttu-id="eeb49-118">*.NET Framework*를 선택한 경우 컨테이너 플랫폼으로 *Windows 컨테이너*를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-118">If you have chosen *.NET Framework*, your container platform choice must be *Windows containers*.</span></span>
* <span data-ttu-id="eeb49-119">응용 프로그램은 **새 컨테이너 기반 개발("그린 필드")**입니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-119">Your application is a  **New container-based development ("green-field")**.</span></span>
    - <span data-ttu-id="eeb49-120">.NET 구현으로 *.NET Core*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-120">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="eeb49-121">컨테이너 플랫폼으로 *Linux 컨테이너*를 선택해도 되고 *Windows 컨테이너*를 선택해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-121">Your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
* <span data-ttu-id="eeb49-122">응용 프로그램은 **컨테이너로의 Windows Server 레거시 앱("브라운 필드") 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="eeb49-122">Your application is a **Windows Server legacy app ("brown-field") migration to containers**</span></span>
    - <span data-ttu-id="eeb49-123">.NET 구현으로 프레임워크 종속성 기반의 *.NET Framework*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-123">Your .NET implementation choice is *.NET Framework* based on framework dependency.</span></span>
    - <span data-ttu-id="eeb49-124">.NET Framework 종속성 때문에 컨테이너 플랫폼으로 *Windows 컨테이너*를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-124">Your container platform choice must be *Windows containers* because of the .NET Framework dependency.</span></span>
* <span data-ttu-id="eeb49-125">응용 프로그램의 디자인 목표는 **동급 최고의 성능 및 확장성**입니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-125">Your application's design goal is **Best-in-class performance and scalability**.</span></span>
    - <span data-ttu-id="eeb49-126">.NET 구현으로 *.NET Core*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-126">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="eeb49-127">컨테이너 플랫폼으로 *Linux 컨테이너*를 선택해도 되고 *Windows 컨테이너*를 선택해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-127">Your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
* <span data-ttu-id="eeb49-128">**ASP.NET Core**를 사용하여 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-128">You built your application using **ASP.NET Core**.</span></span>
    - <span data-ttu-id="eeb49-129">.NET 구현으로 *.NET Core*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-129">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="eeb49-130">다른 프레임워크 종속성이 있는 경우 *.NET Framework* 구현을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-130">You can use the *.NET Framework* implementation, if you have other framework dependencies.</span></span>
    - <span data-ttu-id="eeb49-131">*.NET Core*를 선택한 경우 컨테이너 플랫폼으로 *Linux 컨테이너*를 선택해도 되고 *Windows 컨테이너*를 선택해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-131">If you have chosen *.NET Core*, your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
    - <span data-ttu-id="eeb49-132">*.NET Framework*를 선택한 경우 컨테이너 플랫폼으로 *Windows 컨테이너*를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-132">If you have chosen *.NET Framework*, your container platform choice must be *Windows containers*.</span></span>
* <span data-ttu-id="eeb49-133">**ASP.NET 4(MVC 5, Web API 2 및 Web Forms)**를 사용하여 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-133">You built your application using **ASP.NET 4 (MVC 5, Web API 2, and Web Forms)**.</span></span>
    - <span data-ttu-id="eeb49-134">.NET 구현으로 프레임워크 종속성 기반의 *.NET Framework*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-134">Your .NET implementation choice is *.NET Framework* based on framework dependency.</span></span>
    - <span data-ttu-id="eeb49-135">.NET Framework 종속성 때문에 컨테이너 플랫폼으로 *Windows 컨테이너*를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-135">Your container platform choice must be *Windows containers* because of the .NET Framework dependency.</span></span>
* <span data-ttu-id="eeb49-136">응용 프로그램에서는 **SignalR 서비스**를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-136">Your application uses **SignalR services**.</span></span>
    - <span data-ttu-id="eeb49-137">.NET 구현으로 *.NET Framework*를 선택해도 되고 *.NET Core 2.1 이상(릴리스된 경우)*을 선택해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-137">Your .NET implementation choice can be *.NET Framework*, or *.NET Core 2.1 (when released) or later*.</span></span>
    - <span data-ttu-id="eeb49-138">.NET Framework에서 SignalR 구현을 선택한 경우 컨테이너 플랫폼으로 *Windows 컨테이너*를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-138">Your container platform choice must be *Windows containers* if you chose the SignalR implementation in .NET Framework.</span></span>
    - <span data-ttu-id="eeb49-139">.NET Core 2.1 이상(릴리스된 경우)에서 SignalR 구현을 선택한 경우 컨테이너 플랫폼으로 Linux 컨테이너를 선택해도 되고 Windows 컨테이너를 선택해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-139">Your container platform choice can be either Linux containers or Windows containers if you chose the SignalR implementation in .NET Core 2.1 or later (when released).</span></span>  
    - <span data-ttu-id="eeb49-140">**SignalR 서비스**가 *.NET Core*에서 실행되면 *Linux 컨테이너 또는 Windows 컨테이너*를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-140">When **SignalR services** run on *.NET Core*, you can use *Linux containers or Windows Containers*.</span></span>
* <span data-ttu-id="eeb49-141">응용 프로그램에서는 **WCF, WF 및 기타 레거시 프레임워크**를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-141">Your application uses **WCF, WF, and other legacy frameworks**.</span></span>
    - <span data-ttu-id="eeb49-142">.NET 구현으로 *.NET Framework* 또는 *.NET Core(향후 릴리스에 대한 로드맵에 있는)*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-142">Your .NET implementation choice is *.NET Framework*, or *.NET Core (in the roadmap for a future release)*.</span></span>
    - <span data-ttu-id="eeb49-143">.NET Framework 종속성 때문에 컨테이너 플랫폼으로 *Windows 컨테이너*를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-143">Your container platform choice must be *Windows containers* because of the .NET Framework dependency.</span></span>
* <span data-ttu-id="eeb49-144">응용 프로그램에서는 **Azure 서비스를 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-144">Your application involves **Consumption of Azure services**.</span></span>
    - <span data-ttu-id="eeb49-145">.NET 구현으로 *.NET Framework* 또는 *.NET Core(궁극적으로 모든 Azure 서비스 클라이언트에서 SDKs for .NET Core 제공)*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-145">Your .NET implementation choice is *.NET Framework*, or *.NET Core (eventually all Azure services will provide client SDKs for .NET Core)*.</span></span>
    - <span data-ttu-id="eeb49-146">.NET Framework 클라이언트 API를 사용하는 경우 컨테이너 플랫폼으로 *Windows 컨테이너*를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-146">Your container platform choice must be *Windows containers* if you use .NET Framework client APIs.</span></span>
    - <span data-ttu-id="eeb49-147">*.NET Core*에 제공되는 클라이언트 API를 사용하는 경우 *Linux 컨테이너 및 Windows 컨테이너* 중에 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeb49-147">If you use client APIs available for *.NET Core*, you can also choose between *Linux containers and Windows containers*.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="eeb49-148">[이전] (net-framework-container-scenarios.md) [다음] (net-container-os-targets.md)</span><span class="sxs-lookup"><span data-stu-id="eeb49-148">[Previous] (net-framework-container-scenarios.md) [Next] (net-container-os-targets.md)</span></span>
