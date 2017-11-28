---
title: ".NET Core로 이식 - 타사 종속성 분석"
description: ".NET Core로 이식 - 타사 종속성 분석"
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: b446e9e0-72f6-48f6-92c6-70ad0ce3f86a
ms.openlocfilehash: a074978f2817abafa7b8a9fefe7c67c9c52195b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="porting-to-net-core---analyzing-your-third-party-party-dependencies"></a><span data-ttu-id="9002e-104">.NET Core로 이식 - 타사 종속성 분석</span><span class="sxs-lookup"><span data-stu-id="9002e-104">Porting to .NET Core - Analyzing your Third-Party Party Dependencies</span></span>

<span data-ttu-id="9002e-105">이식 프로세스의 첫 번째 단계는 타사 종속성을 이해하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-105">The first step in the porting process is to understand your third party dependencies.</span></span>  <span data-ttu-id="9002e-106">.NET Core에서 아직 실행되지 않는 것이 무엇인지를 파악하고 이에 대한 대체 계획을 개발해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-106">You need to figure out which of them, if any, don't yet run on .NET Core, and develop a contingency plan for those which don't run on .NET Core.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9002e-107">필수 조건</span><span class="sxs-lookup"><span data-stu-id="9002e-107">Prerequisites</span></span>

<span data-ttu-id="9002e-108">이 문서에서는 사용자가 Windows 및 Visual Studio를 사용하며 .NET Framework에서 실행되는 코드를 가지고 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-108">This article will assume you are using Windows and Visual Studio, and that you have code which runs on the .NET Framework today.</span></span>

## <a name="analyzing-nuget-packages"></a><span data-ttu-id="9002e-109">NuGet 패키지 분석</span><span class="sxs-lookup"><span data-stu-id="9002e-109">Analyzing NuGet Packages</span></span>

<span data-ttu-id="9002e-110">이식성에 대한 NuGet 패키지 분석은 매우 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-110">Analyzing NuGet packages for portability is very easy.</span></span>  <span data-ttu-id="9002e-111">NuGet 패키지는 플랫폼별 어셈블리를 포함하는 폴더의 집합 자체이므로, .NET Core 어셈블리를 포함하는 폴더가 있는지만 확인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-111">Because a NuGet package is itself a set of folders which contain platform-specific assemblies, all you have to do is check to see if there is a folder which contains a .NET Core assembly.</span></span>

<span data-ttu-id="9002e-112">NuGet 패키지 폴더 검사는 [NuGet 패키지 탐색기](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) 도구로 수행하는 것이 가장 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-112">Inspecting NuGet Package folders is easiest with the [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) tool.</span></span>  <span data-ttu-id="9002e-113">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-113">Here's how to do it.</span></span>

1. <span data-ttu-id="9002e-114">NuGet 패키지 탐색기를 다운로드하여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-114">Download and open the NuGet Package Explorer.</span></span>
2. <span data-ttu-id="9002e-115">"온라인 피드에서 패키지 열기"를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-115">Click "Open package from online feed".</span></span>
3. <span data-ttu-id="9002e-116">패키지의 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-116">Search for the name of the package.</span></span>
4. <span data-ttu-id="9002e-117">오른쪽에서 "lib" 폴더를 확장하고 폴더 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-117">Expand the "lib" folder on the right-hand side and look at folder names.</span></span>

<span data-ttu-id="9002e-118">패키지에 대한 페이지의 **종속성** 섹션에 있는 [nuget.org](https://www.nuget.org/)에서 패키지가 지원하는 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-118">You can also see what a package supports on [nuget.org](https://www.nuget.org/) under the **Dependencies** section of the page for that package.</span></span>

<span data-ttu-id="9002e-119">어떤 경우든 [nuget.org](https://www.nuget.org/)에서 다음 이름의 폴더 또는 항목을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-119">In either case, you'll need to look for a folder or entry on [nuget.org](https://www.nuget.org/) with any of the following names:</span></span>

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netcoreapp1.0
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

<span data-ttu-id="9002e-120">[.NET 표준](../../standard/net-standard.md)의 버전에 매핑되는 TFM(대상 프레임워크 모니커) 및 .NET Core와 호환되는 기존의 PCL(이식 가능한 클래스 라이브러리) 프로필입니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-120">These are the Target Framework Monikers (TFM) which map to versions of the [.NET Standard](../../standard/net-standard.md) and traditional Portable Class Library (PCL) profiles which are compatible with .NET Core.</span></span>  <span data-ttu-id="9002e-121">호환되는 `netcoreapp1.0`은 응용 프로그램용이며 라이브러리용이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-121">Note that `netcoreapp1.0`, while compatible, is for applications and not libraries.</span></span>  <span data-ttu-id="9002e-122">`netcoreapp1.0` 기반 라이브러리를 사용하는 것에는 문제가 없지만, 해당 라이브러리는 다른 `netcoreapp1.0` 응용 프로그램이 사용하는 것 *이외의* 용도가 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-122">Although there's nothing wrong with using a library which is `netcoreapp1.0`-based, that library may not be intended for anything *other* than consumption by other `netcoreapp1.0` applications.</span></span>

<span data-ttu-id="9002e-123">호환 가능한 .NET Core의 시험판에서 사용되는 일부 레거시 TFM도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-123">There are also some legacy TFMs used in pre-release versions of .NET Core that may also be compatible:</span></span>

```
dnxcore50
dotnet5.0
dotnet5.1
dotnet5.2
dotnet5.3
dotnet5.4
dotnet5.5
```

<span data-ttu-id="9002e-124">**이러한 것도 코드와 호환될 수는 있지만 호환성이 보장되지는 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="9002e-124">**While these will likely work with your code, there is no guarantee of compatibility**.</span></span>  <span data-ttu-id="9002e-125">이러한 TFM이 포함된 패키지는 시험판 .NET Core 패키지로 빌드된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-125">Packages with these TFMs were built with pre-release .NET Core packages.</span></span>  <span data-ttu-id="9002e-126">이러한 패키지를 `netstandard` 기반으로 업데이트할 경우에는 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-126">Take note of when (or if) packages like this are updated to be `netstandard`-based.</span></span>

> [!NOTE]
> <span data-ttu-id="9002e-127">기존 PCL 또는 시험판 .NET Core를 대상으로 하는 패키지를 사용하려면 `project.json` 파일에서 `imports` 지시문을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-127">To use a package targeting a traditional PCL or pre-release .NET Core target, you must use the `imports` directive in your `project.json` file.</span></span>

### <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a><span data-ttu-id="9002e-128">NuGet 패키지 종속성이 .NET Core에서 실행되지 않는 경우 수행할 작업</span><span class="sxs-lookup"><span data-stu-id="9002e-128">What to do when your NuGet package dependency doesn't run on .NET Core</span></span>

<span data-ttu-id="9002e-129">종속된 NuGet 패키지가 .NET Core에서 실행되지 않을 경우 수행할 수 있는 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-129">There are a few things you can do if a NuGet package you depend on won't run on .NET Core.</span></span>

1. <span data-ttu-id="9002e-130">프로젝트가 오픈 소스이고 GitHub 같은 곳에 호스트된 경우 개발자가 직접 참여하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-130">If the project is open source and hosted somewhere like GitHub, you can engage the developer(s) directly.</span></span>
2. <span data-ttu-id="9002e-131">패키지를 검색하고 패키지 페이지의 왼쪽에서 "연락처 소유자"를 클릭하여 [nuget.org](https://www.nuget.org/)에서 작성자에게 직접 연락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-131">You can contact the author directly on [nuget.org](https://www.nuget.org/) by searching for the package and clicking "Contact Owners" on the left hand side of the package's page.</span></span>
3. <span data-ttu-id="9002e-132">사용하던 패키지와 동일한 작업을 수행하는, .NET Core에서 실행되는 다른 패키지를 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-132">You can look for another package that runs on .NET Core which accomplishes the same task as the package you were using.</span></span>
4. <span data-ttu-id="9002e-133">패키지가 수행하고 있는 코드를 직접 작성해볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-133">You can attempt to write the code the package was doing yourself.</span></span>
5. <span data-ttu-id="9002e-134">적어도 패키지의 호환 버전을 사용할 수 있을 때까지는 앱의 기능을 변경하여 패키지에 대한 종속성을 없앨 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-134">You could eliminate the dependency on the package by changing the functionality of your app, at least until a compatible version of the package becomes available.</span></span>

<span data-ttu-id="9002e-135">오픈 소스 프로젝트 유지 관리자 및 NuGet 패키지 게시자는 특정 도메인을 무료로 관리하며 낮에는 다른 업무가 있는 지원자인 경우가 많다는 점에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="9002e-135">Please remember that open source project maintainers and NuGet package publishers are often volunteers who contribute because they care about a given domain, do it for free, and often have a different daytime job.</span></span> <span data-ttu-id="9002e-136">연락되는 경우 .NET Core 지원을 요청하기 전에 라이브러리에 대한 긍정적인 문장으로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-136">If you do reach out, you might start with a positive statement about the library before asking about .NET Core support.</span></span>

<span data-ttu-id="9002e-137">위 방법으로 문제를 해결할 수 없는 경우 나중에 .NET Core로 이식해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-137">If you're unable to resolve your issue with any of the above, you may have to port to .NET Core at a later date.</span></span>

<span data-ttu-id="9002e-138">.NET 팀은 다음에 .NET Core를 지원하기 위해 어떤 라이브러리가 가장 중요한지 알고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-138">The .NET Team would like to know which libraries are the most important to support next with .NET Core.</span></span> <span data-ttu-id="9002e-139">또한 사용하고 싶은 라이브러리에 대해 dotnet@microsoft.com으로 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-139">You can also send us mail at dotnet@microsoft.com about the libraries you'd like to use.</span></span>

## <a name="analyzing-dependencies-which-arent-nuget-packages"></a><span data-ttu-id="9002e-140">NuGet 패키지가 아닌 종속성 분석</span><span class="sxs-lookup"><span data-stu-id="9002e-140">Analyzing Dependencies which aren't NuGet Packages</span></span>

<span data-ttu-id="9002e-141">파일 시스템의 DLL처럼, NuGet 패키지가 아닌 종속성이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-141">You may have a dependency that isn't a NuGet package, such as a DLL in the filesystem.</span></span>  <span data-ttu-id="9002e-142">해당 종속성의 이식 가능성을 확인하는 유일한 방법은 [ApiPort 도구](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/)를 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-142">The only way to determine the portability of that dependency is to run the [ApiPort tool](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9002e-143">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9002e-143">Next steps</span></span>

<span data-ttu-id="9002e-144">라이브러리를 이식하려는 경우 [라이브러리 이식](libraries.md)을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9002e-144">If you're porting a library, check out [Porting your Libraries](libraries.md).</span></span>
