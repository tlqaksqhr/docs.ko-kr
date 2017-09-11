---
title: "Visual Studio 2017에서 .NET Core 및 C#을 사용하여 Hello World 응용 프로그램 빌드"
description: "Visual Studio 2017에서 C#을 사용하여 간단한 .NET Core 콘솔 응용 프로그램을 빌드하는 방법을 알아봅니다."
keywords: ".NET Core, .NET Core 콘솔 응용 프로그램, Visual Studio 2017"
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 97aa50bf-bdf8-416d-a56c-ac77504c14ea
ms.translationtype: HT
ms.sourcegitcommit: 9b3a2f38b981dd5e7c3535c8212125a147aab122
ms.openlocfilehash: 37b81a6d4cf53dcf17158ccc4df6aca488f9a26b
ms.contentlocale: ko-kr
ms.lasthandoff: 08/29/2017

---

# <a name="build-a-c-hello-world-application-with-net-core-in-visual-studio-2017"></a><span data-ttu-id="83948-104">Visual Studio 2017에서 .NET Core를 사용하여 C# Hello World 응용 프로그램 빌드</span><span class="sxs-lookup"><span data-stu-id="83948-104">Build a C# Hello World application with .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="83948-105">이 항목에서는 Visual Studio 2017에서 C#을 사용하여 간단한 .NET Core 콘솔 응용 프로그램을 빌드, 디버그 및 게시하는 과정을 단계별로 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-105">This topic provides a step-by-step introduction to building, debugging, and publishing a simple .NET Core console application using C# in Visual Studio 2017.</span></span> <span data-ttu-id="83948-106">Visual Studio 2017은 .NET Core 응용 프로그램 빌드를 위해 필요한 모든 기능을 갖춘 개발 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-106">Visual Studio 2017 provides a full-featured development environment for building .NET Core applications.</span></span> <span data-ttu-id="83948-107">플랫폼 특정 종속성이 없는 응용 프로그램은 .NET Core에서 대상으로 하는 모든 플랫폼과 .NET Core가 설치된 모든 시스템에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83948-107">As long as the application doesn't have platform-specific dependencies, the application can run on any platform that .NET Core targets and on any system that has .NET Core installed.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="83948-108">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="83948-108">Prerequisites</span></span>

<span data-ttu-id="83948-109">".NET Core 플랫폼 간 개발" 워크로드가 설치된 [Visual Studio 2017](https://www.visualstudio.com/downloads/).</span><span class="sxs-lookup"><span data-stu-id="83948-109">[Visual Studio 2017](https://www.visualstudio.com/downloads/) with the ".NET Core cross-platform development" workload installed.</span></span> <span data-ttu-id="83948-110">.NET Core 1.1 또는 .NET Core 2.0을 사용하여 앱을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83948-110">You can develop your app with either .NET Core 1.1 or .NET Core 2.0.</span></span>

<span data-ttu-id="83948-111">자세한 내용은 [Windows의 .NET Core에 대한 필수 조건](../../core/windows-prerequisites.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83948-111">For more information, see the [Prerequisites for .NET Core on Windows](../../core/windows-prerequisites.md) topic.</span></span>

## <a name="a-simple-hello-world-application"></a><span data-ttu-id="83948-112">간단한 Hello World 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="83948-112">A simple Hello World application</span></span>

<span data-ttu-id="83948-113">먼저 간단한 "Hello World" 콘솔 응용 프로그램을 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="83948-113">Begin by creating a simple "Hello World" console application.</span></span> <span data-ttu-id="83948-114">아래 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-114">Follow these steps:</span></span>

1. <span data-ttu-id="83948-115">Visual Studio 2017을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-115">Launch Visual Studio 2017.</span></span> <span data-ttu-id="83948-116">메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-116">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="83948-117">*새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **.NET Core** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-117">In the *New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="83948-118">그런 다음 **콘솔 앱(.NET Core)** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-118">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="83948-119">**이름** 텍스트 상자에 "HelloWorld"를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-119">In the **Name** text box, type "HelloWorld".</span></span> <span data-ttu-id="83948-120">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-120">Select the **OK** button.</span></span>

   ![콘솔 앱이 선택된 새 프로젝트 대화 상자](./media/with-visual-studio/newproject.png)
   
1. <span data-ttu-id="83948-122">Visual Studio에서는 템플릿을 사용하여 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83948-122">Visual Studio uses the template to create your project.</span></span> <span data-ttu-id="83948-123">.NET Core용 C# 콘솔 응용 프로그램 템플릿은 <xref:System.String> 배열을 인수로 사용하는 단일 메서드 `Main`로 `Program` 클래스를 자동으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-123">The C# Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="83948-124">`Main`은 응용 프로그램 진입점으로, 응용 프로그램을 시작할 때 런타임에 의해 자동으로 호출되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="83948-124">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="83948-125">응용 프로그램이 시작될 때 제공되는 모든 명령줄 인수는 *args* 배열에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83948-125">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio 및 새 HelloWorld 프로젝트](./media/with-visual-studio/devenv.png)

   <span data-ttu-id="83948-127">템플릿은 간단한 "Hello World" 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83948-127">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="83948-128"><xref:System.Console.WriteLine(System.String)?displayProperty=fullName> 메서드를 호출하여 리터럴 문자열 "Hello World!"를</span><span class="sxs-lookup"><span data-stu-id="83948-128">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=fullName> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="83948-129">콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-129">in the console window.</span></span> <span data-ttu-id="83948-130">도구 모음에서 녹색 화살표가 있는 **HelloWorld** 단추를 선택하여 디버그 모드에서 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83948-130">By selecting the **HelloWorld** button with the green arrow on the toolbar, you can run the program in Debug mode.</span></span> <span data-ttu-id="83948-131">이렇게 하면 콘솔 창이 잠깐만 표시되었다가 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="83948-131">If you do, the console window is visible for only a brief time interval before it closes.</span></span> <span data-ttu-id="83948-132">`Main` 메서드의 단일 문이 실행되는 즉시 `Main` 메서드가 종료되고 응용 프로그램도 종료되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="83948-132">This occurs because the `Main` method terminates and the application ends as soon as the single statement in the `Main` method executes.</span></span>

1. <span data-ttu-id="83948-133">응용 프로그램이 콘솔 창을 닫기 전에 일시 중지되도록 하려면 <xref:System.Console.WriteLine(System.String)?displayProperty=fullName> 메서드 호출 바로 뒤에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-133">To cause the application to pause before it closes the console window, add the following code immediately after the call to the <xref:System.Console.WriteLine(System.String)?displayProperty=fullName> method:</span></span>

   ```csharp
   Console.Write("Press any key to continue...");
   Console.ReadKey(true);
   ```
   <span data-ttu-id="83948-134">이 코드는 프로그램을 중지하려면 아무 키나 누르라는 메시지를 표시하며, 사용자가 아무 키나 누르면 프로그램이 일시 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="83948-134">This code prompts the user to press any key and then pauses the program until a key is pressed.</span></span>

1. <span data-ttu-id="83948-135">메뉴 모음에서 **빌드** > **솔루션 빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-135">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="83948-136">이렇게 하면 프로그램이 IL(중간 언어)로 컴파일됩니다. 이 컴파일 결과는 JIT(Just-In-Time) 컴파일러에 의해 이진 코드로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="83948-136">This compiles your program into an intermediate language (IL) that's converted into binary code by a just-in-time (JIT) compiler.</span></span>

1. <span data-ttu-id="83948-137">도구 모음에서 녹색 화살표가 있는 **HelloWorld** 단추를 선택하여 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-137">Run the program by selecting the **HelloWorld** button with the green arrow on the toolbar.</span></span>

   ![“Hello World 계속하려면 아무 키나 누르세요.”를 표시하는 콘솔 창](./media/with-visual-studio/helloworld1.png)

1. <span data-ttu-id="83948-139">콘솔 창을 닫으려면 아무 키나 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="83948-139">Press any key to close the console window.</span></span>

## <a name="enhancing-the-hello-world-application"></a><span data-ttu-id="83948-140">Hello World 응용 프로그램 개선</span><span class="sxs-lookup"><span data-stu-id="83948-140">Enhancing the Hello World application</span></span>

<span data-ttu-id="83948-141">사용자에게 이름을 입력하라는 메시지를 표시한 다음 사용자 이름을 날짜 및 시간과 함께 표시하도록 응용 프로그램을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-141">Enhance your application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="83948-142">프로그램을 수정하고 테스트하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-142">To modify and test the program, do the following:</span></span>

1. <span data-ttu-id="83948-143">코드 창에서 `public static void Main(string[] args)` 줄 다음에 오는 여는 중괄호 바로 뒤, 첫 번째 닫는 중괄호 앞에 다음 C# 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-143">Enter the following C# code in the code window immediately after the opening bracket that follows the `public static void Main(string[] args)` line and before the first closing bracket:</span></span>

   <span data-ttu-id="83948-144">[!code-csharp[GettingStarted#1](../../../samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="83948-144">[!code-csharp[GettingStarted#1](../../../samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]</span></span>

   <span data-ttu-id="83948-145">이 코드는 기존 <xref:System.Console.WriteLine%2A?displayProperty=fullName>, <xref:System.Console.Write%2A?displayProperty=fullName> 및 <xref:System.Console.ReadKey%2A?displayProperty=fullName> 문을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-145">This code replaces the existing <xref:System.Console.WriteLine%2A?displayProperty=fullName>, <xref:System.Console.Write%2A?displayProperty=fullName>, and <xref:System.Console.ReadKey%2A?displayProperty=fullName> statements.</span></span>

   ![업데이트된 Main 메서드가 포함된 Visual Studio 프로그램 C# 파일](./media/with-visual-studio/codewindow.png)

   <span data-ttu-id="83948-147">이 코드는 "What is your name?"을</span><span class="sxs-lookup"><span data-stu-id="83948-147">This code displays "What is your name?"</span></span> <span data-ttu-id="83948-148">콘솔 창에 표시하고 사용자가 문자열을 입력한 후 Enter 키를 누를 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="83948-148">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="83948-149">이 문자열을 `name`이라는 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-149">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="83948-150">또한 현재 현지 시간을 포함하는 <xref:System.DateTime.Now?displayProperty=fullName> 속성 값을 검색한 후 `date`라는 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-150">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=fullName> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="83948-151">마지막으로, [보간된 문자열](../../csharp/language-reference/keywords/interpolated-strings.md)을 사용하여 콘솔 창에 이러한 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-151">Finally, it uses an [interpolated string](../../csharp/language-reference/keywords/interpolated-strings.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="83948-152">**빌드** > **솔루션 빌드**를 선택하여 프로그램을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-152">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="83948-153">도구 모음에서 녹색 화살표를 선택하거나, F5 키를 누르거나, **디버그** > **디버깅 시작** 메뉴 항목을 선택하여 Visual Studio의 디버그 모드에서 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-153">Run the program in Debug mode in Visual Studio by selecting the green arrow on the toolbar, pressing F5, or choosing the **Debug** > **Start Debugging** menu item.</span></span> <span data-ttu-id="83948-154">이름을 입력하고 Enter 키를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-154">Respond to the prompt by entering a name and pressing the Enter key.</span></span>

   ![수정된 프로그램 출력이 표시된 콘솔 창](./media/with-visual-studio/helloworld2.png)

1. <span data-ttu-id="83948-156">콘솔 창을 닫으려면 아무 키나 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="83948-156">Press any key to close the console window.</span></span>

<span data-ttu-id="83948-157">응용 프로그램을 만들고 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="83948-157">You've created and run your application.</span></span> <span data-ttu-id="83948-158">전문가 수준의 응용 프로그램을 개발하려면 응용 프로그램 릴리스 준비를 위해 몇 가지 추가 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="83948-158">To develop a professional application, take some additional steps to make your application ready for release:</span></span>

- <span data-ttu-id="83948-159">응용 프로그램 디버그에 대한 자세한 내용은 [Visual Studio 2017을 사용하여 C# Hello World 응용 프로그램 디버그](debugging-with-visual-studio.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83948-159">For information on debugging your application, see [Debugging your C# Hello World application with Visual Studio 2017](debugging-with-visual-studio.md).</span></span>

- <span data-ttu-id="83948-160">응용 프로그램의 배포 가능한 버전을 개발 및 게시하는 방법에 대한 자세한 내용은 [Visual Studio 2017을 사용하여 C# Hello World 응용 프로그램 게시](publishing-with-visual-studio.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83948-160">For information on developing and publishing a distributable version of your application, see [Publishing your C# Hello World application with Visual Studio 2017](publishing-with-visual-studio.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="83948-161">관련 항목</span><span class="sxs-lookup"><span data-stu-id="83948-161">Related topics</span></span>

<span data-ttu-id="83948-162">콘솔 응용 프로그램 대신 .NET Core 및 Visual Studio 2017을 사용하여 클래스 라이브러리를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83948-162">Instead of a console application, you can also build a class library with .NET Core and Visual Studio 2017.</span></span> <span data-ttu-id="83948-163">단계별 지침을 보려면 [Visual Studio 2017에서 C# 및 .NET Core로 클래스 라이브러리 빌드](library-with-visual-studio.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83948-163">For a step-by-step introduction, see [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md).</span></span>

<span data-ttu-id="83948-164">다운로드할 수 있는 코드 편집기인 [Visual Studio Code](https://code.visualstudio.com/)를 사용하여 Mac, Linux 및 Windows에서 .NET Core 콘솔 응용 프로그램을 개발할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83948-164">You can also develop a .NET Core console app on Mac, Linux, and Windows by using [Visual Studio Code](https://code.visualstudio.com/), a downloadable code editor.</span></span> <span data-ttu-id="83948-165">단계별 자습서에 대해서는 [Visual Studio Code 시작](with-visual-studio-code.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83948-165">For a step-by-step tutorial, see [Getting Started with Visual Studio Code](with-visual-studio-code.md).</span></span>

