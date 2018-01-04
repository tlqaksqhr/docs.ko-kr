---
title: "Windows Forms에서의 끌어서 놓기 기능"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drag and drop [Windows Forms], Windows Forms
- Windows Forms, drag and drop
ms.assetid: 65cd2c03-8782-474e-b958-cbe43eeb902c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 86234aca209c5533abf9025911b22c391b0ef22b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="drag-and-drop-functionality-in-windows-forms"></a><span data-ttu-id="d38e2-102">Windows Forms에서의 끌어서 놓기 기능</span><span class="sxs-lookup"><span data-stu-id="d38e2-102">Drag-and-Drop Functionality in Windows Forms</span></span>
<span data-ttu-id="d38e2-103">Windows Forms에는 끌어서 놓기 동작을 구현하는 메서드, 이벤트 및 클래스 집합이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-103">Windows Forms includes a set of methods, events, and classes that implement drag-and-drop behavior.</span></span> <span data-ttu-id="d38e2-104">이 항목에서는 Windows Forms의 끌어서 놓기 지원에 대해 개괄적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-104">This topic provides an overview of the drag-and-drop support in Windows Forms.</span></span>  <span data-ttu-id="d38e2-105">또한 참조 [끌어서 놓기 작업 및 클립보드 지원](http://msdn.microsoft.com/library/fe5ebfwe\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-105">Also see [Drag-and-Drop Operations and Clipboard Support](http://msdn.microsoft.com/library/fe5ebfwe\(v=vs.110\)).</span></span>  
  
## <a name="performing-drag-and-drop-operations"></a><span data-ttu-id="d38e2-106">끌어서 놓기 작업 수행</span><span class="sxs-lookup"><span data-stu-id="d38e2-106">Performing Drag-and-Drop Operations</span></span>  
 <span data-ttu-id="d38e2-107">끌어서 놓기 작업을 수행하려면 <xref:System.Windows.Forms.Control> 클래스의 <xref:System.Windows.Forms.Control.DoDragDrop%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-107">To perform a drag-and-drop operation, use the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="d38e2-108">끌어서 놓기 작업을 수행하는 방법에 대한 자세한 내용은 <xref:System.Windows.Forms.Control.DoDragDrop%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d38e2-108">For more information about how a drag-and-drop operation is performed, see <xref:System.Windows.Forms.Control.DoDragDrop%2A>.</span></span> <span data-ttu-id="d38e2-109">끌어서 놓기 작업이 시작되기 전에 마우스 포인터를 위로 끌어와야 하는 사각형을 가져오려면 <xref:System.Windows.Forms.SystemInformation> 클래스의 <xref:System.Windows.Forms.SystemInformation.DragSize%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-109">To get the rectangle that the mouse pointer must be dragged over before a drag-and-drop operation begins, use the <xref:System.Windows.Forms.SystemInformation.DragSize%2A> property of the <xref:System.Windows.Forms.SystemInformation> class.</span></span>  
  
## <a name="events-related-to-drag-and-drop-operations"></a><span data-ttu-id="d38e2-110">끌어서 놓기 작업과 관련된 이벤트</span><span class="sxs-lookup"><span data-stu-id="d38e2-110">Events Related to Drag-and-Drop Operations</span></span>  
 <span data-ttu-id="d38e2-111">끌어서 놓기 작업에는 두 가지 범주의 이벤트가 있습니다. 하나는 끌어서 놓기 작업의 현재 대상에서 발생하는 이벤트이고, 다른 하나는 끌어서 놓기 작업의 소스에서 발생하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-111">There are two categories of events in a drag and drop operation: events that occur on the current target of the drag-and-drop operation, and events that occur on the source of the drag and drop operation.</span></span>  
  
### <a name="events-on-the-current-target"></a><span data-ttu-id="d38e2-112">현재 대상의 이벤트</span><span class="sxs-lookup"><span data-stu-id="d38e2-112">Events on the Current Target</span></span>  
 <span data-ttu-id="d38e2-113">다음 표에서는 끌어서 놓기 작업의 현재 대상에서 발생하는 이벤트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-113">The following table shows the events that occur on the current target of a drag-and-drop operation.</span></span>  
  
|<span data-ttu-id="d38e2-114">마우스 이벤트</span><span class="sxs-lookup"><span data-stu-id="d38e2-114">Mouse Event</span></span>|<span data-ttu-id="d38e2-115">설명</span><span class="sxs-lookup"><span data-stu-id="d38e2-115">Description</span></span>|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.DragEnter>|<span data-ttu-id="d38e2-116">이 이벤트는 개체를 컨트롤의 범위로 끌어올 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-116">This event occurs when an object is dragged into the control's bounds.</span></span> <span data-ttu-id="d38e2-117">이 이벤트의 처리기는 <xref:System.Windows.Forms.DragEventArgs> 형식의 인수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-117">The handler for this event receives an argument of type <xref:System.Windows.Forms.DragEventArgs>.</span></span>|  
|<xref:System.Windows.Forms.Control.DragOver>|<span data-ttu-id="d38e2-118">이 이벤트는 마우스 포인터가 컨트롤의 범위 내에 있는 동안 개체를 끌 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-118">This event occurs when an object is dragged while the mouse pointer is within the control's bounds.</span></span> <span data-ttu-id="d38e2-119">이 이벤트의 처리기는 <xref:System.Windows.Forms.DragEventArgs> 형식의 인수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-119">The handler for this event receives an argument of type <xref:System.Windows.Forms.DragEventArgs>.</span></span>|  
|<xref:System.Windows.Forms.Control.DragDrop>|<span data-ttu-id="d38e2-120">이 이벤트는 끌어서 놓기 작업이 완료될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-120">This event occurs when a drag-and-drop operation is completed.</span></span> <span data-ttu-id="d38e2-121">이 이벤트의 처리기는 <xref:System.Windows.Forms.DragEventArgs> 형식의 인수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-121">The handler for this event receives an argument of type <xref:System.Windows.Forms.DragEventArgs>.</span></span>|  
|<xref:System.Windows.Forms.Control.DragLeave>|<span data-ttu-id="d38e2-122">이 이벤트는 컨트롤의 범위 밖으로 개체를 끌 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-122">This event occurs when an object is dragged out of the control's bounds.</span></span> <span data-ttu-id="d38e2-123">이 이벤트의 처리기는 <xref:System.EventArgs> 형식의 인수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-123">The handler for this event receives an argument of type <xref:System.EventArgs>.</span></span>|  
  
 <span data-ttu-id="d38e2-124"><xref:System.Windows.Forms.DragEventArgs> 클래스는 마우스 포인터의 위치, 마우스 단추의 현재 상태 및 키보드의 한정자 키, 끄는 데이터, 끌기 이벤트의 소스에서 허용되는 작업과 작업의 대상 놓기 효과를 지정하는 <xref:System.Windows.Forms.DragDropEffects> 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-124">The <xref:System.Windows.Forms.DragEventArgs> class provides the location of the mouse pointer, the current state of the mouse buttons and modifier keys of the keyboard, the data being dragged, and <xref:System.Windows.Forms.DragDropEffects> values that specify the operations allowed by the source of the drag event and the target drop effect for the operation.</span></span>  
  
### <a name="events-on-the-source"></a><span data-ttu-id="d38e2-125">소스의 이벤트</span><span class="sxs-lookup"><span data-stu-id="d38e2-125">Events on the Source</span></span>  
 <span data-ttu-id="d38e2-126">다음 표에서는 끌어서 놓기 작업의 소스에서 발생하는 이벤트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-126">The following table shows the events that occur on the source of the drag-and-drop operation.</span></span>  
  
|<span data-ttu-id="d38e2-127">마우스 이벤트</span><span class="sxs-lookup"><span data-stu-id="d38e2-127">Mouse Event</span></span>|<span data-ttu-id="d38e2-128">설명</span><span class="sxs-lookup"><span data-stu-id="d38e2-128">Description</span></span>|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.GiveFeedback>|<span data-ttu-id="d38e2-129">이 이벤트는 끌기 작업 중에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-129">This event occurs during a drag operation.</span></span> <span data-ttu-id="d38e2-130">마우스 포인터 변경 등 끌어서 놓기 작업이 발생하고 있음을 알리는 시각 신호를 사용자에게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-130">It provides an opportunity to give a visual cue to the user that the drag-and-drop operation is occurring, such as changing the mouse pointer.</span></span> <span data-ttu-id="d38e2-131">이 이벤트의 처리기는 <xref:System.Windows.Forms.GiveFeedbackEventArgs> 형식의 인수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-131">The handler for this event receives an argument of type <xref:System.Windows.Forms.GiveFeedbackEventArgs>.</span></span>|  
|<xref:System.Windows.Forms.Control.QueryContinueDrag>|<span data-ttu-id="d38e2-132">이 이벤트는 끌어서 놓기 작업 중에 발생하며 끌기 소스가 끌어서 놓기 작업을 취소해야 할지를 결정하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-132">This event is raised during a drag-and-drop operation and enables the drag source to determine whether the drag-and-drop operation should be canceled.</span></span> <span data-ttu-id="d38e2-133">이 이벤트의 처리기는 <xref:System.Windows.Forms.QueryContinueDragEventArgs> 형식의 인수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-133">The handler for this event receives an argument of type <xref:System.Windows.Forms.QueryContinueDragEventArgs>.</span></span>|  
  
 <span data-ttu-id="d38e2-134"><xref:System.Windows.Forms.QueryContinueDragEventArgs> 클래스는 마우스 단추의 현재 상태 및 키보드의 한정자 키, Esc 키를 눌렀는지 여부를 지정하는 값, 끌어서 놓기 작업을 계속할지 여부를 지정하기 위해 설정할 수 있는 <xref:System.Windows.Forms.DragAction> 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d38e2-134">The <xref:System.Windows.Forms.QueryContinueDragEventArgs> class provides the current state of the mouse buttons and modifier keys of the keyboard, a value specifying whether the ESC key was pressed, and a <xref:System.Windows.Forms.DragAction> value that can be set to specify whether the drag-and-drop operation should continue.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d38e2-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d38e2-135">See Also</span></span>  
 [<span data-ttu-id="d38e2-136">Windows Forms 응용 프로그램의 마우스 입력</span><span class="sxs-lookup"><span data-stu-id="d38e2-136">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
