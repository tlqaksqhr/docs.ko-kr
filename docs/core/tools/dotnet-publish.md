---
title: dotnet publish 명령 - .NET Core CLI
description: dotnet publish 명령은 .NET Core 프로젝트를 디렉터리에 게시합니다.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 38224aa8472f99df107e523667e18892384a20b0
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696662"
---
# <a name="dotnet-publish"></a><span data-ttu-id="1e32d-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="1e32d-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="1e32d-104">name</span><span class="sxs-lookup"><span data-stu-id="1e32d-104">Name</span></span>

<span data-ttu-id="1e32d-105">`dotnet publish` - 호스팅 시스템에 배포하기 위해 응용 프로그램 및 해당 종속성을 폴더에 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1e32d-106">개요</span><span class="sxs-lookup"><span data-stu-id="1e32d-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="1e32d-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1e32d-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="1e32d-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1e32d-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1e32d-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1e32d-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="1e32d-110">설명</span><span class="sxs-lookup"><span data-stu-id="1e32d-110">Description</span></span>

<span data-ttu-id="1e32d-111">`dotnet publish`는 응용 프로그램을 컴파일하고 프로젝트 파일에 지정된 종속성을 읽은 다음 결과 파일 집합을 디렉터리에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="1e32d-112">출력에는 다음과 같은 자산이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-112">The output includes the following assets:</span></span>

* <span data-ttu-id="1e32d-113">*dll* 확장과 함께 어셈블리의 IL(중간 언어) 코드</span><span class="sxs-lookup"><span data-stu-id="1e32d-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="1e32d-114">프로젝트의 종속성을 모두 포함하는 *.deps.json* 파일</span><span class="sxs-lookup"><span data-stu-id="1e32d-114">*.deps.json* file that includes all of the dependencies of the project.</span></span>
* <span data-ttu-id="1e32d-115">런타임에 대한 기타 구성 옵션(예: 가비지 수집 유형)뿐만 아니라 응용 프로그램에서 예상하는 공유 런타임을 지정하는 *.runtime.config.json* 파일</span><span class="sxs-lookup"><span data-stu-id="1e32d-115">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="1e32d-116">응용 프로그램의 종속성은 NuGet 캐시에서 출력 폴더로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-116">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="1e32d-117">`dotnet publish` 명령의 출력이 실행을 위해 호스팅 시스템(예: 서버, PC, Mac, 랩톱)에 배포할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="1e32d-118">이는 배포를 위해 응용 프로그램을 준비하는 데 공식적으로 지원되는 유일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-118">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="1e32d-119">프로젝트에서 지정하는 배포 유형에 따라 호스팅 시스템에 .NET Core 공유 런타임이 설치되어 있을 수도 있고 그렇지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="1e32d-120">자세한 내용은 [.NET Core 응용 프로그램 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e32d-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="1e32d-121">게시된 응용 프로그램의 디렉터리 구조에 대해서는 [디렉터리 구조](/aspnet/core/hosting/directory-structure)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e32d-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="1e32d-122">인수</span><span class="sxs-lookup"><span data-stu-id="1e32d-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="1e32d-123">게시할 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-123">The project to publish.</span></span> <span data-ttu-id="1e32d-124">지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-124">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="1e32d-125">옵션</span><span class="sxs-lookup"><span data-stu-id="1e32d-125">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="1e32d-126">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1e32d-126">.NET Core 2.1</span></span>](#tab/netcore21)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="1e32d-127">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-127">Defines the build configuration.</span></span> <span data-ttu-id="1e32d-128">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-128">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="1e32d-129">지정한 [대상 프레임워크](../../standard/frameworks.md)에 대한 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-129">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="1e32d-130">프로젝트 파일에 대상 프레임워크를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-130">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="1e32d-131">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-131">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="1e32d-132">이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-132">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="1e32d-133">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-133">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="1e32d-134">앱을 통해 게시된 패키지 집합을 잘라내는 데 사용할 하나 이상의 [대상 매니페스트](../deploying/runtime-store.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-134">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="1e32d-135">매니페스트 파일은 [`dotnet store` 명령](dotnet-store.md) 출력의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-135">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="1e32d-136">여러 매니페스트를 지정하려면 각 매니페스트에 대해 `--manifest` 옵션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-136">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="1e32d-137">이 옵션은 .NET Core 2.0 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-137">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-build`

<span data-ttu-id="1e32d-138">게시하기 전에 프로젝트를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-138">Doesn't build the project before publishing.</span></span> <span data-ttu-id="1e32d-139">또한 `--no-restore` 플래그를 암시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-139">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="1e32d-140">프로젝트 간 참조를 무시하고 루트 프로젝트만 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-140">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="1e32d-141">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-141">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="1e32d-142">출력 디렉터리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-142">Specifies the path for the output directory.</span></span> <span data-ttu-id="1e32d-143">지정하지 않으면 프레임워크 종속 배포의 경우 *./bin/[configuration]/[framework]/publish/* 로, 자체 포함 배포의 경우 *./bin/[configuration]/[framework]/[runtime]/publish/* 로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-143">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="1e32d-144">상대 경로인 경우 생성된 출력 디렉터리는 현재 작업 디렉터리가 아닌 프로젝트 파일 위치에 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-144">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="1e32d-145">대상 컴퓨터에 런타임을 설치할 필요가 없도록 응용 프로그램을 통해 .NET Core 런타임을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-145">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="1e32d-146">런타임 식별자를 지정할 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-146">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="1e32d-147">다른 배포 형식에 대한 자세한 내용은 [.NET Core 응용 프로그램 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e32d-147">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="1e32d-148">지정된 런타임에 대한 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-148">Publishes the application for a given runtime.</span></span> <span data-ttu-id="1e32d-149">[SCD(자체 포함 배포_](../deploying/index.md#self-contained-deployments-scd)를 만들 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-149">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="1e32d-150">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e32d-150">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="1e32d-151">기본값은 [FDD(프레임워크 종속 배포)](../deploying/index.md#framework-dependent-deployments-fdd)를 게시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-151">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="1e32d-152">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-152">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1e32d-153">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-153">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="1e32d-154">프로젝트 파일의 버전 필드에서 별표(`*`)를 대신할 버전 접미사를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-154">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="1e32d-155">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1e32d-155">.NET Core 2.0</span></span>](#tab/netcore20)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="1e32d-156">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-156">Defines the build configuration.</span></span> <span data-ttu-id="1e32d-157">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-157">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="1e32d-158">지정한 [대상 프레임워크](../../standard/frameworks.md)에 대한 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-158">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="1e32d-159">프로젝트 파일에 대상 프레임워크를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-159">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="1e32d-160">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-160">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="1e32d-161">이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-161">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="1e32d-162">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-162">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="1e32d-163">앱을 통해 게시된 패키지 집합을 잘라내는 데 사용할 하나 이상의 [대상 매니페스트](../deploying/runtime-store.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-163">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="1e32d-164">매니페스트 파일은 [`dotnet store` 명령](dotnet-store.md) 출력의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-164">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="1e32d-165">여러 매니페스트를 지정하려면 각 매니페스트에 대해 `--manifest` 옵션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-165">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="1e32d-166">이 옵션은 .NET Core 2.0 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-166">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="1e32d-167">프로젝트 간 참조를 무시하고 루트 프로젝트만 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-167">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="1e32d-168">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-168">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="1e32d-169">출력 디렉터리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-169">Specifies the path for the output directory.</span></span> <span data-ttu-id="1e32d-170">지정하지 않으면 프레임워크 종속 배포의 경우 *./bin/[configuration]/[framework]/publish/* 로, 자체 포함 배포의 경우 *./bin/[configuration]/[framework]/[runtime]/publish/* 로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-170">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="1e32d-171">상대 경로인 경우 생성된 출력 디렉터리는 현재 작업 디렉터리가 아닌 프로젝트 파일 위치에 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-171">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="1e32d-172">대상 컴퓨터에 런타임을 설치할 필요가 없도록 응용 프로그램을 통해 .NET Core 런타임을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-172">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="1e32d-173">런타임 식별자를 지정할 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-173">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="1e32d-174">다른 배포 형식에 대한 자세한 내용은 [.NET Core 응용 프로그램 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e32d-174">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="1e32d-175">지정된 런타임에 대한 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-175">Publishes the application for a given runtime.</span></span> <span data-ttu-id="1e32d-176">[SCD(자체 포함 배포_](../deploying/index.md#self-contained-deployments-scd)를 만들 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-176">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="1e32d-177">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e32d-177">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="1e32d-178">기본값은 [FDD(프레임워크 종속 배포)](../deploying/index.md#framework-dependent-deployments-fdd)를 게시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-178">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="1e32d-179">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-179">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1e32d-180">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-180">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="1e32d-181">프로젝트 파일의 버전 필드에서 별표(`*`)를 대신할 버전 접미사를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-181">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1e32d-182">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1e32d-182">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="1e32d-183">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-183">Defines the build configuration.</span></span> <span data-ttu-id="1e32d-184">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-184">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="1e32d-185">지정한 [대상 프레임워크](../../standard/frameworks.md)에 대한 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-185">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="1e32d-186">프로젝트 파일에 대상 프레임워크를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-186">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="1e32d-187">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-187">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="1e32d-188">앱을 통해 게시된 패키지 집합을 잘라내는 데 사용할 하나 이상의 [대상 매니페스트](../deploying/runtime-store.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-188">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="1e32d-189">매니페스트 파일은 [`dotnet store` 명령](dotnet-store.md) 출력의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-189">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="1e32d-190">여러 매니페스트를 지정하려면 각 매니페스트에 대해 `--manifest` 옵션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-190">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="1e32d-191">이 옵션은 .NET Core 2.0 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-191">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="1e32d-192">출력 디렉터리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-192">Specifies the path for the output directory.</span></span> <span data-ttu-id="1e32d-193">지정하지 않으면 프레임워크 종속 배포의 경우 *./bin/[configuration]/[framework]/publish/* 로, 자체 포함 배포의 경우 *./bin/[configuration]/[framework]/[runtime]/publish/* 로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-193">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="1e32d-194">상대 경로인 경우 생성된 출력 디렉터리는 현재 작업 디렉터리가 아닌 프로젝트 파일 위치에 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-194">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="1e32d-195">지정된 런타임에 대한 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-195">Publishes the application for a given runtime.</span></span> <span data-ttu-id="1e32d-196">[SCD(자체 포함 배포_](../deploying/index.md#self-contained-deployments-scd)를 만들 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-196">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="1e32d-197">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e32d-197">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="1e32d-198">기본값은 [FDD(프레임워크 종속 배포)](../deploying/index.md#framework-dependent-deployments-fdd)를 게시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-198">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="1e32d-199">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-199">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1e32d-200">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-200">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="1e32d-201">프로젝트 파일의 버전 필드에서 별표(`*`)를 대신할 버전 접미사를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-201">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="1e32d-202">예제</span><span class="sxs-lookup"><span data-stu-id="1e32d-202">Examples</span></span>

<span data-ttu-id="1e32d-203">현재 디렉터리에 있는 프로젝트를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-203">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="1e32d-204">지정된 프로젝트 파일을 사용하여 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-204">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="1e32d-205">`netcoreapp1.1` 프레임워크를 사용하여 현재 디렉터리에 있는 프로젝트를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-205">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="1e32d-206">`netcoreapp1.1` 프레임워크 및 `OS X 10.10`에 대한 런타임을 사용하여 현재 응용 프로그램을 게시합니다. 프로젝트 파일에서 이 RID를 나열해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e32d-206">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="1e32d-207">현재 응용 프로그램을 게시하지만 프로젝트 간(P2P) 참조를 복원하지 않습니다. 복원 작업 중 루트 프로젝트만 복원합니다(.NET Core SDK 2.0 이상 버전).</span><span class="sxs-lookup"><span data-stu-id="1e32d-207">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="1e32d-208">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e32d-208">See also</span></span>

* [<span data-ttu-id="1e32d-209">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="1e32d-209">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="1e32d-210">RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="1e32d-210">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
