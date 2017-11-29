---
title: "방법: ToolStrip 컨트롤에 설정/해제 단추 만들기"
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
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a8529637db7bc4cca011d0992b257d5b8ce9aaff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a><span data-ttu-id="cd5c1-102">방법: ToolStrip 컨트롤에 설정/해제 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="cd5c1-102">How to: Create Toggle Buttons in ToolStrip Controls</span></span>
<span data-ttu-id="cd5c1-103">사용자가 토글 단추를 클릭 하면 오목 하 게 표시 하 고 사용자가 단추를 다시 클릭할 때까지 모양이 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5c1-103">When a user clicks a toggle button, it appears sunken and retains the sunken appearance until the user clicks the button again.</span></span>  
  
### <a name="to-create-a-toggling-toolstripbutton"></a><span data-ttu-id="cd5c1-104">토글 ToolStripButton를 만들려면</span><span class="sxs-lookup"><span data-stu-id="cd5c1-104">To create a toggling ToolStripButton</span></span>  
  
-   <span data-ttu-id="cd5c1-105">다음 코드 예제에서는 같은 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5c1-105">Use code such as the following code example.</span></span> <span data-ttu-id="cd5c1-106">이 코드는 폼에 포함 되어 있다고 가정는 <xref:System.Windows.Forms.ToolStrip> 컨트롤과 해당 <xref:System.Windows.Forms.ToolStrip.Items%2A> 컬렉션에 포함 되어는 <xref:System.Windows.Forms.ToolStripButton> 호출 `toolStripButton1`합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5c1-106">This code assumes that your form contains a <xref:System.Windows.Forms.ToolStrip> control, and that its <xref:System.Windows.Forms.ToolStrip.Items%2A> collection contains a <xref:System.Windows.Forms.ToolStripButton> called `toolStripButton1`.</span></span> <span data-ttu-id="cd5c1-107">또한 라는 이벤트 처리기 있다고 가정 `toolStripButton1_CheckedChanged`합니다.</span><span class="sxs-lookup"><span data-stu-id="cd5c1-107">It also assumes that you have an event handler called `toolStripButton1_CheckedChanged`.</span></span>  
  
    ```vb  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
    ```csharp  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cd5c1-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd5c1-108">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripButton>  
 [<span data-ttu-id="cd5c1-109">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="cd5c1-109">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
