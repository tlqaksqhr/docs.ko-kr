---
title: "방법: Windows Forms에서 탭 순서 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TabStop
- TabIndex
helpviewer_keywords:
- tab order [Windows Forms], controls on Windows forms
- Windows Forms controls, setting tab order
- controls [Windows Forms], setting tab order
- Windows Forms, setting tab order
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a7acca633a5a2b98d7c4b6dd64355996e763d6df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a><span data-ttu-id="110f4-102">방법: Windows Forms에서 탭 순서 설정</span><span class="sxs-lookup"><span data-stu-id="110f4-102">How to: Set the Tab Order on Windows Forms</span></span>
<span data-ttu-id="110f4-103">탭 순서는 사용자가 이동 포커스가 한 컨트롤에서 다른 TAB 키를 눌러 순서는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-103">The tab order is the order in which a user moves focus from one control to another by pressing the TAB key.</span></span> <span data-ttu-id="110f4-104">각 폼에는 자체 탭 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-104">Each form has its own tab order.</span></span> <span data-ttu-id="110f4-105">기본적으로 탭 순서는 컨트롤을 만든 순서와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-105">By default, the tab order is the same as the order in which you created the controls.</span></span> <span data-ttu-id="110f4-106">탭 순서 번호는 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-106">Tab-order numbering begins with zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="110f4-107">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="110f4-108">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="110f4-109">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="110f4-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-the-tab-order-of-a-control"></a><span data-ttu-id="110f4-110">컨트롤의 탭 순서 설정</span><span class="sxs-lookup"><span data-stu-id="110f4-110">To set the tab order of a control</span></span>  
  
1.  <span data-ttu-id="110f4-111">에 **보기** 메뉴를 클릭 하 여 **탭 순서**합니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-111">On the **View** menu, click **Tab Order**.</span></span>  
  
     <span data-ttu-id="110f4-112">양식에서 탭 순서 선택 모드를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-112">This activates the tab-order selection mode on the form.</span></span> <span data-ttu-id="110f4-113">숫자 (나타내는 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성) 각 컨트롤의 왼쪽 위 모서리에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-113">A number (representing the <xref:System.Windows.Forms.Control.TabIndex%2A> property) appears in the upper-left corner of each control.</span></span>  
  
2.  <span data-ttu-id="110f4-114">원하는 탭 순서를 설정 하는 순차적으로 컨트롤을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-114">Click the controls sequentially to establish the tab order you want.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="110f4-115">탭 순서는 컨트롤의 위치는 0 보다 크거나 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-115">A control's place within the tab order can be set to any value greater than or equal to 0.</span></span> <span data-ttu-id="110f4-116">중복이 발생 하는 경우 두 컨트롤의 z 순서 계산 되 고 맨 위에 있는 컨트롤이 탭 처음으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-116">When duplicates occur, the z-order of the two controls is evaluated and the control on top is tabbed to first.</span></span> <span data-ttu-id="110f4-117">(Z-순서는 폼의 z 축 [깊이]와 함께 폼에 컨트롤의 시각적 계층 않습니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-117">(The z-order is the visual layering of controls on a form along the form's z-axis [depth].</span></span> <span data-ttu-id="110f4-118">Z 좌표는 컨트롤 결정 앞뒤 합니다.) Z-순서에 대 한 자세한 내용은 참조 하십시오. [Windows Forms에서 개체 계층화](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-118">The z-order determines which controls are in front of other controls.) For more information on z-order, see [Layering Objects on Windows Forms](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md).</span></span>  
  
3.  <span data-ttu-id="110f4-119">완료 되 면 클릭 **탭 순서** 에 **보기** 메뉴 다시 탭 순서 모드를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-119">When you have finished, click **Tab Order** on the **View** menu again to leave tab order mode.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="110f4-120">사용 안 함 및 보이지 않는 컨트롤 뿐 아니라 포커스를 받을 수 없는 컨트롤 하지 않은 한 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성 및은 탭 순서에 포함 되지 합니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-120">Controls that cannot get the focus, as well as disabled and invisible controls, do not have a <xref:System.Windows.Forms.Control.TabIndex%2A> property and are not included in the tab order.</span></span> <span data-ttu-id="110f4-121">TAB 키를 누를 때 이러한 컨트롤은 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-121">As a user presses the TAB key, these controls are skipped.</span></span>  
  
 <span data-ttu-id="110f4-122">또는 탭 순서를 사용 하 여 속성 창에서 설정할 수는 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-122">Alternatively, tab order can be set in the Properties window using the <xref:System.Windows.Forms.Control.TabIndex%2A> property.</span></span> <span data-ttu-id="110f4-123"><xref:System.Windows.Forms.Control.TabIndex%2A> 속성 컨트롤의 탭 순서에 배치 되는 위치를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-123">The <xref:System.Windows.Forms.Control.TabIndex%2A> property of a control determines where it is positioned in the tab order.</span></span> <span data-ttu-id="110f4-124">기본적으로 그린 첫 번째 컨트롤에는 <xref:System.Windows.Forms.Control.TabIndex%2A> 값 0을 두 번째는는 <xref:System.Windows.Forms.Control.TabIndex%2A> 1, 및 등입니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-124">By default, the first control drawn has a <xref:System.Windows.Forms.Control.TabIndex%2A> value of 0, the second has a <xref:System.Windows.Forms.Control.TabIndex%2A> of 1, and so on.</span></span>  
  
 <span data-ttu-id="110f4-125">또한 기본적으로 <xref:System.Windows.Forms.GroupBox> 컨트롤에 고유한 <xref:System.Windows.Forms.Control.TabIndex%2A> 값은 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-125">Additionally, by default, a <xref:System.Windows.Forms.GroupBox> control has its own <xref:System.Windows.Forms.Control.TabIndex%2A> value, which is a whole number.</span></span> <span data-ttu-id="110f4-126">A <xref:System.Windows.Forms.GroupBox> 런타임 시 컨트롤 자체 포커스를 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-126">A <xref:System.Windows.Forms.GroupBox> control itself cannot have focus at run time.</span></span> <span data-ttu-id="110f4-127">따라서 각 컨트롤 내에서 한 <xref:System.Windows.Forms.GroupBox> 는 고유한 10 진수 <xref:System.Windows.Forms.Control.TabIndex%2A> .0 부터는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-127">Thus, each control within a <xref:System.Windows.Forms.GroupBox> has its own decimal <xref:System.Windows.Forms.Control.TabIndex%2A> value, beginning with .0.</span></span> <span data-ttu-id="110f4-128">기본적으로 <xref:System.Windows.Forms.Control.TabIndex%2A> 의 <xref:System.Windows.Forms.GroupBox> 컨트롤 증가, 내에 있는 컨트롤을 적절 하 게 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-128">Naturally, as the <xref:System.Windows.Forms.Control.TabIndex%2A> of a <xref:System.Windows.Forms.GroupBox> control is incremented, the controls within it will be incremented accordingly.</span></span> <span data-ttu-id="110f4-129">변경한 경우에 <xref:System.Windows.Forms.Control.TabIndex%2A> 5-6의 값은 <xref:System.Windows.Forms.Control.TabIndex%2A> 해당 그룹의 첫 번째 컨트롤의 값이 자동으로 6.0 및 등을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-129">If you changed a <xref:System.Windows.Forms.Control.TabIndex%2A> value from 5 to 6, the <xref:System.Windows.Forms.Control.TabIndex%2A> value of the first control in its group automatically changes to 6.0, and so on.</span></span>  
  
 <span data-ttu-id="110f4-130">마지막으로, 특정 컨트롤을 다로 폼의 탭 순서에서 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-130">Finally, any control of the many on your form can be skipped in the tab order.</span></span> <span data-ttu-id="110f4-131">일반적으로 TAB 키를 누르면 연속적으로 실행된 시간 선택에서 탭 순서에서 각 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-131">Usually, pressing TAB successively at run time selects each control in the tab order.</span></span> <span data-ttu-id="110f4-132">전원을 켜는 방식으로 <xref:System.Windows.Forms.Control.TabStop%2A> 속성 폼의 탭 순서에서를 통해 전달 되어야 하는 컨트롤을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-132">By turning off the <xref:System.Windows.Forms.Control.TabStop%2A> property, you can make a control be passed over in the tab order of the form.</span></span>  
  
#### <a name="to-remove-a-control-from-the-tab-order"></a><span data-ttu-id="110f4-133">탭 순서에서 컨트롤을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="110f4-133">To remove a control from the tab order</span></span>  
  
1.  <span data-ttu-id="110f4-134">컨트롤의 <xref:System.Windows.Forms.Control.TabStop%2A> 속성을 `false` 속성 창에서.</span><span class="sxs-lookup"><span data-stu-id="110f4-134">Set the control's <xref:System.Windows.Forms.Control.TabStop%2A> property to `false` in the Properties window.</span></span>  
  
     <span data-ttu-id="110f4-135">A 컨트롤 <xref:System.Windows.Forms.Control.TabStop%2A> 속성이 설정 되어 `false` TAB 키로 컨트롤을 순환 하는 경우 컨트롤을 건너 하는 경우에 여전히 탭 순서에서 그 위치를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-135">A control whose <xref:System.Windows.Forms.Control.TabStop%2A> property has been set to `false` still maintains its position in the tab order, even though the control is skipped when you cycle through the controls with the TAB key.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="110f4-136">라디오 단추 그룹 실행 시 단일 탭을 있습니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-136">A radio button group has a single tab stop at run time.</span></span> <span data-ttu-id="110f4-137">선택한 단추 (사용 하 여 단추, 즉 해당 <xref:System.Windows.Forms.RadioButton.Checked%2A> 속성이로 설정 `true`)가 해당 <xref:System.Windows.Forms.Control.TabStop%2A> 속성으로 자동 설정 `true`다른 단추를 포함 하는 반면, 해당 <xref:System.Windows.Forms.Control.TabStop%2A> 속성이로 설정 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-137">The selected button (that is, the button with its <xref:System.Windows.Forms.RadioButton.Checked%2A> property set to `true`) has its <xref:System.Windows.Forms.Control.TabStop%2A> property automatically set to `true`, while the other buttons have their <xref:System.Windows.Forms.Control.TabStop%2A> property set to `false`.</span></span> <span data-ttu-id="110f4-138">그룹화에 대 한 자세한 내용은 <xref:System.Windows.Forms.RadioButton> 컨트롤 참조 [집합으로 함수에 Windows Forms RadioButton 컨트롤 그룹화](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="110f4-138">For more information about grouping <xref:System.Windows.Forms.RadioButton> controls, see [Grouping Windows Forms RadioButton Controls to Function as a Set](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="110f4-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="110f4-139">See Also</span></span>  
 [<span data-ttu-id="110f4-140">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="110f4-140">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="110f4-141">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="110f4-141">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="110f4-142">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="110f4-142">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="110f4-143">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="110f4-143">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
