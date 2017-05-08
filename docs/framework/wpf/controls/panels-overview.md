---
title: "Panel 개요 | Microsoft Docs"
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
  - "컨트롤, 패널"
  - "Panel 컨트롤[WPF], Panel 컨트롤 정보"
ms.assetid: f73644af-9941-4611-8754-6d4cef03fc44
caps.latest.revision: 48
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 45
---
# Panel 개요
<xref:System.Windows.Controls.Panel> 요소는 크기 및 차원, 위치, 자식 콘텐츠 정렬 등과 같은 요소 렌더링을 제어하는 구성 요소입니다.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 사용자 지정 <xref:System.Windows.Controls.Panel> 요소를 생성하는 기능뿐만 아니라 미리 정의된 많은 <xref:System.Windows.Controls.Panel> 요소를 제공합니다.  
  
 이 항목에는 다음 단원이 포함되어 있습니다.  
  
-   [Panel 클래스](#Panels_view_from_10000_feet)  
  
-   [Panel 요소의 공용 멤버](#Panels_declared_members)  
  
-   [파생 Panel 요소](#Panels_derived_elements)  
  
-   [사용자 인터페이스 패널](#Panels_main_UI_elements)  
  
-   [중첩 Panel 요소](#Panels_nested_panel_elements)  
  
-   [사용자 지정 Panel 요소](#Panels_custom_panel_elements)  
  
-   [지역화\/전역화 지원](#Panels_global_localization)  
  
-   [관련 항목](#seeAlsoToggle)  
  
<a name="Panels_view_from_10000_feet"></a>   
## Panel 클래스  
 <xref:System.Windows.Controls.Panel>은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 레이아웃 지원을 제공하는 모든 요소에 대한 기본 클래스입니다.  파생 <xref:System.Windows.Controls.Panel> 요소는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 및 코드에서 요소를 배치하고 정렬하는 데 사용됩니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 여러 가지 복잡한 레이아웃을 가능하게 하는 광범위한 파생 패널 구현 집합이 포함되어 있습니다.  이러한 파생 클래스는 대부분의 표준 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 시나리오를 가능하게 하는 속성 및 메서드를 노출합니다.  요구에 맞는 자식 정렬 동작을 찾을 수 없는 개발자는 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 및 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 메서드를 재정의하여 새 레이아웃을 만들 수 있습니다.  사용자 지정 레이아웃 동작에 대한 자세한 내용은 [사용자 지정 Panel 요소](#Panels_custom_panel_elements)를 참조하십시오.  
  
<a name="Panels_declared_members"></a>   
## Panel의 공용 멤버  
 모든 <xref:System.Windows.Controls.Panel> 요소는 <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> 및 <xref:System.Windows.FrameworkElement.LayoutTransform%2A>을 비롯하여 <xref:System.Windows.FrameworkElement>로 정의되는 기본 크기 조정 및 배치 속성을 지원합니다.  <xref:System.Windows.FrameworkElement>로 정의되는 배치 속성에 대한 자세한 내용은 [맞춤, 여백 및 안쪽 여백 개요](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Controls.Panel>은 레이아웃을 이해하고 사용하는 데 있어 매우 중요한 추가 속성을 노출합니다.  <xref:System.Windows.Controls.Panel.Background%2A> 속성은 <xref:System.Windows.Media.Brush>를 사용하여 파생 panel 요소의 경계 사이의 영역을 채우는 데 사용됩니다.  <xref:System.Windows.Controls.Panel.Children%2A>은 <xref:System.Windows.Controls.Panel>을 구성하는 요소의 자식 컬렉션을 나타냅니다.  <xref:System.Windows.Controls.Panel.InternalChildren%2A>은 데이터 바인딩을 통해 생성된 멤버와 함께 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션의 콘텐츠를 나타냅니다.  둘 모두 부모 <xref:System.Windows.Controls.Panel> 내에 호스팅되는 자식 요소의 <xref:System.Windows.Controls.UIElementCollection>으로 구성됩니다.  
  
 Panel은 파생 <xref:System.Windows.Controls.Panel>에서 계층화 정렬을 수행하는 데 사용할 수 있는 <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=fullName> 연결된 속성을 노출합니다.  <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=fullName> 값이 큰 패널의 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션은 <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=fullName> 값이 작은 해당 컬렉션보다 앞에 나타납니다.  이는 자식이 동일한 좌표 공간을 공유할 수 있도록 허용하는 <xref:System.Windows.Controls.Canvas> 및 <xref:System.Windows.Controls.Grid>와 같은 패널에 특히 유용합니다.  
  
 <xref:System.Windows.Controls.Panel>은 <xref:System.Windows.Controls.Panel>의 기본 표시 동작을 재정의하는 데 사용할 수 있는 <xref:System.Windows.Controls.Panel.OnRender%2A> 메서드도 정의합니다.  
  
#### 연결된 속성  
 파생 panel 요소는 [연결된 속성](GTMT)을 광범위하게 사용합니다.  연결된 속성은 기존의 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성 “래퍼”가 없는 [종속성 속성](GTMT)의 특수 형식입니다.  연결된 속성에는 아래의 몇 가지 예제에서 볼 수 있는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]의 특수 구문이 있습니다.  
  
 연결된 속성의 용도 중 하나는 실질적으로 부모 요소가 정의한 속성의 고유 값을 자식 요소가 저장할 수 있도록 하는 것입니다.  이 기능이 있는 응용 프로그램에서는 자식 요소가 자신이 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에 표시될 방법을 부모에게 알리게 됩니다. 이는 응용 프로그램 레이아웃에 매우 유용합니다.  자세한 내용은 [연결된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)를 참조하십시오.  
  
<a name="Panels_derived_elements"></a>   
## 파생 Panel 요소  
 많은 개체가 <xref:System.Windows.Controls.Panel>에서 파생되지만 이러한 모든 개체를 루트 레이아웃 공급자로 사용할 수는 없습니다.  응용 프로그램 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 만들기 위해 <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel> 및 <xref:System.Windows.Controls.WrapPanel>이라는 6개의 정의된 panel 클래스가 특별히 디자인되었습니다.  
  
 각 panel 요소는 다음 표와 같은 고유한 특수 기능을 캡슐화합니다.  
  
|요소 이름|UI 패널 여부|설명|  
|-----------|--------------|--------|  
|<xref:System.Windows.Controls.Canvas>|예|<xref:System.Windows.Controls.Canvas> 영역에 상대적인 좌표를 사용하여 자식 요소를 명시적으로 배치할 수 있는 영역을 정의합니다.|  
|<xref:System.Windows.Controls.DockPanel>|예|자식 요소를 서로에 상대적으로 가로나 세로로 정렬할 수 있는 영역을 정의합니다.|  
|<xref:System.Windows.Controls.Grid>|예|열과 행으로 구성되는 유연한 표 영역을 정의합니다.  <xref:System.Windows.Controls.Grid>의 자식 요소는 <xref:System.Windows.FrameworkElement.Margin%2A> 속성을 사용하여 정확한 위치를 지정할 수 있습니다.|  
|<xref:System.Windows.Controls.StackPanel>|예|자식 요소를 가로 또는 세로 방향으로 지정할 수 있는 단일 선에 따라 정렬합니다.|  
|<xref:System.Windows.Controls.Primitives.TabPanel>|아니요|<xref:System.Windows.Controls.TabControl>에 있는 탭 단추의 레이아웃을 처리합니다.|  
|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|아니요|<xref:System.Windows.Controls.ToolBar> 컨트롤 내의 콘텐츠를 정렬합니다.|  
|<xref:System.Windows.Controls.Primitives.UniformGrid>|아니요|<xref:System.Windows.Controls.Primitives.UniformGrid>는 셀 크기가 모두 동일한 표에 자식을 정렬하는 데 사용됩니다.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|아니요|해당 자식 컬렉션을 "가상화"할 수 있는 패널에 대한 기본 클래스를 제공합니다.|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|예|가로 또는 세로 방향으로 지정된 한 줄에 콘텐츠를 정렬하고 가상화합니다.|  
|<xref:System.Windows.Controls.WrapPanel>|예|<xref:System.Windows.Controls.WrapPanel>은 자식 요소를 왼쪽에서 오른쪽으로 순차적으로 배치하고, 포함하는 상자의 가장자리에서 내용을 다음 줄로 바꿉니다.  이후에는 <xref:System.Windows.Controls.WrapPanel.Orientation%2A> 속성 값에 따라 순서가 위쪽에서 아래쪽으로 또는 오른쪽에서 왼쪽으로 순차적으로 지정됩니다.|  
  
<a name="Panels_main_UI_elements"></a>   
## 사용자 인터페이스 패널  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 시나리오를 지원하기 위해 최적화된 6개의 panel 클래스인 <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.VirtualizingStackPanel> 및 <xref:System.Windows.Controls.WrapPanel>을 사용할 수 있습니다.  이러한 panel 요소는 사용이 용이하고 융통성이 있으며 대부분의 응용 프로그램에 대해 충분히 확장 가능합니다.  
  
 각 파생 <xref:System.Windows.Controls.Panel> 요소는 크기 조정 제약 조건을 서로 다르게 처리합니다.  <xref:System.Windows.Controls.Panel>이 가로 또는 세로 방향에서 제약 조건을 처리하는 방법을 이해하면 레이아웃을 예측하는 데 더욱 도움이 됩니다.  
  
|**패널 이름**|**x 차원**|**y 차원**|  
|---------------|--------------|--------------|  
|<xref:System.Windows.Controls.Canvas>|콘텐츠의 제약을 받음|콘텐츠의 제약을 받음|  
|<xref:System.Windows.Controls.DockPanel>|제약을 받음|제약을 받음|  
|<xref:System.Windows.Controls.StackPanel>\(세로 방향\)|제약을 받음|콘텐츠의 제약을 받음|  
|<xref:System.Windows.Controls.StackPanel>\(가로 방향\)|콘텐츠의 제약을 받음|제약을 받음|  
|<xref:System.Windows.Controls.Grid>|제약을 받음|제약을 받음\(예외: <xref:System.Windows.GridUnitType>가 행 및 열에 적용되는 경우\)|  
|<xref:System.Windows.Controls.WrapPanel>|콘텐츠의 제약을 받음|콘텐츠의 제약을 받음|  
  
 이러한 각 요소에 대한 자세한 내용 및 사용 예제는 아래를 참조하십시오.  
  
<a name="Panels_overview_Canvas_subsection"></a>   
### Canvas  
 <xref:System.Windows.Controls.Canvas> 요소를 사용하면 절대 *x* 좌표 및 *y* 좌표에 따라 콘텐츠의 위치를 지정할 수 있습니다.  요소를 고유 위치에 그릴 수 있지만 여러 요소가 동일한 좌표를 사용하는 경우에는 해당 요소가 태그에 나타나는 순서대로 요소가 그려집니다.  
  
 <xref:System.Windows.Controls.Canvas>는 모든 <xref:System.Windows.Controls.Panel> 중 가장 유연한 레이아웃 지원을 제공합니다.  Height 및 Width 속성은 캔버스의 영역을 정의하는 데 사용되며 내부 요소에는 부모 <xref:System.Windows.Controls.Canvas>의 영역에 상대적으로 절대 좌표가 할당됩니다.  4개의 연결된 속성 <xref:System.Windows.Controls.Canvas.Left%2A?displayProperty=fullName>, <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=fullName>, <xref:System.Windows.Controls.Canvas.Right%2A?displayProperty=fullName> 및 <xref:System.Windows.Controls.Canvas.Bottom%2A?displayProperty=fullName>을 사용하면 <xref:System.Windows.Controls.Canvas> 내에서의 개체 배치를 보다 자세히 제어할 수 있으므로 개발자가 화면에서 요소를 정확하게 배치 및 정렬할 수 있습니다.  
  
#### 캔버스 내의 ClipToBounds  
 <xref:System.Windows.Controls.Canvas>는 정의된 자체 <xref:System.Windows.FrameworkElement.Height%2A> 및 <xref:System.Windows.FrameworkElement.Width%2A>를 벗어나는 좌표를 비롯하여 화면의 모든 위치에 자식 요소를 배치할 수 있습니다.  또한 <xref:System.Windows.Controls.Canvas>는 자식 크기에 의해 영향을 받지 않습니다.  따라서 자식 요소는 부모 <xref:System.Windows.Controls.Canvas>의 경계 사각형을 벗어나는 다른 요소를 그릴 수 있습니다.  부모 <xref:System.Windows.Controls.Canvas>의 범위를 벗어나는 자식을 그릴 수 있는 것이 <xref:System.Windows.Controls.Canvas>의 기본 동작입니다.  이러한 동작이 필요 없는 경우에는 <xref:System.Windows.UIElement.ClipToBounds%2A> 속성을 `true`로 설정합니다.  이렇게 하면 <xref:System.Windows.Controls.Canvas>가 자체 크기로 클리핑됩니다.  <xref:System.Windows.Controls.Canvas>는 해당 범위를 벗어나는 자식을 그릴 수 있도록 허용하는 유일한 레이아웃 요소입니다.  
  
 이러한 동작에 대한 그림을 보려면 [Width Properties Comparison 샘플](http://go.microsoft.com/fwlink/?LinkID=160050)을 참조하십시오.  
  
#### 캔버스 정의 및 사용  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 또는 코드를 사용하면 <xref:System.Windows.Controls.Canvas>를 간단하게 인스턴스화할 수 있습니다.  다음 예제에서는 <xref:System.Windows.Controls.Canvas>를 사용하여 콘텐츠의 절대 위치를 지정하는 방법을 보여 줍니다.  이 코드에서는 세 개의 100픽셀 사각형을 생성합니다.  첫 번째 사각형은 빨간색이며 왼쪽 위\(*x, y*\) 위치가 \(0, 0\)으로 지정됩니다.  두 번째 사각형은 녹색이며 첫 번째 사각형의 바로 아래 오른쪽인 \(100, 100\)으로 왼쪽 위 위치가 지정됩니다.  세 번째 사각형은 파란색이며 왼쪽 위 위치는 \(50, 50\)입니다. 따라서 세 번째 사각형은 첫 번째 사각형의 오른쪽 아래 1\/4과 두 번째의 왼쪽 위 1\/4을 덮습니다.  세 번째 사각형은 마지막에 배치되므로 다른 두 사각형의 위에 표시됩니다. 즉, 겹친 부분의 색은 세 번째 상자의 색입니다.  
  
 [!code-csharp[CanvasOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasOvwSample/CSharp/Canvas_Ovw_Sample.cs#1)]
 [!code-vb[CanvasOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasOvwSample/VisualBasic/canvas_vb.vb#1)]
 [!code-xml[CanvasOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/CanvasOvwSample/XAML/default.xaml#1)]  
  
 컴파일된 응용 프로그램은 다음과 같은 새 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 생성합니다.  
  
 ![일반적인 Canvas 요소](../../../../docs/framework/wpf/controls/media/panel-intro-canvas.png "panel\_intro\_canvas")  
  
<a name="Panels_overview_DockPanel_subsection"></a>   
### DockPanel  
 <xref:System.Windows.Controls.DockPanel> 요소는 자식 콘텐츠 요소에 설정된 <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> 연결된 속성을 사용하여 컨테이너의 가장자리를 따라 콘텐츠를 배치합니다.  <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>을 <xref:System.Windows.Controls.Dock> 또는 <xref:System.Windows.Controls.Dock>으로 설정하면 자식 요소가 서로의 위 또는 아래에 배치됩니다.  <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName>을 <xref:System.Windows.Controls.Dock> 또는 <xref:System.Windows.Controls.Dock>로 설정하면 자식 요소가 서로의 왼쪽 또는 오른쪽에 배치됩니다.  <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> 속성은 <xref:System.Windows.Controls.DockPanel>의 자식으로 추가되는 마지막 요소의 위치를 결정합니다.  
  
 <xref:System.Windows.Controls.DockPanel>을 사용하여 단추 집합과 같이 서로 관련된 컨트롤 그룹을 배치할 수 있습니다.  이를 사용하여 [!INCLUDE[TLA#tla_outlook](../../../../includes/tlasharptla-outlook-md.md)]의 UI와 유사한 "창이 있는" [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 만들 수도 있습니다.  
  
#### 콘텐츠에 맞게 크기 조정  
 해당 <xref:System.Windows.FrameworkElement.Height%2A> 및 <xref:System.Windows.FrameworkElement.Width%2A> 속성을 지정하지 않으면 <xref:System.Windows.Controls.DockPanel>의 크기가 해당 콘텐츠에 맞게 조정됩니다.  크기는 해당 자식 요소의 크기에 맞게 늘이거나 줄일 수 있습니다.  그러나 이러한 속성을 지정하며 다음으로 지정하는 자식 요소를 위한 공간이 더 이상 없는 경우에는 <xref:System.Windows.Controls.DockPanel>이 해당 자식 요소 또는 후속 자식 요소를 표시하지 않으며 후속 자식 요소를 측정하지 않습니다.  
  
#### LastChildFill  
 기본적으로 <xref:System.Windows.Controls.DockPanel> 요소의 마지막 자식이 할당되지 않은 나머지 공간을 "채웁니다".  이러한 동작이 필요 없는 경우에는 <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> 속성을 `false`로 설정합니다.  
  
#### DockPanel 정의 및 사용  
 다음 예제에서는 <xref:System.Windows.Controls.DockPanel>을 사용하여 공간을 분할하는 방법을 보여 줍니다.  5개의 <xref:System.Windows.Controls.Border> 요소가 부모 <xref:System.Windows.Controls.DockPanel>의 자식으로 추가됩니다.  각 요소는 <xref:System.Windows.Controls.DockPanel>의 서로 다른 위치 지정 속성을 사용하여 공간을 분할합니다.  마지막 요소가 할당되지 않은 나머지 공간을 "채웁니다".  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
 컴파일된 응용 프로그램은 다음과 같은 새 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 생성합니다.  
  
 ![일반적인 DockPanel 시나리오](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.png "panel\_intro\_dockpanel")  
  
<a name="Panels_overview_Grid_subsection"></a>   
### 모눈  
 <xref:System.Windows.Controls.Grid> 요소는 절대 위치 지정 컨트롤과 표 형식 데이터 컨트롤의 기능을 병합합니다.  <xref:System.Windows.Controls.Grid>를 사용하면 요소의 위치와 스타일을 쉽게 지정할 수 있습니다.  또한 <xref:System.Windows.Controls.Grid>는 유연한 행 및 열 그룹화를 정의할 수 있도록 하며 여러 <xref:System.Windows.Controls.Grid> 요소 간에 크기 조정 정보를 공유할 수 있는 메커니즘도 제공합니다.  
  
#### 모눈과 표의 차이점  
 <xref:System.Windows.Documents.Table> 및 <xref:System.Windows.Controls.Grid>는 공통된 기능을 공유하지만 각각 적합한 시나리오는 서로 다릅니다.  <xref:System.Windows.Documents.Table>은 유동 콘텐츠 내에서 사용되도록 설계된 것입니다. 유동 콘텐츠에 대한 자세한 내용은 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)를 참조하십시오.  모눈은 기본적으로는 유동 콘텐츠 외부 어디에서든 사용할 수 있으나 폼 내부에서 사용하기에 가장 적합합니다.  <xref:System.Windows.Documents.FlowDocument> 내부에서 <xref:System.Windows.Documents.Table>은 페이지 매김, 열 흐름 변경 및 콘텐츠 선택과 같은 유동 콘텐츠 동작을 지원하지만 <xref:System.Windows.Controls.Grid>는 지원하지 않습니다.  한편 <xref:System.Windows.Controls.Grid>는 <xref:System.Windows.Controls.Grid>가 행 및 열 인덱스를 기반으로 요소를 추가하는 반면 <xref:System.Windows.Documents.Table>은 그렇지 않다는 등의 여러 가지 이유에서 <xref:System.Windows.Documents.FlowDocument> 외부에서 사용하기에 가장 적합합니다.  <xref:System.Windows.Controls.Grid> 요소를 사용하면 자식 콘텐츠를 계층화할 수 있으므로 단일 "셀" 내에 둘 이상의 요소가 존재할 수 있습니다. <xref:System.Windows.Documents.Table>은 계층화를 지원하지 않습니다.  <xref:System.Windows.Controls.Grid>의 자식 요소는 해당 "셀" 경계 영역을 기준으로 절대 위치에 배치될 수 있습니다.  <xref:System.Windows.Documents.Table>은 이 기능을 지원하지 않습니다.  마지막으로 <xref:System.Windows.Controls.Grid>는 <xref:System.Windows.Documents.Table>보다 간단합니다.  
  
#### 열 및 행의 크기 조정 동작  
 <xref:System.Windows.Controls.Grid> 내에 정의된 열 및 행에 대해 <xref:System.Windows.GridUnitType> 크기 조정을 활용하여 나머지 공간을 비례적으로 나눌 수 있습니다.  <xref:System.Windows.GridUnitType>를 행이나 열의 Height 또는 Width로 선택하면 사용 가능한 나머지 공간의 가중 크기가 해당 열이나 행에 할당됩니다.  이러한 동작은 열이나 행 내의 콘텐츠 크기에 따라 공간을 균등하게 나누는 <xref:System.Windows.GridUnitType>의 동작과 대조됩니다.  이 값은 `*` 또는 `2*`\([!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용할 경우\)로 표현됩니다.  첫 번째 경우에는 행이나 열에 사용 가능한 공간의 1배가 할당되고 두 번째 경우에는 2배가 할당되는 식입니다.  이 방법과 `Stretch`의 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 값으로 공간을 비율에 따라 배분하는 방법을 결합하면 레이아웃 공간을 화면 공간의 백분율에 따라 나눌 수 있습니다.  이러한 방식으로 공간을 배분할 수 있는 레이아웃 패널은 <xref:System.Windows.Controls.Grid>뿐입니다.  
  
#### 모눈 정의 및 사용  
 다음 예제에서는 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 시작 메뉴에서 사용 가능한 실행 대화 상자에 있는 것과 유사한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 빌드하는 방법을 보여 줍니다.  
  
 [!code-csharp[GridRunDialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
 컴파일된 응용 프로그램은 다음과 같은 새 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 생성합니다.  
  
 ![일반적인 Grid 요소](../../../../docs/framework/wpf/controls/media/avalon-run-dialog.png "avalon\_run\_dialog")  
  
<a name="Panels_overview_StackPanel_subsection"></a>   
### StackPanel  
 <xref:System.Windows.Controls.StackPanel>을 사용하면 요소를 할당된 방향으로 "쌓을" 수 있습니다.  기본 스택 방향은 수직입니다.  <xref:System.Windows.Controls.StackPanel.Orientation%2A> 속성을 사용하면 콘텐츠의 흐름을 제어할 수 있습니다.  
  
#### StackPanel 및DockPanel  
 <xref:System.Windows.Controls.DockPanel>도 자식 요소를 "쌓을" 수는 있지만 <xref:System.Windows.Controls.DockPanel>과 <xref:System.Windows.Controls.StackPanel>은 일부 사용 시나리오에서 유사한 결과를 생성하지 않습니다.  예를 들어 자식 요소의 순서가 <xref:System.Windows.Controls.DockPanel>에서는 자식 요소의 크기에 영향을 주지만 <xref:System.Windows.Controls.StackPanel>에서는 그렇지 않을 수 있습니다.  <xref:System.Windows.Controls.StackPanel>은 <xref:System.Double.PositiveInfinity>에서 쌓는 방향으로 측정하지만 <xref:System.Windows.Controls.DockPanel>은 사용 가능한 크기만 측정하기 때문에 이러한 동작 차이가 발생합니다.  
  
 다음 예제에서는 이러한 주요 차이를 보여 줍니다.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
 렌더링 동작 차이는 다음 그림에서 확인할 수 있습니다.  
  
 ![스크린 샷: StackPanel 대 DockPanel 스크린 샷](../../../../docs/framework/wpf/controls/media/layout-smiley-stackpanel.png "layout\_smiley\_stackpanel")  
  
#### StackPanel 정의 및 사용  
 다음 예제에서는 <xref:System.Windows.Controls.StackPanel>을 사용하여 세로 방향으로 배치된 단추 집합을 만드는 방법을 보여 줍니다.  가로 방향으로 배치하려면 <xref:System.Windows.Controls.StackPanel.Orientation%2A> 속성을 <xref:System.Windows.Controls.Orientation>로 설정합니다.  
  
 [!code-csharp[StackPanel_ovw2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanel_ovw2/CSharp/StackPanel_Ovw_Sample2.cs#1)]
 [!code-vb[StackPanel_ovw2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanel_ovw2/VisualBasic/StackPanelOvw.vb#1)]  
  
 컴파일된 응용 프로그램은 다음과 같은 새 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 생성합니다.  
  
 ![일반적인 StackPanel 요소](../../../../docs/framework/wpf/controls/media/panel-intro-stackpanel.png "panel\_intro\_stackpanel")  
  
<a name="Panels_overview_VirtualizingStackPanel_subsection"></a>   
#### VirtualizingStackPanel  
 또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 데이터 바인딩된 자식 콘텐츠를 자동으로 "가상화"하는 <xref:System.Windows.Controls.StackPanel> 요소의 변형을 제공합니다.  여기서 가상화라는 단어는 화면에 표시되는 항목에 따라 많은 수의 데이터 항목에서 요소의 하위 집합이 생성되는 기술을 가리킵니다.  특정 시점에 화면에 표시되는 것보다 많은 개수의 UI 요소를 생성하는 것은 메모리 및 프로세서 측면에서 비효율적입니다.  <xref:System.Windows.Controls.VirtualizingPanel>이 제공하는 기능을 통해 <xref:System.Windows.Controls.VirtualizingStackPanel>은 표시되는 항목을 계산하고, <xref:System.Windows.Controls.ListBox> 또는 <xref:System.Windows.Controls.ListView>와 같은 <xref:System.Windows.Controls.ItemsControl>의 <xref:System.Windows.Controls.ItemContainerGenerator>를 사용하여 표시되는 항목에 대한 요소만 만듭니다.  
  
 <xref:System.Windows.Controls.VirtualizingStackPanel> 요소는 <xref:System.Windows.Controls.ListBox>와 같은 컨트롤에 대한 항목 호스트로 자동 설정됩니다.  데이터 바인딩된 컬렉션을 호스팅하는 경우 콘텐츠가 <xref:System.Windows.Controls.ScrollViewer>의 범위 내에 있으면 콘텐츠는 자동으로 가상화됩니다.  이렇게 하면 많은 자식 항목을 호스팅하는 경우 성능이 크게 개선됩니다.  
  
 다음 태그에서는 <xref:System.Windows.Controls.VirtualizingStackPanel>을 항목 호스트로 사용하는 방법을 보여 줍니다.  가상화가 발생하려면 <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName> [연결된 속성](GTMT)을 `true`\(기본값\)로 설정해야 합니다.  
  
 [!code-xml[VirtualizingStackPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VirtualizingStackPanel_Intro/CS/default.xaml#1)]  
  
<a name="Panels_overview_WrapPanel"></a>   
### WrapPanel  
 <xref:System.Windows.Controls.WrapPanel>은 자식 요소를 왼쪽에서 오른쪽으로 순차적으로 배치하고, 해당 부모 컨테이너의 가장자리에 도달할 경우 내용을 다음 줄로 바꾸는 데 사용됩니다.  콘텐츠는 가로 또는 세로 방향으로 설정할 수 있습니다.  <xref:System.Windows.Controls.WrapPanel>은 간단한 유동 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 시나리오에 유용하며  모든 해당 자식 요소에 동일한 크기를 적용하는 데에도 사용될 수 있습니다.  
  
 다음 예제에서는 해당 컨테이너의 가장자리에 도달할 경우 줄을 바꾸는 <xref:System.Windows.Controls.Button> 컨트롤을 표시하는 <xref:System.Windows.Controls.WrapPanel>을 만드는 방법을 보여 줍니다.  
  
 [!code-cpp[WrapPanel_Intro#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WrapPanel_Intro/CPP/WrapPanel_Code.cpp#1)]
 [!code-csharp[WrapPanel_Intro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WrapPanel_Intro/CSharp/WrapPanel_Code.cs#1)]
 [!code-vb[WrapPanel_Intro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WrapPanel_Intro/VisualBasic/WrapPanel_vb.vb#1)]
 [!code-xml[WrapPanel_Intro#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/WrapPanel_Intro/XAML/default.xaml#1)]  
  
 컴파일된 응용 프로그램은 다음과 같은 새 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 생성합니다.  
  
 ![일반적인 WrapPanel 요소](../../../../docs/framework/wpf/controls/media/wrappanel-element.png "WrapPanel\_Element")  
  
<a name="Panels_nested_panel_elements"></a>   
## 중첩 Panel 요소  
 <xref:System.Windows.Controls.Panel> 요소를 각 해당 요소 내에 중첩시켜 복잡한 레이아웃을 생성할 수 있습니다.  이렇게 하면 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 부분에 하나의 <xref:System.Windows.Controls.Panel>이 적절한 경우 매우 유용하지만 다양한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 부분의 요구에는 맞지 않을 수 있습니다.  
  
 응용 프로그램에서 지원할 수 있는 중첩의 양에는 사실상 제한이 없지만 원하는 레이아웃에 대해 실제로 필요한 패널만 사용하도록 응용 프로그램을 제한하는 것이 일반적으로 가장 좋습니다.  대부분의 경우 융통성을 위해 중첩 패널 대신 <xref:System.Windows.Controls.Grid> 요소를 레이아웃 컨테이너로 사용합니다.  이렇게 하면 불필요한 요소를 트리에서 제외하여 응용 프로그램 성능이 향상됩니다.  
  
 다음 예제에서는 특정 레이아웃을 만들기 위해 중첩 <xref:System.Windows.Controls.Panel> 요소를 활용하는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 만드는 방법을 보여 줍니다.  여기서는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 구조체를 제공하는 데 <xref:System.Windows.Controls.DockPanel> 요소를 사용하고 부모 <xref:System.Windows.Controls.DockPanel> 내에 자식 요소를 정확하게 배치하는 데 중첩 <xref:System.Windows.Controls.StackPanel> 요소, <xref:System.Windows.Controls.Grid> 및 <xref:System.Windows.Controls.Canvas>를 사용합니다.  
  
 [!code-csharp[Nested_Panels#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Nested_Panels/CSharp/nestedpanels.cs#1)]
 [!code-vb[Nested_Panels#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Nested_Panels/VisualBasic/nestedpanels.vb#1)]  
  
 컴파일된 응용 프로그램은 다음과 같은 새 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 생성합니다.  
  
 ![중첩된 패널의 이점을 활용하는 UI](../../../../docs/framework/wpf/controls/media/nested-panels.png "nested\_panels")  
  
<a name="Panels_custom_panel_elements"></a>   
## 사용자 지정 Panel 요소  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 유연한 레이아웃 컨트롤 배열을 제공하지만 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 및 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 메서드를 재정의하여 사용자 지정 레이아웃 동작을 얻을 수도 있습니다.  사용자 지정 크기 조정 및 위치 지정은 이러한 재정의 메서드 내에서 새 위치 지정 동작을 정의하여 수행할 수 있습니다.  
  
 마찬가지로 <xref:System.Windows.Controls.Canvas> 또는 <xref:System.Windows.Controls.Grid>와 같은 파생 클래스를 기반으로 하는 사용자 지정 레이아웃 동작을 해당 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 및 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 메서드를 재정의하여 정의할 수 있습니다.  
  
 다음 태그에서는 사용자 지정 <xref:System.Windows.Controls.Panel> 요소를 만드는 방법을 보여 줍니다.  `PlotPanel`로 정의된 이 새 <xref:System.Windows.Controls.Panel>은 하드 코드된 *x* 좌표 및 *y* 좌표를 사용하여 자식 요소의 위치를 지정하는 작업을 지원합니다.  이 예제에서 표시되지 않은 <xref:System.Windows.Shapes.Rectangle> 요소는 그림 지점 50\(*x*\), 50\(*y*\)에 배치됩니다.  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
 더 복잡한 사용자 지정 패널 구현을 보려면 [Create a Custom Content\-Wrapping Panel 샘플](http://go.microsoft.com/fwlink/?LinkID=159979)을 참조하십시오.  
  
<a name="Panels_global_localization"></a>   
## 지역화\/전역화 지원  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 지역화할 수 있는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 생성에 도움이 되는 여러 가지 기능을 지원합니다.  
  
 모든 패널은 사용자의 로캘 또는 언어 설정에 따라 동적으로 콘텐츠의 흐름을 변경하는 데 사용할 수 있는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성을 기본적으로 지원합니다.  자세한 내용은 <xref:System.Windows.FrameworkElement.FlowDirection%2A>을 참조하십시오.  
  
 <xref:System.Windows.Window.SizeToContent%2A> 속성은 응용 프로그램 개발자가 지역화된 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 요구를 예상할 수 있도록 하는 메커니즘을 제공합니다.  이 속성의 <xref:System.Windows.SizeToContent> 값을 사용하면 부모 <xref:System.Windows.Window>의 크기가 콘텐츠에 맞게 동적으로 조정되며 해당 창에 인위적인 높이 또는 너비 제한이 적용되지 않습니다.  
  
 <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Grid> 및 <xref:System.Windows.Controls.StackPanel>은 모두 지역화할 수 있는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에 대해 적합한 선택입니다.  그러나 <xref:System.Windows.Controls.Canvas>는 콘텐츠를 절대 배치하여 지역화하기가 힘들어지기 때문에 적합한 선택이 아닙니다.  
  
 지역화할 수 있는 [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]가 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 만드는 방법에 대한 자세한 내용은 [자동 레이아웃 사용 개요](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)를 참조하십시오.  
  
## 참고 항목  
 [연습: WPF 시작](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)   
 [WPF Layout Gallery 샘플](http://go.microsoft.com/fwlink/?LinkID=160054)   
 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)   
 [WPF Controls Gallery 샘플](http://go.microsoft.com/fwlink/?LinkID=160053)   
 [맞춤, 여백 및 안쪽 여백 개요](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)   
 [Create a Custom Content\-Wrapping Panel 샘플](http://go.microsoft.com/fwlink/?LinkID=159979)   
 [연결된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)   
 [자동 레이아웃 사용 개요](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)   
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)