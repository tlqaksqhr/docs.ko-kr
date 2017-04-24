---
title: "성능 최적화: 컨트롤 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "컨테이너 재활용"
  - "컨트롤[WPF], 성능 향상"
  - "사용자 인터페이스 가상화"
ms.assetid: 45a31c43-ea8a-4546-96c8-0631b9934179
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# 성능 최적화: 컨트롤
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에는 대부분의 Windows 응용 프로그램에 사용되는 일반적인 UI\(사용자 인터페이스\) 구성 요소가 다수 포함되어 있습니다.  이 항목에서는 UI의 성능을 향상시킬 수 있는 기술에 대해 설명합니다.  
  
   
  
<a name="Displaying"></a>   
## 대용량 데이터 집합 표시  
 <xref:System.Windows.Controls.ListView> 및 <xref:System.Windows.Controls.ComboBox>와 같은 WPF 컨트롤은 응용 프로그램에서 항목 목록을 표시하는 데 사용됩니다.  표시할 목록이 크면 응용 프로그램의 성능에 영향을 줄 수 있습니다.  그 이유는 표준 레이아웃 시스템에서는 목록 컨트롤과 연결된 각 항목에 대해 레이아웃 컨테이너를 만들고 해당 레이아웃의 크기와 위치를 계산하기 때문입니다.  대개는 모든 항목을 동시에 표시할 필요가 없습니다. 대신 항목의 일부만 표시하고 사용자가 목록을 스크롤하면 됩니다.  이 경우에는 UI *가상화*를 사용하는 것이 적합합니다. 가상화를 사용하면 항목이 실제로 표시될 때까지 해당 항목에 대한 항목 컨테이너 생성 및 연결된 레이아웃에 대한 계산이 지연됩니다.  
  
 UI 가상화는 목록 컨트롤의 중요한 요소입니다.  UI 가상화를 데이터 가상화와 혼동해서는 안 됩니다.  UI 가상화의 경우 표시 가능한 항목만 메모리에 저장되지만 데이터 바인딩 시나리오에서는 전체 데이터 구조가 메모리에 저장됩니다.  반면 데이터 가상화의 경우 화면에 표시되는 데이터 항목만 메모리에 저장됩니다.  
  
 기본적으로 UI 가상화는 <xref:System.Windows.Controls.ListView> 및 <xref:System.Windows.Controls.ListBox> 컨트롤의 목록 항목이 데이터에 바인딩될 때 해당 컨트롤에 대해 사용할 수 있도록 설정됩니다.  <xref:System.Windows.Controls.TreeView> 가상화는 <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName> 연결된 속성을 `true`로 설정하는 방법으로 사용할 수 있도록 설정할 수 있습니다.  <xref:System.Windows.Controls.ItemsControl>에서 파생된 사용자 지정 컨트롤 또는 <xref:System.Windows.Controls.ComboBox>와 같이 <xref:System.Windows.Controls.StackPanel> 클래스를 사용하는 기존 항목 컨트롤에 대해 UI 가상화를 설정하려면 <xref:System.Windows.Controls.ItemsControl.ItemsPanel%2A>을 <xref:System.Windows.Controls.VirtualizingStackPanel>로 설정하고 <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizing%2A>을 `true`로 설정합니다.  그러나 자신도 모르게 이러한 컨트롤의 UI 가상화 기능이 해제될 수 있습니다.  UI 가상화는 다음과 같은 경우에 해제됩니다.  
  
-   <xref:System.Windows.Controls.ItemsControl>에 항목 컨테이너를 직접 추가한 경우.  예를 들어 응용 프로그램에서 <xref:System.Windows.Controls.ListBox>에 <xref:System.Windows.Controls.ListBoxItem> 개체를 명시적으로 추가하면 <xref:System.Windows.Controls.ListBox>가 <xref:System.Windows.Controls.ListBoxItem> 개체를 가상화하지 않습니다.  
  
-   <xref:System.Windows.Controls.ItemsControl>의 항목 컨테이너 형식이 다른 경우.  예를 들어 <xref:System.Windows.Controls.Separator> 개체를 사용하는 <xref:System.Windows.Controls.Menu>의 경우에는 <xref:System.Windows.Controls.Menu>에 <xref:System.Windows.Controls.Separator> 및 <xref:System.Windows.Controls.MenuItem> 형식의 개체가 포함되기 때문에 항목 재활용을 구현할 수 없습니다.  
  
-   <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A>을 `false`로 설정한 경우  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A>을 `false`로 설정한 경우  
  
 항목 컨테이너 가상화 할 때 중요 한 고려 사항 항목에 속한 항목 컨테이너와 관련 된 추가 상태 정보를 있는지 여부입니다.  추가적인 상태가 있는 경우 해당 상태를 저장해야 합니다.  예를 들어 <xref:System.Windows.Controls.Expander> 컨트롤에 항목이 포함되어 있고 <xref:System.Windows.Controls.Expander.IsExpanded%2A> 상태가 항목 자체가 아니라 항목의 컨테이너에 바인딩되었을 수 있습니다.  이 경우 새 항목에 대해 컨테이너를 재사용하면 <xref:System.Windows.Controls.Expander.IsExpanded%2A>의 현재 값이 새 항목에 사용되고  이전 항목은 올바른 <xref:System.Windows.Controls.Expander.IsExpanded%2A> 값을 잃게 됩니다.  
  
 현재 모든 WPF 컨트롤은 데이터 가상화를 기본적으로 지원하지 않습니다.  
  
<a name="Container"></a>   
## 컨테이너 재활용  
 .NET Framework 3.5 SP1에서는 <xref:System.Windows.Controls.ItemsControl>에서 상속하는 컨트롤에 대해 사용할 수 있는 UI 가상화에 *컨테이너 재활용*이라는 기능이 추가되었으며 이를 통해서도 스크롤 성능을 높일 수 있습니다.  UI 가상화를 사용하는 <xref:System.Windows.Controls.ItemsControl>이 채워지면 스크롤하여 표시되는 각 항목의 항목 컨테이너가 만들어지고, 스크롤하여 더 이상 표시되지 않는 각 항목의 항목 컨테이너가 소멸됩니다.  *컨테이너 재활용*을 사용하면 컨트롤이 서로 다른 데이터 항목에 기존 항목 컨테이너를 재사용하기 때문에 사용자가 <xref:System.Windows.Controls.ItemsControl>을 스크롤하는 동안 항목 컨테이너가 만들어지고 소멸되는 과정이 반복되지 않습니다.  항목을 설정 하 여 재활용을 사용 하도록 선택할 수도 있는 <xref:System.Windows.Controls.VirtualizingPanel.VirtualizationMode%2A> 속성에 연결 된 <xref:System.Windows.Controls.VirtualizationMode>.  
  
 가상화를 지원하는 모든 <xref:System.Windows.Controls.ItemsControl>에 컨테이너 재활용 기능을 사용할 수 있습니다.  <xref:System.Windows.Controls.ListBox>에서 컨테이너 재활용을 사용하는 예제는 [ListBox의 스크롤 성능 개선](../../../../docs/framework/wpf/controls/how-to-improve-the-scrolling-performance-of-a-listbox.md)을 참조하십시오.  
  
<a name="Supporting"></a>   
## 양방향 가상화 지원  
 <xref:System.Windows.Controls.VirtualizingStackPanel>에서는 기본적으로 UI 가상화가 가로 또는 세로 중 한 방향으로 지원됩니다.  컨트롤에 양방향 가상화를 사용하려면 <xref:System.Windows.Controls.VirtualizingStackPanel> 클래스를 확장하는 사용자 지정 패널을 구현해야 합니다.  <xref:System.Windows.Controls.VirtualizingStackPanel> 클래스는 <xref:System.Windows.Controls.VirtualizingStackPanel.OnViewportSizeChanged%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.LineUp%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.PageUp%2A> 및 <xref:System.Windows.Controls.VirtualizingStackPanel.MouseWheelUp%2A>과 같은 가상 메서드를 노출합니다. 이러한 가상 메서드를 사용하면 목록의 표시 부분에 대한 변경을 감지하여 적절하게 처리할 수 있습니다.  
  
<a name="Optimizing"></a>   
## 템플릿 최적화  
 시각적 트리에는 응용 프로그램의 모든 시각적 요소가 포함됩니다.  여기에는 직접 만든 개체뿐만 아니라 템플릿 확장에 따른 개체도 포함됩니다.  예를 들어 <xref:System.Windows.Controls.Button>을 만들면 시각적 트리에 <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> 및 <xref:System.Windows.Controls.ContentPresenter> 개체도 만들어집니다.  컨트롤 템플릿을 최적화하지 않으면 시각적 트리에 수많은 불필요한 개체가 만들어질 수 있습니다.  시각적 트리에 대한 자세한 내용은 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)를 참조하십시오.  
  
<a name="Deferred"></a>   
## 스크롤 지연  
 기본적으로 사용자가 스크롤 막대의 엄지 단추를 끌면 콘텐츠 뷰가 지속적으로 업데이트됩니다.  컨트롤의 스크롤 속도가 느린 경우에는 스크롤 지연을 사용하는 것이 좋습니다.  스크롤 지연을 사용하면 사용자가 엄지 단추를 놓을 때만 콘텐츠가 업데이트됩니다.  
  
 스크롤 지연을 구현하려면 <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> 속성을 `true`로 설정합니다.  <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A>는 연결된 속성으로, <xref:System.Windows.Controls.ScrollViewer> 및 컨트롤 템플릿에 <xref:System.Windows.Controls.ScrollViewer>가 포함된 모든 컨트롤에 설정할 수 있습니다.  
  
<a name="Controls"></a>   
## 성능 기능을 구현하는 컨트롤  
 다음 표에서는 데이터를 표시하는 일반적인 컨트롤 및 각 컨트롤에 성능 기능이 지원되는지 여부를 보여 줍니다.  이러한 기능을 설정하는 방법은 이전 단원을 참조하십시오.  
  
|컨트롤|시각화|컨테이너 재활용|스크롤 지연|  
|---------|---------|--------------|------------|  
|<xref:System.Windows.Controls.ComboBox>|사용할 수 있음|사용할 수 있음|사용할 수 있음|  
|<xref:System.Windows.Controls.ContextMenu>|사용할 수 있음|사용할 수 있음|사용할 수 있음|  
|<xref:System.Windows.Controls.DocumentViewer>|사용할 수 없음|사용할 수 없음|사용할 수 있음|  
|<xref:System.Windows.Controls.ListBox>|Default|사용할 수 있음|사용할 수 있음|  
|<xref:System.Windows.Controls.ListView>|Default|사용할 수 있음|사용할 수 있음|  
|<xref:System.Windows.Controls.TreeView>|사용할 수 있음|사용할 수 있음|사용할 수 있음|  
|<xref:System.Windows.Controls.ToolBar>|사용할 수 없음|사용할 수 없음|사용할 수 있음|  
  
> [!NOTE]
>  <xref:System.Windows.Controls.TreeView>에서 가상화 및 컨테이너 재활용을 사용하는 예제는 [TreeView의 성능 개선](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md)을 참조하십시오.  
  
## 참고 항목  
 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)   
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [컨트롤](../../../../docs/framework/wpf/controls/index.md)   
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [연습: WPF 응용 프로그램에서 응용 프로그램 데이터 캐싱](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)