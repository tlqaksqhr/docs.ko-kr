---
title: "방법: Windows Forms DataGridView 컨트롤에서 열 고정"
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
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], freezing columns
- DataGridView control [Windows Forms], columns always in view
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f85930731daa223fda8353f295e631c33bda5144
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="7a12d-102">방법: Windows Forms DataGridView 컨트롤에서 열 고정</span><span class="sxs-lookup"><span data-stu-id="7a12d-102">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="7a12d-103">사용자가 Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시된 데이터를 볼 때 단일 열이나 열 집합을 자주 참조해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a12d-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="7a12d-104">예를 들어 많은 열이 포함된 고객 정보 테이블을 표시하는 경우 다른 열을 표시되는 영역 바깥으로 스크롤할 수 있게 하면서 고객 이름은 항상 표시하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a12d-104">For example, when displaying a table of customer information that contains many columns, it is useful to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>  
  
 <span data-ttu-id="7a12d-105">이 동작을 얻기 위해 컨트롤에서 열을 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a12d-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="7a12d-106">열을 고정하는 경우 왼쪽(또는 오른쪽에서 왼쪽 언어 스크립트의 경우 오른쪽)에 있는 모든 열도 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a12d-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="7a12d-107">다른 모든 열을 스크롤할 수 있는 동안 고정된 열은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a12d-107">Frozen columns remain in place while all other columns can scroll.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a12d-108">열 다시 정렬을 사용하는 경우 고정된 열은 고정되지 않은 열과 별개인 그룹으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a12d-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="7a12d-109">사용자는 각 그룹에서 열의 위치를 변경할 수 있지만 그룹 간에 열을 이동할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a12d-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>  
  
 <span data-ttu-id="7a12d-110">열의 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> 속성은 표에서 열이 항상 표시되는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a12d-110">The <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property of a column determines whether the column is always visible within the grid.</span></span>  
  
 <span data-ttu-id="7a12d-111">Visual Studio에서는 이 작업이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a12d-111">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="7a12d-112">또한 참조 [하는 방법:는 Windows Forms DataGridView 컨트롤 사용 하 여 디자이너에서 열 고정](http://msdn.microsoft.com/library/717ss6s6\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="7a12d-112">Also see [How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer](http://msdn.microsoft.com/library/717ss6s6\(v=vs.110\)).</span></span>  
  
### <a name="to-freeze-a-column-programmatically"></a><span data-ttu-id="7a12d-113">프로그래밍 방식으로 열을 고정하려면</span><span class="sxs-lookup"><span data-stu-id="7a12d-113">To freeze a column programmatically</span></span>  
  
-   <span data-ttu-id="7a12d-114"><xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a12d-114">Set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7a12d-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7a12d-115">Compiling the Code</span></span>  
 <span data-ttu-id="7a12d-116">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7a12d-116">This example requires:</span></span>  
  
-   <span data-ttu-id="7a12d-117">이름이 `AddToCartButton`인 열을 포함하는 이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7a12d-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `AddToCartButton`.</span></span>  
  
-   <span data-ttu-id="7a12d-118"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="7a12d-118">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a12d-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a12d-119">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="7a12d-120">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="7a12d-120">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [<span data-ttu-id="7a12d-121">방법: Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용</span><span class="sxs-lookup"><span data-stu-id="7a12d-121">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)
