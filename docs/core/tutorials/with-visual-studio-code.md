---
title: "C# 및 Visual Studio Code 시작 - C# 가이드 | Microsoft Docs"
description: "Visual Studio Code를 사용하여 C#에서 첫 번째 .NET Core 응용 프로그램을 만들고 디버그하는 방법을 알아봅니다."
keywords: "C#, 시작, 취득, 설치, Visual Studio Code, 플랫폼 간"
author: kendrahavens
ms.author: mairaw
ms.date: 8/01/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 76c23597-4cf9-467e-8a47-0c3703ce37e7
ms.translationtype: HT
ms.sourcegitcommit: 3bd8800e7410ae4a3b89f5962af957789edd48b0
ms.openlocfilehash: a10fda5663f0a49069388ee8ee7a9ebb575cd549
ms.contentlocale: ko-kr
ms.lasthandoff: 08/03/2017

---

# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="d0026-104">C# 및 Visual Studio Code 시작</span><span class="sxs-lookup"><span data-stu-id="d0026-104">Get Started with C# and Visual Studio Code</span></span>

<span data-ttu-id="d0026-105">.NET Core는 Windows, Linux 및 macOS에서 실행되는 응용 프로그램을 만들기 위한 빠른 모듈식 플랫폼을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-105">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="d0026-106">C# 확장이 있는 Visual Studio Code를 사용하면 C# IntelliSense(스마트 코드 완성) 및 디버깅을 완벽하게 지원하는 강력한 편집 환경이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-106">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d0026-107">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d0026-107">Prerequisites</span></span>

1. <span data-ttu-id="d0026-108">[Visual Studio Code](https://code.visualstudio.com/)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-108">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="d0026-109">[.NET Core SDK](https://www.microsoft.com/net/download/core)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-109">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="d0026-110">Visual Studio Code Marketplace에서 [C# 확장](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-110">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) from the Visual Studio Code Marketplace.</span></span>

## <a name="hello-world"></a><span data-ttu-id="d0026-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="d0026-111">Hello World</span></span>

<span data-ttu-id="d0026-112">.NET Core에서 간단한 "Hello World" 프로그램으로 시작해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="d0026-113">프로젝트 열기</span><span class="sxs-lookup"><span data-stu-id="d0026-113">Open a project:</span></span>

    * <span data-ttu-id="d0026-114">Visual Studio Code를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="d0026-115">왼쪽 메뉴에 있는 탐색기 아이콘을 클릭한 다음 **폴더 열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="d0026-116">C# 프로젝트를 저장할 폴더를 선택하고 **폴더 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-116">Select the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="d0026-117">이 예제에서는 'hello World'라는 프로젝트에 대한 폴더를 만들어 봅니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-117">For our example, we'll create a folder for our project named 'HelloWorld'.</span></span> 

  ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

    * <span data-ttu-id="d0026-119">또는 주 메뉴에서 **파일** > **폴더 열기**를 선택하여 프로젝트 폴더를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-119">Alternatively, you can select **File** > **Open Folder** from the main menu to open your project folder.</span></span>

2. <span data-ttu-id="d0026-120">C# 프로젝트 초기화</span><span class="sxs-lookup"><span data-stu-id="d0026-120">Initialize a C# project:</span></span>
    * <span data-ttu-id="d0026-121"><kbd>CTRL</kbd>+<kbd>\\` </kbd>(백틱 기호)을 입력하여 Visual Studio Code에서 통합 터미널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-121">Open the Integrated Terminal from Visual Studio Code by typing <kbd>CTRL</kbd>+<kbd>\\`</kbd> (backtick).</span></span> <span data-ttu-id="d0026-122">또는 주 메뉴에서 **보기** > **통합 터미널**을 선택해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-122">Alternatively, you can select **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="d0026-123">터미널 창에서 `dotnet new console`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-123">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="d0026-124">이렇게 하면 이미 작성된 간단한 "Hello World" 프로그램이 있는 폴더에 `Program.cs` 파일이 만들어지고 `HelloWorld.csproj`라는 C# 프로젝트 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-124">This creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

  ![dotnet new 명령](media/with-visual-studio-code/dotnetnew.png)

3. <span data-ttu-id="d0026-126">빌드 자산 확인</span><span class="sxs-lookup"><span data-stu-id="d0026-126">Resolve the build assets:</span></span>

    * <span data-ttu-id="d0026-127">**.NET Core 1.1**의 경우 `dotnet restore`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-127">For **.NET Core 1.1**, type `dotnet restore`.</span></span> <span data-ttu-id="d0026-128">`dotnet restore`를 실행하면 프로젝트를 빌드하는 데 필요한 필수 .NET Core 패키지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-128">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

   ![dotnet restore 명령](media/with-visual-studio-code/dotnetrestore.png)

    * <span data-ttu-id="d0026-130">**.NET Core 2.0**의 경우 이 단계는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-130">For **.NET Core 2.0**, this step is optional.</span></span> <span data-ttu-id="d0026-131">새 프로젝트를 만들 때는 `dotnet restore` 명령이 자동으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-131">The `dotnet restore` command executes automatically when a new project is created.</span></span>

4. <span data-ttu-id="d0026-132">"Hello World" 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="d0026-132">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="d0026-133">`dotnet run`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-133">Type `dotnet run`.</span></span> 

  ![dotnet run 명령](media/with-visual-studio-code/dotnetrun.png)

<span data-ttu-id="d0026-135">[Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) 또는 [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu)에 대한 추가 설치 도움말이 제공되는 짧은 비디오 자습서를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-135">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="d0026-136">디버그</span><span class="sxs-lookup"><span data-stu-id="d0026-136">Debug</span></span>
1. <span data-ttu-id="d0026-137">*Program.cs*를 클릭하여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-137">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="d0026-138">Visual Studio Code에서 C# 파일을 처음 열면 [OmniSharp](http://www.omnisharp.net/)에서 편집기가 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-138">The first time you open a C# file in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) will load in the editor.</span></span>

  ![Program.cs 파일 열기](media/with-visual-studio-code/opencs.png)

2. <span data-ttu-id="d0026-140">Visual Studio Code는 앱을 빌드하고 디버그하기 위해 누락된 자산을 추가하라는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-140">Visual Studio Code will prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="d0026-141">**예**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-141">Select **Yes**.</span></span> 

  ![누락된 자산에 대한 프롬프트](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="d0026-143">디버그 보기를 열려면 왼쪽 메뉴에서 디버깅 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-143">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

  ![디버그 탭 열기](media/with-visual-studio-code/opendebug.png)

4. <span data-ttu-id="d0026-145">창 위쪽에서 녹색 화살표를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-145">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="d0026-146">옆에 있는 드롭다운 목록에서 `.NET Core Launch (console)`가 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-146">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

  ![.NET Core 선택](media/with-visual-studio-code/selectcore.png)

5. <span data-ttu-id="d0026-148">9번째 줄 옆에 있는 **편집기 여백**(편집기에서 줄 번호 왼쪽에 있는 공간)을 클릭하여 프로젝트에 중단점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-148">Add a breakpoint to your project by clicking on the **editor margin** (the space on the left of the line numbers in the editor) next to line 9.</span></span>

  ![중단점 설정](media/with-visual-studio-code/setbreakpoint.png)

6. <span data-ttu-id="d0026-150"><kbd>F5</kbd> 또는 녹색 화살표를 선택하여 디버그를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-150">Select <kbd>F5</kbd> or the green arrow to start debugging.</span></span> <span data-ttu-id="d0026-151">이전 단계에서 설정한 중단점에 도달하면 디버거에서 프로그램 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-151">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="d0026-152">디버깅 동안 왼쪽 위에 있는 창에서 지역 변수를 보거나 디버그 콘솔을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-152">While debugging you can view your local variables in the top left pane or use the debug console.</span></span>

  ![실행 및 디버그](media/with-visual-studio-code/rundebug.png)

7. <span data-ttu-id="d0026-154">디버깅을 계속하려면 위쪽에 있는 녹색 화살표를 선택하고, 중지하려면 위쪽의 빨간색 사각형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d0026-154">Select the green arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

> [!TIP] 
> <span data-ttu-id="d0026-155">Visual Studio Code에서 OmniSharp를 사용한 .NET Core 디버깅에 대한 자세한 내용 및 문제 해결 정보는 [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)(.NET Core 디버거 설정 지침)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0026-155">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d0026-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0026-156">See also</span></span>
<span data-ttu-id="d0026-157">[Visual Studio Code 설정](https://code.visualstudio.com/docs/setup/setup-overview) </span><span class="sxs-lookup"><span data-stu-id="d0026-157">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span></span>  
[<span data-ttu-id="d0026-158">Visual Studio Code의 디버깅</span><span class="sxs-lookup"><span data-stu-id="d0026-158">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/editor/debugging)

