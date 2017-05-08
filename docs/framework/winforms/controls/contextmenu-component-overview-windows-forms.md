---
title: "ContextMenu 구성 요소 개요(Windows Forms) | Microsoft Docs"
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
  - "ContextMenu"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "상황에 맞는 메뉴, ContextMenu 구성 요소"
  - "ContextMenu 구성 요소[Windows Forms], ContextMenu 구성 요소 정보"
  - "바로 가기 메뉴, ContextMenu 구성 요소"
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# ContextMenu 구성 요소 개요(Windows Forms)
> [!IMPORTANT]
>  <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip>은 이전 버전의 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 컨트롤에 새로운 기능이 추가된 것으로, 이전 컨트롤을 대체합니다. 그러나 이전 버전과의 호환성 및 앞으로의 사용 가능성을 고려하여 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu>를 계속 유지하도록 선택할 수 있습니다.  
  
 Windows Forms <xref:System.Windows.Forms.ContextMenu> 구성 요소를 사용하면 선택한 개체와 관련하여 자주 사용하는 명령이 포함되어 있고 쉽게 액세스할 수 있는 바로 가기 메뉴를 제공할 수 있습니다.  바로 가기 메뉴에 있는 항목은 주로 응용 프로그램의 다른 곳에 나타나는 주 메뉴 항목의 하위 항목에 해당합니다.  일반적으로 사용자는 마우스 오른쪽 단추를 클릭하여 바로 가기 메뉴에 액세스할 수 있습니다.  Windows Forms에서는 바로 가기 메뉴가 컨트롤과 연결됩니다.  
  
## 키 속성  
 컨트롤의 <xref:System.Windows.Forms.Control.ContextMenu%2A> 속성을 <xref:System.Windows.Forms.ContextMenu> 구성 요소로 설정하여 바로 가기 메뉴를 컨트롤과 연결할 수 있습니다.  바로 가기 메뉴 하나를 여러 컨트롤에 연결할 수 있지만 각 컨트롤에는 바로 가기 메뉴가 하나만 포함될 수 있습니다.  
  
 <xref:System.Windows.Forms.ContextMenu> 구성 요소의 주요 속성은 <xref:System.Windows.Forms.Menu.MenuItems%2A> 속성입니다.  프로그래밍 방식으로 <xref:System.Windows.Forms.MenuItem> 개체를 만든 다음 바로 가기 메뉴의 <xref:System.Windows.Forms.Menu.MenuItemCollection>에 추가하여 메뉴 항목을 추가할 수 있습니다.  바로 가기 메뉴의 항목은 대개 다른 메뉴에서 가져오므로 다른 메뉴의 항목을 복사하여 바로 가기 메뉴에 추가하는 경우가 대부분입니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ContextMenu>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>