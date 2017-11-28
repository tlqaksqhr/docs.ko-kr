---
title: "Visual Studio 2017에서 .NET Core로 클래스 라이브러리 사용"
description: "Visual Studio 2017에서 클래스 라이브러리의 멤버를 호출하는 방법을 알아봅니다."
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
dev_langs:
- csharp
- vb
ms.openlocfilehash: 180ed868116967b03c5d4058b5618927242defc2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="consuming-a-class-library-with-net-core-in-visual-studio-2017"></a><span data-ttu-id="f7e1c-103">Visual Studio 2017에서 .NET Core로 클래스 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="f7e1c-103">Consuming a class library with .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="f7e1c-104">[Visual Studio 2017에서 .NET Core를 사용하여 C# 클래스 라이브러리 빌드](./library-with-visual-studio.md) 또는 [Visual Studio 2017에서 .NET Core를 사용하여 Visual Basic 클래스 라이브러리 빌드](vb-library-with-visual-studio.md)의 단계를 따라 클래스 라이브러리를 만들고, [Visual Studio 2017에서 .NET Core를 사용하여 클래스 라이브러리 테스트](testing-library-with-visual-studio.md)에서 테스트하고, 라이브러리의 릴리스 버전을 빌드한 후 다음 단계는 호출자가 사용할 수 있게 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-104">Once you've created a class library by following the steps in [Building a C# class library with .NET Core in Visual Studio 2017](./library-with-visual-studio.md) or [Building a Visual Basic class library with .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md), tested it in [Testing a class library with .NET Core in Visual Studio 2017](testing-library-with-visual-studio.md), and built a Release version of the library, the next step is to make it available to callers.</span></span> <span data-ttu-id="f7e1c-105">이 작업은</span><span class="sxs-lookup"><span data-stu-id="f7e1c-105">You can do this in two ways:</span></span>

* <span data-ttu-id="f7e1c-106">라이브러리가 단일 솔루션에 사용되는 경우(예: 단일 대형 응용 프로그램의 구성 요소인 경우) 솔루션에 프로젝트로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-106">If the library will be used by a single solution (for example, if it's a component in a single large application), you can include it as a project in your solution.</span></span>

* <span data-ttu-id="f7e1c-107">라이브러리에 일반적으로 액세스할 수 있으면 NuGet 패키지로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-107">If the library will be generally accessible, you can distribute it as a NuGet package.</span></span>

## <a name="including-a-library-as-a-project-in-a-solution"></a><span data-ttu-id="f7e1c-108">라이브러리를 솔루션에 프로젝트로 포함</span><span class="sxs-lookup"><span data-stu-id="f7e1c-108">Including a library as a project in a solution</span></span>

<span data-ttu-id="f7e1c-109">클래스 라이브러리와 동일한 솔루션에 단위 테스트를 포함한 것처럼 응용 프로그램을 해당 솔루션의 일부로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-109">Just as you included unit tests in the same solution as your class library, you can include your application as part of that solution.</span></span> <span data-ttu-id="f7e1c-110">예를 들어 사용자가 문자열을 입력하도록 요구하고 첫 번째 문자가 대문자인지 여부를 보고하는 콘솔 응용 프로그램에서 이 클래스 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-110">For example, you can use your class library in a console application that prompts the user to enter a string and reports whether its first character is uppercase:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="f7e1c-111">C#</span><span class="sxs-lookup"><span data-stu-id="f7e1c-111">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="f7e1c-112">[Visual Studio 2017에서 .NET Core를 사용하여 C# 클래스 라이브러리 빌드](./library-with-visual-studio.md) 항목에서 만든 `ClassLibraryProjects` 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-112">Open the `ClassLibraryProjects` solution you created in the [Building a C# Class Library with .NET Core in Visual Studio 2017](./library-with-visual-studio.md) topic.</span></span> <span data-ttu-id="f7e1c-113">**솔루션 탐색기**에서 **ClassLibraryProjects** 솔루션을 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **추가** > **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-113">In **Solution Explorer**, right-click the **ClassLibraryProjects** solution and select **Add** > **New Project** from the context menu.</span></span>

1. <span data-ttu-id="f7e1c-114">**새 프로젝트 추가** 대화 상자에서 **Visual C#** 노드를 확장하고 **.NET Core** 노드, **콘솔 앱(.NET Core)** 프로젝트 템플릿을 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-114">In the **Add New Project** dialog, expand the **Visual C#** node and select the **.NET Core** node followed by the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="f7e1c-115">**이름** 텍스트 상자에 "ShowCase"를 입력하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-115">In the **Name** text box, type "ShowCase", and select the **OK** button.</span></span>

   ![새 프로젝트 추가 대화 상자](./media/consuming-library-with-visual-studio/addnewproject.png)

1. <span data-ttu-id="f7e1c-117">**솔루션 탐색기**에서 **ShowCase** 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-117">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span> 

   ![ShowCase 상황에 맞는 메뉴](./media/consuming-library-with-visual-studio/setstartupproject.png)

1. <span data-ttu-id="f7e1c-119">처음에는 프로젝트에서 클래스 라이브러리에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-119">Initially, your project doesn't have access to your class library.</span></span> <span data-ttu-id="f7e1c-120">클래스 라이브러리의 메서드를 호출할 수 있도록 허용하려면 클래스 라이브러리에 대한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-120">To allow it to call methods in your class library, you create a reference to the class library.</span></span> <span data-ttu-id="f7e1c-121">**솔루션 탐색기**에서 `ShowCase` 프로젝트의 **종속성** 노드를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-121">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node and select **Add Reference**.</span></span>

   ![ShowCase 종속성 상황에 맞는 메뉴](./media/consuming-library-with-visual-studio/addreference.png)

1. <span data-ttu-id="f7e1c-123">**참조 관리자** 대화 상자에서 **StringLibrary**, 해당 클래스 라이브러리 프로젝트를 차례로 선택한 다음 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-123">In the **Reference Manager** dialog, select **StringLibrary**, your class library project, and select the **OK** button.</span></span>

   ![참조 관리자](./media/consuming-library-with-visual-studio/referencemanager.png)

1. <span data-ttu-id="f7e1c-125">*Program.cs* 파일의 코드 창에서 모든 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-125">In the code window for the *Program.cs* file, replace all of the code with the following code:</span></span>

   [!CODE-csharp[UsingClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]

   <span data-ttu-id="f7e1c-126">이 코드는 [Console.WindowHeight](xref:System.Console.WindowHeight) 속성을 사용하여 콘솔 창의 행 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-126">The code uses the [Console.WindowHeight](xref:System.Console.WindowHeight) property to determine the number of rows in the console window.</span></span> <span data-ttu-id="f7e1c-127">[Console.CursorTop](xref:System.Console.CursorTop) 속성이 콘솔 창의 행 수보다 크거나 같으면 코드는 콘솔 창을 지우고 사용자에게 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-127">Whenever the [Console.CursorTop](xref:System.Console.CursorTop) property is greater than or equal to the number of rows in the console window, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="f7e1c-128">프로그램에서 문자열을 입력하라는 메시지를 사용자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-128">The program prompts the user to enter a string.</span></span> <span data-ttu-id="f7e1c-129">문자열이 대문자로 시작하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-129">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="f7e1c-130">사용자가 문자열을 입력하지 않고 Enter 키를 누르면 응용 프로그램이 종료되고 콘솔 창이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-130">If the user presses the Enter key without entering a string, the application terminates, and the console window closes.</span></span>

1. <span data-ttu-id="f7e1c-131">필요한 경우 도구 모음을 변경하여 컴파일하는 `ShowCase` 프로젝트의 **디버그** 릴리스를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-131">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="f7e1c-132">**ShowCase** 단추에서 녹색 화살표를 선택하여 프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-132">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![이미지](./media/consuming-library-with-visual-studio/toolbar.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="f7e1c-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7e1c-134">Visual Basic</span></span>](#tab/visual-basic)
1. <span data-ttu-id="f7e1c-135">[Visual Studio 2017에서 Visual Basic 및 .NET Core를 사용하여 클래스 라이브러리 빌드](vb-library-with-visual-studio.md) 항목에서 만든 `ClassLibraryProjects` 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-135">Open the `ClassLibraryProjects` solution you created in the [Building a class Library with Visual Basic and .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md) topic.</span></span> <span data-ttu-id="f7e1c-136">**솔루션 탐색기**에서 **ClassLibraryProjects** 솔루션을 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **추가** > **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-136">In **Solution Explorer**, right-click the **ClassLibraryProjects** solution and select **Add** > **New Project** from the context menu.</span></span>

1. <span data-ttu-id="f7e1c-137">**새 프로젝트 추가** 대화 상자에서 **Visual Basic** 노드를 확장하고 **.NET Core** 노드, **콘솔 앱(.NET Core)** 프로젝트 템플릿을 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-137">In the **Add New Project** dialog, expand the **Visual Basic** node and select the **.NET Core** node followed by the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="f7e1c-138">**이름** 텍스트 상자에 "ShowCase"를 입력하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-138">In the **Name** text box, type "ShowCase", and select the **OK** button.</span></span>

   ![새 프로젝트 추가 대화 상자](./media/consuming-library-with-visual-studio/vb-addnewproject.png)

1. <span data-ttu-id="f7e1c-140">**솔루션 탐색기**에서 **ShowCase** 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-140">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span> 

   ![ShowCase 상황에 맞는 메뉴](./media/consuming-library-with-visual-studio/setstartupproject.png)

1. <span data-ttu-id="f7e1c-142">처음에는 프로젝트에서 클래스 라이브러리에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-142">Initially, your project doesn't have access to your class library.</span></span> <span data-ttu-id="f7e1c-143">클래스 라이브러리의 메서드를 호출할 수 있도록 허용하려면 클래스 라이브러리에 대한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-143">To allow it to call methods in your class library, you create a reference to the class library.</span></span> <span data-ttu-id="f7e1c-144">**솔루션 탐색기**에서 `ShowCase` 프로젝트의 **종속성** 노드를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-144">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node and select **Add Reference**.</span></span>

   ![ShowCase 종속성 상황에 맞는 메뉴](./media/consuming-library-with-visual-studio/addreference.png)

1. <span data-ttu-id="f7e1c-146">**참조 관리자** 대화 상자에서 **StringLibrary**, 해당 클래스 라이브러리 프로젝트를 차례로 선택한 다음 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-146">In the **Reference Manager** dialog, select **StringLibrary**, your class library project, and select the **OK** button.</span></span>

   ![참조 관리자](./media/consuming-library-with-visual-studio/referencemanager.png)

1. <span data-ttu-id="f7e1c-148">*Program.vb* 파일의 코드 창에서 모든 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-148">In the code window for the *Program.vb* file, replace all of the code with the following code:</span></span>

    [!CODE-vb[UsingClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   <span data-ttu-id="f7e1c-149">이 코드는 [Console.WindowHeight](xref:System.Console.WindowHeight) 속성을 사용하여 콘솔 창의 행 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-149">The code uses the [Console.WindowHeight](xref:System.Console.WindowHeight) property to determine the number of rows in the console window.</span></span> <span data-ttu-id="f7e1c-150">[Console.CursorTop](xref:System.Console.CursorTop) 속성이 콘솔 창의 행 수보다 크거나 같으면 코드는 콘솔 창을 지우고 사용자에게 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-150">Whenever the [Console.CursorTop](xref:System.Console.CursorTop) property is greater than or equal to the number of rows in the console window, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="f7e1c-151">프로그램에서 문자열을 입력하라는 메시지를 사용자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-151">The program prompts the user to enter a string.</span></span> <span data-ttu-id="f7e1c-152">문자열이 대문자로 시작하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-152">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="f7e1c-153">사용자가 문자열을 입력하지 않고 Enter 키를 누르면 응용 프로그램이 종료되고 콘솔 창이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-153">If the user presses the Enter key without entering a string, the application terminates, and the console window closes.</span></span>

1. <span data-ttu-id="f7e1c-154">필요한 경우 도구 모음을 변경하여 컴파일하는 `ShowCase` 프로젝트의 **디버그** 릴리스를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-154">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="f7e1c-155">**ShowCase** 단추에서 녹색 화살표를 선택하여 프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-155">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![이미지](./media/consuming-library-with-visual-studio/toolbar.png)
---

<span data-ttu-id="f7e1c-157">[Visual Studio 2017을 사용하여 Hello World 응용 프로그램 디버그](debugging-with-visual-studio.md) 및 [Visual Studio 2017을 사용하여 Hello World 응용 프로그램 게시](publishing-with-visual-studio.md)의 단계에 따라 이 라이브러리를 사용하는 응용 프로그램을 디버그하고 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-157">You can debug and publish the application that uses this library by following the steps in [Debugging your Hello World application with Visual Studio 2017](debugging-with-visual-studio.md) and [Publishing your Hello World Application with Visual Studio 2017](publishing-with-visual-studio.md).</span></span>

## <a name="distributing-the-library-in-a-nuget-package"></a><span data-ttu-id="f7e1c-158">NuGet 패키지에 포함된 라이브러리 배포</span><span class="sxs-lookup"><span data-stu-id="f7e1c-158">Distributing the library in a NuGet package</span></span>

<span data-ttu-id="f7e1c-159">클래스 라이브러리를 NuGet 패키지로 게시하여 광범위하게 사용하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-159">You can make your class library widely available by publishing it as a NuGet package.</span></span> <span data-ttu-id="f7e1c-160">Visual Studio에서는 NuGet 패키지의 생성을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-160">Visual Studio does not support the creation of NuGet packages.</span></span> <span data-ttu-id="f7e1c-161">이 패키지를 만들려면 [`dotnet` 명령줄 유틸리티](../../core/tools/dotnet.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-161">To create one, you use the [`dotnet` command line utility](../../core/tools/dotnet.md):</span></span>

1. <span data-ttu-id="f7e1c-162">콘솔 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-162">Open a console window.</span></span> <span data-ttu-id="f7e1c-163">예를 들어 Windows 작업 표시줄의 **무엇이든 물어보세요.** 텍스트 상자에 `Command Prompt`(약식으로 `cmd`)를 입력한 다음 **명령 프롬프트** 데스크톱 앱을 선택하거나 검색 결과에서 선택된 경우 Enter 키를 눌러 콘솔 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-163">For example in the **Ask me anything** text box in the Windows taskbar, enter `Command Prompt` (or `cmd` for short), and open a console window by either selecting the **Command Prompt** desktop app or pressing Enter if it's selected in the search results.</span></span>

1. <span data-ttu-id="f7e1c-164">라이브러리의 프로젝트 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-164">Navigate to your library's project directory.</span></span> <span data-ttu-id="f7e1c-165">일반적인 파일 위치를 다시 구성하지 않은 경우 *Documents\Visual Studio 2017\Projects\ClassLibraryProjects\StringLibrary* 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-165">Unless you've reconfigured the typical file location, it's in the *Documents\Visual Studio 2017\Projects\ClassLibraryProjects\StringLibrary* directory.</span></span> <span data-ttu-id="f7e1c-166">이 디렉터리에는 소스 코드 및 프로젝트 파일 *StringLibrary.csproj*가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-166">The directory contains your source code and a project file, *StringLibrary.csproj*.</span></span>

1. <span data-ttu-id="f7e1c-167">명령 `dotnet pack --no-build`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-167">Issue the command `dotnet pack --no-build`.</span></span> <span data-ttu-id="f7e1c-168">`dotnet` 유틸리티는 *.nupkg* 확장명을 가진 패키지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-168">The `dotnet` utility generates a package with a *.nupkg* extension.</span></span>

   > [!TIP]
   > <span data-ttu-id="f7e1c-169">*dotnet.exe*를 포함하는 디렉터리가 해당 PATH에 없는 경우 콘솔 창에 `where dotnet.exe`를 입력하여 해당 위치를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-169">If the directory that contains *dotnet.exe* is not in your PATH, you can find its location by entering `where dotnet.exe` in the console window.</span></span>

<span data-ttu-id="f7e1c-170">NuGet 패키지를 만드는 방법에 대한 자세한 내용은 [플랫폼 간 도구로 NuGet 패키지를 만드는 방법](../../core/deploying/creating-nuget-packages.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-170">For more information on creating NuGet packages, see [How to Create a NuGet Package with Cross Platform Tools](../../core/deploying/creating-nuget-packages.md).</span></span>
