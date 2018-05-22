---
title: dotnet sln 명령 - .NET Core CLI
description: dotnet-sln 명령은 솔루션 파일의 프로젝트를 추가, 제거 및 나열하는 간편한 옵션을 제공합니다.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 845e666b9d8a8b206c7e1978a7dde9f33ffb8a32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-sln"></a><span data-ttu-id="23cc2-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="23cc2-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="23cc2-104">name</span><span class="sxs-lookup"><span data-stu-id="23cc2-104">Name</span></span>

<span data-ttu-id="23cc2-105">`dotnet sln` - .NET Core 솔루션 파일을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-105">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="23cc2-106">개요</span><span class="sxs-lookup"><span data-stu-id="23cc2-106">Synopsis</span></span>

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="23cc2-107">설명</span><span class="sxs-lookup"><span data-stu-id="23cc2-107">Description</span></span>

<span data-ttu-id="23cc2-108">`dotnet sln` 명령은 솔루션 파일의 프로젝트를 추가, 제거 및 나열하는 간편한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

## <a name="commands"></a><span data-ttu-id="23cc2-109">명령</span><span class="sxs-lookup"><span data-stu-id="23cc2-109">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="23cc2-110">솔루션 파일에 하나 이상의 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-110">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="23cc2-111">Unix/Linux 기반 터미널에서는 [와일드카드 사용 패턴](https://en.wikipedia.org/wiki/Glob_(programming))이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-111">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="23cc2-112">솔루션 파일에서 하나 이상의 프로젝트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-112">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="23cc2-113">Unix/Linux 기반 터미널에서는 [와일드카드 사용 패턴](https://en.wikipedia.org/wiki/Glob_(programming))이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="23cc2-114">솔루션 파일의 모든 프로젝트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-114">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="23cc2-115">인수</span><span class="sxs-lookup"><span data-stu-id="23cc2-115">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="23cc2-116">사용할 솔루션 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-116">Solution file to use.</span></span> <span data-ttu-id="23cc2-117">지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-117">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="23cc2-118">디렉터리에 여러 솔루션 파일이 있으면 하나를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-118">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="23cc2-119">옵션</span><span class="sxs-lookup"><span data-stu-id="23cc2-119">Options</span></span>

`-h|--help`

<span data-ttu-id="23cc2-120">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-120">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="23cc2-121">예제</span><span class="sxs-lookup"><span data-stu-id="23cc2-121">Examples</span></span>

<span data-ttu-id="23cc2-122">솔루션에 C# 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-122">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="23cc2-123">솔루션에서 C# 프로젝트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-123">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="23cc2-124">솔루션에 여러 C# 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-124">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="23cc2-125">솔루션에서 여러 C# 프로젝트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-125">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="23cc2-126">와일드카드 사용 패턴을 사용하여 솔루션에 여러 C# 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-126">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="23cc2-127">와일드카드 사용 패턴을 사용하여 솔루션에서 여러 C# 프로젝트를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="23cc2-127">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`
