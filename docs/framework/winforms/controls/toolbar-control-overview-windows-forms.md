---
title: "ToolBar 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "ToolBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ToolBar 컨트롤[Windows Forms], ToolBar 컨트롤 정보"
  - "도구 모음[Windows Forms], 도구 모음 정보"
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# ToolBar 컨트롤 개요(Windows Forms)
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 Windows Forms <xref:System.Windows.Forms.ToolBar> 컨트롤은 폼에서 컨트롤 막대로 사용됩니다. 컨트롤 막대에는 명령을 활성화하는 비트맵 이미지 단추 및 드롭다운 메뉴가 한 행으로 표시됩니다.  즉, 도구 모음 단추를 클릭하면 메뉴 명령이 선택됩니다.  도구 모음 단추가 누름 단추, 드롭다운 메뉴 또는 구분선으로 표시되고 동작하도록 구성할 수 있습니다.  응용 프로그램에서 가장 많이 사용되는 기능과 명령에 빠르게 액세스할 수 있도록 도구 모음에는 일반적으로 응용 프로그램 메뉴 구조의 항목에 해당하는 단추 및 메뉴가 포함되어 있습니다.  
  
## ToolBar 컨트롤 사용  
 <xref:System.Windows.Forms.ToolBar> 컨트롤은 일반적으로 부모 창의 맨 위에 "도킹"되어 있지만 창에서 원하는 가장자리 위치에 도킹할 수 있습니다.  사용자가 마우스 포인터로 도구 모음 단추를 가리키면 도구 설명이 표시됩니다.  도구 설명은 해당 단추나 메뉴의 기능을 간략하게 설명하는 작은 팝업 창입니다.  도구 설명을 표시하려면 <xref:System.Windows.Forms.ToolBar.ShowToolTips%2A> 속성을 `true`로 설정해야 합니다.  
  
> [!NOTE]
>  특정 응용 프로그램 기능 컨트롤은 응용 프로그램 창 위에 두고 "이동"하며 위치를 변경할 수 있는 기능이 포함된 도구 모음과 매우 비슷합니다.  그러나 Windows Forms ToolBar 컨트롤에는 이러한 기능이 없습니다.  
  
 <xref:System.Windows.Forms.ToolBar.Appearance%2A> 속성을 [Normal](frlrfSystemWindowsFormsToolBarAppearanceClassTopic)로 설정하면 도구 모음 단추가 볼록한 3차원 모양으로 나타납니다.  도구 모음의 <xref:System.Windows.Forms.ToolBar.Appearance%2A> 속성을 <xref:System.Windows.Forms.ToolBarAppearance>으로 설정하면 도구 모음과 도구 모음 단추를 평면 모양으로 만들 수 있습니다.  마우스 포인터를 평면 모양의 단추 위로 이동하면 3차원 모양 단추로 변경됩니다.  구분선을 사용하여 도구 모음 단추를 논리적 그룹으로 나눌 수 있습니다.  구분선은 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 속성이 [Separator](frlrfSystemWindowsFormsToolBarButtonStyleClassTopic)로 설정된 도구 모음 단추이며  도구 모음에서 공백으로 나타납니다.  도구 모음이 평면 모양일 경우에는 단추 구분선이 단추 사이에 공백 대신 선으로 나타납니다.  
  
 <xref:System.Windows.Forms.ToolBar> 컨트롤을 사용하면 <xref:System.Windows.Forms.Button> 개체를 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 컬렉션에 추가하여 도구 모음을 만들 수 있습니다.  컬렉션 편집기를 통해 <xref:System.Windows.Forms.ToolBar> 컨트롤에 단추를 추가할 수 있습니다. 각 <xref:System.Windows.Forms.Button> 개체에는 텍스트나 이미지가 지정되어 있어야 하며 사용자가 직접 지정할 수도 있습니다.  이미지는 연결된 [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) 구성 요소에서 제공합니다.  런타임에 <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A> 및 <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A> 메서드를 사용하여 <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection>에 대해 단추를 추가하거나 제거할 수 있습니다.  <xref:System.Windows.Forms.ToolBar>의 단추를 프로그래밍하려면 <xref:System.Windows.Forms.ToolBar>의 <xref:System.Windows.Forms.ToolBar.ButtonClick> 이벤트에 코드를 추가합니다. 이때 <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> 클래스의 <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> 속성을 사용하여 클릭된 단추를 확인해야 합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolBar>   
 [ToolBar 컨트롤](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)   
 [방법: ToolBar 컨트롤에 단추 추가](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)   
 [방법: 도구 모음 단추의 아이콘 정의](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)   
 [방법: 도구 모음 단추에 대한 메뉴 이벤트 발생](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)