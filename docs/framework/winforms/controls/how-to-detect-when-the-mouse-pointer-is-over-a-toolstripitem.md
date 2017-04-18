---
title: "방법: 마우스 포인터가 ToolStripItem을 가리키는 시점 감지 | Microsoft Docs"
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
  - "마우스, 도구 모음에서 이동 감지"
  - "도구 모음[Windows Forms], 마우스 이동 감지"
  - "ToolStrip 컨트롤[Windows Forms], 마우스 이동 감지"
  - "ToolStripItem 클래스, 마우스 이동 감지"
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 마우스 포인터가 ToolStripItem을 가리키는 시점 감지
다음 절차를 수행하면 마우스 포인터가 <xref:System.Windows.Forms.ToolStripItem>을 가리키는 시점을 감지할 수 있습니다.  
  
### 포인터가 ToolStripItem을 가리키는 시점을 감지하려면  
  
-   <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A>가 `true`인 항목에 <xref:System.Windows.Forms.ToolStripItem.Selected%2A> 속성을 사용합니다.  
  
     그러면 <xref:System.Windows.Forms.ToolStripItem.MouseEnter> 이벤트와 <xref:System.Windows.Forms.ToolStripItem.MouseLeave> 이벤트를 동기화하지 않아도 됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStripItem>   
 <xref:System.Windows.Forms.ToolStripItem.Selected%2A>   
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)