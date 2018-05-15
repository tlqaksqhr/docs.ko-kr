---
title: 소스에서 .NET Core 빌드
description: 소스 코드에서 .NET Core 및 .NET Core CLI를 빌드하는 방법을 알아봅니다.
author: bleroy
ms.author: mairaw
ms.date: 06/28/2017
ms.openlocfilehash: 55a35223a4bc11156e056cceb7f86365c4906222
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="build-net-core-from-source"></a><span data-ttu-id="61c0b-103">소스에서 .NET Core 빌드</span><span class="sxs-lookup"><span data-stu-id="61c0b-103">Build .NET Core from source</span></span>

<span data-ttu-id="61c0b-104">소스 코드에서 .NET Core를 빌드하는 기능은 여러 가지 면에서 중요합니다. .NET Core를 새 플랫폼으로 쉽게 포팅하고, 제품에 대한 기여 및 수정을 할 수 있으며, 사용자 지정 버전의 .NET을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-104">The ability to build .NET Core from its source code is important in multiple ways: it makes it easier to port .NET Core to new platforms, it enables contributions and fixes to the product, and it enables the creation of custom versions of .NET.</span></span>
<span data-ttu-id="61c0b-105">이 문서에서는 고유한 .NET Core 버전을 빌드하고 배포하려는 개발자에게 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-105">This article gives guidance to developers who want to build and distribute their own versions of .NET Core.</span></span>

## <a name="build-the-clr-from-source"></a><span data-ttu-id="61c0b-106">소스에서 CLR 빌드</span><span class="sxs-lookup"><span data-stu-id="61c0b-106">Build the CLR from source</span></span>

<span data-ttu-id="61c0b-107">.NET CoreCLR에 대한 소스 코드는 GitHub의 [dotnet/coreclr](https://github.com/dotnet/coreclr/) 리포지토리에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-107">The source code for the .NET CoreCLR can be found in the [dotnet/coreclr](https://github.com/dotnet/coreclr/) repository on GitHub.</span></span>

<span data-ttu-id="61c0b-108">현재 빌드는 다음 필수 구성 요소에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-108">The build currently depends on the following prerequisites:</span></span>
* [<span data-ttu-id="61c0b-109">Git</span><span class="sxs-lookup"><span data-stu-id="61c0b-109">Git</span></span>](https://git-scm.com/)
* [<span data-ttu-id="61c0b-110">CMake</span><span class="sxs-lookup"><span data-stu-id="61c0b-110">CMake</span></span>](https://cmake.org/)
* [<span data-ttu-id="61c0b-111">Python</span><span class="sxs-lookup"><span data-stu-id="61c0b-111">Python</span></span>](https://www.python.org/)
* <span data-ttu-id="61c0b-112">C++ 컴파일러</span><span class="sxs-lookup"><span data-stu-id="61c0b-112">a C++ compiler.</span></span>

<span data-ttu-id="61c0b-113">이러한 필수 구성 요소를 설치하면 [dotnet/coreclr](https://github.com/dotnet/coreclr/) 리포지토리의 맨 아래에 있는 빌드 스크립트(Windows의 경우 `build.cmd`, Linux 및 macOS의 경우 `build.sh`)를 호출하여 CLR을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-113">After you've installed these prerequisites are installed, you can build the CLR by invoking the build script (`build.cmd` on Windows, or `build.sh` on Linux and macOS) at the base of the [dotnet/coreclr](https://github.com/dotnet/coreclr/) repository.</span></span>

<span data-ttu-id="61c0b-114">구성 요소 설치는 OS(운영 체제)에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-114">Installing the components differ depending on the operating system (OS).</span></span> <span data-ttu-id="61c0b-115">특정 OS에 대한 빌드 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61c0b-115">See the build instructions for your specific OS:</span></span>

 * [<span data-ttu-id="61c0b-116">Windows</span><span class="sxs-lookup"><span data-stu-id="61c0b-116">Windows</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/windows-instructions.md)
 * [<span data-ttu-id="61c0b-117">Linux</span><span class="sxs-lookup"><span data-stu-id="61c0b-117">Linux</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/linux-instructions.md)
 * [<span data-ttu-id="61c0b-118">macOS</span><span class="sxs-lookup"><span data-stu-id="61c0b-118">macOS</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/osx-instructions.md)
 * [<span data-ttu-id="61c0b-119">FreeBSD</span><span class="sxs-lookup"><span data-stu-id="61c0b-119">FreeBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/freebsd-instructions.md) 
 * [<span data-ttu-id="61c0b-120">NetBSD</span><span class="sxs-lookup"><span data-stu-id="61c0b-120">NetBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/netbsd-instructions.md)

<span data-ttu-id="61c0b-121">OS에서 교차 빌드되지 않습니다(X64에서 빌드되는 ARM의 경우에만 교차 빌드됨).</span><span class="sxs-lookup"><span data-stu-id="61c0b-121">There is no cross-building across OS (only for ARM, which is built on X64).</span></span>  
<span data-ttu-id="61c0b-122">특정 플랫폼을 빌드하려면 해당 플랫폼을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-122">You have to be on the particular platform to build that platform.</span></span>  

<span data-ttu-id="61c0b-123">빌드에는 다음과 같은 두 주요 `buildTypes`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-123">The build has two main `buildTypes`:</span></span>

 * <span data-ttu-id="61c0b-124">디버그(기본값) - 최소 최적화와 추가 런타임 검사로 런타임을 컴파일합니다(어설션).</span><span class="sxs-lookup"><span data-stu-id="61c0b-124">Debug (default)- Compiles the runtime with minimal optimizations and additional runtime checks (asserts).</span></span> <span data-ttu-id="61c0b-125">최적화 수준의 감소와 추가 검사는 런타임 실행을 늦추지만 디버깅에는 가치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-125">This reduction in optimization level and the additional checks slow runtime execution but are valuable for debugging.</span></span> <span data-ttu-id="61c0b-126">이는 개발 및 테스트 환경에 권장되는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-126">This is the recommended setting for development and testing environments.</span></span>
 * <span data-ttu-id="61c0b-127">릴리스 - 추가 런타임 검사 없이 전체 최적화를 사용하여 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-127">Release - Compiles the runtime with full optimizations and without the additional runtime checks.</span></span> <span data-ttu-id="61c0b-128">런타임 성능이 더 빨라지지만 빌드하려면 약간 시간이 걸릴 수 있고 디버깅하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-128">This will yield much faster run time performance but it can take a bit longer to build and can be difficult to debug.</span></span> <span data-ttu-id="61c0b-129">이 빌드 유형을 선택하려면 `release`를 빌드 스크립트에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-129">Pass `release` to the build script to select this build type.</span></span>

<span data-ttu-id="61c0b-130">또한 기본적으로 빌드는 런타임 실행 파일을 만들 뿐만 아니라 모든 테스트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-130">In addition, by default the build not only creates the runtime executables, but it also builds all the tests.</span></span>
<span data-ttu-id="61c0b-131">변경 내용을 시험하려는 경우에는 필요하지 않은 테스트가 상당히 많습니다. 이러한 테스트는 시간이 오래 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-131">There are quite a few tests, taking a significant amount of time that isn't necessary if you just want to experiment with changes.</span></span>
<span data-ttu-id="61c0b-132">다음 예와 같이 빌드 스크립트에 `skiptests` 인수를 추가하여 빌드 테스트를 건너뛸 수 있습니다(Unix 컴퓨터에서는 `.\build`를 `./build.sh`로 대체).</span><span class="sxs-lookup"><span data-stu-id="61c0b-132">You can skip the tests builds by adding the `skiptests` argument to the build script, like in the following example (replace `.\build` with `./build.sh` on Unix machines):</span></span>

```bat
    .\build skiptests 
```

<span data-ttu-id="61c0b-133">이전 예에서는 개발 시간 검사(어설션)를 사용하고 최적화를 사용하지 않는 `Debug` 버전을 빌드하는 방법을 보여 줬습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-133">The previous example showed how to build the `Debug` flavor, which has development time checks (asserts) enabled and optimizations disabled.</span></span> <span data-ttu-id="61c0b-134">릴리스(최대 속도) 버전을 빌드하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-134">To build the release (full speed) flavor, do the following:</span></span>

```bat 
    .\build release skiptests
```

<span data-ttu-id="61c0b-135">-? 또는</span><span class="sxs-lookup"><span data-stu-id="61c0b-135">You can find more build options with build by using the -?</span></span> <span data-ttu-id="61c0b-136">-help 한정자를 사용하는 빌드와 함께 더 많은 빌드 옵션을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-136">or -help qualifier.</span></span>   

### <a name="using-your-build"></a><span data-ttu-id="61c0b-137">사용자의 빌드 사용</span><span class="sxs-lookup"><span data-stu-id="61c0b-137">Using Your Build</span></span>

<span data-ttu-id="61c0b-138">빌드는 생성된 모든 파일을 리포지토리의 맨 아래에 있는 `bin` 디렉터리 아래에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-138">The build places all of its generated files under the `bin` directory at the base of the repository.</span></span>
<span data-ttu-id="61c0b-139">빌드 중 생성된 로그 파일이 들어 있는 *bin\Log* 디렉터리가 있습니다(빌드 실패 시 가장 유용함).</span><span class="sxs-lookup"><span data-stu-id="61c0b-139">There is a *bin\Log* directory that contains log files generated during the build (Most useful when the build fails).</span></span>
<span data-ttu-id="61c0b-140">실제 출력 위치는 *bin\Product\Windows_NT.x64.Release* 같은 *bin\Product\[platform].[CPU architecture].[build type]* 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-140">The actual output is placed in a *bin\Product\[platform].[CPU architecture].[build type]* directory, such as *bin\Product\Windows_NT.x64.Release*.</span></span>

<span data-ttu-id="61c0b-141">빌드의 ‘원시’ 출력이 때때로 유용하지만, 사용자는 일반적으로 이전 출력 디렉터리의 `.nuget\pkg` 하위 디렉터리에 있는 NuGet 패키지에만 관심이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-141">While the 'raw' output of the build is sometimes useful, normally you're only interested in the NuGet packages, which are placed in the `.nuget\pkg` subdirectory of the previous output directory.</span></span>

<span data-ttu-id="61c0b-142">새 런타임 사용에 대한 두 가지 기본 기술은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-142">There are two basic techniques for using your new runtime:</span></span>

 1. <span data-ttu-id="61c0b-143">**dotnet.exe 및 NuGet을 사용하여 응용 프로그램을 작성합니다**.</span><span class="sxs-lookup"><span data-stu-id="61c0b-143">**Use dotnet.exe and NuGet to compose an application**.</span></span>
    <span data-ttu-id="61c0b-144">방금 만든 NuGet 패키지 및 'dotnet' CLI(명령줄 인터페이스)를 사용하여 새 런타임을 사용하는 프로그램 작성에 대한 지침은 [사용자의 빌드 사용](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingYourBuild.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61c0b-144">See [Using Your Build](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingYourBuild.md) for instructions on creating a program that uses your new runtime by using the NuGet packages you just created and the 'dotnet' command-line interface (CLI).</span></span> <span data-ttu-id="61c0b-145">이 기술은 비런타임 개발자가 새 런타임을 사용할 것으로 예상되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-145">This technique is the expected way non-runtime developers are likely to consume your new runtime.</span></span>    

 2. <span data-ttu-id="61c0b-146">**corerun.exe를 사용하여 패키지되지 않은 DLL을 사용하는 응용 프로그램을 실행합니다**.</span><span class="sxs-lookup"><span data-stu-id="61c0b-146">**Use corerun.exe to run an application using unpackaged DLLs**.</span></span>
    <span data-ttu-id="61c0b-147">이 리포지토리는 NuGet에서 종속성을 사용하지 않는 corerun.exe라는 간단한 호스트도 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-147">This repository also defines a simple host called corerun.exe that does NOT take any dependency on NuGet.</span></span>
    <span data-ttu-id="61c0b-148">실제로 사용할 필요한 DLL을 가져올 위치를 호스트에 입력해야 하고, 수동으로 수집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-148">You need to tell the host where to get the required DLLs you actually use, and you have to manually gather them together.</span></span>
    <span data-ttu-id="61c0b-149">이 기술은 [dotnet/coreclr](https://github.com/dotnet/coreclr) 리포지토리의 모든 테스트에 사용되며, 예비 유닛 테스트처럼 빠른 로컬 ‘edit-compile-debug’ 루프에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-149">This technique is used by all the tests in the [dotnet/coreclr](https://github.com/dotnet/coreclr) repo, and is useful for quick local 'edit-compile-debug' loop such as preliminary unit testing.</span></span>
    <span data-ttu-id="61c0b-150">이 기술 사용에 대한 자세한 내용은 [Executing .NET Core Apps with CoreRun.exe](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingCoreRun.md)(CoreRun.exe를 사용하여 .NET Core 앱 실행)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61c0b-150">See [Executing .NET Core Apps with CoreRun.exe](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingCoreRun.md) for details on using this technique.</span></span>

## <a name="build-the-cli-from-source"></a><span data-ttu-id="61c0b-151">소스에서 CLI 빌드</span><span class="sxs-lookup"><span data-stu-id="61c0b-151">Build the CLI from source</span></span>

<span data-ttu-id="61c0b-152">.NET Core CLI에 대한 소스 코드는 GitHub의 [dotnet/cli](https://github.com/dotnet/cli/) 리포지토리에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-152">The source code for the .NET Core CLI can be found in the [dotnet/cli](https://github.com/dotnet/cli/) repository on GitHub.</span></span>

<span data-ttu-id="61c0b-153">.NET Core CLI을 빌드하려면 컴퓨터에 다음이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-153">In order to build the .NET Core CLI, you need the following installed on your machine.</span></span>

* <span data-ttu-id="61c0b-154">Windows 및 Linux:</span><span class="sxs-lookup"><span data-stu-id="61c0b-154">Windows & Linux:</span></span>
    - <span data-ttu-id="61c0b-155">PATH의 git</span><span class="sxs-lookup"><span data-stu-id="61c0b-155">git on the PATH</span></span>
* <span data-ttu-id="61c0b-156">macOS:</span><span class="sxs-lookup"><span data-stu-id="61c0b-156">macOS:</span></span>
    - <span data-ttu-id="61c0b-157">PATH의 git</span><span class="sxs-lookup"><span data-stu-id="61c0b-157">git on the PATH</span></span>
    - <span data-ttu-id="61c0b-158">Xcode</span><span class="sxs-lookup"><span data-stu-id="61c0b-158">Xcode</span></span>
    - <span data-ttu-id="61c0b-159">Openssl</span><span class="sxs-lookup"><span data-stu-id="61c0b-159">OpenSSL</span></span>

<span data-ttu-id="61c0b-160">빌드하려면 Windows의 경우 루트에서 `build.cmd`를 실행하고, Linux 및 macOS의 경우 루트에서 `build.sh`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-160">In order to build, run `build.cmd` on Windows, or `build.sh` on Linux and macOS from the root.</span></span> <span data-ttu-id="61c0b-161">테스트를 실행하지 않으려면 `build.cmd /t:Compile` 또는 `./build.sh /t:Compile`을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-161">If you don't want to execute tests, run `build.cmd /t:Compile` or `./build.sh /t:Compile`.</span></span> <span data-ttu-id="61c0b-162">macOS Sierra에서 CLI를 빌드하려면 `export DOTNET_RUNTIME_ID=osx.10.11-x64`를 실행하여 DOTNET_RUNTIME_ID 환경 변수를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-162">To build the CLI in macOS Sierra, you need to set the DOTNET_RUNTIME_ID environment variable by running `export DOTNET_RUNTIME_ID=osx.10.11-x64`.</span></span>

### <a name="using-your-build"></a><span data-ttu-id="61c0b-163">사용자의 빌드 사용</span><span class="sxs-lookup"><span data-stu-id="61c0b-163">Using your build</span></span>

<span data-ttu-id="61c0b-164">*artifacts/{os}-{arch}/stage2*의 `dotnet` 실행 파일을 사용하여 새로 빌드한 CLI를 사용해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-164">Use the `dotnet` executable from *artifacts/{os}-{arch}/stage2* to try out the newly built CLI.</span></span> <span data-ttu-id="61c0b-165">현재 콘솔에서 `dotnet`을 호출할 때 빌드 출력을 사용하려면 *artifacts/{os}-{arch}/stage2*를 PATH에 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c0b-165">If you want to use the build output when invoking `dotnet` from the current console, you can also add *artifacts/{os}-{arch}/stage2* to the PATH.</span></span>

## <a name="see-also"></a><span data-ttu-id="61c0b-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61c0b-166">See also</span></span>

* [<span data-ttu-id="61c0b-167">.NET Core 공용 언어 런타임(CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="61c0b-167">.NET Core Common Language Runtime (CoreCLR)</span></span>](https://github.com/dotnet/coreclr/blob/master/README.md)
* [<span data-ttu-id="61c0b-168">.NET Core CLI 개발자 가이드</span><span class="sxs-lookup"><span data-stu-id="61c0b-168">.NET Core CLI Developer Guide</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/project-docs/developer-guide.md)
* [<span data-ttu-id="61c0b-169">.NET Core 배포 패키징</span><span class="sxs-lookup"><span data-stu-id="61c0b-169">.NET Core distribution packaging</span></span>](./distribution-packaging.md)
