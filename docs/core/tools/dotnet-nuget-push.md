---
title: dotnet nuget push 명령 - .NET Core CLI
description: dotnet nuget push 명령은 서버에 패키지를 푸시하고 게시합니다.
author: karann-msft
ms.author: mairaw
ms.date: 06/01/2018
ms.openlocfilehash: 8a64f9cdc11d03bed82a132265c3b4e1de290807
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728578"
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="5b184-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="5b184-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="5b184-104">name</span><span class="sxs-lookup"><span data-stu-id="5b184-104">Name</span></span>

<span data-ttu-id="5b184-105">`dotnet nuget push` - 서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5b184-106">개요</span><span class="sxs-lookup"><span data-stu-id="5b184-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="5b184-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5b184-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [--no-service-endpoint] [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="5b184-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="5b184-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5b184-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5b184-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget push [<ROOT>] [-d|--disable-buffering] [--force-english-output] [-k|--api-key] [-n|--no-symbols]
    [-s|--source] [-sk|--symbol-api-key] [-ss|--symbol-source] [-t|--timeout]
dotnet nuget push [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="5b184-110">설명</span><span class="sxs-lookup"><span data-stu-id="5b184-110">Description</span></span>

<span data-ttu-id="5b184-111">`dotnet nuget push` 명령은 서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-111">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="5b184-112">push 명령은 시스템의 NuGet 구성 파일에 있는 서버 및 자격 증명 정보 또는 구성 파일 체인을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-112">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="5b184-113">구성 파일에 대한 자세한 내용은 [NuGet 동작 구성](/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b184-113">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="5b184-114">NuGet의 기본 구성은 *%AppData%\NuGet\NuGet.config*(Windows) 또는 *$HOME/.local/share*(Linux/macOS)를 로드한 다음 드라이브의 루트에서 시작되고 현재 디렉터리에서 끝나는 *nuget.config* 또는 *.nuget\nuget.config*를 로드하여 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-114">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="5b184-115">인수</span><span class="sxs-lookup"><span data-stu-id="5b184-115">Arguments</span></span>

`ROOT`

<span data-ttu-id="5b184-116">푸시되는 패키지에 대한 파일 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-116">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="5b184-117">옵션</span><span class="sxs-lookup"><span data-stu-id="5b184-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="5b184-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5b184-118">.NET Core 2.1</span></span>](#tab/netcore21)

`-d|--disable-buffering`

<span data-ttu-id="5b184-119">메모리 사용량을 줄이려면 HTTP(S) 서버로 푸시할 때 버퍼링을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-119">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="5b184-120">고정 영어 기반 문화권을 사용하여 응용 프로그램을 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-120">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="5b184-121">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-121">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="5b184-122">서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-122">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="5b184-123">기호를 푸시하지 않습니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="5b184-123">Doesn't push symbols (even if present).</span></span>

`--no-service-endpoint`

<span data-ttu-id="5b184-124">소스 URL에 “api/v2/package”를 추가하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5b184-124">Doesn't append "api/v2/package" to the source URL.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="5b184-125">서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-125">Specifies the server URL.</span></span> <span data-ttu-id="5b184-126">이 옵션은 NuGet 구성 파일에 `DefaultPushSource` 구성 값이 설정되어 있지 않을 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-126">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="5b184-127">기호 서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-127">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="5b184-128">기호 서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-128">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="5b184-129">서버에 푸시하기 위한 제한 시간(초)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-129">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="5b184-130">기본값은 300 초(5 분)입니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-130">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="5b184-131">0(0초)을 지정하면 기본값이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-131">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="5b184-132">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="5b184-132">.NET Core 2.0</span></span>](#tab/netcore20)

`-d|--disable-buffering`

<span data-ttu-id="5b184-133">메모리 사용량을 줄이려면 HTTP(S) 서버로 푸시할 때 버퍼링을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-133">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="5b184-134">고정 영어 기반 문화권을 사용하여 응용 프로그램을 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-134">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="5b184-135">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-135">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="5b184-136">서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-136">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="5b184-137">기호를 푸시하지 않습니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="5b184-137">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="5b184-138">서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-138">Specifies the server URL.</span></span> <span data-ttu-id="5b184-139">이 옵션은 NuGet 구성 파일에 `DefaultPushSource` 구성 값이 설정되어 있지 않을 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-139">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="5b184-140">기호 서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-140">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="5b184-141">기호 서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-141">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="5b184-142">서버에 푸시하기 위한 제한 시간(초)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-142">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="5b184-143">기본값은 300 초(5 분)입니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-143">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="5b184-144">0(0초)을 지정하면 기본값이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-144">Specifying 0 (zero seconds) applies the default value.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5b184-145">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5b184-145">.NET Core 1.x</span></span>](#tab/netcore1x)

`-d|--disable-buffering`

<span data-ttu-id="5b184-146">메모리 사용량을 줄이려면 HTTP(S) 서버로 푸시할 때 버퍼링을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-146">Disables buffering when pushing to an HTTP(S) server to reduce memory usage.</span></span>

`--force-english-output`

<span data-ttu-id="5b184-147">고정 영어 기반 문화권을 사용하여 응용 프로그램을 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-147">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="5b184-148">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-148">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="5b184-149">서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-149">The API key for the server.</span></span>

`-n|--no-symbols`

<span data-ttu-id="5b184-150">기호를 푸시하지 않습니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="5b184-150">Doesn't push symbols (even if present).</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="5b184-151">서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-151">Specifies the server URL.</span></span> <span data-ttu-id="5b184-152">이 옵션은 NuGet 구성 파일에 `DefaultPushSource` 구성 값이 설정되어 있지 않을 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-152">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`-sk|--symbol-api-key <API_KEY>`

<span data-ttu-id="5b184-153">기호 서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-153">The API key for the symbol server.</span></span>

`-ss|--symbol-source <SOURCE>`

<span data-ttu-id="5b184-154">기호 서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-154">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="5b184-155">서버에 푸시하기 위한 제한 시간(초)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-155">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="5b184-156">기본값은 300 초(5 분)입니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-156">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="5b184-157">0(0초)을 지정하면 기본값이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-157">Specifying 0 (zero seconds) applies the default value.</span></span>

---

## <a name="examples"></a><span data-ttu-id="5b184-158">예제</span><span class="sxs-lookup"><span data-stu-id="5b184-158">Examples</span></span>

<span data-ttu-id="5b184-159">기본 푸시 소스에 *foo.nupkg*를 푸시하여 API 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-159">Pushes *foo.nupkg* to the default push source, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="5b184-160">사용자 지정 푸시 소스 `http://customsource`에 *foo.nupkg*를 푸시하여 API 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-160">Push *foo.nupkg* to the custom push source `http://customsource`, specifying an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

<span data-ttu-id="5b184-161">기본 푸시 소스 *foo.nupkg*를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-161">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg`

<span data-ttu-id="5b184-162">기본 기호 소스에 *foo.symbols.nupkg*를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-162">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="5b184-163">360초 시간 제한을 지정하여 기본 푸시 소스에 *foo.nupkg*를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-163">Pushes *foo.nupkg* to the default push source, specifying a 360-second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="5b184-164">기본 푸시 소스에 현재 디렉터리에 있는 모든 *.nupkg* 파일을 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-164">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`

<span data-ttu-id="5b184-165">사용자 지정 구성 파일 *./config/My.Config*를 지정하여 기본 푸시 소스에 현재 디렉터리에 있는 모든 *.nupkg* 파일을 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="5b184-165">Pushes all *.nupkg* files in the current directory to the default push source, specifying a custom config file *./config/My.Config*:</span></span>

`dotnet nuget push *.nupkg --config-file ./config/My.Config`
