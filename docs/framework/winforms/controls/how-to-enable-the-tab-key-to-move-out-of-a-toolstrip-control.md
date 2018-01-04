---
title: "방법: TAB 키를 사용하여 ToolStrip 컨트롤 밖으로 이동 가능하도록 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 38a2e331d9530c42be6b9047b11ea235ae81d58d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a><span data-ttu-id="b1ed9-102">방법: TAB 키를 사용하여 ToolStrip 컨트롤 밖으로 이동 가능하도록 설정</span><span class="sxs-lookup"><span data-stu-id="b1ed9-102">How to: Enable the TAB Key to Move Out of a ToolStrip Control</span></span>
<span data-ttu-id="b1ed9-103">사용자의 이동 하려면 TAB 키를 사용 하도록 설정 하려면 다음 절차를 사용 하 여 한 <xref:System.Windows.Forms.ToolStrip> 탭 순서의 다음 컨트롤로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ed9-103">Use the following procedure to enable the user to press the TAB key to move out of a <xref:System.Windows.Forms.ToolStrip> to the next control in the tab order.</span></span>  
  
 <span data-ttu-id="b1ed9-104"><xref:System.Windows.Forms.ToolStrip> TAB 키와 화살표 키 선택 항목 내에서 첫 번째 키를 눌러 허용는 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ed9-104">The <xref:System.Windows.Forms.ToolStrip> accepts the first press of the TAB key, and the arrow keys select items within the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="b1ed9-105">TAB 키를 두 번째로 누를 때 탭 순서의 다음 컨트롤로 사용자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1ed9-105">When the user presses the TAB key a second time, it takes the user to the next control in the tab order.</span></span>  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a><span data-ttu-id="b1ed9-106">키를 눌러 다음 컨트롤로 ToolStrip 밖으로 이동 하려면 TAB 키를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="b1ed9-106">To enable the user to press the TAB key to move out of a ToolStrip to the next control</span></span>  
  
-   <span data-ttu-id="b1ed9-107">설정의 <xref:System.Windows.Forms.ToolStrip.TabStop%2A> 의 속성은 <xref:System.Windows.Forms.ToolStrip> 를 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ed9-107">Set the <xref:System.Windows.Forms.ToolStrip.TabStop%2A> property of the <xref:System.Windows.Forms.ToolStrip> to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1ed9-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1ed9-108">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.TabStop%2A>  
 [<span data-ttu-id="b1ed9-109">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="b1ed9-109">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
