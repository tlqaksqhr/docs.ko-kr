---
title: Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], elements
- columns [Windows Forms], data grids
- cells [Windows Forms], data grids
- DataGridView control [Windows Forms], programming with grid elements
- rows [Windows Forms], data grids
ms.assetid: 0d76f7e4-4149-42c6-9118-bb37d6669dc5
ms.openlocfilehash: f87d1e2744ffcd81f5711991880deb1fe5edd2a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538543"
---
# <a name="programming-with-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="42301-102">Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="42301-102">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="42301-103">이 섹션에서는 셀, 행 및 열 개체를 관련 된 다양 한 프로그래밍 작업을 보여 주는 항목을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="42301-103">This section provides topics that demonstrate various programming tasks involving cell, row, and column objects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="42301-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="42301-104">In This Section</span></span>  
 [<span data-ttu-id="42301-105">방법: Windows Forms DataGridView 컨트롤에서 개별 셀에 도구 설명 추가</span><span class="sxs-lookup"><span data-stu-id="42301-105">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/add-tooltips-to-individual-cells-in-a-wf-datagridview-control.md)  
 <span data-ttu-id="42301-106">처리 하는 방법에 설명 된 <xref:System.Windows.Forms.DataGridView.CellFormatting> 개별 셀에 대 한 다양 한 도구 설명을 제공 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="42301-106">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting> event to provide different ToolTips for individual cells.</span></span>  
  
 [<span data-ttu-id="42301-107">방법: Windows Forms DataGridView 컨트롤의 셀 변경 내용에 따라 사용자 지정 작업 수행</span><span class="sxs-lookup"><span data-stu-id="42301-107">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/perform-a-custom-action-based-on-changes-in-a-cell-of-a-datagrid.md)  
 <span data-ttu-id="42301-108">처리 하는 방법에 설명 된 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 및 <xref:System.Windows.Forms.DataGridView.CellStateChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="42301-108">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
 [<span data-ttu-id="42301-109">방법: Windows Forms DataGridView 컨트롤에서 밴드 조작</span><span class="sxs-lookup"><span data-stu-id="42301-109">How to: Manipulate Bands in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-manipulate-bands-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="42301-110">형식의 개체를 사용 하 여 프로그래밍 하는 방법을 설명 <xref:System.Windows.Forms.DataGridViewBand>, 행과 열에 대 한 기본 형식입니다.입니다.</span><span class="sxs-lookup"><span data-stu-id="42301-110">Describes how to program with objects of type <xref:System.Windows.Forms.DataGridViewBand>, which is the base type for rows and columns.</span></span>  
  
 [<span data-ttu-id="42301-111">방법: Windows Forms DataGridView 컨트롤에서 행 조작</span><span class="sxs-lookup"><span data-stu-id="42301-111">How to: Manipulate Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-manipulate-rows-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="42301-112">형식의 개체를 사용 하 여 프로그래밍 하는 방법을 설명 `DataGridViewRow`합니다.</span><span class="sxs-lookup"><span data-stu-id="42301-112">Describes how to program with objects of type `DataGridViewRow`.</span></span>  
  
 [<span data-ttu-id="42301-113">방법: Windows Forms DataGridView 컨트롤에서 열 조작</span><span class="sxs-lookup"><span data-stu-id="42301-113">How to: Manipulate Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-manipulate-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="42301-114">형식의 개체를 사용 하 여 프로그래밍 하는 방법을 설명 `DataGridViewColumn`합니다.</span><span class="sxs-lookup"><span data-stu-id="42301-114">Describes how to program with objects of type `DataGridViewColumn`.</span></span>  
  
 [<span data-ttu-id="42301-115">방법: Windows Forms DataGridView 컨트롤에서 이미지 열 작업</span><span class="sxs-lookup"><span data-stu-id="42301-115">How to: Work with Image Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-work-with-image-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="42301-116">사용 하 여 프로그래밍 하는 방법에 설명 된 `DataGridViewImageColumn` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="42301-116">Describes how to program with the `DataGridViewImageColumn` class.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="42301-117">참조</span><span class="sxs-lookup"><span data-stu-id="42301-117">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="42301-118"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="42301-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="42301-119">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewCell> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="42301-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="42301-120">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewRow> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="42301-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="42301-121">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewColumn> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="42301-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="42301-122">관련 단원</span><span class="sxs-lookup"><span data-stu-id="42301-122">Related Sections</span></span>  
 [<span data-ttu-id="42301-123">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="42301-123">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="42301-124">셀, 행 및 열 속성을 사용 하는 일반적으로 설명 하는 항목을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="42301-124">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42301-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42301-125">See Also</span></span>  
 [<span data-ttu-id="42301-126">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="42301-126">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="42301-127">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="42301-127">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
