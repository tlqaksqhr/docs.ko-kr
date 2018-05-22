---
title: .NET 용어
description: .NET 설명서에서 사용되는 선택한 용어의 의미를 알아봅니다.
author: tdykstra
ms.author: tdykstra
ms.date: 07/08/2017
ms.technology: dotnet-standard
ms.openlocfilehash: 195fbb799432b9d01a5faf301c9f8f2d1edfa1ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="net-glossary"></a><span data-ttu-id="dc535-103">.NET 용어</span><span class="sxs-lookup"><span data-stu-id="dc535-103">.NET Glossary</span></span>

<span data-ttu-id="dc535-104">이 용어집의 주 용도는 .NET 설명서에서 정의 없이 자주 나타나는 선택한 용어 및 머리글자어의 의미를 명확히 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-104">The primary goal of this glossary is to clarify meanings of selected terms and acronyms that appear frequently in the .NET documentation without definitions.</span></span>

## <a name="aot"></a><span data-ttu-id="dc535-105">AOT</span><span class="sxs-lookup"><span data-stu-id="dc535-105">AOT</span></span>

<span data-ttu-id="dc535-106">Ahead-Of-Time 컴파일러입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-106">Ahead-of-time compiler.</span></span>

<span data-ttu-id="dc535-107">[JIT](#jit)와 비슷한 이 컴파일러도 [IL](#il)을 기계어 코드로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-107">Similar to [JIT](#jit), this compiler also translates [IL](#il) to machine code.</span></span> <span data-ttu-id="dc535-108">JIT 컴파일과 달리 AOT 컴파일은 응용 프로그램이 실행되기 전에 수행되며 일반적으로 다른 컴퓨터에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-108">In contrast to JIT compilation, AOT compilation happens before the application is executed and is usually performed on a different machine.</span></span> <span data-ttu-id="dc535-109">AOT 도구 체인은 런타임에 컴파일되지 않으므로 컴파일 시간을 최소화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-109">Because AOT tool chains don't compile at runtime, they don't have to minimize time spent compiling.</span></span> <span data-ttu-id="dc535-110">즉, 더 많은 시간을 최적화하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-110">That means they can spend more time optimizing.</span></span> <span data-ttu-id="dc535-111">AOT의 컨텍스트는 전체 응용 프로그램이므로 AOT 컴파일러는 모듈 간 연결 및 전체 프로그램 분석도 수행합니다. 즉, 모든 참조가 수행되고 단일 실행 파일이 생성된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-111">Since the context of AOT is the entire application, the AOT compiler also performs cross-module linking and whole-program analysis, which means that all references are followed and a single executable is produced.</span></span>

## <a name="aspnet"></a><span data-ttu-id="dc535-112">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="dc535-112">ASP.NET</span></span> 

<span data-ttu-id="dc535-113">.NET Framework와 함께 제공되는 원래 ASP.NET 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-113">The original ASP.NET implementation that ships with the .NET Framework.</span></span>

<span data-ttu-id="dc535-114">경우에 따라 ASP.NET은 ASP.NET Core를 포함하여 두 ASP.NET 구현을 나타내는 포괄적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-114">Sometimes ASP.NET is an umbrella term that refers to both ASP.NET implementations including ASP.NET Core.</span></span> <span data-ttu-id="dc535-115">지정된 인스턴스에서 이 용어가 전달하는 의미는 컨텍스트에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-115">The meaning that the term carries in any given instance is determined by context.</span></span> <span data-ttu-id="dc535-116">두 구현을 모두 의미하는 데 ASP.NET을 사용하지 않는 것을 분명히 하려는 경우 ASP.NET 4.x를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-116">Refer to ASP.NET 4.x when you want to make it clear that you’re not using ASP.NET to mean both implementations.</span></span> 

<span data-ttu-id="dc535-117">[ASP.NET 설명서](/aspnet/#pivot=aspnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-117">See [ASP.NET documentation](/aspnet/#pivot=aspnet).</span></span>

## <a name="aspnet-core"></a><span data-ttu-id="dc535-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dc535-118">ASP.NET Core</span></span>

<span data-ttu-id="dc535-119">.NET Core를 기반으로 하는 ASP.NET의 플랫폼 간 고성능 오픈 소스 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-119">A cross-platform, high-performance, open source implementation of ASP.NET built on .NET Core.</span></span>

<span data-ttu-id="dc535-120">[ASP.NET Core 설명서](/aspnet/#pivot=core)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-120">See [ASP.NET Core documentation](/aspnet/#pivot=core).</span></span>

## <a name="assembly"></a><span data-ttu-id="dc535-121">어셈블리</span><span class="sxs-lookup"><span data-stu-id="dc535-121">assembly</span></span>

<span data-ttu-id="dc535-122">앱이나 다른 어셈블리에서 호출할 수 있는 API 컬렉션을 포함할 수 있는 *.dll*/*.exe* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-122">A *.dll*/*.exe* file that can contain a collection of APIs that can be called by apps or other assemblies.</span></span>

<span data-ttu-id="dc535-123">어셈블리에는 인터페이스, 클래스, 구조체, 열거형 및 대리자와 같은 형식이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-123">An assembly may include types such as interfaces, classes, structures, enumerations, and delegates.</span></span> <span data-ttu-id="dc535-124">프로젝트의 *bin* 폴더에 있는 어셈블리를 *바이너리*라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-124">Assemblies in a project's *bin* folder are sometimes referred to as *binaries*.</span></span> <span data-ttu-id="dc535-125">[라이브러리](#library)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-125">See also [library](#library).</span></span>

## <a name="clr"></a><span data-ttu-id="dc535-126">CLR</span><span class="sxs-lookup"><span data-stu-id="dc535-126">CLR</span></span>

<span data-ttu-id="dc535-127">공용 언어 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-127">Common Language Runtime.</span></span>

<span data-ttu-id="dc535-128">정확한 의미는 컨텍스트에 따라 달라지지만 일반적으로 .NET Framework의 런타임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-128">The exact meaning depends on the context, but this usually refers to the runtime of the .NET Framework.</span></span> <span data-ttu-id="dc535-129">CLR은 메모리 할당 및 관리를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-129">The CLR handles memory allocation and management.</span></span> <span data-ttu-id="dc535-130">또한 CLR은 앱을 실행할 뿐만 아니라 JIT 컴파일러를 사용하여 즉시 코드를 생성하고 컴파일하는 가상 머신입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-130">The CLR is also a virtual machine that not only executes apps but also generates and compiles code on-the-fly using a JIT compiler.</span></span> <span data-ttu-id="dc535-131">현재 Microsoft CLR 구현은 Windows 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-131">The current Microsoft CLR implementation is Windows only.</span></span>

## <a name="coreclr"></a><span data-ttu-id="dc535-132">CoreCLR</span><span class="sxs-lookup"><span data-stu-id="dc535-132">CoreCLR</span></span>

<span data-ttu-id="dc535-133">.NET Core 공용 언어 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-133">.NET Core Common Language Runtime.</span></span>

<span data-ttu-id="dc535-134">이 CLR은 CLR과 동일한 코드베이스에서 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-134">This CLR is built from the same code base as the CLR.</span></span> <span data-ttu-id="dc535-135">원래 CoreCLR은 Silverlight의 런타임이었으며 여러 플랫폼, 특히 Windows 및 OS X에서 실행되도록 설계되었습니다. 이제 CoreCLR은 .NET Core의 일부이며 CLR의 단순화된 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-135">Originally, CoreCLR was the runtime of Silverlight and was designed to run on multiple platforms, specifically Windows and OS X. CoreCLR is now part of .NET Core and represents a simplified version of the CLR.</span></span> <span data-ttu-id="dc535-136">이제 많은 Linux 배포에 대한 지원을 포함하는 플랫폼 간 런타임이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-136">It's still a cross platform runtime, now including support for many Linux distributions.</span></span> <span data-ttu-id="dc535-137">CoreCLR은 JIT 및 코드 실행 기능이 있는 가상 머신이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-137">CoreCLR is also a virtual machine with JIT and code execution capabilities.</span></span>

## <a name="corefx"></a><span data-ttu-id="dc535-138">CoreFX</span><span class="sxs-lookup"><span data-stu-id="dc535-138">CoreFX</span></span>

<span data-ttu-id="dc535-139">.NET Core BCL(기본 클래스 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="dc535-139">.NET Core Base Class Library (BCL)</span></span>

<span data-ttu-id="dc535-140">System.*(및 제한된 범위의 Microsoft.*) 네임스페이스를 구성하는 라이브러리 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-140">A set of libraries that comprise the System.* (and to a limited extent  Microsoft.*) namespaces.</span></span> <span data-ttu-id="dc535-141">BCL은 ASP.NET Core 같은 상위 수준 응용 프로그램 프레임워크의 기반이 되는 하위 수준의 범용 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-141">The BCL is a general purpose, lower-level framework that higher-level application frameworks, such as ASP.NET Core, build on.</span></span> <span data-ttu-id="dc535-142">.NET Core BCL의 소스 코드는 [CoreFX 리포지토리](https://github.com/dotnet/corefx)에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-142">The source code of the .NET Core BCL is contained in the [CoreFX repository](https://github.com/dotnet/corefx).</span></span> <span data-ttu-id="dc535-143">그러나 대부분의 .NET Core API는 .NET Framework에서 사용할 수도 있으므로 CoreFX를 .NET Framework BCL의 포크로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-143">However, the majority of the .NET Core APIs are also available in the .NET Framework, so you can think of CoreFX as a fork of the .NET Framework BCL.</span></span>

## <a name="corert"></a><span data-ttu-id="dc535-144">CoreRT</span><span class="sxs-lookup"><span data-stu-id="dc535-144">CoreRT</span></span>

<span data-ttu-id="dc535-145">.NET Core 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-145">.NET Core runtime.</span></span>

<span data-ttu-id="dc535-146">CLR/CoreCLR과 달리 CoreRT는 가상 머신이 아닙니다. 즉, [JIT](#jit)를 포함하지 않으므로 즉시 코드를 생성하고 실행하는 기능을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-146">In contrast to the CLR/CoreCLR, CoreRT is not a virtual machine, which means it doesn't include the facilities to generate and run code on-the-fly because it doesn't include a [JIT](#jit).</span></span> <span data-ttu-id="dc535-147">그러나 [GC](#gc)와 RTTI(런타임 형식 식별) 및 리플렉션에 대한 기능은 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-147">It does, however, include the [GC](#gc) and the ability for runtime type identification (RTTI) and reflection.</span></span> <span data-ttu-id="dc535-148">그러나 해당 형식 시스템은 리플렉션에 대한 메타데이터가 필요하지 않도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-148">However, its type system is designed so that metadata for reflection isn't required.</span></span> <span data-ttu-id="dc535-149">따라서 불필요한 메타데이터를 분리하고 더 중요하게는 앱이 사용하지 않는 코드를 식별할 수 있는 [AOT](#aot) 도구 체인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-149">This enables having an [AOT](#aot) tool chain that can link away superfluous metadata and (more importantly) identify code that the app doesn't use.</span></span> <span data-ttu-id="dc535-150">CoreRT는 개발 중입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-150">CoreRT is in development.</span></span>

<span data-ttu-id="dc535-151">[.NET 네이티브 및 CoreRT 소개](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-151">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="ecosystem"></a><span data-ttu-id="dc535-152">에코시스템</span><span class="sxs-lookup"><span data-stu-id="dc535-152">ecosystem</span></span>

<span data-ttu-id="dc535-153">특정 기술에 대한 응용 프로그램을 빌드하고 실행하는 데 사용되는 모든 런타임 소프트웨어, 개발 도구 및 커뮤니티 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-153">All of the runtime software, development tools, and community resources that are used to build and run applications for a given technology.</span></span>

<span data-ttu-id="dc535-154">“.NET 에코시스템”이라는 용어는 타사 앱 및 라이브러리를 포함한다는 점에서 “.NET 스택”과 같은 유사한 용어와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-154">The term ".NET ecosystem" differs from similar terms such as ".NET stack" in its inclusion of third-party apps and libraries.</span></span> <span data-ttu-id="dc535-155">다음은 문장에서의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-155">Here's an example in a sentence:</span></span>

- <span data-ttu-id="dc535-156">“[.NET Standard](#net-standard)는 .NET 에코시스템의 균일성을 높이기 위한 것입니다.”</span><span class="sxs-lookup"><span data-stu-id="dc535-156">"The motivation behind the [.NET Standard](#net-standard) is to establish greater uniformity in the .NET ecosystem."</span></span> 

## <a name="framework"></a><span data-ttu-id="dc535-157">프레임워크</span><span class="sxs-lookup"><span data-stu-id="dc535-157">framework</span></span>

<span data-ttu-id="dc535-158">일반적으로 특정 기술을 기반으로 하는 응용 프로그램의 개발 및 배포를 용이하게 하는 포괄적인 API 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-158">In general, a comprehensive collection of APIs that facilitates development and deployment of applications that are based on a particular technology.</span></span> <span data-ttu-id="dc535-159">이 일반적인 의미에서 ASP.NET Core 및 Windows Forms는 응용 프로그램 프레임워크의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-159">In this general sense, ASP.NET Core and Windows Forms are examples of application frameworks.</span></span> <span data-ttu-id="dc535-160">[라이브러리](#library)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-160">See also [library](#library).</span></span>

<span data-ttu-id="dc535-161">“프레임 워크”라는 단어는 다음과 같은 용어에서 좀 더 구체적인 기술적 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-161">The word "framework" has a more specific technical meaning in the following terms:</span></span>
* [<span data-ttu-id="dc535-162">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc535-162">.NET Framework</span></span>](#net-framework)
* [<span data-ttu-id="dc535-163">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="dc535-163">target framework</span></span>](#target-framework)
* [<span data-ttu-id="dc535-164">TFM(대상 프레임워크 모니커)</span><span class="sxs-lookup"><span data-stu-id="dc535-164">TFM (target framework moniker)</span></span>](#tfm)

<span data-ttu-id="dc535-165">기존 설명서에서 “프레임워크”는 경우에 따라 [.NET의 구현](#implementation-of-net)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-165">In the existing documentation, "framework" sometimes refers to an [implementation of .NET](#implementation-of-net).</span></span> <span data-ttu-id="dc535-166">예를 들어 문서에서 .NET Core를 프레임워크라고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-166">For example, an article may call .NET Core a framework.</span></span> <span data-ttu-id="dc535-167">설명서에서 혼동을 주는 이러한 사용을 제거할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-167">We plan to eliminate this confusing usage from the documentation.</span></span>

## <a name="gc"></a><span data-ttu-id="dc535-168">GC</span><span class="sxs-lookup"><span data-stu-id="dc535-168">GC</span></span>

<span data-ttu-id="dc535-169">가비지 수집기입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-169">Garbage collector.</span></span>

<span data-ttu-id="dc535-170">가비지 수집기는 자동 메모리 관리의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-170">The garbage collector is an implementation of automatic memory management.</span></span>  <span data-ttu-id="dc535-171">GC는 개체가 사용한 메모리에서 더 이상 사용되지 않는 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-171">The GC frees memory occupied by objects that are no longer in use.</span></span> 

<span data-ttu-id="dc535-172">[가비지 수집](garbage-collection/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-172">See [Garbage Collection](garbage-collection/index.md).</span></span>

## <a name="il"></a><span data-ttu-id="dc535-173">IL</span><span class="sxs-lookup"><span data-stu-id="dc535-173">IL</span></span>

<span data-ttu-id="dc535-174">중간 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-174">Intermediate language.</span></span>

<span data-ttu-id="dc535-175">C#과 같은 상위 수준 .NET 언어가 IL(중간 언어)이라는 하드웨어 독립 명령 집합으로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-175">Higher-level .NET languages, such as C#, compile down to a hardware-agnostic instruction set, which is called Intermediate Language (IL).</span></span> <span data-ttu-id="dc535-176">IL은 MSIL(Microsoft IL) 또는 CIL(공통 IL)이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-176">IL is sometimes referred to as MSIL (Microsoft IL) or CIL (Common IL).</span></span>

## <a name="jit"></a><span data-ttu-id="dc535-177">JIT</span><span class="sxs-lookup"><span data-stu-id="dc535-177">JIT</span></span>

<span data-ttu-id="dc535-178">Just-In-Time 컴파일러입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-178">Just-in-time compiler.</span></span>

<span data-ttu-id="dc535-179">[AOT](#aot)와 유사한 이 컴파일러는 [IL](#il)을 프로세서에서 이해하는 기계어 코드로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-179">Similar to [AOT](#aot), this compiler translates [IL](#il) to machine code that the processor understands.</span></span> <span data-ttu-id="dc535-180">AOT와 달리 JIT 컴파일은 요청 시 수행되며 코드가 실행되어야 하는 것과 동일한 컴퓨터에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-180">Unlike AOT, JIT compilation happens on demand and is performed on the same machine that the code needs to run on.</span></span> <span data-ttu-id="dc535-181">JIT 컴파일은 응용 프로그램이 실행되는 동안 수행되므로 컴파일 시간이 실행 시간의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-181">Since JIT compilation occurs during execution of the application, compile time is part of the run time.</span></span> <span data-ttu-id="dc535-182">따라서 JIT 컴파일러는 결과 코드가 생성할 수 있는 시간 단축과 코드 최적화에 소요된 시간의 균형을 맞춰야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-182">Thus, JIT compilers have to balance time spent optimizing code against the savings that the resulting code can produce.</span></span> <span data-ttu-id="dc535-183">그러나 JIT는 실제 하드웨어를 인식하므로 개발자가 다른 구현을 제공할 필요가 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-183">But a JIT knows the actual hardware and can free developers from having to ship different implementations.</span></span>

## <a name="implementation-of-net"></a><span data-ttu-id="dc535-184">.NET의 구현</span><span class="sxs-lookup"><span data-stu-id="dc535-184">implementation of .NET</span></span>

<span data-ttu-id="dc535-185">.NET의 구현에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-185">An implementation of .NET includes the following:</span></span>

- <span data-ttu-id="dc535-186">하나 이상의 런타임.</span><span class="sxs-lookup"><span data-stu-id="dc535-186">One or more runtimes.</span></span> <span data-ttu-id="dc535-187">예를 들어 CLR, CoreCLR, CoreRT가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-187">Examples: CLR, CoreCLR, CoreRT.</span></span>
- <span data-ttu-id="dc535-188">.NET Standard의 버전을 구현하고 추가 API를 포함할 수 있는 클래스 라이브러리.</span><span class="sxs-lookup"><span data-stu-id="dc535-188">A class library that implements a version of the .NET Standard and may include additional APIs.</span></span> <span data-ttu-id="dc535-189">예를 들어 .NET Framework 기본 클래스 라이브러리, .NET Core 기본 클래스 라이브러리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-189">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="dc535-190">필요에 따라 하나 이상의 응용 프로그램 프레임워크.</span><span class="sxs-lookup"><span data-stu-id="dc535-190">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="dc535-191">예를 들어 ASP.NET, Windows Forms 및 WPF가 .NET Framework에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-191">Examples: ASP.NET, Windows Forms, and WPF are included in the .NET Framework.</span></span>
- <span data-ttu-id="dc535-192">필요에 따라 개발 도구.</span><span class="sxs-lookup"><span data-stu-id="dc535-192">Optionally, development tools.</span></span> <span data-ttu-id="dc535-193">일부 개발 도구는 여러 구현에서 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-193">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="dc535-194">.NET 구현의 예:</span><span class="sxs-lookup"><span data-stu-id="dc535-194">Examples of .NET implementations:</span></span>

- [<span data-ttu-id="dc535-195">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc535-195">.NET Framework</span></span>](#net-framework)
- [<span data-ttu-id="dc535-196">.NET Core</span><span class="sxs-lookup"><span data-stu-id="dc535-196">.NET Core</span></span>](#net-core)
- [<span data-ttu-id="dc535-197">UWP(유니버설 Windows 플랫폼)</span><span class="sxs-lookup"><span data-stu-id="dc535-197">Universal Windows Platform (UWP)</span></span>](#uwp)

## <a name="library"></a><span data-ttu-id="dc535-198">라이브러리</span><span class="sxs-lookup"><span data-stu-id="dc535-198">library</span></span>

<span data-ttu-id="dc535-199">앱이나 다른 라이브러리에서 호출할 수 있는 API 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-199">A collection of APIs that can be called by apps or other libraries.</span></span> <span data-ttu-id="dc535-200">.NET 라이브러리는 하나 이상의 [어셈블리](#assembly)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-200">A .NET library is composed of one or more [assemblies](#assembly).</span></span>

<span data-ttu-id="dc535-201">라이브러리 및 [프레임워크](#framework)라는 단어는 종종 같은 뜻으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-201">The words library and [framework](#framework) are often used synonymously.</span></span>

## <a name="metapackage"></a><span data-ttu-id="dc535-202">메타패키지</span><span class="sxs-lookup"><span data-stu-id="dc535-202">metapackage</span></span>

<span data-ttu-id="dc535-203">고유한 라이브러리는 없지만 유일한 종속성 목록인 NuGet 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-203">A NuGet package that has no library of its own but is only a list of dependencies.</span></span> <span data-ttu-id="dc535-204">포함된 패키지는 필요에 따라 대상 프레임워크에 대한 API를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-204">The included packages can optionally establish the API for a target framework.</span></span>

<span data-ttu-id="dc535-205">[패키지, 메타패키지 및 프레임워크](../core/packages.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-205">See [Packages, Metapackages and Frameworks](../core/packages.md)</span></span>

## <a name="mono"></a><span data-ttu-id="dc535-206">Mono</span><span class="sxs-lookup"><span data-stu-id="dc535-206">Mono</span></span>

<span data-ttu-id="dc535-207">Mono는 작은 런타임이 필요할 때 주로 사용되는 .NET 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-207">Mono is a .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="dc535-208">이는 Android, Mac, iOS, tvOS 및 watchOS에서 Xamarin 응용 프로그램의 성능을 향상하는 런타임으로, 주로 작은 사용 공간이 필요한 앱에 초점을 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-208">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on apps that require a small footprint.</span></span>

<span data-ttu-id="dc535-209">Mono는 현재 게시된 .NET Standard 버전을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-209">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="dc535-210">지금까지 Mono는 .NET Framework의 더 큰 API를 구현하고 Unix에서 가장 인기 있는 기능 중 일부를 에뮬레이트했습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-210">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="dc535-211">경우에 따라 Unix에서 해당 기능을 사용하는 .NET 응용 프로그램을 실행하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-211">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="dc535-212">일반적으로 Mono는 Just-In-Time 컴파일러에서 사용되지만 iOS 같은 플랫폼에 사용되는 전체 정적 컴파일러(Ahead-Of-Time 컴파일) 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-212">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="dc535-213">Mono에 대한 자세한 내용은 [Mono 설명서](https://www.mono-project.com/docs/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-213">To learn more about Mono, see the [Mono documentation](https://www.mono-project.com/docs/).</span></span>

## <a name="net"></a><span data-ttu-id="dc535-214">.NET</span><span class="sxs-lookup"><span data-stu-id="dc535-214">.NET</span></span>

<span data-ttu-id="dc535-215">[.NET Standard](#net-standard) 및 모든 [.NET 구현](#implementation-of-net)과 워크로드에 대한 포괄적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-215">The umbrella term for [.NET Standard](#net-standard) and all [.NET implementations](#implementation-of-net) and workloads.</span></span> <span data-ttu-id="dc535-216">항상 대문자로 표기되며, “.Net”이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-216">Always capitalized, never ".Net".</span></span>

<span data-ttu-id="dc535-217">[.NET 가이드](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-217">See the [.NET Guide](index.md)</span></span>

## <a name="net-core"></a><span data-ttu-id="dc535-218">.NET Core</span><span class="sxs-lookup"><span data-stu-id="dc535-218">.NET Core</span></span> 

<span data-ttu-id="dc535-219">.NET의 플랫폼 간 고성능 오픈 소스 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-219">A cross-platform, high-performance, open source implementation of .NET.</span></span> <span data-ttu-id="dc535-220">CoreCLR(Core 공용 언어 런타임), Core AOT 런타임(CoreRT, 개발 중), Core 기본 클래스 라이브러리 및 Core SDK를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-220">Includes the Core Common Language Runtime (CoreCLR), the Core AOT Runtime (CoreRT, in development), the Core Base Class Library, and the Core SDK.</span></span>

<span data-ttu-id="dc535-221">[.NET Core](../core/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-221">See [.NET Core](../core/index.md).</span></span>

## <a name="net-core-cli"></a><span data-ttu-id="dc535-222">.NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="dc535-222">.NET Core CLI</span></span>

<span data-ttu-id="dc535-223">.NET Core 응용 프로그램을 개발하기 위한 플랫폼 간 도구 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-223">A cross-platform toolchain for developing .NET Core applications.</span></span>

<span data-ttu-id="dc535-224">[.NET Core CLI(명령줄 인터페이스) 도구](../core/tools/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-224">See [.NET Core command-line interface (CLI) tools](../core/tools/index.md).</span></span>

## <a name="net-core-sdk"></a><span data-ttu-id="dc535-225">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="dc535-225">.NET Core SDK</span></span>

<span data-ttu-id="dc535-226">개발자가 .NET Core 응용 프로그램과 라이브러리를 만드는 데 사용할 수 있는 라이브러리 및 도구 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-226">A set of libraries and tools that allow developers to create .NET Core applications and libraries.</span></span> <span data-ttu-id="dc535-227">앱을 빌드하기 위한 [.NET Core CLI](#net-core-cli), 앱을 빌드하고 실행하기 위한 .NET Core 라이브러리 및 런타임, CLI 명령을 실행하고 응용 프로그램을 실행하는 dotnet 실행 파일(*dotnet.exe*)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-227">Includes the [.NET Core CLI](#net-core-cli) for building apps, .NET Core libraries and runtime for building and running apps, and the dotnet executable (*dotnet.exe*) that runs CLI commands and runs applications.</span></span>

<span data-ttu-id="dc535-228">[.NET Core SDK 개요](../core/sdk.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-228">See [.NET Core SDK Overview](../core/sdk.md).</span></span>

## <a name="net-framework"></a><span data-ttu-id="dc535-229">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc535-229">.NET Framework</span></span>

<span data-ttu-id="dc535-230">Windows에서만 실행되는 .NET의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-230">An implementation of .NET that runs only on Windows.</span></span> <span data-ttu-id="dc535-231">CLR(공용 언어 런타임), 기본 클래스 라이브러리 및 ASP.NET, Windows Forms, WPF 등의 응용 프로그램 프레임워크 라이브러리를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-231">Includes the Common Language Runtime (CLR), the Base Class Library, and application framework libraries such as ASP.NET, Windows Forms, and WPF.</span></span>

<span data-ttu-id="dc535-232">[.NET Framework 가이드](../framework/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-232">See [.NET Framework Guide](../framework/index.md).</span></span>

## <a name="net-native"></a><span data-ttu-id="dc535-233">.NET 네이티브</span><span class="sxs-lookup"><span data-stu-id="dc535-233">.NET Native</span></span>

<span data-ttu-id="dc535-234">JIT(Just-In-Time)와 반대로 네이티브 코드 AOT(Ahead-Of-Time)를 생성하는 컴파일러 도구 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-234">A compiler tool chain that produces native code ahead-of-time (AOT), as opposed to just-in-time (JIT).</span></span>

<span data-ttu-id="dc535-235">컴파일은 C++ 컴파일러 및 링커가 작동하는 방식과 유사하게 개발자의 컴퓨터에서 수행되며,</span><span class="sxs-lookup"><span data-stu-id="dc535-235">Compilation happens on the developer's machine similar to the way a C++ compiler and linker works.</span></span> <span data-ttu-id="dc535-236">사용되지 않는 코드를 제거하고 더 많은 시간을 최적화에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-236">It removes unused code and spends more time optimizing it.</span></span> <span data-ttu-id="dc535-237">라이브러리에서 코드를 추출하여 실행 파일에 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-237">It extracts code from libraries and merges them into the executable.</span></span> <span data-ttu-id="dc535-238">결과는 전체 앱을 나타내는 단일 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-238">The result is a single module that represents the entire app.</span></span>

<span data-ttu-id="dc535-239">UWP는 .NET 네이티브에서 지원하는 첫 번째 응용 프로그램 프레임워크였습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-239">UWP was the first application framework supported by .NET Native.</span></span> <span data-ttu-id="dc535-240">이제 Windows, macOS 및 Linux용 네이티브 콘솔 앱 작성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-240">Now, we support building native console apps for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="dc535-241">[.NET 네이티브 및 CoreRT 소개](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-241">See [Intro to .NET Native and CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)</span></span>

## <a name="net-standard"></a><span data-ttu-id="dc535-242">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="dc535-242">.NET Standard</span></span>

<span data-ttu-id="dc535-243">각 .NET 구현에서 사용할 수 있는 .NET API의 공식 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-243">A formal specification of .NET APIs that are available in each .NET implementation.</span></span>

<span data-ttu-id="dc535-244">.NET Standard 사양은 설명서에서 라이브러리라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-244">The .NET Standard specification is sometimes called a library in the documentation.</span></span> <span data-ttu-id="dc535-245">라이브러리는 API 구현을 포함하므로 사양(인터페이스)뿐만 아니라 .NET Standard를 “라이브러리”라고 잘못 부르기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-245">Because a library includes API implementations, not only specifications (interfaces), it's misleading to call .NET Standard a "library."</span></span> <span data-ttu-id="dc535-246">.NET Standard 메타패키지(`NETStandard.Library`)의 이름을 참조할 때를 제외하고 설명서에서 이러한 사용을 제거할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-246">We plan to eliminate that usage from the documentation, except in reference to the name of the .NET Standard metapackage (`NETStandard.Library`).</span></span>

<span data-ttu-id="dc535-247">[.NET Standard](net-standard.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-247">See [.NET Standard](net-standard.md).</span></span>

## <a name="ngen"></a><span data-ttu-id="dc535-248">NGEN</span><span class="sxs-lookup"><span data-stu-id="dc535-248">NGEN</span></span>

<span data-ttu-id="dc535-249">네이티브(이미지) 생성입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-249">Native (image) generation.</span></span>

<span data-ttu-id="dc535-250">이 기술을 영구 JIT 컴파일러로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-250">You can think of this technology as a persistent JIT compiler.</span></span> <span data-ttu-id="dc535-251">일반적으로 코드가 실행되는 컴퓨터에서 코드를 컴파일하지만 컴파일은 대개 설치 시에 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-251">It usually compiles code on the machine where the code is executed, but compilation typically occurs at install time.</span></span>

## <a name="package"></a><span data-ttu-id="dc535-252">패키지</span><span class="sxs-lookup"><span data-stu-id="dc535-252">package</span></span>

<span data-ttu-id="dc535-253">NuGet 패키지(또는 줄여서 패키지)는 작성자 이름과 같은 추가 메타데이터와 함께 동일한 이름의 어셈블리가 하나 이상 있는 .zip 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-253">A NuGet package &mdash; or just a package &mdash; is a *.zip* file with one or more assemblies of the same name along with additional metadata such as the author name.</span></span>

<span data-ttu-id="dc535-254">*.zip* 파일은 *.nupkg* 확장명을 사용하며 *.dll* 파일 및 *.xml* 파일과 같이 여러 대상 프레임워크 및 버전에서 사용할 자산을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-254">The *.zip* file has a *.nupkg* extension and may contain assets, such as *.dll* files and *.xml* files, for use with multiple target frameworks and versions.</span></span> <span data-ttu-id="dc535-255">앱 또는 라이브러리에 설치된 경우 앱 또는 라이브러리에서 지정한 대상 프레임워크에 따라 적절한 자산이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-255">When installed in an app or library, the appropriate assets are selected based on the target framework specified by the app or library.</span></span> <span data-ttu-id="dc535-256">인터페이스를 정의하는 자산은 *ref* 폴더에 있으며 구현을 정의하는 자산은 *lib* 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-256">The assets that define the interface are in the *ref* folder, and the assets that define the implementation are in the *lib* folder.</span></span>

## <a name="platform"></a><span data-ttu-id="dc535-257">platform</span><span class="sxs-lookup"><span data-stu-id="dc535-257">platform</span></span>

<span data-ttu-id="dc535-258">Windows, macOS, Linux, iOS 및 Android 같은 운영 체제와 해당 운영 체제가 실행되는 하드웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-258">An operating system and the hardware it runs on, such as Windows, macOS, Linux, iOS, and Android.</span></span>

<span data-ttu-id="dc535-259">다음은 문장에서의 사용 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-259">Here are examples of usage in sentences:</span></span>

- <span data-ttu-id="dc535-260">“.NET Core는 .NET의 플랫폼 간 구현입니다.”</span><span class="sxs-lookup"><span data-stu-id="dc535-260">".NET Core is a cross-platform implementation of .NET."</span></span> 
- <span data-ttu-id="dc535-261">“PCL 프로필은 Microsoft 플랫폼을 나타내지만 .NET Standard는 플랫폼에 독립적입니다.”</span><span class="sxs-lookup"><span data-stu-id="dc535-261">"PCL profiles represent Microsoft platforms, while the .NET Standard is agnostic to platform."</span></span>

<span data-ttu-id="dc535-262">.NET 설명서에서는 .NET의 구현이나 모든 구현을 포함하는 .NET 스택을 의미하는 데 “.NET 플랫폼”을 자주 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-262">The .NET documentation frequently uses ".NET platform" to mean either an implementation of .NET or the .NET stack including all implementations.</span></span> <span data-ttu-id="dc535-263">이러한 사용은 모두 기본(OS/하드웨어) 의미와 혼동되므로 설명서에서 이러한 사용을 제거할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-263">Both of these usages tend to get confused with the primary (OS/hardware) meaning, so we plan to eliminate these usages from the documentation.</span></span>

## <a name="runtime"></a><span data-ttu-id="dc535-264">런타임(runtime)</span><span class="sxs-lookup"><span data-stu-id="dc535-264">runtime</span></span>

<span data-ttu-id="dc535-265">관리되는 프로그램에 대한 실행 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-265">The execution environment for a managed program.</span></span>

<span data-ttu-id="dc535-266">OS는 런타임 환경의 일부이지만 .NET 런타임의 일부는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-266">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="dc535-267">다음은 .NET 런타임의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-267">Here are some examples of .NET runtimes:</span></span>

- <span data-ttu-id="dc535-268">CLR(공용 언어 런타임)</span><span class="sxs-lookup"><span data-stu-id="dc535-268">Common Language Runtime (CLR)</span></span>
- <span data-ttu-id="dc535-269">CoreCLR(Core 공용 언어 런타임)</span><span class="sxs-lookup"><span data-stu-id="dc535-269">Core Common Language Runtime (CoreCLR)</span></span>
- <span data-ttu-id="dc535-270">.NET 네이티브(UWP)</span><span class="sxs-lookup"><span data-stu-id="dc535-270">.NET Native (for UWP)</span></span>
- <span data-ttu-id="dc535-271">Mono 런타임</span><span class="sxs-lookup"><span data-stu-id="dc535-271">Mono runtime</span></span>

<span data-ttu-id="dc535-272">.NET 설명서에서는 경우에 따라 “런타임”을 사용하여 .NET의 구현을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-272">The .NET documentation sometimes uses "runtime" to mean an implementation of .NET.</span></span> <span data-ttu-id="dc535-273">예를 들어 다음 문장에서 “런타임”은 “구현”으로 대체되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-273">For example, in the following sentences "runtime" should be replaced with "implementation":</span></span>

- <span data-ttu-id="dc535-274">“다양한 .NET 런타임에서 특정 버전의 .NET Standard를 구현합니다.”</span><span class="sxs-lookup"><span data-stu-id="dc535-274">"The various .NET runtimes implement specific versions of .NET Standard."</span></span>
- <span data-ttu-id="dc535-275">“여러 런타임에서 실행되도록 만들어진 라이브러리는 이 프레임워크를 대상으로 해야 합니다.”</span><span class="sxs-lookup"><span data-stu-id="dc535-275">"Libraries that are intended to run on multiple runtimes should target this framework."</span></span> <span data-ttu-id="dc535-276">(.NET Standard를 참조)</span><span class="sxs-lookup"><span data-stu-id="dc535-276">(referring to .NET Standard)</span></span>
- <span data-ttu-id="dc535-277">“다양한 .NET 런타임에서 특정 버전의 .NET Standard를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-277">"The various .NET runtimes implement specific versions of .NET Standard.</span></span> <span data-ttu-id="dc535-278">…</span><span class="sxs-lookup"><span data-stu-id="dc535-278">…</span></span> <span data-ttu-id="dc535-279">각 .NET 런타임 버전은 지원하는 최신 .NET Standard 버전을 보급합니다.”</span><span class="sxs-lookup"><span data-stu-id="dc535-279">Each .NET runtime version advertises the highest .NET Standard version it supports …"</span></span>

<span data-ttu-id="dc535-280">이러한 일관되지 않은 사용을 제거할 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-280">We plan to eliminate this inconsistent usage.</span></span> 

## <a name="stack"></a><span data-ttu-id="dc535-281">스택</span><span class="sxs-lookup"><span data-stu-id="dc535-281">stack</span></span>

<span data-ttu-id="dc535-282">응용 프로그램을 빌드하고 실행하는 데 함께 사용되는 프로그래밍 기술 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-282">A set of programming technologies that are used together to build and run applications.</span></span>

<span data-ttu-id="dc535-283">“.NET 스택”은 .NET Standard 및 모든 .NET 구현을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-283">"The .NET stack" refers to the .NET Standard and all .NET implementations.</span></span> <span data-ttu-id="dc535-284">“.NET 스택”이라는 구가 .NET 구현 하나를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-284">The phrase "a .NET stack" may refer to one implementation of .NET.</span></span> 

## <a name="target-framework"></a><span data-ttu-id="dc535-285">대상 프레임워크(target framework)</span><span class="sxs-lookup"><span data-stu-id="dc535-285">target framework</span></span>

<span data-ttu-id="dc535-286">.NET 앱 또는 라이브러리에서 사용하는 API 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-286">The collection of APIs that a .NET app or library relies on.</span></span>

<span data-ttu-id="dc535-287">앱 또는 라이브러리는 모든.NET 구현에서 표준화된 API 집합에 대한 사양인 .NET Standard의 버전(예: .NET Standard 2.0)을 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-287">An app or library can target a version of .NET Standard (for example, .NET Standard 2.0), which is specification for a standardized set of APIs across all .NET implementations.</span></span> <span data-ttu-id="dc535-288">또한 앱 또는 라이브러리는 특정 .NET 구현의 버전을 대상으로 할 수 있으며, 이 경우 구현 관련 API에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-288">An app or library can also target a version of a specific .NET implementation, in which case it gets access to implementation-specific APIs.</span></span> <span data-ttu-id="dc535-289">예를 들어 Xamarin.iOS를 대상으로 하는 앱은 Xamarin 제공 iOS API 래퍼에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-289">For example, an app that targets Xamarin.iOS gets access to Xamarin-provided iOS API wrappers.</span></span>

<span data-ttu-id="dc535-290">일부 대상 프레임워크(예: .NET Framework)에서 사용 가능한 API는 .NET 구현에서 시스템에 설치하는 어셈블리에 의해 정의되고 응용 프로그램 프레임워크 API(예: ASP.NET, WinForms)를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-290">For some target frameworks (for example, the .NET Framework) the available APIs are defined by the assemblies that a .NET implementation installs on a system, which may include application framework APIs (for example, ASP.NET, WinForms).</span></span> <span data-ttu-id="dc535-291">패키지 기반 대상 프레임워크(예: .NET Standard 및 .NET Core)에서 프레임워크 API는 앱이나 라이브러리에 설치된 패키지에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-291">For package-based target frameworks (such as .NET Standard and .NET Core), the framework APIs are defined by the packages installed in the app or library.</span></span> <span data-ttu-id="dc535-292">이 경우 대상 프레임워크는 함께 모여 프레임워크를 구성하는 모든 패키지를 참조하는 메타패키지를 암시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-292">In that case, the target framework implicitly specifies a metapackage that references all the packages that together make up the framework.</span></span>

<span data-ttu-id="dc535-293">[대상 프레임워크](frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-293">See [Target Frameworks](frameworks.md).</span></span>

## <a name="tfm"></a><span data-ttu-id="dc535-294">TFM</span><span class="sxs-lookup"><span data-stu-id="dc535-294">TFM</span></span>

<span data-ttu-id="dc535-295">대상 프레임워크 모니커입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-295">Target framework moniker.</span></span>

<span data-ttu-id="dc535-296">.NET 앱 또는 라이브러리의 대상 프레임워크를 지정하기 위해 표준화된 토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-296">A standardized token format for specifying the target framework of a .NET app or library.</span></span> <span data-ttu-id="dc535-297">대상 프레임워크는 일반적으로 `net462` 같은 짧은 이름으로 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-297">Target frameworks are typically referenced by a short name, such as `net462`.</span></span> <span data-ttu-id="dc535-298">긴 형식의 TFM(예: .NETFramework,Version=4.6.2)이 있지만 대상 프레임워크를 지정하는 데 일반적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-298">Long-form TFMs (such as .NETFramework,Version=4.6.2) exist but are not generally used to specify a target framework.</span></span>

<span data-ttu-id="dc535-299">[대상 프레임워크](frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc535-299">See [Target Frameworks](frameworks.md).</span></span>

## <a name="uwp"></a><span data-ttu-id="dc535-300">UWP</span><span class="sxs-lookup"><span data-stu-id="dc535-300">UWP</span></span>

<span data-ttu-id="dc535-301">유니버설 Windows 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-301">Universal Windows Platform.</span></span>

<span data-ttu-id="dc535-302">IoT(사물 인터넷)에 대한 최신 터치 가능 Windows 응용 프로그램 및 소프트웨어를 작성하는 데 사용되는 .NET의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-302">An implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="dc535-303">PC, 태블릿, 패블릿, 휴대폰, Xbox 등 대상으로 지정할 수 있는 다양한 종류의 장치를 통합하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-303">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="dc535-304">UWP는 중앙 집중식 앱 스토어, 실행 환경(AppContainer), Win32 대신 사용할 Windows API 집합(WinRT) 등 많은 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-304">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="dc535-305">앱은 C++, C#, VB.NET 및 JavaScript로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-305">Apps can be written in C++, C#, VB.NET, and JavaScript.</span></span> <span data-ttu-id="dc535-306">C# 및 VB.NET을 사용할 경우 .NET API는 .NET Core에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc535-306">When using C# and VB.NET, the .NET APIs are provided by .NET Core.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc535-307">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc535-307">See also</span></span>

[<span data-ttu-id="dc535-308">.NET 가이드</span><span class="sxs-lookup"><span data-stu-id="dc535-308">.NET Guide</span></span>](index.md)  
[<span data-ttu-id="dc535-309">.NET Framework 가이드</span><span class="sxs-lookup"><span data-stu-id="dc535-309">.NET Framework Guide</span></span>](../framework/index.md)  
[<span data-ttu-id="dc535-310">.NET Core</span><span class="sxs-lookup"><span data-stu-id="dc535-310">.NET Core</span></span>](../core/index.md)  
[<span data-ttu-id="dc535-311">ASP.NET 개요</span><span class="sxs-lookup"><span data-stu-id="dc535-311">ASP.NET Overview</span></span>](/aspnet/index#pivot=aspnet)  
[<span data-ttu-id="dc535-312">ASP.NET Core 개요</span><span class="sxs-lookup"><span data-stu-id="dc535-312">ASP.NET Core Overview</span></span>](/aspnet/index#pivot=core)  

