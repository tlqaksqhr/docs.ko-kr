---
title: "방법: Windows Forms ListView 컨트롤에서 항목 선택"
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
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ef672dc909717ba979d81bd98510dad6419583a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="d9840-102">방법: Windows Forms ListView 컨트롤에서 항목 선택</span><span class="sxs-lookup"><span data-stu-id="d9840-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="d9840-103">이 예제에서는 프로그래밍 방식으로 Windows Forms에서 항목을 선택 하는 방법을 보여 줍니다 <xref:System.Windows.Forms.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9840-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="d9840-104">프로그래밍 방식으로 항목을 선택 하면 자동으로 바뀌지 않습니다에 포커스는 <xref:System.Windows.Forms.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9840-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="d9840-105">이러한 이유로 일반적으로 하려는 항목을 선택할 때 중심으로 항목을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9840-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9840-106">예</span><span class="sxs-lookup"><span data-stu-id="d9840-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d9840-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d9840-107">Compiling the Code</span></span>  
 <span data-ttu-id="d9840-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d9840-108">This example requires:</span></span>  
  
-   <span data-ttu-id="d9840-109">A <xref:System.Windows.Forms.ListView> 라는 컨트롤 `listView1` 항목을 하나 이상 들어 있는입니다.</span><span class="sxs-lookup"><span data-stu-id="d9840-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
-   <span data-ttu-id="d9840-110"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="d9840-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9840-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9840-111">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
