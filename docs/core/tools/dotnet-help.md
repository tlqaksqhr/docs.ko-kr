---
title: "dotnet help 명령 - .NET Core CLI"
description: "dotnet help 명령은 지정된 명령에 대한 자세한 온라인 설명서를 표시합니다."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: b33d21d7578bb4c1b33c655103f720b32aaf2203
ms.contentlocale: ko-kr
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-help-reference"></a><span data-ttu-id="f0d81-103">dotnet help reference</span><span class="sxs-lookup"><span data-stu-id="f0d81-103">dotnet help reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="f0d81-104">이름</span><span class="sxs-lookup"><span data-stu-id="f0d81-104">Name</span></span>

<span data-ttu-id="f0d81-105">`dotnet help` - 지정된 명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d81-105">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f0d81-106">개요</span><span class="sxs-lookup"><span data-stu-id="f0d81-106">Synopsis</span></span>

`dotnet list <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="f0d81-107">설명</span><span class="sxs-lookup"><span data-stu-id="f0d81-107">Description</span></span>

<span data-ttu-id="f0d81-108">`dotnet help` 명령은 docs.microsoft.com에서 지정된 명령에 대한 자세한 정보를 제공하는 참조 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f0d81-108">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="f0d81-109">인수</span><span class="sxs-lookup"><span data-stu-id="f0d81-109">Arguments</span></span>

`COMMAND_NAME`

<span data-ttu-id="f0d81-110">.NET Core CLI 명령의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0d81-110">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="f0d81-111">유효한 CLI 명령 목록은 [CLI 명령](index.md#cli-commands)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0d81-111">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="f0d81-112">옵션</span><span class="sxs-lookup"><span data-stu-id="f0d81-112">Options</span></span>

`-h|--help`

<span data-ttu-id="f0d81-113">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d81-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="f0d81-114">예제</span><span class="sxs-lookup"><span data-stu-id="f0d81-114">Examples</span></span>

<span data-ttu-id="f0d81-115">지정된 프로젝트에 대한 프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d81-115">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="f0d81-116">현재 디렉터리에 있는 프로젝트에 대한 프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d81-116">List the project references for the project in the current directory:</span></span>

`dotnet list reference`

