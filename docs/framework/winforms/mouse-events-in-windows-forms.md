---
title: "Windows Forms의 마우스 이벤트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MouseLeave event [Windows Forms]
- events [Windows Forms], mouse
- Click event [Windows Forms], raising order
- Windows Forms controls, click events
- MouseDoubleClick event [Windows Forms]
- MouseEnter event [Windows Forms]
- MouseHover event [Windows Forms]
- MouseDown event [Windows Forms]
- MouseClick event [Windows Forms]
- MouseMove event [Windows Forms]
- mouse [Windows Forms], events
- MouseUp event
ms.assetid: 8cf0070d-793b-4876-b09e-d20d28280fab
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 803f2daab5b8f6e216effe4a9ae9f34752d24e70
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="mouse-events-in-windows-forms"></a><span data-ttu-id="f67c3-102">Windows Forms의 마우스 이벤트</span><span class="sxs-lookup"><span data-stu-id="f67c3-102">Mouse Events in Windows Forms</span></span>
<span data-ttu-id="f67c3-103">마우스 입력을 처리하는 경우 일반적으로 마우스 포인터의 위치와 마우스 단추의 상태를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-103">When you handle mouse input, you usually want to know the location of the mouse pointer and the state of the mouse buttons.</span></span> <span data-ttu-id="f67c3-104">이 항목에서는 마우스 이벤트에서 이 정보를 가져오는 방법을 자세히 설명하고 Windows Forms 컨트롤에서 마우스 클릭 이벤트가 발생하는 순서를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-104">This topic provides details on how to get this information from mouse events, and explains the order in which mouse click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="f67c3-105">목록 및 모든 마우스 이벤트의 설명에 대 한 참조 [Windows Forms의 마우스 입력 방법](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-105">For a list and description of all of the mouse events, see [How Mouse Input Works in Windows Forms](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md).</span></span>  <span data-ttu-id="f67c3-106">또한 참조 [이벤트 처리기 개요 (Windows Forms)](http://msdn.microsoft.com/library/be6fx1bb\(v=vs.110\)), [이벤트 개요 (Windows Forms)](http://msdn.microsoft.com/library/1h12f09z\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="f67c3-106">Also see [Event Handlers Overview (Windows Forms)](http://msdn.microsoft.com/library/be6fx1bb\(v=vs.110\)), [Events Overview (Windows Forms)](http://msdn.microsoft.com/library/1h12f09z\(v=vs.110\))</span></span>  
  
## <a name="mouse-information"></a><span data-ttu-id="f67c3-107">마우스 정보</span><span class="sxs-lookup"><span data-stu-id="f67c3-107">Mouse Information</span></span>  
 <span data-ttu-id="f67c3-108"><xref:System.Windows.Forms.MouseEventArgs>는 마우스 단추 클릭 및 마우스 움직임 추적과 관련된 마우스 이벤트 처리기로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-108">A <xref:System.Windows.Forms.MouseEventArgs> is sent to the handlers of mouse events related to clicking a mouse button and tracking mouse movements.</span></span> <span data-ttu-id="f67c3-109"><xref:System.Windows.Forms.MouseEventArgs>는 클라이언트 좌표에서 마우스 포인터의 위치, 누른 마우스 단추, 마우스 휠의 스크롤 여부를 포함하여 마우스의 현재 상태에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-109"><xref:System.Windows.Forms.MouseEventArgs> provides information about the current state of the mouse, including the location of the mouse pointer in client coordinates, which mouse buttons are pressed, and whether the mouse wheel has scrolled.</span></span> <span data-ttu-id="f67c3-110">마우스 포인터가 컨트롤의 범위로 들어오거나 나갈 때 단순히 알리는 이벤트와 같은 여러 마우스 이벤트가 추가 정보 없이 <xref:System.EventArgs>를 이벤트 처리기로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-110">Several mouse events, such as those that simply notify when the mouse pointer has entered or left the bounds of a control, send an <xref:System.EventArgs> to the event handler with no further information.</span></span>  
  
 <span data-ttu-id="f67c3-111">마우스 이벤트를 처리하지 않고 마우스 단추의 현재 상태나 마우스 포인터의 위치를 확인하려는 경우 <xref:System.Windows.Forms.Control> 클래스의 <xref:System.Windows.Forms.Control.MouseButtons%2A> 및 <xref:System.Windows.Forms.Control.MousePosition%2A> 속성을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-111">If you want to know the current state of the mouse buttons or the location of the mouse pointer, and you want to avoid handling a mouse event, you can also use the <xref:System.Windows.Forms.Control.MouseButtons%2A> and <xref:System.Windows.Forms.Control.MousePosition%2A> properties of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="f67c3-112"><xref:System.Windows.Forms.Control.MouseButtons%2A>는 현재 누른 마우스 단추에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-112"><xref:System.Windows.Forms.Control.MouseButtons%2A> returns information about which mouse buttons are currently pressed.</span></span> <span data-ttu-id="f67c3-113"><xref:System.Windows.Forms.Control.MousePosition%2A>은 마우스 포인터의 화면 좌표를 반환하며 <xref:System.Windows.Forms.Cursor.Position%2A>에서 반환되는 값과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-113">The <xref:System.Windows.Forms.Control.MousePosition%2A> returns the screen coordinates of the mouse pointer and is equivalent to the value returned by <xref:System.Windows.Forms.Cursor.Position%2A>.</span></span>  
  
## <a name="converting-between-screen-and-client-coordinates"></a><span data-ttu-id="f67c3-114">화면 좌표와 클라이언트 좌표 간의 변환</span><span class="sxs-lookup"><span data-stu-id="f67c3-114">Converting Between Screen and Client Coordinates</span></span>  
 <span data-ttu-id="f67c3-115">일부 마우스 위치 정보는 클라이언트 좌표로 표시되고 일부 정보는 화면 좌표로 표시되므로 좌표계 간에 지점을 변환해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-115">Because some mouse location information is in client coordinates and some is in screen coordinates, you may need to convert a point from one coordinate system to the other.</span></span> <span data-ttu-id="f67c3-116"><xref:System.Windows.Forms.Control> 클래스에서 사용할 수 있는 <xref:System.Windows.Forms.Control.PointToClient%2A> 및 <xref:System.Windows.Forms.Control.PointToScreen%2A> 메서드를 사용하면 이 작업을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-116">You can do this easily by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available on the <xref:System.Windows.Forms.Control> class.</span></span>  
  
## <a name="standard-click-event-behavior"></a><span data-ttu-id="f67c3-117">표준 클릭 이벤트 동작</span><span class="sxs-lookup"><span data-stu-id="f67c3-117">Standard Click Event Behavior</span></span>  
 <span data-ttu-id="f67c3-118">마우스 클릭 이벤트를 적절한 순서로 처리하려는 경우 Windows Forms 컨트롤에서 클릭 이벤트가 발생하는 순서를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-118">If you want to handle mouse click events in the proper order, you need to know the order in which click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="f67c3-119">개별 컨트롤에 대한 다음 목록에 명시된 경우를 제외하고 모든 Windows Forms 컨트롤은 어떤 마우스 단추인지에 관계없이 마우스 단추를 눌렀다 놓는 순서대로 클릭 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-119">All Windows Forms controls raise click events in the same order when a mouse button is pressed and released (regardless of which mouse button), except where noted in the following list for individual controls.</span></span> <span data-ttu-id="f67c3-120">다음 목록에서는 마우스 단추 한 번 클릭에 대해 발생하는 이벤트 순서를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-120">The following list shows the order of events raised for a single mouse-button click:</span></span>  
  
1.  <span data-ttu-id="f67c3-121"><xref:System.Windows.Forms.Control.MouseDown> 이벤트</span><span class="sxs-lookup"><span data-stu-id="f67c3-121"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
2.  <span data-ttu-id="f67c3-122"><xref:System.Windows.Forms.Control.Click> 이벤트</span><span class="sxs-lookup"><span data-stu-id="f67c3-122"><xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
3.  <span data-ttu-id="f67c3-123"><xref:System.Windows.Forms.Control.MouseClick> 이벤트</span><span class="sxs-lookup"><span data-stu-id="f67c3-123"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>  
  
4.  <span data-ttu-id="f67c3-124"><xref:System.Windows.Forms.Control.MouseUp> 이벤트</span><span class="sxs-lookup"><span data-stu-id="f67c3-124"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
 <span data-ttu-id="f67c3-125">다음은 마우스 단추 두 번 클릭에 대해 발생하는 이벤트 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-125">Following is the order of events raised for a double mouse-button click:</span></span>  
  
1.  <span data-ttu-id="f67c3-126"><xref:System.Windows.Forms.Control.MouseDown> 이벤트</span><span class="sxs-lookup"><span data-stu-id="f67c3-126"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
2.  <span data-ttu-id="f67c3-127"><xref:System.Windows.Forms.Control.Click> 이벤트</span><span class="sxs-lookup"><span data-stu-id="f67c3-127"><xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
3.  <span data-ttu-id="f67c3-128"><xref:System.Windows.Forms.Control.MouseClick> 이벤트</span><span class="sxs-lookup"><span data-stu-id="f67c3-128"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>  
  
4.  <span data-ttu-id="f67c3-129"><xref:System.Windows.Forms.Control.MouseUp> 이벤트</span><span class="sxs-lookup"><span data-stu-id="f67c3-129"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
5.  <span data-ttu-id="f67c3-130"><xref:System.Windows.Forms.Control.MouseDown> 이벤트</span><span class="sxs-lookup"><span data-stu-id="f67c3-130"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
6.  <span data-ttu-id="f67c3-131"><xref:System.Windows.Forms.Control.DoubleClick> 이벤트</span><span class="sxs-lookup"><span data-stu-id="f67c3-131"><xref:System.Windows.Forms.Control.DoubleClick> event.</span></span> <span data-ttu-id="f67c3-132">해당 컨트롤에 대한 <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> 스타일 비트가 `true`로 설정되었는지 여부에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-132">(This can vary, depending on whether the control in question has the <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> style bit set to `true`.</span></span> <span data-ttu-id="f67c3-133"><xref:System.Windows.Forms.ControlStyles>를 설정하는 방법에 대한 자세한 내용은 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f67c3-133">For more information about how to set a <xref:System.Windows.Forms.ControlStyles> bit, see the <xref:System.Windows.Forms.Control.SetStyle%2A> method.)</span></span>  
  
7.  <span data-ttu-id="f67c3-134"><xref:System.Windows.Forms.Control.MouseDoubleClick> 이벤트</span><span class="sxs-lookup"><span data-stu-id="f67c3-134"><xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span>  
  
8.  <span data-ttu-id="f67c3-135"><xref:System.Windows.Forms.Control.MouseUp> 이벤트</span><span class="sxs-lookup"><span data-stu-id="f67c3-135"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
 <span data-ttu-id="f67c3-136">마우스의 순서를 보여 주는 코드 예제에 대 한 click 이벤트를 참조 하십시오 [하는 방법: Windows Forms 컨트롤에서 사용자 입력 이벤트 처리](../../../docs/framework/winforms/how-to-handle-user-input-events-in-windows-forms-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-136">For a code example that demonstrates the order of the mouse click events, see [How to: Handle User Input Events in Windows Forms Controls](../../../docs/framework/winforms/how-to-handle-user-input-events-in-windows-forms-controls.md).</span></span>  
  
### <a name="individual-controls"></a><span data-ttu-id="f67c3-137">개별 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f67c3-137">Individual Controls</span></span>  
 <span data-ttu-id="f67c3-138">다음 컨트롤은 표준 마우스 클릭 이벤트 동작을 준수하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-138">The following controls do not conform to the standard mouse click event behavior:</span></span>  
  
-   <span data-ttu-id="f67c3-139"><xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.ComboBox> 및 <xref:System.Windows.Forms.RadioButton> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f67c3-139"><xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.ComboBox>, and <xref:System.Windows.Forms.RadioButton> controls</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f67c3-140"><xref:System.Windows.Forms.ComboBox> 컨트롤의 경우 사용자가 편집 필드, 단추 또는 목록 내의 항목을 클릭하면 나중에 자세히 설명하는 이벤트 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-140">For the <xref:System.Windows.Forms.ComboBox> control, the event behavior detailed later occurs if the user clicks on the edit field, the button, or on an item within the list.</span></span>  
  
    -   <span data-ttu-id="f67c3-141">마우스 왼쪽 단추 클릭: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="f67c3-141">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>  
  
    -   <span data-ttu-id="f67c3-142">마우스 오른쪽 단추 클릭: 클릭 이벤트가 발생하지 않음</span><span class="sxs-lookup"><span data-stu-id="f67c3-142">Right click: No click events raised</span></span>  
  
    -   <span data-ttu-id="f67c3-143">마우스 왼쪽 단추 두 번 클릭: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="f67c3-143">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>  
  
    -   <span data-ttu-id="f67c3-144">마우스 오른쪽 단추 두 번 클릭: 클릭 이벤트가 발생하지 않음</span><span class="sxs-lookup"><span data-stu-id="f67c3-144">Right double-click: No click events raised</span></span>  
  
-   <span data-ttu-id="f67c3-145"><xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox>및 <xref:System.Windows.Forms.CheckedListBox> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f67c3-145"><xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox>, and <xref:System.Windows.Forms.CheckedListBox> controls</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f67c3-146">사용자가 이러한 컨트롤 내의 아무 곳이나 클릭하면 나중에 자세히 설명하는 이벤트 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-146">The event behavior detailed later occurs when the user clicks anywhere within these controls.</span></span>  
  
    -   <span data-ttu-id="f67c3-147">마우스 왼쪽 단추 클릭: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="f67c3-147">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>  
  
    -   <span data-ttu-id="f67c3-148">마우스 오른쪽 단추 클릭: 클릭 이벤트가 발생하지 않음</span><span class="sxs-lookup"><span data-stu-id="f67c3-148">Right click: No click events raised</span></span>  
  
    -   <span data-ttu-id="f67c3-149">마우스 왼쪽 단추 두 번 클릭: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="f67c3-149">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>  
  
    -   <span data-ttu-id="f67c3-150">마우스 오른쪽 단추 두 번 클릭: 클릭 이벤트가 발생하지 않음</span><span class="sxs-lookup"><span data-stu-id="f67c3-150">Right double-click: No click events raised</span></span>  
  
-   <span data-ttu-id="f67c3-151"><xref:System.Windows.Forms.ListView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f67c3-151"><xref:System.Windows.Forms.ListView> control</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f67c3-152">사용자가 <xref:System.Windows.Forms.ListView> 컨트롤의 항목을 클릭하는 경우에만 나중에 자세히 설명하는 이벤트 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-152">The event behavior detailed later occurs only when the user clicks on the items in the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="f67c3-153">컨트롤의 다른 곳을 클릭하면 이벤트가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-153">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="f67c3-154">나중에 설명하는 이벤트 외에도 <xref:System.Windows.Forms.ListView> 컨트롤에 유효성 검사를 사용하려는 경우 중요할 수 있는 <xref:System.Windows.Forms.ListView.BeforeLabelEdit> 및 <xref:System.Windows.Forms.ListView.AfterLabelEdit> 이벤트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-154">In addition to the events described later, there are the <xref:System.Windows.Forms.ListView.BeforeLabelEdit> and <xref:System.Windows.Forms.ListView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
    -   <span data-ttu-id="f67c3-155">마우스 왼쪽 단추 클릭: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="f67c3-155">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>  
  
    -   <span data-ttu-id="f67c3-156">마우스 오른쪽 단추 클릭: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="f67c3-156">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>  
  
    -   <span data-ttu-id="f67c3-157">마우스 왼쪽 단추 두 번 클릭: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="f67c3-157">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>  
  
    -   <span data-ttu-id="f67c3-158">마우스 오른쪽 단추 두 번 클릭: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="f67c3-158">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>  
  
-   <span data-ttu-id="f67c3-159"><xref:System.Windows.Forms.TreeView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f67c3-159"><xref:System.Windows.Forms.TreeView> control</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f67c3-160">사용자가 <xref:System.Windows.Forms.TreeView> 컨트롤에서 항목 자체나 항목 오른쪽을 클릭하는 경우에만 나중에 자세히 설명하는 이벤트 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-160">The event behavior detailed later occurs only when the user clicks on the items themselves or to the right of the items in the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="f67c3-161">컨트롤의 다른 곳을 클릭하면 이벤트가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-161">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="f67c3-162">나중에 설명하는 이벤트 외에도 <xref:System.Windows.Forms.TreeView> 컨트롤에 유효성 검사를 사용하려는 경우 중요할 수 있는 <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck> 및 <xref:System.Windows.Forms.TreeView.AfterLabelEdit> 이벤트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-162">In addition to those described later, there are the <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck>, and <xref:System.Windows.Forms.TreeView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.TreeView> control.</span></span>  
  
    -   <span data-ttu-id="f67c3-163">마우스 왼쪽 단추 클릭: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="f67c3-163">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>  
  
    -   <span data-ttu-id="f67c3-164">마우스 오른쪽 단추 클릭: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="f67c3-164">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>  
  
    -   <span data-ttu-id="f67c3-165">마우스 왼쪽 단추 두 번 클릭: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="f67c3-165">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>  
  
    -   <span data-ttu-id="f67c3-166">마우스 오른쪽 단추 두 번 클릭: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="f67c3-166">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>  
  
### <a name="painting-behavior-of-toggle-controls"></a><span data-ttu-id="f67c3-167">토글 컨트롤의 그리기 동작</span><span class="sxs-lookup"><span data-stu-id="f67c3-167">Painting Behavior of Toggle Controls</span></span>  
 <span data-ttu-id="f67c3-168"><xref:System.Windows.Forms.ButtonBase> 클래스에서 파생되는 컨트롤과 같은 토글 컨트롤은 마우스 클릭 이벤트와 결합되어 다음과 같은 고유한 그리기 동작을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-168">Toggle controls, such as the controls deriving from the <xref:System.Windows.Forms.ButtonBase> class, have the following distinctive painting behavior in combination with mouse click events:</span></span>  
  
1.  <span data-ttu-id="f67c3-169">사용자가 마우스 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-169">The user presses the mouse button.</span></span>  
  
2.  <span data-ttu-id="f67c3-170">컨트롤이 눌린 상태로 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-170">The control paints in the pressed state.</span></span>  
  
3.  <span data-ttu-id="f67c3-171"><xref:System.Windows.Forms.Control.MouseDown> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-171">The <xref:System.Windows.Forms.Control.MouseDown> event is raised.</span></span>  
  
4.  <span data-ttu-id="f67c3-172">사용자가 마우스 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-172">The user releases the mouse button.</span></span>  
  
5.  <span data-ttu-id="f67c3-173">컨트롤이 올려진 상태로 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-173">The control paints in the raised state.</span></span>  
  
6.  <span data-ttu-id="f67c3-174"><xref:System.Windows.Forms.Control.Click> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-174">The <xref:System.Windows.Forms.Control.Click> event is raised.</span></span>  
  
7.  <span data-ttu-id="f67c3-175"><xref:System.Windows.Forms.Control.MouseClick> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-175">The <xref:System.Windows.Forms.Control.MouseClick> event is raised.</span></span>  
  
8.  <span data-ttu-id="f67c3-176"><xref:System.Windows.Forms.Control.MouseUp> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-176">The <xref:System.Windows.Forms.Control.MouseUp> event is raised.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f67c3-177">사용자가 마우스 단추를 누른 동안 토글 컨트롤에서 포인터를 이동하는 경우(예: 누른 동안 <xref:System.Windows.Forms.Button> 컨트롤에서 마우스 이동) 토글 컨트롤이 올려진 상태로 그려지고 <xref:System.Windows.Forms.Control.MouseUp> 이벤트만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-177">If the user moves the pointer out of the toggle control while the mouse button is down (such as moving the mouse off the <xref:System.Windows.Forms.Button> control while it is pressed), the toggle control will paint in the raised state and only the <xref:System.Windows.Forms.Control.MouseUp> event occurs.</span></span> <span data-ttu-id="f67c3-178">이런 상황에서는 <xref:System.Windows.Forms.Control.Click> 또는 <xref:System.Windows.Forms.Control.MouseClick> 이벤트가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f67c3-178">The <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> events will not occur in this situation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f67c3-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f67c3-179">See Also</span></span>  
 [<span data-ttu-id="f67c3-180">Windows Forms 응용 프로그램의 마우스 입력</span><span class="sxs-lookup"><span data-stu-id="f67c3-180">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
