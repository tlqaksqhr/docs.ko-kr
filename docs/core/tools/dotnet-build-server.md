---
title: dotnet build-server 명령 - .NET Core CLI
description: dotnet build-server는 빌드에서 시작된 서버와 상호 작용합니다.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 929b8d74aa5f3f0ad73b108be8a5bf22f86e30d6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696256"
---
# <a name="dotnet-build"></a><span data-ttu-id="b3565-103">dotnet-build</span><span class="sxs-lookup"><span data-stu-id="b3565-103">dotnet-build</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="b3565-104">name</span><span class="sxs-lookup"><span data-stu-id="b3565-104">Name</span></span>

<span data-ttu-id="b3565-105">`dotnet build-server` - 빌드에서 시작된 서버와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="b3565-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b3565-106">개요</span><span class="sxs-lookup"><span data-stu-id="b3565-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="b3565-107">명령</span><span class="sxs-lookup"><span data-stu-id="b3565-107">Commands</span></span>

`shutdown`

<span data-ttu-id="b3565-108">Dotnet에서 시작된 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b3565-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="b3565-109">기본적으로 모든 서버가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3565-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="b3565-110">옵션</span><span class="sxs-lookup"><span data-stu-id="b3565-110">Options</span></span>

`-h|--help`

<span data-ttu-id="b3565-111">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b3565-111">Prints out a short help for the command.</span></span>

`--msbuild`

<span data-ttu-id="b3565-112">MSBuild 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b3565-112">Shuts down the MSBuild build server.</span></span>

`--razor`

<span data-ttu-id="b3565-113">Razor 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b3565-113">Shuts down the Razor build server.</span></span>

`--vbcscompiler`

<span data-ttu-id="b3565-114">VB/C# 컴파일러 빌드 서버를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b3565-114">Shuts down the VB/C# compiler build server.</span></span>
