---
title: dotnet restore 명령 - .NET Core CLI
description: dotnet restore 명령을 사용하여 종속성 및 프로젝트 관련 도구를 복원하는 방법을 알아봅니다.
author: mairaw
ms.author: mairaw
ms.date: 11/30/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: b20d9e72fcc754a7538e9c54677a86a1c9bbc2d1
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-restore"></a><span data-ttu-id="eea3d-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="eea3d-103">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="eea3d-104">name</span><span class="sxs-lookup"><span data-stu-id="eea3d-104">Name</span></span>

<span data-ttu-id="eea3d-105">`dotnet restore` - 프로젝트의 종속성 및 도구를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-105">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="eea3d-106">개요</span><span class="sxs-lookup"><span data-stu-id="eea3d-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="eea3d-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="eea3d-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="eea3d-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="eea3d-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="eea3d-109">설명</span><span class="sxs-lookup"><span data-stu-id="eea3d-109">Description</span></span>

<span data-ttu-id="eea3d-110">`dotnet restore` 명령은 NuGet을 사용하여 프로젝트 파일에 지정된 종속성 및 프로젝트 관련 도구를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-110">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="eea3d-111">기본적으로 종속성 및 도구의 복원은 병렬로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-111">By default, the restoration of dependencies and tools are performed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="eea3d-112">종속성을 복원하려면 NuGet에 패키지가 있는 피드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-112">In order to restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="eea3d-113">피드는 일반적으로 *NuGet.config* 구성 파일을 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-113">Feeds are usually provided via the *NuGet.config* configuration file.</span></span> <span data-ttu-id="eea3d-114">CLI 도구가 설치될 때 기본 구성 파일이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-114">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="eea3d-115">프로젝트 디렉터리에 고유한 *NuGet.config* 파일을 만들어 추가 피드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-115">You specify additional feeds by creating your own *NuGet.config* file in the project directory.</span></span> <span data-ttu-id="eea3d-116">또한 명령 프롬프트에서 호출당 추가 피드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-116">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="eea3d-117">종속성의 경우 복원 작업 중 `--packages` 인수를 사용하여 복원된 패키지가 배치될 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-117">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="eea3d-118">지정하지 않으면 모든 운영 체제에서 사용자의 홈 디렉터리(예: Linux의 경우 */home/user1* 또는 Windows의 경우 *C:\Users\user1*)에 있는 `.nuget/packages` 디렉터리에 있는 기본 NuGet 패키지 캐시가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-118">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems (for example, */home/user1* on Linux or *C:\Users\user1* on Windows).</span></span>

<span data-ttu-id="eea3d-119">프로젝트 관련 도구의 경우 `dotnet restore`는 먼저 도구가 압축된 패키지를 복원한 다음 프로젝트 파일에 지정된 대로 도구의 종속성을 계속 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-119">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

<span data-ttu-id="eea3d-120">`dotnet restore` 명령의 동작은 *Nuget.Config* 파일(있는 경우)에 있는 일부 설정의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-120">The behavior of the `dotnet restore` command is affected by some of the settings in the *Nuget.Config* file, if present.</span></span> <span data-ttu-id="eea3d-121">예를 들어 *NuGet.Config*의 `globalPackagesFolder`를 설정하면 복원된 NuGet 패키지가 지정한 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-121">For example, setting the `globalPackagesFolder` in *NuGet.Config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="eea3d-122">`dotnet restore` 명령의 `--packages` 옵션을 지정하는 대신 이 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-122">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="eea3d-123">자세한 내용은 [NuGet.Config 참조](/nuget/schema/nuget-config-file)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eea3d-123">For more information, see the [NuGet.Config reference](/nuget/schema/nuget-config-file).</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="eea3d-124">암시적 `dotnet restore`</span><span class="sxs-lookup"><span data-stu-id="eea3d-124">Implicit `dotnet restore`</span></span>

<span data-ttu-id="eea3d-125">.NET Core 2.0부터는 다음 명령을 실행할 때 필요한 경우 `dotnet restore`가 암시적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-125">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="eea3d-126">대부분의 경우 더 이상 `dotnet restore` 명령을 명시적으로 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-126">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span> 

<span data-ttu-id="eea3d-127">일부 경우 `dotnet restore`를 암시적으로 실행하기가 불편합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-127">In some cases, it is inconvenient for `dotnet restore` to run implicitly.</span></span> <span data-ttu-id="eea3d-128">예를 들어 빌드 시스템과 같은 자동화된 일부 시스템은 네트워크 사용량을 제어할 수 있도록 복원이 발생하는 경우를 제어하기 위해 명시적으로 `dotnet restore`를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-128">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="eea3d-129">`dotnet restore`가 암시적으로 실행되지 않게 하려면 이러한 명령 중 하나와 함께 `--no-restore` 스위치를 사용하여 암시적 복원을 사용하지 않도록 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-129">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` switch with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="eea3d-130">인수</span><span class="sxs-lookup"><span data-stu-id="eea3d-130">Arguments</span></span>

`ROOT`

<span data-ttu-id="eea3d-131">프로젝트 파일을 복원하는 선택적 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-131">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="eea3d-132">옵션</span><span class="sxs-lookup"><span data-stu-id="eea3d-132">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="eea3d-133">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="eea3d-133">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="eea3d-134">복원 작업에 사용할 NuGet 구성 파일(*NuGet.config*)입니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-134">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="eea3d-135">여러 프로젝트를 병렬로 복원을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-135">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="eea3d-136">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-136">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="eea3d-137">이것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-137">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="eea3d-138">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-138">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="eea3d-139">버전 요구 사항을 충족하는 패키지가 있는 경우 실패한 소스에 대해서만 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-139">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="eea3d-140">패키지 및 HTTP 요청을 캐시하지 하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-140">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="eea3d-141">프로젝트 간(P2P) 참조를 사용하여 프로젝트를 복원할 경우 참조가 아닌 루트 프로젝트를 복원하세요.</span><span class="sxs-lookup"><span data-stu-id="eea3d-141">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="eea3d-142">복원된 패키지에 대한 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-142">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="eea3d-143">패키지 복원의 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-143">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="eea3d-144">*.csproj* 파일의 `<RuntimeIdentifiers>` 태그에 명시적으로 나열되지 않은 런타임의 패키지를 복원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-144">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="eea3d-145">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eea3d-145">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="eea3d-146">이 옵션을 여러 번 지정하여 여러 RID를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-146">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="eea3d-147">복원 작업 중 사용할 NuGet 패키지 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-147">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="eea3d-148">이 소스는 *NuGet.config* 파일에 지정된 모든 소스를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-148">This overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="eea3d-149">이 옵션을 여러 번 지정하여 여러 소스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-149">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="eea3d-150">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="eea3d-151">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="eea3d-152">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="eea3d-152">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="eea3d-153">복원 작업에 사용할 NuGet 구성 파일(*NuGet.config*)입니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-153">The NuGet configuration file (*NuGet.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="eea3d-154">여러 프로젝트를 병렬로 복원을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-154">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="eea3d-155">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-155">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="eea3d-156">버전 요구 사항을 충족하는 패키지가 있는 경우 실패한 소스에 대해서만 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-156">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="eea3d-157">패키지 및 HTTP 요청을 캐시하지 하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-157">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="eea3d-158">프로젝트 간(P2P) 참조를 사용하여 프로젝트를 복원할 경우 참조가 아닌 루트 프로젝트를 복원하세요.</span><span class="sxs-lookup"><span data-stu-id="eea3d-158">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="eea3d-159">복원된 패키지에 대한 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-159">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="eea3d-160">패키지 복원의 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-160">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="eea3d-161">*.csproj* 파일의 `<RuntimeIdentifiers>` 태그에 명시적으로 나열되지 않은 런타임의 패키지를 복원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-161">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="eea3d-162">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eea3d-162">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="eea3d-163">이 옵션을 여러 번 지정하여 여러 RID를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-163">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="eea3d-164">복원 작업 중 사용할 NuGet 패키지 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-164">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="eea3d-165">이 소스는 *NuGet.config* 파일에 지정된 모든 소스를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-165">This overrides all of the sources specified in the *NuGet.config* files.</span></span> <span data-ttu-id="eea3d-166">이 옵션을 여러 번 지정하여 여러 소스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-166">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="eea3d-167">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-167">Sets the verbosity level of the command.</span></span> <span data-ttu-id="eea3d-168">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-168">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="eea3d-169">예제</span><span class="sxs-lookup"><span data-stu-id="eea3d-169">Examples</span></span>

<span data-ttu-id="eea3d-170">현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-170">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="eea3d-171">지정된 경로에 있는 `app1` 프로젝트에 대한 종속성 및 도구를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-171">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="eea3d-172">소스로 제공된 파일 경로를 사용하여 현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-172">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="eea3d-173">소스로 제공된 2개의 파일 경로를 사용하여 현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-173">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="eea3d-174">현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원하고 최소 출력만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eea3d-174">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`
