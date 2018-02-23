---
title: "일반 지침"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 일반 지침"
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
ms.openlocfilehash: fa58d1d81b2d1523baf123d4963db2ca00fee15d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="general-guidance"></a><span data-ttu-id="ca782-104">일반 지침</span><span class="sxs-lookup"><span data-stu-id="ca782-104">General guidance</span></span>

<span data-ttu-id="ca782-105">이 섹션에서는 .NET Framework 또는.NET Core를 선택하는 경우에 대해 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-105">This section provides a summary of when to choose .NET Core or .NET Framework.</span></span> <span data-ttu-id="ca782-106">이 선택에 대한 더 자세한 내용은 다음 섹션에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-106">We provide more details about these choices in the sections that follow.</span></span>

<span data-ttu-id="ca782-107">다음과 같은 상황에서는 컨테이너화된 Dockeer 서버 응용 프로그램에 대해 .NET Core를 Linux 또는 Windows Containers에 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-107">You should use .NET Core, with Linux or Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="ca782-108">플랫폼 간 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-108">You have cross-platform needs.</span></span> <span data-ttu-id="ca782-109">예를 들어 Linux와 Windows 컨테이너를 모두 사용하려 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-109">For example, you want to use both Linux and Windows Containers.</span></span>

-   <span data-ttu-id="ca782-110">응용 프로그램 아키텍처가 마이크로 서비스를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-110">Your application architecture is based on microservices.</span></span>

-   <span data-ttu-id="ca782-111">비용을 낮추기 위해 하드웨어당 밀도를 높이거나 또는 더 많은 컨테이너를 달성하려는 경우 컨테이너당 공간을 줄이고 더 빠르게 컨테이너를 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-111">You need to start containers fast and want a small footprint per container to achieve better density or more containers per hardware unit in order to lower your costs.</span></span>

<span data-ttu-id="ca782-112">즉 컨테이너화된 새 .NET 응용 프로그램을 만들 때는 .NET Core를 기본 선택으로 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-112">In short, when you create new containerized .NET applications, you should consider .NET Core as the default choice.</span></span> <span data-ttu-id="ca782-113">여러 장점이 있고 컨테이너 개념과 작업 스타일에 가장 잘 맞습니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-113">It has many benefits and fits best with the containers philosophy and style of working.</span></span>

<span data-ttu-id="ca782-114">.NET Core를 사용하면 같은 머신 안에서 응용 프로그램에 대해 .NET 버전을 함께 실행한다는 또 다른 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-114">An additional benefit of using .NET Core is that you can run side by side .NET versions for applications within the same machine.</span></span> <span data-ttu-id="ca782-115">이러한 장점은 컨테이너가 앱이 필요한 .NET 버전을 격리하기 때문에 컨테이너를 사용하지 않는 서버나 VM에서 특히 중요합니다</span><span class="sxs-lookup"><span data-stu-id="ca782-115">This benefit is more important for servers or VMs that do not use containers, because containers isolate the versions of .NET that the app needs.</span></span> <span data-ttu-id="ca782-116">(기본 OS와 호환되는 한).</span><span class="sxs-lookup"><span data-stu-id="ca782-116">(As long as they are compatible with the underlying OS.)</span></span>

<span data-ttu-id="ca782-117">다음과 같은 상황에서는 컨테이너화된 Dockeer 서버 응용 프로그램에 대해 .NET Framework를 Windows Containers에 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-117">You should use .NET Framework, with Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="ca782-118">응용 프로그램에서 현재 .NET Framework를 사용하며 Windows에 대한 의존도가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-118">Your application currently uses .NET Framework and has strong dependencies on Windows.</span></span>

-   <span data-ttu-id="ca782-119">.NET Core에서 지원되지 않는 Windows API를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-119">You need to use Windows APIs that are not supported by .NET Core.</span></span>

-   <span data-ttu-id="ca782-120">.NET Core에 사용할 수 없는 타사 .NET 라이브러리 또는 NuGet 패키지를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-120">You need to use third-party .NET libraries or NuGet packages that are not available for .NET Core.</span></span>

<span data-ttu-id="ca782-121">Docker에서 .NET Framework를 사용하면 배포 문제 최소화를 통해 배포 환경을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-121">Using .NET Framework on Docker can improve your deployment experiences by minimizing deployment issues.</span></span> <span data-ttu-id="ca782-122">이러한 [*"이동 편의" 시나리오*](https://aka.ms/liftandshiftwithcontainersebook)는 ASP.NET WebForms, MVC 웹앱 또는 WCF(Windows Communication Foundation) 서비스 같은 기존 .NET Framework로 개발된 레거시 응용 프로그램을 컨테이너화하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="ca782-122">This [*"lift and shift" scenario*](https://aka.ms/liftandshiftwithcontainersebook) is important for containerizing legacy applications that were originally developed with the traditional .NET Framework, like ASP.NET WebForms, MVC web apps or WCF (Windows Communication Foundation) services.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ca782-123">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="ca782-123">Additional resources</span></span>

-   <span data-ttu-id="ca782-124">**전자책: Azure 및 Windows Containers를 통한 기존 .NET Framework 응용 프로그램 현대화**
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span><span class="sxs-lookup"><span data-stu-id="ca782-124">**e-book: Modernize existing .NET Framework applications with Azure and Windows Containers**
[*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span></span>

-   <span data-ttu-id="ca782-125">**앱 샘플: Windows Containers를 통한 레거시 ASP.NET 웹 앱 현대화**
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span><span class="sxs-lookup"><span data-stu-id="ca782-125">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers**
[*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="ca782-126">[이전] (index.md) [다음] (net-core-container-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="ca782-126">[Previous] (index.md) [Next] (net-core-container-scenarios.md)</span></span>
