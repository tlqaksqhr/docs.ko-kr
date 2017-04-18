---
title: "MenuStrip 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "MenuStrip"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "메뉴, 만들기"
  - "MenuStrip 컨트롤[Windows Forms], MenuStrip 컨트롤 정보"
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# MenuStrip 컨트롤 개요(Windows Forms)
메뉴에 포함되어 있는 명령은 공통 테마별로 그룹화된 상태로 사용자에게 기능이 노출됩니다.  
  
 <xref:System.Windows.Forms.MenuStrip> 컨트롤은 이 버전의 Visual Studio 및 .NET Framework에 새로 도입된 컨트롤입니다.  이 컨트롤을 사용하면 Microsoft Office에 있는 메뉴와 비슷한 메뉴를 쉽게 만들 수 있습니다.  
  
 <xref:System.Windows.Forms.MenuStrip> 컨트롤은 MDI\(다중 문서 인터페이스\) 및 메뉴 병합, 도구 설명 및 오버플로를 지원합니다.  선택키, 바로 가기 키, 확인 표시, 이미지 및 구분선을 추가하여 메뉴를 더 쉽게 사용하고 보기 좋게 만들 수 있습니다.  
  
 <xref:System.Windows.Forms.MenuStrip>은 <xref:System.Windows.Forms.MainMenu> 컨트롤에 새로운 기능이 추가된 것으로, 이전 컨트롤을 대체합니다. 그러나 이전 버전과의 호환성 및 앞으로의 사용 가능성을 고려하여 <xref:System.Windows.Forms.MainMenu> 컨트롤을 유지하도록 선택할 수 있습니다.  
  
## MenuStrip 컨트롤의 사용 방법  
 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용하여 다음 작업을 수행할 수 있습니다.  
  
-   텍스트 및 이미지 순서 매기기와 맞춤, 끌어서 놓기 작업, MDI, 오버플로, 메뉴 명령에 액세스하기 위한 대체 모드 등과 같은 고급 사용자 인터페이스 및 레이아웃 기능을 지원하는 일반적인 사용자 지정 메뉴를 쉽게 만들 수 있습니다.  
  
-   운영 체제의 일반적인 모양과 동작을 지원할 수 있습니다.  
  
-   모든 컨테이너와 포함된 항목에 대한 이벤트를 다른 컨트롤에 대한 이벤트를 처리할 때와 같은 방법으로 일관성 있게 처리할 수 있습니다.  
  
 다음 표에서는 <xref:System.Windows.Forms.MenuStrip> 및 연결된 클래스의 특히 중요한 몇 가지 속성을 보여 줍니다.  
  
|Property|설명|  
|--------------|--------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|MDI 자식 폼의 목록을 표시하는 데 사용되는 <xref:System.Windows.Forms.ToolStripMenuItem>을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=fullName>|MDI 응용 프로그램에서 자식 메뉴를 부모 메뉴와 병합하는 방법을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=fullName>|MDI 응용 프로그램에서 메뉴 내에 병합된 항목의 위치를 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=fullName>|폼이 MDI 자식 폼에 대한 컨테이너인지 여부를 나타내는 값을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<xref:System.Windows.Forms.MenuStrip>에 대한 도구 설명이 표시되는지 여부를 나타내는 값을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<xref:System.Windows.Forms.MenuStrip>에서 오버플로 기능을 지원하는지 여부를 나타내는 값을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<xref:System.Windows.Forms.ToolStripMenuItem>에 연결된 바로 가기 키를 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<xref:System.Windows.Forms.ToolStripMenuItem>에 연결된 바로 가기 키가 <xref:System.Windows.Forms.ToolStripMenuItem> 옆에 표시되는지 여부를 나타내는 값을 가져오거나 설정합니다.|  
  
 다음 표에서는 중요한 <xref:System.Windows.Forms.MenuStrip> 동반 클래스를 보여 줍니다.  
  
|클래스|설명|  
|---------|--------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<xref:System.Windows.Forms.MenuStrip> 또는 <xref:System.Windows.Forms.ContextMenuStrip>에 표시된 선택 가능한 옵션을 나타냅니다.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|바로 가기 메뉴를 나타냅니다.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<xref:System.Windows.Forms.ToolStripDropDownButton> 또는 상위 수준 메뉴 항목을 클릭할 때 표시되는 목록에서 단일 항목을 선택할 수 있게 하는 컨트롤을 나타냅니다.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|클릭하면 드롭다운 항목이 표시되는 <xref:System.Windows.Forms.ToolStripItem>에서 파생되는 컨트롤의 기본 기능을 제공합니다.|  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 <xref:System.Windows.Forms.ToolStripItem>   
 <xref:System.Windows.Forms.ToolStripDropDown>