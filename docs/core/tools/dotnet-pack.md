---
title: dotnet pack 명령 - .NET Core CLI
description: dotnet pack 명령은 .NET Core 프로젝트에 대한 NuGet 패키지를 만듭니다.
author: mairaw
ms.author: mairaw
ms.date: 03/10/2018
ms.openlocfilehash: 6e6136e22c4bac201cfa0e4af321329432c04936
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-pack"></a><span data-ttu-id="7add7-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="7add7-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="7add7-104">name</span><span class="sxs-lookup"><span data-stu-id="7add7-104">Name</span></span>

<span data-ttu-id="7add7-105">`dotnet pack` - 코드를 NuGet 패키지로 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7add7-106">개요</span><span class="sxs-lookup"><span data-stu-id="7add7-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7add7-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7add7-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7add7-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7add7-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="7add7-109">설명</span><span class="sxs-lookup"><span data-stu-id="7add7-109">Description</span></span>

<span data-ttu-id="7add7-110">`dotnet pack` 명령은 프로젝트를 빌드하고 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="7add7-111">이 명령의 결과가 NuGet 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="7add7-112">`--include-symbols` 옵션이 있는 경우 디버그 기호를 포함하는 다른 패키지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="7add7-113">압축된 프로젝트의 NuGet 종속성은 *.nuspec* 파일에 추가되므로 패키지를 설치할 때 적절히 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="7add7-114">프로젝트 간 참조는 프로젝트 내에서 패키지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="7add7-115">현재 프로젝트 간 종속성이 있는 경우 프로젝트당 패키지가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="7add7-116">`dotnet pack`은 기본적으로 프로젝트를 먼저 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="7add7-117">이렇게 하지 않으려면 `--no-build` 옵션을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="7add7-118">이 옵션은 코드가 이미 빌드된 CI(연속 통합) 빌드 시나리오에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-118">This is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="7add7-119">압축 프로세스에 대한 `dotnet pack` 명령에 MSBuild 속성을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="7add7-120">자세한 내용은 [NuGet 메타데이터 속성](csproj.md#nuget-metadata-properties) 및 [MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7add7-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="7add7-121">[예제](#examples) 섹션에서는 몇 가지 시나리오에 MSBuild /p 스위치를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-121">The [Examples](#examples) section shows how to use the MSBuild /p switch for a couple of different scenarios.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="7add7-122">인수</span><span class="sxs-lookup"><span data-stu-id="7add7-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="7add7-123">압축할 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-123">The project to pack.</span></span> <span data-ttu-id="7add7-124">[csproj file](csproj.md) 파일 또는 디렉터리에 대한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-124">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="7add7-125">생략하면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-125">If omitted, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="7add7-126">옵션</span><span class="sxs-lookup"><span data-stu-id="7add7-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7add7-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7add7-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="7add7-128">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-128">Defines the build configuration.</span></span> <span data-ttu-id="7add7-129">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-129">The default value is `Debug`.</span></span>

<span data-ttu-id="7add7-130">`--force` 마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-130">`--force` Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="7add7-131">이것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-131">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="7add7-132">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-132">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="7add7-133">NuGet 패키지에 소스 파일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-133">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="7add7-134">소스 파일은 `nupkg`의 `src` 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-134">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="7add7-135">기호 `nupkg`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-135">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="7add7-136">압축하기 전에 프로젝트를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-136">Doesn't build the project before packing.</span></span>

`--no-dependencies`

<span data-ttu-id="7add7-137">프로젝트 간 참조를 무시하고 루트 프로젝트만 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-137">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="7add7-138">명령을 실행할 때 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-138">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7add7-139">지정된 디렉터리에 빌드된 패키지를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-139">Places the built packages in the directory specified.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="7add7-140">패키지를 복원할 대상 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-140">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="7add7-141">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7add7-141">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-s|--serviceable`

<span data-ttu-id="7add7-142">패키지에 서비스 가능 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-142">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="7add7-143">자세한 내용은 [.NET 블로그: .NET 4.5.1에서 .NET NuGet 라이브러리에 대한 Microsoft 보안 업데이트를 지원함](https://aka.ms/nupkgservicing)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7add7-143">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="7add7-144">프로젝트에서 `$(VersionSuffix)` MSBuild 속성에 대한 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-144">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="7add7-145">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-145">Sets the verbosity level of the command.</span></span> <span data-ttu-id="7add7-146">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-146">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7add7-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7add7-147">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="7add7-148">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-148">Defines the build configuration.</span></span> <span data-ttu-id="7add7-149">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-149">The default value is `Debug`.</span></span>

`-h|--help`

<span data-ttu-id="7add7-150">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-150">Prints out a short help for the command.</span></span>

`--include-source`

<span data-ttu-id="7add7-151">NuGet 패키지에 소스 파일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-151">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="7add7-152">소스 파일은 `nupkg`의 `src` 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-152">The sources files are included in the `src` folder within the `nupkg`.</span></span>

`--include-symbols`

<span data-ttu-id="7add7-153">기호 `nupkg`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-153">Generates the symbols `nupkg`.</span></span>

`--no-build`

<span data-ttu-id="7add7-154">압축하기 전에 프로젝트를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-154">Doesn't build the project before packing.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7add7-155">지정된 디렉터리에 빌드된 패키지를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-155">Places the built packages in the directory specified.</span></span>

`-s|--serviceable`

<span data-ttu-id="7add7-156">패키지에 서비스 가능 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-156">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="7add7-157">자세한 내용은 [.NET 블로그: .NET 4.5.1에서 .NET NuGet 라이브러리에 대한 Microsoft 보안 업데이트를 지원함](https://aka.ms/nupkgservicing)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7add7-157">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="7add7-158">프로젝트에서 `$(VersionSuffix)` MSBuild 속성에 대한 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-158">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="7add7-159">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-159">Sets the verbosity level of the command.</span></span> <span data-ttu-id="7add7-160">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-160">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="7add7-161">예제</span><span class="sxs-lookup"><span data-stu-id="7add7-161">Examples</span></span>

<span data-ttu-id="7add7-162">현재 디렉터리에 있는 프로젝트를 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-162">Pack the project in the current directory:</span></span>

`dotnet pack`

<span data-ttu-id="7add7-163">`app1` 프로젝트를 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-163">Pack the `app1` project:</span></span>

`dotnet pack ~/projects/app1/project.csproj`

<span data-ttu-id="7add7-164">현재 디렉터리에 있는 프로젝트를 압축하고 결과 패키지를 `nupkgs` 폴더에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-164">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

`dotnet pack --output nupkgs`

<span data-ttu-id="7add7-165">현재 디렉터리에 있는 프로젝트를 `nupkgs` 폴더로 압축하고 빌드 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-165">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

`dotnet pack --no-build --output nupkgs`

<span data-ttu-id="7add7-166">*.csproj* 파일에서 프로젝트의 버전 접미사를 `<VersionSuffix>$(VersionSuffix)</VersionSuffix>`로 구성한 상태로 현재 프로젝트를 압축하고 결과 패키지 버전을 지정된 접미사로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-166">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

`dotnet pack --version-suffix "ci-1234"`

<span data-ttu-id="7add7-167">`PackageVersion` MSBuild 속성을 사용하여 패키지 버전을 `2.1.0`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-167">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

`dotnet pack /p:PackageVersion=2.1.0`

<span data-ttu-id="7add7-168">특정 [대상 프레임워크](../../standard/frameworks.md)에 대한 프로젝트를 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="7add7-168">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

`dotnet pack /p:TargetFrameworks=net45`

<span data-ttu-id="7add7-169">프로젝트를 압축하고 복원 작업에 대한 특정 런타임(Windows 10)을 사용합니다(.NET Core SDK 2.0 이상 버전).</span><span class="sxs-lookup"><span data-stu-id="7add7-169">Pack the project and use a specific runtime (Windows 10) for the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet pack --runtime win10-x64`