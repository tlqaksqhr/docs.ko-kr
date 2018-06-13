---
title: '방법: Windows Forms DataGridView 컨트롤의 셀 변경 내용에 따라 사용자 지정 작업 수행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: 3de58c1dd87d890f089366e6e85041f2983acc64
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535147"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a><span data-ttu-id="5449c-102">방법: Windows Forms DataGridView 컨트롤의 셀 변경 내용에 따라 사용자 지정 작업 수행</span><span class="sxs-lookup"><span data-stu-id="5449c-102">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5449c-103"><xref:System.Windows.Forms.DataGridView> 컨트롤의 상태 변경을 감지 하는 동안 사용할 수 있는 이벤트의 개수가 <xref:System.Windows.Forms.DataGridView> 셀입니다.</span><span class="sxs-lookup"><span data-stu-id="5449c-103">The <xref:System.Windows.Forms.DataGridView> control has a number of events you can use to detect changes in the state of <xref:System.Windows.Forms.DataGridView> cells.</span></span> <span data-ttu-id="5449c-104">가장 일반적으로 사용 되는 두 가지는 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 및 <xref:System.Windows.Forms.DataGridView.CellStateChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="5449c-104">Two of the most commonly used are the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a><span data-ttu-id="5449c-105">DataGridView 셀의 값에 변경 내용을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="5449c-105">To detect changes in the values of DataGridView cells</span></span>  
  
-   <span data-ttu-id="5449c-106">에 대 한 처리기를 작성 하는 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="5449c-106">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellValueChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a><span data-ttu-id="5449c-107">DataGridView 셀의 상태에 변경 내용을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="5449c-107">To detect changes in the states of DataGridView cells</span></span>  
  
-   <span data-ttu-id="5449c-108">에 대 한 처리기를 작성 하는 <xref:System.Windows.Forms.DataGridView.CellStateChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="5449c-108">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellStateChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5449c-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5449c-109">Compiling the Code</span></span>  
 <span data-ttu-id="5449c-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5449c-110">This example requires:</span></span>  
  
-   <span data-ttu-id="5449c-111">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5449c-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span> <span data-ttu-id="5449c-112">C#에 대 한 이벤트 처리기가 해당 이벤트에 연결 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5449c-112">For C#, the event handlers must be connected to the corresponding events.</span></span>  
  
-   <span data-ttu-id="5449c-113"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="5449c-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5449c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5449c-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>  
 [<span data-ttu-id="5449c-115">Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="5449c-115">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 [<span data-ttu-id="5449c-116">연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="5449c-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
