---
title: dotnet tool list 명령 - .NET Core CLI
description: dotnet tool list 명령은 컴퓨터에서 지정한 .NET Core Global Tool을 나열합니다.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 5f4793cd37c3a8df06eb6930ad9f381ac70d4e67
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696727"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="9aa72-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="9aa72-103">dotnet tool list</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="9aa72-104">name</span><span class="sxs-lookup"><span data-stu-id="9aa72-104">Name</span></span>

<span data-ttu-id="9aa72-105">`dotnet tool list` - 컴퓨터의 기본 디렉터리 또는 지정된 경로에 현재 설치된 모든 [.NET Core Global Tool](global-tools.md)을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa72-105">`dotnet tool list` - Lists all [.NET Core Global Tools](global-tools.md) currently installed in the default directory on your machine or in the specified path.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9aa72-106">개요</span><span class="sxs-lookup"><span data-stu-id="9aa72-106">Synopsis</span></span>

```
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list <-h|--help>
```

## <a name="description"></a><span data-ttu-id="9aa72-107">설명</span><span class="sxs-lookup"><span data-stu-id="9aa72-107">Description</span></span>

<span data-ttu-id="9aa72-108">`dotnet tool list` 명령은 컴퓨터(현재 사용자 프로필) 또는 지정된 경로에 사용자 수준에서 설치된 모든.NET Core Global Tool을 나열하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa72-108">The `dotnet tool list` command provides a way for you to list all .NET Core Global Tools installed user-wide on your machine (current user profile) or in the specified path.</span></span> <span data-ttu-id="9aa72-109">이 명령은 패키지 이름, 설치된 버전 및 Global Tool 명령을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa72-109">The command lists the package name, version installed, and the Global Tool command.</span></span> <span data-ttu-id="9aa72-110">목록 명령을 사용하려면 `--global` 옵션을 사용하여 모든 사용자 수준 도구를 표시하도록 지정하거나 `--tool-path` 옵션을 사용하여 사용자 지정 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa72-110">To use the list command, you either have to specify that you want to see all user-wide tools using the `--global` option or specify a custom path using the `--tool-path` option.</span></span>

## <a name="options"></a><span data-ttu-id="9aa72-111">옵션</span><span class="sxs-lookup"><span data-stu-id="9aa72-111">Options</span></span>

`-g|--global`

<span data-ttu-id="9aa72-112">사용자 수준 Global Tool을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa72-112">Lists user-wide Global Tools.</span></span> <span data-ttu-id="9aa72-113">`--tool-path` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa72-113">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="9aa72-114">이 옵션을 지정하지 않으면 `--tool-path` 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa72-114">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="9aa72-115">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa72-115">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="9aa72-116">Global Tool을 찾을 사용자 지정 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa72-116">Specifies a custom location where to find Global Tools.</span></span> <span data-ttu-id="9aa72-117">PATH는 절대적이거나 상대적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa72-117">PATH can be absolute or relative.</span></span> <span data-ttu-id="9aa72-118">`--global` 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9aa72-118">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="9aa72-119">이 옵션을 지정하지 않으면 `--global` 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa72-119">If you don't specify this option, you must specify the `--global` option.</span></span>

## <a name="examples"></a><span data-ttu-id="9aa72-120">예제</span><span class="sxs-lookup"><span data-stu-id="9aa72-120">Examples</span></span>

<span data-ttu-id="9aa72-121">사용자 수준 컴퓨터에 설치된 모든 Global Tool을 나열합니다(현재 사용자 프로필).</span><span class="sxs-lookup"><span data-stu-id="9aa72-121">Lists all Global Tools installed user-wide on your machine (current user profile):</span></span>

`dotnet tool list -g`

<span data-ttu-id="9aa72-122">특정 Windows 폴더의 Global Tool을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa72-122">Lists the Global Tools from a specific Windows folder:</span></span>

`dotnet tool list --tool-path c:\global-tools`

<span data-ttu-id="9aa72-123">특정 Linux/macOS 폴더의 Global Tool을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="9aa72-123">Lists the Global Tools from a specific Linux/macOS folder:</span></span>

`dotnet tool list --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="9aa72-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9aa72-124">See also</span></span>

[<span data-ttu-id="9aa72-125">.NET Core Global Tool</span><span class="sxs-lookup"><span data-stu-id="9aa72-125">.NET Core Global Tools</span></span>](global-tools.md)