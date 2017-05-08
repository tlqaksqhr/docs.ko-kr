---
title: "ToolBar 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "컨트롤, ToolBar"
  - "ToolBar 컨트롤"
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
caps.latest.revision: 28
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 27
---
# ToolBar 개요
<xref:System.Windows.Controls.ToolBar> 컨트롤은 일반적으로 기능에 있어 서로 관련된 명령 또는 컨트롤 그룹에 대한 컨테이너입니다.  <xref:System.Windows.Controls.ToolBar>에는 일반적으로 명령을 호출하는 단추가 들어 있습니다.  
  
   
  
<a name="ToolBarControl"></a>   
## ToolBar 컨트롤  
 <xref:System.Windows.Controls.ToolBar> 컨트롤은 단추 또는 기타 컨트롤이 단일 행 또는 열에 막대\(bar\) 모양으로 배열되는 것에서 이름이 지정되었습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> 컨트롤은 크기 제약이 있는 <xref:System.Windows.Controls.ToolBar> 내에 맞지 않는 항목을 특수 오버플로 영역에 배치하는 오버플로 메커니즘을 제공합니다.  또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> 컨트롤은 일반적으로 관련 <xref:System.Windows.Controls.ToolBarTray> 컨트롤과 함께 사용됩니다. 이러한 컨트롤은 도구 모음에 대해 사용자가 시작하는 크기 조정 및 배열에 대한 지원뿐만 아니라 특수 레이아웃 동작도 제공합니다.  
  
<a name="Creating_ToolBars"></a>   
## ToolBarTray에서 ToolBar의 위치 지정  
 <xref:System.Windows.Controls.ToolBar.Band%2A> 및 <xref:System.Windows.Controls.ToolBar.BandIndex%2A> 속성을 사용하여 <xref:System.Windows.Controls.ToolBarTray>에서 <xref:System.Windows.Controls.ToolBar>의 위치를 지정합니다.  <xref:System.Windows.Controls.ToolBar.Band%2A>는 해당 부모 <xref:System.Windows.Controls.ToolBarTray> 내에서 <xref:System.Windows.Controls.ToolBar>가 배치되는 위치를 나타냅니다.  <xref:System.Windows.Controls.ToolBar.BandIndex%2A>는 해당 밴드 내에서 <xref:System.Windows.Controls.ToolBar>가 배치되는 순서를 나타냅니다.  다음 예제에서는 이 속성을 사용하여 <xref:System.Windows.Controls.ToolBar> 컨트롤을 <xref:System.Windows.Controls.ToolBarTray> 내부에 배치하는 방법을 보여 줍니다.  
  
 [!code-xml[ToolBarExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## 오버플로 항목이 있는 ToolBar  
 도구 모음의 크기에 맞는 것보다 많은 항목이 <xref:System.Windows.Controls.ToolBar> 컨트롤에 포함되는 경우가 많습니다.  이러한 경우 <xref:System.Windows.Controls.ToolBar>는 오버플로 단추를 표시합니다.  오버플로 항목을 보기 위해 사용자가 오버플로 단추를 클릭하면 해당 항목이 <xref:System.Windows.Controls.ToolBar> 아래의 팝업 창에 표시됩니다.  다음 그래픽에서는 오버플로 항목이 있는 <xref:System.Windows.Controls.ToolBar>를 보여 줍니다.  
  
 ![오버플로가 발생한 도구 모음](../../../../docs/framework/wpf/controls/media/toolbarwithoverflowitem.png "ToolbarWithOverflowItem")  
오버플로 항목이 있는 ToolBar  
  
 <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=fullName> 연결 속성을 <xref:System.Windows.Controls.OverflowMode?displayProperty=fullName>, <xref:System.Windows.Controls.OverflowMode?displayProperty=fullName> 또는 <xref:System.Windows.Controls.OverflowMode?displayProperty=fullName>로 설정하여 도구 모음의 항목이 오버플로 패널에 배치되는 경우를 지정할 수 있습니다.  다음 예제에서는 도구 모음의 마지막 4개 단추가 항상 오버플로 패널에 있어야 함을 지정합니다.  
  
 [!code-xml[ToolBarExample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 <xref:System.Windows.Controls.ToolBar>는 <xref:System.Windows.Controls.Primitives.ToolBarPanel> 및 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>을 해당 <xref:System.Windows.Controls.ControlTemplate>으로 사용합니다.  <xref:System.Windows.Controls.Primitives.ToolBarPanel>은 도구 모음에 있는 항목의 레이아웃을 담당합니다.  <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>은 <xref:System.Windows.Controls.ToolBar>에 맞지 않는 항목의 레이아웃을 담당합니다.  <xref:System.Windows.Controls.ToolBar>에 대한 <xref:System.Windows.Controls.ControlTemplate>의 예제를 보려면 다음을 참조하십시오.  
  
 [ToolBar 스타일 및 템플릿](../../../../docs/framework/wpf/controls/toolbar-styles-and-templates.md).  
  
## 참고 항목  
 <xref:System.Windows.Controls.Primitives.ToolBarPanel>   
 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>   
 [ToolBar 컨트롤의 스타일 지정](../../../../docs/framework/wpf/controls/how-to-style-controls-on-a-toolbar.md)   
 [WPF Controls Gallery 샘플](http://go.microsoft.com/fwlink/?LinkID=160053)