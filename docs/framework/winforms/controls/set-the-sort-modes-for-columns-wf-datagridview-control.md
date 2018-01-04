---
title: "방법: Windows Forms DataGridView 컨트롤의 열 정렬 모드 설정"
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
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a8571209ea0a80a64c1f30336c9a52b1bc79622
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="b2b9f-102">방법: Windows Forms DataGridView 컨트롤의 열 정렬 모드 설정</span><span class="sxs-lookup"><span data-stu-id="b2b9f-102">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b2b9f-103">에 <xref:System.Windows.Forms.DataGridView> 컨트롤, 텍스트 상자 열에서는 다른 형식의 열이 자동으로 정렬 되지 않는 동안 기본적으로 자동 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2b9f-103">In the <xref:System.Windows.Forms.DataGridView> control, text box columns use automatic sorting by default, while other column types are not sorted automatically.</span></span> <span data-ttu-id="b2b9f-104">이 기본값을 재정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2b9f-104">Sometimes you will want to override these defaults.</span></span> <span data-ttu-id="b2b9f-105">예를 들어, 텍스트, 숫자 또는 열거형 셀 값 대신 이미지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2b9f-105">For example, you can display images in place of text, numbers, or enumeration cell values.</span></span> <span data-ttu-id="b2b9f-106">이미지를 정렬할 수 있어야 하는 동안에 나타내는 내부 값을 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2b9f-106">While the images cannot be sorted, the underlying values that they represent can be sorted.</span></span>  
  
 <span data-ttu-id="b2b9f-107">에 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 열의 속성 값의 정렬 동작을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2b9f-107">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property value of a column determines its sorting behavior.</span></span>  
  
 <span data-ttu-id="b2b9f-108">에서는 다음 절차는 `Priority` 열에서 [하는 방법: Windows Forms DataGridView 컨트롤에서 사용자 지정 데이터 형식](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2b9f-108">The following procedure shows the `Priority` column from [How to: Customize Data Formatting in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="b2b9f-109">이 열은 이미지 열 이므로 기본적으로 정렬 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2b9f-109">This column is an image column and is not sortable by default.</span></span> <span data-ttu-id="b2b9f-110">그러나은 문자열을 실제 셀 값 포함 하는 자동으로 정렬 될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2b9f-110">It contains actual cell values that are strings, however, so it can be sorted automatically.</span></span>  
  
### <a name="to-set-the-sort-mode-for-a-column"></a><span data-ttu-id="b2b9f-111">열에 대 한 정렬 모드를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="b2b9f-111">To set the sort mode for a column</span></span>  
  
-   <span data-ttu-id="b2b9f-112"><xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2b9f-112">Set the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b2b9f-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b2b9f-113">Compiling the Code</span></span>  
 <span data-ttu-id="b2b9f-114">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b2b9f-114">This example requires:</span></span>  
  
-   <span data-ttu-id="b2b9f-115">이름이 `Priority`인 열을 포함하는 이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b2b9f-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Priority`.</span></span>  
  
-   <span data-ttu-id="b2b9f-116"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="b2b9f-116">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b9f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2b9f-117">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="b2b9f-118">Windows Forms DataGridView 컨트롤의 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="b2b9f-118">Sorting Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="b2b9f-119">Windows Forms DataGridView 컨트롤의 열 정렬 모드</span><span class="sxs-lookup"><span data-stu-id="b2b9f-119">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="b2b9f-120">방법: Windows Forms DataGridView 컨트롤에서 정렬 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b2b9f-120">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
