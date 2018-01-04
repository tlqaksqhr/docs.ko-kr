---
title: "Windows Forms DataGridView 컨트롤 사용자 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 348651784ef2b4d99679038a1875fc6650688a6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="e542d-102">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e542d-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e542d-103">`DataGridView` 컨트롤은 모양과 해당 셀, 행 및 열의 기본 동작 (모양 및 느낌)를 조정 하는 데 사용할 수 있는 몇 가지 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e542d-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="e542d-104">기능 이외에 특별 한 요구 사항이 있으면는 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스, 있지만 수 또한 소유자 그리기 컨트롤에 대 한 구현 하거나 사용자 지정 셀, 열 및 행을 만들어 기능을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e542d-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="e542d-105">그릴 셀 및 행 직접 다양 한 처리할 수 있습니다 `DataGridView` 그리기 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e542d-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="e542d-106">를 기존 기능을 수정 하거나 새로운 기능을 제공 하려면 기존에서 파생 된 형식을 사용자를 만들 수 있습니다 `DataGridViewCell`, `DataGridViewColumn`, 및 `DataGridViewRow` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e542d-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="e542d-107">또한 선택한 셀이 편집 모드일 때 컨트롤을 표시 하는 파생된 형식을 만들면 새 편집 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e542d-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e542d-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="e542d-108">In This Section</span></span>  
 [<span data-ttu-id="e542d-109">방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e542d-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="e542d-110">처리 하는 방법에 설명 된 <xref:System.Windows.Forms.DataGridView.CellPainting> 셀을 수동으로 그리기 위해 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e542d-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="e542d-111">방법: Windows Forms DataGridView 컨트롤에서 행 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e542d-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="e542d-112">처리 하는 방법에 설명 된 <xref:System.Windows.Forms.DataGridView.RowPrePaint> 및 <xref:System.Windows.Forms.DataGridView.RowPostPaint> 이벤트는 사용자 지정, 그라데이션 배경의 행을 그릴 하 고는 콘텐츠의 하기 위해 여러 열에 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e542d-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="e542d-113">방법: Windows Forms DataGridView 컨트롤에서 동작 및 모양을 확장하여 셀과 열 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e542d-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="e542d-114">파생 된 사용자 정의 형식을 만드는 방법을 설명 `DataGridViewCell` 및 `DataGridViewColumn` 에 마우스 포인터를 놓으면 셀을 강조 표시 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="e542d-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="e542d-115">방법: Windows Forms DataGridView 컨트롤의 단추 열에서 단추 비활성화</span><span class="sxs-lookup"><span data-stu-id="e542d-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="e542d-116">파생 된 사용자 정의 형식을 만드는 방법을 설명 <xref:System.Windows.Forms.DataGridViewButtonCell> 및 <xref:System.Windows.Forms.DataGridViewButtonColumn> 단추 열에서 비활성화 된 단추를 표시 하기 위해 합니다.</span><span class="sxs-lookup"><span data-stu-id="e542d-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="e542d-117">방법: Windows Forms DataGridView 셀에서 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="e542d-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="e542d-118">구현 하는 방법에 설명는 `IDataGridViewEditingControl` 인터페이스 및에서 파생 된 사용자 지정 형식을 만들 `DataGridViewCell` 및 `DataGridViewColumn` 표시 하기 위해는 <xref:System.Windows.Forms.DateTimePicker> 때 셀이 편집 모드를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="e542d-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e542d-119">참조</span><span class="sxs-lookup"><span data-stu-id="e542d-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="e542d-120"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e542d-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="e542d-121">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewCell> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e542d-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="e542d-122">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewRow> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e542d-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="e542d-123">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewColumn> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e542d-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="e542d-124">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.IDataGridViewEditingControl> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e542d-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e542d-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="e542d-125">Related Sections</span></span>  
 [<span data-ttu-id="e542d-126">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="e542d-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e542d-127">컨트롤의 기본 모양과 셀 데이터의 표시 형식을 수정하는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e542d-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e542d-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e542d-128">See Also</span></span>  
 [<span data-ttu-id="e542d-129">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="e542d-129">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="e542d-130">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="e542d-130">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
