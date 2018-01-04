---
title: "Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3fa5c240adaaf6512cfbd6b7bd0796bd0983a530
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="07303-102">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="07303-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="07303-103">`DataGridView` 컨트롤을 사용 하면 쉽게 셀의 기본 모양과 셀 값의 표시 형식을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07303-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="07303-104">모양을 정의할 수 있습니다 및 속성을 설정 하 여 개별 셀, 특정 열과 행의 셀 또는 컨트롤에 있는 모든 셀에 대 한 스타일 서식을 `DataGridViewCellStyle` 다양 한를 통해 액세스 되는 개체 `DataGridView` 속성을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="07303-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="07303-105">또한 처리 하 여 셀 값 등의 요인에 따라 동적으로 이러한 스타일을 수정할 수는 `CellFormatting` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="07303-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="07303-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="07303-106">In This Section</span></span>  
 [<span data-ttu-id="07303-107">방법: Windows Forms DataGridView 컨트롤의 테두리 및 모눈선 스타일 변경</span><span class="sxs-lookup"><span data-stu-id="07303-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="07303-108">설정 하는 방법에 설명 `DataGridView` 셀 사이의 경계 선과 컨트롤 테두리의 모양을 정의 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="07303-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="07303-109">Windows Forms DataGridView 컨트롤의 셀 스타일</span><span class="sxs-lookup"><span data-stu-id="07303-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="07303-110">설명의 `DataGridViewCellStyle` 클래스 및 해당 형식의 속성은 컨트롤에서 셀을 표시 하는 방법을 정의 하려면 상호 작용 하는 방법을 합니다.</span><span class="sxs-lookup"><span data-stu-id="07303-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="07303-111">방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="07303-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="07303-112">사용 하는 방법에 설명 `DataGridViewCellStyle` 전체 컨트롤 및 특정 행과 열에서 셀의 기본 모양을 정의 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="07303-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="07303-113">방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="07303-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="07303-114">사용 하 여 셀 표시 값의 형식을 지정 하는 방법을 설명 `DataGridViewCellStyle` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="07303-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="07303-115">방법: Windows Forms DataGridView 컨트롤의 글꼴 및 색 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="07303-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="07303-116">사용 하는 방법에 설명 된 `DefaultCellStyle` 속성을 기본 설정 컨트롤에 모든 셀에 대 한 특성을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="07303-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="07303-117">방법: Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="07303-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="07303-118">다르게 표시 되는 행에 번갈아 표시를 사용 하 여 컨트롤에서 장부와 비슷한 효과 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="07303-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="07303-119">방법: 행 템플릿을 사용하여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="07303-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="07303-120">사용 하는 방법에 설명 된 `RowTemplate` 속성을 컨트롤의 모든 행에 사용할 행 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07303-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="07303-121">참조</span><span class="sxs-lookup"><span data-stu-id="07303-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="07303-122"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="07303-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="07303-123">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="07303-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="07303-124">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="07303-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="07303-125">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="07303-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="07303-126">관련 단원</span><span class="sxs-lookup"><span data-stu-id="07303-126">Related Sections</span></span>  
 [<span data-ttu-id="07303-127">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="07303-127">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="07303-128"><xref:System.Windows.Forms.DataGridView> 셀 및 행의 사용자 지정 그리기를 수행하고 파생된 셀, 열 및 행 형식을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="07303-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="07303-129">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="07303-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="07303-130">셀, 행 및 열 속성을 사용 하는 일반적으로 설명 하는 항목을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="07303-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07303-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07303-131">See Also</span></span>  
 [<span data-ttu-id="07303-132">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="07303-132">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
