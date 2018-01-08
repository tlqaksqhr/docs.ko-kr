---
title: "dotnet nuget delete 명령 - .NET Core CLI"
description: "dotnet-nuget-delete 명령은 서버에서 패키지를 삭제하거나 목록에서 제거합니다."
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 3c09556fe90a5c447b181bc1ac5b36f014399e4f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="66e9c-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="66e9c-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="66e9c-104">name</span><span class="sxs-lookup"><span data-stu-id="66e9c-104">Name</span></span>

<span data-ttu-id="66e9c-105">`dotnet nuget delete` - 서버에서 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="66e9c-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="66e9c-106">개요</span><span class="sxs-lookup"><span data-stu-id="66e9c-106">Synopsis</span></span>

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="66e9c-107">설명</span><span class="sxs-lookup"><span data-stu-id="66e9c-107">Description</span></span>

<span data-ttu-id="66e9c-108">`dotnet nuget delete` 명령은 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="66e9c-108">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="66e9c-109">[nuget.org](https://www.nuget.org/)의 경우 작업을 통해 패키지가 목록에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e9c-109">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="66e9c-110">인수</span><span class="sxs-lookup"><span data-stu-id="66e9c-110">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="66e9c-111">삭제할 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="66e9c-111">Package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="66e9c-112">삭제할 패키지의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="66e9c-112">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="66e9c-113">옵션</span><span class="sxs-lookup"><span data-stu-id="66e9c-113">Options</span></span>

`-h|--help`

<span data-ttu-id="66e9c-114">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="66e9c-114">Prints out a short help for the command.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="66e9c-115">서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66e9c-115">Specifies the server URL.</span></span> <span data-ttu-id="66e9c-116">nuget.org에 대해 지원되는 URL에는 `http://www.nuget.org`, `http://www.nuget.org/api/v3` 및 `http://www.nuget.org/api/v2/package`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e9c-116">Supported URLs for nuget.org include `http://www.nuget.org`, `http://www.nuget.org/api/v3`, and `http://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="66e9c-117">개인용 피드의 경우 호스트 이름(예: `%hostname%/api/v3`)을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="66e9c-117">For private feeds, substitute the host name (for example, `%hostname%/api/v3`).</span></span>

`--non-interactive`

<span data-ttu-id="66e9c-118">사용자 입력 또는 확인에 대한 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66e9c-118">Doesn't prompt for user input or confirmations.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="66e9c-119">서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="66e9c-119">The API key for the server.</span></span>

`--force-english-output`

<span data-ttu-id="66e9c-120">명령줄 출력이 영어로 강제로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e9c-120">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="66e9c-121">예제</span><span class="sxs-lookup"><span data-stu-id="66e9c-121">Examples</span></span>

<span data-ttu-id="66e9c-122">`Microsoft.AspNetCore.Mvc` 패키지 버전 1.0을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="66e9c-122">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

<span data-ttu-id="66e9c-123">사용자에게 자격 증명 또는 기타 입력을 위한 메시지를 표시하지 않고 `Microsoft.AspNetCore.Mvc` 패키지 버전 1.0을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="66e9c-123">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`