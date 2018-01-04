---
title: "방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정"
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
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4be8ce245fdc17c55c03adb3d1e50f93b4e2a7e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="b2e5c-102">방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="b2e5c-102">How to: Format Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b2e5c-103">다음 절차를 사용 하 여 셀 값의 기본 형식을 보여 줍니다.는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 의 속성을 <xref:System.Windows.Forms.DataGridView> 컨트롤 및 컨트롤의 특정 열입니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-103">The following procedures demonstrate basic formatting of cell values using the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> property of a <xref:System.Windows.Forms.DataGridView> control and of specific columns in a control.</span></span> <span data-ttu-id="b2e5c-104">고급 데이터 형식에 대 한 정보를 참조 하십시오. [하는 방법: Windows Forms DataGridView 컨트롤에서 사용자 지정 데이터 형식](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-104">For information about advanced data formatting, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="to-format-currency-and-date-values"></a><span data-ttu-id="b2e5c-105">통화 서식 지정 및 날짜 값</span><span class="sxs-lookup"><span data-stu-id="b2e5c-105">To format currency and date values</span></span>  
  
-   <span data-ttu-id="b2e5c-106"><xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-106">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="b2e5c-107">사용 하 여 특정 열에 대 한 서식을 설정 하는 다음 코드 예제는 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 열 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-107">The following code example sets the format for specific columns using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the columns.</span></span> <span data-ttu-id="b2e5c-108">값에 `UnitPrice` 괄호로 묶어 음수 값을 갖는 열이 현재 culture 별 통화 형식으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-108">Values in the `UnitPrice` column appear in the current culture-specific currency format, with negative values surrounded by parentheses.</span></span> <span data-ttu-id="b2e5c-109">값에 `ShipDate` 열 현재 culture 별 간단한 날짜 형식에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-109">Values in the `ShipDate` column appear in the current culture-specific short date format.</span></span> <span data-ttu-id="b2e5c-110">에 대 한 자세한 내용은 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 값, 참조 [형식 지정](../../../../docs/standard/base-types/formatting-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-110">For more information about <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> values, see [Formatting Types](../../../../docs/standard/base-types/formatting-types.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a><span data-ttu-id="b2e5c-111">Null 데이터베이스 값의 표시를 사용자 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="b2e5c-111">To customize the display of null database values</span></span>  
  
-   <span data-ttu-id="b2e5c-112"><xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-112">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle>.</span></span> <span data-ttu-id="b2e5c-113">다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 동일한 값을 포함 하는 모든 셀에 "항목이"를 표시 하는 속성 <xref:System.DBNull.Value?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-113">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to display "no entry" in all cells containing values equal to <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a><span data-ttu-id="b2e5c-114">텍스트 기반 셀에 단어 잘림 방지를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="b2e5c-114">To enable wordwrap in text-based cells</span></span>  
  
-   <span data-ttu-id="b2e5c-115">설정의 <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> 속성은 <xref:System.Windows.Forms.DataGridViewCellStyle> 중 하나에 <xref:System.Windows.Forms.DataGridViewTriState> 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-115">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewTriState> enumeration values.</span></span> <span data-ttu-id="b2e5c-116">다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> 속성을 전체 컨트롤에 대 한 래핑 모드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-116">The following code example uses the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> property to set the wrap mode for the entire control.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a><span data-ttu-id="b2e5c-117">DataGridView 셀의 텍스트 맞춤을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="b2e5c-117">To specify the text alignment of DataGridView cells</span></span>  
  
-   <span data-ttu-id="b2e5c-118">설정의 <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> 속성은 <xref:System.Windows.Forms.DataGridViewCellStyle> 중 하나에 <xref:System.Windows.Forms.DataGridViewContentAlignment> 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-118">Set the <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> property of a <xref:System.Windows.Forms.DataGridViewCellStyle> to one of the <xref:System.Windows.Forms.DataGridViewContentAlignment> enumeration values.</span></span> <span data-ttu-id="b2e5c-119">사용 하 여 특정 열에 대 한 맞춤을 설정 하는 다음 코드 예제는 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 열의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-119">The following code example sets the alignment for a specific column using the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property of the column.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a><span data-ttu-id="b2e5c-120">예</span><span class="sxs-lookup"><span data-stu-id="b2e5c-120">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b2e5c-121">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b2e5c-121">Compiling the Code</span></span>  
 <span data-ttu-id="b2e5c-122">이러한 예제에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-122">These examples require:</span></span>  
  
-   <span data-ttu-id="b2e5c-123">A <xref:System.Windows.Forms.DataGridView> 라는 컨트롤 `dataGridView1` 라는 열이 포함 된 `UnitPrice`, 이라는 열 `ShipDate`, 및 라는 열 `CustomerName`합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-123">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `UnitPrice`, a column named `ShipDate`, and a column named `CustomerName`.</span></span>  
  
-   <span data-ttu-id="b2e5c-124"><xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="b2e5c-124">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b2e5c-125">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b2e5c-125">Robust Programming</span></span>  
 <span data-ttu-id="b2e5c-126">최대 확장성을 위해 공유 해야 <xref:System.Windows.Forms.DataGridViewCellStyle> 여러 행, 열 또는 셀 개별적으로 각 요소에 대 한 스타일 속성을 설정 하는 대신 동일한 스타일을 사용 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-126">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="b2e5c-127">자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 크기 조정에 대 한 유용한](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e5c-127">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2e5c-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2e5c-128">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 [<span data-ttu-id="b2e5c-129">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="b2e5c-129">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="b2e5c-130">Windows Forms DataGridView 컨트롤의 셀 스타일</span><span class="sxs-lookup"><span data-stu-id="b2e5c-130">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="b2e5c-131">Windows Forms DataGridView 컨트롤의 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="b2e5c-131">Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="b2e5c-132">방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b2e5c-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="b2e5c-133">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="b2e5c-133">Formatting Types</span></span>](../../../../docs/standard/base-types/formatting-types.md)
