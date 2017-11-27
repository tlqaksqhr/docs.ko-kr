---
title: "방법: Windows Forms DataGridView 컨트롤의 셀 변경 내용에 따라 사용자 지정 작업 수행"
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
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7f81cf7df0272a1b90de77332712b3b8a9e202de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a><span data-ttu-id="fe904-102">방법: Windows Forms DataGridView 컨트롤의 셀 변경 내용에 따라 사용자 지정 작업 수행</span><span class="sxs-lookup"><span data-stu-id="fe904-102">How to: Perform a Custom Action Based on Changes in a Cell of a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fe904-103"><xref:System.Windows.Forms.DataGridView> 컨트롤의 상태 변경을 감지 하는 동안 사용할 수 있는 이벤트의 개수가 <xref:System.Windows.Forms.DataGridView> 셀입니다.</span><span class="sxs-lookup"><span data-stu-id="fe904-103">The <xref:System.Windows.Forms.DataGridView> control has a number of events you can use to detect changes in the state of <xref:System.Windows.Forms.DataGridView> cells.</span></span> <span data-ttu-id="fe904-104">가장 일반적으로 사용 되는 두 가지는 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 및 <xref:System.Windows.Forms.DataGridView.CellStateChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="fe904-104">Two of the most commonly used are the <xref:System.Windows.Forms.DataGridView.CellValueChanged> and <xref:System.Windows.Forms.DataGridView.CellStateChanged> events.</span></span>  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a><span data-ttu-id="fe904-105">DataGridView 셀의 값에 변경 내용을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="fe904-105">To detect changes in the values of DataGridView cells</span></span>  
  
-   <span data-ttu-id="fe904-106">에 대 한 처리기를 작성 하는 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="fe904-106">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellValueChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a><span data-ttu-id="fe904-107">DataGridView 셀의 상태에 변경 내용을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="fe904-107">To detect changes in the states of DataGridView cells</span></span>  
  
-   <span data-ttu-id="fe904-108">에 대 한 처리기를 작성 하는 <xref:System.Windows.Forms.DataGridView.CellStateChanged> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="fe904-108">Write a handler for the <xref:System.Windows.Forms.DataGridView.CellStateChanged> event.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fe904-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="fe904-109">Compiling the Code</span></span>  
 <span data-ttu-id="fe904-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fe904-110">This example requires:</span></span>  
  
-   <span data-ttu-id="fe904-111">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fe904-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span> <span data-ttu-id="fe904-112">C#에 대 한 이벤트 처리기가 해당 이벤트에 연결 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe904-112">For C#, the event handlers must be connected to the corresponding events.</span></span>  
  
-   <span data-ttu-id="fe904-113"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="fe904-113">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe904-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe904-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>  
 [<span data-ttu-id="fe904-115">Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="fe904-115">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 [<span data-ttu-id="fe904-116">연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="fe904-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
