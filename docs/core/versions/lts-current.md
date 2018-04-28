---
title: .NET Core 지원
description: .NET Core에 대한 여러 릴리스 트레인 지원(LTS 및 현재)에 대해 알아봅니다.
author: kendrahavens
ms.author: mairaw
ms.date: 01/30/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 8bb2cd1895513ca2d895aa45671cb341193d2359
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="net-core-support"></a><span data-ttu-id="2af3b-103">.NET Core 지원</span><span class="sxs-lookup"><span data-stu-id="2af3b-103">.NET Core Support</span></span>

<span data-ttu-id="2af3b-104">.NET Core 지원에 대한 일반적인 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-104">This is a general description of .NET Core support.</span></span>

## <a name="lts-and-current-release-trains"></a><span data-ttu-id="2af3b-105">LTS 및 현재 릴리스 트레인</span><span class="sxs-lookup"><span data-stu-id="2af3b-105">LTS and Current Release Trains</span></span>

<span data-ttu-id="2af3b-106">두 개의 지원 릴리스 트레인이 있는 것은 소프트웨어 환경 특히, .NET Core와 같은 오픈 프로젝트 전반에서 일반적으로 사용되는 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-106">Having two support release trains is a common concept in use throughout the software world, specially for open-source projects like .NET Core.</span></span> <span data-ttu-id="2af3b-107">.NET Core에는 [LTS(장기 지원)](https://en.wikipedia.org/wiki/Long-term_support) 및 현재라는 두 가지 지원 릴리스 트레인이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-107">.NET Core has the following support release trains: [Long Term Support (LTS)](https://en.wikipedia.org/wiki/Long-term_support) and Current.</span></span> <span data-ttu-id="2af3b-108">LTS 릴리스는 중요한 문제에 대한 수정 및 보안 수정을 수신하여 수명 주기 동안 안정성을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-108">LTS releases are maintained for stability over their lifecycle, receiving fixes for important issues and security fixes.</span></span> <span data-ttu-id="2af3b-109">현재 릴리스에서는 새 기능이 작동되고 추가 버그 수정이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-109">New feature work and additional bug fixes take place in Current releases.</span></span> <span data-ttu-id="2af3b-110">지원 관점에서 이러한 릴리스 트레인에는 다음과 같은 지원 수명 주기 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-110">From a support perspective, these release trains have the following support lifecycle attributes.</span></span>

<span data-ttu-id="2af3b-111">LTS 릴리스:</span><span class="sxs-lookup"><span data-stu-id="2af3b-111">LTS releases are</span></span>
* <span data-ttu-id="2af3b-112">LTS의 일반 공급 날짜 이후 3년 동안 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-112">Supported for three years after the general availability date of a LTS release</span></span>
* <span data-ttu-id="2af3b-113">또는 후속 LTS 릴리스의 일반 공급 후 1년 동안 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-113">Or one year after the general availability of a subsequent LTS release</span></span>

<span data-ttu-id="2af3b-114">현재 릴리스:</span><span class="sxs-lookup"><span data-stu-id="2af3b-114">Current releases are</span></span>
* <span data-ttu-id="2af3b-115">부모 LTS 릴리스와 동일한 3년 기간 내에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-115">Supported within the same three-year window as the parent LTS release</span></span>
* <span data-ttu-id="2af3b-116">후속 현재 릴리스의 일반 공급 후 3개월 동안 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-116">Supported for three months after the general availability of a subsequent Current release</span></span>
* <span data-ttu-id="2af3b-117">그리고 후속 LTS 릴리스의 일반 공급 후 1년 동안 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-117">And one year after the general availability of a subsequent LTS release</span></span>

## <a name="versioning"></a><span data-ttu-id="2af3b-118">버전 관리</span><span class="sxs-lookup"><span data-stu-id="2af3b-118">Versioning</span></span>
<span data-ttu-id="2af3b-119">새 LTS 릴리스는 주 버전 번호가 증가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-119">New LTS releases are marked by an increase in the Major version number.</span></span> <span data-ttu-id="2af3b-120">현재 릴리스는 해당하는 LTS 트레인과 주 번호가 동일하고 부 버전 번호가 증가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-120">Current releases have the same Major number as the corresponding LTS train and are marked by an increase in the Minor version number.</span></span> <span data-ttu-id="2af3b-121">예를 들어 LTS는 1.0.3이 되고 현재는 1.1.0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-121">For example, 1.0.3 would be LTS and 1.1.0 would be Current.</span></span> <span data-ttu-id="2af3b-122">어느 한 트레인의 버그 수정 업데이트가 수행되면 패치 버전이 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-122">Bug fix updates to either train increment the Patch version.</span></span> <span data-ttu-id="2af3b-123">버전 관리 체계에 대한 자세한 내용은 [.NET Core 버전 관리](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2af3b-123">For more information on the versioning scheme, see [.NET Core Versioning](index.md).</span></span>

## <a name="what-causes-updates-in-lts-and-current-trains"></a><span data-ttu-id="2af3b-124">LTS 및 현재 트레인에서 업데이트가 수행되는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="2af3b-124">What causes updates in LTS and Current trains?</span></span>
<span data-ttu-id="2af3b-125">버그 수정 또는 API 추가와 같이 버전 번호가 업데이트되게 하는 변경 사항에 대해 알아보려면 [버전 관리 설명서](index.md)의 의사 결정 트리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2af3b-125">To understand what specific changes, such as bug fixes or the addition of APIs, cause updates to the version numbers review the Decision Tree section in the [Versioning Documentation](index.md).</span></span> <span data-ttu-id="2af3b-126">어떤 변경 사항으로 현재 릴리스에서 LTS 분기가 생성되는지를 결정하는 기본 규칙은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-126">There is not a golden set of rules that decide what changes are pulled into the LTS branch from Current.</span></span> <span data-ttu-id="2af3b-127">일반적으로 필요한 동작을 수정하는 필수 보안 업데이트 및 패치로 인해 LTS 분기가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-127">Typically, necessary security updates and patches that fix expected behaviour are reasons to update the LTS branch.</span></span> <span data-ttu-id="2af3b-128">또한 항상 가능한 것은 아니지만 LTS 분기에서 최신 데스크톱 개발자 운영 체제를 지원하기 위한 것이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-128">We also intend to support recent desktop developer operating systems on the LTS branch, though this may not always be possible.</span></span> <span data-ttu-id="2af3b-129">특정 릴리스에서 지원되는 API, 수정 및 운영 체제를 파악하는 좋은 방법은 GitHub에서 [릴리스 정보](https://github.com/dotnet/core/tree/master/release-notes)를 검색하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2af3b-129">A good way to catch up on what APIs, fixes, and operating systems are supported in a certain release is to browse its [release notes](https://github.com/dotnet/core/tree/master/release-notes) on GitHub.</span></span>

### <a name="further-reading"></a><span data-ttu-id="2af3b-130">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2af3b-130">Further Reading</span></span>
* <span data-ttu-id="2af3b-131">[.NET Core Support Lifecycle Fact Sheet](https://www.microsoft.com/net/core/support)(.NET Core 지원 수명 주기 팩트 시트)</span><span class="sxs-lookup"><span data-stu-id="2af3b-131">[.NET Core Support Lifecycle Fact Sheet](https://www.microsoft.com/net/core/support)</span></span>
* <span data-ttu-id="2af3b-132">[Currently supported operating systems and versions](https://github.com/dotnet/core/blob/master/roadmap.md)(현재 지원되는 운영 체제 및 버전)</span><span class="sxs-lookup"><span data-stu-id="2af3b-132">[Currently supported operating systems and versions](https://github.com/dotnet/core/blob/master/roadmap.md)</span></span>
