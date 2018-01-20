---
title: "방법: Windows Forms에서 컨트롤 고정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ceaacc250d48e7199d7224f95aa91ed976c097e0
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="a5b93-102">방법: Windows Forms에서 컨트롤 고정</span><span class="sxs-lookup"><span data-stu-id="a5b93-102">How to: Anchor Controls on Windows Forms</span></span>
<span data-ttu-id="a5b93-103">런타임 시 사용자 크기를 조정할 수 있는 폼을 디자인 하는 경우 폼에서 컨트롤의 크기를 조정 하 고 제대로 위치를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-103">If you are designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="a5b93-104">폼을 사용 하 여 동적으로 컨트롤의 크기를 조정 하려면 사용할 수 있습니다는 <xref:System.Windows.Forms.Control.Anchor%2A> Windows Forms 컨트롤의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="a5b93-105"><xref:System.Windows.Forms.Control.Anchor%2A> 속성은 컨트롤에 대 한 앵커 위치를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="a5b93-106">폼에 컨트롤 고정 폼의 크기를 조정할 때 컨트롤 컨트롤 앵커 위치 사이의 거리를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="a5b93-107">예를 들어 한 <xref:System.Windows.Forms.TextBox> 컨트롤을 폼의 크기가 조정 왼쪽, 오른쪽 및 폼의 아래쪽 가장자리에 고정 되는 <xref:System.Windows.Forms.TextBox> 컨트롤의 크기가 조정 가로로 폼의 오른쪽 및 왼쪽 면에서 동일 하 게 유지 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="a5b93-108">또한 컨트롤 배치 자체 세로로 위치는 항상 폼의 아래쪽 가장자리 로부터 같은 거리 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="a5b93-109">컨트롤 고정 하지 않으면 폼의 크기를 조정 하는 경우 폼의 가장자리를 기준으로 컨트롤의 위치 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>  
  
 <span data-ttu-id="a5b93-110"><xref:System.Windows.Forms.Control.Anchor%2A> 속성와 상호 작용 하는 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="a5b93-111">자세한 내용은 참조 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-111">For more information, see [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5b93-112">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a5b93-113">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a5b93-114">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5b93-114">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-anchor-a-control-on-a-form"></a><span data-ttu-id="a5b93-115">폼에 컨트롤을 고정 하려면</span><span class="sxs-lookup"><span data-stu-id="a5b93-115">To anchor a control on a form</span></span>  
  
1.  <span data-ttu-id="a5b93-116">고정 하려는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-116">Select the control you want to anchor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a5b93-117">CTRL 키를 선택 하는 각 컨트롤을 누른 다음이 절차의 나머지 여 동시에 여러 컨트롤을 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-117">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>  
  
2.  <span data-ttu-id="a5b93-118">에 **속성** 창 오른쪽의 화살표를 클릭는 <xref:System.Windows.Forms.Control.Anchor%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-118">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>  
  
     <span data-ttu-id="a5b93-119">편집기는 십자형 표시가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-119">An editor is displayed that shows a cross.</span></span>  
  
3.  <span data-ttu-id="a5b93-120">앵커를 설정 하려면 위쪽, 왼쪽, 오른쪽 또는 맨 아래 섹션의 교차를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-120">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>  
  
     <span data-ttu-id="a5b93-121">컨트롤 위쪽에 고정 되며 기본적으로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-121">Controls are anchored to the top and left by default.</span></span>  
  
4.  <span data-ttu-id="a5b93-122">고정 된 컨트롤의 측면을 지우려면 십자형에서 해당 막대를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-122">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>  
  
5.  <span data-ttu-id="a5b93-123">닫습니다는 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 편집기 클릭는 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 이름을 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-123">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>  
  
 <span data-ttu-id="a5b93-124">런타임에 폼에 표시 되 면 폼의 가장자리 로부터 같은 거리에 위치를 유지 하도록 컨트롤 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-124">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="a5b93-125">고정된 된 가장자리에서의 거리는 항상 동일 하 게 유지 거리 Windows Forms 디자이너에 컨트롤을 배치 하는 경우 정의 된 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-125">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5b93-126">와 같은 특정 컨트롤에서 <xref:System.Windows.Forms.ComboBox> 는 높이에 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-126">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="a5b93-127">맨 아래 폼 이나 컨테이너 컨트롤을 고정 컨트롤의 높이 제한이을 강제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-127">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>  
  
 <span data-ttu-id="a5b93-128">상속 된 컨트롤 이어야 합니다 `Protected` 고정 되어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b93-128">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="a5b93-129">컨트롤의 액세스 수준을 변경 하려면 해당 `Modifiers` 속성에는 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="a5b93-129">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b93-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5b93-130">See Also</span></span>  
 [<span data-ttu-id="a5b93-131">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a5b93-131">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="a5b93-132">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="a5b93-132">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="a5b93-133">AutoSize 속성 개요</span><span class="sxs-lookup"><span data-stu-id="a5b93-133">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [<span data-ttu-id="a5b93-134">방법: Windows Forms에서 컨트롤 고정</span><span class="sxs-lookup"><span data-stu-id="a5b93-134">How to: Dock Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [<span data-ttu-id="a5b93-135">연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="a5b93-135">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="a5b93-136">연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="a5b93-136">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="a5b93-137">연습: Padding, Margins 및 AutoSize 속성을 사용하여 Windows Forms 컨트롤 레이아웃</span><span class="sxs-lookup"><span data-stu-id="a5b93-137">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
