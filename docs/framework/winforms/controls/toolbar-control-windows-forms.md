---
title: "ToolBar 컨트롤(Windows Forms) | Microsoft Docs"
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
  - "ToolBar 컨트롤[Windows Forms]"
  - "도구 모음[Windows Forms]"
ms.assetid: 6b40e9ce-6a7a-4784-bfc9-7f1d36b7462e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# ToolBar 컨트롤(Windows Forms)
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip> 컨트롤은 `ToolBar` 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 `ToolBar` 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 Windows Forms `ToolBar` 컨트롤은 폼에서 드롭다운 메뉴 및 명령을 활성화하는 비트맵 단추가 포함된 한 행을 표시하는 컨트롤 막대로 사용됩니다.  따라서 도구 모음 단추 클릭은 메뉴 명령을 선택하는 것과 같습니다.  단추는 누름 단추, 드롭다운 메뉴 또는 구분 기호로 표시 및 동작하도록 구성할 수 있습니다.  일반적으로 도구 모음에는 응용 프로그램 메뉴 구조의 항목에 해당하는 단추 및 메뉴가 포함되며, 응용 프로그램에서 자주 사용되는 함수 및 명령에 대한 빠른 액세스를 제공합니다.  
  
> [!NOTE]
>  `ToolBar` 컨트롤의 <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> 속성은 <xref:System.Windows.Forms.ContextMenu> 클래스의 인스턴스를 참조로 사용합니다.  이 속성은 <xref:System.Windows.Forms.Menu> 클래스에서 상속되는 모든 개체를 수락하므로 응용 프로그램의 도구 모음에 이러한 종류의 단추를 구현할 때는 전달하는 참조를 신중하게 고려합니다.  
  
## 단원 내용  
 [ToolBar 컨트롤 개요](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 사용자가 사용할 수 있는 사용자 지정 도구 모음을 디자인할 수 있게 해주는 `ToolBar` 컨트롤의 일반적인 개념을 소개합니다.  
  
 [방법: ToolBar 컨트롤에 단추 추가](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)  
 `ToolBar` 컨트롤에 단추를 추가하는 방법을 설명합니다.  
  
 [방법: 도구 모음 단추의 아이콘 정의](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 `ToolBar` 컨트롤의 단추 내에 아이콘을 표시하는 방법을 설명합니다.  
  
 [방법: 도구 모음 단추에 대한 메뉴 이벤트 발생](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 사용자가 `ToolBar` 컨트롤에서 클릭하는 단추를 해석하는 코드를 작성하는 방법에 대한 지침을 제공합니다.  
  
 [방법: 디자이너를 사용하여 도구 모음 단추의 아이콘 정의](http://msdn.microsoft.com/library/ms233659\(v=vs.110\)), [방법: 디자이너를 사용하여 ToolBar 컨트롤에 단추 추가](http://msdn.microsoft.com/library/ms233650\(v=vs.110\))를 참조하세요.  
  
## 참조  
 <xref:System.Windows.Forms.ToolBar> 클래스  
 클래스 및 해당 멤버에 대한 참조 정보를 제공합니다.  
  
## 관련 단원  
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.  
  
 [ToolStrip 컨트롤](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 Windows Forms 응용 프로그램에서 메뉴, 컨트롤 및 사용자 정의 컨트롤을 호스트할 수 있는 도구 모음을 설명합니다.