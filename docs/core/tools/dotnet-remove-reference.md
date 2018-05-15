---
title: dotnet remove reference 명령 - .NET Core CLI
description: dotnet remove reference 명령은 프로젝트 간 참조를 제거하는 편리한 옵션을 제공합니다.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 209f1ad62221e8a80efa161354a2c074d74b7c5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="f2c24-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="f2c24-103">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="f2c24-104">name</span><span class="sxs-lookup"><span data-stu-id="f2c24-104">Name</span></span>

<span data-ttu-id="f2c24-105">`dotnet remove reference` - 프로젝트 간 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f2c24-105">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f2c24-106">개요</span><span class="sxs-lookup"><span data-stu-id="f2c24-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="f2c24-107">설명</span><span class="sxs-lookup"><span data-stu-id="f2c24-107">Description</span></span>

<span data-ttu-id="f2c24-108">`dotnet remove reference` 명령은 프로젝트에서 프로젝트 참조를 제거하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f2c24-108">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="f2c24-109">인수</span><span class="sxs-lookup"><span data-stu-id="f2c24-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="f2c24-110">대상 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f2c24-110">Target project file.</span></span> <span data-ttu-id="f2c24-111">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f2c24-111">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="f2c24-112">제거할 프로젝트 간(P2P) 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="f2c24-112">Project to project (P2P references to remove.</span></span> <span data-ttu-id="f2c24-113">하나 또는 여러 프로젝트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2c24-113">You can specify one or multiple projects.</span></span> <span data-ttu-id="f2c24-114">Unix/Linux 기반 터미널에서는 [와일드카드 사용 패턴](https://en.wikipedia.org/wiki/Glob_(programming))이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2c24-114">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="f2c24-115">옵션</span><span class="sxs-lookup"><span data-stu-id="f2c24-115">Options</span></span>

`-h|--help`

<span data-ttu-id="f2c24-116">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f2c24-116">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="f2c24-117">특정 [프레임워크](../../standard/frameworks.md)를 대상으로 하는 경우에만 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f2c24-117">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="f2c24-118">예제</span><span class="sxs-lookup"><span data-stu-id="f2c24-118">Examples</span></span>

<span data-ttu-id="f2c24-119">지정한 프로젝트에서 프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f2c24-119">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="f2c24-120">현재 디렉터리의 프로젝트에서 여러 프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f2c24-120">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="f2c24-121">Unix/Linux에서 와일드카드 사용 패턴을 사용하여 여러 프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f2c24-121">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`
