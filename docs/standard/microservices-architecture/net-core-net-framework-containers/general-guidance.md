---
title: "일반적인 지침"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 일반적인 지침"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 22dea926e77079e4f543934613ced13a28b2dae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="general-guidance"></a><span data-ttu-id="c75bb-104">일반적인 지침</span><span class="sxs-lookup"><span data-stu-id="c75bb-104">General guidance</span></span>

<span data-ttu-id="c75bb-105">이 섹션에서는.NET Framework 또는.NET Core를 선택 하는 경우에 대 한 요약을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75bb-105">This section provides a summary of when to choose .NET Core or .NET Framework.</span></span> <span data-ttu-id="c75bb-106">에서는 다음 섹션에서는 이러한 선택 항목에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75bb-106">We provide more details about these choices in the sections that follow.</span></span>

<span data-ttu-id="c75bb-107">컨테이너 화 된 Docker 서버 응용 프로그램에 대 한 Linux 또는 Windows 컨테이너와 함께.NET Core를 사용 해야 경우:</span><span class="sxs-lookup"><span data-stu-id="c75bb-107">You should use .NET Core, with Linux or Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="c75bb-108">플랫폼 간 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75bb-108">You have cross-platform needs.</span></span> <span data-ttu-id="c75bb-109">예를 들어 Linux와 Windows 컨테이너를 사용 하려면.</span><span class="sxs-lookup"><span data-stu-id="c75bb-109">For example, you want to use both Linux and Windows Containers.</span></span>

-   <span data-ttu-id="c75bb-110">응용 프로그램 아키텍처 microservices를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75bb-110">Your application architecture is based on microservices.</span></span>

-   <span data-ttu-id="c75bb-111">비용을 절감 하기 위해 향상 된 밀도 달성 하기 위해 컨테이너 또는 하드웨어 단위당 컨테이너가 더 이상 당 적은 공간만 사용 하 고 컨테이너 빠른 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75bb-111">You need to start containers fast and want a small footprint per container to achieve better density or more containers per hardware unit in order to lower your costs.</span></span>

<span data-ttu-id="c75bb-112">즉, 새 컨테이너 화 된.NET 응용 프로그램을 만들 때.NET Core 기본 선택으로 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75bb-112">In short, when you create new containerized .NET applications, you should consider .NET Core as the default choice.</span></span> <span data-ttu-id="c75bb-113">다양 한 이점을 있으며 컨테이너 대 한 개념 및 작업 스타일에 가장 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75bb-113">It has many benefits and fits best with the containers philosophy and style of working.</span></span>

<span data-ttu-id="c75bb-114">.NET Core를 사용 하 여 또 다른 이점은 동일한 컴퓨터에서 응용 프로그램에 대 한 병렬.NET 버전을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75bb-114">An additional benefit of using .NET Core is that you can run side by side .NET versions for applications within the same machine.</span></span> <span data-ttu-id="c75bb-115">이 기능은 컨테이너 응용 프로그램에 필요한.NET 버전을 격리 하기 때문에 서버 또는 컨테이너를 사용 하지 않는 Vm에 대 한 더 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75bb-115">This benefit is more important for servers or VMs that do not use containers, because containers isolate the versions of .NET that the app needs.</span></span> <span data-ttu-id="c75bb-116">(으로 기본 운영 체제와 호환 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="c75bb-116">(As long as they are compatible with the underlying OS.)</span></span>

<span data-ttu-id="c75bb-117">Windows 컨테이너와 컨테이너 화 된 Docker 서버 응용 프로그램에 대 한.NET Framework를 사용 해야 경우:</span><span class="sxs-lookup"><span data-stu-id="c75bb-117">You should use .NET Framework, with Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="c75bb-118">응용 프로그램에 현재.NET Framework를 사용 하 여와 Windows에 강력한 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75bb-118">Your application currently uses .NET Framework and has strong dependencies on Windows.</span></span>

-   <span data-ttu-id="c75bb-119">.NET Core에서 지원 되지 않는 Windows Api를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75bb-119">You need to use Windows APIs that are not supported by .NET Core.</span></span>

-   <span data-ttu-id="c75bb-120">제 3 자.NET 라이브러리 또는.NET Core를 사용할 수 없는 NuGet 패키지를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75bb-120">You need to use third-party .NET libraries or NuGet packages that are not available for .NET Core.</span></span>

<span data-ttu-id="c75bb-121">Docker에서.NET Framework를 사용 하 여 배포 문제를 최소화 하 여 배포 환경을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75bb-121">Using .NET Framework on Docker can improve your deployment experiences by minimizing deployment issues.</span></span> <span data-ttu-id="c75bb-122">이 [ *"리프트 및 이동" 시나리오* ](https://aka.ms/liftandshiftwithcontainersebook) containerizing ASP.NET WebForms, MVC 웹 응용 프로그램 또는 WCF (처럼 기존.NET Framework와 함께 원래 개발 된 레거시 응용 프로그램에 대 한 중요 Windows Communication Foundation) 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="c75bb-122">This [*"lift and shift" scenario*](https://aka.ms/liftandshiftwithcontainersebook) is important for containerizing legacy applications that were originally developed with the traditional .NET Framework, like ASP.NET WebForms, MVC web apps or WCF (Windows Communication Foundation) services.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="c75bb-123">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="c75bb-123">Additional resources</span></span>

-   <span data-ttu-id="c75bb-124">**전자책: Azure와 Windows 컨테이너와 기존.NET Framework 응용 프로그램을 최신식**
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span><span class="sxs-lookup"><span data-stu-id="c75bb-124">**e-book: Modernize existing .NET Framework applications with Azure and Windows Containers**
[*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span></span>

-   <span data-ttu-id="c75bb-125">**앱 샘플: Windows 컨테이너를 사용 하 여 기존 ASP.NET 웹 응용 프로그램의 현대화**
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span><span class="sxs-lookup"><span data-stu-id="c75bb-125">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers**
[*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="c75bb-126">[이전] [다음] (net-코어-컨테이너-scenarios.md) (index.md)</span><span class="sxs-lookup"><span data-stu-id="c75bb-126">[Previous] (index.md) [Next] (net-core-container-scenarios.md)</span></span>
