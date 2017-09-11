---
title: "Visual Studio 2017에서 .NET Core로 클래스 라이브러리 사용"
description: "Visual Studio 2017에서 클래스 라이브러리의 멤버를 호출하는 방법을 알아봅니다."
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.translationtype: HT
ms.sourcegitcommit: 1b028e5880f9e57e87c16eabeb442e0a46a369da
ms.openlocfilehash: 38e6c7d8797285abc4eb2e87602cc0bbf46ba590
ms.contentlocale: ko-kr
ms.lasthandoff: 09/08/2017

---

# <a name="consuming-a-class-library-with-net-core-in-visual-studio-2017"></a><span data-ttu-id="ddf47-103">Visual Studio 2017에서 .NET Core로 클래스 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="ddf47-103">Consuming a class library with .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="ddf47-104">[Visual Studio 2017에서 .NET Core를 사용하여 C# 클래스 라이브러리 빌드](./library-with-visual-studio.md) 또는 [Visual Studio 2017에서 .NET Core를 사용하여 Visual Basic 클래스 라이브러리 빌드](vb-library-with-visual-studio.md)의 단계를 따라 클래스 라이브러리를 만들고, [Visual Studio 2017에서 .NET Core를 사용하여 클래스 라이브러리 테스트](testing-library-with-visual-studio.md)에서 테스트하고, 라이브러리의 릴리스 버전을 빌드한 후 다음 단계는 호출자가 사용할 수 있게 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-104">Once you've created a class library by following the steps in [Building a C# class library with .NET Core in Visual Studio 2017](./library-with-visual-studio.md) or [Building a Visual Basic class library with .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md), tested it in [Testing a class library with .NET Core in Visual Studio 2017](testing-library-with-visual-studio.md), and built a Release version of the library, the next step is to make it available to callers.</span></span> <span data-ttu-id="ddf47-105">이 작업은</span><span class="sxs-lookup"><span data-stu-id="ddf47-105">You can do this in two ways:</span></span>

* <span data-ttu-id="ddf47-106">라이브러리가 단일 솔루션에 사용되는 경우(예: 단일 대형 응용 프로그램의 구성 요소인 경우) 솔루션에 프로젝트로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-106">If the library will be used by a single solution (for example, if it's a component in a single large application), you can include it as a project in your solution.</span></span>

* <span data-ttu-id="ddf47-107">라이브러리에 일반적으로 액세스할 수 있으면 NuGet 패키지로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-107">If the library will be generally accessible, you can distribute it as a NuGet package.</span></span>

## <a name="including-a-library-as-a-project-in-a-solution"></a><span data-ttu-id="ddf47-108">라이브러리를 솔루션에 프로젝트로 포함</span><span class="sxs-lookup"><span data-stu-id="ddf47-108">Including a library as a project in a solution</span></span>

<span data-ttu-id="ddf47-109">클래스 라이브러리와 동일한 솔루션에 단위 테스트를 포함한 것처럼 응용 프로그램을 해당 솔루션의 일부로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-109">Just as you included unit tests in the same solution as your class library, you can include your application as part of that solution.</span></span> <span data-ttu-id="ddf47-110">예를 들어 사용자가 문자열을 입력하도록 요구하고 첫 번째 문자가 대문자인지 여부를 보고하는 콘솔 응용 프로그램에서 이 클래스 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-110">For example, you can use your class library in a console application that prompts the user to enter a string and reports whether its first character is uppercase:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="ddf47-111">C#</span><span class="sxs-lookup"><span data-stu-id="ddf47-111">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="ddf47-112">[Visual Studio 2017에서 .NET Core를 사용하여 C# 클래스 라이브러리 빌드](./library-with-visual-studio.md) 항목에서 만든 `ClassLibraryProjects` 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-112">Open the `ClassLibraryProjects` solution you created in the [Building a C# Class Library with .NET Core in Visual Studio 2017](./library-with-visual-studio.md) topic.</span></span> <span data-ttu-id="ddf47-113">**솔루션 탐색기**에서 **ClassLibraryProjects** 솔루션을 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **추가** > **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-113">In **Solution Explorer**, right-click the **ClassLibraryProjects** solution and select **Add** > **New Project** from the context menu.</span></span>

1. <span data-ttu-id="ddf47-114">**새 프로젝트 추가** 대화 상자에서 **Visual C#** 노드를 확장하고 **.NET Core** 노드, **콘솔 앱(.NET Core)** 프로젝트 템플릿을 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-114">In the **Add New Project** dialog, expand the **Visual C#** node and select the **.NET Core** node followed by the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="ddf47-115">**이름** 텍스트 상자에 "ShowCase"를 입력하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-115">In the **Name** text box, type "ShowCase", and select the **OK** button.</span></span>

   ![새 프로젝트 추가 대화 상자](./media/consuming-library-with-visual-studio/addnewproject.png)

1. <span data-ttu-id="ddf47-117">**솔루션 탐색기**에서 **ShowCase** 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-117">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span> 

   ![ShowCase 상황에 맞는 메뉴](./media/consuming-library-with-visual-studio/setstartupproject.png)

1. <span data-ttu-id="ddf47-119">처음에는 프로젝트에서 클래스 라이브러리에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-119">Initially, your project doesn't have access to your class library.</span></span> <span data-ttu-id="ddf47-120">클래스 라이브러리의 메서드를 호출할 수 있도록 허용하려면 클래스 라이브러리에 대한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-120">To allow it to call methods in your class library, you create a reference to the class library.</span></span> <span data-ttu-id="ddf47-121">**솔루션 탐색기**에서 `ShowCase` 프로젝트의 **종속성** 노드를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-121">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node and select **Add Reference**.</span></span>

   ![ShowCase 종속성 상황에 맞는 메뉴](./media/consuming-library-with-visual-studio/addreference.png)

1. <span data-ttu-id="ddf47-123">**참조 관리자** 대화 상자에서 **StringLibrary**, 해당 클래스 라이브러리 프로젝트를 차례로 선택한 다음 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-123">In the **Reference Manager** dialog, select **StringLibrary**, your class library project, and select the **OK** button.</span></span>

   ![참조 관리자](./media/consuming-library-with-visual-studio/referencemanager.png)

1. <span data-ttu-id="ddf47-125">*Program.cs* 파일의 코드 창에서 모든 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-125">In the code window for the *Program.cs* file, replace all of the code with the following code:</span></span>

   <span data-ttu-id="ddf47-126">[!CODE-csharp[UsingClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]</span><span class="sxs-lookup"><span data-stu-id="ddf47-126">[!CODE-csharp[UsingClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]</span></span>

   <span data-ttu-id="ddf47-127">이 코드는 [Console.WindowHeight](xref:System.Console.WindowHeight) 속성을 사용하여 콘솔 창의 행 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-127">The code uses the [Console.WindowHeight](xref:System.Console.WindowHeight) property to determine the number of rows in the console window.</span></span> <span data-ttu-id="ddf47-128">[Console.CursorTop](xref:System.Console.CursorTop) 속성이 콘솔 창의 행 수보다 크거나 같으면 코드는 콘솔 창을 지우고 사용자에게 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-128">Whenever the [Console.CursorTop](xref:System.Console.CursorTop) property is greater than or equal to the number of rows in the console window, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="ddf47-129">프로그램에서 문자열을 입력하라는 메시지를 사용자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-129">The program prompts the user to enter a string.</span></span> <span data-ttu-id="ddf47-130">문자열이 대문자로 시작하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-130">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="ddf47-131">사용자가 문자열을 입력하지 않고 Enter 키를 누르면 응용 프로그램이 종료되고 콘솔 창이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-131">If the user presses the Enter key without entering a string, the application terminates, and the console window closes.</span></span>

1. <span data-ttu-id="ddf47-132">필요한 경우 도구 모음을 변경하여 컴파일하는 `ShowCase` 프로젝트의 **디버그** 릴리스를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-132">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="ddf47-133">**ShowCase** 단추에서 녹색 화살표를 선택하여 프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-133">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![이미지](./media/consuming-library-with-visual-studio/toolbar.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="ddf47-135">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ddf47-135">Visual Basic</span></span>](#tab/visual-basic)
1. <span data-ttu-id="ddf47-136">[Visual Studio 2017에서 Visual Basic 및 .NET Core를 사용하여 클래스 라이브러리 빌드](vb-library-with-visual-studio.md) 항목에서 만든 `ClassLibraryProjects` 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-136">Open the `ClassLibraryProjects` solution you created in the [Building a class Library with Visual Basic and .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md) topic.</span></span> <span data-ttu-id="ddf47-137">**솔루션 탐색기**에서 **ClassLibraryProjects** 솔루션을 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **추가** > **새 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-137">In **Solution Explorer**, right-click the **ClassLibraryProjects** solution and select **Add** > **New Project** from the context menu.</span></span>

1. <span data-ttu-id="ddf47-138">**새 프로젝트 추가** 대화 상자에서 **Visual Basic** 노드를 확장하고 **.NET Core** 노드, **콘솔 앱(.NET Core)** 프로젝트 템플릿을 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-138">In the **Add New Project** dialog, expand the **Visual Basic** node and select the **.NET Core** node followed by the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="ddf47-139">**이름** 텍스트 상자에 "ShowCase"를 입력하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-139">In the **Name** text box, type "ShowCase", and select the **OK** button.</span></span>

   ![새 프로젝트 추가 대화 상자](./media/consuming-library-with-visual-studio/vb-addnewproject.png)

1. <span data-ttu-id="ddf47-141">**솔루션 탐색기**에서 **ShowCase** 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-141">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span> 

   ![ShowCase 상황에 맞는 메뉴](./media/consuming-library-with-visual-studio/setstartupproject.png)

1. <span data-ttu-id="ddf47-143">처음에는 프로젝트에서 클래스 라이브러리에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-143">Initially, your project doesn't have access to your class library.</span></span> <span data-ttu-id="ddf47-144">클래스 라이브러리의 메서드를 호출할 수 있도록 허용하려면 클래스 라이브러리에 대한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-144">To allow it to call methods in your class library, you create a reference to the class library.</span></span> <span data-ttu-id="ddf47-145">**솔루션 탐색기**에서 `ShowCase` 프로젝트의 **종속성** 노드를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-145">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node and select **Add Reference**.</span></span>

   ![ShowCase 종속성 상황에 맞는 메뉴](./media/consuming-library-with-visual-studio/addreference.png)

1. <span data-ttu-id="ddf47-147">**참조 관리자** 대화 상자에서 **StringLibrary**, 해당 클래스 라이브러리 프로젝트를 차례로 선택한 다음 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-147">In the **Reference Manager** dialog, select **StringLibrary**, your class library project, and select the **OK** button.</span></span>

   ![참조 관리자](./media/consuming-library-with-visual-studio/referencemanager.png)

1. <span data-ttu-id="ddf47-149">*Program.vb* 파일의 코드 창에서 모든 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-149">In the code window for the *Program.vb* file, replace all of the code with the following code:</span></span>

    <span data-ttu-id="ddf47-150">[!CODE-vb[UsingClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]</span><span class="sxs-lookup"><span data-stu-id="ddf47-150">[!CODE-vb[UsingClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]</span></span>

   <span data-ttu-id="ddf47-151">이 코드는 [Console.WindowHeight](xref:System.Console.WindowHeight) 속성을 사용하여 콘솔 창의 행 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-151">The code uses the [Console.WindowHeight](xref:System.Console.WindowHeight) property to determine the number of rows in the console window.</span></span> <span data-ttu-id="ddf47-152">[Console.CursorTop](xref:System.Console.CursorTop) 속성이 콘솔 창의 행 수보다 크거나 같으면 코드는 콘솔 창을 지우고 사용자에게 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-152">Whenever the [Console.CursorTop](xref:System.Console.CursorTop) property is greater than or equal to the number of rows in the console window, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="ddf47-153">프로그램에서 문자열을 입력하라는 메시지를 사용자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-153">The program prompts the user to enter a string.</span></span> <span data-ttu-id="ddf47-154">문자열이 대문자로 시작하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-154">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="ddf47-155">사용자가 문자열을 입력하지 않고 Enter 키를 누르면 응용 프로그램이 종료되고 콘솔 창이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-155">If the user presses the Enter key without entering a string, the application terminates, and the console window closes.</span></span>

1. <span data-ttu-id="ddf47-156">필요한 경우 도구 모음을 변경하여 컴파일하는 `ShowCase` 프로젝트의 **디버그** 릴리스를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-156">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="ddf47-157">**ShowCase** 단추에서 녹색 화살표를 선택하여 프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-157">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![이미지](./media/consuming-library-with-visual-studio/toolbar.png)
---

<span data-ttu-id="ddf47-159">[Visual Studio 2017을 사용하여 Hello World 응용 프로그램 디버그](debugging-with-visual-studio.md) 및 [Visual Studio 2017을 사용하여 Hello World 응용 프로그램 게시](publishing-with-visual-studio.md)의 단계에 따라 이 라이브러리를 사용하는 응용 프로그램을 디버그하고 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-159">You can debug and publish the application that uses this library by following the steps in [Debugging your Hello World application with Visual Studio 2017](debugging-with-visual-studio.md) and [Publishing your Hello World Application with Visual Studio 2017](publishing-with-visual-studio.md).</span></span>

## <a name="distributing-the-library-in-a-nuget-package"></a><span data-ttu-id="ddf47-160">NuGet 패키지에 포함된 라이브러리 배포</span><span class="sxs-lookup"><span data-stu-id="ddf47-160">Distributing the library in a NuGet package</span></span>

<span data-ttu-id="ddf47-161">클래스 라이브러리를 NuGet 패키지로 게시하여 광범위하게 사용하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-161">You can make your class library widely available by publishing it as a NuGet package.</span></span> <span data-ttu-id="ddf47-162">Visual Studio에서는 NuGet 패키지의 생성을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-162">Visual Studio does not support the creation of NuGet packages.</span></span> <span data-ttu-id="ddf47-163">이 패키지를 만들려면 [`dotnet` 명령줄 유틸리티](../../core/tools/dotnet.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-163">To create one, you use the [`dotnet` command line utility](../../core/tools/dotnet.md):</span></span>

1. <span data-ttu-id="ddf47-164">콘솔 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-164">Open a console window.</span></span> <span data-ttu-id="ddf47-165">예를 들어 Windows 작업 표시줄의 **무엇이든 물어보세요.** 텍스트 상자에 `Command Prompt`(약식으로 `cmd`)를 입력한 다음 **명령 프롬프트** 데스크톱 앱을 선택하거나 검색 결과에서 선택된 경우 Enter 키를 눌러 콘솔 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-165">For example in the **Ask me anything** text box in the Windows taskbar, enter `Command Prompt` (or `cmd` for short), and open a console window by either selecting the **Command Prompt** desktop app or pressing Enter if it's selected in the search results.</span></span>

1. <span data-ttu-id="ddf47-166">라이브러리의 프로젝트 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-166">Navigate to your library's project directory.</span></span> <span data-ttu-id="ddf47-167">일반적인 파일 위치를 다시 구성하지 않은 경우 *Documents\Visual Studio 2017\Projects\ClassLibraryProjects\StringLibrary* 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-167">Unless you've reconfigured the typical file location, it's in the *Documents\Visual Studio 2017\Projects\ClassLibraryProjects\StringLibrary* directory.</span></span> <span data-ttu-id="ddf47-168">이 디렉터리에는 소스 코드 및 프로젝트 파일 *StringLibrary.csproj*가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-168">The directory contains your source code and a project file, *StringLibrary.csproj*.</span></span>

1. <span data-ttu-id="ddf47-169">명령 `dotnet pack --no-build`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-169">Issue the command `dotnet pack --no-build`.</span></span> <span data-ttu-id="ddf47-170">`dotnet` 유틸리티는 *.nupkg* 확장명을 가진 패키지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-170">The `dotnet` utility generates a package with a *.nupkg* extension.</span></span>

   > [!TIP]
   > <span data-ttu-id="ddf47-171">*dotnet.exe*를 포함하는 디렉터리가 해당 PATH에 없는 경우 콘솔 창에 `where dotnet.exe`를 입력하여 해당 위치를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddf47-171">If the directory that contains *dotnet.exe* is not in your PATH, you can find its location by entering `where dotnet.exe` in the console window.</span></span>

<span data-ttu-id="ddf47-172">NuGet 패키지를 만드는 방법에 대한 자세한 내용은 [플랫폼 간 도구로 NuGet 패키지를 만드는 방법](../../core/deploying/creating-nuget-packages.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ddf47-172">For more information on creating NuGet packages, see [How to Create a NuGet Package with Cross Platform Tools](../../core/deploying/creating-nuget-packages.md).</span></span>

