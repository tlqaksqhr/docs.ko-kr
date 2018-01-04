---
title: "방법: Windows Forms에 컨트롤 도킹"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc7227ee46f127070b44771a56a89b82bd0930ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="99547-102">방법: Windows Forms에 컨트롤 도킹</span><span class="sxs-lookup"><span data-stu-id="99547-102">How to: Dock Controls on Windows Forms</span></span>
<span data-ttu-id="99547-103">폼의 가장자리에 컨트롤을 도킹 하거나 컨트롤의 컨테이너 (폼 또는 컨테이너 컨트롤)을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99547-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="99547-104">Windows 탐색기 창을 도킹 하는 예를 들어 해당 <xref:System.Windows.Forms.TreeView> 컨트롤 창의 왼쪽 가장자리와 해당 <xref:System.Windows.Forms.ListView> 컨트롤 창의 왼쪽에서 오른쪽으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="99547-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="99547-105">사용 된 <xref:System.Windows.Forms.Control.Dock%2A> 표시 하는 모든 Windows Forms 컨트롤 도킹 모드를 정의 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="99547-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99547-106">역방향 z-순서에 컨트롤 도킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99547-106">Controls are docked in reverse z-order.</span></span>  
  
 <span data-ttu-id="99547-107"><xref:System.Windows.Forms.Control.Dock%2A> 속성와 상호 작용 하는 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="99547-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="99547-108">자세한 내용은 참조 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="99547-108">For more information, see [AutoSize Property Overview](../../../../docs/framework/winforms/controls/autosize-property-overview.md).</span></span>  
  
### <a name="to-dock-a-control"></a><span data-ttu-id="99547-109">컨트롤을 도킹 하려면</span><span class="sxs-lookup"><span data-stu-id="99547-109">To dock a control</span></span>  
  
1.  <span data-ttu-id="99547-110">컨트롤을 도킹 하려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="99547-110">Select the control that you want to dock.</span></span>  
  
2.  <span data-ttu-id="99547-111">속성 창에서 오른쪽의 화살표를 클릭 하 고 <xref:System.Windows.Forms.Control.Dock%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="99547-111">In the Properties window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="99547-112">일련의 가장자리와 폼의 중심을 나타내는 상자를 표시 하는 편집기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99547-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>  
  
3.  <span data-ttu-id="99547-113">도킹 된 컨트롤을 폼의 가장자리를 나타내는 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99547-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="99547-114">컨트롤의 폼 이나 컨테이너 컨트롤의 내용을 채울 센터 상자를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99547-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="99547-115">클릭 **(없음)** 도킹 하지 않으려면입니다.</span><span class="sxs-lookup"><span data-stu-id="99547-115">Click **(none)** to disable docking.</span></span>  
  
     <span data-ttu-id="99547-116">컨트롤은 자동으로 도킹된 된 가장자리의 경계에 맞게 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99547-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="99547-117">상속 된 컨트롤 이어야 합니다 `Protected` 도킹 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99547-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="99547-118">컨트롤의 액세스 수준을 변경 하려면 해당 **한정자** 속성 창에서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="99547-118">To change the access level of a control, set its **Modifier** property in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99547-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99547-119">See Also</span></span>  
 [<span data-ttu-id="99547-120">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="99547-120">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="99547-121">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="99547-121">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="99547-122">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="99547-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="99547-123">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="99547-123">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="99547-124">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="99547-124">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [<span data-ttu-id="99547-125">방법: FlowLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="99547-125">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="99547-126">방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="99547-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="99547-127">AutoSize 속성 개요</span><span class="sxs-lookup"><span data-stu-id="99547-127">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [<span data-ttu-id="99547-128">방법: Windows Forms에서 컨트롤 고정</span><span class="sxs-lookup"><span data-stu-id="99547-128">How to: Anchor Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)
