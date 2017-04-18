---
title: "방법: 디자이너를 사용하여 ToolBar 컨트롤에 단추 추가 | Microsoft Docs"
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
  - "예제[Windows Forms], 도구 모음"
  - "ToolBar 컨트롤[Windows Forms], 단추 추가"
  - "ToolBar 컨트롤[Windows Forms], 드롭다운 메뉴 추가"
  - "ToolBar 컨트롤[Windows Forms], 구분선 추가"
  - "도구 모음[Windows Forms], 단추 추가"
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 디자이너를 사용하여 ToolBar 컨트롤에 단추 추가
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 사용자가 <xref:System.Windows.Forms.ToolBar> 컨트롤에 추가하는 단추는 이 컨트롤에서 중요한 역할을 합니다.  이러한 단추를 사용하면 사용자가 메뉴 명령에 쉽게 액세스할 수 있습니다. 또한 메뉴 구조에서 사용할 수 없는 명령을 사용자에게 제공하기 위해 응용 프로그램 사용자 인터페이스의 다른 영역에 이러한 단추를 배치할 수도 있습니다.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.ToolBar> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자인 타임에 단추를 추가하려면  
  
1.  <xref:System.Windows.Forms.ToolBar> 컨트롤을 선택합니다.  
  
2.  **속성** 창에서 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 속성을 클릭하여 선택한 다음 **줄임표**\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) 단추를 클릭하여 **ToolBarButton 컬렉션 편집기**를 엽니다.  
  
3.  **추가** 및 **제거**단추를 사용하여 <xref:System.Windows.Forms.ToolBar> 컨트롤에서 단추를 추가하거나 제거합니다.  
  
4.  편집기의 오른쪽 창에 표시되는 **속성** 창에서 개별 단추의 속성을 구성합니다.  다음 표에서는 고려해야 할 일부 중요 속성을 보여 줍니다.  
  
    |Property|설명|  
    |--------------|--------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|드롭다운 도구 모음 단추에 표시할 메뉴를 설정합니다.  도구 모음 단추의 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 속성을 <xref:System.Windows.Forms.ToolBarButtonStyle>으로 설정해야 합니다.  이 속성은 <xref:System.Windows.Forms.ContextMenu> 클래스의 인스턴스를 참조로 사용합니다.|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|도구 모음의 토글 스타일 단추를 부분적으로 눌린 상태로 표시할지 여부를 설정합니다.  도구 모음 단추의 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 속성을 <xref:System.Windows.Forms.ToolBarButtonStyle>으로 설정해야 합니다.|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|도구 모음의 토글 스타일 단추를 현재 눌린 상태로 표시할지 여부를 설정합니다.  도구 모음 단추의 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 속성을 <xref:System.Windows.Forms.ToolBarButtonStyle>이나 <xref:System.Windows.Forms.ToolBarButtonStyle>으로 설정해야 합니다.|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|도구 모음 단추의 스타일을 설정합니다.  이 속성 값은 <xref:System.Windows.Forms.ToolBarButtonStyle> 열거형 값 중 하나여야 합니다.|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|단추에 표시되는 텍스트 문자열입니다.|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|단추에 대한 도구 설명으로 표시되는 텍스트입니다.|  
  
5.  **확인**을 클릭하여 대화 상자를 닫고 지정한 패널을 만듭니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolBar>   
 [방법: 도구 모음 단추의 아이콘 정의](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)   
 [방법: 도구 모음 단추에 대한 메뉴 이벤트 발생](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)   
 [ToolBar 컨트롤 개요](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)   
 [ToolBar 컨트롤](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)