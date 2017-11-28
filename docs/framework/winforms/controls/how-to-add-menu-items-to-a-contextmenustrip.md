---
title: "방법: ContextMenuStrip에 메뉴 항목 추가"
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
- ContextMenuStrips [Windows Forms], adding menu items
- shortcut menus [Windows Forms], adding items
- context menus [Windows Forms], adding menu items
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ad9aa3ced90793b8051b377f499c94466bc3751a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a>방법: ContextMenuStrip에 메뉴 항목 추가
한 번에 하나만 메뉴 항목 또는 여러 항목을 추가할 수 있습니다는 <xref:System.Windows.Forms.ContextMenuStrip>합니다.  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a>ContextMenuStrip에 메뉴 단일 항목을 추가 하려면  
  
-   사용 하 여는 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 을 메뉴 항목을 추가 하는 메서드는 <xref:System.Windows.Forms.ContextMenuStrip>합니다.  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a>ContextMenuStrip에 몇 가지 메뉴 항목을 추가 하려면  
  
-   사용 하 여는 <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> 여러 메뉴 항목을 추가 하는 메서드는 <xref:System.Windows.Forms.ContextMenuStrip>합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [ContextMenuStrip 컨트롤](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
