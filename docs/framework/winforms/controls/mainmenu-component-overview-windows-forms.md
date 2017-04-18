---
title: "MainMenu 구성 요소 개요(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MenuItem"
  - "MainMenu"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MainMenu 컨트롤[Windows Forms], MainMenu 컨트롤 정보"
  - "메뉴"
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# MainMenu 구성 요소 개요(Windows Forms)
> [!IMPORTANT]
>  <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip>은 이전 버전의 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 컨트롤에 새로운 기능이 추가된 것으로, 이전 컨트롤을 대체합니다. 그러나 이전 버전과의 호환성 및 앞으로의 사용 가능성을 고려하여 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu>를 계속 유지하도록 선택할 수 있습니다.  
  
 Windows Forms <xref:System.Windows.Forms.MainMenu> 구성 요소는 런타임에 메뉴를 표시합니다.  주 메뉴의 모든 하위 메뉴와 개별 항목은 <xref:System.Windows.Forms.MenuItem> 개체입니다.  
  
## 키 속성  
 <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> 속성을 `true`로 설정하면 메뉴 항목을 기본 항목으로 지정할 수 있습니다.  기본 항목은 메뉴를 클릭할 경우 굵은 글꼴로 나타납니다.  메뉴 항목의 <xref:System.Windows.Forms.MenuItem.Checked%2A> 속성은 `true` 또는 `false`이며 메뉴 항목의 선택 여부를 나타냅니다.  메뉴 항목의 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 속성은 선택된 항목의 모양을 사용자 지정합니다. <xref:System.Windows.Forms.MenuItem.RadioCheck%2A>를 `true`로 설정하면 항목 옆에 라디오 단추가 나타납니다. <xref:System.Windows.Forms.MenuItem.RadioCheck%2A>를 `false`로 설정하면 항목 옆에 확인 표시가 나타납니다  
  
## 참고 항목  
 <xref:System.Windows.Forms.MainMenu>   
 <xref:System.Windows.Forms.Menu>   
 <xref:System.Windows.Forms.MenuItem>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>   
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)