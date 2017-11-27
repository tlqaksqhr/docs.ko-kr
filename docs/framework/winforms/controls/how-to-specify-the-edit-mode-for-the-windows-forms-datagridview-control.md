---
title: "방법: Windows Forms DataGridView 컨트롤에 편집 모드 지정"
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
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 70bf241865eef3366444e1b4dc20c19adaff983e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a><span data-ttu-id="d7fec-102">방법: Windows Forms DataGridView 컨트롤에 편집 모드 지정</span><span class="sxs-lookup"><span data-stu-id="d7fec-102">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d7fec-103">기본적으로 사용자의 현재 내용을 편집할 수 있습니다 <xref:System.Windows.Forms.DataGridView> 에서 직접 입력 하거나 F2 키를 눌러 텍스트 상자 셀입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fec-103">By default, users can edit the contents of the current <xref:System.Windows.Forms.DataGridView> text box cell by typing in it or pressing F2.</span></span> <span data-ttu-id="d7fec-104">다음 조건이 모두 충족 될 경우에 편집 모드에 셀 전환:</span><span class="sxs-lookup"><span data-stu-id="d7fec-104">This puts the cell in edit mode if all of the following conditions are met:</span></span>  
  
-   <span data-ttu-id="d7fec-105">데이터 원본 편집을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fec-105">The underlying data source supports editing.</span></span>  
  
-   <span data-ttu-id="d7fec-106"><xref:System.Windows.Forms.DataGridView> 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fec-106">The <xref:System.Windows.Forms.DataGridView> control is enabled.</span></span>  
  
-   <span data-ttu-id="d7fec-107"><xref:System.Windows.Forms.DataGridView.EditMode%2A> 속성 값이 <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fec-107">The <xref:System.Windows.Forms.DataGridView.EditMode%2A> property value is not <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.</span></span>  
  
-   <span data-ttu-id="d7fec-108">`ReadOnly` 셀, 행, 열 및 컨트롤의 속성을 모두 설정 되어 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fec-108">The `ReadOnly` properties of the cell, row, column, and control are all set to `false`.</span></span>  
  
 <span data-ttu-id="d7fec-109">편집 모드에 사용자 셀 값을 변경 하 고 enter 키를 눌러 변경 내용을 커밋하거나 셀을 원래 값으로 되돌리려면 ESC 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fec-109">In edit mode, the user can change the cell value and press ENTER to commit the change or ESC to revert the cell to its original value.</span></span>  
  
 <span data-ttu-id="d7fec-110">구성할 수는 <xref:System.Windows.Forms.DataGridView> 셀이 현재 셀이으로 편집 모드로 전환 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fec-110">You can configure a <xref:System.Windows.Forms.DataGridView> control so that a cell enters edit mode as soon as it becomes the current cell.</span></span> <span data-ttu-id="d7fec-111">이 경우 ENTER 및 ESC 키의 동작이 변경 되지 않습니다 되지만 값 커밋하거나 되돌려야 후 셀이 편집 모드에 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7fec-111">The behavior of the ENTER and ESC keys is unchanged in this case, but the cell remains in edit mode after the value is committed or reverted.</span></span> <span data-ttu-id="d7fec-112">셀의 셀 이나 사용자가 f 2를 눌러 사용자가 입력 하는 경우에 편집 모드로 전환 되도록 컨트롤을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fec-112">You can also configure the control so that cells enter edit mode only when users type in the cell or only when users press F2.</span></span> <span data-ttu-id="d7fec-113">마지막으로 호출 하는 경우를 제외 하 고 편집 모드가 셀을 방지할 수 있습니다는 <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="d7fec-113">Finally, you can prevent cells from entering edit mode except when you call the <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> method.</span></span>  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a><span data-ttu-id="d7fec-114">DataGridView 컨트롤의 편집 모드를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="d7fec-114">To change the edit mode of a DataGridView control</span></span>  
  
-   <span data-ttu-id="d7fec-115">설정의 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> 속성을 적절 한 <xref:System.Windows.Forms.DataGridViewEditMode> 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fec-115">Set the <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> property to the appropriate <xref:System.Windows.Forms.DataGridViewEditMode> enumeration.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7fec-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d7fec-116">Compiling the Code</span></span>  
 <span data-ttu-id="d7fec-117">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fec-117">This example requires:</span></span>  
  
-   <span data-ttu-id="d7fec-118">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d7fec-118">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="d7fec-119"><xref:System> 및 <xref:System.Windows.Forms> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="d7fec-119">References to the <xref:System> and <xref:System.Windows.Forms> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7fec-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7fec-120">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="d7fec-121">Windows Forms DataGridView 컨트롤의 데이터 입력</span><span class="sxs-lookup"><span data-stu-id="d7fec-121">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
