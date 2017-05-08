---
title: "방법: ContextMenuStrip Opening 이벤트 처리 | Microsoft Docs"
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
  - "상황에 맞는 메뉴, 이벤트 처리"
  - "ContextMenuStrip 컨트롤[Windows Forms]"
  - "이벤트 처리, 상황에 맞는 메뉴"
  - "바로 가기 메뉴, 이벤트 처리"
  - "ToolStrip 컨트롤[Windows Forms]"
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: ContextMenuStrip Opening 이벤트 처리
<xref:System.Windows.Forms.ToolStripDropDown.Opening> 이벤트를 처리하여 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤의 동작을 사용자 지정할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 이벤트를 처리하는 방법을 보여 줍니다.  이벤트 처리기는 항목을 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤에 동적으로 추가합니다.  전체 코드 예제를 보려면 [방법: 동적으로 ToolStrip 항목 추가](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md)을 참조하십시오.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=fullName> 속성을 `true`로 설정하여 메뉴가 열리지 않도록 합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ContextMenuStrip>   
 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>   
 <xref:System.Windows.Forms.ToolStripDropDown>   
 [ToolStrip 컨트롤](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)