---
title: "Visual Studio 2017에서 C# 또는 Visual Basic Hello World .NET Core 응용 프로그램 디버깅"
description: "Visual Studio 2017에서 C# 또는 Visual Basic으로 작성된 Hello World 앱을 디버그하는 방법을 알아봅니다."
keywords: ".NET Core, .NET Core 콘솔 응용 프로그램, .NET Core 디버깅"
author: BillWagner
ms.author: wiwagn
ms.date: 12/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: cb213625-cc60-438b-9b9e-49aed0e4a974
ms.workload: dotnetcore
ms.openlocfilehash: 6c8e1de4e0053ae6f74dc6c74fe37b6d7661932e
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2018
---
# <a name="debug-your-hello-world-application-with-visual-studio-2017"></a><span data-ttu-id="0caca-104">Visual Studio 2017을 사용하여 Hello World 응용 프로그램 디버그</span><span class="sxs-lookup"><span data-stu-id="0caca-104">Debug your Hello World application with Visual Studio 2017</span></span>

<span data-ttu-id="0caca-105">지금까지 [Visual Studio 2017에서 .NET Core를 사용하여 C# Hello World 응용 프로그램 빌드](.\with-visual-studio.md) 또는 [Visual Studio 2017에서 .NET Core를 사용하여 Visual Basic Hello World 응용 프로그램 빌드](vb-with-visual-studio.md)의 단계에 따라 간단한 콘솔 응용 프로그램을 만들고 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-105">So far, you've followed the steps in [Build a C# Hello World Application with .NET Core in Visual Studio 2017](.\with-visual-studio.md) or [Build a Visual Basic Hello World Application with .NET Core in Visual Studio 2017](vb-with-visual-studio.md) to create and run a simple console application.</span></span> <span data-ttu-id="0caca-106">응용 프로그램을 작성하고 컴파일했으면 테스트를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-106">Once you've written and compiled your application, you can begin testing it.</span></span> <span data-ttu-id="0caca-107">Visual Studio에는 응용 프로그램을 테스트하고 문제를 해결하는 데 사용할 수 있는 포괄적인 디버깅 도구 집합이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-107">Visual Studio includes a comprehensive set of debugging tools that you can use when testing and troubleshooting your application.</span></span>

## <a name="debugging-in-debug-mode"></a><span data-ttu-id="0caca-108">디버그 모드에서 디버깅</span><span class="sxs-lookup"><span data-stu-id="0caca-108">Debugging in Debug mode</span></span>

<span data-ttu-id="0caca-109">*디버그* 및 *릴리스*는 Visual Studio의 기본 빌드 구성 중 두 개입니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-109">*Debug* and *Release* are two of Visual Studio's default build configurations.</span></span> <span data-ttu-id="0caca-110">현재 빌드 구성은 도구 모음에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-110">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="0caca-111">다음 도구 모음 그림은 Visual Studio가 **디버그** 모드로 응용 프로그램을 컴파일하도록 구성되어 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-111">The following toolbar image shows that Visual Studio is configured to compile your application in **Debug** mode.</span></span>

   ![Visual Studio 도구 모음](./media/debugging-with-visual-studio/toolbar1.png)

<span data-ttu-id="0caca-113">항상 디버그 모드에서 프로그램을 테스트하면서 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-113">You should always begin by testing your program in Debug mode.</span></span> <span data-ttu-id="0caca-114">디버그 모드는 대부분의 컴파일러 최적화를 끄고 빌드 프로세스 중 보다 다양한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-114">Debug mode turns off most compiler optimizations and provides richer information during the build process.</span></span>

## <a name="setting-a-breakpoint"></a><span data-ttu-id="0caca-115">중단점 설정</span><span class="sxs-lookup"><span data-stu-id="0caca-115">Setting a breakpoint</span></span>

<span data-ttu-id="0caca-116">디버그 모드에서 프로그램을 실행하고 몇 가지 디버깅 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-116">Run your program in Debug mode and try a few debugging features:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="0caca-117">C#</span><span class="sxs-lookup"><span data-stu-id="0caca-117">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="0caca-118">*중단점*은 중단점이 설정된 줄이 실행되기 *전에* 응용 프로그램 실행을 일시적으로 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-118">A *breakpoint* temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span> 

   <span data-ttu-id="0caca-119">코드 창의 왼쪽 여백에서 `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");` 줄을 클릭하거나 해당 줄을 선택하고 **디버그** > **중단점 설정/해제** 메뉴 항목을 선택하여 줄에 중단점을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-119">Set a breakpoint on the line that reads `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");` by clicking in the left margin of the code window on that line or by choosing the **Debug** > **Toggle Breakpoint** menu item with the line selected.</span></span> <span data-ttu-id="0caca-120">다음 그림에서 볼 수 있듯이 Visual Studio에서는 중단점이 설정된 줄을 강조 표시하고 왼쪽 여백에 빨간색 원을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-120">As the following figure shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red circle in its left margin.</span></span>

   ![중단점이 설정된 Visual Studio 프로그램 창](./media/debugging-with-visual-studio/setbreakpoint.png)

1. <span data-ttu-id="0caca-122">도구 모음에서 녹색 화살표가 있는 **HelloWorld** 단추를 선택하거나 F5 키를 누르거나 **디버그** > **디버깅 시작**을 선택하여 프로그램을 디버그 모드에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-122">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar, pressing F5, or choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="0caca-123">프로그램 이름을 입력하라는 메시지가 표시되면 콘솔 창에 문자열을 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-123">Enter a string in the console window when the program prompts for a name and press Enter.</span></span>

1. <span data-ttu-id="0caca-124">중단점에 도달할 때와 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-124">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="0caca-125">**자동** 창에는 현재 줄 주위에서 사용되는 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-125">The **Autos** window displays the values of variables that are used around the current line.</span></span> <span data-ttu-id="0caca-126">**지역** 창(**지역** 탭을 클릭하여 볼 수 있음)에는 현재 실행 중인 메서드에 정의된 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-126">The **Locals** window (which you can view by clicking the **Locals** tab) displays the values of variables that are defined in the currently executing method.</span></span>

   ![Visual Studio 응용 프로그램 창](./media/debugging-with-visual-studio/break.png)

1. <span data-ttu-id="0caca-128">변수 값을 변경하여 프로그램에 미치는 영향을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-128">You can change the value of the variables to see how it affects your program.</span></span> <span data-ttu-id="0caca-129">**직접 실행 창**이 표시되지 않는 경우 **디버그** > **창** > **직접 실행** 메뉴 항목을 선택하여 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-129">If the **Immediate Window** is not visible, display it by choosing the **Debug** > **Windows** > **Immediate** menu item.</span></span> <span data-ttu-id="0caca-130">**직접 실행 창**에서는 디버그하는 응용 프로그램을 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-130">The **Immediate Window** lets you interact with the application you're debugging.</span></span>

1. <span data-ttu-id="0caca-131">변수 값을 대화형으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-131">You can interactively change the values of variables.</span></span> <span data-ttu-id="0caca-132">**직접 실행 창**에 `name = "Gracie"`를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-132">Enter `name = "Gracie"` in the **Immediate Window** and press the Enter key.</span></span>

1. <span data-ttu-id="0caca-133">**직접 실행 창**에 `date = new DateTime(2016,11,01,11,59,00)`을 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-133">Enter `date = new DateTime(2016,11,01,11,59,00)` in the **Immediate Window** and press the Enter key.</span></span>

   <span data-ttu-id="0caca-134">**직접 실행 창**에는 문자열 변수의 값과 <xref:System.DateTime> 값의 속성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-134">The **Immediate Window** displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="0caca-135">또한 변수 값이 **자동** 및 **지역** 창에서 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-135">In addition, the value of the variables is updated in the **Autos** and **Locals** windows.</span></span>

   ![자동 창 및 직접 실행 창](./media/debugging-with-visual-studio/autosimmediate.png)

1. <span data-ttu-id="0caca-137">도구 모음에서 **계속** 단추를 선택하거나 **디버그** > **계속** 메뉴 항목을 선택하여 프로그램을 계속 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-137">Continue program execution by selecting the **Continue** button in the toolbar or by selecting the **Debug** > **Continue** menu item.</span></span> <span data-ttu-id="0caca-138">콘솔 창에 표시되는 값은 **직접 실행 창**에서 변경한 값과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-138">The values displayed in the console window correspond to the changes you made in the **Immediate Window**.</span></span>

   ![What is your name? 프롬프트에 형식화된 값 Jack과 Hello Gracie on 11/1/2016 at 11:59am을 차례로 표시하는 콘솔 창](./media/debugging-with-visual-studio/changed.png)

1. <span data-ttu-id="0caca-140">아무 키나 눌러 응용 프로그램을 끝내고 디버그 모드를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-140">Press any key to exit the application and end Debug mode.</span></span>
# <a name="visual-basictabvb"></a>[<span data-ttu-id="0caca-141">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0caca-141">Visual Basic</span></span>](#tab/vb)
1. <span data-ttu-id="0caca-142">*중단점*은 중단점이 설정된 줄이 실행되기 *전에* 응용 프로그램 실행을 일시적으로 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-142">A *breakpoint* temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span> 

   <span data-ttu-id="0caca-143">코드 창의 왼쪽 여백에서 `Console.WriteLine(vbCrLf + $"Hello, {name}, on {currentDate:d} at {currentDate:t}!")` 줄을 클릭하거나 해당 줄을 선택하고 **디버그** > **중단점 설정/해제** 메뉴 항목을 선택하여 줄에 중단점을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-143">Set a breakpoint on the line that reads `Console.WriteLine(vbCrLf + $"Hello, {name}, on {currentDate:d} at {currentDate:t}!")` by clicking in the left margin of the code window on that line or by choosing the **Debug** > **Toggle Breakpoint** menu item with the line selected.</span></span> <span data-ttu-id="0caca-144">다음 그림에서 볼 수 있듯이 Visual Studio에서는 중단점이 설정된 줄을 강조 표시하고 왼쪽 여백에 빨간색 원을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-144">As the following figure shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red circle in its left margin.</span></span>

   ![중단점이 설정된 Visual Studio 프로그램 창](./media/debugging-with-visual-studio/vb-setbreakpoint.png)

1. <span data-ttu-id="0caca-146">도구 모음에서 녹색 화살표가 있는 **HelloWorld** 단추를 선택하거나 F5 키를 누르거나 **디버그** > **디버깅 시작**을 선택하여 프로그램을 디버그 모드에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-146">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar, pressing F5, or choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="0caca-147">프로그램 이름을 입력하라는 메시지가 표시되면 콘솔 창에 문자열을 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-147">Enter a string in the console window when the program prompts for a name and press Enter.</span></span>

1. <span data-ttu-id="0caca-148">중단점에 도달할 때와 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-148">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="0caca-149">**자동** 창에는 현재 줄 주위에서 사용되는 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-149">The **Autos** window displays the values of variables that are used around the current line.</span></span> <span data-ttu-id="0caca-150">**지역** 창(**지역** 탭을 클릭하여 볼 수 있음)에는 현재 실행 중인 메서드에 정의된 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-150">The **Locals** window (which you can view by clicking the **Locals** tab) displays the values of variables that are defined in the currently executing method.</span></span>

   ![Visual Studio 응용 프로그램 창](./media/debugging-with-visual-studio/vb-break.png)

1. <span data-ttu-id="0caca-152">변수 값을 변경하여 프로그램에 미치는 영향을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-152">You can change the value of the variables to see how it affects your program.</span></span> <span data-ttu-id="0caca-153">**직접 실행 창**이 표시되지 않는 경우 **디버그** > **창** > **직접 실행** 메뉴 항목을 선택하여 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-153">If the **Immediate Window** is not visible, display it by choosing the **Debug** > **Windows** > **Immediate** menu item.</span></span> <span data-ttu-id="0caca-154">**직접 실행 창**에서는 디버그하는 응용 프로그램을 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-154">The **Immediate Window** lets you interact with the application you're debugging.</span></span>

1. <span data-ttu-id="0caca-155">변수 값을 대화형으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-155">You can interactively change the values of variables.</span></span> <span data-ttu-id="0caca-156">**직접 실행 창**에 `name = "Gracie"`를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-156">Enter `name = "Gracie"` in the **Immediate Window** and press the Enter key.</span></span>

1. <span data-ttu-id="0caca-157">**직접 실행 창**에 `currentDate = new DateTime(2016,11,01,11,59,00)`를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-157">Enter `currentDate = new DateTime(2016,11,01,11,59,00)` in the **Immediate Window** and press the Enter key.</span></span>

1. <span data-ttu-id="0caca-158">도구 모음에서 **계속** 단추를 선택하거나 **디버그** > **계속** 메뉴 항목을 선택하여 프로그램을 계속 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-158">Continue program execution by selecting the **Continue** button in the toolbar or by selecting the **Debug** > **Continue** menu item.</span></span> <span data-ttu-id="0caca-159">콘솔 창에 표시되는 값은 **직접 실행 창**에서 변경한 값과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-159">The values displayed in the console window correspond to the changes you made in the **Immediate Window**.</span></span>

   ![직접 실행 창에 입력된, 변경된 값을 보여 주는 콘솔 창](./media/debugging-with-visual-studio/changed.png)

1. <span data-ttu-id="0caca-161">아무 키나 눌러 응용 프로그램을 끝내고 디버그 모드를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-161">Press any key to exit the application and end Debug mode.</span></span>
---

## <a name="setting-a-conditional-breakpoint"></a><span data-ttu-id="0caca-162">조건부 중단점 설정</span><span class="sxs-lookup"><span data-stu-id="0caca-162">Setting a conditional breakpoint</span></span>

<span data-ttu-id="0caca-163">프로그램은 사용자가 입력하는 문자열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-163">Your program displays the string that the user enters.</span></span> <span data-ttu-id="0caca-164">사용자가 아무 값도 입력하지 않으면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="0caca-164">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="0caca-165">하나 이상의 조건이 충족될 경우 프로그램 실행을 중단하는 유용한 디버깅 기능인 *조건부 중단점*을 사용하여 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-165">You can test this with a useful debugging feature, the *conditional breakpoint*, which breaks program execution when one or more conditions are met.</span></span>

<span data-ttu-id="0caca-166">조건부 중단점을 설정하고 사용자가 문자열을 입력하지 못한 경우에 발생하는 상황을 테스트하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-166">To set a conditional breakpoint and test what happens when the user fails to enter a string, do the following:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="0caca-167">C#</span><span class="sxs-lookup"><span data-stu-id="0caca-167">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="0caca-168">중단점을 나타내는 빨간색 점을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-168">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="0caca-169">상황에 맞는 메뉴에서 **조건**을 선택하여 **중단점 설정** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-169">On the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="0caca-170">**조건** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-170">Check the box for **Conditions**.</span></span>

   ![중단점 설정 패널](./media/debugging-with-visual-studio/breakpointsettings.png)

1. <span data-ttu-id="0caca-172">**조건식**에서 "e.g. x == 5"를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-172">For the **Conditional Expression** replace "e.g. x == 5" with the following:</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="0caca-173">*name*에 값이 할당되지 않았거나 해당 값이 빈 문자열("")이기 때문에 `String.IsNullOrEmpty(name)` 메서드 호출이 `true`인 코드 조건을 테스트하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-173">You're testing for a code condition, that the `String.IsNullOrEmpty(name)` method call is `true` either because *name* has not been assigned a value or because its value is an empty string ("").</span></span> <span data-ttu-id="0caca-174">문이 실행되기 전에 프로그램 실행을 중단하는 *적중 횟수* 또는 스레드 식별자, 프로세스 이름 또는 스레드 이름과 같은 특성을 기준으로 프로그램 실행을 중단하는 *필터 조건*을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-174">You can also specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="0caca-175">**닫기** 단추를 선택하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-175">Select the **Close** button to close the dialog.</span></span>

1. <span data-ttu-id="0caca-176">디버그 모드에서 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-176">Run the program in Debug mode.</span></span>

1. <span data-ttu-id="0caca-177">콘솔 창에 이름을 입력하라는 메시지가 나타나면 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-177">In the console window, press the Enter key when prompted to enter your name.</span></span>

1. <span data-ttu-id="0caca-178">`name`이 `null` 또는 <xref:System.String.Empty?displayProperty=nameWithType>이라는 지정한 조건이 충족되었으므로 중단점에 도달한 후 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-178">Because the condition we specified, `name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>, has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="0caca-179">**지역** 창을 선택합니다. 이 창에는 현재 실행 중인 메서드(프로그램의 `Main` 메서드)에 로컬인 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-179">Select the **Locals** window, which shows the values of variables that are local to the currently executing method, which is the `Main` method in your program.</span></span> <span data-ttu-id="0caca-180">`name` 변수의 값은 `""` 또는 <xref:System.String.Empty?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-180">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="0caca-181">**직접 실행 창**에 다음 문을 입력하여 값이 빈 문자열인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-181">Confirm the value is an empty string by entering the following statement in the **Immediate Window**.</span></span> <span data-ttu-id="0caca-182">결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-182">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ![문이 실행된 후 true 값을 반환하는 직접 실행 창](./media/debugging-with-visual-studio/emptystring.png)

1. <span data-ttu-id="0caca-184">도구 모음에서 **계속** 단추를 선택하여 프로그램 실행을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-184">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="0caca-185">아무 키나 눌러 콘솔 창을 닫고 디버그 모드를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-185">Press any key to close the console window and exit Debug mode.</span></span>

1. <span data-ttu-id="0caca-186">코드 창 왼쪽 여백에 있는 점을 클릭하거나 행을 선택하고 **디버그 > 중단점 설정/해제** 메뉴 항목을 선택하여 중단점을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-186">Clear the breakpoint by clicking on the dot in the left margin of the code window or by choosing the **Debug > Toggle Breakpoint** menu item with the row selected.</span></span>
# <a name="visual-basictabvb"></a>[<span data-ttu-id="0caca-187">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0caca-187">Visual Basic</span></span>](#tab/vb)
1. <span data-ttu-id="0caca-188">중단점을 나타내는 빨간색 점을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-188">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="0caca-189">상황에 맞는 메뉴에서 **조건**을 선택하여 **중단점 설정** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-189">On the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="0caca-190">**조건** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-190">Check the box for **Conditions**.</span></span>

   ![중단점 설정 패널](./media/debugging-with-visual-studio/vb-breakpointsettings.png)

1. <span data-ttu-id="0caca-192">**조건식**에서 “e.g. x = 5”를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-192">For the **Conditional Expression** replace "e.g. x = 5" with the following:</span></span>

   ```vb
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="0caca-193">*name*에 값이 할당되지 않았거나 해당 값이 빈 문자열("")이기 때문에 `String.IsNullOrEmpty(name)` 메서드 호출이 `True`인 코드 조건을 테스트하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-193">You're testing for a code condition, that the `String.IsNullOrEmpty(name)` method call is `True` either because *name* has not been assigned a value or because its value is an empty string ("").</span></span> <span data-ttu-id="0caca-194">문이 실행되기 전에 프로그램 실행을 중단하는 *적중 횟수* 또는 스레드 식별자, 프로세스 이름 또는 스레드 이름과 같은 특성을 기준으로 프로그램 실행을 중단하는 *필터 조건*을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-194">You can also specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="0caca-195">**닫기** 단추를 선택하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-195">Select the **Close** button to close the dialog.</span></span>

1. <span data-ttu-id="0caca-196">디버그 모드에서 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-196">Run the program in Debug mode.</span></span>

1. <span data-ttu-id="0caca-197">콘솔 창에 이름을 입력하라는 메시지가 나타나면 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-197">In the console window, press the Enter key when prompted to enter your name.</span></span>

1. <span data-ttu-id="0caca-198">`name`이 `null` 또는 <xref:System.String.Empty?displayProperty=nameWithType>이라는 지정한 조건이 충족되었으므로 중단점에 도달한 후 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-198">Because the condition we specified, `name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>, has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="0caca-199">**지역** 창을 선택합니다. 이 창에는 현재 실행 중인 메서드(프로그램의 `Main` 메서드)에 로컬인 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-199">Select the **Locals** window, which shows the values of variables that are local to the currently executing method, which is the `Main` method in your program.</span></span> <span data-ttu-id="0caca-200">`name` 변수의 값은 `""` 또는 <xref:System.String.Empty?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-200">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="0caca-201">**직접 실행 창**에 다음 문을 입력하여 값이 빈 문자열인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-201">Confirm the value is an empty string by entering the following statement in the **Immediate Window**.</span></span> <span data-ttu-id="0caca-202">결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-202">The result is `true`.</span></span>

   ```vb
   ? String.IsNullOrEmpty(name)
   ```
  ![문이 실행된 후 true 값을 반환하는 직접 실행 창](./media/debugging-with-visual-studio/vb-emptystring.png)

1. <span data-ttu-id="0caca-204">도구 모음에서 **계속** 단추를 선택하여 프로그램 실행을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-204">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="0caca-205">아무 키나 눌러 콘솔 창을 닫고 디버그 모드를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-205">Press any key to close the console window and exit Debug mode.</span></span>

1. <span data-ttu-id="0caca-206">코드 창 왼쪽 여백에 있는 점을 클릭하거나 행을 선택하고 **디버그 > 중단점 설정/해제** 메뉴 항목을 선택하여 중단점을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-206">Clear the breakpoint by clicking on the dot in the left margin of the code window or by choosing the **Debug > Toggle Breakpoint** menu item with the row selected.</span></span>
---
## <a name="stepping-through-a-program"></a><span data-ttu-id="0caca-207">단계별 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="0caca-207">Stepping through a program</span></span>

<span data-ttu-id="0caca-208">Visual Studio에서 프로그램을 한 줄씩 단계별로 실행하고 해당 실행을 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-208">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="0caca-209">일반적으로 중단점을 설정하고 이 기능을 사용하여 프로그램 코드 일부의 프로그램 흐름을 따라가면서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-209">Ordinarily, you'd set a breakpoint and use this feature to follow program flow though a small part of your program code.</span></span> <span data-ttu-id="0caca-210">여기서는 프로그램이 작으므로 다음을 수행하여 전체 프로그램을 단계별로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-210">Since your program is small, you can step through the entire program by doing the following:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="0caca-211">C#</span><span class="sxs-lookup"><span data-stu-id="0caca-211">C#</span></span>](#tab/csharp)
1. <span data-ttu-id="0caca-212">메뉴 모음에서 **디버그** > **한 단계씩 코드 실행**을 선택하거나 F11 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-212">On the menu bar, choose **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="0caca-213">Visual Studio에서 다음에 실행될 줄을 강조 표시하고 옆에 화살표를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-213">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   ![Visual Studio 창](./media/debugging-with-visual-studio/stepinto1.png)

   <span data-ttu-id="0caca-215">이때 **자동** 창에는 현재 프로그램에서 단일 변수인 `args`만 정의되었다고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-215">At this point, the **Autos** window shows that your program has defined only one variable, `args`.</span></span> <span data-ttu-id="0caca-216">프로그램에 명령줄 인수를 전달하지 않았으므로 해당 값은 빈 문자열 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-216">Because you haven't passed any command-line arguments to the program, its value is an empty string array.</span></span> <span data-ttu-id="0caca-217">또한 Visual Studio에서는 빈 콘솔 창이 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-217">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="0caca-218">**디버그** > **한 단계씩 코드 실행**을 선택하거나 F11 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-218">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="0caca-219">이제 Visual Studio에서 다음에 실행될 줄을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-219">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="0caca-220">그림에서 볼 수 있듯이 마지막 문과 이 문 사이의 코드를 실행하는 데는 1밀리초 미만이 소요되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-220">As the figure shows, it has taken less than one millisecond to execute the code between the last statement and this one.</span></span> <span data-ttu-id="0caca-221">`args`가 선언된 유일한 변수이며 콘솔 창은 여전히 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-221">`args` remains the only declared variable, and the console window remains blank.</span></span>

   ![Visual Studio 창](./media/debugging-with-visual-studio/stepinto2.png)

1. <span data-ttu-id="0caca-223">**디버그** > **한 단계씩 코드 실행**을 선택하거나 F11 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-223">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="0caca-224">Visual Studio는 `name` 변수 할당을 포함하는 문을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-224">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="0caca-225">**자동** 창에서는 `name`이 `null`로 표시되고 콘솔 창에서는 문자열 "What is your name?"이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-225">The **Autos** window shows that `name` is `null`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="0caca-226">콘솔 창에 문자열을 입력하고 Enter 키를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-226">Respond to the prompt by entering a string in the console window and pressing Enter.</span></span> <span data-ttu-id="0caca-227">콘솔은 응답하지 않게 되고 입력한 문자열이 콘솔 창에 표시되지 않지만 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드는 사용자의 입력을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-227">The console is unresponsive, and the string you enter isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="0caca-228">**디버그** > **한 단계씩 코드 실행**을 선택하거나 F11 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-228">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="0caca-229">Visual Studio는 `date`(C#) 또는 `currentDate`(Visual Basic) 변수 할당을 포함하는 문을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-229">Visual Studio highlights the statement that includes the `date` (in C#) or `currentDate` (in Visual Basic) variable assignment.</span></span> <span data-ttu-id="0caca-230">**자동** 창에는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성 값과 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드 호출에 의해 반환된 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-230">The **Autos** window shows the <xref:System.DateTime.Now?displayProperty=nameWithType> property value and the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0caca-231">콘솔 창에는 콘솔이 입력을 요구할 때 입력된 문자열도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-231">The console window also displays the string entered when the console prompted for input.</span></span>

1. <span data-ttu-id="0caca-232">**디버그** > **한 단계씩 코드 실행**을 선택하거나 F11 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-232">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="0caca-233">**자동** 창에는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성에 따라 할당된 이후의 `date` 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-233">The **Autos** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="0caca-234">콘솔 창은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-234">The console window is unchanged.</span></span>

1. <span data-ttu-id="0caca-235">**디버그** > **한 단계씩 코드 실행**을 선택하거나 F11 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-235">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="0caca-236">Visual Studio에서 <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-236">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0caca-237">`date`(또는 `currentDate`) 및 `name` 변수 값이 **자동** 창에 표시되고 콘솔 창에는 서식 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-237">The values of the `date` (or `currentDate`) and `name` variables appear in the **Autos** window, and the console window displays the formatted string.</span></span>

1. <span data-ttu-id="0caca-238">**디버그** > **프로시저 나가기**를 선택하거나 Shift+F11을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-238">Select **Debug** > **Step Out** or press Shift and the F11 key.</span></span> <span data-ttu-id="0caca-239">이렇게 하면 단계별 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-239">This stops step-by-step execution.</span></span> <span data-ttu-id="0caca-240">콘솔 창은 메시지를 표시하고 사용자가 키를 누르기를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-240">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="0caca-241">아무 키나 눌러 콘솔 창을 닫고 디버그 모드를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-241">Press any key to close the console window and exit Debug mode.</span></span>
# <a name="visual-basictabvb"></a>[<span data-ttu-id="0caca-242">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0caca-242">Visual Basic</span></span>](#tab/vb)
1. <span data-ttu-id="0caca-243">메뉴 모음에서 **디버그** > **한 단계씩 코드 실행**을 선택하거나 F11 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-243">On the menu bar, choose **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="0caca-244">Visual Studio에서 다음에 실행될 줄을 강조 표시하고 옆에 화살표를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-244">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   ![Visual Studio 창](./media/debugging-with-visual-studio/vb-stepinto1.png)

   <span data-ttu-id="0caca-246">현재 프로그램에 명령줄 인수를 전달하지 않았으므로 **자동** 창에는 `args` 변수의 값이 빈 문자열 배열로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-246">At this point, because you haven't passed any command-line arguments to the program, the **Autos** window shows that the value of the `args` variable is an empty string array.</span></span> <span data-ttu-id="0caca-247">또한 Visual Studio에서는 빈 콘솔 창이 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-247">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="0caca-248">**디버그** > **한 단계씩 코드 실행**을 선택하거나 F11 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-248">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="0caca-249">이제 Visual Studio에서 다음에 실행될 줄을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-249">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="0caca-250">그림에서 볼 수 있듯이 마지막 문과 이 문 사이의 코드를 실행하는 데는 1밀리초 미만이 소요되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-250">As the figure shows, it has taken less than one millisecond to execute the code between the last statement and this one.</span></span> <span data-ttu-id="0caca-251">`args`가 선언된 유일한 변수이며 콘솔 창은 여전히 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-251">`args` remains the only declared variable, and the console window remains blank.</span></span>

   ![Visual Studio 창](./media/debugging-with-visual-studio/vb-stepinto2.png)

1. <span data-ttu-id="0caca-253">**디버그** > **한 단계씩 코드 실행**을 선택하거나 F11 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-253">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="0caca-254">Visual Studio는 `name` 변수 할당을 포함하는 문을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-254">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="0caca-255">**자동** 창에서는 `name`이 `Nothing`로 표시되고 콘솔 창에서는 문자열 "What is your name?"이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-255">The **Autos** window shows that `name` is `Nothing`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="0caca-256">콘솔 창에 문자열을 입력하고 Enter 키를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-256">Respond to the prompt by entering a string in the console window and pressing Enter.</span></span> <span data-ttu-id="0caca-257">콘솔은 응답하지 않게 되고 입력한 문자열이 콘솔 창에 표시되지 않지만 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드는 사용자의 입력을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-257">The console is unresponsive, and the string you enter isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="0caca-258">**디버그** > **한 단계씩 코드 실행**을 선택하거나 F11 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-258">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="0caca-259">Visual Studio는 `date`(C#) 또는 `currentDate`(Visual Basic) 변수 할당을 포함하는 문을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-259">Visual Studio highlights the statement that includes the `date` (in C#) or `currentDate` (in Visual Basic) variable assignment.</span></span> <span data-ttu-id="0caca-260">**자동** 창에는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성 값과 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드 호출에 의해 반환된 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-260">The **Autos** window shows the <xref:System.DateTime.Now?displayProperty=nameWithType> property value and the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0caca-261">콘솔 창에는 콘솔이 입력을 요구할 때 입력된 문자열도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-261">The console window also displays the string entered when the console prompted for input.</span></span>

1. <span data-ttu-id="0caca-262">**디버그** > **한 단계씩 코드 실행**을 선택하거나 F11 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-262">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="0caca-263">**자동** 창에는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성에 따라 할당된 이후의 `date` 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-263">The **Autos** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="0caca-264">콘솔 창은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-264">The console window is unchanged.</span></span>

1. <span data-ttu-id="0caca-265">**디버그** > **한 단계씩 코드 실행**을 선택하거나 F11 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-265">Select **Debug** > **Step Into** or press the F11 key.</span></span> <span data-ttu-id="0caca-266">Visual Studio에서 <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-266">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0caca-267">`date`(또는 `currentDate`) 및 `name` 변수 값이 **자동** 창에 표시되고 콘솔 창에는 서식 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-267">The values of the `date` (or `currentDate`) and `name` variables appear in the **Autos** window, and the console window displays the formatted string.</span></span>

1. <span data-ttu-id="0caca-268">**디버그** > **프로시저 나가기**를 선택하거나 Shift+F11을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-268">Select **Debug** > **Step Out** or press Shift and the F11 key.</span></span> <span data-ttu-id="0caca-269">이렇게 하면 단계별 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-269">This stops step-by-step execution.</span></span> <span data-ttu-id="0caca-270">콘솔 창은 메시지를 표시하고 사용자가 키를 누르기를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-270">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="0caca-271">아무 키나 눌러 콘솔 창을 닫고 디버그 모드를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-271">Press any key to close the console window and exit Debug mode.</span></span>
---

## <a name="building-a-release-version"></a><span data-ttu-id="0caca-272">릴리스 버전 빌드</span><span class="sxs-lookup"><span data-stu-id="0caca-272">Building a Release version</span></span>

<span data-ttu-id="0caca-273">응용 프로그램의 디버그 빌드를 테스트한 후에는 릴리스 버전을 컴파일하고 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-273">Once you've tested the Debug build of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="0caca-274">릴리스 버전에는 응용 프로그램의 동작에 부정적인 영향을 줄 수 있는 컴파일러 최적화가 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-274">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="0caca-275">예를 들어 성능 향상을 위해 설계된 컴파일러 최적화는 비동기 또는 다중 스레드 응용 프로그램에서 경합 상태를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-275">For example, compiler optimizations that are designed to improve performance can create race conditions in asynchronous or multithreaded applications.</span></span>

<span data-ttu-id="0caca-276">콘솔 응용 프로그램의 릴리스 버전을 빌드하고 테스트하려면 도구 모음에서 빌드 구성을 **디버그**에서 **릴리스**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-276">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

![이미지](./media/debugging-with-visual-studio/toolbar2.png)

<span data-ttu-id="0caca-278">F5 키를 누르거나 **빌드** 메뉴에서 **솔루션 빌드**를 선택하면 Visual Studio에서 콘솔 응용 프로그램의 릴리스 버전을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-278">When you press F5 or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of your console application.</span></span> <span data-ttu-id="0caca-279">응용 프로그램의 디버그 버전처럼 릴리스 버전을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-279">You can test it as you did the Debug version of the application.</span></span>

<span data-ttu-id="0caca-280">응용 프로그램 디버그를 마친 후의 다음 단계는 배포 가능한 응용 프로그램 버전을 게시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0caca-280">Once you've finished debugging your application, the next step is to publish a deployable version of your application.</span></span> <span data-ttu-id="0caca-281">이 작업을 수행하는 방법에 대한 자세한 내용은 [Visual Studio 2017을 사용하여 Hello World 응용 프로그램 게시](./publishing-with-visual-studio.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0caca-281">For information on how to do this, see [Publish the Hello World application with Visual Studio 2017](./publishing-with-visual-studio.md).</span></span>
