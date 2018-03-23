---
title: .NET 용어
description: .NET 설명서에서 사용되는 선택한 용어의 의미를 알아봅니다.
keywords: .NET 용어, .NET 사전, .NET 용어, .NET 플랫폼, .NET framework, .NET 런타임
author: tdykstra
ms.author: tdykstra
ms.date: 07/08/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 33123732514a53574036f6f8e948b2cf9acb9229
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2018
---
# <a name="net-glossary"></a><span data-ttu-id="b3c31-104">.NET 용어</span><span class="sxs-lookup"><span data-stu-id="b3c31-104">.NET Glossary</span></span>

<span data-ttu-id="b3c31-105">이 용어집의 주 용도는 .NET 설명서에서 정의 없이 자주 나타나는 선택한 용어 및 머리글자어의 의미를 명확히 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-105">The primary goal of this glossary is to clarify meanings of selected terms and acronyms that appear frequently in the .NET documentation without definitions.</span></span>

## <a name="aot"></a><span data-ttu-id="b3c31-106">AOT</span><span class="sxs-lookup"><span data-stu-id="b3c31-106">AOT</span></span>

<span data-ttu-id="b3c31-107">Ahead-Of-Time 컴파일러입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-107">Ahead-of-time compiler.</span></span>

<span data-ttu-id="b3c31-108">[JIT](#jit)와 비슷한 이 컴파일러도 [IL](#il)을 기계어 코드로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-108">Similar to [JIT](#jit), this compiler also translates [IL](#il) to machine code.</span></span> <span data-ttu-id="b3c31-109">JIT 컴파일과 달리 AOT 컴파일은 응용 프로그램이 실행되기 전에 수행되며 일반적으로 다른 컴퓨터에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-109">In contrast to JIT compilation, AOT compilation happens before the application is executed and is usually performed on a different machine.</span></span> <span data-ttu-id="b3c31-110">AOT 도구 체인은 런타임에 컴파일되지 않으므로 컴파일 시간을 최소화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-110">Because AOT tool chains don't compile at runtime, they don't have to minimize time spent compiling.</span></span> <span data-ttu-id="b3c31-111">즉, 더 많은 시간을 최적화하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-111">That means they can spend more time optimizing.</span></span> <span data-ttu-id="b3c31-112">AOT의 컨텍스트는 전체 응용 프로그램이므로 AOT 컴파일러는 모듈 간 연결 및 전체 프로그램 분석도 수행합니다. 즉, 모든 참조가 수행되고 단일 실행 파일이 생성된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-112">Since the context of AOT is the entire application, the AOT compiler also performs cross-module linking and whole-program analysis, which means that all references are followed and a single executable is produced.</span></span>

## <a name="aspnet"></a><span data-ttu-id="b3c31-113">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b3c31-113">ASP.NET</span></span> 

<span data-ttu-id="b3c31-114">.NET Framework와 함께 제공되는 원래 ASP.NET 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-114">The original ASP.NET implementation that ships with the .NET Framework.</span></span>

<span data-ttu-id="b3c31-115">경우에 따라 ASP.NET은 ASP.NET Core를 포함하여 두 ASP.NET 구현을 나타내는 포괄적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-115">Sometimes ASP.NET is an umbrella term that refers to both ASP.NET implementations including ASP.NET Core.</span></span> <span data-ttu-id="b3c31-116">지정된 인스턴스에서 이 용어가 전달하는 의미는 컨텍스트에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-116">The meaning that the term carries in any given instance is determined by context.</span></span> <span data-ttu-id="b3c31-117">두 구현을 모두 의미하는 데 ASP.NET을 사용하지 않는 것을 분명히 하려는 경우 ASP.NET 4.x를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-117">Refer to ASP.NET 4.x when you want to make it clear that you’re not using ASP.NET to mean both implementations.</span></span> 

<span data-ttu-id="b3c31-118">[ASP.NET 설명서](/aspnet/#pivot=aspnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-118">See [ASP.NET documentation](/aspnet/#pivot=aspnet).</span></span>

## <a name="aspnet-core"></a><span data-ttu-id="b3c31-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b3c31-119">ASP.NET Core</span></span>

<span data-ttu-id="b3c31-120">.NET Core를 기반으로 하는 ASP.NET의 플랫폼 간 고성능 오픈 소스 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-120">A cross-platform, high-performance, open source implementation of ASP.NET built on .NET Core.</span></span>

<span data-ttu-id="b3c31-121">[ASP.NET Core 설명서](/aspnet/#pivot=core)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-121">See [ASP.NET Core documentation](/aspnet/#pivot=core).</span></span>

## <a name="assembly"></a><span data-ttu-id="b3c31-122">어셈블리</span><span class="sxs-lookup"><span data-stu-id="b3c31-122">assembly</span></span>

<span data-ttu-id="b3c31-123">앱이나 다른 어셈블리에서 호출할 수 있는 API 컬렉션을 포함할 수 있는 *.dll*/*.exe* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-123">A *.dll*/*.exe* file that can contain a collection of APIs that can be called by apps or other assemblies.</span></span>

<span data-ttu-id="b3c31-124">어셈블리에는 인터페이스, 클래스, 구조체, 열거형 및 대리자와 같은 형식이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-124">An assembly may include types such as interfaces, classes, structures, enumerations, and delegates.</span></span> <span data-ttu-id="b3c31-125">프로젝트의 *bin* 폴더에 있는 어셈블리를 *바이너리*라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-125">Assemblies in a project's *bin* folder are sometimes referred to as *binaries*.</span></span> <span data-ttu-id="b3c31-126">[라이브러리](#library)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-126">See also [library](#library).</span></span>

## <a name="clr"></a><span data-ttu-id="b3c31-127">CLR</span><span class="sxs-lookup"><span data-stu-id="b3c31-127">CLR</span></span>

<span data-ttu-id="b3c31-128">공용 언어 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-128">Common Language Runtime.</span></span>

<span data-ttu-id="b3c31-129">정확한 의미는 컨텍스트에 따라 달라지지만 일반적으로 .NET Framework의 런타임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-129">The exact meaning depends on the context, but this usually refers to the runtime of the .NET Framework.</span></span> <span data-ttu-id="b3c31-130">CLR은 메모리 할당 및 관리를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-130">The CLR handles memory allocation and management.</span></span> <span data-ttu-id="b3c31-131">또한 CLR은 앱을 실행할 뿐만 아니라 JIT 컴파일러를 사용하여 즉시 코드를 생성하고 컴파일하는 가상 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-131">The CLR is also a virtual machine that not only executes apps but also generates and compiles code on-the-fly using a JIT compiler.</span></span> <span data-ttu-id="b3c31-132">현재 Microsoft CLR 구현은 Windows 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-132">The current Microsoft CLR implementation is Windows only.</span></span>

## <a name="coreclr"></a><span data-ttu-id="b3c31-133">CoreCLR</span><span class="sxs-lookup"><span data-stu-id="b3c31-133">CoreCLR</span></span>

<span data-ttu-id="b3c31-134">.NET Core 공용 언어 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-134">.NET Core Common Language Runtime.</span></span>

<span data-ttu-id="b3c31-135">이 CLR은 CLR과 동일한 코드베이스에서 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-135">This CLR is built from the same code base as the CLR.</span></span> <span data-ttu-id="b3c31-136">원래 CoreCLR은 Silverlight의 런타임이었으며 여러 플랫폼, 특히 Windows 및 OS X에서 실행되도록 설계되었습니다. 이제 CoreCLR은 .NET Core의 일부이며 CLR의 단순화된 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-136">Originally, CoreCLR was the runtime of Silverlight and was designed to run on multiple platforms, specifically Windows and OS X. CoreCLR is now part of .NET Core and represents a simplified version of the CLR.</span></span> <span data-ttu-id="b3c31-137">이제 많은 Linux 배포에 대한 지원을 포함하는 플랫폼 간 런타임이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-137">It's still a cross platform runtime, now including support for many Linux distributions.</span></span> <span data-ttu-id="b3c31-138">CoreCLR은 JIT 및 코드 실행 기능이 있는 가상 컴퓨터이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-138">CoreCLR is also a virtual machine with JIT and code execution capabilities.</span></span>

## <a name="corefx"></a><span data-ttu-id="b3c31-139">CoreFX</span><span class="sxs-lookup"><span data-stu-id="b3c31-139">CoreFX</span></span>

<span data-ttu-id="b3c31-140">.NET Core BCL(기본 클래스 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="b3c31-140">.NET Core Base Class Library (BCL)</span></span>

<span data-ttu-id="b3c31-141">System.*(및 제한된 범위의 Microsoft.*) 네임스페이스를 구성하는 라이브러리 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-141">A set of libraries that comprise the System.* (and to a limited extent  Microsoft.*) namespaces.</span></span> <span data-ttu-id="b3c31-142">BCL은 ASP.NET Core 같은 상위 수준 응용 프로그램 프레임워크의 기반이 되는 하위 수준의 범용 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-142">The BCL is a general purpose, lower-level framework that higher-level application frameworks, such as ASP.NET Core, build on.</span></span> <span data-ttu-id="b3c31-143">.NET Core BCL의 소스 코드는 [CoreFX 리포지토리](https://github.com/dotnet/corefx)에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-143">The source code of the .NET Core BCL is contained in the [CoreFX repository](https://github.com/dotnet/corefx).</span></span> <span data-ttu-id="b3c31-144">그러나 대부분의 .NET Core API는 .NET Framework에서 사용할 수도 있으므로 CoreFX를 .NET Framework BCL의 포크로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-144">However, the majority of the .NET Core APIs are also available in the .NET Framework, so you can think of CoreFX as a fork of the .NET Framework BCL.</span></span>

## <a name="corert"></a><span data-ttu-id="b3c31-145">CoreRT</span><span class="sxs-lookup"><span data-stu-id="b3c31-145">CoreRT</span></span>

<span data-ttu-id="b3c31-146">.NET Core 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-146">.NET Core runtime.</span></span>

<span data-ttu-id="b3c31-147">CLR/CoreCLR과 달리 CoreRT는 가상 컴퓨터가 아닙니다. 즉, [JIT](#jit)를 포함하지 않으므로 즉시 코드를 생성하고 실행하는 기능을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-147">In contrast to the CLR/CoreCLR, CoreRT is not a virtual machine, which means it doesn't include the facilities to generate and run code on-the-fly because it doesn't include a [JIT](#jit).</span></span> <span data-ttu-id="b3c31-148">그러나 [GC](#gc)와 RTTI(런타임 형식 식별) 및 리플렉션에 대한 기능은 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-148">It does, however, include the [GC](#gc) and the ability for runtime type identification (RTTI) and reflection.</span></span> <span data-ttu-id="b3c31-149">그러나 해당 형식 시스템은 리플렉션에 대한 메타데이터가 필요하지 않도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-149">However, its type system is designed so that metadata for reflection isn't required.</span></span> <span data-ttu-id="b3c31-150">따라서 불필요한 메타데이터를 분리하고 더 중요하게는 앱이 사용하지 않는 코드를 식별할 수 있는 [AOT](#aot) 도구 체인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-150">This enables having an [AOT](#aot) tool chain that can link away superfluous metadata and (more importantly) identify code that the app doesn't use.</span></span> <span data-ttu-id="b3c31-151">CoreRT는 개발 중입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-151">CoreRT is in development.</span></span>

<span data-ttu-id="b3c31-152">[.NET 네이티브 및 CoreRT 소개](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-152">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="ecosystem"></a><span data-ttu-id="b3c31-153">에코시스템</span><span class="sxs-lookup"><span data-stu-id="b3c31-153">ecosystem</span></span>

<span data-ttu-id="b3c31-154">특정 기술에 대한 응용 프로그램을 빌드하고 실행하는 데 사용되는 모든 런타임 소프트웨어, 개발 도구 및 커뮤니티 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-154">All of the runtime software, development tools, and community resources that are used to build and run applications for a given technology.</span></span>

<span data-ttu-id="b3c31-155">“.NET 에코시스템”이라는 용어는 타사 앱 및 라이브러리를 포함한다는 점에서 “.NET 스택”과 같은 유사한 용어와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-155">The term ".NET ecosystem" differs from similar terms such as ".NET stack" in its inclusion of third-party apps and libraries.</span></span> <span data-ttu-id="b3c31-156">다음은 문장에서의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-156">Here's an example in a sentence:</span></span>

- <span data-ttu-id="b3c31-157">“[.NET Standard](#net-standard)는 .NET 에코시스템의 균일성을 높이기 위한 것입니다.”</span><span class="sxs-lookup"><span data-stu-id="b3c31-157">"The motivation behind the [.NET Standard](#net-standard) is to establish greater uniformity in the .NET ecosystem."</span></span> 

## <a name="framework"></a><span data-ttu-id="b3c31-158">프레임워크</span><span class="sxs-lookup"><span data-stu-id="b3c31-158">framework</span></span>

<span data-ttu-id="b3c31-159">일반적으로 특정 기술을 기반으로 하는 응용 프로그램의 개발 및 배포를 용이하게 하는 포괄적인 API 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-159">In general, a comprehensive collection of APIs that facilitates development and deployment of applications that are based on a particular technology.</span></span> <span data-ttu-id="b3c31-160">이 일반적인 의미에서 ASP.NET Core 및 Windows Forms는 응용 프로그램 프레임워크의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-160">In this general sense, ASP.NET Core and Windows Forms are examples of application frameworks.</span></span> <span data-ttu-id="b3c31-161">[라이브러리](#library)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-161">See also [library](#library).</span></span>

<span data-ttu-id="b3c31-162">“프레임 워크”라는 단어는 다음과 같은 용어에서 좀 더 구체적인 기술적 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-162">The word "framework" has a more specific technical meaning in the following terms:</span></span>
* [<span data-ttu-id="b3c31-163">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="b3c31-163">.NET Framework</span></span>](#net-framework)
* [<span data-ttu-id="b3c31-164">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="b3c31-164">target framework</span></span>](#target-framework)
* [<span data-ttu-id="b3c31-165">TFM(대상 프레임워크 모니커)</span><span class="sxs-lookup"><span data-stu-id="b3c31-165">TFM (target framework moniker)</span></span>](#tfm)

<span data-ttu-id="b3c31-166">기존 설명서에서 “프레임워크”는 경우에 따라 [.NET의 구현](#implementation-of-net)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-166">In the existing documentation, "framework" sometimes refers to an [implementation of .NET](#implementation-of-net).</span></span> <span data-ttu-id="b3c31-167">예를 들어 문서에서 .NET Core를 프레임워크라고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-167">For example, an article may call .NET Core a framework.</span></span> <span data-ttu-id="b3c31-168">설명서에서 혼동을 주는 이러한 사용을 제거할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-168">We plan to eliminate this confusing usage from the documentation.</span></span>

## <a name="gc"></a><span data-ttu-id="b3c31-169">GC</span><span class="sxs-lookup"><span data-stu-id="b3c31-169">GC</span></span>

<span data-ttu-id="b3c31-170">가비지 수집기입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-170">Garbage collector.</span></span>

<span data-ttu-id="b3c31-171">가비지 수집기는 자동 메모리 관리의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-171">The garbage collector is an implementation of automatic memory management.</span></span>  <span data-ttu-id="b3c31-172">GC는 개체가 사용한 메모리에서 더 이상 사용되지 않는 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-172">The GC frees memory occupied by objects that are no longer in use.</span></span> 

<span data-ttu-id="b3c31-173">[가비지 수집](garbage-collection/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-173">See [Garbage Collection](garbage-collection/index.md).</span></span>

## <a name="il"></a><span data-ttu-id="b3c31-174">IL</span><span class="sxs-lookup"><span data-stu-id="b3c31-174">IL</span></span>

<span data-ttu-id="b3c31-175">중간 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-175">Intermediate language.</span></span>

<span data-ttu-id="b3c31-176">C#과 같은 상위 수준 .NET 언어가 IL(중간 언어)이라는 하드웨어 독립 명령 집합으로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-176">Higher-level .NET languages, such as C#, compile down to a hardware-agnostic instruction set, which is called Intermediate Language (IL).</span></span> <span data-ttu-id="b3c31-177">IL은 MSIL(Microsoft IL) 또는 CIL(공통 IL)이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-177">IL is sometimes referred to as MSIL (Microsoft IL) or CIL (Common IL).</span></span>

## <a name="jit"></a><span data-ttu-id="b3c31-178">JIT</span><span class="sxs-lookup"><span data-stu-id="b3c31-178">JIT</span></span>

<span data-ttu-id="b3c31-179">Just-In-Time 컴파일러입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-179">Just-in-time compiler.</span></span>

<span data-ttu-id="b3c31-180">[AOT](#aot)와 유사한 이 컴파일러는 [IL](#il)을 프로세서에서 이해하는 기계어 코드로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-180">Similar to [AOT](#aot), this compiler translates [IL](#il) to machine code that the processor understands.</span></span> <span data-ttu-id="b3c31-181">AOT와 달리 JIT 컴파일은 요청 시 수행되며 코드가 실행되어야 하는 것과 동일한 컴퓨터에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-181">Unlike AOT, JIT compilation happens on demand and is performed on the same machine that the code needs to run on.</span></span> <span data-ttu-id="b3c31-182">JIT 컴파일은 응용 프로그램이 실행되는 동안 수행되므로 컴파일 시간이 실행 시간의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-182">Since JIT compilation occurs during execution of the application, compile time is part of the run time.</span></span> <span data-ttu-id="b3c31-183">따라서 JIT 컴파일러는 결과 코드가 생성할 수 있는 시간 단축과 코드 최적화에 소요된 시간의 균형을 맞춰야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-183">Thus, JIT compilers have to balance time spent optimizing code against the savings that the resulting code can produce.</span></span> <span data-ttu-id="b3c31-184">그러나 JIT는 실제 하드웨어를 인식하므로 개발자가 다른 구현을 제공할 필요가 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-184">But a JIT knows the actual hardware and can free developers from having to ship different implementations.</span></span>

## <a name="implementation-of-net"></a><span data-ttu-id="b3c31-185">.NET의 구현</span><span class="sxs-lookup"><span data-stu-id="b3c31-185">implementation of .NET</span></span>

<span data-ttu-id="b3c31-186">.NET의 구현에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-186">An implementation of .NET includes the following:</span></span>

- <span data-ttu-id="b3c31-187">하나 이상의 런타임.</span><span class="sxs-lookup"><span data-stu-id="b3c31-187">One or more runtimes.</span></span> <span data-ttu-id="b3c31-188">예를 들어 CLR, CoreCLR, CoreRT가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-188">Examples: CLR, CoreCLR, CoreRT.</span></span>
- <span data-ttu-id="b3c31-189">.NET Standard의 버전을 구현하고 추가 API를 포함할 수 있는 클래스 라이브러리.</span><span class="sxs-lookup"><span data-stu-id="b3c31-189">A class library that implements a version of the .NET Standard and may include additional APIs.</span></span> <span data-ttu-id="b3c31-190">예를 들어 .NET Framework 기본 클래스 라이브러리, .NET Core 기본 클래스 라이브러리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-190">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="b3c31-191">필요에 따라 하나 이상의 응용 프로그램 프레임워크.</span><span class="sxs-lookup"><span data-stu-id="b3c31-191">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="b3c31-192">예를 들어 ASP.NET, Windows Forms 및 WPF가 .NET Framework에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-192">Examples: ASP.NET, Windows Forms, and WPF are included in the .NET Framework.</span></span>
- <span data-ttu-id="b3c31-193">필요에 따라 개발 도구.</span><span class="sxs-lookup"><span data-stu-id="b3c31-193">Optionally, development tools.</span></span> <span data-ttu-id="b3c31-194">일부 개발 도구는 여러 구현에서 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-194">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="b3c31-195">.NET 구현의 예:</span><span class="sxs-lookup"><span data-stu-id="b3c31-195">Examples of .NET implementations:</span></span>

- [<span data-ttu-id="b3c31-196">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="b3c31-196">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="b3c31-197">.NET Core</span><span class="sxs-lookup"><span data-stu-id="b3c31-197">.NET Core</span></span>](#net-core)
- [<span data-ttu-id="b3c31-198">UWP(유니버설 Windows 플랫폼)</span><span class="sxs-lookup"><span data-stu-id="b3c31-198">Universal Windows Platform (UWP)</span></span>](#uwp)

## <a name="library"></a><span data-ttu-id="b3c31-199">라이브러리</span><span class="sxs-lookup"><span data-stu-id="b3c31-199">library</span></span>

<span data-ttu-id="b3c31-200">앱이나 다른 라이브러리에서 호출할 수 있는 API 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-200">A collection of APIs that can be called by apps or other libraries.</span></span> <span data-ttu-id="b3c31-201">.NET 라이브러리는 하나 이상의 [어셈블리](#assembly)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-201">A .NET library is composed of one or more [assemblies](#assembly).</span></span>

<span data-ttu-id="b3c31-202">라이브러리 및 [프레임워크](#framework)라는 단어는 종종 같은 뜻으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-202">The words library and [framework](#framework) are often used synonymously.</span></span>

## <a name="metapackage"></a><span data-ttu-id="b3c31-203">메타패키지</span><span class="sxs-lookup"><span data-stu-id="b3c31-203">metapackage</span></span>

<span data-ttu-id="b3c31-204">고유한 라이브러리는 없지만 유일한 종속성 목록인 NuGet 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-204">A NuGet package that has no library of its own but is only a list of dependencies.</span></span> <span data-ttu-id="b3c31-205">포함된 패키지는 필요에 따라 대상 프레임워크에 대한 API를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-205">The included packages can optionally establish the API for a target framework.</span></span>

<span data-ttu-id="b3c31-206">[패키지, 메타패키지 및 프레임워크](../core/packages.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-206">See [Packages, Metapackages and Frameworks](../core/packages.md)</span></span>

## <a name="mono"></a><span data-ttu-id="b3c31-207">Mono</span><span class="sxs-lookup"><span data-stu-id="b3c31-207">Mono</span></span>

<span data-ttu-id="b3c31-208">Mono는 작은 런타임이 필요할 때 주로 사용되는 .NET 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-208">Mono is a .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="b3c31-209">이는 Android, Mac, iOS, tvOS 및 watchOS에서 Xamarin 응용 프로그램의 성능을 향상하는 런타임으로, 주로 작은 사용 공간이 필요한 앱에 초점을 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-209">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on apps that require a small footprint.</span></span>

<span data-ttu-id="b3c31-210">Mono는 현재 게시된 .NET Standard 버전을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-210">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="b3c31-211">지금까지 Mono는 .NET Framework의 더 큰 API를 구현하고 Unix에서 가장 인기 있는 기능 중 일부를 에뮬레이트했습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-211">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="b3c31-212">경우에 따라 Unix에서 해당 기능을 사용하는 .NET 응용 프로그램을 실행하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-212">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="b3c31-213">일반적으로 Mono는 Just-In-Time 컴파일러에서 사용되지만 iOS 같은 플랫폼에 사용되는 전체 정적 컴파일러(Ahead-Of-Time 컴파일) 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-213">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="b3c31-214">Mono에 대한 자세한 내용은 [Mono 설명서](http://www.mono-project.com/docs/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-214">To learn more about Mono, see the [Mono documentation](http://www.mono-project.com/docs/).</span></span>

## <a name="net"></a><span data-ttu-id="b3c31-215">.NET</span><span class="sxs-lookup"><span data-stu-id="b3c31-215">.NET</span></span>

<span data-ttu-id="b3c31-216">[.NET Standard](#net-standard) 및 모든 [.NET 구현](#implementation-of-net)과 워크로드에 대한 포괄적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-216">The umbrella term for [.NET Standard](#net-standard) and all [.NET implementations](#implementation-of-net) and workloads.</span></span> <span data-ttu-id="b3c31-217">항상 대문자로 표기되며, “.Net”이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-217">Always capitalized, never ".Net".</span></span>

<span data-ttu-id="b3c31-218">[.NET 가이드](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-218">See the [.NET Guide](index.md)</span></span>

## <a name="net-core"></a><span data-ttu-id="b3c31-219">.NET Core</span><span class="sxs-lookup"><span data-stu-id="b3c31-219">.NET Core</span></span> 

<span data-ttu-id="b3c31-220">.NET의 플랫폼 간 고성능 오픈 소스 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-220">A cross-platform, high-performance, open source implementation of .NET.</span></span> <span data-ttu-id="b3c31-221">CoreCLR(Core 공용 언어 런타임), Core AOT 런타임(CoreRT, 개발 중), Core 기본 클래스 라이브러리 및 Core SDK를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-221">Includes the Core Common Language Runtime (CoreCLR), the Core AOT Runtime (CoreRT, in development), the Core Base Class Library, and the Core SDK.</span></span>

<span data-ttu-id="b3c31-222">[.NET Core](../core/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-222">See [.NET Core](../core/index.md).</span></span>

## <a name="net-core-cli"></a><span data-ttu-id="b3c31-223">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="b3c31-223">.NET Core CLI</span></span>

<span data-ttu-id="b3c31-224">.NET Core 응용 프로그램을 개발하기 위한 플랫폼 간 도구 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-224">A cross-platform toolchain for developing .NET Core applications.</span></span>

<span data-ttu-id="b3c31-225">[.NET Core CLI(명령줄 인터페이스) 도구](../core/tools/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-225">See [.NET Core command-line interface (CLI) tools](../core/tools/index.md).</span></span>

## <a name="net-core-sdk"></a><span data-ttu-id="b3c31-226">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="b3c31-226">.NET Core SDK</span></span>

<span data-ttu-id="b3c31-227">개발자가 .NET Core 응용 프로그램과 라이브러리를 만드는 데 사용할 수 있는 라이브러리 및 도구 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-227">A set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="b3c31-228">앱을 빌드하기 위한 [.NET Core CLI](#net-core-cli), 앱을 빌드하고 실행하기 위한 .NET Core 라이브러리 및 런타임, CLI 명령을 실행하고 응용 프로그램을 실행하는 dotnet 실행 파일(*dotnet.exe*)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-228">Includes the [.NET Core CLI](#net-core-cli) for building apps, .NET Core libraries and runtime for building and running apps, and the dotnet executable (*dotnet.exe*) that runs CLI commands and runs applications.</span></span>

<span data-ttu-id="b3c31-229">[.NET Core SDK 개요](../core/sdk.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-229">See [.NET Core SDK Overview](../core/sdk.md).</span></span>

## <a name="net-framework"></a><span data-ttu-id="b3c31-230">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="b3c31-230">.NET Framework</span></span>

<span data-ttu-id="b3c31-231">Windows에서만 실행되는 .NET의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-231">An implementation of .NET that runs only on Windows.</span></span> <span data-ttu-id="b3c31-232">CLR(공용 언어 런타임), 기본 클래스 라이브러리 및 ASP.NET, Windows Forms, WPF 등의 응용 프로그램 프레임워크 라이브러리를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-232">Includes the Common Language Runtime (CLR), the Base Class Library, and application framework libraries such as ASP.NET, Windows Forms, and WPF.</span></span>

<span data-ttu-id="b3c31-233">[.NET Framework 가이드](../framework/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-233">See [.NET Framework Guide](../framework/index.md).</span></span>

## <a name="net-native"></a><span data-ttu-id="b3c31-234">.NET 네이티브</span><span class="sxs-lookup"><span data-stu-id="b3c31-234">.NET Native</span></span>

<span data-ttu-id="b3c31-235">JIT(Just-In-Time)와 반대로 네이티브 코드 AOT(Ahead-Of-Time)를 생성하는 컴파일러 도구 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-235">A compiler tool chain that produces native code ahead-of-time (AOT), as opposed to just-in-time (JIT).</span></span>

<span data-ttu-id="b3c31-236">컴파일은 C++ 컴파일러 및 링커가 작동하는 방식과 유사하게 개발자의 컴퓨터에서 수행되며,</span><span class="sxs-lookup"><span data-stu-id="b3c31-236">Compilation happens on the developer's machine similar to the way a C++ compiler and linker works.</span></span> <span data-ttu-id="b3c31-237">사용되지 않는 코드를 제거하고 더 많은 시간을 최적화에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-237">It removes unused code and spends more time optimizing it.</span></span> <span data-ttu-id="b3c31-238">라이브러리에서 코드를 추출하여 실행 파일에 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-238">It extracts code from libraries and merges them into the executable.</span></span> <span data-ttu-id="b3c31-239">결과는 전체 앱을 나타내는 단일 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-239">The result is a single module that represents the entire app.</span></span>

<span data-ttu-id="b3c31-240">UWP는 .NET 네이티브에서 지원하는 첫 번째 응용 프로그램 프레임워크였습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-240">UWP was the first application framework supported by .NET Native.</span></span> <span data-ttu-id="b3c31-241">이제 Windows, macOS 및 Linux용 네이티브 콘솔 앱 작성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-241">Now, we support building native console apps for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="b3c31-242">[.NET 네이티브 및 CoreRT 소개](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-242">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="net-standard"></a><span data-ttu-id="b3c31-243">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="b3c31-243">.NET Standard</span></span>

<span data-ttu-id="b3c31-244">각 .NET 구현에서 사용할 수 있는 .NET API의 공식 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-244">A formal specification of .NET APIs that are available in each .NET implementation.</span></span>

<span data-ttu-id="b3c31-245">.NET Standard 사양은 설명서에서 라이브러리라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-245">The .NET Standard specification is sometimes called a library in the documentation.</span></span> <span data-ttu-id="b3c31-246">라이브러리는 API 구현을 포함하므로 사양(인터페이스)뿐만 아니라 .NET Standard를 “라이브러리”라고 잘못 부르기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-246">Because a library includes API implementations, not only specifications (interfaces), it's misleading to call .NET Standard a "library."</span></span> <span data-ttu-id="b3c31-247">.NET Standard 메타패키지(`NETStandard.Library`)의 이름을 참조할 때를 제외하고 설명서에서 이러한 사용을 제거할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-247">We plan to eliminate that usage from the documentation, except in reference to the name of the .NET Standard metapackage (`NETStandard.Library`).</span></span>

<span data-ttu-id="b3c31-248">[.NET Standard](net-standard.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-248">See [.NET Standard](net-standard.md).</span></span>

## <a name="ngen"></a><span data-ttu-id="b3c31-249">NGEN</span><span class="sxs-lookup"><span data-stu-id="b3c31-249">NGEN</span></span>

<span data-ttu-id="b3c31-250">네이티브(이미지) 생성입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-250">Native (image) generation.</span></span>

<span data-ttu-id="b3c31-251">이 기술을 영구 JIT 컴파일러로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-251">You can think of this technology as a persistent JIT compiler.</span></span> <span data-ttu-id="b3c31-252">일반적으로 코드가 실행되는 컴퓨터에서 코드를 컴파일하지만 컴파일은 대개 설치 시에 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-252">It usually compiles code on the machine where the code is executed, but compilation typically occurs at install time.</span></span>

## <a name="package"></a><span data-ttu-id="b3c31-253">패키지</span><span class="sxs-lookup"><span data-stu-id="b3c31-253">package</span></span>

<span data-ttu-id="b3c31-254">NuGet 패키지(또는 줄여서 패키지)는 작성자 이름과 같은 추가 메타데이터와 함께 동일한 이름의 어셈블리가 하나 이상 있는 .zip 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-254">A NuGet package &mdash; or just a package &mdash; is a *.zip* file with one or more assemblies of the same name along with additional metadata such as the author name.</span></span>

<span data-ttu-id="b3c31-255">*.zip* 파일은 *.nupkg* 확장명을 사용하며 *.dll* 파일 및 *.xml* 파일과 같이 여러 대상 프레임워크 및 버전에서 사용할 자산을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-255">The *.zip* file has a *.nupkg* extension and may contain assets, such as *.dll* files and *.xml* files, for use with multiple target frameworks and versions.</span></span> <span data-ttu-id="b3c31-256">앱 또는 라이브러리에 설치된 경우 앱 또는 라이브러리에서 지정한 대상 프레임워크에 따라 적절한 자산이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-256">When installed in an app or library, the appropriate assets are selected based on the target framework specified by the app or library.</span></span> <span data-ttu-id="b3c31-257">인터페이스를 정의하는 자산은 *ref* 폴더에 있으며 구현을 정의하는 자산은 *lib* 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-257">The assets that define the interface are in the *ref* folder, and the assets that define the implementation are in the *lib* folder.</span></span>

## <a name="platform"></a><span data-ttu-id="b3c31-258">platform</span><span class="sxs-lookup"><span data-stu-id="b3c31-258">platform</span></span>

<span data-ttu-id="b3c31-259">Windows, macOS, Linux, iOS 및 Android 같은 운영 체제와 해당 운영 체제가 실행되는 하드웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-259">An operating system and the hardware it runs on, such as Windows, macOS, Linux, iOS, and Android.</span></span>

<span data-ttu-id="b3c31-260">다음은 문장에서의 사용 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-260">Here are examples of usage in sentences:</span></span>

- <span data-ttu-id="b3c31-261">“.NET Core는 .NET의 플랫폼 간 구현입니다.”</span><span class="sxs-lookup"><span data-stu-id="b3c31-261">".NET Core is a cross-platform implementation of .NET."</span></span> 
- <span data-ttu-id="b3c31-262">“PCL 프로필은 Microsoft 플랫폼을 나타내지만 .NET Standard는 플랫폼에 독립적입니다.”</span><span class="sxs-lookup"><span data-stu-id="b3c31-262">"PCL profiles represent Microsoft platforms, while the .NET Standard is agnostic to platform."</span></span>

<span data-ttu-id="b3c31-263">.NET 설명서에서는 .NET의 구현이나 모든 구현을 포함하는 .NET 스택을 의미하는 데 “.NET 플랫폼”을 자주 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-263">The .NET documentation frequently uses ".NET platform" to mean either an implementation of .NET or the .NET stack including all implementations.</span></span> <span data-ttu-id="b3c31-264">이러한 사용은 모두 기본(OS/하드웨어) 의미와 혼동되므로 설명서에서 이러한 사용을 제거할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-264">Both of these usages tend to get confused with the primary (OS/hardware) meaning, so we plan to eliminate these usages from the documentation.</span></span>

## <a name="runtime"></a><span data-ttu-id="b3c31-265">런타임(runtime)</span><span class="sxs-lookup"><span data-stu-id="b3c31-265">runtime</span></span>

<span data-ttu-id="b3c31-266">관리되는 프로그램에 대한 실행 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-266">The execution environment for a managed program.</span></span>

<span data-ttu-id="b3c31-267">OS는 런타임 환경의 일부이지만 .NET 런타임의 일부는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-267">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="b3c31-268">다음은 .NET 런타임의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-268">Here are some examples of .NET runtimes:</span></span>

- <span data-ttu-id="b3c31-269">CLR(공용 언어 런타임)</span><span class="sxs-lookup"><span data-stu-id="b3c31-269">Common Language Runtime (CLR)</span></span>
- <span data-ttu-id="b3c31-270">CoreCLR(Core 공용 언어 런타임)</span><span class="sxs-lookup"><span data-stu-id="b3c31-270">Core Common Language Runtime (CoreCLR)</span></span>
- <span data-ttu-id="b3c31-271">.NET 네이티브(UWP)</span><span class="sxs-lookup"><span data-stu-id="b3c31-271">.NET Native (for UWP)</span></span>
- <span data-ttu-id="b3c31-272">Mono 런타임</span><span class="sxs-lookup"><span data-stu-id="b3c31-272">Mono runtime</span></span>

<span data-ttu-id="b3c31-273">.NET 설명서에서는 경우에 따라 “런타임”을 사용하여 .NET의 구현을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-273">The .NET documentation sometimes uses "runtime" to mean an implementation of .NET.</span></span> <span data-ttu-id="b3c31-274">예를 들어 다음 문장에서 “런타임”은 “구현”으로 대체되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-274">For example, in the following sentences "runtime" should be replaced with "implementation":</span></span>

- <span data-ttu-id="b3c31-275">“다양한 .NET 런타임에서 특정 버전의 .NET Standard를 구현합니다.”</span><span class="sxs-lookup"><span data-stu-id="b3c31-275">"The various .NET runtimes implement specific versions of .NET Standard."</span></span>
- <span data-ttu-id="b3c31-276">“여러 런타임에서 실행되도록 만들어진 라이브러리는 이 프레임워크를 대상으로 해야 합니다.”</span><span class="sxs-lookup"><span data-stu-id="b3c31-276">"Libraries that are intended to run on multiple runtimes should target this framework."</span></span> <span data-ttu-id="b3c31-277">(.NET Standard를 참조)</span><span class="sxs-lookup"><span data-stu-id="b3c31-277">(referring to .NET Standard)</span></span>
- <span data-ttu-id="b3c31-278">“다양한 .NET 런타임에서 특정 버전의 .NET Standard를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-278">"The various .NET runtimes implement specific versions of .NET Standard.</span></span> <span data-ttu-id="b3c31-279">…</span><span class="sxs-lookup"><span data-stu-id="b3c31-279">…</span></span> <span data-ttu-id="b3c31-280">각 .NET 런타임 버전은 지원하는 최신 .NET Standard 버전을 보급합니다.”</span><span class="sxs-lookup"><span data-stu-id="b3c31-280">Each .NET runtime version advertises the highest .NET Standard version it supports …"</span></span>

<span data-ttu-id="b3c31-281">이러한 일관되지 않은 사용을 제거할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-281">We plan to eliminate this inconsistent usage.</span></span> 

## <a name="stack"></a><span data-ttu-id="b3c31-282">스택</span><span class="sxs-lookup"><span data-stu-id="b3c31-282">stack</span></span>

<span data-ttu-id="b3c31-283">응용 프로그램을 빌드하고 실행하는 데 함께 사용되는 프로그래밍 기술 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-283">A set of programming technologies that are used together to build and run applications.</span></span>

<span data-ttu-id="b3c31-284">“.NET 스택”은 .NET Standard 및 모든 .NET 구현을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-284">"The .NET stack" refers to the .NET Standard and all .NET implementations.</span></span> <span data-ttu-id="b3c31-285">“.NET 스택”이라는 구가 .NET 구현 하나를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-285">The phrase "a .NET stack" may refer to one implementation of .NET.</span></span> 

## <a name="target-framework"></a><span data-ttu-id="b3c31-286">대상 프레임워크(target framework)</span><span class="sxs-lookup"><span data-stu-id="b3c31-286">target framework</span></span>

<span data-ttu-id="b3c31-287">.NET 앱 또는 라이브러리에서 사용하는 API 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-287">The collection of APIs that a .NET app or library relies on.</span></span>

<span data-ttu-id="b3c31-288">앱 또는 라이브러리는 모든.NET 구현에서 표준화된 API 집합에 대한 사양인 .NET Standard의 버전(예: .NET Standard 2.0)을 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-288">An app or library can target a version of .NET Standard (for example, .NET Standard 2.0), which is specification for a standardized set of APIs across all .NET implementations.</span></span> <span data-ttu-id="b3c31-289">또한 앱 또는 라이브러리는 특정 .NET 구현의 버전을 대상으로 할 수 있으며, 이 경우 구현 관련 API에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-289">An app or library can also target a version of a specific .NET implementation, in which case it gets access to implementation-specific APIs.</span></span> <span data-ttu-id="b3c31-290">예를 들어 Xamarin.iOS를 대상으로 하는 앱은 Xamarin 제공 iOS API 래퍼에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-290">For example, an app that targets Xamarin.iOS gets access to Xamarin-provided iOS API wrappers.</span></span>

<span data-ttu-id="b3c31-291">일부 대상 프레임워크(예: .NET Framework)에서 사용 가능한 API는 .NET 구현에서 시스템에 설치하는 어셈블리에 의해 정의되고 응용 프로그램 프레임워크 API(예: ASP.NET, WinForms)를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-291">For some target frameworks (for example, the .NET Framework) the available APIs are defined by the assemblies that a .NET implementation installs on a system, which may include application framework APIs (for example, ASP.NET, WinForms).</span></span> <span data-ttu-id="b3c31-292">패키지 기반 대상 프레임워크(예: .NET Standard 및 .NET Core)에서 프레임워크 API는 앱이나 라이브러리에 설치된 패키지에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-292">For package-based target frameworks (such as .NET Standard and .NET Core), the framework APIs are defined by the packages installed in the app or library.</span></span> <span data-ttu-id="b3c31-293">이 경우 대상 프레임워크는 함께 모여 프레임워크를 구성하는 모든 패키지를 참조하는 메타패키지를 암시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-293">In that case, the target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

<span data-ttu-id="b3c31-294">[대상 프레임워크](frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-294">See [Target Frameworks](frameworks.md).</span></span>

## <a name="tfm"></a><span data-ttu-id="b3c31-295">TFM</span><span class="sxs-lookup"><span data-stu-id="b3c31-295">TFM</span></span>

<span data-ttu-id="b3c31-296">대상 프레임워크 모니커입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-296">Target framework moniker.</span></span>

<span data-ttu-id="b3c31-297">.NET 앱 또는 라이브러리의 대상 프레임워크를 지정하기 위해 표준화된 토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-297">A standardized token format for specifying the target framework of a .NET app or library.</span></span> <span data-ttu-id="b3c31-298">대상 프레임워크는 일반적으로 `net462` 같은 짧은 이름으로 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-298">Target frameworks are typically referenced by a short name, such as `net462`.</span></span> <span data-ttu-id="b3c31-299">긴 형식의 TFM(예: .NETFramework,Version=4.6.2)이 있지만 대상 프레임워크를 지정하는 데 일반적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-299">Long-form TFMs (such as .NETFramework,Version=4.6.2) exist but are not generally used to specify a target framework.</span></span>

<span data-ttu-id="b3c31-300">[대상 프레임워크](frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3c31-300">See [Target Frameworks](frameworks.md).</span></span>

## <a name="uwp"></a><span data-ttu-id="b3c31-301">UWP</span><span class="sxs-lookup"><span data-stu-id="b3c31-301">UWP</span></span>

<span data-ttu-id="b3c31-302">유니버설 Windows 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-302">Universal Windows Platform.</span></span>

<span data-ttu-id="b3c31-303">IoT(사물 인터넷)에 대한 최신 터치 가능 Windows 응용 프로그램 및 소프트웨어를 작성하는 데 사용되는 .NET의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-303">An implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="b3c31-304">PC, 태블릿, 패블릿, 휴대폰, Xbox 등 대상으로 지정할 수 있는 다양한 종류의 장치를 통합하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-304">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="b3c31-305">UWP는 중앙 집중식 앱 스토어, 실행 환경(AppContainer), Win32 대신 사용할 Windows API 집합(WinRT) 등 많은 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-305">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="b3c31-306">앱은 C++, C#, VB.NET 및 JavaScript로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-306">Apps can be written in C++, C#, VB.NET, and JavaScript.</span></span> <span data-ttu-id="b3c31-307">C# 및 VB.NET을 사용할 경우 .NET API는 .NET Core에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3c31-307">When using C# and VB.NET, the .NET APIs are provided by .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3c31-308">참고자료</span><span class="sxs-lookup"><span data-stu-id="b3c31-308">See also</span></span>

[<span data-ttu-id="b3c31-309">.NET 가이드</span><span class="sxs-lookup"><span data-stu-id="b3c31-309">.NET Guide</span></span>](index.md)  
[<span data-ttu-id="b3c31-310">.NET Framework 가이드</span><span class="sxs-lookup"><span data-stu-id="b3c31-310">.NET Framework Guide</span></span>](../framework/index.md)  
[<span data-ttu-id="b3c31-311">.NET Core</span><span class="sxs-lookup"><span data-stu-id="b3c31-311">.NET Core</span></span>](../core/index.md)  
[<span data-ttu-id="b3c31-312">ASP.NET 개요</span><span class="sxs-lookup"><span data-stu-id="b3c31-312">ASP.NET Overview</span></span>](/aspnet/index#pivot=aspnet)  
[<span data-ttu-id="b3c31-313">ASP.NET Core 개요</span><span class="sxs-lookup"><span data-stu-id="b3c31-313">ASP.NET Core Overview</span></span>](/aspnet/index#pivot=core)  

