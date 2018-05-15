---
title: .NET Core 1.0에 대한 패키지 종속성 버전을 관리하는 방법
description: .NET Core 라이브러리 및 앱에 대한 패키지 종속성 버전 관리에 관해 알아봅니다.
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.openlocfilehash: 96d154f045303e32de606475e77ab2e6b4f7bcda
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-manage-package-dependency-versions-for-net-core-10"></a><span data-ttu-id="340e3-103">.NET Core 1.0에 대한 패키지 종속성 버전을 관리하는 방법</span><span class="sxs-lookup"><span data-stu-id="340e3-103">How to Manage Package Dependency Versions for .NET Core 1.0</span></span>

<span data-ttu-id="340e3-104">이 문서에서는 .NET Core 라이브러리 및 앱의 패키지 버전에 대해 알아야 할 내용을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-104">This article covers what you need to know about package versions for your .NET Core libraries and apps.</span></span>

## <a name="glossary"></a><span data-ttu-id="340e3-105">용어</span><span class="sxs-lookup"><span data-stu-id="340e3-105">Glossary</span></span>

<span data-ttu-id="340e3-106">**고정** - 종속성 고정이란 .NET Core 1.0용 NuGet에 대해 릴리스된 동일한 패키지 "제품군"을 사용한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-106">**Fix** - Fixing dependencies means you are using the same "family" of packages released on NuGet for .NET Core 1.0.</span></span>

<span data-ttu-id="340e3-107">**메타패키지** - NuGet 패키지 집합을 나타내는 NuGet 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-107">**Metapackage** - A NuGet package that represents a set of NuGet packages.</span></span>

<span data-ttu-id="340e3-108">**잘라내기** - 종속되지 않은 패키지를 메타패키지에서 제거하는 행위입니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-108">**Trimming** - The act of removing the packages you do not depend on from a metapackage.</span></span>  <span data-ttu-id="340e3-109">이는 NuGet 패키지 작성자와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-109">This is something relevant for NuGet package authors.</span></span>  <span data-ttu-id="340e3-110">자세한 내용은 [project.json(project.json으로 패키지 종속성 감소)](../deploying/reducing-dependencies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="340e3-110">See [Reducing Package Dependencies with project.json](../deploying/reducing-dependencies.md) for more information.</span></span> 

## <a name="fix-your-dependencies-to-net-core-10"></a><span data-ttu-id="340e3-111">.NET Core 1.0으로 종속성 고정</span><span class="sxs-lookup"><span data-stu-id="340e3-111">Fix your dependencies to .NET Core 1.0</span></span>

<span data-ttu-id="340e3-112">신뢰할 수 있는 방식으로 패키지를 복원하고 신뢰할 수 있는 코드를 작성하려면 .NET Core 1.0과 함께 제공된 패키지의 버전에 대한 종속성을 수정하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-112">To reliably restore packages and write reliable code, it's important that you fix your dependencies to the versions of packages shipping alongside .NET Core 1.0.</span></span>  <span data-ttu-id="340e3-113">즉, 추가 한정자 없이 모든 패키지에 단일 버전이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-113">This means every package should have a single version with no additional qualifiers.</span></span>

<span data-ttu-id="340e3-114">**1.0으로 고정된 패키지의 예**</span><span class="sxs-lookup"><span data-stu-id="340e3-114">**Examples of packages fixed to 1.0**</span></span>

`"System.Collections":"4.0.11"`

`"NETStandard.Library":"1.6.0"`

`"Microsoft.NETCore.App":"1.0.0"`

<span data-ttu-id="340e3-115">**1.0으로 고정되지 않는 패키지의 예**</span><span class="sxs-lookup"><span data-stu-id="340e3-115">**Examples of packages that are NOT fixed to 1.0**</span></span>

`"Microsoft.NETCore.App":"1.0.0-rc4-00454-00"`

`"System.Net.Http":"4.1.0-*"`

`"System.Text.RegularExpressions":"4.0.10-rc3-24021-00"`

### <a name="why-does-this-matter"></a><span data-ttu-id="340e3-116">이것이 왜 문제가 될까요?</span><span class="sxs-lookup"><span data-stu-id="340e3-116">Why does this matter?</span></span>

<span data-ttu-id="340e3-117">.NET Core 1.0과 함께 제공된 것으로 종속성을 고정하는 경우 해당 패키지가 모두 함께 작동하는 것이 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-117">We guarantee that if you fix your dependencies to what ships alongside .NET Core 1.0, those packages will all work together.</span></span> <span data-ttu-id="340e3-118">이렇게 고정되지 않은 패키지를 사용할 경우 작동이 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-118">There is no such guarantee if you use packages which aren't fixed in this way.</span></span>

### <a name="scenarios"></a><span data-ttu-id="340e3-119">시나리오</span><span class="sxs-lookup"><span data-stu-id="340e3-119">Scenarios</span></span>

<span data-ttu-id="340e3-120">.NET Core 1.0과 함께 출시된 모든 패키지와 버전의 큰 목록이 있지만 코드가 특정 시나리오에 놓인 경우 이러한 목록을 검토하지 않아도 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-120">Although there is a big list of all packages and their versions released with .NET Core 1.0, you may not have to look through it if your code falls under certain scenarios.</span></span>

<span data-ttu-id="340e3-121">`NETStandard.Library`**에만 종속되어 있나요** **?**</span><span class="sxs-lookup"><span data-stu-id="340e3-121">**Are you depending only on** `NETStandard.Library`**?**</span></span>

<span data-ttu-id="340e3-122">이 경우 `NETStandard.Library` 패키지를 버전 `1.6`으로 고정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-122">If so, you should fix your `NETStandard.Library` package to version `1.6`.</span></span>  <span data-ttu-id="340e3-123">이것은 조정된 메타패키지이므로 패키지 종료도 1.0으로 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-123">Because this is a curated metapackage, its package closure is also fixed to 1.0.</span></span>

<span data-ttu-id="340e3-124">`Microsoft.NETCore.App`**에만 종속되어 있나요** **?**</span><span class="sxs-lookup"><span data-stu-id="340e3-124">**Are you depending only on** `Microsoft.NETCore.App`**?**</span></span>

<span data-ttu-id="340e3-125">이 경우 `Microsoft.NETCore.App` 패키지를 버전 `1.0.0`으로 고정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-125">If so, you should fix your `Microsoft.NETCore.App` package to version `1.0.0`.</span></span>  <span data-ttu-id="340e3-126">이것은 조정된 메타패키지이므로 패키지 종료도 1.0으로 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-126">Because this is a curated metapackage, its package closure is also fixed to 1.0.</span></span>

<span data-ttu-id="340e3-127">**당신은 [트리밍](../deploying/reducing-dependencies.md) 프로그램** `NETStandard.Library` **또는** `Microsoft.NETCore.App` **metapackage 종속성?**</span><span class="sxs-lookup"><span data-stu-id="340e3-127">**Are you [trimming](../deploying/reducing-dependencies.md) your** `NETStandard.Library` **or** `Microsoft.NETCore.App` **metapackage dependencies?**</span></span>

<span data-ttu-id="340e3-128">그렇다면 시작하는 메타패키지도 1.0으로 고정되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-128">If so, you should ensure that the metapackage you start with is fixed to 1.0.</span></span>  <span data-ttu-id="340e3-129">잘라낸 후 종속된 개별 패키지도 1.0으로 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-129">The individual packages you depend on after trimming are also fixed to 1.0.</span></span>

<span data-ttu-id="340e3-130">**외부에서 패키지에 따라 입니까는** `NETStandard.Library` **또는** `Microsoft.NETCore.App` **metapackages?**</span><span class="sxs-lookup"><span data-stu-id="340e3-130">**Are you depending on packages outside the** `NETStandard.Library` **or** `Microsoft.NETCore.App` **metapackages?**</span></span>

<span data-ttu-id="340e3-131">그렇다면 다른 종속성을 1.0으로 고정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-131">If so, you need to fix your other dependencies to 1.0.</span></span>  <span data-ttu-id="340e3-132">이 문서 뒤에 나오는 올바른 패키지 버전 및 빌드 번호를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="340e3-132">See the correct package versions and build numbers at the end of this article.</span></span>

### <a name="a-note-on-using-a-splat-string--when-versioning"></a><span data-ttu-id="340e3-133">버전 관리 시 스플랫 문자열(\*) 참고 사항</span><span class="sxs-lookup"><span data-stu-id="340e3-133">A note on using a splat string (\*) when versioning</span></span>

<span data-ttu-id="340e3-134">스플랫(\*) 문자열을 사용하는 버전 관리 패턴을 다음과 같이 조정했을 수 있습니다. `"System.Collections":"4.0.11-*"`</span><span class="sxs-lookup"><span data-stu-id="340e3-134">You may have adopted a versioning pattern which uses a splat (\*) string like this: `"System.Collections":"4.0.11-*"`.</span></span>

<span data-ttu-id="340e3-135">**이렇게 해서는 안 됩니다**.</span><span class="sxs-lookup"><span data-stu-id="340e3-135">**You should not do this**.</span></span>  <span data-ttu-id="340e3-136">스플랫 문자열을 사용하면 패키지가 다른 빌드에서 복원될 수 있으며, 이중 일부는 .NET Core 1.0보다 더 나아간 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-136">Using the splat string could result in restoring packages from different builds, some of which may be further along than .NET Core 1.0.</span></span>  <span data-ttu-id="340e3-137">이 경우 일부 패키지는 호환되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="340e3-137">This could then result in some packages being incompatible.</span></span>

## <a name="packages-and-version-numbers-organized-by-metapackage"></a><span data-ttu-id="340e3-138">메타패키지로 구성된 패키지 및 버전 번호</span><span class="sxs-lookup"><span data-stu-id="340e3-138">Packages and Version Numbers organized by Metapackage</span></span>

<span data-ttu-id="340e3-139">[.NET 표준 패키지 및 1.0에 대한 해당 버전을 나열합니다](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt).</span><span class="sxs-lookup"><span data-stu-id="340e3-139">[List of all .NET Standard packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt).</span></span>

<span data-ttu-id="340e3-140">[모든 런타임 패키지 및 1.0에 대한 해당 버전을 나열합니다](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt).</span><span class="sxs-lookup"><span data-stu-id="340e3-140">[List of all runtime packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt).</span></span>

<span data-ttu-id="340e3-141">[모든 .NET Core 응용 프로그램 패키지 및 1.0에 대한 해당 버전을 나열합니다](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt).</span><span class="sxs-lookup"><span data-stu-id="340e3-141">[List of all .NET Core application packages and their versions for 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt).</span></span>
