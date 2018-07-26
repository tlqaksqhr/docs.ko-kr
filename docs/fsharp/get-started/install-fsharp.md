---
title: 'F # 설치'
description: 'F #의 경우이 사용자 환경에 따라 설치 하는 방법에 알아봅니다.'
ms.date: 07/03/2018
ms.openlocfilehash: 142265a95e1d3ee1603a89f650a24c6a45709181
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37878852"
---
# <a name="install-f"></a><span data-ttu-id="f541b-103">F # 설치</span><span class="sxs-lookup"><span data-stu-id="f541b-103">Install F#</span></span> #

<span data-ttu-id="f541b-104">설치할 수 있습니다 F # 여러 가지 방법으로 사용자 환경에 따라.</span><span class="sxs-lookup"><span data-stu-id="f541b-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="f541b-105">Visual Studio를 사용 하 여 F # 설치</span><span class="sxs-lookup"><span data-stu-id="f541b-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="f541b-106">다운로드 하는 경우 [Visual Studio](https://visualstudio.microsoft.com/) 처음으로이 먼저 설치는 Visual Studio 설치 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="f541b-107">설치 관리자에서 적절 한 SKU의 Visual Studio를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="f541b-108">이미 있는 경우 설치를 클릭 **수정**합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="f541b-109">다음 워크 로드의 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="f541b-110">선택 **ASP.NET 및 웹 개발**, F # 지원,.NET Core 지원 설치할지 및 ASP.NET Core에 대 한 지원 되는 F # 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-110">Select **ASP.NET and web development**, which will install F# support, .NET Core support, and F# support for ASP.NET Core projects.</span></span>

<span data-ttu-id="f541b-111">다음으로, 클릭 **수정** 오른쪽 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="f541b-112">그러면 선택한 모든 항목이 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-112">This will install everything you have selected.</span></span> <span data-ttu-id="f541b-113">클릭 하 여 F # 언어 지원과 Visual Studio 2017을 열고 다음 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="f541b-114">F # Visual Studio를 사용 하 여 Mac 용 설치</span><span class="sxs-lookup"><span data-stu-id="f541b-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="f541b-115">F #에서 기본적으로 설치 됩니다 [Mac 용 Visual Studio](https://visualstudio.microsoft.com/vs/mac/), 어떤 구성에 관계 없이 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/), no matter what configuration you choose.</span></span>

<span data-ttu-id="f541b-116">설치가 완료 되 면 "Visual Studio 시작"을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="f541b-117">또한 macOS에서 Finder를 통해 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="f541b-118">Visual Studio Code를 사용 하 여 F # 설치</span><span class="sxs-lookup"><span data-stu-id="f541b-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="f541b-119">있어야 [설치 된 git가](https://git-scm.com/download) 되도록 경로에서 사용할 수 있습니다 Ionide 프로젝트 템플릿을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates in Ionide.</span></span> <span data-ttu-id="f541b-120">입력 하 여 제대로 설치 되었는지 확인할 수 있습니다 `git --version` 명령 프롬프트 및 키를 눌러 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="f541b-121">macOS</span><span class="sxs-lookup"><span data-stu-id="f541b-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="f541b-122">다음을 사용 하 여 Ionide [Mono](http://www.mono-project.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-122">Ionide uses [Mono](http://www.mono-project.com).</span></span> <span data-ttu-id="f541b-123">MacOS에서 Mono를 설치 하는 가장 쉬운 방법은 Homebrew 통해 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="f541b-124">터미널에 다음을 입력 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="f541b-125">또한 설치 해야 합니다 [.NET Core SDK](https://www.microsoft.com/net/download)합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-125">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="f541b-126">Linux</span><span class="sxs-lookup"><span data-stu-id="f541b-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="f541b-127">Linux에서 Ionide 또한 사용 하 여 [Mono](https://www.mono-project.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-127">On Linux, Ionide also uses [Mono](https://www.mono-project.com).</span></span> <span data-ttu-id="f541b-128">Debian 또는 Ubuntu의 경우 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="f541b-129">또한 설치 해야 합니다 [.NET Core SDK](https://www.microsoft.com/net/download)합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-129">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="f541b-130">Windows</span><span class="sxs-lookup"><span data-stu-id="f541b-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="f541b-131">Windows를 사용 하는 경우 수행 해야 합니다 [F # 지원을 사용 하 여 Visual Studio 설치](#install-f-with-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-131">If you're on Windows, you must [install Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="f541b-132">이 작성, 컴파일 및 F # 코드를 실행 하는 데 필요한 모든 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="f541b-133">또한 설치 해야 합니다 [.NET Core SDK](https://www.microsoft.com/net/download/)합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-133">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

<span data-ttu-id="f541b-134">해야 [Visual Studio Code](https://code.visualstudio.com) 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="f541b-135">그런 다음 확장 아이콘 및 "Ionide"에 대 한 검색을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="f541b-136">Visual Studio Code에서 F # 지원에 필요한 유일한 플러그 인 [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="f541b-137">그러나 설치할 수도 있습니다 [Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) 가져오려는 [가짜](https://fsharp.github.io/FAKE/) 지원 및 [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) 가져오려면 [Paket](https://fsprojects.github.io/Paket/) 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="f541b-138">모조 Paket 프로젝트를 빌드하고 각각 종속성을 관리 하기 위한 F # 커뮤니티 도구 추가 되며 합니다.</span><span class="sxs-lookup"><span data-stu-id="f541b-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>