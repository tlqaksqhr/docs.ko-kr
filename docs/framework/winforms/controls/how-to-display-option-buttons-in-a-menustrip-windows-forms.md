---
title: "방법: MenuStrip에 옵션 단추 표시(Windows Forms)"
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
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0de3b8596bc06c79f391141ef85fec65ac343d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a><span data-ttu-id="fe96f-102">방법: MenuStrip에 옵션 단추 표시(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="fe96f-102">How to: Display Option Buttons in a MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="fe96f-103">옵션 단추, 라디오 단추 라고도 한 번에 하나씩만 선택할 수 있다는 점을 제외 하 고 확인란을 선택 하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-103">Option buttons, also known as radio buttons, are similar to check boxes except that users can select only one at a time.</span></span> <span data-ttu-id="fe96f-104">기본적으로 있지만 <xref:System.Windows.Forms.ToolStripMenuItem> 클래스 옵션 단추 동작을 제공 하지 않습니다는 클래스에서 메뉴 항목에 대 한 옵션 단추 동작을 구현 하는 사용자 지정할 수 있는 확인란 동작을 제공는 <xref:System.Windows.Forms.MenuStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-104">Although by default the <xref:System.Windows.Forms.ToolStripMenuItem> class does not provide option-button behavior, the class does provide check-box behavior that you can customize to implement option-button behavior for menu items in a <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="fe96f-105">경우는 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 메뉴 항목의 속성은 `true`, 사용자가 확인 표시가 표시 설정/해제 항목을 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-105">When the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property of a menu item is `true`, users can click the item to toggle the display of a check mark.</span></span> <span data-ttu-id="fe96f-106"><xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 속성 항목의 현재 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-106">The <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property indicates the current state of the item.</span></span> <span data-ttu-id="fe96f-107">항목을 선택 하는 경우 설정 하는 확인 해야 기본 옵션 단추 동작을 구현 하려면는 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 이전에 선택한 항목에 대 한 속성 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-107">To implement basic option-button behavior, you must ensure that when an item is selected, you set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property for the previously selected item to `false`.</span></span>  
  
 <span data-ttu-id="fe96f-108">다음 절차는이 구현 하는 방법을 설명 하 고 상속 된 클래스에 추가 된 기능은 <xref:System.Windows.Forms.ToolStripMenuItem> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-108">The following procedures describe how to implement this and additional functionality in a class that inherits the <xref:System.Windows.Forms.ToolStripMenuItem> class.</span></span> <span data-ttu-id="fe96f-109">`ToolStripRadioButtonMenuItem` 클래스와 같은 멤버를 재정의 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> 및 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> 선택 동작 및 모양 옵션 단추를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-109">The `ToolStripRadioButtonMenuItem` class overrides members such as <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> and <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> to provide the selection behavior and appearance of option buttons.</span></span> <span data-ttu-id="fe96f-110">또한이 클래스는 재정의 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 부모 항목을 선택 하지 않으면 속성 하위 메뉴의 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-110">Additionally, this class overrides the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that options on a submenu are disabled unless the parent item is selected.</span></span>  
  
### <a name="to-implement-option-button-selection-behavior"></a><span data-ttu-id="fe96f-111">옵션 단추 선택 동작을 구현 하려면</span><span class="sxs-lookup"><span data-stu-id="fe96f-111">To implement option-button selection behavior</span></span>  
  
1.  <span data-ttu-id="fe96f-112">초기화는 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 속성을 `true` 항목을 선택할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-112">Initialize the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true` to enable item selection.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  <span data-ttu-id="fe96f-113">재정의 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> 메서드를 새 항목을 선택할 때 이전에 선택한 항목의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-113">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> method to clear the selection of the previously selected item when a new item is selected.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  <span data-ttu-id="fe96f-114">재정의 <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> 메서드를 해당 이미 선택 된 항목을 클릭 하 여 선택 영역 지워지지 것입니다. 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-114">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> method to ensure that clicking an item that has already been selected will not clear the selection.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### <a name="to-modify-the-appearance-of-the-option-button-items"></a><span data-ttu-id="fe96f-115">옵션 단추 항목의 모양을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="fe96f-115">To modify the appearance of the option-button items</span></span>  
  
1.  <span data-ttu-id="fe96f-116">재정의 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> 옵션 단추를 사용 하 여 기본 확인 표시를 대체 하는 메서드는 <xref:System.Windows.Forms.RadioButtonRenderer> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-116">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method to replace the default check-mark with an option button by using the <xref:System.Windows.Forms.RadioButtonRenderer> class.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  <span data-ttu-id="fe96f-117">재정의 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, 및 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> 마우스 상태를 추적 하 고 있는지 확인 하는 메서드는 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> 메서드는 올바른 옵션 단추 상태를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-117">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, and <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> methods to track the state of the mouse and ensure that the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method paints the correct option-button state.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a><span data-ttu-id="fe96f-118">부모 항목을 선택 하지 않으면 하위 메뉴의 옵션을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="fe96f-118">To disable options on a submenu when the parent item is not selected</span></span>  
  
1.  <span data-ttu-id="fe96f-119">재정의 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 부모 항목 둘 다와 함께 설치 된 항목이 사용 불가능 하는 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 값 `true` 및 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 의 값 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-119">Override the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that the item is disabled when it has a parent item with both a <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> value of `true` and a <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> value of `false`.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  <span data-ttu-id="fe96f-120">재정의 <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> 구독할 메서드는 <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> 부모 항목의 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-120">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> method to subscribe to the <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event of the parent item.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  <span data-ttu-id="fe96f-121">부모 항목에 대 한 처리기에서 <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> 이벤트를 새 활성화 된 상태와 디스플레이 업데이트 하려면 항목을 무효화 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-121">In the handler for the parent-item <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event, invalidate the item to update the display with the new enabled state.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## <a name="example"></a><span data-ttu-id="fe96f-122">예</span><span class="sxs-lookup"><span data-stu-id="fe96f-122">Example</span></span>  
 <span data-ttu-id="fe96f-123">다음 코드 예제에서는 제공 전체 `ToolStripRadioButtonMenuItem` 클래스 및 <xref:System.Windows.Forms.Form> 클래스 및 `Program` 클래스 옵션 단추 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-123">The following code example provides the complete `ToolStripRadioButtonMenuItem` class, and a <xref:System.Windows.Forms.Form> class and `Program` class to demonstrate the option-button behavior.</span></span>  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fe96f-124">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="fe96f-124">Compiling the Code</span></span>  
 <span data-ttu-id="fe96f-125">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fe96f-125">This example requires:</span></span>  
  
-   <span data-ttu-id="fe96f-126">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="fe96f-126">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe96f-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe96f-127">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RadioButtonRenderer>  
 [<span data-ttu-id="fe96f-128">MenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fe96f-128">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [<span data-ttu-id="fe96f-129">방법: 사용자 지정 ToolStripRenderer 구현</span><span class="sxs-lookup"><span data-stu-id="fe96f-129">How to: Implement a Custom ToolStripRenderer</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-toolstriprenderer.md)
