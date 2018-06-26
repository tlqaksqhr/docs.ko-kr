---
title: dotnet build 명령 - .NET Core CLI
description: dotnet build 명령은 프로젝트와 모든 종속성을 빌드합니다.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 6b0b7bc11b560d8632b38f1dfa4e7eb3ce6c54d2
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34697133"
---
# <a name="dotnet-build"></a><span data-ttu-id="19ecb-103">dotnet-build</span><span class="sxs-lookup"><span data-stu-id="19ecb-103">dotnet-build</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="19ecb-104">name</span><span class="sxs-lookup"><span data-stu-id="19ecb-104">Name</span></span>

<span data-ttu-id="19ecb-105">`dotnet build` - 프로젝트 및 모든 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-105">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="19ecb-106">개요</span><span class="sxs-lookup"><span data-stu-id="19ecb-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="19ecb-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="19ecb-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--no-dependencies] [--no-incremental]
    [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="19ecb-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="19ecb-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--no-dependencies] [--no-incremental] [-o|--output]
    [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="19ecb-109">설명</span><span class="sxs-lookup"><span data-stu-id="19ecb-109">Description</span></span>

<span data-ttu-id="19ecb-110">`dotnet build` 명령은 이진 파일 집합으로 프로젝트와 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-110">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="19ecb-111">이진 파일에는 *.dll* 확장명을 갖는 IL(중간 언어)의 프로젝트 코드와 *.pdb* 확장명을 가지며 디버깅에 사용되는 기호 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-111">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="19ecb-112">응용 프로그램의 종속성을 나열하는 종속성 JSON 파일(*\*.deps.json*)이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-112">A dependencies JSON file (*\*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="19ecb-113">응용 프로그램에 대한 공유 런타임 및 해당 버전을 지정하는 *\*.runtimeconfig.json* 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-113">A *\*.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="19ecb-114">프로젝트에 NuGet의 라이브러리와 같은 타사 종속성이 있는 경우, 이러한 종속성은 NuGet 캐시에서 확인되고 프로젝트의 빌드 출력으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-114">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="19ecb-115">따라서 `dotnet build`의 제품을 실행하기 위해 다른 컴퓨터로 전송할 준비가 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-115">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="19ecb-116">이는 실행 가능한 프로젝트(응용 프로그램) 빌드로 .NET Framework가 설치된 컴퓨터에서 실행할 수 있는 출력을 생성하는 .NET Framework의 동작과는 대조적입니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-116">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="19ecb-117">.NET Core에서 비슷한 환경을 사용하려면 [dotnet publish](dotnet-publish.md) 명령을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-117">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="19ecb-118">자세한 내용은 [.NET Core 응용 프로그램 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19ecb-118">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="19ecb-119">빌드하려면 응용 프로그램의 종속성을 나열하는 *project.assets.json* 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-119">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="19ecb-120">[`dotnet restore`](dotnet-restore.md)가 실행되면 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-120">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="19ecb-121">자산 파일이 없으면 도구로 참조 어셈블리를 확인할 수 없으므로 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-121">Without the assets file in place, the tooling cannot resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="19ecb-122">.NET Core 1.x SDK를 사용할 경우 `dotnet build`를 실행하기 전에 `dotnet restore`를 명시적으로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-122">With .NET Core 1.x SDK, you needed to explicitly run the `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="19ecb-123">.NET Core 2.0 SDK부터 `dotnet restore`는 `dotnet build`를 실행할 때 암시적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-123">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="19ecb-124">빌드 명령을 실행할 때 암시적 복원을 사용하지 않으려면 `--no-restore` 옵션을 전달하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-124">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="19ecb-125">`dotnet build`는 MSBuild를 사용하여 프로젝트를 빌드하므로 병렬 및 증분 빌드를 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-125">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="19ecb-126">자세한 내용은 [증분 빌드](/visualstudio/msbuild/incremental-builds)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19ecb-126">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="19ecb-127">해당 옵션 외에도, `dotnet build` 명령은 속성 설정에 대한 `/p` 또는 로거를 정의하는 `/l`처럼 MSBuild 옵션도 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-127">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `/p` for setting properties or `/l` to define a logger.</span></span> <span data-ttu-id="19ecb-128">이러한 옵션에 대한 자세한 내용은 [MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="19ecb-128">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="19ecb-129">프로젝트가 실행 가능한지 아닌지 여부는 프로젝트 파일의 `<OutputType>` 속성으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-129">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="19ecb-130">다음 예제에서는 실행 코드를 생성하는 프로젝트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-130">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="19ecb-131">라이브러리를 생성하려면 `<OutputType>` 속성을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-131">In order to produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="19ecb-132">빌드된 출력의 주요 차이점은 라이브러리에 대한 IL DLL이 진입점을 포함하지 않으며 실행할 수 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-132">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

## <a name="arguments"></a><span data-ttu-id="19ecb-133">인수</span><span class="sxs-lookup"><span data-stu-id="19ecb-133">Arguments</span></span>

`PROJECT`

<span data-ttu-id="19ecb-134">빌드할 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-134">The project file to build.</span></span> <span data-ttu-id="19ecb-135">프로젝트 파일을 지정하지 않으면 MSBuild는 현재 작업 디렉터리에서 *proj*로 끝나는 파일 확장명이 있는 파일을 검색하고 해당 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-135">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="19ecb-136">옵션</span><span class="sxs-lookup"><span data-stu-id="19ecb-136">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="19ecb-137">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="19ecb-137">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="19ecb-138">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-138">Defines the build configuration.</span></span> <span data-ttu-id="19ecb-139">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-139">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="19ecb-140">특정 [프레임워크](../../standard/frameworks.md)에 대해 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-140">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="19ecb-141">프레임워크는 [프로젝트 파일](csproj.md)에 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-141">The framework must be defined in the [project file](csproj.md).</span></span>

`--force`

<span data-ttu-id="19ecb-142">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-142">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="19ecb-143">이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-143">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="19ecb-144">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-144">Prints out a short help for the command.</span></span>

`--no-dependencies`

<span data-ttu-id="19ecb-145">프로젝트 간(P2P) 참조를 무시하고 지정된 루트 프로젝트만 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-145">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

`--no-incremental`

<span data-ttu-id="19ecb-146">빌드를 증분 빌드에 안전하지 않은 것으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-146">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="19ecb-147">이 플래그로 증분 컴파일이 해제되고 프로젝트 종속성 그래프를 강제로 완전히 다시 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-147">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

`--no-restore`

<span data-ttu-id="19ecb-148">빌드하는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-148">Doesn't execute an implicit restore during build.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="19ecb-149">빌드된 이진 파일을 배치할 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-149">Directory in which to place the built binaries.</span></span> <span data-ttu-id="19ecb-150">이 옵션을 지정하는 경우 `--framework`도 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-150">You also need to define `--framework` when you specify this option.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="19ecb-151">대상 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-151">Specifies the target runtime.</span></span> <span data-ttu-id="19ecb-152">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19ecb-152">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="19ecb-153">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="19ecb-154">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="19ecb-155">프로젝트 파일의 버전 필드에서 별표(`*`)에 대한 버전 접미사를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-155">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="19ecb-156">형식은 NuGet의 버전 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-156">The format follows NuGet's version guidelines.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="19ecb-157">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="19ecb-157">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="19ecb-158">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-158">Defines the build configuration.</span></span> <span data-ttu-id="19ecb-159">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-159">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="19ecb-160">특정 [프레임워크](../../standard/frameworks.md)에 대해 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-160">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="19ecb-161">프레임워크는 [프로젝트 파일](csproj.md)에 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-161">The framework must be defined in the [project file](csproj.md).</span></span>

`-h|--help`

<span data-ttu-id="19ecb-162">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-162">Prints out a short help for the command.</span></span>

`--no-dependencies`

<span data-ttu-id="19ecb-163">프로젝트 간(P2P) 참조를 무시하고 지정된 루트 프로젝트만 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-163">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

`--no-incremental`

<span data-ttu-id="19ecb-164">빌드를 증분 빌드에 안전하지 않은 것으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-164">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="19ecb-165">이 플래그로 증분 컴파일이 해제되고 프로젝트 종속성 그래프를 강제로 완전히 다시 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-165">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="19ecb-166">빌드된 이진 파일을 배치할 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-166">Directory in which to place the built binaries.</span></span> <span data-ttu-id="19ecb-167">이 옵션을 지정하는 경우 `--framework`도 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-167">You also need to define `--framework` when you specify this option.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="19ecb-168">대상 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-168">Specifies the target runtime.</span></span> <span data-ttu-id="19ecb-169">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19ecb-169">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="19ecb-170">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-170">Sets the verbosity level of the command.</span></span> <span data-ttu-id="19ecb-171">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-171">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="19ecb-172">프로젝트 파일의 버전 필드에서 별표(`*`)에 대한 버전 접미사를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-172">Defines the version suffix for an asterisk (`*`) in the version field of the project file.</span></span> <span data-ttu-id="19ecb-173">형식은 NuGet의 버전 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-173">The format follows NuGet's version guidelines.</span></span>

---

## <a name="examples"></a><span data-ttu-id="19ecb-174">예제</span><span class="sxs-lookup"><span data-stu-id="19ecb-174">Examples</span></span>

<span data-ttu-id="19ecb-175">프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-175">Build a project and its dependencies:</span></span>

`dotnet build`

<span data-ttu-id="19ecb-176">릴리스 구성을 사용하여 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-176">Build a project and its dependencies using Release configuration:</span></span>

`dotnet build --configuration Release`

<span data-ttu-id="19ecb-177">특정 런타임(이 예제의 경우 Ubuntu 16.04)에 대한 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="19ecb-177">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 16.04):</span></span>

`dotnet build --runtime ubuntu.16.04-x64`

<span data-ttu-id="19ecb-178">프로젝트를 빌드하고 복원 작업 중 지정된 NuGet 패키지 원본을 사용합니다(.NET Core SDK 2.0 이상 버전).</span><span class="sxs-lookup"><span data-stu-id="19ecb-178">Build the project and use the specified NuGet package source during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet build --source c:\packages\mypackages`