---
title: dotnet run 명령 - .NET Core CLI
description: dotnet run 명령은 소스 코드에서 응용 프로그램을 실행하는 편리한 옵션을 제공합니다.
author: mairaw
ms.author: mairaw
ms.date: 03/10/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 18ceb395ed025fa562f295fc2facd00c67a75536
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-run"></a><span data-ttu-id="fec75-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="fec75-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="fec75-104">name</span><span class="sxs-lookup"><span data-stu-id="fec75-104">Name</span></span>

<span data-ttu-id="fec75-105">`dotnet run` - 명시적 컴파일이나 시작 명령을 사용하지 않고 소스 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fec75-106">개요</span><span class="sxs-lookup"><span data-stu-id="fec75-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="fec75-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="fec75-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies] [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fec75-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fec75-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="fec75-109">설명</span><span class="sxs-lookup"><span data-stu-id="fec75-109">Description</span></span>

<span data-ttu-id="fec75-110">`dotnet run` 명령은 하나의 명령을 사용하여 소스 코드에서 응용 프로그램을 실행하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-110">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="fec75-111">명령줄에서 빠른 반복 개발에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-111">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="fec75-112">이 명령은 코드 빌드 시 [`dotnet build`](dotnet-build.md) 명령에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-112">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="fec75-113">프로젝트를 먼저 복원해야 하는 등, 빌드에 대한 요구 사항은 `dotnet run`에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-113">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="fec75-114">출력 파일은 기본 위치, 즉 `bin/<configuration>/<target>`에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-114">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="fec75-115">예를 들어 `netcoreapp1.0` 응용 프로그램이 있고 `dotnet run`을 실행하는 경우 출력은 `bin/Debug/netcoreapp1.0`에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-115">For example if you have a `netcoreapp1.0` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp1.0`.</span></span> <span data-ttu-id="fec75-116">필요에 따라 파일을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-116">Files are overwritten as needed.</span></span> <span data-ttu-id="fec75-117">임시 파일은 `obj` 디렉터리에 놓입니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-117">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="fec75-118">프로젝트가 여러 프레임워크를 지정하는 경우 프레임워크를 지정하는 데 `-f|--framework <FRAMEWORK>` 옵션을 사용하지 않은 한, `dotnet run`을 실행하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-118">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="fec75-119">`dotnet run` 명령은 빌드된 어셈블리가 아닌 프로젝트의 컨텍스트에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-119">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="fec75-120">대신 프레임워크 종속 응용 프로그램 DLL을 실행하려고 하는 경우 명령 없이 [dotnet](dotnet.md)을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-120">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="fec75-121">예를 들어 `myapp.dll`을 실행하려면 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-121">For example, to run `myapp.dll`, use:</span></span>

```
dotnet myapp.dll
```

<span data-ttu-id="fec75-122">`dotnet` 드라이버에 대한 자세한 내용은 [.NET Core 명령줄 도구(CLI)](index.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fec75-122">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="fec75-123">응용 프로그램을 실행하기 위해 `dotnet run` 명령은 NuGet 캐시에서 공유 런타임의 외부에 있는 응용 프로그램의 종속성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-123">In order to run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="fec75-124">캐시된 종속성을 사용하기 때문에 프로덕션 환경에서 응용 프로그램을 실행하는 데 `dotnet run`을 사용하는 것은 바람직하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-124">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="fec75-125">대신, [`dotnet publish`](dotnet-publish.md) 명령을 사용하여 [배포를 만들고](../deploying/index.md) 게시된 출력을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-125">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="fec75-126">옵션</span><span class="sxs-lookup"><span data-stu-id="fec75-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="fec75-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="fec75-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`--`

<span data-ttu-id="fec75-128">실행 중인 응용 프로그램에 대한 인수에서 `dotnet run`에 대한 인수를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-128">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="fec75-129">이 인수 다음의 모든 인수가 실행 중인 응용 프로그램에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-129">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="fec75-130">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-130">Defines the build configuration.</span></span> <span data-ttu-id="fec75-131">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-131">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="fec75-132">지정된 [프레임워크](../../standard/frameworks.md)를 사용하여 앱을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-132">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="fec75-133">프레임워크는 프로젝트 파일에 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-133">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="fec75-134">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-134">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="fec75-135">이것은 *project.assets.json*을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-135">This is equivalent to deleting *project.assets.json*.</span></span>

`-h|--help`

<span data-ttu-id="fec75-136">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-136">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="fec75-137">응용 프로그램을 시작할 때 사용할 시작 프로필(있는 경우)의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-137">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="fec75-138">시작 프로필은 *launchSettings.json* 파일에서 정의되고 일반적으로 `Development`, `Staging` 및 `Production`이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-138">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging` and `Production`.</span></span> <span data-ttu-id="fec75-139">자세한 내용은 [여러 환경 사용](/aspnet/core/fundamentals/environments)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fec75-139">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="fec75-140">실행하기 전에 프로젝트를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-140">Doesn't build the project before running.</span></span>

`--no-dependencies`

<span data-ttu-id="fec75-141">프로젝트 간(P2P) 참조를 사용하여 프로젝트를 복원할 경우 참조가 아닌 루트 프로젝트를 복원하세요.</span><span class="sxs-lookup"><span data-stu-id="fec75-141">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="fec75-142">응용 프로그램을 구성하는 데 *launchSettings.json*을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-142">Doesn't attempt to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="fec75-143">명령을 실행할 때 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-143">Doesn't perform an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="fec75-144">실행할 프로젝트 파일의 경로를 지정합니다(폴더 이름 또는 전체 경로).</span><span class="sxs-lookup"><span data-stu-id="fec75-144">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="fec75-145">지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-145">It defaults to the current directory if not specified.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="fec75-146">패키지를 복원할 대상 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-146">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="fec75-147">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fec75-147">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fec75-148">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fec75-148">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="fec75-149">실행 중인 응용 프로그램에 대한 인수에서 `dotnet run`에 대한 인수를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-149">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="fec75-150">이 인수 다음의 모든 인수가 실행 중인 응용 프로그램에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-150">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="fec75-151">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-151">Defines the build configuration.</span></span> <span data-ttu-id="fec75-152">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-152">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="fec75-153">지정된 [프레임워크](../../standard/frameworks.md)를 사용하여 앱을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-153">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="fec75-154">프레임워크는 프로젝트 파일에 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-154">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="fec75-155">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-155">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="fec75-156">프로젝트 파일의 경로 및 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-156">Specifies the path and name of the project file.</span></span> <span data-ttu-id="fec75-157">(참고 참조) 지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-157">(See the NOTE.) It defaults to the current directory if not specified.</span></span>

> [!NOTE]
> <span data-ttu-id="fec75-158">`-p|--project` 옵션과 함께 프로젝트 파일의 경로와 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-158">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="fec75-159">CLI의 재발로 인해 폴더 경로에 .NET Core SDK 1.x를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-159">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="fec75-160">이 문제에 대한 자세한 내용은 [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992)(dotnet run -p로 프로젝트를 시작할 수 없음(dotnet/cli #5992))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fec75-160">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="fec75-161">예제</span><span class="sxs-lookup"><span data-stu-id="fec75-161">Examples</span></span>

<span data-ttu-id="fec75-162">현재 디렉터리에 있는 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-162">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="fec75-163">지정된 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-163">Run the specified project:</span></span>

`dotnet run --project /projects/proj1/proj1.csproj`

<span data-ttu-id="fec75-164">현재 디렉터리에 있는 프로젝트를 실행합니다. `--` 인수가 사용되므로 이 예제의 `--help` 인수는 응용 프로그램에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="fec75-164">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the `--` argument is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="fec75-165">최소 출력만을 표시하는 현재 디렉터리에 프로젝트에 대한 종속성 및 도구를 저장한 다음, 프로젝트를 실행합니다(.NET Core SDK 2.0 이상 버전).</span><span class="sxs-lookup"><span data-stu-id="fec75-165">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`