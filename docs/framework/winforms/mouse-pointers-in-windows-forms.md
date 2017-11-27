---
title: "Windows Forms의 마우스 포인터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4fb0e193ccbced719f30ede91cb59cd51dd349a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="mouse-pointers-in-windows-forms"></a><span data-ttu-id="13918-102">Windows Forms의 마우스 포인터</span><span class="sxs-lookup"><span data-stu-id="13918-102">Mouse Pointers in Windows Forms</span></span>
<span data-ttu-id="13918-103">마우스 *포인터*, 마우스를 사용 하 여 사용자 입력에 대 한 화면에 포커스가 위치를 지정 하는 비트맵은 커서 참조 되는 경우에 따라 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="13918-103">The mouse *pointer*, which is sometimes referred to as the cursor, is a bitmap that specifies a focus point on the screen for user input with the mouse.</span></span> <span data-ttu-id="13918-104">이 항목 Windows Forms에서 마우스 포인터의 개요를 제공 하 고 수정 하 고 마우스 포인터를 제어 하는 방법 중 일부에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="13918-104">This topic provides an overview of the mouse pointer in Windows Forms and describes some of the ways to modify and control the mouse pointer.</span></span>  
  
## <a name="accessing-the-mouse-pointer"></a><span data-ttu-id="13918-105">마우스 포인터에 액세스</span><span class="sxs-lookup"><span data-stu-id="13918-105">Accessing the Mouse Pointer</span></span>  
 <span data-ttu-id="13918-106">마우스 포인터가 나타내는 <xref:System.Windows.Forms.Cursor> 클래스 및 각 <xref:System.Windows.Forms.Control> 에 <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> 해당 컨트롤에 대 한 포인터를 지정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="13918-106">The mouse pointer is represented by the <xref:System.Windows.Forms.Cursor> class, and each <xref:System.Windows.Forms.Control> has a <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> property that specifies the pointer for that control.</span></span> <span data-ttu-id="13918-107"><xref:System.Windows.Forms.Cursor> 클래스와 같은 포인터를 설명 하는 속성이 포함 된 <xref:System.Windows.Forms.Cursor.Position%2A> 및 <xref:System.Windows.Forms.Cursor.HotSpot%2A> 속성과 같은 포인터의 모양을 수정할 수 있는 메서드는 <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>, 및 <xref:System.Windows.Forms.Cursor.DrawStretched%2A> 메서드를 합니다.</span><span class="sxs-lookup"><span data-stu-id="13918-107">The <xref:System.Windows.Forms.Cursor> class contains properties that describe the pointer, such as the <xref:System.Windows.Forms.Cursor.Position%2A> and <xref:System.Windows.Forms.Cursor.HotSpot%2A> properties, and methods that can modify the appearance of the pointer, such as the <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>, and <xref:System.Windows.Forms.Cursor.DrawStretched%2A> methods.</span></span>  
  
## <a name="controlling-the-mouse-pointer"></a><span data-ttu-id="13918-108">마우스 포인터를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="13918-108">Controlling the Mouse Pointer</span></span>  
 <span data-ttu-id="13918-109">경우에 따라 다음 마우스 포인터 사용할 수 있거나 마우스 위치를 변경할 영역을 제한 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13918-109">Sometimes you may want to limit the area in which the mouse pointer can be used or change the position the mouse.</span></span> <span data-ttu-id="13918-110">가져오거나 사용 하 여 마우스의 현재 위치를 설정할 수는 <xref:System.Windows.Forms.Cursor.Position%2A> 의 속성은 <xref:System.Windows.Forms.Cursor>합니다.</span><span class="sxs-lookup"><span data-stu-id="13918-110">You can get or set the current location of the mouse using the <xref:System.Windows.Forms.Cursor.Position%2A> property of the <xref:System.Windows.Forms.Cursor>.</span></span> <span data-ttu-id="13918-111">마우스 포인터를 사용할 수 있습니다 영역을 제한할 수는 또한 설정 수는 <xref:System.Windows.Forms.Cursor.Clip%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="13918-111">In addition, you can limit the area the mouse pointer can be used be setting the <xref:System.Windows.Forms.Cursor.Clip%2A> property.</span></span> <span data-ttu-id="13918-112">기본적으로의 클립 영역에는 전체 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="13918-112">The clip area, by default, is the entire screen.</span></span>  
  
## <a name="changing-the-mouse-pointer"></a><span data-ttu-id="13918-113">마우스 포인터 변경</span><span class="sxs-lookup"><span data-stu-id="13918-113">Changing the Mouse Pointer</span></span>  
 <span data-ttu-id="13918-114">사용자에 게 피드백을 제공 하는 중요 한 차이점은 마우스 포인터를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="13918-114">Changing the mouse pointer is an important way of providing feedback to the user.</span></span> <span data-ttu-id="13918-115">예를 들어의 처리기에서 마우스 포인터를 수정할 수 있습니다는 <xref:System.Windows.Forms.Control.MouseEnter> 및 <xref:System.Windows.Forms.Control.MouseLeave> 계산이 수행 되는 사용자에 게 알림를 제한 하 고 컨트롤의 사용자 상호 작용 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="13918-115">For example, the mouse pointer can be modified in the handlers of the <xref:System.Windows.Forms.Control.MouseEnter> and <xref:System.Windows.Forms.Control.MouseLeave> events to tell the user that computations are occurring and to limit user interaction in the control.</span></span> <span data-ttu-id="13918-116">경우에 따라 끌어서 놓기 작업에서 응용 프로그램은 포함 하는 경우와 같은 시스템 이벤트 때문에 마우스 포인터 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13918-116">Sometimes, the mouse pointer will change because of system events, such as when your application is involved in a drag-and-drop operation.</span></span>  
  
 <span data-ttu-id="13918-117">설정 된 경우 마우스 포인터를 변경 하는 기본적인 방법은 <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> 또는 <xref:System.Windows.Forms.Control.DefaultCursor%2A> 새 컨트롤의 속성 <xref:System.Windows.Forms.Cursor>합니다.</span><span class="sxs-lookup"><span data-stu-id="13918-117">The primary way to change the mouse pointer is by setting the <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> or <xref:System.Windows.Forms.Control.DefaultCursor%2A> property of a control to a new <xref:System.Windows.Forms.Cursor>.</span></span> <span data-ttu-id="13918-118">마우스 포인터 변경의 예의 코드 예제를 참조 하십시오.는 <xref:System.Windows.Forms.Cursor> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="13918-118">For examples of changing the mouse pointer, see the code example in the <xref:System.Windows.Forms.Cursor> class.</span></span> <span data-ttu-id="13918-119">또한는 <xref:System.Windows.Forms.Cursors> 클래스 집합을 노출 <xref:System.Windows.Forms.Cursor> 다양 한 유형의 손 모양 유사한 포인터와 같은 포인터에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="13918-119">In addition, the <xref:System.Windows.Forms.Cursors> class exposes a set of <xref:System.Windows.Forms.Cursor> objects for many different types of pointers, such as a pointer that resembles a hand.</span></span> <span data-ttu-id="13918-120">사용 하 여는 경우 언제 든 지 마우스 포인터가 컨트롤에는 모래 시계과 비슷한, 대기 포인터의 표시는 <xref:System.Windows.Forms.Control.UseWaitCursor%2A> 속성의는 <xref:System.Windows.Forms.Control> 클래스.</span><span class="sxs-lookup"><span data-stu-id="13918-120">To display the wait pointer, which resembles an hourglass, whenever the mouse pointer is on the control, use the <xref:System.Windows.Forms.Control.UseWaitCursor%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13918-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13918-121">See Also</span></span>  
 <xref:System.Windows.Forms.Cursor>  
 [<span data-ttu-id="13918-122">Windows Forms 응용 프로그램의 마우스 입력</span><span class="sxs-lookup"><span data-stu-id="13918-122">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)  
 [<span data-ttu-id="13918-123">Windows Forms에서의 끌어서 놓기 기능</span><span class="sxs-lookup"><span data-stu-id="13918-123">Drag-and-Drop Functionality in Windows Forms</span></span>](../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)
