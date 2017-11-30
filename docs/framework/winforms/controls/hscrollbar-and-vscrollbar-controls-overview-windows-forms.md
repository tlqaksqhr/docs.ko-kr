---
title: "HScrollBar 및 VScrollBar 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 80ec592bf83969ae57495b0df2af110b5622ea11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a><span data-ttu-id="55fcb-102">HScrollBar 및 VScrollBar 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="55fcb-102">HScrollBar and VScrollBar Controls Overview (Windows Forms)</span></span>
<span data-ttu-id="55fcb-103">Windows Forms <xref:System.Windows.Forms.ScrollBar> 컨트롤 가로로 또는 세로로 응용 프로그램 또는 컨트롤 내에서 쉽게 탐색 긴 목록 항목이 나 많은 양의 정보를 제공 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fcb-103">Windows Forms <xref:System.Windows.Forms.ScrollBar> controls are used to provide easy navigation through a long list of items or a large amount of information by scrolling either horizontally or vertically within an application or control.</span></span> <span data-ttu-id="55fcb-104">스크롤 막대는 Windows 인터페이스의 공통 요소 이므로 <xref:System.Windows.Forms.ScrollBar> 컨트롤에서 파생 되지 않는 컨트롤과 대개는 <xref:System.Windows.Forms.ScrollableControl> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcb-104">Scroll bars are a common element of the Windows interface, so the <xref:System.Windows.Forms.ScrollBar> control is often used with controls that do not derive from the <xref:System.Windows.Forms.ScrollableControl> class.</span></span> <span data-ttu-id="55fcb-105">대부분의 개발자 통합 하도록 선택 하는 마찬가지로,는 <xref:System.Windows.Forms.ScrollBar> 자신의 사용자 컨트롤 작성 하는 시기를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fcb-105">Similarly, many developers choose to incorporate the <xref:System.Windows.Forms.ScrollBar> control when authoring their own user controls.</span></span>  
  
 <span data-ttu-id="55fcb-106"><xref:System.Windows.Forms.HScrollBar> (가로) 및 <xref:System.Windows.Forms.VScrollBar> (세로) 컨트롤 다른 컨트롤에서 독립적으로 작동 하 고 이벤트, 속성 및 메서드 집합이 자신의 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fcb-106">The <xref:System.Windows.Forms.HScrollBar> (horizontal) and <xref:System.Windows.Forms.VScrollBar> (vertical) controls operate independently from other controls and have their own set of events, properties, and methods.</span></span> <span data-ttu-id="55fcb-107"><xref:System.Windows.Forms.ScrollBar>컨트롤 텍스트 상자, 목록 상자 및 콤보 상자, MDI 폼에 연결 되어 있는 기본 제공 스크롤 막대와 동일 하지 않은 (의 <xref:System.Windows.Forms.TextBox> 컨트롤에는 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 속성을 컨트롤에 연결 되어 있는 스크롤 막대 표시 또는 숨기기).</span><span class="sxs-lookup"><span data-stu-id="55fcb-107"><xref:System.Windows.Forms.ScrollBar> controls are not the same as the built-in scroll bars that are attached to text boxes, list boxes, combo boxes, or MDI forms (the <xref:System.Windows.Forms.TextBox> control has a <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to show or hide scroll bars that are attached to the control).</span></span>  
  
 <span data-ttu-id="55fcb-108"><xref:System.Windows.Forms.ScrollBar> 사용을 제어는 <xref:System.Windows.Forms.ScrollBar.Scroll> 스크롤 막대를 따라 (엄지 단추 라고도 함) 스크롤 상자의 움직임을 모니터링 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcb-108">The <xref:System.Windows.Forms.ScrollBar> controls use the <xref:System.Windows.Forms.ScrollBar.Scroll> event to monitor the movement of the scroll box (sometimes referred to as the thumb) along the scroll bar.</span></span> <span data-ttu-id="55fcb-109">사용 하는 <xref:System.Windows.Forms.ScrollBar.Scroll> 이벤트를 끌 때 스크롤 막대의 값에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fcb-109">Using the <xref:System.Windows.Forms.ScrollBar.Scroll> event provides access to the scroll bar value as it is being dragged.</span></span>  
  
## <a name="value-property"></a><span data-ttu-id="55fcb-110">값 속성</span><span class="sxs-lookup"><span data-stu-id="55fcb-110">Value Property</span></span>  
 <span data-ttu-id="55fcb-111"><xref:System.Windows.Forms.ScrollBar.Value%2A> (즉, 기본적으로 0) 속성은 한 `integer` , 스크롤 막대의 스크롤 상자 위치에 해당 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcb-111">The <xref:System.Windows.Forms.ScrollBar.Value%2A> property (which, by default, is 0) is an `integer` value corresponding to the position of the scroll box in the scroll bar.</span></span> <span data-ttu-id="55fcb-112">스크롤 상자 위치가 최소값에, 가로 스크롤 막대 맨 왼쪽 위치 또는 세로 스크롤 막대 위쪽 위치를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fcb-112">When the scroll box position is at the minimum value, it moves to the left-most position (for horizontal scroll bars) or the top position (for vertical scroll bars).</span></span> <span data-ttu-id="55fcb-113">때 스크롤 상자는 최대값, 스크롤 상자가 이동 맨 오른쪽 또는 아래쪽 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fcb-113">When the scroll box is at the maximum value, the scroll box moves to the right-most or bottom position.</span></span> <span data-ttu-id="55fcb-114">마찬가지로, 하 한 및 상한 범위 사이의 중간 값 스크롤 막대를 중간에 있는 스크롤 상자의 첨단 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="55fcb-114">Similarly, a value halfway between the bottom and top of the range places the leading edge of the scroll box in the middle of the scroll bar.</span></span>  
  
 <span data-ttu-id="55fcb-115">마우스 클릭을 사용 하 여 스크롤 막대 값을 변경 하려면를 사용자 막대를 따라 어떤 위치로 든 스크롤 상자를 끌 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55fcb-115">In addition to using mouse clicks to change the scroll bar value, a user can also drag the scroll box to any point along the bar.</span></span> <span data-ttu-id="55fcb-116">결과 값의 스크롤 상자 위치에 따라 달라 지지만 범위 내에서 <xref:System.Windows.Forms.ScrollBar.Minimum%2A> 를 <xref:System.Windows.Forms.ScrollBar.Maximum%2A> 속성은 사용자가 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55fcb-116">The resulting value depends on the position of the scroll box, but it is always within the range of the <xref:System.Windows.Forms.ScrollBar.Minimum%2A> to <xref:System.Windows.Forms.ScrollBar.Maximum%2A> properties set by the user.</span></span>  
  
## <a name="largechange-and-smallchange-properties"></a><span data-ttu-id="55fcb-117">LargeChange 및 SmallChange 속성</span><span class="sxs-lookup"><span data-stu-id="55fcb-117">LargeChange and SmallChange Properties</span></span>  
 <span data-ttu-id="55fcb-118">사용자의 PAGE UP 또는 PAGE DOWN 키를 누르거나 스크롤 상자 옆에 있는 스크롤 막대 트랙에 클릭할 때는 <xref:System.Windows.Forms.ScrollBar.Value%2A> 속성에 설정 된 값에 따라이 변경의 <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcb-118">When the user presses the PAGE UP or PAGE DOWN key or clicks in the scroll bar track on either side of the scroll box, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> property.</span></span>  
  
 <span data-ttu-id="55fcb-119">키를 누를 때 화살표 중 하나 또는 스크롤 막대 단추 중 하나를 클릭는 <xref:System.Windows.Forms.ScrollBar.Value%2A> 속성에 설정 된 값에 따라이 변경 된 <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcb-119">When the user presses one of the arrow keys or clicks one of the scroll bar buttons, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55fcb-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55fcb-120">See Also</span></span>  
 <xref:System.Windows.Forms.HScrollBar>  
 <xref:System.Windows.Forms.VScrollBar>  
 [<span data-ttu-id="55fcb-121">.NET Framework 2.0에 대 한 Windows Forms에 대 한 추가</span><span class="sxs-lookup"><span data-stu-id="55fcb-121">Additions to Windows Forms for the .NET Framework 2.0</span></span>](http://msdn.microsoft.com/en-us/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)  
 [<span data-ttu-id="55fcb-122">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="55fcb-122">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
