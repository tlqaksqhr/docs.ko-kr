---
title: ".NET 아키텍처 구성 요소"
description: ".NET Standard, .NET 구현, .NET 런타임 및 도구와 같은 .NET 아키텍처 구성 요소에 대해 설명합니다."
author: cartermp
ms.author: mairaw
ms.date: 08/23/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.translationtype: HT
ms.sourcegitcommit: 1b028e5880f9e57e87c16eabeb442e0a46a369da
ms.openlocfilehash: ce3368f4c34a8e4b20a7deb2a6c6e4d163927cd4
ms.contentlocale: ko-kr
ms.lasthandoff: 08/23/2017

---
# <a name="net-architectural-components"></a><span data-ttu-id="fb427-103">.NET 아키텍처 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fb427-103">.NET architectural components</span></span>

<span data-ttu-id="fb427-104">.NET 앱은 하나 이상의 *.NET 구현*에 대해 개발되고 이 구현에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-104">A .NET app is developed for and runs in one or more *implementations of .NET*.</span></span>  <span data-ttu-id="fb427-105">.NET 구현에는 .NET Framework, .NET Core 및 Mono가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-105">Implementations of .NET include the .NET Framework, .NET Core, and Mono.</span></span> <span data-ttu-id="fb427-106">.NET Standard라는 모든 .NET 구현에 공통된 API 사양이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-106">There is an API specification common to all implementations of .NET that's called the .NET Standard.</span></span> <span data-ttu-id="fb427-107">이 문서에서는 이러한 각 개념에 대해 간략하게 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-107">This article gives a brief introduction to each of these concepts.</span></span>

## <a name="net-standard"></a><span data-ttu-id="fb427-108">.NET 표준</span><span class="sxs-lookup"><span data-stu-id="fb427-108">.NET Standard</span></span>

<span data-ttu-id="fb427-109">.NET Standard는 .NET 구현의 기본 클래스 라이브러리에서 구현하는 API 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-109">The .NET Standard is a set of APIs that are implemented by the Base Class Library of a .NET implementation.</span></span> <span data-ttu-id="fb427-110">공식적으로 말하자면 코드를 컴파일할 균일한 계약 집합을 구성하는 .NET API 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-110">More formally, it's a specification of .NET APIs that make up a uniform set of contracts that you compile your code against.</span></span> <span data-ttu-id="fb427-111">이러한 계약은 각 .NET 구현에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-111">These contracts are implemented in each .NET implementation.</span></span> <span data-ttu-id="fb427-112">그러면 코드가 어디서든 실행될 수 있도록 여러 .NET 구현 간에 이식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-112">This enables portability across different .NET implementations, effectively allowing your code to run everywhere.</span></span>

<span data-ttu-id="fb427-113">.NET Standard는 또한 [대상 프레임워크](glossary.md#target-framework)입니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-113">The .NET Standard is also a [target framework](glossary.md#target-framework).</span></span> <span data-ttu-id="fb427-114">코드가 .NET Standard의 버전을 대상으로 하는 경우 해당 버전의 .NET Standard를 지원하는 모든 .NET 구현에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-114">If your code targets a version of the .NET Standard, it can run on any .NET implementation which supports that version of the .NET Standard.</span></span>

<span data-ttu-id="fb427-115">.NET Standard 및 대상으로 지정하는 방법에 대한 자세한 내용은 [.NET Standard](net-standard.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb427-115">To learn more about the .NET Standard and how to target it, see the [.NET Standard](net-standard.md) topic.</span></span>

## <a name="net-implementations"></a><span data-ttu-id="fb427-116">.NET 구현</span><span class="sxs-lookup"><span data-stu-id="fb427-116">.NET implementations</span></span>

<span data-ttu-id="fb427-117">.NET의 각 구현에는 다음과 같은 구성 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-117">Each implementation of .NET includes the following components:</span></span>

- <span data-ttu-id="fb427-118">하나 이상의 런타임.</span><span class="sxs-lookup"><span data-stu-id="fb427-118">One or more runtimes.</span></span> <span data-ttu-id="fb427-119">예를 들어 .NET Framework용 CLR, CoreCLR 및 .NET Core용 CoreRT가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-119">Examples: CLR for .NET Framework, CoreCLR and CoreRT for .NET Core.</span></span>
- <span data-ttu-id="fb427-120">.NET Standard를 구현하고 추가 API를 구현할 수 있는 클래스 라이브러리.</span><span class="sxs-lookup"><span data-stu-id="fb427-120">A class library that implements the .NET Standard and may implement additional APIs.</span></span> <span data-ttu-id="fb427-121">예를 들어 .NET Framework 기본 클래스 라이브러리, .NET Core 기본 클래스 라이브러리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-121">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="fb427-122">필요에 따라 하나 이상의 응용 프로그램 프레임워크.</span><span class="sxs-lookup"><span data-stu-id="fb427-122">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="fb427-123">예를 들어 [ASP.NET](https://www.asp.net/), [Windows Forms](../framework/winforms/windows-forms-overview.md) 및 [WPF(Windows Presentation Foundation)](../framework/wpf/index.md)가 .NET Framework에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-123">Examples: [ASP.NET](https://www.asp.net/), [Windows Forms](../framework/winforms/windows-forms-overview.md), and [Windows Presentation Foundation (WPF)](../framework/wpf/index.md) are included in the .NET Framework.</span></span>
- <span data-ttu-id="fb427-124">필요에 따라 개발 도구.</span><span class="sxs-lookup"><span data-stu-id="fb427-124">Optionally, development tools.</span></span> <span data-ttu-id="fb427-125">일부 개발 도구는 여러 구현에서 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-125">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="fb427-126">Microsoft에서 적극적으로 개발하고 유지 관리하는 네 가지 기본 .NET 구현은 .NET Core, .NET Framework, Mono 및 UWP입니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-126">There are four primary .NET implementations that Microsoft actively develops and maintains: .NET Core, .NET Framework, Mono, and UWP.</span></span>

### <a name="net-core"></a><span data-ttu-id="fb427-127">.NET Core</span><span class="sxs-lookup"><span data-stu-id="fb427-127">.NET Core</span></span>

<span data-ttu-id="fb427-128">.NET Core는 .NET의 플랫폼 간 구현으로, 대규모 서버 및 클라우드 워크로드를 처리하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-128">.NET Core is a cross-platform implementation of .NET and designed to handle server and cloud workloads at scale.</span></span> <span data-ttu-id="fb427-129">Windows, macOS 및 Linux에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-129">It runs on Windows, macOS and Linux.</span></span> <span data-ttu-id="fb427-130">.NET Core는 .NET Standard를 구현하므로 .NET Standard를 대상으로 하는 코드는 .NET Core에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-130">It implements the .NET Standard, so code that targets the .NET Standard can run on .NET Core.</span></span> <span data-ttu-id="fb427-131">ASP.NET Core는 .NET Core에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-131">ASP.NET Core runs on .NET Core.</span></span> 

<span data-ttu-id="fb427-132">.NET Core에 대한 자세한 내용은 [.NET Core 가이드](../core/index.md) 및 [서버 앱에 대해 .NET Core와 .NET Framework 중에 선택](choosing-core-framework-server.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb427-132">To learn more about .NET Core, see the [.NET Core Guide](../core/index.md) and [Choosing between .NET Core and .NET Framework for server apps](choosing-core-framework-server.md).</span></span>

### <a name="net-framework"></a><span data-ttu-id="fb427-133">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="fb427-133">.NET Framework</span></span>

<span data-ttu-id="fb427-134">.NET Framework는 2002년부터 있었던 원래 .NET 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-134">The.NET Framework is the original .NET implementation that has existed since 2002.</span></span> <span data-ttu-id="fb427-135">기존 .NET 개발자가 항상 사용해 온 것과 동일한 .NET Framework입니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-135">It's the same .NET Framework that existing .NET developers have always used.</span></span> <span data-ttu-id="fb427-136">버전 4.5 이상은 .NET Standard를 구현하므로 .NET Standard를 대상으로 하는 코드는 .NET Framework의 해당 버전에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-136">Versions 4.5 and later implement the .NET Standard, so code that targets the .NET Standard can run on those versions of the .NET Framework.</span></span> <span data-ttu-id="fb427-137">Windows Forms 및 WPF를 사용하는 Windows 데스크톱 개발용 API와 같이 Windows 관련 추가 API가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-137">It contains additional Windows-specific APIs, such as APIs for Windows desktop development with Windows Forms and WPF.</span></span> <span data-ttu-id="fb427-138">.NET Framework는 Windows 데스크톱 응용 프로그램을 구축을 위해 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-138">The .NET Framework is optimized for building Windows desktop applications.</span></span>

<span data-ttu-id="fb427-139">.NET Framework에 대한 자세한 내용은 [.NET Framework 가이드](../framework/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb427-139">To learn more about the .NET Framework, see the [.NET Framework Guide](../framework/index.md).</span></span>

### <a name="mono"></a><span data-ttu-id="fb427-140">Mono</span><span class="sxs-lookup"><span data-stu-id="fb427-140">Mono</span></span>

<span data-ttu-id="fb427-141">Mono는 작은 런타임이 필요할 때 주로 사용되는 .NET 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-141">Mono is a .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="fb427-142">이는 Android, Mac, iOS, tvOS 및 watchOS에서 Xamarin 응용 프로그램의 성능을 향상하는 런타임으로, 주로 작은 사용 공간에 초점을 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-142">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on a small footprint.</span></span>

<span data-ttu-id="fb427-143">Mono는 현재 게시된 .NET Standard 버전을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-143">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="fb427-144">지금까지 Mono는 .NET Framework의 더 큰 API를 구현하고 Unix에서 가장 인기 있는 기능 중 일부를 에뮬레이트했습니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-144">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="fb427-145">경우에 따라 Unix에서 해당 기능을 사용하는 .NET 응용 프로그램을 실행하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-145">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="fb427-146">일반적으로 Mono는 Just-In-Time 컴파일러에서 사용되지만 iOS 같은 플랫폼에 사용되는 전체 정적 컴파일러(Ahead-Of-Time 컴파일) 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-146">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="fb427-147">Mono에 대한 자세한 내용은 [Mono 설명서](http://www.mono-project.com/docs/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb427-147">To learn more about Mono, see the [Mono documentation](http://www.mono-project.com/docs/).</span></span>

### <a name="universal-windows-platform-uwp"></a><span data-ttu-id="fb427-148">UWP(유니버설 Windows 플랫폼)</span><span class="sxs-lookup"><span data-stu-id="fb427-148">Universal Windows Platform (UWP)</span></span>

<span data-ttu-id="fb427-149">UWP는 IoT(사물 인터넷)에 대한 최신 터치 가능 Windows 응용 프로그램 및 소프트웨어를 작성하는 데 사용되는 .NET의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-149">UWP is an implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="fb427-150">PC, 태블릿, 패블릿, 휴대폰, Xbox 등 대상으로 지정할 수 있는 다양한 종류의 장치를 통합하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-150">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="fb427-151">UWP는 중앙 집중식 앱 스토어, 실행 환경(AppContainer), Win32 대신 사용할 Windows API 집합(WinRT) 등 많은 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-151">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="fb427-152">앱은 C++, C#, VB.NET 및 JavaScript로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-152">Apps can be written in C++, C#, VB.NET, and JavaScript.</span></span> <span data-ttu-id="fb427-153">C# 및 VB.NET을 사용할 경우 .NET API는 .NET Core에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-153">When using C# and VB.NET, the .NET APIs are provided by .NET Core.</span></span>

<span data-ttu-id="fb427-154">UWP에 대한 자세한 내용은 [유니버설 Windows 플랫폼 소개](https://docs.microsoft.com/windows/uwp/get-started/universal-application-platform-guide)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb427-154">To learn more about UWP, see [Intro to the Universal Windows Platform](https://docs.microsoft.com/windows/uwp/get-started/universal-application-platform-guide).</span></span>

## <a name="net-runtimes"></a><span data-ttu-id="fb427-155">.NET 런타임</span><span class="sxs-lookup"><span data-stu-id="fb427-155">.NET runtimes</span></span>

<span data-ttu-id="fb427-156">런타임은 관리되는 프로그램에 대한 실행 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-156">A runtime is the execution environment for a managed program.</span></span> <span data-ttu-id="fb427-157">OS는 런타임 환경의 일부이지만 .NET 런타임의 일부는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-157">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="fb427-158">다음은 .NET 런타임의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-158">Here are some examples of .NET runtimes:</span></span>
 
 - <span data-ttu-id="fb427-159">.NET Framework에 대한 CLR(공용 언어 런타임)</span><span class="sxs-lookup"><span data-stu-id="fb427-159">Common Language Runtime (CLR) for the .NET Framework</span></span>
 - <span data-ttu-id="fb427-160">.NET Core에 대한 CoreCLR(Core 공용 언어 런타임)</span><span class="sxs-lookup"><span data-stu-id="fb427-160">Core Common Language Runtime (CoreCLR) for .NET Core</span></span>
 - <span data-ttu-id="fb427-161">유니버설 Windows 플랫폼용 .NET 네이티브</span><span class="sxs-lookup"><span data-stu-id="fb427-161">.NET Native for Universal Windows Platform</span></span> 
 - <span data-ttu-id="fb427-162">Xamarin.iOS, Xamarin.Android, Xamarin.Mac 및 Mono 데스크톱 프레임워크에 대한 Mono 런타임</span><span class="sxs-lookup"><span data-stu-id="fb427-162">The Mono runtime for Xamarin.iOS, Xamarin.Android, Xamarin.Mac, and the Mono desktop framework</span></span>

## <a name="net-tooling-and-common-infrastructure"></a><span data-ttu-id="fb427-163">.NET 도구 및 공통 인프라</span><span class="sxs-lookup"><span data-stu-id="fb427-163">.NET tooling and common infrastructure</span></span>

<span data-ttu-id="fb427-164">모든 .NET 구현에서 작동하는 광범위한 도구 및 인프라 구성 요소 집합에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-164">You have access to an extensive set of tools and infrastructure components that work with every implementation of .NET.</span></span> <span data-ttu-id="fb427-165">여기에는 다음이 포함되지만 다음으로 제한되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb427-165">These include, but are not limited to the following:</span></span>

- <span data-ttu-id="fb427-166">.NET 언어 및 해당 컴파일러</span><span class="sxs-lookup"><span data-stu-id="fb427-166">The .NET languages and their compilers</span></span>
- <span data-ttu-id="fb427-167">.NET 프로젝트 시스템(*.csproj*, *.vbproj* 및 *.fsproj* 파일 기반)</span><span class="sxs-lookup"><span data-stu-id="fb427-167">The .NET project system (based on *.csproj*, *.vbproj*, and *.fsproj* files)</span></span>
- <span data-ttu-id="fb427-168">프로젝트를 빌드하는 데 사용하는 빌드 엔진 [MSBuild](/visualstudio/msbuild/msbuild)</span><span class="sxs-lookup"><span data-stu-id="fb427-168">[MSBuild](/visualstudio/msbuild/msbuild), the build engine used to build projects</span></span>
- <span data-ttu-id="fb427-169">.NET에 대한 Microsoft의 패키지 관리자 [NuGet](/nuget/)</span><span class="sxs-lookup"><span data-stu-id="fb427-169">[NuGet](/nuget/), Microsoft's package manager for .NET</span></span>
- <span data-ttu-id="fb427-170">[CAKE](http://cakebuild.net/) 및 [FAKE](https://fake.build/) 등의 오픈 소스 빌드 오케스트레이션 도구</span><span class="sxs-lookup"><span data-stu-id="fb427-170">Open-source build orchestration tools, such as [CAKE](http://cakebuild.net/) and [FAKE](https://fake.build/)</span></span>

## <a name="see-also"></a><span data-ttu-id="fb427-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb427-171">See also</span></span>
<span data-ttu-id="fb427-172">[서버 앱에 대해 .NET Core와 .NET Framework 중에 선택](choosing-core-framework-server.md) </span><span class="sxs-lookup"><span data-stu-id="fb427-172">[Choosing between .NET Core and .NET Framework for server apps](choosing-core-framework-server.md) </span></span>  
[<span data-ttu-id="fb427-173">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="fb427-173">.NET Standard</span></span>](net-standard.md)  
[<span data-ttu-id="fb427-174">.NET Core 가이드</span><span class="sxs-lookup"><span data-stu-id="fb427-174">.NET Core Guide</span></span>](../core/index.md)  
[<span data-ttu-id="fb427-175">.NET Framework 가이드</span><span class="sxs-lookup"><span data-stu-id="fb427-175">.NET Framework Guide</span></span>](../framework/index.md)  
[<span data-ttu-id="fb427-176">C# 가이드</span><span class="sxs-lookup"><span data-stu-id="fb427-176">C# Guide</span></span>](../csharp/index.md)  
[<span data-ttu-id="fb427-177">F# 가이드</span><span class="sxs-lookup"><span data-stu-id="fb427-177">F# Guide</span></span>](../fsharp/index.md)  
[<span data-ttu-id="fb427-178">VB.NET 가이드</span><span class="sxs-lookup"><span data-stu-id="fb427-178">VB.NET Guide</span></span>](../visual-basic/index.md)  


