---
title: '방법: ContextMenuStrip에 메뉴 항목 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrips [Windows Forms], adding menu items
- shortcut menus [Windows Forms], adding items
- context menus [Windows Forms], adding menu items
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
ms.openlocfilehash: d044cf92cf7ce6db3425aacf397d6c7b4f111324
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524627"
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="3f934-102">방법: ContextMenuStrip에 메뉴 항목 추가</span><span class="sxs-lookup"><span data-stu-id="3f934-102">How to: Add Menu Items to a ContextMenuStrip</span></span>
<span data-ttu-id="3f934-103">한 번에 하나만 메뉴 항목 또는 여러 항목을 추가할 수 있습니다는 <xref:System.Windows.Forms.ContextMenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="3f934-103">You can add just one menu item or several items at a time to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a><span data-ttu-id="3f934-104">ContextMenuStrip에 메뉴 단일 항목을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="3f934-104">To add a single menu item to a ContextMenuStrip</span></span>  
  
-   <span data-ttu-id="3f934-105">사용 하 여는 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 을 메뉴 항목을 추가 하는 메서드는 <xref:System.Windows.Forms.ContextMenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="3f934-105">Use the <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add one menu item to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="3f934-106">ContextMenuStrip에 몇 가지 메뉴 항목을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="3f934-106">To add several menu items to a ContextMenuStrip</span></span>  
  
-   <span data-ttu-id="3f934-107">사용 하 여는 <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> 여러 메뉴 항목을 추가 하는 메서드는 <xref:System.Windows.Forms.ContextMenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="3f934-107">Use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> method to add several menu items to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new   
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3f934-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f934-108">See Also</span></span>  
 [<span data-ttu-id="3f934-109">ContextMenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3f934-109">ContextMenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
