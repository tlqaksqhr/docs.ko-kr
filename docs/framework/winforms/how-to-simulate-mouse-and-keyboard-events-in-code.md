---
title: "방법: 코드에서 마우스 및 키보드 이벤트 시뮬레이션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboards [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
- mouse clicks [Windows Forms], simulating
- mouse [Windows Forms], event simulation
ms.assetid: 6abcb67e-3766-4af2-9590-bf5dabd17e41
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5b764533b845ddf1585c9b3de9eb6283ec5ec6ea
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-simulate-mouse-and-keyboard-events-in-code"></a><span data-ttu-id="7a4ce-102">방법: 코드에서 마우스 및 키보드 이벤트 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="7a4ce-102">How to: Simulate Mouse and Keyboard Events in Code</span></span>
<span data-ttu-id="7a4ce-103">Windows Forms는 프로그래밍 방식으로 마우스 및 키보드 입력을 시뮬레이션하기 위한 여러 가지 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-103">Windows Forms provides several options for programmatically simulating mouse and keyboard input.</span></span> <span data-ttu-id="7a4ce-104">이 항목에서는 이러한 옵션에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-104">This topic provides an overview of these options.</span></span>  
  
## <a name="simulating-mouse-input"></a><span data-ttu-id="7a4ce-105">마우스 입력 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="7a4ce-105">Simulating Mouse Input</span></span>  
 <span data-ttu-id="7a4ce-106">마우스 이벤트를 시뮬레이션하는 가장 좋은 방법은 시뮬레이션하려는 마우스 이벤트를 발생시키는 `On`*EventName* 메서드를 호출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-106">The best way to simulate mouse events is to call the `On`*EventName* method that raises the mouse event you want to simulate.</span></span> <span data-ttu-id="7a4ce-107">이벤트를 발생시키는 메서드는 보호되며 컨트롤이나 폼 외부에서 액세스할 수 없기 때문에 이 옵션은 일반적으로 사용자 지정 컨트롤 및 폼 내에서만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-107">This option is usually possible only within custom controls and forms, because the methods that raise events are protected and cannot be accessed outside the control or form.</span></span> <span data-ttu-id="7a4ce-108">예를 들어 다음 단계에서는 코드에서 마우스 오른쪽 단추를 클릭하여 시뮬레이션하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-108">For example, the following steps illustrate how to simulate clicking the right mouse button in code.</span></span>  
  
#### <a name="to-programmatically-click-the-right-mouse-button"></a><span data-ttu-id="7a4ce-109">프로그래밍 방식으로 마우스 오른쪽 단추를 클릭하려면</span><span class="sxs-lookup"><span data-stu-id="7a4ce-109">To programmatically click the right mouse button</span></span>  
  
1.  <span data-ttu-id="7a4ce-110"><xref:System.Windows.Forms.MouseEventArgs.Button%2A> 속성이 <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> 값으로 설정된 <xref:System.Windows.Forms.MouseEventArgs>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-110">Create a <xref:System.Windows.Forms.MouseEventArgs> whose <xref:System.Windows.Forms.MouseEventArgs.Button%2A> property is set to the <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> value.</span></span>  
  
2.  <span data-ttu-id="7a4ce-111">이 <xref:System.Windows.Forms.Control.OnMouseClick%2A> 를 인수로 사용하여 <xref:System.Windows.Forms.MouseEventArgs> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-111">Call the <xref:System.Windows.Forms.Control.OnMouseClick%2A> method with this <xref:System.Windows.Forms.MouseEventArgs> as the argument.</span></span>  
  
 <span data-ttu-id="7a4ce-112">사용자 지정 컨트롤에 대한 자세한 내용은 [디자인 타임에 Windows Forms 컨트롤 개발](../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-112">For more information on custom controls, see [Developing Windows Forms Controls at Design Time](../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span>  
  
 <span data-ttu-id="7a4ce-113">마우스 입력을 시뮬레이션하는 다른 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-113">There are other ways to simulate mouse input.</span></span> <span data-ttu-id="7a4ce-114">예를 들어 일반적으로 마우스 입력을 통해 설정되는 상태를 나타내는 컨트롤 속성(예: <xref:System.Windows.Forms.CheckBox.Checked%2A> 컨트롤의 <xref:System.Windows.Forms.CheckBox> 속성)을 프로그래밍 방식으로 설정하거나 시뮬레이션하려는 이벤트에 연결된 대리자를 직접 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-114">For example, you can programmatically set a control property that represents a state that is typically set through mouse input (such as the <xref:System.Windows.Forms.CheckBox.Checked%2A> property of the <xref:System.Windows.Forms.CheckBox> control), or you can directly call the delegate that is attached to the event you want to simulate.</span></span>  
  
## <a name="simulating-keyboard-input"></a><span data-ttu-id="7a4ce-115">키보드 입력 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="7a4ce-115">Simulating Keyboard Input</span></span>  
 <span data-ttu-id="7a4ce-116">마우스 입력에 대해 위에서 설명한 전략을 사용하여 키보드 입력을 시뮬레이션할 수도 있지만 Windows Forms에서는 활성 응용 프로그램에 키 입력을 전송하기 위한 <xref:System.Windows.Forms.SendKeys> 클래스도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-116">Although you can simulate keyboard input by using the strategies discussed above for mouse input, Windows Forms also provides the <xref:System.Windows.Forms.SendKeys> class for sending keystrokes to the active application.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7a4ce-117">다양한 키보드를 통해 전 세계에서 사용하기 위한 응용 프로그램인 경우 <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType>를 사용하면 예기치 않은 결과가 발생할 수 있으며 피해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-117">If your application is intended for international use with a variety of keyboards, the use of <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> could yield unpredictable results and should be avoided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a4ce-118"><xref:System.Windows.Forms.SendKeys> 클래스는 Windows Vista에서 실행되는 응용 프로그램에서 사용할 수 있도록 .NET Framework 3.0에서 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-118">The <xref:System.Windows.Forms.SendKeys> class has been updated for the .NET Framework 3.0 to enable its use in applications that run on Windows Vista.</span></span> <span data-ttu-id="7a4ce-119">Windows Vista의 향상된 보안(사용자 계정 컨트롤 또는 UAC라고 함) 때문에 이전 구현이 예상대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-119">The enhanced security of Windows Vista (known as User Account Control or UAC) prevents the previous implementation from working as expected.</span></span>  
>   
>  <span data-ttu-id="7a4ce-120"><xref:System.Windows.Forms.SendKeys> 클래스는 타이밍 문제에 취약하며, 이를 해결하기 위해 일부 개발자가 노력해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-120">The <xref:System.Windows.Forms.SendKeys> class is susceptible to timing issues, which some developers have had to work around.</span></span> <span data-ttu-id="7a4ce-121">업데이트된 구현도 타이밍 문제에 취약하지만 약간 더 빠르며 해결 방법에 대한 변경이 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-121">The updated implementation is still susceptible to timing issues, but is slightly faster and may require changes to the workarounds.</span></span> <span data-ttu-id="7a4ce-122"><xref:System.Windows.Forms.SendKeys> 클래스는 먼저 이전 구현을 사용하려고 시도하며, 실패할 경우 새 구현을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-122">The <xref:System.Windows.Forms.SendKeys> class tries to use the previous implementation first, and if that fails, uses the new implementation.</span></span> <span data-ttu-id="7a4ce-123">따라서 <xref:System.Windows.Forms.SendKeys> 클래스는 운영 체제마다 다르게 동작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-123">As a result, the <xref:System.Windows.Forms.SendKeys> class may behave differently on different operating systems.</span></span> <span data-ttu-id="7a4ce-124">또한 <xref:System.Windows.Forms.SendKeys> 클래스가 새 구현을 사용하는 경우 <xref:System.Windows.Forms.SendKeys.SendWait%2A> 메서드는 다른 프로세스로 전송된 메시지가 처리될 때까지 기다리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-124">Additionally, when the <xref:System.Windows.Forms.SendKeys> class uses the new implementation, the <xref:System.Windows.Forms.SendKeys.SendWait%2A> method will not wait for messages to be processed when they are sent to another process.</span></span>  
>   
>  <span data-ttu-id="7a4ce-125">응용 프로그램이 운영 체제와 관계없이 일관된 동작에 의존하는 경우 app.config 파일에 다음 응용 프로그램 설정을 추가하여 <xref:System.Windows.Forms.SendKeys> 클래스에서 새 구현을 사용하도록 강제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-125">If your application relies on consistent behavior regardless of the operating system, you can force the <xref:System.Windows.Forms.SendKeys> class to use the new implementation by adding the following application setting to your app.config file.</span></span>  
>   
>  `<appSettings>`  
>   
>  `<add key="SendKeys" value="SendInput"/>`  
>   
>  `</appSettings>`  
>   
>  <span data-ttu-id="7a4ce-126"><xref:System.Windows.Forms.SendKeys> 클래스에서 이전 구현을 사용하도록 강제하려면 `"JournalHook"` 값을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-126">To force the <xref:System.Windows.Forms.SendKeys> class to use the previous implementation, use the value `"JournalHook"` instead.</span></span>  
  
#### <a name="to-send-a-keystroke-to-the-same-application"></a><span data-ttu-id="7a4ce-127">동일한 응용 프로그램에 키 입력을 보내려면</span><span class="sxs-lookup"><span data-stu-id="7a4ce-127">To send a keystroke to the same application</span></span>  
  
1.  <span data-ttu-id="7a4ce-128"><xref:System.Windows.Forms.SendKeys.Send%2A> 클래스의 <xref:System.Windows.Forms.SendKeys.SendWait%2A> 또는 <xref:System.Windows.Forms.SendKeys> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-128">Call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method of the <xref:System.Windows.Forms.SendKeys> class.</span></span> <span data-ttu-id="7a4ce-129">응용 프로그램의 활성 컨트롤이 지정된 키 입력을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-129">The specified keystrokes will be received by the active control of the application.</span></span> <span data-ttu-id="7a4ce-130">다음 코드 예제에서는 <xref:System.Windows.Forms.SendKeys.Send%2A> 를 사용하여 사용자가 폼의 화면을 두 번 클릭할 때 Enter 키 누름을 시뮬레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-130">The following code example uses <xref:System.Windows.Forms.SendKeys.Send%2A> to simulate pressing the ENTER key when the user double-clicks the surface of the form.</span></span> <span data-ttu-id="7a4ce-131">이 예제에서는 탭 인덱스가 0인 단일 <xref:System.Windows.Forms.Form> 컨트롤이 있는 <xref:System.Windows.Forms.Button> 을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-131">This example assumes a <xref:System.Windows.Forms.Form> with a single <xref:System.Windows.Forms.Button> control that has a tab index of 0.</span></span>  
  
     [!code-cpp[System.Windows.Forms.SimulateKeyPress#10](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#10)]
     [!code-csharp[System.Windows.Forms.SimulateKeyPress#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#10)]
     [!code-vb[System.Windows.Forms.SimulateKeyPress#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#10)]  
  
#### <a name="to-send-a-keystroke-to-a-different-application"></a><span data-ttu-id="7a4ce-132">다른 응용 프로그램에 키 입력을 보내려면</span><span class="sxs-lookup"><span data-stu-id="7a4ce-132">To send a keystroke to a different application</span></span>  
  
1.  <span data-ttu-id="7a4ce-133">키 입력을 수신할 응용 프로그램 창을 활성화한 다음 <xref:System.Windows.Forms.SendKeys.Send%2A> 또는 <xref:System.Windows.Forms.SendKeys.SendWait%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-133">Activate the application window that will receive the keystrokes, and then call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method.</span></span> <span data-ttu-id="7a4ce-134">다른 응용 프로그램을 활성화할 관리되는 메서드가 없으므로 네이티브 Windows 메서드를 사용하여 다른 응용 프로그램에 포커스를 강제로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-134">Because there is no managed method to activate another application, you must use native Windows methods to force focus on other applications.</span></span> <span data-ttu-id="7a4ce-135">다음 코드 예제에서는 플랫폼 호출을 통해 `FindWindow` 및 `SetForegroundWindow` 메서드를 호출하여 계산기 응용 프로그램 창을 활성화한 다음 <xref:System.Windows.Forms.SendKeys.SendWait%2A> 를 호출하여 계산기 응용 프로그램에 일련의 계산을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-135">The following code example uses platform invoke to call the `FindWindow` and `SetForegroundWindow` methods to activate the Calculator application window, and then calls <xref:System.Windows.Forms.SendKeys.SendWait%2A> to issue a series of calculations to the Calculator application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a4ce-136">계산기 응용 프로그램을 찾는 `FindWindow` 호출의 올바른 매개 변수는 Windows 버전에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-136">The correct parameters of the `FindWindow` call that locates the Calculator application vary based on your version of Windows.</span></span>  <span data-ttu-id="7a4ce-137">다음 코드에서는 [!INCLUDE[win7](../../../includes/win7-md.md)]에서 계산기 응용 프로그램을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-137">The following code finds the Calculator application on [!INCLUDE[win7](../../../includes/win7-md.md)].</span></span> <span data-ttu-id="7a4ce-138">[!INCLUDE[windowsver](../../../includes/windowsver-md.md)]에서 첫 번째 매개 변수를 "SciCalc"로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-138">On [!INCLUDE[windowsver](../../../includes/windowsver-md.md)], change the first parameter to "SciCalc".</span></span> <span data-ttu-id="7a4ce-139">Visual Studio에 포함된 Spy++ 도구를 사용하여 올바른 매개 변수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-139">You can use the Spy++ tool, included with Visual Studio, to determine the correct parameters.</span></span>  
  
     [!code-cpp[System.Windows.Forms.SimulateKeyPress#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.SimulateKeyPress#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.SimulateKeyPress#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="7a4ce-140">예제</span><span class="sxs-lookup"><span data-stu-id="7a4ce-140">Example</span></span>  
 <span data-ttu-id="7a4ce-141">다음 코드 예제는 이전 코드 예제에 대한 전체 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-141">The following code example is the complete application for the previous code examples.</span></span>  
  
 [!code-cpp[System.Windows.Forms.SimulateKeyPress#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.SimulateKeyPress#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.SimulateKeyPress#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7a4ce-142">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7a4ce-142">Compiling the Code</span></span>  
 <span data-ttu-id="7a4ce-143">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-143">This example requires:</span></span>  
  
-   <span data-ttu-id="7a4ce-144">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="7a4ce-144">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="7a4ce-145">[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-145">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="7a4ce-146">[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-146">You can also build this example in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="7a4ce-147">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a4ce-147">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a4ce-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a4ce-148">See Also</span></span>  
 [<span data-ttu-id="7a4ce-149">Windows Forms에 사용자 입력</span><span class="sxs-lookup"><span data-stu-id="7a4ce-149">User Input in Windows Forms</span></span>](../../../docs/framework/winforms/user-input-in-windows-forms.md)
