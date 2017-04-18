---
title: "레이아웃 | Microsoft Docs"
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
  - "컨트롤[WPF], 레이아웃 시스템"
  - "레이아웃 시스템[WPF]"
  - "WPF 레이아웃 시스템"
ms.assetid: 3eecdced-3623-403a-a077-7595453a9221
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# 레이아웃
이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 레이아웃 시스템에 대해 설명합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 사용자 인터페이스를 만들려면 언제, 어떻게 레이아웃을 계산해야 하는지를 이해해야 합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [요소 경계 상자](#LayoutSystem_BoundingBox)  
  
-   [레이아웃 시스템](#LayoutSystem_Overview)  
  
-   [자식 항목 측정 및 정렬](#LayoutSystem_Measure_Arrange)  
  
-   [패널 요소 및 사용자 지정 레이아웃 동작](#LayoutSystem_PanelsCustom)  
  
-   [레이아웃 성능 고려 사항](#LayoutSystem_Performance)  
  
-   [하위 픽셀 렌더링 및 레이아웃 반올림](#LayoutSystem_LayoutRounding)  
  
-   [새로운 기능](#LayoutSystem_whatsnext)  
  
<a name="LayoutSystem_BoundingBox"></a>   
## 요소 경계 상자  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 레이아웃을 고려할 때는 모든 요소를 둘러싸고 있는 경계 상자를 이해하는 것이 중요합니다.  레이아웃 시스템에서 사용하는 각 <xref:System.Windows.FrameworkElement>를 레이아웃에 배치되는 직사각형으로 생각할 수 있습니다.  <xref:System.Windows.Controls.Primitives.LayoutInformation> 클래스는 요소의 레이아웃 할당 또는 슬롯에 대한 경계를 반환합니다.  해당 직사각형의 크기는 사용 가능한 화면 크기, 제약 조건의 크기, 레이아웃 고유 속성\(예: 여백 및 안쪽 여백\) 그리고 부모 <xref:System.Windows.Controls.Panel> 요소의 개별 동작을 계산하여 결정합니다.  이 데이터를 처리함으로써 레이아웃 시스템은 특정 <xref:System.Windows.Controls.Panel>의 모든 자식 항목의 위치를 계산할 수 있습니다.  <xref:System.Windows.Controls.Border>와 같이 부모 요소에 정의된 크기 조정 특성은 자식 항목에 영향을 줍니다.  
  
 다음 그림에서는 간단한 레이아웃을 보여 줍니다.  
  
 ![경계 상자가 없는 일반적인 Grid](../../../../docs/framework/wpf/advanced/media/boundingbox1.png "boundingbox1")  
  
 이 레이아웃은 다음 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하여 만들 수 있습니다.  
  
 [!code-xml[LayoutInformation#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml#1)]  
  
 단일 <xref:System.Windows.Controls.TextBlock> 요소가 <xref:System.Windows.Controls.Grid>에 호스팅됩니다.  텍스트는 첫 번째 열의 왼쪽 위 모퉁이만 채우지만 <xref:System.Windows.Controls.TextBlock>에 할당된 공간은 실제로 훨씬 큽니다.  <xref:System.Windows.FrameworkElement>의 경계 상자는 <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> 메서드를 사용하여 검색할 수 있습니다.  다음 그림에서는 <xref:System.Windows.Controls.TextBlock> 요소에 대한 경계 상자를 보여 줍니다.  
  
 ![이제 TextBlock의 경계 상자가 표시됨](../../../../docs/framework/wpf/advanced/media/boundingbox2.png "boundingbox2")  
  
 노란색 사각형으로 표시되는 <xref:System.Windows.Controls.TextBlock> 요소에 대해 할당된 공간은 실제로는 표시되는 공간보다 훨씬 큽니다.  요소가 <xref:System.Windows.Controls.Grid>에 더 추가될 때 추가되는 요소의 형식과 크기에 따라 이 할당이 축소되거나 확장될 수 있습니다.  
  
 <xref:System.Windows.Controls.TextBlock>의 레이아웃 슬롯은 <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> 메서드를 통해 <xref:System.Windows.Shapes.Path>로 변환됩니다.  이 기법은 요소의 경계 상자를 표시하는 데 유용합니다.  
  
 [!code-csharp[LayoutInformation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml.cs#2)]
 [!code-vb[LayoutInformation#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LayoutInformation/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="LayoutSystem_Overview"></a>   
## 레이아웃 시스템  
 가장 간단한 레이아웃은 요소의 크기 조정, 배치 및 그리기를 수행하는 재귀 시스템입니다.  다시 말해서 레이아웃이라는 용어는 <xref:System.Windows.Controls.Panel> 요소의 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션에 속한 멤버를 측정하고 정렬하는 프로세스를 말합니다.  레이아웃은 집약적인 프로세스입니다.  <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션이 클수록 수행되는 계산 수도 많아집니다.  컬렉션을 소유하는 <xref:System.Windows.Controls.Panel> 요소가 정의하는 레이아웃 동작을 기준으로 보다 복잡한 레이아웃 계산도 수행할 수 있습니다.  <xref:System.Windows.Controls.Canvas>와 같이 상대적으로 간단한 <xref:System.Windows.Controls.Panel>은 <xref:System.Windows.Controls.Grid>와 같은 복잡한 <xref:System.Windows.Controls.Panel>보다 훨씬 뛰어난 성능을 제공합니다.  
  
 자식 <xref:System.Windows.UIElement>가 해당 위치를 변경할 때마다 레이아웃 시스템에 의한 새 처리 단계가 트리거될 수 있습니다.  따라서 레이아웃 시스템을 호출할 수 있는 이벤트를 이해하는 것이 중요합니다. 불필요한 호출로 인해 응용 프로그램 성능이 저하될 수 있기 때문입니다.  아래에서는 레이아웃 시스템이 호출될 때 발생하는 프로세스에 대해 설명합니다.  
  
1.  자식 <xref:System.Windows.UIElement>는 먼저 핵심 속성이 측정되도록 하여 레이아웃 프로세스를 시작합니다.  
  
2.  <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A> 및 <xref:System.Windows.FrameworkElement.Margin%2A>과 같이 <xref:System.Windows.FrameworkElement>에 정의된 크기 조정 속성이 평가됩니다.  
  
3.  <xref:System.Windows.Controls.Dock> 방향 또는 스택 <xref:System.Windows.Controls.StackPanel.Orientation%2A>과 같은 <xref:System.Windows.Controls.Panel> 고유 논리가 적용됩니다.  
  
4.  모든 자식 항목을 측정한 후에 내용이 정렬됩니다.  
  
5.  <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션이 화면에 그려집니다.  
  
6.  <xref:System.Windows.Controls.Panel.Children%2A>이 화면에 더 추가되거나 <xref:System.Windows.FrameworkElement.LayoutTransform%2A>이 적용되거나 <xref:System.Windows.UIElement.UpdateLayout%2A> 메서드가 호출되면 프로세스가 다시 호출됩니다.  
  
 이 프로세스 및 이 프로세스가 호출되는 방법은 이후 단원에서 자세히 정의되어 있습니다.  
  
<a name="LayoutSystem_Measure_Arrange"></a>   
## 자식 항목 측정 및 정렬  
 레이아웃 시스템은 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션의 각 멤버에 대해 두 처리 단계인 측정 처리 단계 및 정렬 처리 단계를 수행합니다.  각 자식 <xref:System.Windows.Controls.Panel>은 고유한 특정 레이아웃 동작을 제공하기 위해 고유의 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 및 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드를 제공합니다.  
  
 측정 처리 단계에서 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션의 각 멤버가 평가됩니다.  이 프로세스는 <xref:System.Windows.UIElement.Measure%2A> 메서드를 호출하면서 시작됩니다.  이 메서드는 부모 <xref:System.Windows.Controls.Panel> 요소의 구현 내에서 호출되며 레이아웃이 발생하도록 명시적으로 호출될 필요는 없습니다.  
  
 첫째, <xref:System.Windows.UIElement.Clip%2A> 및 <xref:System.Windows.UIElement.Visibility%2A> 같은 <xref:System.Windows.UIElement>의 기본 크기 속성이 평가됩니다.  이때 `constraintSize`라는 값이 생성되어 <xref:System.Windows.FrameworkElement.MeasureCore%2A>로 전달됩니다.  
  
 둘째, <xref:System.Windows.FrameworkElement>에 정의된 프레임워크 속성이 처리되어 `constraintSize`의 값에 영향을 줍니다.  이 속성은 일반적으로 <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> 및 <xref:System.Windows.FrameworkElement.Style%2A> 같은 내부 <xref:System.Windows.UIElement>의 크기 조정 특성을 설명합니다.  이러한 각 속성은 요소를 표시하는 데 필요한 공간을 변경할 수 있습니다.  그런 다음 `constraintSize`를 매개 변수로 사용하여 <xref:System.Windows.FrameworkElement.MeasureOverride%2A>를 호출합니다.  
  
> [!NOTE]
>  <xref:System.Windows.FrameworkElement.Height%2A> 속성과 <xref:System.Windows.FrameworkElement.Width%2A> 속성 사이에 그리고 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 속성과 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 속성 사이에 차이점이 있습니다.  예를 들어 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 속성은 다른 높이 입력 및 레이아웃 시스템에 따라 계산된 값입니다.  이 값은 실제 렌더링 패스에 따라 레이아웃 시스템 자체적으로 설정되므로 입력 변경의 기준인 <xref:System.Windows.FrameworkElement.Height%2A> 같은 속성의 설정 값 뒤에 약간 지연될 수 있습니다.  
>   
>  <xref:System.Windows.FrameworkElement.ActualHeight%2A>는 계산된 값이므로 레이아웃 시스템에서 수행되는 다양한 작업의 결과로 여러 차례 또는 점증적으로 변경될 수 있습니다.  레이아웃 시스템은 자식 요소에 필요한 측정 공간, 부모 요소에 의한 제약 조건 등을 계산할 수도 있습니다.  
  
 측정 처리 단계의 궁극적인 목표는 <xref:System.Windows.FrameworkElement.MeasureCore%2A> 호출 동안 발생하는 <xref:System.Windows.UIElement.DesiredSize%2A>를 자식 항목이 확인할 수 있도록 하는 것입니다.  <xref:System.Windows.UIElement.DesiredSize%2A> 값은 내용 정렬 처리 단계에서 사용할 수 있도록 <xref:System.Windows.UIElement.Measure%2A>에 의해 저장됩니다.  
  
 정렬 처리 단계는 <xref:System.Windows.UIElement.Arrange%2A> 메서드에 대한 호출로 시작됩니다.  정렬 처리 단계 동안 부모 <xref:System.Windows.Controls.Panel> 요소는 자식 항목의 경계를 나타내는 직사각형을 생성합니다.  이 값은 처리를 위해 <xref:System.Windows.FrameworkElement.ArrangeCore%2A> 메서드에 전달됩니다.  
  
 <xref:System.Windows.FrameworkElement.ArrangeCore%2A> 메서드는 자식의 <xref:System.Windows.UIElement.DesiredSize%2A>와 렌더링된 요소 크기에 영향을 줄 수 있는 추가 여백을 평가합니다.  <xref:System.Windows.FrameworkElement.ArrangeCore%2A>는 <xref:System.Windows.Controls.Panel>의 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드에 매개 변수로 전달되는 `arrangeSize`를 생성합니다.  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>는 자식의 `finalSize`를 생성합니다.  마지막으로 <xref:System.Windows.FrameworkElement.ArrangeCore%2A> 메서드는 여백, 맞춤 등과 같은 오프셋 속성을 최종적으로 평가하고 자식을 레이아웃 슬롯 내에 배치합니다.  자식 항목은 할당된 공간을 모두 채울 필요가 없으며 실제로도 모두 채우는 경우가 드뭅니다.  그런 다음 컨트롤이 부모 <xref:System.Windows.Controls.Panel>에 반환되고 레이아웃 프로세스가 완료됩니다.  
  
<a name="LayoutSystem_PanelsCustom"></a>   
## 패널 요소 및 사용자 지정 레이아웃 동작  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 <xref:System.Windows.Controls.Panel>에서 파생되는 요소 그룹을 포함합니다.  이러한 <xref:System.Windows.Controls.Panel> 요소는 많은 복잡한 레이아웃을 가능하게 합니다.  예를 들어 요소 스택은 <xref:System.Windows.Controls.StackPanel> 요소를 사용하여 쉽게 달성할 수 있는 반면 보다 복잡하고 흐름이 자유로운 레이아웃은 <xref:System.Windows.Controls.Canvas>를 사용하여 달성할 수 있습니다.  
  
 다음 표에서는 사용 가능한 레이아웃 <xref:System.Windows.Controls.Panel> 요소를 요약하여 설명합니다.  
  
|패널 이름|설명|  
|-----------|--------|  
|<xref:System.Windows.Controls.Canvas>|<xref:System.Windows.Controls.Canvas> 영역에 상대적인 좌표를 사용하여 자식 요소를 명시적으로 배치할 수 있는 영역을 정의합니다.|  
|<xref:System.Windows.Controls.DockPanel>|자식 요소를 서로에 상대적으로 가로나 세로로 정렬할 수 있는 영역을 정의합니다.|  
|<xref:System.Windows.Controls.Grid>|열과 행으로 구성되는 유연한 표 영역을 정의합니다.|  
|<xref:System.Windows.Controls.StackPanel>|자식 요소를 가로 또는 세로 방향으로 지정할 수 있는 단일 선에 따라 정렬합니다.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|자식 데이터 컬렉션을 가상화하는 <xref:System.Windows.Controls.Panel> 요소를 위한 프레임워크를 제공합니다.  추상 클래스입니다.|  
|<xref:System.Windows.Controls.WrapPanel>|자식 요소를 왼쪽에서 오른쪽으로 순차적으로 배치하고, 포함하는 상자의 가장자리에서 내용을 다음 줄로 바꿉니다.  이후에는 <xref:System.Windows.Controls.WrapPanel.Orientation%2A> 속성 값에 따라 순서가 위쪽에서 아래쪽으로 또는 오른쪽에서 왼쪽으로 순차적으로 지정됩니다.|  
  
 미리 정의된 <xref:System.Windows.Controls.Panel> 요소를 사용하여 달성할 수 없는 레이아웃이 필요한 응용 프로그램의 경우에는 <xref:System.Windows.Controls.Panel>로부터 상속하고 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 및 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드를 재정의함으로써 사용자 지정 레이아웃 동작을 완성할 수 있습니다.  예제를 보려면 [Custom Radial Panel 샘플](http://go.microsoft.com/fwlink/?LinkID=159982)을 참조하십시오.  
  
<a name="LayoutSystem_Performance"></a>   
## 레이아웃 성능 고려 사항  
 레이아웃은 재귀적인 프로세스입니다.  <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션에 있는 각 자식 요소는 레이아웃 시스템이 호출될 때마다 처리됩니다.  따라서 필요하지 않을 때 레이아웃 시스템을 트리거하는 것을 피해야 합니다.  다음은 보다 뛰어난 성능을 얻는 데 도움이 되는 고려 사항입니다.  
  
-   레이아웃 시스템의 재귀적 업데이트를 강제하는 속성 값 변경에 유의합니다.  
  
     레이아웃 시스템을 초기화하는 값을 가진 종속성 속성은 공용 플래그로 표시됩니다.  <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> 및 <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>는 어떤 속성 값 변경이 레이아웃 시스템의 재귀적 업데이트를 강제하는지에 대한 유용한 단서를 제공합니다.  일반적으로 요소의 경계 상자 크기에 영향을 줄 수 있는 속성은 <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> 플래그를 true로 설정해야 합니다.  자세한 내용은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하십시오.  
  
-   가능하면 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 대신 <xref:System.Windows.UIElement.RenderTransform%2A>을 사용합니다.  
  
     <xref:System.Windows.FrameworkElement.LayoutTransform%2A>은 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]의 내용에 영향을 주는 매우 유용한 방법이 될 수 있습니다.  그러나 변환 효과가 다른 요소의 위치에 영향을 줄 필요가 없는 경우에는 <xref:System.Windows.UIElement.RenderTransform%2A>을 대신 사용하는 것이 좋습니다. <xref:System.Windows.UIElement.RenderTransform%2A>은 레이아웃 시스템을 호출하지 않기 때문입니다.  <xref:System.Windows.FrameworkElement.LayoutTransform%2A>은 변환을 적용하고 재귀적 레이아웃 업데이트를 강제하여 영향을 받는 요소의 새 위치를 계산합니다.  
  
-   <xref:System.Windows.UIElement.UpdateLayout%2A>에 대한 불필요한 호출을 피하십시오.  
  
     <xref:System.Windows.UIElement.UpdateLayout%2A> 메서드는 재귀적 레이아웃 업데이트를 강제하며 불필요한 경우가 많습니다.  전체 업데이트가 필요하다고 확신하는 경우를 제외하고는 레이아웃 시스템에서 이 메서드를 대신 호출하도록 하십시오.  
  
-   큰 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션으로 작업할 때는 일반 <xref:System.Windows.Controls.StackPanel> 대신 <xref:System.Windows.Controls.VirtualizingStackPanel>을 사용해 보십시오.  
  
     자식 컬렉션을 가상화함으로써 <xref:System.Windows.Controls.VirtualizingStackPanel>은 현재 부모의 [ViewPort](GTMT) 내에 있는 메모리의 개체만 유지합니다.  따라서 대부분의 시나리오에서 성능이 크게 향상됩니다.  
  
<a name="LayoutSystem_LayoutRounding"></a>   
## 하위 픽셀 렌더링 및 레이아웃 반올림  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 시스템에서는 해상도와 장치의 영향을 받지 않기 위해 장치 독립적 단위를 사용합니다.  각각의 장치 독립적 픽셀은 시스템의 [!INCLUDE[TLA#tla_dpi](../../../../includes/tlasharptla-dpi-md.md)] 설정에 맞게 자동으로 크기가 조정됩니다.  따라서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 다양한 [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] 설정에 적합한 배율 조정이 가능하며 자동으로 [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)]를 인식할 수 있습니다.  
  
 그러나 이러한 [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] 독립성은 앤티 앨리어싱으로 인해 불규칙한 가장자리 렌더링을 발생시킬 수 있습니다.  대개 흐리거나 반투명한 가장자리로 표시되는 이러한 아티팩트는 가장자리의 위치가 장치 픽셀 사이가 아닌 장치 픽셀 가운데에 있을 때 발생할 수 있습니다.  레이아웃 시스템에서는 레이아웃 반올림을 사용하여 조정할 수 있는 방법을 제공합니다.  레이아웃 반올림은 레이아웃 렌더링 처리 단계의 모든 비정수 픽셀 값을 레이아웃 시스템에서 반올림하는 것입니다.  
  
 레이아웃 반올림은 기본적으로 사용되지 않습니다.  레이아웃 반올림을 사용하려면 <xref:System.Windows.FrameworkElement>에서 <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> 속성을 `true`로 설정합니다.  종속성 속성이므로 값이 시각적 트리의 모든 자식에 전파됩니다.  전체 UI에 대해 레이아웃 반올림을 사용하려면 루트 컨테이너에서 <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>을 `true`로 설정합니다.  예제를 보려면 <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>을 참조하십시오.  
  
<a name="LayoutSystem_whatsnext"></a>   
## 새로운 기능  
 요소의 측정 방법과 정렬 방법을 이해하는 것이 레이아웃을 이해하기 위한 첫 단계입니다.  사용 가능한 <xref:System.Windows.Controls.Panel> 요소에 대한 자세한 내용은 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)를 참조하십시오.  레이아웃에 영향을 줄 수 있는 다양한 배치 속성에 대한 자세한 내용은 [맞춤, 여백 및 안쪽 여백 개요](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)를 참조하십시오.  사용자 지정 <xref:System.Windows.Controls.Panel> 요소의 예제를 보려면 [Custom Radial Panel 샘플](http://go.microsoft.com/fwlink/?LinkID=159982)을 참조하십시오.  이 모든 것을 간단한 응용 프로그램 내에 구현할 준비가 되었으면 [연습: WPF 시작](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.UIElement>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [맞춤, 여백 및 안쪽 여백 개요](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)   
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)