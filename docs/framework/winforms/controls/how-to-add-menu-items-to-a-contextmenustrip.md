---
title: "방법: ContextMenuStrip에 메뉴 항목 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "상황에 맞는 메뉴, 메뉴 항목 추가"
  - "ContextMenuStrip, 메뉴 항목 추가"
  - "바로 가기 메뉴, 항목 추가"
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: ContextMenuStrip에 메뉴 항목 추가
<xref:System.Windows.Forms.ContextMenuStrip>에 한 번에 메뉴 항목을 하나만 추가하거나 여러 항목을 한꺼번에 추가할 수 있습니다.  
  
### ContextMenuStrip에 단일 메뉴 항목을 추가하려면  
  
-   <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 메서드를 사용하여 메뉴 항목 하나를 <xref:System.Windows.Forms.ContextMenuStrip>에 추가합니다.  
  
     \[Visual Basic\]  
  
    ```  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### ContextMenuStrip에 여러 메뉴 항목을 추가하려면  
  
-   <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> 메서드를 사용하여 여러 메뉴 항목을 <xref:System.Windows.Forms.ContextMenuStrip>에 추가합니다.  
  
     \[Visual Basic\]  
  
    ```  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new   
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## 참고 항목  
 [ContextMenuStrip 컨트롤](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)