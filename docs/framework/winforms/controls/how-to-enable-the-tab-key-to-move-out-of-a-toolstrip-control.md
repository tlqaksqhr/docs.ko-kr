---
title: "방법: TAB 키를 사용하여 ToolStrip 컨트롤 밖으로 이동 가능하도록 설정 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], 이동"
  - "Tab 키, 사용"
  - "ToolStrip 컨트롤[Windows Forms], 이동"
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: TAB 키를 사용하여 ToolStrip 컨트롤 밖으로 이동 가능하도록 설정
다음 절차를 수행하면 사용자가 Tab 키를 눌러 탭 순서에서 <xref:System.Windows.Forms.ToolStrip> 밖의 다음 컨트롤로 이동하게 할 수 있습니다.  
  
 <xref:System.Windows.Forms.ToolStrip>에서는 처음에 누르는 Tab 키를 받으며, 화살표 키를 누르면 <xref:System.Windows.Forms.ToolStrip> 내의 항목이 선택됩니다.  사용자가 두 번째로 Tab 키를 누르면 탭 순서에서 다음 컨트롤로 이동됩니다.  
  
### Tab 키를 눌러 ToolStrip 밖의 다음 컨트롤로 이동할 수 있게 하려면  
  
-   <xref:System.Windows.Forms.ToolStrip>의 <xref:System.Windows.Forms.ToolStrip.TabStop%2A> 속성을 `true`로 설정합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStrip.TabStop%2A>   
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)