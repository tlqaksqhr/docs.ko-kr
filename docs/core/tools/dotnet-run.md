---
title: dotnet run 명령 - .NET Core CLI
description: dotnet run 명령은 소스 코드에서 응용 프로그램을 실행하는 편리한 옵션을 제공합니다.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 609ac27f21e6801992b9e10c7d465a805492859e
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245254"
---
# <a name="dotnet-run"></a><span data-ttu-id="cfb53-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="cfb53-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="cfb53-104">name</span><span class="sxs-lookup"><span data-stu-id="cfb53-104">Name</span></span>

<span data-ttu-id="cfb53-105">`dotnet run` - 명시적 컴파일이나 시작 명령을 사용하지 않고 소스 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cfb53-106">개요</span><span class="sxs-lookup"><span data-stu-id="cfb53-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cfb53-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cfb53-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cfb53-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cfb53-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cfb53-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cfb53-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="cfb53-110">설명</span><span class="sxs-lookup"><span data-stu-id="cfb53-110">Description</span></span>

<span data-ttu-id="cfb53-111">`dotnet run` 명령은 하나의 명령을 사용하여 소스 코드에서 응용 프로그램을 실행하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-111">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="cfb53-112">명령줄에서 빠른 반복 개발에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-112">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="cfb53-113">이 명령은 코드 빌드 시 [`dotnet build`](dotnet-build.md) 명령에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-113">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="cfb53-114">프로젝트를 먼저 복원해야 하는 등, 빌드에 대한 요구 사항은 `dotnet run`에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-114">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="cfb53-115">출력 파일은 기본 위치, 즉 `bin/<configuration>/<target>`에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-115">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="cfb53-116">예를 들어 `netcoreapp1.0` 응용 프로그램이 있고 `dotnet run`을 실행하는 경우 출력은 `bin/Debug/netcoreapp1.0`에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-116">For example if you have a `netcoreapp1.0` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp1.0`.</span></span> <span data-ttu-id="cfb53-117">필요에 따라 파일을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-117">Files are overwritten as needed.</span></span> <span data-ttu-id="cfb53-118">임시 파일은 `obj` 디렉터리에 놓입니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-118">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="cfb53-119">프로젝트가 여러 프레임워크를 지정하는 경우 프레임워크를 지정하는 데 `-f|--framework <FRAMEWORK>` 옵션을 사용하지 않은 한, `dotnet run`을 실행하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-119">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="cfb53-120">`dotnet run` 명령은 빌드된 어셈블리가 아닌 프로젝트의 컨텍스트에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-120">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="cfb53-121">대신 프레임워크 종속 응용 프로그램 DLL을 실행하려고 하는 경우 명령 없이 [dotnet](dotnet.md)을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-121">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="cfb53-122">예를 들어 `myapp.dll`을 실행하려면 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-122">For example, to run `myapp.dll`, use:</span></span>

```console
dotnet myapp.dll
```

<span data-ttu-id="cfb53-123">`dotnet` 드라이버에 대한 자세한 내용은 [.NET Core 명령줄 도구(CLI)](index.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfb53-123">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="cfb53-124">응용 프로그램을 실행하기 위해 `dotnet run` 명령은 NuGet 캐시에서 공유 런타임의 외부에 있는 응용 프로그램의 종속성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-124">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="cfb53-125">캐시된 종속성을 사용하기 때문에 프로덕션 환경에서 응용 프로그램을 실행하는 데 `dotnet run`을 사용하는 것은 바람직하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-125">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="cfb53-126">대신, [`dotnet publish`](dotnet-publish.md) 명령을 사용하여 [배포를 만들고](../deploying/index.md) 게시된 출력을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-126">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="cfb53-127">옵션</span><span class="sxs-lookup"><span data-stu-id="cfb53-127">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cfb53-128">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cfb53-128">.NET Core 2.1</span></span>](#tab/netcore21)

`--`

<span data-ttu-id="cfb53-129">실행 중인 응용 프로그램에 대한 인수에서 `dotnet run`에 대한 인수를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-129">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="cfb53-130">이 구분 기호 다음의 모든 인수가 실행 중인 응용 프로그램에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-130">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="cfb53-131">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-131">Defines the build configuration.</span></span> <span data-ttu-id="cfb53-132">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-132">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="cfb53-133">지정된 [프레임워크](../../standard/frameworks.md)를 사용하여 앱을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-133">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="cfb53-134">프레임워크는 프로젝트 파일에 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-134">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="cfb53-135">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-135">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="cfb53-136">이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-136">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="cfb53-137">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-137">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="cfb53-138">응용 프로그램을 시작할 때 사용할 시작 프로필(있는 경우)의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-138">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="cfb53-139">시작 프로필은 *launchSettings.json* 파일에서 정의되고 일반적으로 `Development`, `Staging` 및 `Production`이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-139">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="cfb53-140">자세한 내용은 [여러 환경 사용](/aspnet/core/fundamentals/environments)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfb53-140">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="cfb53-141">실행하기 전에 프로젝트를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-141">Doesn't build the project before running.</span></span> <span data-ttu-id="cfb53-142">또한 `--no-restore` 플래그를 암시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-142">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="cfb53-143">프로젝트 간(P2P) 참조를 사용하여 프로젝트를 복원할 경우 참조가 아닌 루트 프로젝트를 복원하세요.</span><span class="sxs-lookup"><span data-stu-id="cfb53-143">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="cfb53-144">응용 프로그램을 구성하는 데 *launchSettings.json*을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-144">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="cfb53-145">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-145">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="cfb53-146">실행할 프로젝트 파일의 경로를 지정합니다(폴더 이름 또는 전체 경로).</span><span class="sxs-lookup"><span data-stu-id="cfb53-146">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="cfb53-147">지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-147">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="cfb53-148">패키지를 복원할 대상 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-148">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="cfb53-149">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfb53-149">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="cfb53-150">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="cfb53-151">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cfb53-152">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cfb53-152">.NET Core 2.0</span></span>](#tab/netcore20)

`--`

<span data-ttu-id="cfb53-153">실행 중인 응용 프로그램에 대한 인수에서 `dotnet run`에 대한 인수를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-153">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="cfb53-154">이 구분 기호 다음의 모든 인수가 실행 중인 응용 프로그램에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-154">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="cfb53-155">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-155">Defines the build configuration.</span></span> <span data-ttu-id="cfb53-156">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-156">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="cfb53-157">지정된 [프레임워크](../../standard/frameworks.md)를 사용하여 앱을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-157">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="cfb53-158">프레임워크는 프로젝트 파일에 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-158">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="cfb53-159">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-159">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="cfb53-160">이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-160">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="cfb53-161">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-161">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="cfb53-162">응용 프로그램을 시작할 때 사용할 시작 프로필(있는 경우)의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-162">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="cfb53-163">시작 프로필은 *launchSettings.json* 파일에서 정의되고 일반적으로 `Development`, `Staging` 및 `Production`이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-163">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="cfb53-164">자세한 내용은 [여러 환경 사용](/aspnet/core/fundamentals/environments)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfb53-164">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="cfb53-165">실행하기 전에 프로젝트를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-165">Doesn't build the project before running.</span></span> <span data-ttu-id="cfb53-166">또한 `--no-restore` 플래그를 암시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-166">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="cfb53-167">프로젝트 간(P2P) 참조를 사용하여 프로젝트를 복원할 경우 참조가 아닌 루트 프로젝트를 복원하세요.</span><span class="sxs-lookup"><span data-stu-id="cfb53-167">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="cfb53-168">응용 프로그램을 구성하는 데 *launchSettings.json*을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-168">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="cfb53-169">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-169">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="cfb53-170">실행할 프로젝트 파일의 경로를 지정합니다(폴더 이름 또는 전체 경로).</span><span class="sxs-lookup"><span data-stu-id="cfb53-170">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="cfb53-171">지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-171">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="cfb53-172">패키지를 복원할 대상 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-172">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="cfb53-173">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfb53-173">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cfb53-174">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cfb53-174">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="cfb53-175">실행 중인 응용 프로그램에 대한 인수에서 `dotnet run`에 대한 인수를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-175">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="cfb53-176">이 구분 기호 다음의 모든 인수가 실행 중인 응용 프로그램에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-176">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="cfb53-177">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-177">Defines the build configuration.</span></span> <span data-ttu-id="cfb53-178">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-178">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="cfb53-179">지정된 [프레임워크](../../standard/frameworks.md)를 사용하여 앱을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-179">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="cfb53-180">프레임워크는 프로젝트 파일에 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-180">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="cfb53-181">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-181">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="cfb53-182">프로젝트 파일의 경로 및 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-182">Specifies the path and name of the project file.</span></span> <span data-ttu-id="cfb53-183">(참고 참조) 지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-183">(See the NOTE.) If not specified, it defaults to the current directory.</span></span>

> [!NOTE]
> <span data-ttu-id="cfb53-184">`-p|--project` 옵션과 함께 프로젝트 파일의 경로와 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-184">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="cfb53-185">CLI의 재발로 인해 폴더 경로에 .NET Core SDK 1.x를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-185">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="cfb53-186">이 문제에 대한 자세한 내용은 [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992)(dotnet run -p로 프로젝트를 시작할 수 없음(dotnet/cli #5992))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfb53-186">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="cfb53-187">예제</span><span class="sxs-lookup"><span data-stu-id="cfb53-187">Examples</span></span>

<span data-ttu-id="cfb53-188">현재 디렉터리에 있는 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-188">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="cfb53-189">지정된 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-189">Run the specified project:</span></span>

`dotnet run --project ./projects/proj1/proj1.csproj`

<span data-ttu-id="cfb53-190">현재 디렉터리에 있는 프로젝트를 실행합니다. 비어 있는 `--` 옵션을 사용하므로 이 예제의 `--help` 인수는 응용 프로그램에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfb53-190">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="cfb53-191">최소 출력만을 표시하는 현재 디렉터리에 프로젝트에 대한 종속성 및 도구를 저장한 다음, 프로젝트를 실행합니다(.NET Core SDK 2.0 이상 버전).</span><span class="sxs-lookup"><span data-stu-id="cfb53-191">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`