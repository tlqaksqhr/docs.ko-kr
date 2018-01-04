---
title: "방법: 마우스 포인터가 ToolStripItem을 가리키는 시점 감지"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b04d0ef38a8946abc43da2672ade0723f5f2446f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="ec697-102">방법: 마우스 포인터가 ToolStripItem을 가리키는 시점 감지</span><span class="sxs-lookup"><span data-stu-id="ec697-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="ec697-103">다음 절차를 사용 하 여 마우스 포인터를 위로 가져갈 때 검색 하는 <xref:System.Windows.Forms.ToolStripItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="ec697-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="ec697-104">포인터가 toolstripitem을 가리키는 시점 감지 하려면</span><span class="sxs-lookup"><span data-stu-id="ec697-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
-   <span data-ttu-id="ec697-105">사용 하 여는 <xref:System.Windows.Forms.ToolStripItem.Selected%2A> 는 항목에 대 한 속성 <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> 은 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec697-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="ec697-106">이렇게 하면 사용자를 동기화 하는 것과 <xref:System.Windows.Forms.ToolStripItem.MouseEnter> 및 <xref:System.Windows.Forms.ToolStripItem.MouseLeave> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="ec697-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec697-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec697-107">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripItem.Selected%2A>  
 [<span data-ttu-id="ec697-108">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="ec697-108">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
