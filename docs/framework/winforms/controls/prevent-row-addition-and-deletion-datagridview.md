---
title: "방법: Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지"
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
- DataGridView control [Windows Forms], disabling data entry
- data entry [Windows Forms], disabling in grids
- data grids [Windows Forms], disabling data entry
ms.assetid: ef9539ce-539b-404e-84b6-ac282b64b88c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e90e36ef8a74caf58f6454027971f0711c406d52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2001e-102">방법: Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지</span><span class="sxs-lookup"><span data-stu-id="2001e-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2001e-103">때때로 사용자가 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 새 데이터 행을 입력하거나 기존 행을 삭제하지 않도록 방지하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2001e-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2001e-104"><xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 속성은 컨트롤 아래쪽에 새 레코드에 대한 행이 있는지를 나타내는 반면, <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> 속성은 행을 제거할 수 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2001e-104">The <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property indicates whether the row for new records is present at the bottom of the control, while the <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> property indicates whether rows can be removed.</span></span> <span data-ttu-id="2001e-105">다음 코드 예제에서는 이들 속성을 사용하고 <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> 속성을 설정하여 컨트롤을 전체적으로 읽기 전용으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2001e-105">The following code example uses these properties and also sets the <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> property to make the control entirely read-only.</span></span>  
  
 <span data-ttu-id="2001e-106">Visual Studio에서는 이 작업이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2001e-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="2001e-107">또한 참조 [하는 방법: 행 추가 및 삭제 금지는 Windows Forms DataGridView 컨트롤 사용 하 여 디자이너에서](http://msdn.microsoft.com/library/k5c88sw3\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="2001e-107">Also see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](http://msdn.microsoft.com/library/k5c88sw3\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2001e-108">예제</span><span class="sxs-lookup"><span data-stu-id="2001e-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2001e-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="2001e-109">Compiling the Code</span></span>  
 <span data-ttu-id="2001e-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2001e-110">This example requires:</span></span>  
  
-   <span data-ttu-id="2001e-111">`dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2001e-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="2001e-112"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="2001e-112">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2001e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2001e-113">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="2001e-114">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="2001e-114">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
