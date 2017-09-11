---
title: "dotnet pack 명령 - .NET Core CLI"
description: "dotnet pack 명령은 .NET Core 프로젝트에 대한 NuGet 패키지를 만듭니다."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 8594c863d67baf0237b63e61f28ca9ee315eeddf
ms.contentlocale: ko-kr
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-pack"></a><span data-ttu-id="fa80f-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="fa80f-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="fa80f-104">이름</span><span class="sxs-lookup"><span data-stu-id="fa80f-104">Name</span></span>

<span data-ttu-id="fa80f-105">`dotnet pack` - 코드를 NuGet 패키지로 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fa80f-106">개요</span><span class="sxs-lookup"><span data-stu-id="fa80f-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="fa80f-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="fa80f-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies] [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fa80f-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fa80f-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="fa80f-109">설명</span><span class="sxs-lookup"><span data-stu-id="fa80f-109">Description</span></span>

<span data-ttu-id="fa80f-110">`dotnet pack` 명령은 프로젝트를 빌드하고 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="fa80f-111">이 명령의 결과가 NuGet 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="fa80f-112">`--include-symbols` 옵션이 있는 경우 디버그 기호를 포함하는 다른 패키지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="fa80f-113">압축된 프로젝트의 NuGet 종속성은 *.nuspec* 파일에 추가되므로 패키지를 설치할 때 적절히 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="fa80f-114">프로젝트 간 참조는 프로젝트 내에서 패키지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="fa80f-115">현재 프로젝트 간 종속성이 있는 경우 프로젝트당 패키지가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="fa80f-116">`dotnet pack`은 기본적으로 프로젝트를 먼저 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="fa80f-117">이렇게 하지 않으려면 `--no-build` 옵션을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="fa80f-118">이 옵션은 코드가 이미 빌드된 CI(연속 통합) 빌드 시나리오에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-118">This is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="fa80f-119">압축 프로세스에 대한 `dotnet pack` 명령에 MSBuild 속성을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="fa80f-120">자세한 내용은 [NuGet 메타데이터 속성](csproj.md#nuget-metadata-properties) 및 [MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa80f-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

## <a name="arguments"></a><span data-ttu-id="fa80f-121">인수</span><span class="sxs-lookup"><span data-stu-id="fa80f-121">Arguments</span></span>

`PROJECT`

<span data-ttu-id="fa80f-122">압축할 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-122">The project to pack.</span></span> <span data-ttu-id="fa80f-123">[csproj file](csproj.md) 파일 또는 디렉터리에 대한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-123">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="fa80f-124">생략하면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-124">If omitted, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="fa80f-125">옵션</span><span class="sxs-lookup"><span data-stu-id="fa80f-125">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="fa80f-126">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="fa80f-126">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="fa80f-127">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-127">Defines the build configuration.</span></span> <span data-ttu-id="fa80f-128">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-128">The default value is `Debug`.</span></span>

<span data-ttu-id="fa80f-129">`--force` 마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-129">`--force` Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="fa80f-130">이것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-130">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="fa80f-131">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-131">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="fa80f-132">NuGet 패키지에 소스 파일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-132">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="fa80f-133">소스 파일은 `nupkg`의 `src` 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-133">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="fa80f-134">기호 `nupkg`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-134">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="fa80f-135">압축하기 전에 프로젝트를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-135">Doesn't build the project before packing.</span></span>

`--no-dependencies`

<span data-ttu-id="fa80f-136">프로젝트 간 참조를 무시하고 루트 프로젝트만 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-136">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="fa80f-137">명령을 실행할 때 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-137">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="fa80f-138">지정된 디렉터리에 빌드된 패키지를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-138">Places the built packages in the directory specified.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="fa80f-139">패키지를 복원할 대상 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-139">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="fa80f-140">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa80f-140">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-s|--serviceable`

<span data-ttu-id="fa80f-141">패키지에 서비스 가능 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-141">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="fa80f-142">자세한 내용은 [.NET 블로그: .NET 4.5.1에서 .NET NuGet 라이브러리에 대한 Microsoft 보안 업데이트를 지원함](https://aka.ms/nupkgservicing)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa80f-142">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="fa80f-143">프로젝트에서 `$(VersionSuffix)` MSBuild 속성에 대한 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-143">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="fa80f-144">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-144">Sets the verbosity level of the command.</span></span> <span data-ttu-id="fa80f-145">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-145">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fa80f-146">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fa80f-146">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="fa80f-147">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-147">Defines the build configuration.</span></span> <span data-ttu-id="fa80f-148">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-148">The default value is `Debug`.</span></span>

`-h|--help`

<span data-ttu-id="fa80f-149">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-149">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="fa80f-150">NuGet 패키지에 소스 파일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-150">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="fa80f-151">소스 파일은 `nupkg`의 `src` 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-151">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="fa80f-152">기호 `nupkg`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-152">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="fa80f-153">압축하기 전에 프로젝트를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-153">Doesn't build the project before packing.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="fa80f-154">지정된 디렉터리에 빌드된 패키지를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-154">Places the built packages in the directory specified.</span></span>

`-s|--serviceable`

<span data-ttu-id="fa80f-155">패키지에 서비스 가능 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-155">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="fa80f-156">자세한 내용은 [.NET 블로그: .NET 4.5.1에서 .NET NuGet 라이브러리에 대한 Microsoft 보안 업데이트를 지원함](https://aka.ms/nupkgservicing)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa80f-156">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="fa80f-157">프로젝트에서 `$(VersionSuffix)` MSBuild 속성에 대한 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-157">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="fa80f-158">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-158">Sets the verbosity level of the command.</span></span> <span data-ttu-id="fa80f-159">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-159">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="fa80f-160">예제</span><span class="sxs-lookup"><span data-stu-id="fa80f-160">Examples</span></span>

<span data-ttu-id="fa80f-161">현재 디렉터리에 있는 프로젝트를 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-161">Pack the project in the current directory:</span></span>

`dotnet pack`

<span data-ttu-id="fa80f-162">`app1` 프로젝트를 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-162">Pack the `app1` project:</span></span>

`dotnet pack ~/projects/app1/project.csproj`
    
<span data-ttu-id="fa80f-163">현재 디렉터리에 있는 프로젝트를 압축하고 결과 패키지를 `nupkgs` 폴더에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-163">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

`dotnet pack --output nupkgs`

<span data-ttu-id="fa80f-164">현재 디렉터리에 있는 프로젝트를 `nupkgs` 폴더로 압축하고 빌드 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-164">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

`dotnet pack --no-build --output nupkgs`

<span data-ttu-id="fa80f-165">*.csproj* 파일에서 프로젝트의 버전 접미사를 `<VersionSuffix>$(VersionSuffix)</VersionSuffix>`로 구성한 상태로 현재 프로젝트를 압축하고 결과 패키지 버전을 지정된 접미사로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-165">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

`dotnet pack --version-suffix "ci-1234"`

<span data-ttu-id="fa80f-166">`PackageVersion` MSBuild 속성을 사용하여 패키지 버전을 `2.1.0`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa80f-166">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

`dotnet pack /p:PackageVersion=2.1.0`

