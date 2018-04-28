---
title: .NET Core로 이식 - 타사 종속성 분석
description: .NET Framework에서 .NET Core로 프로젝트를 이식하기 위해 타사 종속성을 분석하는 방법을 알아봅니다.
author: cartermp
ms.author: mairaw
ms.date: 02/15/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.workload:
- dotnetcore
ms.openlocfilehash: be8d5a60977c7863136a1661a60e3bf23c0eb93e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="analyze-your-third-party-dependencies"></a><span data-ttu-id="729ba-103">타사 종속성 분석</span><span class="sxs-lookup"><span data-stu-id="729ba-103">Analyze your third-party dependencies</span></span>

<span data-ttu-id="729ba-104">.NET Core 또는 .NET Standard에 코드를 이식하려는 경우 이식 프로세스의 첫 번째 단계는 타사 종속성을 이해하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-104">If you're looking to port your code to .NET Core or .NET Standard, the first step in the porting process is to understand your third-party dependencies.</span></span> <span data-ttu-id="729ba-105">타사 종속성은 [NuGet 패키지](#analyze-referenced-nuget-packages-on-your-project) 또는 프로젝트에서 참조 중인 [DLL](#analyze-dependencies-that-arent-nuget-packages)입니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-105">Third-party dependencies are either [NuGet packages](#analyze-referenced-nuget-packages-on-your-project) or [DLLs](#analyze-dependencies-that-arent-nuget-packages) you're referencing in your project.</span></span> <span data-ttu-id="729ba-106">각 종속성을 평가하고 .NET Core와 호환되지 않는 종속성에 대한 대체 계획을 개발합니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-106">Evaluate each dependency and develop a contingency plan for the dependencies that aren't compatible with .NET Core.</span></span> <span data-ttu-id="729ba-107">이 문서에서는 종속성이 .NET Core와 호환되는지 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-107">This article shows you how to determine if the dependency is compatible with .NET Core.</span></span>

## <a name="analyze-referenced-nuget-packages-in-your-project"></a><span data-ttu-id="729ba-108">프로젝트에서 참조된 NuGet 패키지 분석</span><span class="sxs-lookup"><span data-stu-id="729ba-108">Analyze referenced NuGet packages in your project</span></span>

<span data-ttu-id="729ba-109">프로젝트에서 NuGet 패키지를 참조하는 경우 .NET Core와 호환되는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-109">If you're referencing NuGet packages in your project, you need to verify if they're compatible with .NET Core.</span></span>
<span data-ttu-id="729ba-110">여기에는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-110">There are two ways to accomplish that:</span></span>

* <span data-ttu-id="729ba-111">[NuGet 패키지 탐색기 앱 사용](#analyze-nuget-packages-using-nuget-package-explorer)(가장 안정적인 방법)</span><span class="sxs-lookup"><span data-stu-id="729ba-111">[Using the NuGet Package Explorer app](#analyze-nuget-packages-using-nuget-package-explorer) (the most reliable method).</span></span>
* <span data-ttu-id="729ba-112">[nuget.org 사이트 사용](#analyze-nuget-packages-using-nugetorg)</span><span class="sxs-lookup"><span data-stu-id="729ba-112">[Using the nuget.org site](#analyze-nuget-packages-using-nugetorg).</span></span>

<span data-ttu-id="729ba-113">패키지를 분석한 후 .NET Core 및 대상 .NET Framework와 호환되지 않는 경우 [.NET Framework 호환 모드](#net-framework-compatibility-mode)가 이식 프로세스에 도움이 될 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-113">After analyzing the packages, if they're not compatible with .NET Core and only target .NET Framework, you can check if the [.NET Framework compatibility mode](#net-framework-compatibility-mode) can help with your porting process.</span></span>

### <a name="analyze-nuget-packages-using-nuget-package-explorer"></a><span data-ttu-id="729ba-114">NuGet 패키지 탐색기를 사용하여 NuGet 패키지 분석</span><span class="sxs-lookup"><span data-stu-id="729ba-114">Analyze NuGet packages using NuGet Package Explorer</span></span>

<span data-ttu-id="729ba-115">NuGet 패키지 자체는 플랫폼 관련 어셈블리를 포함하는 폴더 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-115">A NuGet package is itself a set of folders that contain platform-specific assemblies.</span></span> <span data-ttu-id="729ba-116">따라서 패키지 내에 호환되는 어셈블리를 포함하는 폴더인지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-116">So you need to check if there's a folder that contains a compatible assembly inside the package.</span></span>

<span data-ttu-id="729ba-117">NuGet 패키지 폴더를 검사하는 가장 쉬운 방법은 [NuGet 패키지 탐색기](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) 도구를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-117">The easiest way to inspect NuGet Package folders is to use the [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) tool.</span></span> <span data-ttu-id="729ba-118">설치한 후 다음 단계를 사용하여 폴더 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-118">After installing it, use the following steps to see the folder names:</span></span>

1. <span data-ttu-id="729ba-119">NuGet 패키지 탐색기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-119">Open the NuGet Package Explorer.</span></span>
2. <span data-ttu-id="729ba-120">**온라인 피드에서 패키지 열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-120">Click **Open package from online feed**.</span></span>
3. <span data-ttu-id="729ba-121">패키지의 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-121">Search for the name of the package.</span></span>
4. <span data-ttu-id="729ba-122">검색 결과에서 패키지 이름을 선택하고 **열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-122">Select the package name from the search results and click **open**.</span></span>
5. <span data-ttu-id="729ba-123">오른쪽에서 *lib* 폴더를 확장하고 폴더 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-123">Expand the *lib* folder on the right-hand side and look at folder names.</span></span>

<span data-ttu-id="729ba-124">다음 이름 중 하나를 사용하여 폴더를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-124">Look for a folder with any of the following names:</span></span>

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netstandard2.0
netcoreapp1.0
netcoreapp1.1
netcoreapp2.0
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

<span data-ttu-id="729ba-125">이러한 값은 [.NET Standard](../../standard/net-standard.md), .NET Core의 버전에 매핑되는 [TFM(대상 프레임워크 모니커)](../../standard/frameworks.md) 및 .NET Core와 호환되는 기존의 PCL(이식 가능한 클래스 라이브러리) 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-125">These values are the [Target Framework Monikers (TFMs)](../../standard/frameworks.md) that map to versions of the [.NET Standard](../../standard/net-standard.md), .NET Core, and traditional Portable Class Library (PCL) profiles that are compatible with .NET Core.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="729ba-126">패키지에서 지원하는 TFM을 살펴볼 때 호환되는 동안 `netcoreapp*`은 .NET Standard 프로젝트용이 아닌 .NET Core 프로젝트용입니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-126">When looking at the TFMs that a package supports, note that `netcoreapp*`, while compatible, is for .NET Core projects only and not for .NET Standard projects.</span></span>
> <span data-ttu-id="729ba-127">`netstandard*`가 아닌 `netcoreapp*`만을 대상으로 하는 라이브러리는 다른 .NET Core 앱에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-127">A library that only targets `netcoreapp*` and not `netstandard*` can only be consumed by other .NET Core apps.</span></span>

<span data-ttu-id="729ba-128">호환 가능한 .NET Core의 시험판에서 사용되는 일부 레거시 TFM도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-128">There are also some legacy TFMs used in pre-release versions of .NET Core that may also be compatible:</span></span>

```
dnxcore50
dotnet5.0
dotnet5.1
dotnet5.2
dotnet5.3
dotnet5.4
dotnet5.5
```

<span data-ttu-id="729ba-129">이러한 TFM은 코드와 호환될 수는 있지만 호환성이 보장되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-129">While these TFMs likely work with your code, there is no guarantee of compatibility.</span></span> <span data-ttu-id="729ba-130">이러한 TFM이 포함된 패키지는 시험판 .NET Core 패키지로 빌드된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-130">Packages with these TFMs were built with pre-release .NET Core packages.</span></span> <span data-ttu-id="729ba-131">이러한 TFM을 사용하여 패키지가 .NET Standard 기반으로 업데이트되는 경우를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-131">Take note of when (or if) packages using these TFMs are updated to be .NET Standard-based.</span></span>

> [!NOTE]
> <span data-ttu-id="729ba-132">기존 PCL 또는 시험판 .NET Core를 대상으로 하는 패키지를 사용하려면 프로젝트 파일에서 `PackageTargetFallback` MSBuild 요소를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-132">To use a package targeting a traditional PCL or pre-release .NET Core target, you must use the `PackageTargetFallback` MSBuild element in your project file.</span></span>
> <span data-ttu-id="729ba-133">이 MSBuild 요소에 대한 자세한 내용은 [`PackageTargetFallback`](../tools/csproj.md#packagetargetfallback)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="729ba-133">For more information about this MSBuild element, see [`PackageTargetFallback`](../tools/csproj.md#packagetargetfallback).</span></span>

### <a name="analyze-nuget-packages-using-nugetorg"></a><span data-ttu-id="729ba-134">nuget.org를 사용하여 NuGet 패키지 분석</span><span class="sxs-lookup"><span data-stu-id="729ba-134">Analyze NuGet packages using nuget.org</span></span>

<span data-ttu-id="729ba-135">또는 패키지 페이지의 **종속성** 섹션 아래의 [nuget.org](https://www.nuget.org/)에서 패키지가 지원하는 TFM을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-135">Alternatively, you can see the TFMs that each package supports on [nuget.org](https://www.nuget.org/) under the **Dependencies** section of the package page.</span></span>

<span data-ttu-id="729ba-136">사이트를 사용하는 것이 호환성을 확인하는 쉬운 방법이지만 **종속성** 정보를 모든 패키지에 대한 사이트에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-136">Although using the site is an easier method to verify the compatibility, **Dependencies** information is not available on the site for all packages.</span></span>

### <a name="net-framework-compatibility-mode"></a><span data-ttu-id="729ba-137">.NET Framework 호환 모드</span><span class="sxs-lookup"><span data-stu-id="729ba-137">.NET Framework compatibility mode</span></span>

<span data-ttu-id="729ba-138">NuGet 패키지를 분석한 후 대부분의 NuGet 패키지와 마찬가지로 .NET Framework만 대상으로 하는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-138">After analyzing the NuGet packages, you might find that they only target the .NET Framework, as most NuGet packages do.</span></span>

<span data-ttu-id="729ba-139">.NET Standard 2.0부터 .NET Framework 호환성 모드가 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-139">Starting with .NET Standard 2.0, the .NET Framework compatibility mode was introduced.</span></span> <span data-ttu-id="729ba-140">이 호환 모드에서는 .NET Standard 및 .NET Core 프로젝트에서 .NET Framework 라이브러리를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-140">This compatibility mode allows .NET Standard and .NET Core projects to reference .NET Framework libraries.</span></span> <span data-ttu-id="729ba-141">.NET Framework 라이브러리 참조는 라이브러리가 WPF(Windows Presentation Foundation) API를 사용하는 것처럼 모든 프로젝트에 대해 작동하지 않지만 많은 이식 시나리오를 차단 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-141">Referencing .NET Framework libraries doesn't work for all projects, such as if the library uses Windows Presentation Foundation (WPF) APIs, but it does unblock many porting scenarios.</span></span>

<span data-ttu-id="729ba-142">프로젝트에서 .NET Framework를 대상으로 하는 NuGet 패키지를 참조하는 경우(예:[Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections)) 다음 예제와 유사한 패키지 대체 경고([NU1701](/nuget/reference/errors-and-warnings#nu1701))를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-142">When you reference NuGet packages that target the .NET Framework in your project, such as [Huitian.PowerCollections](https://www.nuget.org/packages/Huitian.PowerCollections), you get a package fallback warning ([NU1701](/nuget/reference/errors-and-warnings#nu1701)) similar to the following example:</span></span>

`NU1701: Package ‘Huitian.PowerCollections 1.0.0’ was restored using ‘.NETFramework,Version=v4.6.1’ instead of the project target framework ‘.NETStandard,Version=v2.0’. This package may not be fully compatible with your project.`

<span data-ttu-id="729ba-143">해당 경고는 패키지를 추가하고 해당 패키지를 프로젝트와 테스트하도록 빌드할 때마다 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-143">That warning is displayed when you add the package and every time you build to make sure you test that package with your project.</span></span> <span data-ttu-id="729ba-144">프로젝트가 예상대로 작동하는 경우 Visual Studio에서 패키지 속성을 편집하거나 즐겨 찾는 코드 편집기에서 프로젝트 파일을 수동으로 편집하여 해당 경고를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-144">If your project is working as expected, you can suppress that warning by editing the package properties in Visual Studio or by manually editing the project file in your favorite code editor.</span></span>

<span data-ttu-id="729ba-145">프로젝트 파일을 편집하여 경고를 제거하려면 경고를 제거하려는 패키지에 대한 `PackageReference` 항목을 찾고 `NoWarn` 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-145">To suppress the warning by editing the project file, find the `PackageReference` entry for the package you want to suppress the warning for and add the `NoWarn` attribute.</span></span> <span data-ttu-id="729ba-146">`NoWarn` 특성은 모든 경고 ID의 쉼표로 구분된 목록을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-146">The `NoWarn` attribute accepts a comma-separated list of all the warning IDs.</span></span> <span data-ttu-id="729ba-147">다음 예제는 프로젝트 파일을 수동으로 편집하여 `Huitian.PowerCollections` 프로젝트에 대한 `NU1701` 경고를 제거하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-147">The following example shows how to suppress the `NU1701` warning for the `Huitian.PowerCollections` package by editing your project file manually:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Huitian.PowerCollections" Version="1.0.0" NoWarn="NU1701" />
</ItemGroup>
```

<span data-ttu-id="729ba-148">Visual Studio에서 컴파일러 경고를 제거하는 방법에 대한 자세한 내용은 [NuGet 패키지에 대한 경고 표시 안 함](/visualstudio/ide/how-to-suppress-compiler-warnings#suppressing-warnings-for-nuget-packages)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="729ba-148">For more information on how to suppress compiler warnings in Visual Studio, see [Suppressing warnings for NuGet packages](/visualstudio/ide/how-to-suppress-compiler-warnings#suppressing-warnings-for-nuget-packages).</span></span>

### <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a><span data-ttu-id="729ba-149">NuGet 패키지 종속성이 .NET Core에서 실행되지 않는 경우 수행할 작업</span><span class="sxs-lookup"><span data-stu-id="729ba-149">What to do when your NuGet package dependency doesn't run on .NET Core</span></span>

<span data-ttu-id="729ba-150">종속된 NuGet 패키지가 .NET Core에서 실행되지 않을 경우 수행할 수 있는 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-150">There are a few things you can do if a NuGet package you depend on doesn't run on .NET Core:</span></span>

1. <span data-ttu-id="729ba-151">프로젝트가 오픈 소스이고 GitHub 같은 곳에 호스트된 경우 개발자가 직접 참여하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-151">If the project is open source and hosted somewhere like GitHub, you can engage the developers directly.</span></span>
2. <span data-ttu-id="729ba-152">[nuget.org](https://www.nuget.org/)에서 작성자에게 직접 문의할 수 있습니다. 패키지를 검색하고 패키지 페이지의 왼쪽에서 **연락처 소유자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-152">You can contact the author directly on [nuget.org](https://www.nuget.org/). Search for the package and click **Contact Owners** on the left-hand side of the package's page.</span></span>
3. <span data-ttu-id="729ba-153">사용하던 패키지와 동일한 작업을 수행하는 .NET Core에서 실행되는 다른 패키지를 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-153">You can search for another package that runs on .NET Core that accomplishes the same task as the package you were using.</span></span>
4. <span data-ttu-id="729ba-154">패키지가 수행하고 있는 코드를 직접 작성해볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-154">You can attempt to write the code the package was doing yourself.</span></span>
5. <span data-ttu-id="729ba-155">적어도 패키지의 호환 버전을 사용할 수 있을 때까지는 앱의 기능을 변경하여 패키지에 대한 종속성을 없앨 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-155">You could eliminate the dependency on the package by changing the functionality of your app, at least until a compatible version of the package becomes available.</span></span>

<span data-ttu-id="729ba-156">오픈 소스 프로젝트 유지 관리자와 NuGet 패키지 게시자는 종종 지원자입니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-156">Remember that open-source project maintainers and NuGet package publishers are often volunteers.</span></span> <span data-ttu-id="729ba-157">지정된 도메인을 중요하게 여기기 때문에 참여하고, 자유롭게 수행하고, 종종 다른 주간 작업을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-157">They contribute because they care about a given domain, do it for free, and often have a different daytime job.</span></span> <span data-ttu-id="729ba-158">따라서 .NET Core 지원에 대해 문의하는 경우 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-158">So be mindful of that when contacting them to ask for .NET Core support.</span></span>

<span data-ttu-id="729ba-159">위 방법으로 문제를 해결할 수 없는 경우 나중에 .NET Core로 이식해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-159">If you can't resolve your issue with any of the above, you may have to port to .NET Core at a later date.</span></span>

<span data-ttu-id="729ba-160">.NET 팀은 .NET Core를 지원하기 위해 어떤 라이브러리가 가장 중요한지 알고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-160">The .NET Team would like to know which libraries are the most important to support with .NET Core.</span></span> <span data-ttu-id="729ba-161">사용하고 싶은 라이브러리에 대해 dotnet@microsoft.com으로 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-161">You can send an email to dotnet@microsoft.com about the libraries you'd like to use.</span></span>

## <a name="analyze-dependencies-that-arent-nuget-packages"></a><span data-ttu-id="729ba-162">NuGet 패키지가 아닌 종속성 분석</span><span class="sxs-lookup"><span data-stu-id="729ba-162">Analyze dependencies that aren't NuGet packages</span></span>

<span data-ttu-id="729ba-163">파일 시스템의 DLL처럼, NuGet 패키지가 아닌 종속성이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-163">You may have a dependency that isn't a NuGet package, such as a DLL in the file system.</span></span> <span data-ttu-id="729ba-164">해당 종속성의 이식 가능성을 확인하는 유일한 방법은 [.NET 이식성 분석기](https://github.com/Microsoft/dotnet-apiport)를 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-164">The only way to determine the portability of that dependency is to run the [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport) tool.</span></span> <span data-ttu-id="729ba-165">도구는 .NET Framework를 대상으로 하는 어셈블리를 분석하고 .NET Core와 같은 다른 .NET 플랫폼으로 이식할 수 없는 API를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-165">The tool can analyze assemblies that target the .NET Framework and identify APIs that aren't portable to other .NET platforms such as .NET Core.</span></span> <span data-ttu-id="729ba-166">콘솔 응용 프로그램 또는 [Visual Studio 확장](../../standard/analyzers/portability-analyzer.md)으로 도구를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-166">You can run the tool as a console application or as a [Visual Studio extension](../../standard/analyzers/portability-analyzer.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="729ba-167">다음 단계</span><span class="sxs-lookup"><span data-stu-id="729ba-167">Next steps</span></span>

<span data-ttu-id="729ba-168">라이브러리를 이식하려는 경우 [라이브러리 이식](libraries.md)을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="729ba-168">If you're porting a library, check out [Porting your Libraries](libraries.md).</span></span>
