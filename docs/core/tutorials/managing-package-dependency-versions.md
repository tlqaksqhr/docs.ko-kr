---
title: ".NET Core 1.0에 대한 패키지 종속성 버전을 관리하는 방법"
description: ".NET Core 라이브러리 및 앱에 대한 패키지 종속성 버전 관리에 관해 알아봅니다."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 4424a947-bdf9-4775-8d48-dc350a4e0aee
ms.openlocfilehash: b0d4082d020da782b334a5b3999905f7de744e64
ms.sourcegitcommit: 5d0e069655439984862a835f400058b7e8bbadc6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2017
---
# <a name="how-to-manage-package-dependency-versions-for-net-core-10"></a><span data-ttu-id="beb9b-104">.NET Core 1.0에 대한 패키지 종속성 버전을 관리하는 방법</span><span class="sxs-lookup"><span data-stu-id="beb9b-104">How to Manage Package Dependency Versions for .NET Core 1.0</span></span>

<span data-ttu-id="beb9b-105">이 문서에서는 .NET Core 라이브러리 및 앱의 패키지 버전에 대해 알아야 할 내용을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-105">This article covers what you need to know about package versions for your .NET Core libraries and apps.</span></span>

## <a name="glossary"></a><span data-ttu-id="beb9b-106">용어</span><span class="sxs-lookup"><span data-stu-id="beb9b-106">Glossary</span></span>

<span data-ttu-id="beb9b-107">**고정** - 종속성 고정이란 .NET Core 1.0용 NuGet에 대해 릴리스된 동일한 패키지 "제품군"을 사용한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-107">**Fix** - Fixing dependencies means you are using the same "family" of packages released on NuGet for .NET Core 1.0.</span></span>

<span data-ttu-id="beb9b-108">**메타패키지** - NuGet 패키지 집합을 나타내는 NuGet 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-108">**Metapackage** - A NuGet package that represents a set of NuGet packages.</span></span>

<span data-ttu-id="beb9b-109">**잘라내기** - 종속되지 않은 패키지를 메타패키지에서 제거하는 행위입니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-109">**Trimming** - The act of removing the packages you do not depend on from a metapackage.</span></span>  <span data-ttu-id="beb9b-110">이는 NuGet 패키지 작성자와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-110">This is something relevant for NuGet package authors.</span></span>  <span data-ttu-id="beb9b-111">자세한 내용은 [project.json(project.json으로 패키지 종속성 감소)](../deploying/reducing-dependencies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="beb9b-111">See [Reducing Package Dependencies with project.json](../deploying/reducing-dependencies.md) for more information.</span></span> 

## <a name="fix-your-dependencies-to-net-core-10"></a><span data-ttu-id="beb9b-112">.NET Core 1.0으로 종속성 고정</span><span class="sxs-lookup"><span data-stu-id="beb9b-112">Fix your dependencies to .NET Core 1.0</span></span>

<span data-ttu-id="beb9b-113">신뢰할 수 있는 방식으로 패키지를 복원하고 신뢰할 수 있는 코드를 작성하려면 .NET Core 1.0과 함께 제공된 패키지의 버전에 대한 종속성을 수정하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-113">To reliably restore packages and write reliable code, it's important that you fix your dependencies to the versions of packages shipping alongside .NET Core 1.0.</span></span>  <span data-ttu-id="beb9b-114">즉, 추가 한정자 없이 모든 패키지에 단일 버전이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-114">This means every package should have a single version with no additional qualifiers.</span></span>

<span data-ttu-id="beb9b-115">**1.0으로 고정된 패키지의 예**</span><span class="sxs-lookup"><span data-stu-id="beb9b-115">**Examples of packages fixed to 1.0**</span></span>

`"System.Collections":"4.0.11"`

`"NETStandard.Library":"1.6.0"`

`"Microsoft.NETCore.App":"1.0.0"`

<span data-ttu-id="beb9b-116">**1.0으로 고정되지 않는 패키지의 예**</span><span class="sxs-lookup"><span data-stu-id="beb9b-116">**Examples of packages that are NOT fixed to 1.0**</span></span>

`"Microsoft.NETCore.App":"1.0.0-rc4-00454-00"`

`"System.Net.Http":"4.1.0-*"`

`"System.Text.RegularExpressions":"4.0.10-rc3-24021-00"`

### <a name="why-does-this-matter"></a><span data-ttu-id="beb9b-117">이것이 왜 문제가 될까요?</span><span class="sxs-lookup"><span data-stu-id="beb9b-117">Why does this matter?</span></span>

<span data-ttu-id="beb9b-118">.NET Core 1.0와 함께 어떤 배에 종속성을 수정 하는 경우 이러한 패키지는 모두 함께 작동 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-118">We guarantee that if you fix your dependencies to what ships alongside .NET Core 1.0, those packages will all work together.</span></span> <span data-ttu-id="beb9b-119">이렇게 고정되지 않은 패키지를 사용할 경우 작동이 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-119">There is no such guarantee if you use packages which aren't fixed in this way.</span></span>

### <a name="scenarios"></a><span data-ttu-id="beb9b-120">시나리오</span><span class="sxs-lookup"><span data-stu-id="beb9b-120">Scenarios</span></span>

<span data-ttu-id="beb9b-121">.NET Core 1.0과 함께 출시된 모든 패키지와 버전의 큰 목록이 있지만 코드가 특정 시나리오에 놓인 경우 이러한 목록을 검토하지 않아도 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-121">Although there is a big list of all packages and their versions released with .NET Core 1.0, you may not have to look through it if your code falls under certain scenarios.</span></span>

<span data-ttu-id="beb9b-122">`NETStandard.Library`**에만 종속되어 있나요** **?**</span><span class="sxs-lookup"><span data-stu-id="beb9b-122">**Are you depending only on** `NETStandard.Library`**?**</span></span>

<span data-ttu-id="beb9b-123">따라서 문제를 해결 해야 하는 경우 프로그램 `NETStandard.Library` 패키지를 버전 `1.6`합니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-123">If so, you should fix your `NETStandard.Library` package to version `1.6`.</span></span>  <span data-ttu-id="beb9b-124">이것은 조정된 메타패키지이므로 패키지 종료도 1.0으로 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-124">Because this is a curated metapackage, its package closure is also fixed to 1.0.</span></span>

<span data-ttu-id="beb9b-125">`Microsoft.NETCore.App`**에만 종속되어 있나요** **?**</span><span class="sxs-lookup"><span data-stu-id="beb9b-125">**Are you depending only on** `Microsoft.NETCore.App`**?**</span></span>

<span data-ttu-id="beb9b-126">따라서 문제를 해결 해야 하는 경우 프로그램 `Microsoft.NETCore.App` 패키지를 버전 `1.0.0`합니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-126">If so, you should fix your `Microsoft.NETCore.App` package to version `1.0.0`.</span></span>  <span data-ttu-id="beb9b-127">이것은 조정된 메타패키지이므로 패키지 종료도 1.0으로 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-127">Because this is a curated metapackage, its package closure is also fixed to 1.0.</span></span>

<span data-ttu-id="beb9b-128">**당신은 [트리밍](../deploying/reducing-dependencies.md) 프로그램** `NETStandard.Library` **또는** `Microsoft.NETCore.App` **metapackage 종속성?**</span><span class="sxs-lookup"><span data-stu-id="beb9b-128">**Are you [trimming](../deploying/reducing-dependencies.md) your** `NETStandard.Library` **or** `Microsoft.NETCore.App` **metapackage dependencies?**</span></span>

<span data-ttu-id="beb9b-129">그렇다면 시작하는 메타패키지도 1.0으로 고정되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-129">If so, you should ensure that the metapackage you start with is fixed to 1.0.</span></span>  <span data-ttu-id="beb9b-130">잘라낸 후 종속된 개별 패키지도 1.0으로 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-130">The individual packages you depend on after trimming are also fixed to 1.0.</span></span>

<span data-ttu-id="beb9b-131">**외부에서 패키지에 따라 입니까는** `NETStandard.Library` **또는** `Microsoft.NETCore.App` **metapackages?**</span><span class="sxs-lookup"><span data-stu-id="beb9b-131">**Are you depending on packages outside the** `NETStandard.Library` **or** `Microsoft.NETCore.App` **metapackages?**</span></span>

<span data-ttu-id="beb9b-132">그렇다면 다른 종속성을 1.0으로 고정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-132">If so, you need to fix your other dependencies to 1.0.</span></span>  <span data-ttu-id="beb9b-133">이 문서 뒤에 나오는 올바른 패키지 버전 및 빌드 번호를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="beb9b-133">See the correct package versions and build numbers at the end of this article.</span></span>

### <a name="a-note-on-using-a-splat-string--when-versioning"></a><span data-ttu-id="beb9b-134">버전 관리 시 스플랫 문자열(\*) 참고 사항</span><span class="sxs-lookup"><span data-stu-id="beb9b-134">A note on using a splat string (\*) when versioning</span></span>

<span data-ttu-id="beb9b-135">스플랫(\*) 문자열을 사용하는 버전 관리 패턴을 다음과 같이 조정했을 수 있습니다. `"System.Collections":"4.0.11-*"`</span><span class="sxs-lookup"><span data-stu-id="beb9b-135">You may have adopted a versioning pattern which uses a splat (\*) string like this: `"System.Collections":"4.0.11-*"`.</span></span>

<span data-ttu-id="beb9b-136">**이렇게 해서는 안 됩니다**.</span><span class="sxs-lookup"><span data-stu-id="beb9b-136">**You should not do this**.</span></span>  <span data-ttu-id="beb9b-137">스플랫 문자열을 사용하면 패키지가 다른 빌드에서 복원될 수 있으며, 이중 일부는 .NET Core 1.0보다 더 나아간 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-137">Using the splat string could result in restoring packages from different builds, some of which may be further along than .NET Core 1.0.</span></span>  <span data-ttu-id="beb9b-138">이 경우 일부 패키지는 호환되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beb9b-138">This could then result in some packages being incompatible.</span></span>

## <a name="packages-and-version-numbers-organized-by-metapackage"></a><span data-ttu-id="beb9b-139">메타패키지로 구성된 패키지 및 버전 번호</span><span class="sxs-lookup"><span data-stu-id="beb9b-139">Packages and Version Numbers organized by Metapackage</span></span>

<span data-ttu-id="beb9b-140">[.NET 표준 패키지 및 1.0에 대한 해당 버전을 나열합니다](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt).</span><span class="sxs-lookup"><span data-stu-id="beb9b-140">[List of all .NET Standard packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt).</span></span>

<span data-ttu-id="beb9b-141">[모든 런타임 패키지 및 1.0에 대한 해당 버전을 나열합니다](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt).</span><span class="sxs-lookup"><span data-stu-id="beb9b-141">[List of all runtime packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt).</span></span>

<span data-ttu-id="beb9b-142">[모든 .NET Core 응용 프로그램 패키지 및 1.0에 대한 해당 버전을 나열합니다](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt).</span><span class="sxs-lookup"><span data-stu-id="beb9b-142">[List of all .NET Core application packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt).</span></span>
