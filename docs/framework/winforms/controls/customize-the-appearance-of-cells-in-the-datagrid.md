---
title: '방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 73f93fb2ccbcbe55f2c3a8fa78f509b012956515
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528683"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="90da8-102">방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="90da8-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="90da8-103">처리 하 여 모든 셀의 모양을 사용자 지정할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellPainting> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="90da8-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="90da8-104">추출할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Drawing.Graphics> 에서 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> 의 속성은 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>합니다.</span><span class="sxs-lookup"><span data-stu-id="90da8-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="90da8-105">이 <xref:System.Drawing.Graphics>, 전체의 모양에 영향을 줄 수 <xref:System.Windows.Forms.DataGridView> 컨트롤 있지만 일반적으로 현재 칠하고 있는 셀의 모양에만 영향을 줄 합니다.</span><span class="sxs-lookup"><span data-stu-id="90da8-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="90da8-106"><xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> 의 속성은 <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> 그리기 작업을 현재 칠하고 있는 셀을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90da8-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="90da8-107">다음 코드 예제에서는 모든 셀을 그리도록는 `ContactName` 사용 하 여 열 여 <xref:System.Windows.Forms.DataGridView> 컨트롤의 색 구성표입니다.</span><span class="sxs-lookup"><span data-stu-id="90da8-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="90da8-108">각 셀의 텍스트 내용에 그려질 때 <xref:System.Drawing.Color.Crimson%2A>, 동일한 색으로에서 삽입 사각형이 그려집니다 및는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.GridColor%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="90da8-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90da8-109">예제</span><span class="sxs-lookup"><span data-stu-id="90da8-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="90da8-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="90da8-110">Compiling the Code</span></span>  
 <span data-ttu-id="90da8-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="90da8-111">This example requires:</span></span>  
  
-   <span data-ttu-id="90da8-112">A <xref:System.Windows.Forms.DataGridView> 라는 컨트롤 `dataGridView1` 와 `ContactName` Northwind 샘플 데이터베이스의 Customers 테이블에 같은 열입니다.</span><span class="sxs-lookup"><span data-stu-id="90da8-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
-   <span data-ttu-id="90da8-113">System, System.Windows.Forms 및 System.Drawing 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="90da8-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90da8-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90da8-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellPainting>  
 [<span data-ttu-id="90da8-115">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="90da8-115">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
