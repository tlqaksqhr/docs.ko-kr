---
title: "대상 프레임워크"
description: ".NET Core 앱 및 라이브러리의 대상 프레임워크에 대해 알아봅니다."
keywords: ".NET, .NET Core, 프레임워크, TFM"
author: richlander
ms.author: mairaw
ms.date: 08/25/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 6ef56a2e-593d-497b-925a-1e25bb6df2e6
ms.translationtype: HT
ms.sourcegitcommit: 18b2f7a1c0857abb5f7e09a39ca120b521ba4ddc
ms.openlocfilehash: 7f25cdd52cf5249d3b201978eacb98aaa4a74fa9
ms.contentlocale: ko-kr
ms.lasthandoff: 08/25/2017

---

# <a name="target-frameworks"></a><span data-ttu-id="97a45-104">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="97a45-104">Target frameworks</span></span>

<span data-ttu-id="97a45-105">앱 또는 라이브러리에서 프레임워크를 대상으로 지정하면 앱 또는 라이브러리에서 사용할 수 있도록 하려는 API 집합을 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-105">When you target a framework in an app or library, you're specifying the set of APIs that you'd like to make available to the app or library.</span></span> <span data-ttu-id="97a45-106">TFM(대상 프레임워크 모니터)을 사용하여 프로젝트 파일에서 대상 프레임워크를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-106">You specify the target framework in your project file using Target Framework Monikers (TFMs).</span></span>

<span data-ttu-id="97a45-107">앱 또는 라이브러리는 [.NET Standard](~/docs/standard/net-standard.md) 버전을 대상으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-107">An app or library can target a version of [.NET Standard](~/docs/standard/net-standard.md).</span></span> <span data-ttu-id="97a45-108">.NET Standard 버전은 모든 .NET 구현에서 표준화된 API 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-108">.NET Standard versions represent standardized sets of APIs across all .NET implementations.</span></span> <span data-ttu-id="97a45-109">예를 들어 라이브러리는 .NET Standard 1.6을 대상으로 하고 동일한 코드베이스를 사용하는 .NET Core 및 .NET Framework에서 작동하는 API에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-109">For example, a library can target .NET Standard 1.6 and gain access to APIs that function across .NET Core and .NET Framework using the same codebase.</span></span>

<span data-ttu-id="97a45-110">앱 또는 라이브러리는 특정 .NET 구현을 대상으로 지정하여 구현 관련 API에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-110">An app or library can also target a specific .NET implementation to gain access to implementation-specific APIs.</span></span> <span data-ttu-id="97a45-111">예를 들어 Xamarin.iOS(예: `Xamarin.iOS10`)를 대상으로 하는 앱은 Xamarin에서 제공하는 iOS 10용 iOS API 래퍼에 액세스하고, UWP(유니버설 Windows 플랫폼, `uap10.0`)를 대상으로 하는 앱은 Windows 10을 실행하는 장치에 대해 컴파일하는 API에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-111">For example, an app that targets Xamarin.iOS (for example, `Xamarin.iOS10`) gets access to Xamarin-provided iOS API wrappers for iOS 10, or an app that targets the Universal Windows Platform (UWP, `uap10.0`) has access to APIs that compile for devices that run Windows 10.</span></span>

<span data-ttu-id="97a45-112">일부 대상 프레임워크(예: .NET Framework)에서 API는 프레임워크가 시스템에 설치하는 어셈블리에 의해 정의되고 응용 프로그램 프레임워크 API(예: ASP.NET)를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-112">For some target frameworks (for example, the .NET Framework), the APIs are defined by the assemblies that the framework installs on a system and may include application framework APIs (for example, ASP.NET).</span></span>

<span data-ttu-id="97a45-113">패키지 기반 대상 프레임워크(예: .NET Standard 및 .NET Core)에서 API는 앱이나 라이브러리에 포함된 패키지에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-113">For package-based target frameworks (for example, .NET Standard and .NET Core), the APIs are defined by the packages included in the app or library.</span></span> <span data-ttu-id="97a45-114">*메타패키지*는 고유한 콘텐츠는 없지만 종속성(다른 패키지) 목록인 NuGet 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-114">A *metapackage* is a NuGet package that has no content of its own but is a list of dependencies (other packages).</span></span> <span data-ttu-id="97a45-115">NuGet 패키지 기반 대상 프레임워크는 함께 모여 프레임워크를 구성하는 모든 패키지를 참조하는 메타패키지를 암시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-115">A NuGet package-based target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

## <a name="latest-target-framework-versions"></a><span data-ttu-id="97a45-116">최신 대상 프레임워크 버전</span><span class="sxs-lookup"><span data-stu-id="97a45-116">Latest target framework versions</span></span>

<span data-ttu-id="97a45-117">다음 표에서는 가장 일반적인 대상 프레임워크, 프레임워크가 참조되는 방법 및 프레임워크에서 구현하는 [.NET Standard](~/docs/standard/net-standard.md)의 버전을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-117">The following table defines the most common target frameworks, how they're referenced, and which version of the [.NET Standard](~/docs/standard/net-standard.md) they implement.</span></span> <span data-ttu-id="97a45-118">이러한 대상 프레임워크 버전은 안정적인 최신 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-118">These target framework versions are the latest stable versions.</span></span> <span data-ttu-id="97a45-119">시험판 버전은 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-119">Pre-release versions aren't shown.</span></span> <span data-ttu-id="97a45-120">TFM(대상 프레임워크 모니커)은 .NET 앱 또는 라이브러리의 대상 프레임워크를 지정하기 위해 표준화된 토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-120">A Target Framework Moniker (TFM) is a standardized token format for specifying the target framework of a .NET app or library.</span></span> 

| <span data-ttu-id="97a45-121">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="97a45-121">Target Framework</span></span>      | <span data-ttu-id="97a45-122">최신 버전</span><span class="sxs-lookup"><span data-stu-id="97a45-122">Latest Version</span></span> | <span data-ttu-id="97a45-123">TFM(대상 프레임워크 모니커)</span><span class="sxs-lookup"><span data-stu-id="97a45-123">Target Framework Moniker (TFM)</span></span> | <span data-ttu-id="97a45-124">.NET 표준 버전</span><span class="sxs-lookup"><span data-stu-id="97a45-124">.NET Standard Version</span></span> | <span data-ttu-id="97a45-125">Metapackage</span><span class="sxs-lookup"><span data-stu-id="97a45-125">Metapackage</span></span> |
| :-------------------: | :------------: | :----------------------------: | :-------------------: | :---------: |
| <span data-ttu-id="97a45-126">.NET 표준</span><span class="sxs-lookup"><span data-stu-id="97a45-126">.NET Standard</span></span>         | <span data-ttu-id="97a45-127">2.0.0</span><span class="sxs-lookup"><span data-stu-id="97a45-127">2.0.0</span></span>          | <span data-ttu-id="97a45-128">netstandard2.0</span><span class="sxs-lookup"><span data-stu-id="97a45-128">netstandard2.0</span></span>                 | <span data-ttu-id="97a45-129">N/A</span><span class="sxs-lookup"><span data-stu-id="97a45-129">N/A</span></span>                   | [<span data-ttu-id="97a45-130">NETStandard.Library</span><span class="sxs-lookup"><span data-stu-id="97a45-130">NETStandard.Library</span></span>](https://www.nuget.org/packages/NETStandard.Library) |
| <span data-ttu-id="97a45-131">.NET Core 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="97a45-131">.NET Core Application</span></span> | <span data-ttu-id="97a45-132">2.0.0</span><span class="sxs-lookup"><span data-stu-id="97a45-132">2.0.0</span></span>          | <span data-ttu-id="97a45-133">netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="97a45-133">netcoreapp2.0</span></span>                  | <span data-ttu-id="97a45-134">2.0</span><span class="sxs-lookup"><span data-stu-id="97a45-134">2.0</span></span>                   | [<span data-ttu-id="97a45-135">Microsoft.NETCore.App</span><span class="sxs-lookup"><span data-stu-id="97a45-135">Microsoft.NETCore.App</span></span>](https://www.nuget.org/packages/Microsoft.NETCore.App) |
| <span data-ttu-id="97a45-136">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="97a45-136">.NET Framework</span></span>        | <span data-ttu-id="97a45-137">4.7</span><span class="sxs-lookup"><span data-stu-id="97a45-137">4.7</span></span>            | <span data-ttu-id="97a45-138">net47</span><span class="sxs-lookup"><span data-stu-id="97a45-138">net47</span></span>                          | <span data-ttu-id="97a45-139">1.5</span><span class="sxs-lookup"><span data-stu-id="97a45-139">1.5</span></span>                   | <span data-ttu-id="97a45-140">N/A</span><span class="sxs-lookup"><span data-stu-id="97a45-140">N/A</span></span> |

## <a name="supported-target-framework-versions"></a><span data-ttu-id="97a45-141">지원되는 대상 프레임워크 버전</span><span class="sxs-lookup"><span data-stu-id="97a45-141">Supported target framework versions</span></span>

<span data-ttu-id="97a45-142">대상 프레임워크는 일반적으로 TFM에서 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-142">A target framework is typically referenced by a TFM.</span></span> <span data-ttu-id="97a45-143">다음 표에서는 .NET Core SDK 및 NuGet 클라이언트에서 지원되는 대상 프레임워크를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-143">The following table shows the target frameworks supported by the .NET Core SDK and the NuGet client.</span></span> <span data-ttu-id="97a45-144">일치하는 항목은 대괄호 내에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-144">Equivalents are shown within brackets.</span></span> <span data-ttu-id="97a45-145">예를 들어 `win81`은 `netcore451`과 일치하는 TFM입니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-145">For example, `win81` is an equivalent TFM to `netcore451`.</span></span>

| <span data-ttu-id="97a45-146">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="97a45-146">Target Framework</span></span>           | <span data-ttu-id="97a45-147">TFM</span><span class="sxs-lookup"><span data-stu-id="97a45-147">TFM</span></span> |
| -------------------------- | --- |
| <span data-ttu-id="97a45-148">.NET 표준</span><span class="sxs-lookup"><span data-stu-id="97a45-148">.NET Standard</span></span>              | <span data-ttu-id="97a45-149">netstandard1.0</span><span class="sxs-lookup"><span data-stu-id="97a45-149">netstandard1.0</span></span><br><span data-ttu-id="97a45-150">netstandard1.1</span><span class="sxs-lookup"><span data-stu-id="97a45-150">netstandard1.1</span></span><br><span data-ttu-id="97a45-151">netstandard1.2</span><span class="sxs-lookup"><span data-stu-id="97a45-151">netstandard1.2</span></span><br><span data-ttu-id="97a45-152">netstandard1.3</span><span class="sxs-lookup"><span data-stu-id="97a45-152">netstandard1.3</span></span><br><span data-ttu-id="97a45-153">netstandard1.4</span><span class="sxs-lookup"><span data-stu-id="97a45-153">netstandard1.4</span></span><br><span data-ttu-id="97a45-154">netstandard1.5</span><span class="sxs-lookup"><span data-stu-id="97a45-154">netstandard1.5</span></span><br><span data-ttu-id="97a45-155">netstandard1.6</span><span class="sxs-lookup"><span data-stu-id="97a45-155">netstandard1.6</span></span><br><span data-ttu-id="97a45-156">netstandard2.0</span><span class="sxs-lookup"><span data-stu-id="97a45-156">netstandard2.0</span></span> |
| <span data-ttu-id="97a45-157">.NET Core</span><span class="sxs-lookup"><span data-stu-id="97a45-157">.NET Core</span></span>                  | <span data-ttu-id="97a45-158">netcoreapp1.0</span><span class="sxs-lookup"><span data-stu-id="97a45-158">netcoreapp1.0</span></span><br><span data-ttu-id="97a45-159">netcoreapp1.1</span><span class="sxs-lookup"><span data-stu-id="97a45-159">netcoreapp1.1</span></span><br><span data-ttu-id="97a45-160">netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="97a45-160">netcoreapp2.0</span></span> |
| <span data-ttu-id="97a45-161">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="97a45-161">.NET Framework</span></span>             | <span data-ttu-id="97a45-162">net11</span><span class="sxs-lookup"><span data-stu-id="97a45-162">net11</span></span><br><span data-ttu-id="97a45-163">net20</span><span class="sxs-lookup"><span data-stu-id="97a45-163">net20</span></span><br><span data-ttu-id="97a45-164">net35</span><span class="sxs-lookup"><span data-stu-id="97a45-164">net35</span></span><br><span data-ttu-id="97a45-165">net40</span><span class="sxs-lookup"><span data-stu-id="97a45-165">net40</span></span><br><span data-ttu-id="97a45-166">net403</span><span class="sxs-lookup"><span data-stu-id="97a45-166">net403</span></span><br><span data-ttu-id="97a45-167">net45</span><span class="sxs-lookup"><span data-stu-id="97a45-167">net45</span></span><br><span data-ttu-id="97a45-168">net451</span><span class="sxs-lookup"><span data-stu-id="97a45-168">net451</span></span><br><span data-ttu-id="97a45-169">net452</span><span class="sxs-lookup"><span data-stu-id="97a45-169">net452</span></span><br><span data-ttu-id="97a45-170">net46</span><span class="sxs-lookup"><span data-stu-id="97a45-170">net46</span></span><br><span data-ttu-id="97a45-171">net461</span><span class="sxs-lookup"><span data-stu-id="97a45-171">net461</span></span><br><span data-ttu-id="97a45-172">net462</span><span class="sxs-lookup"><span data-stu-id="97a45-172">net462</span></span><br><span data-ttu-id="97a45-173">net47</span><span class="sxs-lookup"><span data-stu-id="97a45-173">net47</span></span> |
| <span data-ttu-id="97a45-174">Windows 스토어</span><span class="sxs-lookup"><span data-stu-id="97a45-174">Windows Store</span></span>              | <span data-ttu-id="97a45-175">netcore [netcore45]</span><span class="sxs-lookup"><span data-stu-id="97a45-175">netcore [netcore45]</span></span><br><span data-ttu-id="97a45-176">netcore45 [win] [win8]</span><span class="sxs-lookup"><span data-stu-id="97a45-176">netcore45 [win] [win8]</span></span><br><span data-ttu-id="97a45-177">netcore451 [win81]</span><span class="sxs-lookup"><span data-stu-id="97a45-177">netcore451 [win81]</span></span> |
| <span data-ttu-id="97a45-178">.NET Micro Framework</span><span class="sxs-lookup"><span data-stu-id="97a45-178">.NET Micro Framework</span></span>       | <span data-ttu-id="97a45-179">netmf</span><span class="sxs-lookup"><span data-stu-id="97a45-179">netmf</span></span> |
| <span data-ttu-id="97a45-180">Silverlight</span><span class="sxs-lookup"><span data-stu-id="97a45-180">Silverlight</span></span>                | <span data-ttu-id="97a45-181">sl4</span><span class="sxs-lookup"><span data-stu-id="97a45-181">sl4</span></span><br><span data-ttu-id="97a45-182">sl5</span><span class="sxs-lookup"><span data-stu-id="97a45-182">sl5</span></span> |
| <span data-ttu-id="97a45-183">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="97a45-183">Windows Phone</span></span>              | <span data-ttu-id="97a45-184">wp [wp7]</span><span class="sxs-lookup"><span data-stu-id="97a45-184">wp [wp7]</span></span><br><span data-ttu-id="97a45-185">wp7</span><span class="sxs-lookup"><span data-stu-id="97a45-185">wp7</span></span><br><span data-ttu-id="97a45-186">wp75</span><span class="sxs-lookup"><span data-stu-id="97a45-186">wp75</span></span><br><span data-ttu-id="97a45-187">wp8</span><span class="sxs-lookup"><span data-stu-id="97a45-187">wp8</span></span><br><span data-ttu-id="97a45-188">wp81</span><span class="sxs-lookup"><span data-stu-id="97a45-188">wp81</span></span><br><span data-ttu-id="97a45-189">wpa81</span><span class="sxs-lookup"><span data-stu-id="97a45-189">wpa81</span></span> |
| <span data-ttu-id="97a45-190">범용 Windows 플랫폼</span><span class="sxs-lookup"><span data-stu-id="97a45-190">Universal Windows Platform</span></span> | <span data-ttu-id="97a45-191">uap [uap10.0]</span><span class="sxs-lookup"><span data-stu-id="97a45-191">uap [uap10.0]</span></span><br><span data-ttu-id="97a45-192">uap10.0 [win10] [netcore50]</span><span class="sxs-lookup"><span data-stu-id="97a45-192">uap10.0 [win10] [netcore50]</span></span> |

## <a name="how-to-specify-target-frameworks"></a><span data-ttu-id="97a45-193">대상 프레임워크를 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="97a45-193">How to specify target frameworks</span></span>

<span data-ttu-id="97a45-194">대상 프레임워크는 프로젝트 파일에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-194">Target frameworks are specified in your project file.</span></span> <span data-ttu-id="97a45-195">단일 대상 프레임워크를 지정하는 경우 **TargetFramework** 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-195">When a single target framework is specified, use the **TargetFramework** element.</span></span> <span data-ttu-id="97a45-196">다음 콘솔 앱 프로젝트 파일에서는 .NET Core 2.0을 대상으로 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-196">The following console app project file demonstrates how to target .NET Core 2.0:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="97a45-197">여러 대상 프레임워크를 지정하는 경우 각 대상 프레임워크에 대한 어셈블리를 조건부로 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-197">When you specify multiple target frameworks, you may conditionally reference assemblies for each target framework.</span></span> <span data-ttu-id="97a45-198">코드에서는 *if-then-else* 논리에 전처리기 기호를 사용하여 해당 어셈블리를 조건부로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-198">In your code, you can conditionally compile against those assemblies by using preprocessor symbols with *if-then-else* logic.</span></span>

<span data-ttu-id="97a45-199">다음 라이브러리 프로젝트 파일은 .NET Standard(`netstandard1.4`)의 API 및 .NET Framework(`net40` 및 `net45`)의 API를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-199">The following library project file targets APIs of .NET Standard (`netstandard1.4`) and APIs of the .NET Framework (`net40` and `net45`).</span></span> <span data-ttu-id="97a45-200">여러 대상 프레임워크에는 복수형 **TargetFrameworks** 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-200">Use the plural **TargetFrameworks** element with multiple target frameworks.</span></span> <span data-ttu-id="97a45-201">라이브러리가 두 개의 .NET Framework TFM에 대해 컴파일되면 `Condition` 특성에 구현 관련 패키지가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-201">Note how the `Condition` attributes include implementation-specific packages when the library is compiled for the two .NET Framework TFMs:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.0 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net40' ">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.5 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net45' ">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="97a45-202">라이브러리 또는 앱 내에서 각 대상 프레임워크에 대해 컴파일할 조건부 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-202">Within your library or app, you write conditional code to compile for each target framework:</span></span>

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        Console.WriteLine("Target framework: .NET Framework 4.0");
#elif NET45  
        Console.WriteLine("Target framework: .NET Framework 4.5");
#else
        Console.WriteLine("Target framework: .NET Standard 1.4");
#endif
    }
}
```

<span data-ttu-id="97a45-203">빌드 시스템은 [지원되는 대상 프레임워크 버전](#supported-target-framework-versions) 표에 표시된 대상 프레임워크를 나타내는 전처리기 기호를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-203">The build system is aware of preprocessor symbols representing the target frameworks shown in the [Supported target framework versions](#supported-target-framework-versions) table.</span></span> <span data-ttu-id="97a45-204">.NET Standard 또는 .NET Core TFM을 나타내는 기호를 사용할 경우 점을 밑줄로 바꾸고 소문자를 대문자로 변경합니다. 예를 들어 `netstandard1.4`에 대한 기호는 `NETSTANDARD1_4`입니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-204">When using a symbol that represents a .NET Standard or .NET Core TFM, replace the dot with an underscore and change lowercase letters to uppercase (for example, the symbol for `netstandard1.4` is `NETSTANDARD1_4`).</span></span>

<span data-ttu-id="97a45-205">다음은 .NET Core 대상 프레임워크에 대한 전체 전처리기 기호 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-205">The complete list of preprocessor symbols for .NET Core target frameworks is:</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

## <a name="deprecated-target-frameworks"></a><span data-ttu-id="97a45-206">사용되지 않는 대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="97a45-206">Deprecated target frameworks</span></span>

<span data-ttu-id="97a45-207">다음 대상 프레임워크는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-207">The following target frameworks are deprecated.</span></span> <span data-ttu-id="97a45-208">이러한 대상 프레임워크를 대상으로 하는 패키지는 지정된 대체 항목으로 마이그레이션되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97a45-208">Packages targeting these target frameworks should migrate to the indicated replacements.</span></span>

| <span data-ttu-id="97a45-209">사용되지 않는 TFM</span><span class="sxs-lookup"><span data-stu-id="97a45-209">Deprecated TFM</span></span>                                                                             | <span data-ttu-id="97a45-210">Replacement</span><span class="sxs-lookup"><span data-stu-id="97a45-210">Replacement</span></span> |
| ------------------------------------------------------------------------------------------ | ----------- |
| <span data-ttu-id="97a45-211">aspnet50</span><span class="sxs-lookup"><span data-stu-id="97a45-211">aspnet50</span></span><br><span data-ttu-id="97a45-212">aspnetcore50</span><span class="sxs-lookup"><span data-stu-id="97a45-212">aspnetcore50</span></span><br><span data-ttu-id="97a45-213">dnxcore50</span><span class="sxs-lookup"><span data-stu-id="97a45-213">dnxcore50</span></span><br><span data-ttu-id="97a45-214">dnx</span><span class="sxs-lookup"><span data-stu-id="97a45-214">dnx</span></span><br><span data-ttu-id="97a45-215">dnx45</span><span class="sxs-lookup"><span data-stu-id="97a45-215">dnx45</span></span><br><span data-ttu-id="97a45-216">dnx451</span><span class="sxs-lookup"><span data-stu-id="97a45-216">dnx451</span></span><br><span data-ttu-id="97a45-217">dnx452</span><span class="sxs-lookup"><span data-stu-id="97a45-217">dnx452</span></span>                  | <span data-ttu-id="97a45-218">netcoreapp</span><span class="sxs-lookup"><span data-stu-id="97a45-218">netcoreapp</span></span>  |
| <span data-ttu-id="97a45-219">dotnet</span><span class="sxs-lookup"><span data-stu-id="97a45-219">dotnet</span></span><br><span data-ttu-id="97a45-220">dotnet50</span><span class="sxs-lookup"><span data-stu-id="97a45-220">dotnet50</span></span><br><span data-ttu-id="97a45-221">dotnet51</span><span class="sxs-lookup"><span data-stu-id="97a45-221">dotnet51</span></span><br><span data-ttu-id="97a45-222">dotnet52</span><span class="sxs-lookup"><span data-stu-id="97a45-222">dotnet52</span></span><br><span data-ttu-id="97a45-223">dotnet53</span><span class="sxs-lookup"><span data-stu-id="97a45-223">dotnet53</span></span><br><span data-ttu-id="97a45-224">dotnet54</span><span class="sxs-lookup"><span data-stu-id="97a45-224">dotnet54</span></span><br><span data-ttu-id="97a45-225">dotnet55</span><span class="sxs-lookup"><span data-stu-id="97a45-225">dotnet55</span></span><br><span data-ttu-id="97a45-226">dotnet56</span><span class="sxs-lookup"><span data-stu-id="97a45-226">dotnet56</span></span> | <span data-ttu-id="97a45-227">netstandard</span><span class="sxs-lookup"><span data-stu-id="97a45-227">netstandard</span></span> |
| <span data-ttu-id="97a45-228">netcore50</span><span class="sxs-lookup"><span data-stu-id="97a45-228">netcore50</span></span>                                                                                  | <span data-ttu-id="97a45-229">uap10.0</span><span class="sxs-lookup"><span data-stu-id="97a45-229">uap10.0</span></span>     |
| <span data-ttu-id="97a45-230">win</span><span class="sxs-lookup"><span data-stu-id="97a45-230">win</span></span>                                                                                        | <span data-ttu-id="97a45-231">netcore45</span><span class="sxs-lookup"><span data-stu-id="97a45-231">netcore45</span></span>   |
| <span data-ttu-id="97a45-232">win8</span><span class="sxs-lookup"><span data-stu-id="97a45-232">win8</span></span>                                                                                       | <span data-ttu-id="97a45-233">netcore45</span><span class="sxs-lookup"><span data-stu-id="97a45-233">netcore45</span></span>   |
| <span data-ttu-id="97a45-234">win81</span><span class="sxs-lookup"><span data-stu-id="97a45-234">win81</span></span>                                                                                      | <span data-ttu-id="97a45-235">netcore451</span><span class="sxs-lookup"><span data-stu-id="97a45-235">netcore451</span></span>  |
| <span data-ttu-id="97a45-236">win10</span><span class="sxs-lookup"><span data-stu-id="97a45-236">win10</span></span>                                                                                      | <span data-ttu-id="97a45-237">uap10.0</span><span class="sxs-lookup"><span data-stu-id="97a45-237">uap10.0</span></span>     |
| <span data-ttu-id="97a45-238">winrt</span><span class="sxs-lookup"><span data-stu-id="97a45-238">winrt</span></span>                                                                                      | <span data-ttu-id="97a45-239">netcore45</span><span class="sxs-lookup"><span data-stu-id="97a45-239">netcore45</span></span>   |

## <a name="see-also"></a><span data-ttu-id="97a45-240">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97a45-240">See also</span></span>

[<span data-ttu-id="97a45-241">패키지, 메타패키지 및 프레임워크</span><span class="sxs-lookup"><span data-stu-id="97a45-241">Packages, Metapackages and Frameworks</span></span>](~/docs/core/packages.md)  
[<span data-ttu-id="97a45-242">플랫폼 간 도구로 라이브러리 개발</span><span class="sxs-lookup"><span data-stu-id="97a45-242">Developing Libraries with Cross Platform Tools</span></span>](~/docs/core/tutorials/libraries.md)  
[<span data-ttu-id="97a45-243">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="97a45-243">.NET Standard</span></span>](~/docs/standard/net-standard.md)  
[<span data-ttu-id="97a45-244">.NET Core 버전 관리</span><span class="sxs-lookup"><span data-stu-id="97a45-244">.NET Core Versioning</span></span>](~/docs/core/versions/index.md)  
<span data-ttu-id="97a45-245">[dotnet/standard GitHub repository](https://github.com/dotnet/standard)(dotnet/표준 GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="97a45-245">[dotnet/standard GitHub repository](https://github.com/dotnet/standard)</span></span>  
<span data-ttu-id="97a45-246">[NuGet Tools GitHub Repository](https://github.com/joelverhagen/NuGetTools)(NuGet 도구 GitHub 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="97a45-246">[NuGet Tools GitHub Repository](https://github.com/joelverhagen/NuGetTools)</span></span>  
<span data-ttu-id="97a45-247">[Framework Profiles in .NET](http://blog.stephencleary.com/2012/05/framework-profiles-in-net.html)(.NET의 프레임워크 프로필)</span><span class="sxs-lookup"><span data-stu-id="97a45-247">[Framework Profiles in .NET](http://blog.stephencleary.com/2012/05/framework-profiles-in-net.html)</span></span>

