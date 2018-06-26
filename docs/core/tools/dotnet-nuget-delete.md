---
title: dotnet nuget delete 명령 - .NET Core CLI
description: dotnet-nuget-delete 명령은 서버에서 패키지를 삭제하거나 목록에서 제거합니다.
author: karann-msft
ms.author: mairaw
ms.date: 06/01/2018
ms.openlocfilehash: 1b58136d0bc04947f0a5baba320e5e6b3e45e2f1
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728416"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="1fe5b-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="1fe5b-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="1fe5b-104">name</span><span class="sxs-lookup"><span data-stu-id="1fe5b-104">Name</span></span>

<span data-ttu-id="1fe5b-105">`dotnet nuget delete` - 서버에서 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1fe5b-106">개요</span><span class="sxs-lookup"><span data-stu-id="1fe5b-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="1fe5b-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1fe5b-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="1fe5b-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1fe5b-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1fe5b-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1fe5b-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="1fe5b-110">설명</span><span class="sxs-lookup"><span data-stu-id="1fe5b-110">Description</span></span>

<span data-ttu-id="1fe5b-111">`dotnet nuget delete` 명령은 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-111">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="1fe5b-112">[nuget.org](https://www.nuget.org/)의 경우 작업을 통해 패키지가 목록에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-112">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="1fe5b-113">인수</span><span class="sxs-lookup"><span data-stu-id="1fe5b-113">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="1fe5b-114">삭제할 패키지의 이름/ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-114">Name/ID of the package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="1fe5b-115">삭제할 패키지의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-115">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="1fe5b-116">옵션</span><span class="sxs-lookup"><span data-stu-id="1fe5b-116">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="1fe5b-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1fe5b-117">.NET Core 2.1</span></span>](#tab/netcore21)

`--force-english-output`

 <span data-ttu-id="1fe5b-118">고정 영어 기반 문화권을 사용하여 응용 프로그램을 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-118">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="1fe5b-119">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-119">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="1fe5b-120">서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-120">The API key for the server.</span></span>

<span data-ttu-id="1fe5b-121">`--no-service-endpoint` 소스 URL에 “api/v2/package”를 추가하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-121">`--no-service-endpoint` Doesn't append "api/v2/package" to the source URL.</span></span>

`--non-interactive`

<span data-ttu-id="1fe5b-122">사용자 입력 또는 확인에 대한 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-122">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="1fe5b-123">서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-123">Specifies the server URL.</span></span> <span data-ttu-id="1fe5b-124">nuget.org에 대해 지원되는 URL에는 `http://www.nuget.org`, `http://www.nuget.org/api/v3` 및 `http://www.nuget.org/api/v2/package`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-124">Supported URLs for nuget.org include `http://www.nuget.org`, `http://www.nuget.org/api/v3`, and `http://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="1fe5b-125">개인용 피드의 경우 호스트 이름(예: `%hostname%/api/v3`)을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="1fe5b-126">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1fe5b-126">.NET Core 2.0</span></span>](#tab/netcore20)

`--force-english-output`

 <span data-ttu-id="1fe5b-127">고정 영어 기반 문화권을 사용하여 응용 프로그램을 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-127">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="1fe5b-128">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-128">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="1fe5b-129">서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-129">The API key for the server.</span></span>

`--non-interactive`

<span data-ttu-id="1fe5b-130">사용자 입력 또는 확인에 대한 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-130">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="1fe5b-131">서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-131">Specifies the server URL.</span></span> <span data-ttu-id="1fe5b-132">nuget.org에 대해 지원되는 URL에는 `http://www.nuget.org`, `http://www.nuget.org/api/v3` 및 `http://www.nuget.org/api/v2/package`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-132">Supported URLs for nuget.org include `http://www.nuget.org`, `http://www.nuget.org/api/v3`, and `http://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="1fe5b-133">개인용 피드의 경우 호스트 이름(예: `%hostname%/api/v3`)을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-133">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="1fe5b-134">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1fe5b-134">.NET Core 1.x</span></span>](#tab/netcore1x)

`--force-english-output`

 <span data-ttu-id="1fe5b-135">고정 영어 기반 문화권을 사용하여 응용 프로그램을 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-135">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="1fe5b-136">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-136">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="1fe5b-137">서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-137">The API key for the server.</span></span>

`--non-interactive`

<span data-ttu-id="1fe5b-138">사용자 입력 또는 확인에 대한 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-138">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="1fe5b-139">서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-139">Specifies the server URL.</span></span> <span data-ttu-id="1fe5b-140">nuget.org에 대해 지원되는 URL에는 `http://www.nuget.org`, `http://www.nuget.org/api/v3` 및 `http://www.nuget.org/api/v2/package`가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-140">Supported URLs for nuget.org include `http://www.nuget.org`, `http://www.nuget.org/api/v3`, and `http://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="1fe5b-141">개인용 피드의 경우 호스트 이름(예: `%hostname%/api/v3`)을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-141">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

---

## <a name="examples"></a><span data-ttu-id="1fe5b-142">예제</span><span class="sxs-lookup"><span data-stu-id="1fe5b-142">Examples</span></span>

<span data-ttu-id="1fe5b-143">`Microsoft.AspNetCore.Mvc` 패키지 버전 1.0을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-143">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0`

<span data-ttu-id="1fe5b-144">사용자에게 자격 증명 또는 기타 입력을 위한 메시지를 표시하지 않고 `Microsoft.AspNetCore.Mvc` 패키지 버전 1.0을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe5b-144">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`
