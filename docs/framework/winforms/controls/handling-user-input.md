---
title: 사용자 입력 처리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
ms.openlocfilehash: a230611bfbb0a7f21a96de22674377887cc93c2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527802"
---
# <a name="handling-user-input"></a><span data-ttu-id="9d18d-102">사용자 입력 처리</span><span class="sxs-lookup"><span data-stu-id="9d18d-102">Handling User Input</span></span>
<span data-ttu-id="9d18d-103">이 항목에서 제공 하는 기본 키보드 및 마우스 이벤트를 설명 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-103">This topic describes the main keyboard and mouse events provided by <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9d18d-104">이벤트를 처리할 경우 컨트롤 작성자는 이벤트에 대리자를 연결하는 대신 보호된 `On`*EventName* 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-104">When handling an event, control authors should override the protected `On`*EventName* method rather than attaching a delegate to the event.</span></span> <span data-ttu-id="9d18d-105">이벤트의 검토는 [구성 요소에서 이벤트 발생](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d18d-105">For a review of events, see [Raising Events from a Component](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d18d-106">기본 클래스의 인스턴스는 이벤트와 연결 된 데이터가 없는 경우 <xref:System.EventArgs> 에 인수로 전달 되는 `On` *EventName* 메서드.</span><span class="sxs-lookup"><span data-stu-id="9d18d-106">If there is no data associated with an event, an instance of the base class <xref:System.EventArgs> is passed as an argument to the `On`*EventName* method.</span></span>  
  
## <a name="keyboard-events"></a><span data-ttu-id="9d18d-107">키보드 이벤트</span><span class="sxs-lookup"><span data-stu-id="9d18d-107">Keyboard Events</span></span>  
 <span data-ttu-id="9d18d-108">컨트롤을 처리할 수 있는 일반적인 키보드 이벤트는 <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, 및 <xref:System.Windows.Forms.Control.KeyUp>합니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-108">The common keyboard events that your control can handle are <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, and <xref:System.Windows.Forms.Control.KeyUp>.</span></span>  
  
|<span data-ttu-id="9d18d-109">이벤트 이름</span><span class="sxs-lookup"><span data-stu-id="9d18d-109">Event Name</span></span>|<span data-ttu-id="9d18d-110">재정의할 메서드</span><span class="sxs-lookup"><span data-stu-id="9d18d-110">Method to Override</span></span>|<span data-ttu-id="9d18d-111">이벤트 설명</span><span class="sxs-lookup"><span data-stu-id="9d18d-111">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|<span data-ttu-id="9d18d-112">키를 처음 누를 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-112">Raised only when a key is initially pressed.</span></span>|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|<span data-ttu-id="9d18d-113">키를 누를 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-113">Raised every time a key is pressed.</span></span> <span data-ttu-id="9d18d-114">키를 누르고 있으면는 <xref:System.Windows.Forms.Control.KeyPress> 운영 체제에 의해 정의 된 반복 속도에서 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-114">If a key is held down, a <xref:System.Windows.Forms.Control.KeyPress> event is raised at the repeat rate defined by the operating system.</span></span>|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|<span data-ttu-id="9d18d-115">키를 놓으면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-115">Raised when a key is released.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="9d18d-116">키보드 입력 처리는 앞의 테이블에서 이벤트를 재정의하는 것보다 더 복잡하며 이 항목의 범위를 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-116">Handling keyboard input is considerably more complex than overriding the events in the preceding table and is beyond the scope of this topic.</span></span> <span data-ttu-id="9d18d-117">자세한 내용은 [Windows Forms의 사용자 입력](../../../../docs/framework/winforms/user-input-in-windows-forms.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d18d-117">For more information, see [User Input in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).</span></span>  
  
## <a name="mouse-events"></a><span data-ttu-id="9d18d-118">마우스 이벤트</span><span class="sxs-lookup"><span data-stu-id="9d18d-118">Mouse Events</span></span>  
 <span data-ttu-id="9d18d-119">마우스 이벤트는 컨트롤에서 처리할 수 <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, 및 <xref:System.Windows.Forms.Control.MouseUp>합니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-119">The mouse events that your control can handle are <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, and <xref:System.Windows.Forms.Control.MouseUp>.</span></span>  
  
|<span data-ttu-id="9d18d-120">이벤트 이름</span><span class="sxs-lookup"><span data-stu-id="9d18d-120">Event Name</span></span>|<span data-ttu-id="9d18d-121">재정의할 메서드</span><span class="sxs-lookup"><span data-stu-id="9d18d-121">Method to Override</span></span>|<span data-ttu-id="9d18d-122">이벤트 설명</span><span class="sxs-lookup"><span data-stu-id="9d18d-122">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|<span data-ttu-id="9d18d-123">포인터가 컨트롤 위에 있을 때 마우스 단추를 누르면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-123">Raised when the mouse button is pressed while the pointer is over the control.</span></span>|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|<span data-ttu-id="9d18d-124">포인터가 컨트롤의 지역에 먼저 들어가면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-124">Raised when the pointer first enters the region of the control.</span></span>|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|<span data-ttu-id="9d18d-125">포인터로 컨트롤을 가리키면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-125">Raised when the pointer hovers over the control.</span></span>|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|<span data-ttu-id="9d18d-126">포인터가 컨트롤의 지역을 벗어나면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-126">Raised when the pointer leaves the region of the control.</span></span>|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|<span data-ttu-id="9d18d-127">포인터가 컨트롤의 지역에서 이동하면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-127">Raised when the pointer moves in the region of the control.</span></span>|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|<span data-ttu-id="9d18d-128">포인터가 컨트롤 위에 있거나 포인터가 컨트롤의 지역을 벗어나는 동안 마우스 단추를 놓으면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-128">Raised when the mouse button is released while the pointer is over the control or the pointer leaves the region of the control.</span></span>|  
  
 <span data-ttu-id="9d18d-129">다음 코드는 재정의의 예를 보여 줍니다.는 <xref:System.Windows.Forms.Control.MouseDown> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-129">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 <span data-ttu-id="9d18d-130">다음 코드는 재정의의 예를 보여 줍니다.는 <xref:System.Windows.Forms.Control.MouseMove> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-130">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseMove> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 <span data-ttu-id="9d18d-131">다음 코드는 재정의의 예를 보여 줍니다.는 <xref:System.Windows.Forms.Control.MouseUp> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="9d18d-131">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 <span data-ttu-id="9d18d-132">`FlashTrackBar` 샘플의 전체 소스 코드는 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d18d-132">For the complete source code for the `FlashTrackBar` sample, see [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d18d-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d18d-133">See Also</span></span>  
 [<span data-ttu-id="9d18d-134">Windows Forms 컨트롤의 이벤트</span><span class="sxs-lookup"><span data-stu-id="9d18d-134">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [<span data-ttu-id="9d18d-135">이벤트 정의</span><span class="sxs-lookup"><span data-stu-id="9d18d-135">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [<span data-ttu-id="9d18d-136">이벤트</span><span class="sxs-lookup"><span data-stu-id="9d18d-136">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="9d18d-137">Windows Forms에 사용자 입력</span><span class="sxs-lookup"><span data-stu-id="9d18d-137">User Input in Windows Forms</span></span>](../../../../docs/framework/winforms/user-input-in-windows-forms.md)
