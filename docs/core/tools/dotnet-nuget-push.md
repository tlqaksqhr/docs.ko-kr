---
title: dotnet nuget push 명령 - .NET Core CLI
description: dotnet nuget push 명령은 서버에 패키지를 푸시하고 게시합니다.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 090b11646a81859eeadb5fe9d36b43721fc70a5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-nuget-push"></a><span data-ttu-id="29d53-103">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="29d53-103">dotnet nuget push</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="29d53-104">name</span><span class="sxs-lookup"><span data-stu-id="29d53-104">Name</span></span>

<span data-ttu-id="29d53-105">`dotnet nuget push` - 서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-105">`dotnet nuget push` - Pushes a package to the server and publishes it.</span></span>

## <a name="synopsis"></a><span data-ttu-id="29d53-106">개요</span><span class="sxs-lookup"><span data-stu-id="29d53-106">Synopsis</span></span>

`dotnet nuget push [<ROOT>] [-s|--source] [-ss|--symbol-source] [-t|--timeout] [-k|--api-key] [-sk|--symbol-api-key] [-d|--disable-buffering] [-n|--no-symbols] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="29d53-107">설명</span><span class="sxs-lookup"><span data-stu-id="29d53-107">Description</span></span>

<span data-ttu-id="29d53-108">`dotnet nuget push` 명령은 서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-108">The `dotnet nuget push` command pushes a package to the server and publishes it.</span></span> <span data-ttu-id="29d53-109">push 명령은 시스템의 NuGet 구성 파일에 있는 서버 및 자격 증명 정보 또는 구성 파일 체인을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-109">The push command uses server and credential details found in the system's NuGet config file or chain of config files.</span></span> <span data-ttu-id="29d53-110">구성 파일에 대한 자세한 내용은 [NuGet 동작 구성](/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29d53-110">For more information on config files, see [Configuring NuGet Behavior](/nuget/consume-packages/configuring-nuget-behavior).</span></span> <span data-ttu-id="29d53-111">NuGet의 기본 구성은 *%AppData%\NuGet\NuGet.config*(Windows) 또는 *$HOME/.local/share*(Linux/macOS)를 로드한 다음 드라이브의 루트에서 시작되고 현재 디렉터리에서 끝나는 *nuget.config* 또는 *.nuget\nuget.config*를 로드하여 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-111">NuGet's default configuration is obtained by loading *%AppData%\NuGet\NuGet.config* (Windows) or *$HOME/.local/share* (Linux/macOS), then loading any *nuget.config* or *.nuget\nuget.config* starting from the root of drive and ending in the current directory.</span></span>

## <a name="arguments"></a><span data-ttu-id="29d53-112">인수</span><span class="sxs-lookup"><span data-stu-id="29d53-112">Arguments</span></span>

`ROOT`

<span data-ttu-id="29d53-113">푸시되는 패키지에 대한 파일 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-113">Specifies the file path to the package to be pushed.</span></span>

## <a name="options"></a><span data-ttu-id="29d53-114">옵션</span><span class="sxs-lookup"><span data-stu-id="29d53-114">Options</span></span>

`-h|--help`

<span data-ttu-id="29d53-115">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-115">Prints out a short help for the command.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="29d53-116">서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-116">Specifies the server URL.</span></span> <span data-ttu-id="29d53-117">이 옵션은 NuGet 구성 파일에 `DefaultPushSource` 구성 값이 설정되어 있지 않을 때 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-117">This option is required unless `DefaultPushSource` config value is set in the NuGet config file.</span></span>

`--symbol-source <SOURCE>`

<span data-ttu-id="29d53-118">기호 서버 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-118">Specifies the symbol server URL.</span></span>

`-t|--timeout <TIMEOUT>`

<span data-ttu-id="29d53-119">서버에 푸시하기 위한 제한 시간(초)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-119">Specifies the timeout for pushing to a server in seconds.</span></span> <span data-ttu-id="29d53-120">기본값은 300 초(5 분)입니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-120">Defaults to 300 seconds (5 minutes).</span></span> <span data-ttu-id="29d53-121">0(0초)을 지정하면 기본값이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-121">Specifying 0 (zero seconds) applies the default value.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="29d53-122">서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-122">The API key for the server.</span></span>

`--symbol-api-key <API_KEY>`

<span data-ttu-id="29d53-123">기호 서버에 대한 API 키입니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-123">The API key for the symbol server.</span></span>

`-d|--disable-buffering`

<span data-ttu-id="29d53-124">메모리 사용량을 줄이려면 HTTP(S) 서버로 푸시할 때 버퍼링을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-124">Disables buffering when pushing to an HTTP(S) server to decrease memory usage.</span></span>

`-n|--no-symbols`

<span data-ttu-id="29d53-125">기호를 푸시하지 않습니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="29d53-125">Doesn't push symbols (even if present).</span></span>

`--force-english-output`

<span data-ttu-id="29d53-126">기록되는 모든 출력은 영어로 강제로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-126">Forces all logged output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="29d53-127">예제</span><span class="sxs-lookup"><span data-stu-id="29d53-127">Examples</span></span>

<span data-ttu-id="29d53-128">기본 푸시 소스에 *foo.nupkg*를 푸시하여 API 키를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-128">Pushes *foo.nupkg* to the default push source, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

<span data-ttu-id="29d53-129">사용자 지정 푸시 소스 `http://customsource`에 *foo.nupkg*를 푸시하여 API 키를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-129">Push *foo.nupkg* to the custom push source `http://customsource`, providing an API key:</span></span>

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/`

<span data-ttu-id="29d53-130">기본 푸시 소스 *foo.nupkg*를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-130">Pushes *foo.nupkg* to the default push source:</span></span>

`dotnet nuget push foo.nupkg`

<span data-ttu-id="29d53-131">기본 기호 소스에 *foo.symbols.nupkg*를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-131">Pushes *foo.symbols.nupkg* to the default symbols source:</span></span>

`dotnet nuget push foo.symbols.nupkg`

<span data-ttu-id="29d53-132">360초 제한 시간을 지정하여 기본 푸시 소스에 *foo.nupkg*를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-132">Pushes *foo.nupkg* to the default push source, specifying a 360 second timeout:</span></span>

`dotnet nuget push foo.nupkg --timeout 360`

<span data-ttu-id="29d53-133">기본 푸시 소스에 현재 디렉터리에 있는 모든 *.nupkg* 파일을 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-133">Pushes all *.nupkg* files in the current directory to the default push source:</span></span>

`dotnet nuget push *.nupkg`

<span data-ttu-id="29d53-134">사용자 지정 구성 파일 *./config/My.Config*를 지정하여 기본 푸시 소스에 현재 디렉터리에 있는 모든 *.nupkg* 파일을 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="29d53-134">Pushes all *.nupkg* files in the current directory to the default push source, specifying a custom config file *./config/My.Config*:</span></span>

`dotnet nuget push *.nupkg --config-file ./config/My.Config`
