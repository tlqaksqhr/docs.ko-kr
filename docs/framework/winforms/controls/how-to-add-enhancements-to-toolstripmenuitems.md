---
title: "방법: ToolStripMenuItems에 향상된 기능 추가 | Microsoft Docs"
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
  - "확인 표시, 메뉴에 추가"
  - "명령[Windows Forms], 메뉴에 그룹화"
  - "이미지[Windows Forms], 메뉴에 추가"
  - "바로 가기 키, 메뉴에 표시"
  - "메뉴 항목, 확인 표시 추가"
  - "메뉴 항목, 이미지 추가"
  - "메뉴 항목, 선택키 표시"
  - "메뉴 항목, 바로 가기 키 표시"
  - "메뉴 항목, 구분선 표시"
  - "메뉴, 명령 그룹화"
  - "구분 문자, 메뉴에 표시"
  - "ToolStripMenuItems"
  - "ToolStripMenuItems, 확인 표시 추가"
  - "ToolStripMenuItems, 이미지 추가"
  - "ToolStripMenuItems, 선택키 표시"
  - "ToolStripMenuItems, 바로 가기 키 표시"
  - "ToolStripMenuItems, 구분줄 표시"
  - "ToolStripSeparators, MenuStrip에 표시"
ms.assetid: aa5f19bb-b545-4378-bfa6-36ba592f0d7c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: ToolStripMenuItems에 향상된 기능 추가
다음과 같은 방법으로 <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤의 유용성을 향상시킬 수 있습니다.  
  
-   확인 표시를 추가하여 워드프로세서 응용 프로그램의 여백 눈금자 표시 여부와 같이 기능의 설정 또는 해제 상태를 지정하거나 파일 목록 중 **창** 메뉴 등에 표시되는 파일을 나타냅니다.  
  
-   메뉴 명령을 시각적으로 나타내는 이미지를 추가합니다.  
  
-   명령을 수행하는 데 키보드에서 마우스 대신 사용할 수 있는 바로 가기 키를 표시합니다.  예를 들어, Ctrl\+C를 누르면 **Copy** 명령이 수행됩니다.  
  
-   메뉴를 탐색하는 데 키보드에서 마우스 대신 사용할 수 있는 선택키를 표시합니다.  예를 들어, Alt\+F를 누르면 **파일** 메뉴가 선택됩니다.  
  
-   구분줄을 통해 관련된 명령을 그룹화하여 메뉴를 보다 읽기 쉽게 만듭니다.  
  
### 메뉴 명령에 확인 표시를 표시하려면  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 속성을 `true`로 설정합니다.  
  
     또한 <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> 속성을 `true`로 설정합니다.  메뉴 명령의 선택 여부에 관계없이 메뉴 명령이 기본적으로 선택된 것으로 나타나게 하려는 경우에만 이 절차를 수행합니다.  
  
### 클릭할 때마다 상태를 변경하는 확인 표시를 표시하려면  
  
-   메뉴 명령의 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 속성을 `true`로 설정합니다.  
  
### 메뉴 명령에 이미지를 추가하려면  
  
-   메뉴 명령의 <xref:System.Windows.Forms.ToolStripItem.Image%2A> 속성을 이미지의 이름으로 설정합니다.  이 메뉴 명령의 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 속성이 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 또는 <xref:System.Windows.Forms.ToolStripItemDisplayStyle>으로 설정된 경우 이미지를 표시할 수 없습니다.  
  
> [!NOTE]
>  필요한 경우 이미지 여백에 확인 표시를 표시할 수도 있습니다.  또한 이미지의 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 속성을 `true`로 설정하여 런타임에 이미지 주위에 사선 테두리가 나타나도록 할 수 있습니다.  
  
### 메뉴 명령에 대한 바로 가기 키를 표시하려면  
  
-   메뉴 명령의 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> 속성을 원하는 키보드 조합으로 설정\(예: **열기** 메뉴의 경우 Ctrl\+O\)하고 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> 속성을 `true`로 설정합니다.  
  
### 메뉴 명령에 대한 사용자 지정 바로 가기 키를 표시하려면  
  
-   메뉴 명령의 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> 속성을 원하는 키보드 조합으로 설정\(예: Shift\+Ctrl\+O가 아닌 Ctrl\+Shift\+O\)하고 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> 속성을 `true`로 설정합니다.  
  
### 메뉴 명령에 대한 선택키를 표시하려면  
  
-   메뉴 명령에 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 설정하는 경우 밑줄을 표시하여 선택키임을 나타내려는 문자 앞에 앰퍼샌드\(&\)를 입력합니다.  예를 들어, 메뉴 항목의 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성으로 `&Open` 을 입력하면 메뉴 명령에 **O**pen으로 나타납니다.  
  
     이 메뉴 명령을 탐색하려면 Alt 키를 눌러 <xref:System.Windows.Forms.MenuStrip>으로 포커스를 이동한 다음 해당 메뉴 이름의 선택키를 누릅니다.  메뉴가 열리고 선택키가 있는 항목이 표시되면 선택키만 눌러도 메뉴 명령을 선택할 수 있습니다.  
  
> [!NOTE]
>  동일한 메뉴 시스템에서 Alt\+F를 두 번 정의하는 것과 같이 중복된 선택키를 정의하지 마십시오.  중복 선택키를 정의하는 경우 선택 순서는 알 수 없습니다.  
  
### 메뉴 명령 사이에 구분줄을 표시하려면  
  
-   <xref:System.Windows.Forms.MenuStrip> 및 여기에 포함될 항목을 정의한 다음 <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> 또는 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 메서드를 사용하여 원하는 순서대로 메뉴 명령 및 <xref:System.Windows.Forms.ToolStripSeparator> 컨트롤을 <xref:System.Windows.Forms.MenuStrip>에 추가합니다.  
  
     \[Visual Basic\]  
  
    ```  
    ' This code adds a top-level File menu to the MenuStrip.  
    Me.menuStrip1.Items.Add(New ToolStripMenuItem() _  
    {Me.fileToolStripMenuItem})  
  
    ' This code adds the New and Open menu commands, a separator bar,   
    ' and the Save and Exit menu commands to the top-level File menu,   
    ' in that order.  
    Me.fileToolStripMenuItem.DropDownItems.AddRange(New _  
    ToolStripMenuItem() {Me.newToolStripMenuItem, _  
    Me.openToolStripMenuItem, Me.toolStripSeparator1, _  
    Me.saveToolStripMenuItem, Me.exitToolStripMenuItem})  
  
    ```  
  
     \[C\#\]  
  
    ```  
    // This code adds a top-level File menu to the MenuStrip.  
    this.menuStrip1.Items.Add(new ToolStripItem[]_  
    {this.fileToolStripMenuItem});  
  
    // This code adds the New and Open menu commands, a separator bar,   
    // and the Save and Exit menu commands to the top-level File menu,   
    // in that order.  
    this.fileToolStripMenuItem.DropDownItems.AddRange(new _  
    ToolStripItem[] {  
    this.newToolStripMenuItem,  
    this.openToolStripMenuItem,  
    this.toolStripSeparator1,  
    this.saveToolStripMenuItem,  
    this.exitToolStripMenuItem});  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)