---
title: "방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시"
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
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a9da292b5f65ea9dc44b47a8c3bc13cf43e83b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a><span data-ttu-id="63858-102">방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시</span><span class="sxs-lookup"><span data-stu-id="63858-102">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>
<span data-ttu-id="63858-103">Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤 추가 텍스트 또는 자세히 보기의 각 항목에 대 한 하위 항목을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63858-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display additional text, or subitems, for each item in the Details view.</span></span> <span data-ttu-id="63858-104">첫 번째 열에는 예를 들어 직원 번호 항목 텍스트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="63858-104">The first column displays the item text, for example an employee number.</span></span> <span data-ttu-id="63858-105">두 번째, 두 번째, 첫 번째, 세 번째 및 이후의 열에 표시 하 고 후속 관련 된 하위 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="63858-105">The second, third, and subsequent columns display the first, second, and subsequent associated subitems.</span></span>  
  
### <a name="to-add-subitems-to-a-list-item"></a><span data-ttu-id="63858-106">목록 항목에 하위 항목을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="63858-106">To add subitems to a list item</span></span>  
  
1.  <span data-ttu-id="63858-107">필요한 열을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="63858-107">Add any columns needed.</span></span> <span data-ttu-id="63858-108">첫 번째 열에는 항목의 표시 됩니다 <xref:System.Windows.Forms.ListView.Text%2A> 속성을 하나 더 많은 열 하위이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="63858-108">Because the first column will display the item's <xref:System.Windows.Forms.ListView.Text%2A> property, you need one more column than there are subitems.</span></span> <span data-ttu-id="63858-109">추가 열에 대 한 자세한 내용은 참조 하십시오. [하는 방법: Windows Forms ListView 컨트롤에 열 추가](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="63858-109">For more information on adding columns, see [How to: Add Columns to the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span>  
  
2.  <span data-ttu-id="63858-110">호출 된 <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> 에서 반환 된 컬렉션의 메서드는 <xref:System.Windows.Forms.ListViewItem.SubItems%2A> 항목의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="63858-110">Call the <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.ListViewItem.SubItems%2A> property of an item.</span></span> <span data-ttu-id="63858-111">아래의 코드 예제에서는 직원 이름 및 목록 항목에 대 한 부서를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="63858-111">The code example below sets the employee name and department for a list item.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="63858-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63858-112">See Also</span></span>  
 [<span data-ttu-id="63858-113">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="63858-113">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="63858-114">방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="63858-114">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="63858-115">방법: Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="63858-115">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="63858-116">방법: Windows Forms ListView 컨트롤의 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="63858-116">How to: Display Icons for the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="63858-117">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="63858-117">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
