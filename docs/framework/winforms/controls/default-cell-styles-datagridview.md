---
title: "방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 기본 셀 스타일 및 데이터 형식 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65f876742526d13093a852e99f4e6a069c3fba47
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="3af87-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 기본 셀 스타일 및 데이터 형식 설정</span><span class="sxs-lookup"><span data-stu-id="3af87-102">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="3af87-103"><xref:System.Windows.Forms.DataGridView> 제어를 사용 하면 기본 셀 스타일을 지정 하 고 셀 데이터 형식을 전체 컨트롤에 대 한, 특정 열에 대 한, 행 및 열 머리글에 대 한 대체 행 원장 효과를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-103">The <xref:System.Windows.Forms.DataGridView> control lets you specify default cell styles and cell data formats for the entire control, for specific columns, for row and column headers, and for alternating rows to create a ledger effect.</span></span> <span data-ttu-id="3af87-104">전체 컨트롤에 대해 설정 하는 기본 스타일은 기본적으로 열과 대체 행 스타일 설정 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-104">Default styles set for the entire control are overridden by default styles set for columns and alternating rows.</span></span> <span data-ttu-id="3af87-105">또한 개별 행 및 열에 대 한 코드에서 설정한 기본 스타일을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-105">Additionally, styles that you set in code for individual rows and cells override the default styles.</span></span>  
  
 <span data-ttu-id="3af87-106">셀 스타일에 대 한 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-106">For more information about cell styles, see [Cell Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="3af87-107">교대로 반복 되는 행에 대 한 스타일을 설정 하려면 참조 [하는 방법:는 Windows Forms DataGridView 컨트롤 사용 하 여 디자이너에 교대로 반복 되는 행 스타일 설정](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-107">To set styles for alternating rows, see [How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span></span>  
  
 <span data-ttu-id="3af87-108">사용 하 여 스타일을 설정할 수도 있습니다는 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 속성을 컨트롤에 추가 될 모든 행에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-108">You can also set styles using the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property to affect all rows that will be added to the control.</span></span> <span data-ttu-id="3af87-109">행 템플릿에 대 한 자세한 내용은 참조 [하는 방법: Windows Forms DataGridView 컨트롤에서 사용자 지정 행을 행 템플릿을 사용](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-109">For more information about the row template, see [How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md).</span></span>  
  
 <span data-ttu-id="3af87-110">다음 절차를 필요는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-110">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3af87-111">이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-111">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3af87-112">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3af87-113">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3af87-114">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3af87-114">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-default-styles-for-all-cells-in-the-control"></a><span data-ttu-id="3af87-115">컨트롤의 모든 셀에 대 한 기본 스타일을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="3af87-115">To set default styles for all cells in the control</span></span>  
  
1.  <span data-ttu-id="3af87-116">선택 된 <xref:System.Windows.Forms.DataGridView> 디자이너에서 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-116">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>  
  
2.  <span data-ttu-id="3af87-117">에 **속성** 창에서 줄임표 단추를 클릭 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, 또는 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-117">In the **Properties** window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> property.</span></span> <span data-ttu-id="3af87-118">**CellStyle 작성기** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-118">The **CellStyle Builder** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="3af87-119">사용 하 여 속성을 설정 하 여 스타일을 정의 하는 **미리 보기** 선택 사항을 확인 하는 창입니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-119">Define the style by setting the properties, using the **Preview** pane to confirm your choices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3af87-120">비주얼 스타일을 사용 하는 경우 행 및 열 머리글 (제외 하 고는 <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>)는 현재 테마에 따라 자동으로 스타일이 지정 재정의 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 및 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 속성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-120">If visual styles are enabled, the row and column headers (except for the <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) are automatically styled by the current theme, overriding the <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> property values.</span></span>  
>   
>  <span data-ttu-id="3af87-121">선택한 여러에 대 한 셀 스타일을 설정할 수 있습니다 <xref:System.Windows.Forms.DataGridView> 만 디자이너를 사용 하 여 수정 하려는 셀 스타일 속성에 대 한 동일한 값이 있는 경우를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-121">You can set cell styles for multiple selected <xref:System.Windows.Forms.DataGridView> controls using the designer, but only if they have identical values for the cell style property you want to modify.</span></span> <span data-ttu-id="3af87-122">해당 속성에 대 한 셀 스타일 다른 경우는 **속성** 의 창이 **CellStyle 작성기** 대화 상자가 비어 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-122">If any cell styles differ for that property, the **Properties** windows of the **CellStyle Builder** dialog box will be blank.</span></span>  
  
### <a name="to-set-default-styles-for-cells-in-individual-columns"></a><span data-ttu-id="3af87-123">개별 열에 기본 셀 스타일을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="3af87-123">To set default styles for cells in individual columns</span></span>  
  
1.  <span data-ttu-id="3af87-124">마우스 오른쪽 단추로 클릭는 <xref:System.Windows.Forms.DataGridView> 디자이너에서 제어 하 고 선택 **열 편집**합니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-124">Right-click the <xref:System.Windows.Forms.DataGridView> control in the designer and choose **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="3af87-125">열을 선택 된 **선택한 열** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-125">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="3af87-126">에 **열 속성** 그리드, 줄임표 단추를 클릭 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-126">In the **Column Properties** grid, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property.</span></span> <span data-ttu-id="3af87-127">**CellStyle 작성기** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-127">The **CellStyle Builder** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="3af87-128">사용 하 여 속성을 설정 하 여 스타일을 정의 하는 **미리 보기** 선택 사항을 확인 하는 창입니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-128">Define the style by setting the properties, using the **Preview** pane to confirm your choices.</span></span>  
  
### <a name="to-format-data-in-cells"></a><span data-ttu-id="3af87-129">셀의 데이터 서식을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="3af87-129">To format data in cells</span></span>  
  
1.  <span data-ttu-id="3af87-130">앞의 절차 중 하나를 사용 하 여 표시 하는 **CellStyle 작성기** 대화 상자에 기본 셀 스타일 속성이 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-130">Use one of the preceding procedures to display a **CellStyle Builder** dialog box related to a default cell style property.</span></span>  
  
2.  <span data-ttu-id="3af87-131">에 **CellStyle 작성기** 대화 상자에서 줄임표 단추를 클릭 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-131">In the **CellStyle Builder** dialog box, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property.</span></span> <span data-ttu-id="3af87-132">**형식 문자열** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-132">The **Format String** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="3af87-133">형식 유형을 선택한 다음 형식 (예: 개수 표시 하려면 소수 자릿수)의 세부 정보를 수정를 사용 하는 **샘플** 선택 사항을 확인 하는 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-133">Select a format type, then modify the details of the type (such as the number of decimal places to display), using the **Sample** box to confirm your choices.</span></span>  
  
4.  <span data-ttu-id="3af87-134">바인딩하는 경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤 입력, null 값을 포함할 가능성이 있는 데이터 소스는 **Null 값** 입력란.</span><span class="sxs-lookup"><span data-stu-id="3af87-134">If you are binding the <xref:System.Windows.Forms.DataGridView> control to a data source that is likely to contain null values, fill in the **Null Value** text box.</span></span> <span data-ttu-id="3af87-135">이 값을 null 참조 셀 값이 같은 경우에 표시 됩니다 (`Nothing` Visual basic에서) 또는 <xref:System.DBNull.Value?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="3af87-135">This value is displayed when the cell value is equal to a null reference (`Nothing` in Visual Basic) or <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3af87-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3af87-136">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="3af87-137">Windows Forms DataGridView 컨트롤의 셀 스타일</span><span class="sxs-lookup"><span data-stu-id="3af87-137">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="3af87-138">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="3af87-138">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="3af87-139">방법: Windows 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="3af87-139">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="3af87-140">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="3af87-140">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
