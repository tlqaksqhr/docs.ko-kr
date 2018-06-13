---
title: '방법: 표준 컨트롤로 키보드 입력 수정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input [Windows Forms], modifying
- modifying keyboard input
- Windows Forms, modifying keyboard input
- keyboards [Windows Forms], keyboard input
ms.assetid: 626d3712-d866-4988-bcda-a2d5b36ec0ba
ms.openlocfilehash: 726444e1decb3e03989317431e1f8c4a5fc4a697
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540292"
---
# <a name="how-to-modify-keyboard-input-to-a-standard-control"></a><span data-ttu-id="3f337-102">방법: 표준 컨트롤로 키보드 입력 수정</span><span class="sxs-lookup"><span data-stu-id="3f337-102">How to: Modify Keyboard Input to a Standard Control</span></span>
<span data-ttu-id="3f337-103">Windows Forms는 키보드 입력을 사용 및 수정할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-103">Windows Forms provides the ability to consume and modify keyboard input.</span></span> <span data-ttu-id="3f337-104">키 사용은 메시지 큐 아래의 다른 메서드 및 이벤트가 키 값을 수신하지 않도록 메서드 또는 이벤트 처리기 내에서 키를 처리하는 것을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-104">Consuming a key refers to handling a key within a method or event handler so that other methods and events further down the message queue do not receive the key value.</span></span> <span data-ttu-id="3f337-105">키 수정은 메시지 큐 아래의 메서드 및 이벤트 처리기가 다른 키 값을 수신하도록 키 값을 수정하는 것을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-105">Modifying a key refers to modifying the value of a key so that methods and event handlers further down the message queue receive a different key value.</span></span> <span data-ttu-id="3f337-106">이 항목에서는 이러한 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-106">This topic shows how to accomplish these tasks.</span></span>  
  
### <a name="to-consume-a-key"></a><span data-ttu-id="3f337-107">키를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="3f337-107">To consume a key</span></span>  
  
-   <span data-ttu-id="3f337-108"><xref:System.Windows.Forms.Control.KeyPress> 이벤트 처리기에서 <xref:System.Windows.Forms.KeyPressEventArgs> 클래스의 <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-108">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to `true`.</span></span>  
  
     <span data-ttu-id="3f337-109">또는</span><span class="sxs-lookup"><span data-stu-id="3f337-109">-or-</span></span>  
  
     <span data-ttu-id="3f337-110"><xref:System.Windows.Forms.Control.KeyDown> 이벤트 처리기에서 <xref:System.Windows.Forms.KeyEventArgs> 클래스의 <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-110">In a <xref:System.Windows.Forms.Control.KeyDown> event handler, set the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> class to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3f337-111"><xref:System.Windows.Forms.Control.KeyDown> 이벤트 처리기에서 <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> 속성을 설정해도 <xref:System.Windows.Forms.Control.KeyPress> 및 <xref:System.Windows.Forms.Control.KeyUp> 이벤트가 현재 키 입력에 대해 발생하지 않도록 차단되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-111">Setting the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property in the <xref:System.Windows.Forms.Control.KeyDown> event handler does not prevent the <xref:System.Windows.Forms.Control.KeyPress> and <xref:System.Windows.Forms.Control.KeyUp> events from being raised for the current keystroke.</span></span> <span data-ttu-id="3f337-112">이렇게 하려면 <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-112">Use the <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> property for this purpose.</span></span>  
  
     <span data-ttu-id="3f337-113">다음 예제는 <xref:System.Windows.Forms.Control.KeyPress> 이벤트 처리기가 수신한 <xref:System.Windows.Forms.KeyPressEventArgs>의 <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> 속성을 검사하는 `switch` 문에서 발췌한 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-113">The following example is an excerpt from a `switch` statement that examines the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> received by a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span> <span data-ttu-id="3f337-114">이 코드는 'A' 및 'a' 문자 키를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-114">This code consumes the 'A' and 'a' character keys.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#6)]  
  
### <a name="to-modify-a-standard-character-key"></a><span data-ttu-id="3f337-115">표준 문자 키를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="3f337-115">To modify a standard character key</span></span>  
  
-   <span data-ttu-id="3f337-116"><xref:System.Windows.Forms.Control.KeyPress> 이벤트 처리기에서 <xref:System.Windows.Forms.KeyPressEventArgs> 클래스의 <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> 속성을 새 문자 키의 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-116">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to the value of the new character key.</span></span>  
  
     <span data-ttu-id="3f337-117">다음 예제는 'B'를 'A’로 수정하고 'b'를 'a'로 수정하는 `switch` 문에서 발췌한 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-117">The following example is an excerpt from a `switch` statement that modifies 'B' to 'A' and 'b' to 'a'.</span></span> <span data-ttu-id="3f337-118">새로운 키 값이 메시지 큐의 다른 메서드 및 이벤트에 전파되도록 <xref:System.Windows.Forms.KeyPressEventArgs> 매개 변수의 <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> 속성은 `false`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-118">Note that the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> parameter is set to `false`, so that the new key value is propagated to other methods and events in the message queue.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#7)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#7)]  
  
### <a name="to-modify-a-noncharacter-key"></a><span data-ttu-id="3f337-119">문자가 아닌 키를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="3f337-119">To modify a noncharacter key</span></span>  
  
-   <span data-ttu-id="3f337-120">Windows 메시지를 처리하는 <xref:System.Windows.Forms.Control> 메서드를 재정의하고, WM_KEYDOWN 또는 WM_SYSKEYDOWN 메시지를 검색하고, <xref:System.Windows.Forms.Message> 매개 변수의 <xref:System.Windows.Forms.Message.WParam%2A> 속성을 문자가 아닌 새 키를 나타내는 <xref:System.Windows.Forms.Keys> 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-120">Override a <xref:System.Windows.Forms.Control> method that processes Windows messages, detect the WM_KEYDOWN or WM_SYSKEYDOWN message, and set the <xref:System.Windows.Forms.Message.WParam%2A> property of the <xref:System.Windows.Forms.Message> parameter to the <xref:System.Windows.Forms.Keys> value that represents the new noncharacter key.</span></span>  
  
     <span data-ttu-id="3f337-121">다음 코드 예제에서는 컨트롤의 <xref:System.Windows.Forms.Control.PreProcessMessage%2A> 메서드를 재정의하여 F1-F9 키를 검색하고 F3 키 누름을 F1로 수정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-121">The following code example demonstrates how to override the <xref:System.Windows.Forms.Control.PreProcessMessage%2A> method of a control to detect keys F1 through F9 and modify any F3 key press to F1.</span></span> <span data-ttu-id="3f337-122">대 한 자세한 내용은 <xref:System.Windows.Forms.Control> 키보드 메시지를 가로채기 위해 재정의할 수 있는 메서드 참조 [Windows Forms 응용 프로그램에서 사용자 입력](../../../docs/framework/winforms/user-input-in-a-windows-forms-application.md) 및 [키보드 입력 작동 방식](../../../docs/framework/winforms/how-keyboard-input-works.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-122">For more information on <xref:System.Windows.Forms.Control> methods that you can override to intercept keyboard messages, see [User Input in a Windows Forms Application](../../../docs/framework/winforms/user-input-in-a-windows-forms-application.md) and [How Keyboard Input Works](../../../docs/framework/winforms/how-keyboard-input-works.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#12](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#12](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="3f337-123">예제</span><span class="sxs-lookup"><span data-stu-id="3f337-123">Example</span></span>  
 <span data-ttu-id="3f337-124">다음 코드 예제는 이전 섹션의 코드 예제에 대한 전체 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-124">The following code example is the complete application for the code examples in the previous sections.</span></span> <span data-ttu-id="3f337-125">응용 프로그램은 <xref:System.Windows.Forms.TextBox> 클래스에서 파생된 사용자 지정 컨트롤을 통해 키보드 입력을 사용 및 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-125">The application uses a custom control derived from the <xref:System.Windows.Forms.TextBox> class to consume and modify keyboard input.</span></span>  
  
 [!code-csharp[System.Windows.Forms.KeyBoardInput#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInput#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3f337-126">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3f337-126">Compiling the Code</span></span>  
 <span data-ttu-id="3f337-127">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-127">This example requires:</span></span>  
  
-   <span data-ttu-id="3f337-128">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="3f337-128">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="3f337-129">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-129">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="3f337-130">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f337-130">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="3f337-131">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f337-131">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f337-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f337-132">See Also</span></span>  
 [<span data-ttu-id="3f337-133">Windows Forms 응용 프로그램의 키보드 입력</span><span class="sxs-lookup"><span data-stu-id="3f337-133">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [<span data-ttu-id="3f337-134">Windows Forms 응용 프로그램의 사용자 입력</span><span class="sxs-lookup"><span data-stu-id="3f337-134">User Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/user-input-in-a-windows-forms-application.md)  
 [<span data-ttu-id="3f337-135">키보드 입력 작동 방식</span><span class="sxs-lookup"><span data-stu-id="3f337-135">How Keyboard Input Works</span></span>](../../../docs/framework/winforms/how-keyboard-input-works.md)
