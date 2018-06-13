---
title: C# 및 Visual Studio Code 시작 - C# 가이드
description: Visual Studio Code를 사용하여 C#에서 첫 번째 .NET Core 응용 프로그램을 만들고 디버그하는 방법을 알아봅니다.
author: kendrahavens
ms.author: mairaw
ms.date: 09/27/2017
ms.openlocfilehash: 8958c39ba16cadbfab95e35fa36e8e85ce0a4ab8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33213619"
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="0c580-103">C# 및 Visual Studio Code 시작</span><span class="sxs-lookup"><span data-stu-id="0c580-103">Get Started with C# and Visual Studio Code</span></span>

<span data-ttu-id="0c580-104">.NET Core는 Windows, Linux 및 macOS에서 실행되는 응용 프로그램을 만들기 위한 빠른 모듈식 플랫폼을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="0c580-105">C# 확장이 있는 Visual Studio Code를 사용하면 C# IntelliSense(스마트 코드 완성) 및 디버깅을 완벽하게 지원하는 강력한 편집 환경이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0c580-106">전제 조건</span><span class="sxs-lookup"><span data-stu-id="0c580-106">Prerequisites</span></span>

1. <span data-ttu-id="0c580-107">[Visual Studio Code](https://code.visualstudio.com/)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="0c580-108">[.NET Core SDK](https://www.microsoft.com/net/download/core)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-108">Install the [.NET Core SDK](https://www.microsoft.com/net/download/core).</span></span>
3. <span data-ttu-id="0c580-109">Visual Studio Code의 [C# 확장](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="0c580-110">Visual Studio Code의 확장을 설치하는 방법에 대한 자세한 내용은 [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery)(VS Code 확장 Marketplace)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c580-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="0c580-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="0c580-111">Hello World</span></span>

<span data-ttu-id="0c580-112">.NET Core에서 간단한 "Hello World" 프로그램으로 시작해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="0c580-113">프로젝트 열기</span><span class="sxs-lookup"><span data-stu-id="0c580-113">Open a project:</span></span>

    * <span data-ttu-id="0c580-114">Visual Studio Code를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-114">Open Visual Studio Code.</span></span>
    * <span data-ttu-id="0c580-115">왼쪽 메뉴에 있는 탐색기 아이콘을 클릭한 다음 **폴더 열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    * <span data-ttu-id="0c580-116">주 메뉴에서 **파일** > **폴더 열기**를 선택하여 C# 프로젝트를 저장하려는 폴더를 열고 **폴더 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-116">Select **File** > **Open Folder** from the main menu to open the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="0c580-117">이 예제에서는 *HelloWorld*라는 프로젝트에 대한 폴더를 만들어 봅니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-117">For our example, we're creating a folder for our project named *HelloWorld*.</span></span>

      ![VSCodeOpenFolder](media/with-visual-studio-code/vscodeopenfolder.png)

2. <span data-ttu-id="0c580-119">C# 프로젝트 초기화</span><span class="sxs-lookup"><span data-stu-id="0c580-119">Initialize a C# project:</span></span>
    * <span data-ttu-id="0c580-120">주 메뉴에서 **보기** > **통합 터미널**을 선택하여 Visual Studio Code에서 통합 터미널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-120">Open the Integrated Terminal from Visual Studio Code by selecting **View** > **Integrated Terminal** from the main menu.</span></span>
    * <span data-ttu-id="0c580-121">터미널 창에서 `dotnet new console`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-121">In the terminal window, type `dotnet new console`.</span></span>
    * <span data-ttu-id="0c580-122">이 명령은 이미 작성된 간단한 "Hello World" 프로그램이 있는 폴더에 `Program.cs` 파일을 만들고 `HelloWorld.csproj`라는 C# 프로젝트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-122">This command creates a `Program.cs` file in your folder with a simple "Hello World" program already written, along with a C# project file named `HelloWorld.csproj`.</span></span>

      ![dotnet new 명령](media/with-visual-studio-code/dotnetnew.png)

3. <span data-ttu-id="0c580-124">빌드 자산 확인</span><span class="sxs-lookup"><span data-stu-id="0c580-124">Resolve the build assets:</span></span>

    * <span data-ttu-id="0c580-125">**.NET Core 1.x**의 경우 `dotnet restore`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-125">For **.NET Core 1.x**, type `dotnet restore`.</span></span> <span data-ttu-id="0c580-126">`dotnet restore`를 실행하면 프로젝트를 빌드하는 데 필요한 필수 .NET Core 패키지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-126">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

      ![dotnet restore 명령](media/with-visual-studio-code/dotnetrestore.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. <span data-ttu-id="0c580-128">"Hello World" 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="0c580-128">Run the "Hello World" program:</span></span>

    * <span data-ttu-id="0c580-129">`dotnet run`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-129">Type `dotnet run`.</span></span> 

      ![dotnet run 명령](media/with-visual-studio-code/dotnetrun.png)

<span data-ttu-id="0c580-131">[Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) 또는 [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu)에 대한 추가 설치 도움말이 제공되는 짧은 비디오 자습서를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-131">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="0c580-132">디버그</span><span class="sxs-lookup"><span data-stu-id="0c580-132">Debug</span></span>

1. <span data-ttu-id="0c580-133">*Program.cs*를 클릭하여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-133">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="0c580-134">Visual Studio Code에서 C# 파일을 처음 열면 [OmniSharp](http://www.omnisharp.net/)에서 편집기가 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](http://www.omnisharp.net/) loads in the editor.</span></span>

    ![Program.cs 파일 열기](media/with-visual-studio-code/opencs.png)

2. <span data-ttu-id="0c580-136">Visual Studio Code는 앱을 빌드하고 디버그하기 위해 누락된 자산을 추가하라는 메시지를 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-136">Visual Studio Code should prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="0c580-137">**예**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-137">Select **Yes**.</span></span> 

    ![누락된 자산에 대한 프롬프트](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="0c580-139">디버그 보기를 열려면 왼쪽 메뉴에서 디버깅 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-139">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![디버그 탭 열기](media/with-visual-studio-code/opendebug.png)

4. <span data-ttu-id="0c580-141">창 위쪽에서 녹색 화살표를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-141">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="0c580-142">옆에 있는 드롭다운 목록에서 `.NET Core Launch (console)`가 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-142">Make sure the drop-down next to it has `.NET Core Launch (console)` selected.</span></span>

    ![.NET Core 선택](media/with-visual-studio-code/selectcore.png)

5. <span data-ttu-id="0c580-144">9번째 줄 옆에 있는 **편집기 여백**(편집기에서 줄 번호 왼쪽에 있는 공간)을 클릭하여 프로젝트에 중단점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-144">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9.</span></span>

    ![중단점 설정](media/with-visual-studio-code/setbreakpoint.png)

6. <span data-ttu-id="0c580-146">디버깅을 시작하려면 <kbd>F5</kbd> 또는 녹색 화살표를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-146">To start debugging, select <kbd>F5</kbd> or the green arrow.</span></span> <span data-ttu-id="0c580-147">이전 단계에서 설정한 중단점에 도달하면 디버거에서 프로그램 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-147">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    * <span data-ttu-id="0c580-148">디버깅 동안 왼쪽 위에 있는 창에서 지역 변수를 보거나 디버그 콘솔을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-148">While debugging, you can view your local variables in the top left pane or use the debug console.</span></span>

    ![실행 및 디버그](media/with-visual-studio-code/rundebug.png)

7. <span data-ttu-id="0c580-150">디버깅을 계속하려면 위쪽에 있는 녹색 화살표를 선택하고, 중지하려면 위쪽의 빨간색 사각형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c580-150">Select the green arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

> [!TIP] 
> <span data-ttu-id="0c580-151">Visual Studio Code에서 OmniSharp를 사용한 .NET Core 디버깅에 대한 자세한 내용 및 문제 해결 정보는 [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)(.NET Core 디버거 설정 지침)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c580-151">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0c580-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c580-152">See also</span></span>
<span data-ttu-id="0c580-153">[Visual Studio Code 설정](https://code.visualstudio.com/docs/setup/setup-overview) </span><span class="sxs-lookup"><span data-stu-id="0c580-153">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) </span></span>  
[<span data-ttu-id="0c580-154">Visual Studio Code의 디버깅</span><span class="sxs-lookup"><span data-stu-id="0c580-154">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/editor/debugging)
