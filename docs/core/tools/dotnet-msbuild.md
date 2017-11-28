---
title: "dotnet msbuild 명령 - .NET Core CLI"
description: "dotnet msbuild 명령은 MSBuild 명령줄에 대한 액세스 권한을 제공합니다."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 96e4eac528abad2b336a979a98c9be2bee5d17ee
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="1c70a-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="1c70a-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="1c70a-104">이름</span><span class="sxs-lookup"><span data-stu-id="1c70a-104">Name</span></span>

<span data-ttu-id="1c70a-105">`dotnet msbuild` - 프로젝트 및 모든 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1c70a-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1c70a-106">개요</span><span class="sxs-lookup"><span data-stu-id="1c70a-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="1c70a-107">설명</span><span class="sxs-lookup"><span data-stu-id="1c70a-107">Description</span></span>

<span data-ttu-id="1c70a-108">`dotnet msbuild` 명령을 사용하면 모든 기능을 갖춘 MSBuild에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c70a-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="1c70a-109">이 명령에는 기존 MSBuild 명령줄 클라이언트와 정확히 동일한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c70a-109">The command has the exact same capabilities as existing MSBuild command-line client.</span></span> <span data-ttu-id="1c70a-110">옵션은 모두 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1c70a-110">The options are all the same.</span></span> <span data-ttu-id="1c70a-111">[MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)를 사용하여 사용 가능한 옵션에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c70a-111">Use the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) to obtain information on the available options.</span></span> 

## <a name="examples"></a><span data-ttu-id="1c70a-112">예제</span><span class="sxs-lookup"><span data-stu-id="1c70a-112">Examples</span></span>

<span data-ttu-id="1c70a-113">프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1c70a-113">Build a project and its dependencies:</span></span>

`dotnet msbuild`

<span data-ttu-id="1c70a-114">릴리스 구성을 사용하여 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1c70a-114">Build a project and its dependencies using Release configuration:</span></span>

`dotnet msbuild /p:Configuration=Release`

<span data-ttu-id="1c70a-115">게시 대상을 실행하고 `osx.10.11-x64` RID에 대해 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c70a-115">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

<span data-ttu-id="1c70a-116">SDK를 통해 포함된 모든 대상이 있는 전체 프로젝트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c70a-116">See the whole project with all targets included by the SDK:</span></span>

`dotnet msbuild /pp`
