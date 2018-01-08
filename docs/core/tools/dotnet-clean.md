---
title: "dotnet clean 명령 - .NET Core CLI"
description: "dotnet clean 명령은 현재 디렉터리를 정리합니다."
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: f56ccc485884114262cd1364cf9398e302f2c48a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-clean"></a><span data-ttu-id="218a3-103">dotnet-clean</span><span class="sxs-lookup"><span data-stu-id="218a3-103">dotnet-clean</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="218a3-104">name</span><span class="sxs-lookup"><span data-stu-id="218a3-104">Name</span></span>

<span data-ttu-id="218a3-105">`dotnet clean` - 프로젝트의 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-105">`dotnet clean` - Cleans the output of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="218a3-106">개요</span><span class="sxs-lookup"><span data-stu-id="218a3-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="218a3-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="218a3-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="218a3-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="218a3-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-v|--verbosity]
dotnet clean [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="218a3-109">설명</span><span class="sxs-lookup"><span data-stu-id="218a3-109">Description</span></span>

<span data-ttu-id="218a3-110">`dotnet clean` 명령은 이전 빌드의 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-110">The `dotnet clean` command cleans the output of the previous build.</span></span> <span data-ttu-id="218a3-111">이 명령은 [MSBuild 대상](/visualstudio/msbuild/msbuild-targets)으로 구현되므로 명령이 실행될 때 프로젝트가 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-111">It's implemented as an [MSBuild target](/visualstudio/msbuild/msbuild-targets), so the project is evaluated when the command is run.</span></span> <span data-ttu-id="218a3-112">빌드 중 생성된 출력만 정리됩니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-112">Only the outputs created during the build are cleaned.</span></span> <span data-ttu-id="218a3-113">중간(*obj*) 및 최종 출력(*bin*) 폴더가 모두 정리됩니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-113">Both intermediate (*obj*) and final output (*bin*) folders are cleaned.</span></span>

## <a name="arguments"></a><span data-ttu-id="218a3-114">인수</span><span class="sxs-lookup"><span data-stu-id="218a3-114">Arguments</span></span>

`PROJECT`

<span data-ttu-id="218a3-115">정리할 MSBuild 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-115">The MSBuild project to clean.</span></span> <span data-ttu-id="218a3-116">프로젝트 파일을 지정하지 않으면 MSBuild는 현재 작업 디렉터리에서 *proj*로 끝나는 파일 확장명이 있는 파일을 검색하고 해당 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-116">If a project file is not specified, MSBuild searches the current working directory for a file that has a file extension that ends in *proj* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="218a3-117">옵션</span><span class="sxs-lookup"><span data-stu-id="218a3-117">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="218a3-118">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="218a3-118">.NET Core 2.x</span></span>](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="218a3-119">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-119">Defines the build configuration.</span></span> <span data-ttu-id="218a3-120">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-120">The default value is `Debug`.</span></span> <span data-ttu-id="218a3-121">이 옵션은 빌드 시에 지정한 경우에만 정리 시에도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-121">This option is only required when cleaning if you specified it during build time.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="218a3-122">빌드 시 지정한 [프레임워크](../../standard/frameworks.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-122">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="218a3-123">프레임워크는 [프로젝트 파일](csproj.md)에 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-123">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="218a3-124">빌드 시에 프레임워크를 지정한 경우 정리할 때도 프레임워크를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-124">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

`-h|--help`

<span data-ttu-id="218a3-125">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-125">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="218a3-126">빌드 출력이 배치된 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-126">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="218a3-127">프로젝트를 빌드할 때 프레임워크를 지정한 경우 `-f|--framework <FRAMEWORK>` 스위치와 출력 디렉터리 스위치를 함께 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-127">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="218a3-128">지정된 런타임의 출력 폴더를 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-128">Cleans the output folder of the specified runtime.</span></span> <span data-ttu-id="218a3-129">[자체 포함된 배포](../deploying/index.md#self-contained-deployments-scd)가 만들어진 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-129">This is used when a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd) was created.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="218a3-130">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-130">Sets the verbosity level of the command.</span></span> <span data-ttu-id="218a3-131">허용되는 수준은 q[uiet], m[inimal], n[ormal], d[etailed] 및 diag[nostic]입니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-131">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="218a3-132">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="218a3-132">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="218a3-133">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-133">Defines the build configuration.</span></span> <span data-ttu-id="218a3-134">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-134">The default value is `Debug`.</span></span> <span data-ttu-id="218a3-135">이 옵션은 빌드 시에 지정한 경우에만 정리 시에도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-135">This option is only required when cleaning if you specified it during build time.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="218a3-136">빌드 시 지정한 [프레임워크](../../standard/frameworks.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-136">The [framework](../../standard/frameworks.md) that was specified at build time.</span></span> <span data-ttu-id="218a3-137">프레임워크는 [프로젝트 파일](csproj.md)에 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-137">The framework must be defined in the [project file](csproj.md).</span></span> <span data-ttu-id="218a3-138">빌드 시에 프레임워크를 지정한 경우 정리할 때도 프레임워크를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-138">If you specified the framework at build time, you must specify the framework when cleaning.</span></span>

`-h|--help`

<span data-ttu-id="218a3-139">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-139">Prints out a short help for the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="218a3-140">빌드 출력이 배치된 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-140">Directory in which the build outputs are placed.</span></span> <span data-ttu-id="218a3-141">프로젝트를 빌드할 때 프레임워크를 지정한 경우 `-f|--framework <FRAMEWORK>` 스위치와 출력 디렉터리 스위치를 함께 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-141">Specify the `-f|--framework <FRAMEWORK>` switch with the output directory switch if you specified the framework when the project was built.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="218a3-142">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-142">Sets the verbosity level of the command.</span></span> <span data-ttu-id="218a3-143">허용되는 수준은 q[uiet], m[inimal], n[ormal], d[etailed] 및 diag[nostic]입니다.</span><span class="sxs-lookup"><span data-stu-id="218a3-143">Allowed levels are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic].</span></span>

---

## <a name="examples"></a><span data-ttu-id="218a3-144">예제</span><span class="sxs-lookup"><span data-stu-id="218a3-144">Examples</span></span>

<span data-ttu-id="218a3-145">프로젝트의 기본 빌드 정리:</span><span class="sxs-lookup"><span data-stu-id="218a3-145">Clean a default build of the project:</span></span>

`dotnet clean`

<span data-ttu-id="218a3-146">릴리스 구성을 사용하여 빌드한 프로젝트 정리:</span><span class="sxs-lookup"><span data-stu-id="218a3-146">Clean a project built using the Release configuration:</span></span>

`dotnet clean --configuration Release`
