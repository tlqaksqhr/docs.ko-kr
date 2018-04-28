---
title: 'Visual Studio Code에서 F #으로 시작.'
description: 'Visual Studio Code 및 Ionide 플러그 인 suite F #을 사용 하는 방법에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 02/28/2018
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 43fed76a57bd7749a7f22a2039ad625e3d26d132
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="497e6-103">Visual Studio Code에서 F #으로 시작.</span><span class="sxs-lookup"><span data-stu-id="497e6-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="497e6-104">작성할 수 있습니다 F # [Visual Studio Code](https://code.visualstudio.com) 와 [Ionide 플러그 인](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)는 뛰어난 플랫폼 간 사용할 수 있는 경량 IDE (Integrade 개발 Enivronment) 경험을 얻을 수 IntelliSense 및 기본 코드 리팩터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp), to get a great cross-platform, lightweight IDE (Integrade Development Enivronment) experience with IntelliSense and basic code refactorings.</span></span>  <span data-ttu-id="497e6-105">방문 [Ionide.io](http://ionide.io) 플러그 인 집합에 대 한 자세한 내용을 보려면 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin suite.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="497e6-106">전제 조건</span><span class="sxs-lookup"><span data-stu-id="497e6-106">Prerequisites</span></span>

<span data-ttu-id="497e6-107">있어야 [git 설치](https://git-scm.com/download) 및 사용할 수 있도록 경로에 Ionide 프로젝트 템플릿을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-107">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates in Ionide.</span></span>  <span data-ttu-id="497e6-108">입력 하 여 올바르게 설치 되었는지 확인할 수 `git --version` 고 키를 눌러 명령 프롬프트에서 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-108">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="497e6-109">macOS</span><span class="sxs-lookup"><span data-stu-id="497e6-109">macOS</span></span>](#tab/macos)

<span data-ttu-id="497e6-110">사용 하 여 Ionide [모노](http://www.mono-project.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-110">Ionide uses [Mono](http://www.mono-project.com).</span></span>  <span data-ttu-id="497e6-111">Homebrew를 통해 모노 macOS에 설치 하는 가장 쉬운 방법은 됩니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-111">The easiest way to install Mono on macOS is via Homebrew.</span></span>  <span data-ttu-id="497e6-112">단순히 터미널에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-112">Simply type the following into your terminal:</span></span>

```
brew install mono
```

<span data-ttu-id="497e6-113">또한 설치 해야는 [.NET Core SDK](https://www.microsoft.com/net/download)합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-113">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="497e6-114">Linux</span><span class="sxs-lookup"><span data-stu-id="497e6-114">Linux</span></span>](#tab/linux)

<span data-ttu-id="497e6-115">Linux에서 Ionide 또한 사용 하 여 [모노](https://www.mono-project.com)합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-115">On Linux, Ionide also uses [Mono](https://www.mono-project.com).</span></span> <span data-ttu-id="497e6-116">Debian 또는 Ubuntu 인 경우 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-116">If you're on Debian or Ubuntu, you can use the following:</span></span>

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="497e6-117">또한 설치 해야는 [.NET Core SDK](https://www.microsoft.com/net/download)합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-117">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="497e6-118">Windows</span><span class="sxs-lookup"><span data-stu-id="497e6-118">Windows</span></span>](#tab/windows)

<span data-ttu-id="497e6-119">Windows를 사용 하는 경우 해야 [F #를 지 원하는 Visual Studio 설치](get-started-visual-studio.md#installing-f)합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-119">If you're on Windows, you must [install Visual Studio with F# support](get-started-visual-studio.md#installing-f).</span></span> <span data-ttu-id="497e6-120">작성, 컴파일 및 F # 코드를 실행 하는 데 필요한 모든 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-120">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="497e6-121">또한 설치 해야는 [.NET Core SDK](https://www.microsoft.com/net/download/)합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-121">You must also install the [.NET Core SDK](https://www.microsoft.com/net/download/).</span></span>

---

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a><span data-ttu-id="497e6-122">Visual Studio Code 및 Ionide 플러그 인 설치</span><span class="sxs-lookup"><span data-stu-id="497e6-122">Installing Visual Studio Code and the Ionide plugin</span></span>

<span data-ttu-id="497e6-123">Visual Studio Code에서 설치할 수는 [code.visualstudio.com](https://code.visualstudio.com) 웹 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-123">You can install Visual Studio Code from the [code.visualstudio.com](https://code.visualstudio.com) website.</span></span> <span data-ttu-id="497e6-124">그런 다음 두 가지 방법으로 Ionide 플러그 인을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-124">After that, there are two ways to find the Ionide plugin:</span></span>

1. <span data-ttu-id="497e6-125">명령 팔레트 (Ctrl + Shift + P windows에서는 ⌘ + macOS, Ctrl + Shift + P linux에서 Shift + P)를 사용 하 하 고 다음을 입력.</span><span class="sxs-lookup"><span data-stu-id="497e6-125">Use the Command Palette (Ctrl+Shift+P on Windows, ⌘+Shift+P on macOS, Ctrl+Shift+P on Linux) and type the following:</span></span>

    ```
    >ext install Ionide
    ```

2. <span data-ttu-id="497e6-126">확장명 아이콘 및 "Ionide"에 대 한 검색을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-126">Click the Extensions icon and search for "Ionide":</span></span>

    ![](media/getting-started-vscode/vscode-ext.png)

<span data-ttu-id="497e6-127">Visual Studio 코드에서 지원 되는 F #에 필요한 유일한 플러그 인 [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-127">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="497e6-128">그러나 설치할 수도 있습니다 [Ionide 모조](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) 을 받을 [가짜](https://fsharp.github.io/FAKE/) 지원 및 [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) 가져오려는 [Paket](https://fsprojects.github.io/Paket/) 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-128">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) and to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="497e6-129">가짜 및 Paket는 프로젝트를 빌드하고 각각 종속성을 관리 하기 위한 추가 F # 커뮤니티 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-129">FAKE and Paket are additonal F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="497e6-130">Ionide를 사용 하 여 첫 번째 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="497e6-130">Creating your first project with Ionide</span></span>

<span data-ttu-id="497e6-131">새 F # 프로젝트를 만들려면 (수 이름을 바꾸는) 인 새 폴더에 Visual Studio Code를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-131">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

![](media/getting-started-vscode/vscode-open-dir.png)

<span data-ttu-id="497e6-132">그런 다음 명령 팔레트 (Ctrl + Shift + P windows에서는 ⌘ + macOS, Ctrl + Shift + P linux에서 Shift + P)를 열고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-132">Next, open the Command Palette (Ctrl+Shift+P on Windows, ⌘+Shift+P on macOS, Ctrl+Shift+P on Linux) and type the following:</span></span>

```
>f#: New Project
```

<span data-ttu-id="497e6-133">연결 된 값이 고 [FORGE](https://github.com/fsharp-editing/Forge) 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="497e6-133">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>  <span data-ttu-id="497e6-134">다음과 같이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-134">You should see something like this:</span></span>

![](media/getting-started-vscode/vscode-new-proj.png)

> [!NOTE]
<span data-ttu-id="497e6-135">위의 표시 되지 않으면 명령 팔레트에서 다음 명령을 실행 하 여 서식 파일을 새로 고쳐 보세요: `>F#: Refresh Project Templates`합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-135">If you don't see the above, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="497e6-136">F #:: "새 프로젝트"를 클릭 하 여 선택 **Enter**는이 단계로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-136">Select "F#: New Project" by hitting **Enter**, which will take you to this step:</span></span>

![](media/getting-started-vscode/vscode-proj-type.png)

<span data-ttu-id="497e6-137">이렇게 하면 특정 유형의 프로젝트에 대 한 템플릿을 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-137">This will select a template for a specific type of project.</span></span>  <span data-ttu-id="497e6-138">없는 다음와 같은 몇 가지 옵션이 여기에서 [FsLab](https://fslab.org) 데이터 과학을 위한 서식 파일 또는 [Suave](https://suave.io) 웹 프로그래밍을 위한 서식 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-138">There are quite a few options here, such as an [FsLab](https://fslab.org) template for Data Science or [Suave](https://suave.io) template for Web Programming.</span></span>  <span data-ttu-id="497e6-139">이 문서에서는 `classlib` 템플릿을 하므로 하는 강조 표시 하 고 적중 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-139">This article uses the `classlib` template, so highlight that and hit **Enter**.</span></span>  <span data-ttu-id="497e6-140">다음 단계는 다음과 같은 도달 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-140">You will then reach the following step:</span></span>

![](media/getting-started-vscode/vscode-new-dir.png)

<span data-ttu-id="497e6-141">이렇게 하면 원하는 경우 다른 디렉터리에 있는 프로젝트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-141">This lets you create the project in a different directory, if you like.</span></span>  <span data-ttu-id="497e6-142">비워 둡니다 지금은.</span><span class="sxs-lookup"><span data-stu-id="497e6-142">Leave it blank for now.</span></span>  <span data-ttu-id="497e6-143">프로젝트는 현재 디렉터리에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-143">It will create the project in the current directory.</span></span>  <span data-ttu-id="497e6-144">누른 **Enter**, 다음 단계에 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-144">Once you press **Enter**, you will reach the following step:</span></span>

![](media/getting-started-vscode/vscode-proj-name.png)

<span data-ttu-id="497e6-145">이렇게 하면 프로젝트 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-145">This lets you name your project.</span></span>  <span data-ttu-id="497e6-146">사용 하 여 F # [파스칼식 대 / 소문자로](http://c2.com/cgi/wiki?PascalCase) 프로젝트 이름에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-146">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span>  <span data-ttu-id="497e6-147">이 문서에서는 `ClassLibraryDemo` 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-147">This article uses `ClassLibraryDemo` as the name.</span></span>  <span data-ttu-id="497e6-148">프로젝트에 사용할 이름을 입력 하 여, 적중 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-148">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="497e6-149">이전 단계 단계를 수행 하는 경우 Visual Studio 코드 작업 영역 왼쪽에을 다음과 같은 받습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-149">If you followed the previous step steps, you should get the Visual Studio Code Workspace on the left-hand side to look something like this:</span></span>

![](media/getting-started-vscode/vscode-new-proj-explorer.png)

<span data-ttu-id="497e6-150">이 서식 파일에서는 몇 가지 유용한 있습니다 오류가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-150">This template generates a few things you'll find useful:</span></span>

1. <span data-ttu-id="497e6-151">F # 프로젝트 자체를 아래에서 `ClassLibraryDemo` 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-151">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="497e6-152">통해 패키지를 추가 하기 위한 올바른 디렉터리 구조 [ `Paket` ](https://fsprojects.github.io/Paket/)합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-152">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="497e6-153">플랫폼 간 빌드 스크립트와 [ `FAKE` ](https://fsharp.github.io/FAKE/)합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-153">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="497e6-154">`paket.exe` 있습니다에 대 한 종속성을 해결 하 고 패키지를 가져올 수 있는 실행 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-154">The `paket.exe` executable which can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="497e6-155">A `.gitignore` Git 기반 소스 제어에이 프로젝트를 추가 하려는 경우 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-155">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="497e6-156">일부 코드 작성</span><span class="sxs-lookup"><span data-stu-id="497e6-156">Writing some code</span></span>

<span data-ttu-id="497e6-157">열기는 *ClassLibraryDemo* 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-157">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="497e6-158">다음 파일이 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-158">You should see the following files:</span></span>

1. <span data-ttu-id="497e6-159">`ClassLibraryDemo.fs`를 정의 하는 클래스와 F # 구현 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-159">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="497e6-160">`CassLibraryDemo.fsproj`를이 프로젝트를 빌드하는 데는 F # 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-160">`CassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="497e6-161">`Script.fsx`는 F # 스크립트 파일이 소스 파일을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-161">`Script.fsx`, an F# script file which loads the source file.</span></span>
4. <span data-ttu-id="497e6-162">`paket.references`Paket 파일을 프로젝트 종속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-162">`paket.references`, a Paket file which specifies the project dependencies.</span></span>

<span data-ttu-id="497e6-163">열기 `Script.fsx`, 그 후에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-163">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="497e6-164">이 함수는 형태의 단어 변환 [Pig 라틴](https://en.wikipedia.org/wiki/Pig_Latin)합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-164">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span>  <span data-ttu-id="497e6-165">다음 단계에서는 F # 대화형 (FSI)를 사용 하 여 평가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-165">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="497e6-166">전체 함수 (11 줄 이어야 함)를 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-166">Highlight the entire function (it should be 11 lines long).</span></span>  <span data-ttu-id="497e6-167">강조 표시 되 면 보유는 **Alt** 키 및 적중 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-167">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span>  <span data-ttu-id="497e6-168">아래 팝업 창을 보면 하 고 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-168">You'll notice a window pop up below, and it should show something like this:</span></span>

![](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="497e6-169">이 세 가지 했습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-169">This did three things:</span></span>

1. <span data-ttu-id="497e6-170">FSI 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-170">It started the FSI process.</span></span>
2. <span data-ttu-id="497e6-171">FSI 프로세스를 통해 강조 표시 된 코드를 전송.</span><span class="sxs-lookup"><span data-stu-id="497e6-171">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="497e6-172">FSI 프로세스를 통해 전송 된 코드를 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-172">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="497e6-173">통해 보낸 되었으므로 [함수](../language-reference/functions/index.md), 이제 FSI 해당 함수를 호출할 수 있습니다!</span><span class="sxs-lookup"><span data-stu-id="497e6-173">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span>  <span data-ttu-id="497e6-174">대화형 창에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-174">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="497e6-175">다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-175">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="497e6-176">이제 첫 번째 문자로 함께 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-176">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="497e6-177">다음을 입력하세요.</span><span class="sxs-lookup"><span data-stu-id="497e6-177">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="497e6-178">다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-178">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="497e6-179">예상 대로 작동 하는 함수 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-179">The function appears to be working as expected.</span></span>  <span data-ttu-id="497e6-180">축 하 합니다, 방금 Visual Studio 코드에서 첫 번째 F # 함수를 작성 하 고 FSI를 사용 하 여 확인!</span><span class="sxs-lookup"><span data-stu-id="497e6-180">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

>[!NOTE]
<span data-ttu-id="497e6-181">FSI에서 줄 종결 되는지 알 수 있습니다, 처럼 `;;`합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-181">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span>  <span data-ttu-id="497e6-182">즉, FSI를 사용 하면 여러 줄을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-182">This is because FSI allows you to enter multiple lines.</span></span>  <span data-ttu-id="497e6-183">`;;` 끝 FSI 코드가 완료 되었을 때를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-183">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="497e6-184">코드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-184">Explaining the code</span></span>

<span data-ttu-id="497e6-185">코드 실제로 수행 하는 방법에 대 한 잘 모르는 경우 다음 단계별 마법사은입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-185">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="497e6-186">볼 수 있듯이 `toPigLatin` 단어 입력으로 사용 되 고 단어의 Pig 라틴 문자 표현으로 변환 하는 함수가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-186">As you can see, `toPigLatin` is a function which takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span>  <span data-ttu-id="497e6-187">이 규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-187">The rules for this are as follows:</span></span>

<span data-ttu-id="497e6-188">단어의 첫 번째 문자는 함께 시작 되 면 ""이 얼 간 단어의 끝에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-188">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span>  <span data-ttu-id="497e6-189">함께 시작 되지 않는다면 해당 첫 번째 문자는 단어의 끝으로 이동 합니다. 및 "집니다"를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-189">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="497e6-190">FSI에서 다음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-190">You may have noticed the following in FSI:</span></span>

```
val toPigLatin : word:string -> string
```

<span data-ttu-id="497e6-191">이 없다는 `toPigLatin` 에서 사용 하는 함수는 `string` 입력으로 (호출 `word`)를 반환 하는 값 및 `string`합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-191">This states that `toPigLatin` is a function which takes in a `string` as input (called `word`), and returns another `string`.</span></span>  <span data-ttu-id="497e6-192">로 알려져는 [함수의 형식 서명이](https://fsharpforfunandprofit.com/posts/function-signatures/), F # 코드를 이해 하는 F #의 기본적인 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-192">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span>  <span data-ttu-id="497e6-193">Visual Studio 코드의 함수 위로 가져가면에 다음이 표시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-193">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="497e6-194">함수 본문에서 두 가지 부분을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-194">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="497e6-195">호출 하는 내부 함수 `isVowel`, 하는 경우 지정 된 문자를 결정 합니다 (`c`)를 통해 제공 된 패턴 중 하 나와 일치 하는 경우를 확인 하 여이 모음인 [패턴 일치](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="497e6-195">An inner function, called `isVowel`, which determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="497e6-196">[ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) 인지에 따라 첫 번째 문자에 모음이 고 입력된 된 문자를 벗어나는 반환 값을 생성 하는 검사 첫 번째 문자 식에 모음이 되었거나:</span><span class="sxs-lookup"><span data-stu-id="497e6-196">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression which checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="497e6-197">흐름 `toPigLatin` 있으므로:</span><span class="sxs-lookup"><span data-stu-id="497e6-197">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="497e6-198">입력된 단어의 첫 번째 문자에 모음이 있는지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="497e6-198">Check if the first character of the input word is a vowel.</span></span>  <span data-ttu-id="497e6-199">인 경우 단어의 끝에 ""이 얼 간을 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-199">If it is, attach "yay" to the end of the word.</span></span>  <span data-ttu-id="497e6-200">그렇지 않으면 첫 번째 문자가 단어의 끝으로 이동 및 "집니다"를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-200">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="497e6-201">이 대 한 확인 해야 할 사항이 하나는:는 많은 다른 언어와 달리 하셨습니까 함수에서 반환할 수 없는 명시적 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-201">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span>  <span data-ttu-id="497e6-202">F #은 식 기반 이며 함수의 본문에서 반환 값 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-202">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span>  <span data-ttu-id="497e6-203">때문에 `if..then..else` 은 자체는 식의 본문은 `then` 블록 또는 본문에는 `else` 블록 입력된 값에 따라 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-203">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="497e6-204">구현 파일에 스크립트 코드를 이동</span><span class="sxs-lookup"><span data-stu-id="497e6-204">Moving your script code into the implementation file</span></span>

<span data-ttu-id="497e6-205">이 문서의 이전 섹션에는 F # 코드를 작성 합니다. 일반적인 첫 번째 단계는 설명: FSI를 대화형으로 실행 하는 초기 함수를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-205">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span>  <span data-ttu-id="497e6-206">이 복제 기반 개발, 여기서 REPL은 "읽기 평가 인쇄 루프" 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-206">This is known as REPL-driven development, where REPL stands for "Read-Evaluate-Print Loop".</span></span>  <span data-ttu-id="497e6-207">작업 결과가 있는 될 때까지 기능을 시험해 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-207">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="497e6-208">복제 기반 개발의 다음 단계는 F # 구현 파일에 작업 코드를 옮기는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-208">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span>  <span data-ttu-id="497e6-209">그런 다음 컴파일될 수 F # 컴파일러에 의해 실행 될 수 있는 어셈블리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-209">It can then be compiled by the F# compiler into an assembly which can be executed.</span></span>

<span data-ttu-id="497e6-210">를 시작 하려면 열기 `ClassLibraryDemo.fs`합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-210">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="497e6-211">일부 코드는 이미에 있는 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-211">You'll notice that some code is already in there.</span></span>  <span data-ttu-id="497e6-212">계속 진행 하 고 클래스 정의 삭제 하지만을 남겨 두어야는 [ `namespace` ](../language-reference/namespaces.md) 위쪽에 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-212">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="497e6-213">다음으로 새 만듭니다 [ `module` ](../language-reference/modules.md) 호출 `PigLatin` 복사는 `toPigLatin` 따라서 함수에:</span><span class="sxs-lookup"><span data-stu-id="497e6-213">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="497e6-214">C# 또는 Visual Basic 프로젝트에서 코드를 호출 하려는 경우 일반적인 접근 방식 및 F # 코드에서는 함수를 구성할 수는 여러 가지 방법 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-214">This is one of the many ways you can organize functions in F# code, and a common approach if you also want to call your code from C# or Visual Basic projects.</span></span>

<span data-ttu-id="497e6-215">을 열고는 `Script.fsx` 다시 파일을 전체 삭제 `toPigLatin` 작동할 수 있지만 파일에 다음 두 줄을 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-215">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="497e6-216">첫 번째 줄에 로드 하는 데 스크립팅을 FSI 필요한 `ClassLibraryDemo.fs`합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-216">The first line is needed for FSI scripting to load `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="497e6-217">두 번째 줄은 편의 위해: 생략 하는 것은 선택 사항 이지만 입력할 필요가 `open ClassLibraryDemo` FSI 창 상태로 전환 하려는 경우에 `ToPigLatin` 범위로 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-217">The second line is a convenience: omitting it is optional, but you will need to type `open ClassLibraryDemo` in an FSI window if you wish to bring the `ToPigLatin` module into scope.</span></span>

<span data-ttu-id="497e6-218">그런 다음 FSI 창에서 사용 하 여 함수 호출의 `PigLatin` 앞에서 정의한 모듈:</span><span class="sxs-lookup"><span data-stu-id="497e6-218">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="497e6-219">성공</span><span class="sxs-lookup"><span data-stu-id="497e6-219">Success!</span></span>  <span data-ttu-id="497e6-220">이전에 동일한 결과를 가져오지만 이제 F # 구현 파일에서 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-220">You get the same results as before, but now loaded from an F# implementation file.</span></span>  <span data-ttu-id="497e6-221">주요 차이점은 F # 소스 파일 FSI에서 뿐 아니라 어디서 나 실행할 수 있는 어셈블리로 컴파일되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-221">The major difference here is that F# source files are compiled into assemblies which can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="497e6-222">요약</span><span class="sxs-lookup"><span data-stu-id="497e6-222">Summary</span></span>

<span data-ttu-id="497e6-223">이 문서에서는 지금까지 학습:</span><span class="sxs-lookup"><span data-stu-id="497e6-223">In this article, you've learned:</span></span>

1. <span data-ttu-id="497e6-224">Ionide와 Visual Studio 코드를 설정 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="497e6-224">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="497e6-225">Ionide와 첫 번째 F # 프로젝트를 만드는 방법.</span><span class="sxs-lookup"><span data-stu-id="497e6-225">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="497e6-226">Ionide에서 첫 번째 F # 함수를 작성 한 후 FSI에서 실행 F # 스크립트를 사용 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-226">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="497e6-227">F # 소스를 스크립트 코드를 마이그레이션하고 FSI에서 해당 코드를 호출 하는 방법.</span><span class="sxs-lookup"><span data-stu-id="497e6-227">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="497e6-228">코드를 작성할 훨씬 더 많은 F # Visual Studio Code 및 Ionide 사용 하 여 이제 정답입니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-228">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="497e6-229">문제 해결</span><span class="sxs-lookup"><span data-stu-id="497e6-229">Troubleshooting</span></span>

<span data-ttu-id="497e6-230">여기 몇 가지 방법으로 충돌할 수 있는 특정 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-230">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="497e6-231">코드 편집 Ionide의는 기능을 가져오려면 F # 파일 Visual Studio Code 작업 영역에서 열려 있는 폴더 내에서 디스크에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-231">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="497e6-232">시스템에 변경 작업을 수행 하거나 Visual Studio 코드 열려 Ionide 필수 구성 요소를 설치, Visual Studio 코드를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-232">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="497e6-233">F # 컴파일러 및 F # interactive 정식 경로 사용 하지 않고 명령줄에서 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-233">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span>  <span data-ttu-id="497e6-234">입력 하 여 그렇게 할 수 `fsc` F # 컴파일러에 대 한 명령줄의 및 `fsi` 또는 `fsharpi` 에 대 한 Visual F # 도구 창 및 linux/Mac에서 모노에 각각.</span><span class="sxs-lookup"><span data-stu-id="497e6-234">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="497e6-235">프로젝트 디렉터리에 잘못 된 문자가 있으면 Ionide 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-235">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="497e6-236">이 경우 프로젝트 디렉터리를 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-236">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="497e6-237">작업 Ionide 명령 중 없음, 확인 프로그램 [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) 경우 재정의 중인에 실수로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-237">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="497e6-238">컴퓨터에 Ionide 나뉘어집니다 위에 해당는 문제를 해결 하는 경우를 제거해 보세요는 `ionide-fsharp` 컴퓨터에 디렉터리 플러그 인 도구 모음을 다시 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-238">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="497e6-239">Ionide는 오픈 소스 프로젝트 작성 및 F # 커뮤니티의 회원이 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-239">Ionide is an open source project built and maintained by members of the F# community.</span></span>  <span data-ttu-id="497e6-240">문제를 보고 하 고에 참가할 수 정도 하십시오는 [Ionide VSCode: FSharp GitHub 리포지토리](https://github.com/ionide/ionide-vscode-fsharp)합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-240">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="497e6-241">보고서에 문제가 있는 경우 따르십시오 [문제를 보고할 때 사용 하는 로그를 가져오기 위한 지침은](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting)합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-241">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="497e6-242">Ionide 개발자 및 F #에서 커뮤니티에서 도움을 요청할 수도 있습니다는 [Ionide Gitter 채널](https://gitter.im/ionide/ionide-project)합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-242">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="497e6-243">다음 단계</span><span class="sxs-lookup"><span data-stu-id="497e6-243">Next steps</span></span>

<span data-ttu-id="497e6-244">F # 및 언어의 기능에 대 한 자세한 내용은 체크 아웃 [둘러보기의 F #](../tour.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="497e6-244">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="497e6-245">참고자료</span><span class="sxs-lookup"><span data-stu-id="497e6-245">See also</span></span>

[<span data-ttu-id="497e6-246">F# 둘러보기</span><span class="sxs-lookup"><span data-stu-id="497e6-246">Tour of F#</span></span>](../tour.md)

[<span data-ttu-id="497e6-247">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="497e6-247">F# Language Reference</span></span>](../language-reference/index.md)

[<span data-ttu-id="497e6-248">함수</span><span class="sxs-lookup"><span data-stu-id="497e6-248">Functions</span></span>](../language-reference/functions/index.md)

[<span data-ttu-id="497e6-249">모듈</span><span class="sxs-lookup"><span data-stu-id="497e6-249">Modules</span></span>](../language-reference/modules.md)

[<span data-ttu-id="497e6-250">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="497e6-250">Namespaces</span></span>](../language-reference/namespaces.md)

[<span data-ttu-id="497e6-251">VSCode Ionide: FSharp</span><span class="sxs-lookup"><span data-stu-id="497e6-251">Ionide-VSCode: FSharp</span></span>](https://github.com/ionide/ionide-vscode-fsharp)
