---
title: "Docker 컨테이너에 대 한.NET Framework를 선택 하는 경우"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Docker 컨테이너에 대 한.NET Framework를 선택 하는 경우"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1bf1f055f040e7f3dc575b7a04140ebf0c599f98
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a><span data-ttu-id="daa5e-104">Docker 컨테이너에 대 한.NET Framework를 선택 하는 경우</span><span class="sxs-lookup"><span data-stu-id="daa5e-104">When to choose .NET Framework for Docker containers</span></span>

<span data-ttu-id="daa5e-105">.NET Core에서는 새 응용 프로그램 및 응용 프로그램 패턴에 대 한 중요 한 혜택을 제공 하지만 대부분의 기존 시나리오에 적합 하려면.NET Framework 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-105">While .NET Core offers significant benefits for new applications and application patterns, .NET Framework will continue to be a good choice for many existing scenarios.</span></span>

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a><span data-ttu-id="daa5e-106">Windows Server 컨테이너에 직접 기존 응용 프로그램 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="daa5e-106">Migrating existing applications directly to a Windows Server container</span></span>

<span data-ttu-id="daa5e-107">Microservices 만들지 않는 경우에 배포를 단순화 하기 위해 Docker 컨테이너를 사용 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-107">You might want to use Docker containers just to simplify deployment, even if you are not creating microservices.</span></span> <span data-ttu-id="daa5e-108">예를 들어 아마도 향상 시키려면 Docker 통한 DevOps 워크플로-컨테이너 더 격리 된 테스트 환경을 제공할 수와 프로덕션 환경으로 이동 하면 누락 된 종속성에의 한 배포 문제를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-108">For example, perhaps you want to improve your DevOps workflow with Docker—containers can give you better isolated test environments and can also eliminate deployment issues caused by missing dependencies when you move to a production environment.</span></span> <span data-ttu-id="daa5e-109">이와 같은 경우에는 모놀리식 응용 프로그램을 배포 하는 경우에 의미가 현재.NET Framework 응용 프로그램에 대 한 Docker 및 Windows 컨테이너를 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-109">In cases like these, even if you are deploying a monolithic application, it makes sense to use Docker and Windows Containers for your current .NET Framework applications.</span></span>

<span data-ttu-id="daa5e-110">이 시나리오에 대 한 대부분의 경우 않아도 됩니다.NET Core; 하 여 기존 응용 프로그램 마이그레이션 기존.NET Framework를 포함 하는 Docker 컨테이너를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-110">In most cases for this scenario, you will not need to migrate your existing applications to .NET Core; you can use Docker containers that include the traditional .NET Framework.</span></span> <span data-ttu-id="daa5e-111">그러나 ASP.NET Core에서 새 서비스를 작성 하는 등 기존 응용 프로그램을 확장 하는 대로.NET Core를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-111">However, a recommended approach is to use .NET Core as you extend an existing application, such as writing a new service in ASP.NET Core.</span></span>

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a><span data-ttu-id="daa5e-112">.NET Core에 대 한 제 3 자.NET 라이브러리 또는 사용할 수 없는 NuGet 패키지를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="daa5e-112">Using third-party .NET libraries or NuGet packages not available for .NET Core</span></span>

<span data-ttu-id="daa5e-113">타사 라이브러리의 디렉터리가 신속 하 게는 [.NET 표준](https://docs.microsoft.com/dotnet/standard/net-standard), 하면.NET Core를 포함 하 여 모든.NET 버전에서 공유 하는 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-113">Third-party libraries are quickly embracing the [.NET Standard](https://docs.microsoft.com/dotnet/standard/net-standard), which enables code sharing across all .NET flavors, including .NET Core.</span></span> <span data-ttu-id="daa5e-114">다양 한 프레임 워크에서 호환성 크게 증가 되었습니다 API 화면.NET 표준 라이브러리 2.0 이상 및.NET Core 2.0에서 응용 프로그램 수를 직접 참조할 수도 기존.NET Framework 라이브러리 (참조 [호환 가능 shim](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work)).</span><span class="sxs-lookup"><span data-stu-id="daa5e-114">With the .NET Standard Library 2.0 and beyond the API surface compatibility across different frameworks has become significantly larger and in .NET Core 2.0 applications can also directly reference existing .NET Framework libraries (see [compat shim](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work)).</span></span>

<span data-ttu-id="daa5e-115">그러나 표준.NET 2.0 및.NET Core 2.0 이후 해당 뛰어난 진행, 된 경우에 있을 수 있습니다 특정 NuGet 패키지 해야 Windows를 실행 하 고.NET Core를 지원 하지 않을 수 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="daa5e-115">However, even with that exceptional progression since .NET Standard 2.0 and .NET Core 2.0, there might be cases where certain NuGet packages need Windows to run and might not support .NET Core.</span></span> <span data-ttu-id="daa5e-116">이러한 패키지를 응용 프로그램에 대 한 중요 한 경우 Windows 컨테이너에서.NET Framework를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-116">If those packages are critical for your application, then you will need to use .NET Framework on Windows Containers.</span></span>

## <a name="usingnet-technologies-not-available-for-net-core"></a><span data-ttu-id="daa5e-117">.NET Core에 사용할 수 없는 Using.NET 기술</span><span class="sxs-lookup"><span data-stu-id="daa5e-117">Using.NET technologies not available for .NET Core</span></span> 

<span data-ttu-id="daa5e-118">일부.NET Framework 기술을.NET Core (버전 2.0 부터는)의 현재 버전에서 사용할 수 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-118">Some .NET Framework technologies are not available in the current version of .NET Core (version 2.0 as of this writing).</span></span> <span data-ttu-id="daa5e-119">그 중 일부를 다음.NET Core 시리즈에서 사용할 수 있습니다 (.NET Core 2.x), 되지만 다른 패턴의 대상.NET Core 및 사용할 수 없습니다 새 응용 프로그램에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-119">Some of them will be available in later .NET Core releases (.NET Core 2.x), but others do not apply to the new application patterns targeted by .NET Core and might never be available.</span></span>

<span data-ttu-id="daa5e-120">다음은 대부분의.NET Core 2.0에서 사용할 수 없는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-120">The following list shows most of the technologies that are not available in .NET Core 2.0:</span></span>

-   <span data-ttu-id="daa5e-121">ASP.NET Web Forms 합니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-121">ASP.NET Web Forms.</span></span> <span data-ttu-id="daa5e-122">이 기술은만.NET Framework에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-122">This technology is only available on .NET Framework.</span></span> <span data-ttu-id="daa5e-123">현재 .NET Core에 ASP.NET Web Forms를 적용할 계획은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-123">Currently there are no plans to bring ASP.NET Web Forms to .NET Core.</span></span>

-   <span data-ttu-id="daa5e-124">WCF 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-124">WCF services.</span></span> <span data-ttu-id="daa5e-125">경우에 한 [WCF 클라이언트 라이브러리](https://github.com/dotnet/wcf) .NET Core에서 WCF 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-125">Even when a [WCF-Client library](https://github.com/dotnet/wcf) is available to consume WCF services from .NET Core.</span></span> <span data-ttu-id="daa5e-126">2017 중순 현재 WCF 서버 구현은.NET Framework에서 사용할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-126">as of mid-2017, the WCF server implementation is only available on .NET Framework.</span></span> <span data-ttu-id="daa5e-127">.NET Core의 이후 릴리스에서이 시나리오 고려 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-127">This scenario might be considered for future releases of .NET Core.</span></span>

-   <span data-ttu-id="daa5e-128">워크플로 관련 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-128">Workflow-related services.</span></span> <span data-ttu-id="daa5e-129">Windows WF (Workflow Foundation), 워크플로 서비스 (WCF + 단일 서비스에서 WF) 및 WCF 데이터 서비스 (이전의 ADO.NET Data Services)은.NET Framework에서 사용할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-129">Windows Workflow Foundation (WF), Workflow Services (WCF + WF in a single service), and WCF Data Services (formerly known as ADO.NET Data Services) are only available on .NET Framework.</span></span> <span data-ttu-id="daa5e-130">현재.NET Core 서로 일치 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-130">There are currently no plans to bring them to .NET Core.</span></span>

<span data-ttu-id="daa5e-131">공식에 나열 된 기술 외에도 [.NET Core 로드맵](https://github.com/aspnet/Home/wiki/Roadmap), 다른 기능과.NET Core로 이식 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-131">In addition to the technologies listed in the official [.NET Core roadmap](https://github.com/aspnet/Home/wiki/Roadmap), other features might be ported to .NET Core.</span></span> <span data-ttu-id="daa5e-132">전체 목록에 대 한 것으로 태그 항목을 찾아야 [포트 코어](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) CoreFX GitHub 사이트에서.</span><span class="sxs-lookup"><span data-stu-id="daa5e-132">For a full list, look at the items tagged as [port-to-core](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) on the CoreFX GitHub site.</span></span> <span data-ttu-id="daa5e-133">이 목록에서 Microsoft.NET Core에 이러한 구성 요소를 업그레이드 하기 위한 코드를 나타내지 않는 참고-항목 커뮤니티에서 요청을 단순히 캡처.</span><span class="sxs-lookup"><span data-stu-id="daa5e-133">Note that this list does not represent a commitment from Microsoft to bring those components to .NET Core—the items simply capture requests from the community.</span></span> <span data-ttu-id="daa5e-134">위에 나열 된 구성 요소 중 하나에 대 한 관심이 있으면 음성을 답변을 받을 수 있도록 GitHub의 토론에 참여 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-134">If you care about any of the components listed above, consider participating in the discussions on GitHub so that your voice can be heard.</span></span> <span data-ttu-id="daa5e-135">누락된 내용이 있다고 생각이 들면 [CoreFX 리포지토리에 새로운 문제를 등록](https://github.com/dotnet/corefx/issues/new)하세요.</span><span class="sxs-lookup"><span data-stu-id="daa5e-135">And if you think something is missing, please [file a new issue in the CoreFX repository](https://github.com/dotnet/corefx/issues/new).</span></span>

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a><span data-ttu-id="daa5e-136">플랫폼 또는.NET Core를 지원 하지 않는 API를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="daa5e-136">Using a platform or API that does not support .NET Core</span></span>

<span data-ttu-id="daa5e-137">일부 Microsoft 또는 타사 플랫폼과.NET Core를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-137">Some Microsoft or third-party platforms do not support .NET Core.</span></span> <span data-ttu-id="daa5e-138">예를 들어 일부 Azure 서비스가 아직 사용할 수 없는.NET Core에서 소비에 대 한 SDK를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-138">For example, some Azure services provide an SDK that is not yet available for consumption on .NET Core.</span></span> <span data-ttu-id="daa5e-139">모든 Azure 서비스는.NET Core를 사용 하 여 결국 때문 일시적입니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-139">This is temporary, because all Azure services will eventually use .NET Core.</span></span> <span data-ttu-id="daa5e-140">예를 들어는 [Azure DocumentDB SDK for.NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1) 2016 년 11 월 16 일에 대 한 미리 보기로 릴리스된 그러나 이제에서는 안정적인 버전으로 사용할 수 있는 (GA).</span><span class="sxs-lookup"><span data-stu-id="daa5e-140">For example, the [Azure DocumentDB SDK for .NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1) was released as a preview on November 16, 2016, but it is now generally available (GA) as a stable version.</span></span>

<span data-ttu-id="daa5e-141">그 동안에 모든 플랫폼 또는 Azure 서비스에에서 여전히를 지원 하지 않으면.NET Core는 클라이언트 API와.NET Framework에서 Azure 서비스 또는 SDK 클라이언트에서 해당 하는 REST API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daa5e-141">In the meantime, if any platform or service in Azure still doesn’t support .NET Core with its client API, you can use the equivalent REST API from the Azure service or the client SDK on .NET Framework.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="daa5e-142">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="daa5e-142">Additional resources</span></span>

-   <span data-ttu-id="daa5e-143">**.NET core 가이드**
    [*https://docs.microsoft.com/dotnet/core/index*](https://docs.microsoft.com/dotnet/core/index)</span><span class="sxs-lookup"><span data-stu-id="daa5e-143">**.NET Core Guide**
[*https://docs.microsoft.com/dotnet/core/index*](https://docs.microsoft.com/dotnet/core/index)</span></span>

-   <span data-ttu-id="daa5e-144">**.NET Framework에서.NET Core로 이식**
    [*https://docs.microsoft.com/dotnet/core/porting/index*](https://docs.microsoft.com/dotnet/core/porting/index)</span><span class="sxs-lookup"><span data-stu-id="daa5e-144">**Porting from .NET Framework to .NET Core**
[*https://docs.microsoft.com/dotnet/core/porting/index*](https://docs.microsoft.com/dotnet/core/porting/index)</span></span>

-   <span data-ttu-id="daa5e-145">**Docker 설명서에.NET framework**
    [*https://docs.microsoft.com/dotnet/framework/docker/*](https://docs.microsoft.com/dotnet/framework/docker/)</span><span class="sxs-lookup"><span data-stu-id="daa5e-145">**.NET Framework on Docker Guide**
[*https://docs.microsoft.com/dotnet/framework/docker/*](https://docs.microsoft.com/dotnet/framework/docker/)</span></span>

-   <span data-ttu-id="daa5e-146">**.NET 구성 요소 개요**
    [*https://docs.microsoft.com/dotnet/standard/components*](https://docs.microsoft.com/dotnet/standard/components)</span><span class="sxs-lookup"><span data-stu-id="daa5e-146">**.NET Components Overview**
[*https://docs.microsoft.com/dotnet/standard/components*](https://docs.microsoft.com/dotnet/standard/components)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="daa5e-147">[이전] (net-코어-컨테이너-scenarios.md) [다음] (컨테이너-프레임 워크-선택-factors.md)</span><span class="sxs-lookup"><span data-stu-id="daa5e-147">[Previous] (net-core-container-scenarios.md) [Next] (container-framework-choice-factors.md)</span></span>
