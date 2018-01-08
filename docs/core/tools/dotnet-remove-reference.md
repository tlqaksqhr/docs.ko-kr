---
title: "dotnet remove reference 명령 - .NET Core CLI"
description: "dotnet remove reference 명령은 프로젝트 간 참조를 제거하는 편리한 옵션을 제공합니다."
keywords: "dotnet-remove, CLI, CLI 명령, .NET Core"
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 691fd77c7605b6476adc764f20e59b51abd7d914
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="547e6-104">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="547e6-104">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="547e6-105">name</span><span class="sxs-lookup"><span data-stu-id="547e6-105">Name</span></span>

<span data-ttu-id="547e6-106">`dotnet remove reference` - 프로젝트 간 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="547e6-106">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="547e6-107">개요</span><span class="sxs-lookup"><span data-stu-id="547e6-107">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="547e6-108">설명</span><span class="sxs-lookup"><span data-stu-id="547e6-108">Description</span></span>

<span data-ttu-id="547e6-109">`dotnet remove reference` 명령은 프로젝트에서 프로젝트 참조를 제거하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="547e6-109">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="547e6-110">인수</span><span class="sxs-lookup"><span data-stu-id="547e6-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="547e6-111">대상 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="547e6-111">Target project file.</span></span> <span data-ttu-id="547e6-112">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="547e6-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="547e6-113">제거할 프로젝트 간(P2P) 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="547e6-113">Project to project (P2P references to remove.</span></span> <span data-ttu-id="547e6-114">하나 또는 여러 프로젝트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="547e6-114">You can specify one or multiple projects.</span></span> <span data-ttu-id="547e6-115">Unix/Linux 기반 터미널에서는 [와일드카드 사용 패턴](https://en.wikipedia.org/wiki/Glob_(programming))이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="547e6-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="547e6-116">옵션</span><span class="sxs-lookup"><span data-stu-id="547e6-116">Options</span></span>

`-h|--help`

<span data-ttu-id="547e6-117">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="547e6-117">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="547e6-118">특정 [프레임워크](../../standard/frameworks.md)를 대상으로 하는 경우에만 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="547e6-118">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="547e6-119">예제</span><span class="sxs-lookup"><span data-stu-id="547e6-119">Examples</span></span>

<span data-ttu-id="547e6-120">지정한 프로젝트에서 프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="547e6-120">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="547e6-121">현재 디렉터리의 프로젝트에서 여러 프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="547e6-121">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="547e6-122">Unix/Linux에서 와일드카드 사용 패턴을 사용하여 여러 프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="547e6-122">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`
