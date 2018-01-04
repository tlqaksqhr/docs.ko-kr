---
title: "방법: Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정"
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
- DataGridView control [Windows Forms], row styles
- data grids [Windows Forms], row styles
- rows [Windows Forms], data grids
ms.assetid: 699ef759-458c-426d-ac87-7c7e71b018ae
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c6e6b8938bfb2595f80ee71146d1de817cc9bcfd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="d876e-102">방법: Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="d876e-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d876e-103">대체로 테이블 형식 데이터는 교대로 반복되는 행의 배경색이 서로 다른 장부와 비슷한 형식으로 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d876e-103">Tabular data is often presented to users in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="d876e-104">이 형식을 사용하면 특히 많은 열을 포함하는 넓은 테이블에서 사용자가 각 행에 있는 셀을 쉽게 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d876e-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>  
  
 <span data-ttu-id="d876e-105"><xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하여 교대로 반복되는 행에 대한 전체 스타일 정보를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d876e-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="d876e-106">이 경우 배경색 외에도 전경색 및 글꼴과 같은 스타일 특성을 사용하여 교대로 반복되는 행을 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d876e-106">This enables you use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span>  
  
 <span data-ttu-id="d876e-107">Visual Studio에서는 이 작업이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d876e-107">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="d876e-108">또한 참조 [하는 방법:는 Windows Forms DataGridView 컨트롤 사용 하 여 디자이너에 교대로 반복 되는 행 스타일 설정](http://msdn.microsoft.com/library/3z9sk148\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="d876e-108">Also see [How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer](http://msdn.microsoft.com/library/3z9sk148\(v=vs.110\)).</span></span>  
  
### <a name="to-set-alternating-row-styles-programmatically"></a><span data-ttu-id="d876e-109">프로그래밍 방식으로 교대로 반복되는 행 스타일을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="d876e-109">To set alternating row styles programmatically</span></span>  
  
-   <span data-ttu-id="d876e-110"><xref:System.Windows.Forms.DataGridView>의 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 및 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> 속성에서 반환된 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체의 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d876e-110">Set the properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> objects returned by the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties of the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#068)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#068)]  
  
    > [!NOTE]
    >  <span data-ttu-id="d876e-111"><xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 및 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> 속성을 사용하여 지정된 스타일은 열과 <xref:System.Windows.Forms.DataGridView> 수준에 지정된 스타일을 재정의하지만 개별 행 및 셀 수준에서 설정된 스타일에 의해 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d876e-111">The styles specified using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> properties override the styles specified on the column and <xref:System.Windows.Forms.DataGridView> level, but are overridden by the styles set on the individual row and cell level.</span></span> <span data-ttu-id="d876e-112">자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d876e-112">For more information, see [Cell Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d876e-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d876e-113">Compiling the Code</span></span>  
 <span data-ttu-id="d876e-114">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d876e-114">This example requires:</span></span>  
  
-   <span data-ttu-id="d876e-115">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d876e-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="d876e-116"><xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="d876e-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d876e-117">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="d876e-117">Robust Programming</span></span>  
 <span data-ttu-id="d876e-118">최대 확장성을 얻으려면 각 요소에 대한 스타일 속성을 별도로 설정하는 대신 동일한 스타일을 사용하는 여러 행, 열 또는 셀에서 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체를 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d876e-118">For maximum scalability, you should share <xref:System.Windows.Forms.DataGridViewCellStyle> objects across multiple rows, columns, or cells that use the same styles, rather than setting the style properties for each element separately.</span></span> <span data-ttu-id="d876e-119">자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 크기 조정에 대 한 유용한](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d876e-119">For more information, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d876e-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d876e-120">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 [<span data-ttu-id="d876e-121">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="d876e-121">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="d876e-122">Windows Forms DataGridView 컨트롤의 셀 스타일</span><span class="sxs-lookup"><span data-stu-id="d876e-122">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="d876e-123">Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="d876e-123">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="d876e-124">방법: Windows Forms DataGridView 컨트롤의 글꼴 및 색 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="d876e-124">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)
