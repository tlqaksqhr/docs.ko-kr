---
title: Visual Studio 2017을 사용하여 Hello World 응용 프로그램 게시
description: 게시하면 응용 프로그램을 실행하는 데 필요한 파일 집합이 만들어집니다.
author: BillWagner
ms.author: wiwagn
ms.date: 10/05/2017
ms.openlocfilehash: 11421c8820dd562ba1dbb5900ba1e9bf944b45d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33212133"
---
# <a name="publish-your-hello-world-application-with-visual-studio-2017"></a><span data-ttu-id="5a340-103">Visual Studio 2017을 사용하여 Hello World 응용 프로그램 게시</span><span class="sxs-lookup"><span data-stu-id="5a340-103">Publish your Hello World application with Visual Studio 2017</span></span>

<span data-ttu-id="5a340-104">[Visual Studio 2017에서 .NET Core를 사용하여 C# Hello World 응용 프로그램 빌드](with-visual-studio.md) 또는 [Visual Studio 2017에서 .NET Core를 사용하여 Visual Basic Hello World 응용 프로그램 빌드](vb-with-visual-studio.md)에서 Hello World 콘솔 응용 프로그램을 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-104">In [Build a C# Hello World application with .NET Core in Visual Studio 2017](with-visual-studio.md) or [Build a Visual Basic Hello World application with .NET Core in Visual Studio 2017](vb-with-visual-studio.md), you built a Hello World console application.</span></span> <span data-ttu-id="5a340-105">[Visual Studio 2017을 사용하여 C# Hello World 응용 프로그램 디버그](debugging-with-visual-studio.md)에서 Visual Studio 디버거를 사용하여 테스트했습니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-105">In [Debug your C# Hello World application with Visual Studio 2017](debugging-with-visual-studio.md), you tested it using the Visual Studio debugger.</span></span> <span data-ttu-id="5a340-106">예상대로 작동하는지 확인했으므로 다른 사용자가 실행할 수 있도록 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-106">Now that you're sure that it works as expected, you can publish it so that other users can run it.</span></span> <span data-ttu-id="5a340-107">게시하면 응용 프로그램을 실행하는 데 필요한 파일 집합이 만들어지며, 이 파일을 대상 컴퓨터에 복사하여 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-107">Publishing creates the set of files that are needed to run your application, and you can deploy the files by copying them to a target machine.</span></span>

<span data-ttu-id="5a340-108">응용 프로그램을 게시하고 실행하려면</span><span class="sxs-lookup"><span data-stu-id="5a340-108">To publish and run your application:</span></span> 

1. <span data-ttu-id="5a340-109">Visual Studio에서 응용 프로그램의 릴리스 버전을 빌드하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-109">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="5a340-110">필요한 경우 도구 모음의 빌드 구성 설정을 **디버그**에서 **릴리스**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-110">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![Visual Studio 도구 모음](media/publishing-with-visual-studio/toolbar.png)

1. <span data-ttu-id="5a340-112">**HelloWorld** 프로젝트(HelloWorld 솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 메뉴에서 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-112">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span> <span data-ttu-id="5a340-113">주 Visual Studio에서 **빌드** 메뉴에서 **HelloWorld 게시**를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-113">You can also select **Publish HelloWorld** from the main Visual Studio **Build** menu.</span></span>

   ![Visual Studio 도구 모음](media/publishing-with-visual-studio/publish1.png)


   ![Visual Studio 도구 모음](media/publishing-with-visual-studio/publishwindow.png)

1. <span data-ttu-id="5a340-116">콘솔 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-116">Open a console window.</span></span> <span data-ttu-id="5a340-117">예를 들어 Windows 작업 표시줄의 **검색하려면 여기에 입력하세요.** 텍스트 상자에 `Command Prompt`(약식으로 `cmd`)를 입력한 다음 **명령 프롬프트** 데스크톱 앱을 선택하거나 검색 결과에서 선택된 경우 Enter 키를 눌러 콘솔 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-117">For example in the **Type here to search** text box in the Windows taskbar, enter `Command Prompt` (or `cmd` for short), and open a console window by either selecting the **Command Prompt** desktop app or pressing Enter if it's selected in the search results.</span></span>

1. <span data-ttu-id="5a340-118">응용 프로그램 프로젝트 디렉터리의 `bin\release\PublishOutput` 하위 디렉터리에 게시된 응용 프로그램으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-118">Navigate to the published application in the `bin\release\PublishOutput` subdirectory of your application's project directory.</span></span> <span data-ttu-id="5a340-119">다음 그림과 같이, 게시된 출력에는 다음 4개의 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-119">As the following figure shows, the published output includes the following four files:</span></span>

      * <span data-ttu-id="5a340-120">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="5a340-120">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="5a340-121">응용 프로그램의 런타임 종속성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-121">The application's runtime dependencies file.</span></span> <span data-ttu-id="5a340-122">응용 프로그램을 실행하는 데 필요한 .NET Core 구성 요소 및 라이브러리(응용 프로그램을 포함하는 동적 연결 라이브러리 포함)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-122">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run your application.</span></span> <span data-ttu-id="5a340-123">자세한 내용은 [ 런타임 구성 파일](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a340-123">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>
 
      * <span data-ttu-id="5a340-124">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="5a340-124">*HelloWorld.dll*</span></span>

         <span data-ttu-id="5a340-125">응용 프로그램을 포함하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-125">The file that contains your application.</span></span> <span data-ttu-id="5a340-126">콘솔 창에 `dotnet HelloWorld.dll` 명령을 입력하여 실행될 수 있는 동적 연결 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-126">It is a dynamic link library that can be executed by entering the `dotnet HelloWorld.dll` command in a console window.</span></span> 

      * <span data-ttu-id="5a340-127">*HelloWorld.pdb*(배포에 대한 선택 사항)</span><span class="sxs-lookup"><span data-stu-id="5a340-127">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="5a340-128">디버그 기호를 포함하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-128">A file that contains debug symbols.</span></span> <span data-ttu-id="5a340-129">게시된 응용 프로그램 버전을 디버그해야 하는 경우에는 이 파일을 저장해야 하지만 그렇지 않으면 응용 프로그램과 함께 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-129">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="5a340-130">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="5a340-130">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="5a340-131">응용 프로그램의 런타임 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-131">The application's runtime configuration file.</span></span> <span data-ttu-id="5a340-132">응용 프로그램이 실행되도록 빌드된 .NET Core의 버전을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-132">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="5a340-133">자세한 내용은 [ 런타임 구성 파일](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a340-133">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>  

   ![게시된 파일을 보여 주는 콘솔 창](media/publishing-with-visual-studio/publishedfiles.png)

<span data-ttu-id="5a340-135">게시 프로세스는 프레임워크 종속 배포를 만듭니다. 이 배포는 시스템에 .NET Core가 설치되어 있으면 게시된 응용 프로그램이 .NET Core에서 지원하는 모든 플랫폼에서 실행되는 배포 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-135">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application will run on any platform supported by .NET Core with .NET Core installed on the system.</span></span> <span data-ttu-id="5a340-136">사용자는 콘솔 창에서 `dotnet HelloWorld.dll` 명령을 실행하여 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a340-136">Users can run your application by issuing the `dotnet HelloWorld.dll` command from a console window.</span></span>

<span data-ttu-id="5a340-137">.NET Core 응용 프로그램 게시 및 배포에 대한 자세한 내용은 [.NET Core 응용 프로그램 배포](../../core/deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a340-137">For more information on publishing and deploying .NET Core applications, see [.NET Core Application Deployment](../../core/deploying/index.md).</span></span>
