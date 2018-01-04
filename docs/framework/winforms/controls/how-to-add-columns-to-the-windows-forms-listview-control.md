---
title: "방법: Windows Forms ListView 컨트롤에 열 추가"
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
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4895d9fbd84ac00291a717e47102f3d0e04176f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="cd5db-102">방법: Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="cd5db-102">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="cd5db-103">세부 정보 뷰에서 <xref:System.Windows.Forms.ListView> 컨트롤 각 목록 항목에 대 한 여러 열을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd5db-103">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="cd5db-104">여러 유형의 각 목록 항목에 대 한 정보를 사용자에 게 표시 하는 열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd5db-104">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="cd5db-105">예를 들어 파일 이름, 파일 형식, 크기 및 파일을 마지막으로 수정한 날짜 파일의 목록을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd5db-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="cd5db-106">생성 된 후 열을 채우는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Windows Forms ListView 컨트롤에서 열에 하위 항목 표시](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5db-106">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="cd5db-107">프로그래밍 방식으로 열을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="cd5db-107">To add columns programmatically</span></span>  
  
1.  <span data-ttu-id="cd5db-108">컨트롤의 <xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View.Details>합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5db-108">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2.  <span data-ttu-id="cd5db-109">사용 하 여는 <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> 메서드 목록 보기의 <xref:System.Windows.Forms.ListView.Columns%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cd5db-109">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="cd5db-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd5db-110">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 [<span data-ttu-id="cd5db-111">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cd5db-111">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="cd5db-112">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="cd5db-112">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
