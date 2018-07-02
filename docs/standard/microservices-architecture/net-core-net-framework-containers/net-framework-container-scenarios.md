---
title: Docker 컨테이너에 대해 .NET Framework를 선택하는 경우
description: 컨테이너화된 .NET 응용 프로그램용 .NET 마이크로 서비스 아키텍처 | Docker 컨테이너에 대해 .NET Framework를 선택하는 경우
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/07/2018
ms.openlocfilehash: 2fdf0c24999891e48e1867e8fa7b4ba0f5302850
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106712"
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a><span data-ttu-id="edfda-103">Docker 컨테이너에 대해 .NET Framework를 선택하는 경우</span><span class="sxs-lookup"><span data-stu-id="edfda-103">When to choose .NET Framework for Docker containers</span></span>

<span data-ttu-id="edfda-104">.NET Core는 새 응용 프로그램 및 응용 프로그램 패턴에 상당한 이점을 제공하는 반면, .NET Framework는 계속해서 다양한 기존 시나리오에 적합한 선택 사양이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-104">While .NET Core offers significant benefits for new applications and application patterns, .NET Framework will continue to be a good choice for many existing scenarios.</span></span>

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a><span data-ttu-id="edfda-105">기존 응용 프로그램을 Windows Server 컨테이너로 직접 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="edfda-105">Migrating existing applications directly to a Windows Server container</span></span>

<span data-ttu-id="edfda-106">마이크로 서비스를 만들지 않는 경우에도 Docker 컨테이너를 사용하여 배포를 단순화하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-106">You might want to use Docker containers just to simplify deployment, even if you are not creating microservices.</span></span> <span data-ttu-id="edfda-107">예를 들어 Docker를 사용하여 DevOps 워크플로를 향상시키려는 경우, 컨테이너를 통해 더 효율적으로 격리된 테스트 환경을 제공하고, 프로덕션 환경으로 이동할 때 종속성 누락으로 인한 배포 문제를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-107">For example, perhaps you want to improve your DevOps workflow with Docker—containers can give you better isolated test environments and can also eliminate deployment issues caused by missing dependencies when you move to a production environment.</span></span> <span data-ttu-id="edfda-108">이러한 경우 모놀리식 응용 프로그램을 배포하더라도 현재 .NET Framework 응용 프로그램에 Docker 및 Windows 컨테이너를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-108">In cases like these, even if you are deploying a monolithic application, it makes sense to use Docker and Windows Containers for your current .NET Framework applications.</span></span>

<span data-ttu-id="edfda-109">이 시나리오에서 대부분의 경우 기존 응용 프로그램을 .NET Core로 마이그레이션할 필요가 없습니다. 즉 기존 .NET Framework가 포함된 Docker 컨테이너를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-109">In most cases for this scenario, you will not need to migrate your existing applications to .NET Core; you can use Docker containers that include the traditional .NET Framework.</span></span> <span data-ttu-id="edfda-110">그러나 ASP.NET Core에서 새 웹 서비스를 작성하는 것과 같이 기존 응용 프로그램을 확장할 때 .NET Core를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-110">However, a recommended approach is to use .NET Core as you extend an existing application, such as writing a new service in ASP.NET Core.</span></span>

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a><span data-ttu-id="edfda-111">.NET Core에 사용할 수 없는 타사 .NET 라이브러리 또는 NuGet 패키지 사용</span><span class="sxs-lookup"><span data-stu-id="edfda-111">Using third-party .NET libraries or NuGet packages not available for .NET Core</span></span>

<span data-ttu-id="edfda-112">타사 라이브러리는 [.NET 표준](../../net-standard.md)을 빠르게 수용하여 .NET Core를 포함한 모든 .NET 계열에서 코드 공유를 사용할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-112">Third-party libraries are quickly embracing the [.NET Standard](../../net-standard.md), which enables code sharing across all .NET flavors, including .NET Core.</span></span> <span data-ttu-id="edfda-113">.NET Standard 라이브러리 2.0 이상에서는 서로 다른 프레임워크 간의 API 표면 호환성이 크게 증가하였으며, .NET Core 2.x에서는 응용 프로그램이 기존 .NET Framework 라이브러리를 직접 참조할 수도 있습니다([호환 shim](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work) 참조).</span><span class="sxs-lookup"><span data-stu-id="edfda-113">With the .NET Standard Library 2.0 and beyond, the API surface compatibility across different frameworks has become significantly larger and in .NET Core 2.x applications can also directly reference existing .NET Framework libraries (see [compat shim](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work)).</span></span>

<span data-ttu-id="edfda-114">그러나 .NET Standard 2.0 및 .NET Core 2.0 이후의 뛰어난 발전에도 불구하고 특정 NuGet 패키지에서 Windows를 실행해야 하고 .NET Core를 지원하지 않는 경우가 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-114">However, even with that exceptional progression since .NET Standard 2.0 and .NET Core 2.0, there might be cases where certain NuGet packages need Windows to run and might not support .NET Core.</span></span> <span data-ttu-id="edfda-115">이러한 패키지가 응용 프로그램에 매우 중요한 경우 Windows 컨테이너에서 .NET Framework를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-115">If those packages are critical for your application, then you will need to use .NET Framework on Windows Containers.</span></span>

## <a name="using-net-technologies-not-available-for-net-core"></a><span data-ttu-id="edfda-116">.NET Core에 사용할 수 없는 .NET 기술 사용</span><span class="sxs-lookup"><span data-stu-id="edfda-116">Using .NET technologies not available for .NET Core</span></span> 

<span data-ttu-id="edfda-117">일부 .NET Framework 기술은 현재 버전의 .NET Core(이 문서를 작성한 시점 이후 버전 2.1)에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-117">Some .NET Framework technologies are not available in the current version of .NET Core (version 2.1 as of this writing).</span></span> <span data-ttu-id="edfda-118">그 중 일부는 이후 .NET Core 릴리스(.NET Core 2.x)에서 사용할 수 있지만, 다른 일부는 .NET Core에서 대상으로 하는 새 응용 프로그램 패턴에 적용되지 않으며 사용하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-118">Some of them will be available in later .NET Core releases (.NET Core 2.x), but others do not apply to the new application patterns targeted by .NET Core and might never be available.</span></span>

<span data-ttu-id="edfda-119">다음 목록에서는 .NET Core 2.1에서 사용할 수 없는 대부분의 기술을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-119">The following list shows most of the technologies that are not available in .NET Core 2.1:</span></span>

-   <span data-ttu-id="edfda-120">ASP.NET Web Forms.</span><span class="sxs-lookup"><span data-stu-id="edfda-120">ASP.NET Web Forms.</span></span> <span data-ttu-id="edfda-121">이 기술은 .NET Framework에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-121">This technology is only available on .NET Framework.</span></span> <span data-ttu-id="edfda-122">현재 .NET Core에 ASP.NET Web Forms를 적용할 계획은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-122">Currently there are no plans to bring ASP.NET Web Forms to .NET Core.</span></span>

-   <span data-ttu-id="edfda-123">WCF 서비스.</span><span class="sxs-lookup"><span data-stu-id="edfda-123">WCF services.</span></span> <span data-ttu-id="edfda-124">[WCF 클라이언트 라이브러리](https://github.com/dotnet/wcf)가 .NET Core에서 WCF 서비스를 사용할 수 있는 경우에도</span><span class="sxs-lookup"><span data-stu-id="edfda-124">Even when a [WCF-Client library](https://github.com/dotnet/wcf) is available to consume WCF services from .NET Core.</span></span> <span data-ttu-id="edfda-125">2017년 중반부터 WCF 서버 구현은 .NET Framework에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-125">as of mid-2017, the WCF server implementation is only available on .NET Framework.</span></span> <span data-ttu-id="edfda-126">이 시나리오는 .NET Core의 향후 릴리스에서 고려될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-126">This scenario might be considered for future releases of .NET Core.</span></span>

-   <span data-ttu-id="edfda-127">워크플로 관련 서비스.</span><span class="sxs-lookup"><span data-stu-id="edfda-127">Workflow-related services.</span></span> <span data-ttu-id="edfda-128">Windows WF(Workflow Foundation), 워크플로 서비스(단일 서비스의 WCF + WF) 및 WCF Data Services(이전의 ADO.NET Data Services)는 .NET Framework에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-128">Windows Workflow Foundation (WF), Workflow Services (WCF + WF in a single service), and WCF Data Services (formerly known as ADO.NET Data Services) are only available on .NET Framework.</span></span> <span data-ttu-id="edfda-129">현재 .NET Core로 가져올 계획은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-129">There are currently no plans to bring them to .NET Core.</span></span>

<span data-ttu-id="edfda-130">공식 [.NET Core 로드맵](https://github.com/aspnet/Home/wiki/Roadmap)에 나열된 기술 외에도 다른 기능이 .NET Core에 이식될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-130">In addition to the technologies listed in the official [.NET Core roadmap](https://github.com/aspnet/Home/wiki/Roadmap), other features might be ported to .NET Core.</span></span> <span data-ttu-id="edfda-131">전체 목록은 CoreFX GitHub 사이트에서 [port-to-core](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) 태그로 지정된 항목을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="edfda-131">For a full list, look at the items tagged as [port-to-core](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) on the CoreFX GitHub site.</span></span> <span data-ttu-id="edfda-132">이 목록은 이러한 구성 요소를 .NET Core로 가져오는 Microsoft의 약속을 나타내지는 않으며, 항목은 단순히 커뮤니티의 요청만 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-132">Note that this list does not represent a commitment from Microsoft to bring those components to .NET Core — the items simply capture requests from the community.</span></span> <span data-ttu-id="edfda-133">위에 나열된 구성 요소 중 하나에 관심이 있는 경우 자신의 의견에 대해 답변을 받을 수 있도록 GitHub의 토론에 참여해 보세요.</span><span class="sxs-lookup"><span data-stu-id="edfda-133">If you care about any of the components listed above, consider participating in the discussions on GitHub so that your voice can be heard.</span></span> <span data-ttu-id="edfda-134">누락된 내용이 있다고 생각이 들면 [CoreFX 리포지토리에 새로운 문제를 등록](https://github.com/dotnet/corefx/issues/new)하세요.</span><span class="sxs-lookup"><span data-stu-id="edfda-134">And if you think something is missing, please [file a new issue in the CoreFX repository](https://github.com/dotnet/corefx/issues/new).</span></span>

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a><span data-ttu-id="edfda-135">.NET Core를 지원하지 않는 플랫폼 또는 API 사용</span><span class="sxs-lookup"><span data-stu-id="edfda-135">Using a platform or API that does not support .NET Core</span></span>

<span data-ttu-id="edfda-136">일부 Microsoft 또는 타사 플랫폼은 .NET Core를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-136">Some Microsoft or third-party platforms do not support .NET Core.</span></span> <span data-ttu-id="edfda-137">예를 들어 일부 Azure 서비스는 .NET Core에서 아직 사용할 수 없는 SDK를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-137">For example, some Azure services provide an SDK that is not yet available for consumption on .NET Core.</span></span> <span data-ttu-id="edfda-138">모든 Azure 서비스에서 결국에는 .NET Core를 사용할 것이므로 이는 일시적인 현상입니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-138">This is temporary, because all Azure services will eventually use .NET Core.</span></span> <span data-ttu-id="edfda-139">예를 들어 [.NET Core용 Azure DocumentDB SDK](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1)는 2016년 11월 16일에 미리 보기로 릴리스되었지만 이제는 안정적인 GA(일반 공급) 버전으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-139">For example, the [Azure DocumentDB SDK for .NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1) was released as a preview on November 16, 2016, but it is now generally available (GA) as a stable version.</span></span>

<span data-ttu-id="edfda-140">그동안 Azure의 플랫폼 또는 서비스에서 여전히 클라이언트 API를 통해 .NET Core를 지원하지 않는 경우에는 Azure 서비스 또는 .NET Framework의 클라이언트 SDK에서 동등한 REST API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edfda-140">In the meantime, if any platform or service in Azure still doesn’t support .NET Core with its client API, you can use the equivalent REST API from the Azure service or the client SDK on .NET Framework.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="edfda-141">추가 자료</span><span class="sxs-lookup"><span data-stu-id="edfda-141">Additional resources</span></span>

-   <span data-ttu-id="edfda-142">**.NET Core 가이드**
    [*https://docs.microsoft.com/dotnet/core/index*](../../../core/index.md)</span><span class="sxs-lookup"><span data-stu-id="edfda-142">**.NET Core Guide**
[*https://docs.microsoft.com/dotnet/core/index*](../../../core/index.md)</span></span>

-   <span data-ttu-id="edfda-143">**.NET Framework에서 .NET Core로 이식**
    [*https://docs.microsoft.com/dotnet/core/porting/index*](../../../core/porting/index.md)</span><span class="sxs-lookup"><span data-stu-id="edfda-143">**Porting from .NET Framework to .NET Core**
[*https://docs.microsoft.com/dotnet/core/porting/index*](../../../core/porting/index.md)</span></span>

-   <span data-ttu-id="edfda-144">**Docker 가이드의 .NET Framework**
    [*https://docs.microsoft.com/dotnet/framework/docker/*](../../../framework/docker/index.md)</span><span class="sxs-lookup"><span data-stu-id="edfda-144">**.NET Framework on Docker Guide**
[*https://docs.microsoft.com/dotnet/framework/docker/*](../../../framework/docker/index.md)</span></span>

-   <span data-ttu-id="edfda-145">**.NET 구성 요소 개요**
    [*https://docs.microsoft.com/dotnet/standard/components*](../../components.md)</span><span class="sxs-lookup"><span data-stu-id="edfda-145">**.NET Components Overview**
[*https://docs.microsoft.com/dotnet/standard/components*](../../components.md)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="edfda-146">[이전](net-core-container-scenarios.md)
[다음](container-framework-choice-factors.md)</span><span class="sxs-lookup"><span data-stu-id="edfda-146">[Previous](net-core-container-scenarios.md)
[Next](container-framework-choice-factors.md)</span></span>
