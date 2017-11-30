---
title: "dotnet publish 명령 - .NET Core CLI"
description: "dotnet publish 명령은 .NET Core 프로젝트를 디렉터리에 게시합니다."
author: mairaw
ms.author: mairaw
ms.date: 09/01/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: d59ba8cf74a63c7d4a2234989477b5778fa0148f
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2017
---
# <a name="dotnet-publish"></a><span data-ttu-id="19448-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="19448-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="19448-104">이름</span><span class="sxs-lookup"><span data-stu-id="19448-104">Name</span></span>

<span data-ttu-id="19448-105">`dotnet publish` - 호스팅 시스템에 배포하기 위해 응용 프로그램 및 해당 종속성을 폴더에 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="19448-106">개요</span><span class="sxs-lookup"><span data-stu-id="19448-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="19448-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="19448-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [no-dependencies] [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="19448-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="19448-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="19448-109">설명</span><span class="sxs-lookup"><span data-stu-id="19448-109">Description</span></span>

<span data-ttu-id="19448-110">`dotnet publish`는 응용 프로그램을 컴파일하고 프로젝트 파일에 지정된 종속성을 읽은 다음 결과 파일 집합을 디렉터리에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-110">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="19448-111">출력에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="19448-111">The output will contain the following:</span></span>

* <span data-ttu-id="19448-112">*dll* 확장과 함께 어셈블리의 IL(중간 언어) 코드</span><span class="sxs-lookup"><span data-stu-id="19448-112">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
* <span data-ttu-id="19448-113">프로젝트의 종속성이 모두 포함된 *.deps.json* 파일</span><span class="sxs-lookup"><span data-stu-id="19448-113">*.deps.json* file that contains all of the dependencies of the project.</span></span>
* <span data-ttu-id="19448-114">런타임에 대한 기타 구성 옵션(예: 가비지 수집 유형)뿐만 아니라 응용 프로그램에서 예상하는 공유 런타임을 지정하는 *.runtime.config.json* 파일</span><span class="sxs-lookup"><span data-stu-id="19448-114">*.runtime.config.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
* <span data-ttu-id="19448-115">응용 프로그램의 종속성.</span><span class="sxs-lookup"><span data-stu-id="19448-115">The application's dependencies.</span></span> <span data-ttu-id="19448-116">이러한 종속성은 NuGet 캐시에서 출력 폴더로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="19448-116">These are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="19448-117">`dotnet publish` 명령의 출력은 실행을 위해 호스팅 시스템(예: 서버, PC, Mac, 랩톱)으로 배포할 준비가 되었으며 응용 프로그램의 배포를 준비하는 공식적으로 지원되는 유일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="19448-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution and is the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="19448-118">프로젝트에서 지정하는 배포 유형에 따라 호스팅 시스템에 .NET Core 공유 런타임이 설치되어 있을 수도 있고 그렇지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19448-118">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="19448-119">자세한 내용은 [.NET Core 응용 프로그램 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19448-119">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="19448-120">게시된 응용 프로그램의 디렉터리 구조에 대해서는 [디렉터리 구조](/aspnet/core/hosting/directory-structure)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19448-120">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

## <a name="arguments"></a><span data-ttu-id="19448-121">인수</span><span class="sxs-lookup"><span data-stu-id="19448-121">Arguments</span></span>

`PROJECT`

<span data-ttu-id="19448-122">게시할 프로젝트이며, 지정하지 않을 경우 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="19448-122">The project to publish, which defaults to the current directory if not specified.</span></span>

## <a name="options"></a><span data-ttu-id="19448-123">옵션</span><span class="sxs-lookup"><span data-stu-id="19448-123">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="19448-124">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="19448-124">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="19448-125">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-125">Defines the build configuration.</span></span> <span data-ttu-id="19448-126">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="19448-126">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="19448-127">지정한 [대상 프레임워크](../../standard/frameworks.md)에 대한 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-127">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="19448-128">프로젝트 파일에 대상 프레임워크를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-128">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="19448-129">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-129">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="19448-130">이것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19448-130">This is equivalent to deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="19448-131">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-131">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="19448-132">앱을 통해 게시된 패키지 집합을 잘라내는 데 사용할 하나 이상의 [대상 매니페스트](../deploying/runtime-store.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-132">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="19448-133">매니페스트 파일은 [`dotnet store` 명령](dotnet-store.md) 출력의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="19448-133">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="19448-134">여러 매니페스트를 지정하려면 각 매니페스트에 대해 `--manifest` 옵션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-134">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="19448-135">이 옵션은 .NET Core 2.0 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19448-135">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="19448-136">프로젝트 간 참조를 무시하고 루트 프로젝트만 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-136">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="19448-137">명령을 실행할 때 암시적 복원을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19448-137">Doesn't perform an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="19448-138">출력 디렉터리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-138">Specifies the path for the output directory.</span></span> <span data-ttu-id="19448-139">지정하지 않으면 프레임워크 종속 배포의 경우 *./bin/[configuration]/[framework]/*로, 자체 포함 배포의 경우 *./bin/[configuration]/[framework]/[runtime]*으로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="19448-139">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>
<span data-ttu-id="19448-140">상대 경로가 제공 하는 경우 프로젝트 파일 위치에는 현재 작업 디렉터리 하지 상대적 생성 된 출력 디렉터리가입니다.</span><span class="sxs-lookup"><span data-stu-id="19448-140">If a relative path is provided, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="19448-141">대상 컴퓨터에 런타임을 설치할 필요가 없도록 응용 프로그램을 통해 .NET Core 런타임을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-141">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="19448-142">런타임 식별자를 지정할 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="19448-142">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="19448-143">다른 배포 유형에 대 한 자세한 내용은 참조 [.NET Core 응용 프로그램 배포](../deploying/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-143">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="19448-144">지정된 런타임에 대한 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-144">Publishes the application for a given runtime.</span></span> <span data-ttu-id="19448-145">[SCD(자체 포함 배포_](../deploying/index.md#self-contained-deployments-scd)를 만들 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19448-145">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="19448-146">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19448-146">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="19448-147">기본값은 [FDD(프레임워크 종속 배포)](../deploying/index.md#framework-dependent-deployments-fdd)를 게시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19448-147">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="19448-148">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-148">Sets the verbosity level of the command.</span></span> <span data-ttu-id="19448-149">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="19448-149">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="19448-150">프로젝트 파일의 버전 필드에서 별표(`*`)를 대신할 버전 접미사를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-150">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="19448-151">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="19448-151">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="19448-152">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-152">Defines the build configuration.</span></span> <span data-ttu-id="19448-153">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="19448-153">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="19448-154">지정한 [대상 프레임워크](../../standard/frameworks.md)에 대한 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-154">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="19448-155">프로젝트 파일에 대상 프레임워크를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-155">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="19448-156">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-156">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="19448-157">앱을 통해 게시된 패키지 집합을 잘라내는 데 사용할 하나 이상의 [대상 매니페스트](../deploying/runtime-store.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-157">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="19448-158">매니페스트 파일은 [`dotnet store` 명령](dotnet-store.md) 출력의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="19448-158">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="19448-159">여러 매니페스트를 지정하려면 각 매니페스트에 대해 `--manifest` 옵션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-159">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="19448-160">이 옵션은 .NET Core 2.0 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19448-160">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="19448-161">출력 디렉터리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-161">Specifies the path for the output directory.</span></span> <span data-ttu-id="19448-162">지정하지 않으면 프레임워크 종속 배포의 경우 *./bin/[configuration]/[framework]/*로, 자체 포함 배포의 경우 *./bin/[configuration]/[framework]/[runtime]*으로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="19448-162">If not specified, it defaults to *./bin/[configuration]/[framework]/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]* for a self-contained deployment.</span></span>
<span data-ttu-id="19448-163">상대 경로가 제공 하는 경우 프로젝트 파일 위치에는 현재 작업 디렉터리 하지 상대적 생성 된 출력 디렉터리가입니다.</span><span class="sxs-lookup"><span data-stu-id="19448-163">If a relative path is provided, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="19448-164">지정된 런타임에 대한 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-164">Publishes the application for a given runtime.</span></span> <span data-ttu-id="19448-165">[SCD(자체 포함 배포_](../deploying/index.md#self-contained-deployments-scd)를 만들 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="19448-165">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span> <span data-ttu-id="19448-166">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19448-166">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="19448-167">기본값은 [FDD(프레임워크 종속 배포)](../deploying/index.md#framework-dependent-deployments-fdd)를 게시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="19448-167">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="19448-168">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-168">Sets the verbosity level of the command.</span></span> <span data-ttu-id="19448-169">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="19448-169">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="19448-170">프로젝트 파일의 버전 필드에서 별표(`*`)를 대신할 버전 접미사를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-170">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="19448-171">예제</span><span class="sxs-lookup"><span data-stu-id="19448-171">Examples</span></span>

<span data-ttu-id="19448-172">현재 디렉터리에 있는 프로젝트를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-172">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="19448-173">지정된 프로젝트 파일을 사용하여 응용 프로그램을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-173">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`
    
<span data-ttu-id="19448-174">`netcoreapp1.1` 프레임워크를 사용하여 현재 디렉터리에 있는 프로젝트를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-174">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`
    
<span data-ttu-id="19448-175">`netcoreapp1.1` 프레임워크 및 `OS X 10.10`에 대한 런타임을 사용하여 현재 응용 프로그램을 게시합니다. 프로젝트 파일에서 이 RID를 나열해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19448-175">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a><span data-ttu-id="19448-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19448-176">See also</span></span>

* [<span data-ttu-id="19448-177">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="19448-177">Target frameworks</span></span>](../../standard/frameworks.md)
* [<span data-ttu-id="19448-178">RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="19448-178">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
