---
title: "성능 최적화: 개체 동작 | Microsoft Docs"
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
  - "종속성 속성, 성능"
  - "이벤트 처리기[WPF]"
  - "Freezable 개체, 성능"
  - "개체 성능 고려 사항"
  - "사용자 인터페이스 가상화"
ms.assetid: 73aa2f47-1d73-439a-be1f-78dc4ba2b5bd
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 성능 최적화: 개체 동작
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 개체의 기본 동작을 이해하면 기능과 성능 간의 균형을 적절하게 조정할 수 있습니다.  
  
   
  
<a name="Not_Removing_Event_Handlers"></a>   
## 개체에 대한 이벤트 처리기를 제거하지 않으면 개체가 활성 상태로 유지될 수 있음  
 개체가 해당 이벤트에 전달하는 대리자는 사실상 해당 개체에 대한 참조입니다.  따라서 이벤트 처리기는 예상보다 오래 개체의 활성 상태를 유지할 수 있습니다.  개체의 이벤트를 수신하도록 등록된 개체를 정리하는 경우에는 개체를 해제하기 전에 먼저 대리자를 제거해야 합니다.  불필요한 개체를 활성 상태로 유지하면 응용 프로그램의 메모리 사용이 늘어납니다.  이러한 현상은 특히 개체가 [논리 트리](GTMT) 또는 [시각적 트리](GTMT)의 루트인 경우 발생합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 소스와 수신기 간의 개체 수명 관계를 추적하기 어려운 경우에 유용할 수 있는 이벤트에 대한 약한 이벤트 수신기 패턴이 도입되었습니다.  일부 기존 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트에서 이 패턴을 사용하기도 합니다.  사용자 지정 이벤트를 사용하여 개체를 구현하는 경우 이 패턴이 유용할 수 있습니다.  자세한 내용은 [약한 이벤트 패턴](../../../../docs/framework/wpf/advanced/weak-event-patterns.md)을 참조하십시오.  
  
 지정된 프로세스의 메모리 사용에 대한 정보를 제공할 수 있는 CLR 프로파일러 및 작업 집합 뷰어와 같은 여러 가지 도구가 있습니다.  CLR 프로파일러에는 할당된 형식에 대한 히스토그램, 할당 및 호출 그래프, 다양한 세대의 가비지 수집을 보여 주는 시간 표시 막대\/이러한 수집 이후의 관리되는 힙에 대한 결과 상태, 메서드당 할당 및 어셈블리 로드를 보여 주는 호출 트리와 같은 할당 프로필에 대한 매우 유용한 여러 뷰가 포함되어 있습니다.  자세한 내용은 [.NET Framework Developer Center](http://go.microsoft.com/fwlink/?LinkId=117435)를 참조하십시오.  
  
<a name="DPs_and_Objects"></a>   
## 종속성 속성 및 개체  
 일반적으로 <xref:System.Windows.DependencyObject>의 [종속성 속성](GTMT)에 액세스하는 것이 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성에 액세스하는 것보다 느리지 않습니다.  속성 값을 설정하는 데 약간의 성능 오버헤드가 있지만 값을 가져오는 것은 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성에서 값을 가져오는 것만큼 빠릅니다.  이러한 약간의 성능 오버헤드는 [종속성 속성](GTMT)이 데이터 바인딩, 애니메이션, 상속 및 스타일 설정과 같은 강력한 기능을 지원한다는 사실로 상쇄됩니다.  자세한 내용은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하십시오.  
  
### DependencyProperty 최적화  
 응용 프로그램에서 [종속성 속성](GTMT)을 정의할 때는 매우 신중해야 합니다.  <xref:System.Windows.DependencyProperty>가 <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>와 같은 다른 메타데이터 옵션이 아닌 렌더링 형식 메타데이터 옵션에만 영향을 미치는 경우 해당 메타데이터를 겹쳐씀으로써 이를 표시해야 합니다.  속성 메타데이터를 겹쳐쓰거나 얻는 방법에 대한 자세한 내용은 [종속성 속성 메타데이터](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)를 참조하십시오.  
  
 모든 속성 변경이 실제로 측정, 정렬 및 렌더링에 영향을 미치는 것이 아니라면 속성 변경 처리기가 측정, 정렬 및 렌더링 처리 단계를 수동으로 무효화하도록 하는 것이 더 효율적일 수 있습니다.  예를 들어 값이 설정된 한계보다 클 경우에만 배경을 다시 렌더링하도록 결정하는 경우  속성 변경 처리기는 값이 설정된 한계를 초과하는 경우에 렌더링을 무효화하기만 합니다.  
  
### DependencyProperty를 상속 가능하게 만드는 경우 성능에 미치는 영향  
 기본적으로 등록된 [종속성 속성](GTMT)은 상속되지 않습니다.  그러나 어떤 속성이든 명시적으로 상속 가능하게 만들 수 있습니다.  이는 유용한 기능이지만 속성을 상속 가능한 속성으로 변환하면 속성 무효화를 위한 시간이 길어져서 성능에 영향을 미칩니다.  
  
### RegisterClassHandler의 신중한 사용  
 <xref:System.Windows.EventManager.RegisterClassHandler%2A>를 호출하여 인스턴스 상태를 저장하는 경우 모든 인스턴스에 처리기가 호출되어 성능 문제를 발생시킬 수 있음을 주의해야 합니다.  응용 프로그램에서 인스턴스 상태를 저장해야 할 필요가 있는 경우에만 <xref:System.Windows.EventManager.RegisterClassHandler%2A>를 사용하십시오.  
  
### 등록 시 DependencyProperty에 대한 기본값 설정  
 기본값이 필요한 <xref:System.Windows.DependencyProperty>를 만들 때 <xref:System.Windows.DependencyProperty>의 <xref:System.Windows.DependencyProperty.Register%2A> 메서드에 매개 변수로 전달되는 기본 메타데이터를 사용하여 값을 설정합니다.  생성자 또는 요소의 각 인스턴스에 속성 값을 설정하는 기술보다 이 기술을 사용하십시오.  
  
### Register를 사용하여 PropertyMetadata 값 설정  
 <xref:System.Windows.DependencyProperty>를 만들 때 <xref:System.Windows.DependencyProperty.Register%2A> 또는 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 메서드를 사용하여 <xref:System.Windows.PropertyMetadata>를 설정할 수 있습니다.  개체에 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>를 호출하기 위한 정적 생성자가 포함될 수 있지만 이는 적절한 솔루션이 아니며 성능에 영향을 미칩니다.  최적의 성능을 위해서는 <xref:System.Windows.DependencyProperty.Register%2A>를 호출할 때 <xref:System.Windows.PropertyMetadata>를 설정합니다.  
  
<a name="Freezable_Objects"></a>   
## Freezable 개체  
 <xref:System.Windows.Freezable>은 고정되지 않음과 고정이라는 두 가지 상태를 가지는 특수한 개체 형식입니다.  가능할 때마다 개체를 고정하면 응용 프로그램 성능이 향상되며 해당 작업 집합을 줄일 수 있습니다.  자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
 각 <xref:System.Windows.Freezable>에는 변경될 때마다 발생하는 <xref:System.Windows.Freezable.Changed> 이벤트가 있습니다.  그러나 변경 알림은 응용 프로그램 성능을 저하시킵니다.  
  
 다음 예제에서는 각각의 <xref:System.Windows.Shapes.Rectangle>에서 동일한 <xref:System.Windows.Media.Brush> 개체를 사용합니다.  
  
 [!code-csharp[Performance#PerformanceSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 기본적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 <xref:System.Windows.Shapes.Rectangle> 개체의 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성을 무효화하기 위해 <xref:System.Windows.Media.SolidColorBrush> 개체의 <xref:System.Windows.Freezable.Changed> 이벤트에 대한 이벤트 처리기를 제공합니다.  이 경우 <xref:System.Windows.Media.SolidColorBrush>가 해당 <xref:System.Windows.Freezable.Changed> 이벤트를 발생시켜야 할 때마다 각 <xref:System.Windows.Shapes.Rectangle>에 대한 콜백 함수를 호출해야 합니다. 이러한 콜백 함수 호출을 누적하면 성능에 심각한 영향을 미칩니다.  또한 이 시점에서 처리기를 추가 및 제거하면 응용 프로그램에서 이 작업을 위해 전체 목록을 이동해야 하므로 성능에 상당한 영향을 미칩니다.  응용 프로그램 시나리오에서 <xref:System.Windows.Media.SolidColorBrush>를 변경하지 않는 경우에는 <xref:System.Windows.Freezable.Changed> 이벤트 처리기를 유지 관리하는 비용이 불필요하게 소요됩니다.  
  
 <xref:System.Windows.Freezable>을 고정하면 변경 알림 유지 관리에 더 이상 리소스를 사용할 필요가 없으므로 성능을 향상시킬 수 있습니다.  아래 표에서는 <xref:System.Windows.Freezable.IsFrozen%2A> 속성을 `true`로 설정한 경우의 간단한 <xref:System.Windows.Media.SolidColorBrush> 크기를 이렇게 설정하지 않는 경우와 비교하여 보여 줍니다.  여기에서는 <xref:System.Windows.Shapes.Rectangle> 개체 10개의 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성에 브러시 하나를 적용한다고 가정합니다.  
  
|**State**|**크기**|  
|---------------|------------|  
|고정된 <xref:System.Windows.Media.SolidColorBrush>|212바이트|  
|고정되지 않은 <xref:System.Windows.Media.SolidColorBrush>|972바이트|  
  
 다음 코드 샘플에서는 이러한 개념을 보여 줍니다.  
  
 [!code-csharp[Performance#PerformanceSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### 고정되지 않은 Freezable에 대한 처리기를 변경하면 개체가 활성 상태로 유지될 수 있음  
 개체가 <xref:System.Windows.Freezable> 개체의 <xref:System.Windows.Freezable.Changed> 이벤트에 전달하는 대리자는 사실상 해당 개체에 대한 참조입니다.  따라서 <xref:System.Windows.Freezable.Changed> 이벤트 처리기는 예상보다 오래 개체의 활성 상태를 유지할 수 있습니다.  <xref:System.Windows.Freezable> 개체의 <xref:System.Windows.Freezable.Changed> 이벤트를 수신하도록 등록된 개체를 정리하는 경우에는 개체를 해제하기 전에 먼저 대리자를 제거해야 합니다.  
  
 또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 <xref:System.Windows.Freezable.Changed> 이벤트를 내부적으로 후크합니다.  예를 들어 값으로 <xref:System.Windows.Freezable>을 사용하는 모든 [종속성 속성](GTMT)은 자동으로 <xref:System.Windows.Freezable.Changed> 이벤트를 수신합니다.  <xref:System.Windows.Media.Brush>를 사용하는 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성은 이 개념을 보여 줍니다.  
  
 [!code-csharp[Performance#PerformanceSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 `myBrush`를 `myRectangle.Fill`에 할당할 때 <xref:System.Windows.Shapes.Rectangle> 개체를 다시 가리키는 대리자가 <xref:System.Windows.Media.SolidColorBrush> 개체의 <xref:System.Windows.Freezable.Changed> 이벤트에 추가됩니다.  이는 다음 코드에서 실제로 `myRect`를 가비지 수집에 적합하게 만들지 않음을 의미합니다.  
  
 [!code-csharp[Performance#PerformanceSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 이 경우 `myBrush`는 `myRectangle`을 계속해서 활성 상태로 유지하고 <xref:System.Windows.Freezable.Changed> 이벤트가 발생하면 해당 이벤트로 콜백합니다.  `myBrush`를 새 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성에 할당하면 단지 다른 이벤트 처리기가 `myBrush`에 추가됩니다.  
  
 세 가지 형식의 개체를 정리하기 위한 권장되는 방법은 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성에서 <xref:System.Windows.Media.Brush>를 제거하는 것입니다. 이렇게 제거한 후에는 <xref:System.Windows.Freezable.Changed> 이벤트 처리기가 제거됩니다.  
  
 [!code-csharp[Performance#PerformanceSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>   
## 사용자 인터페이스 가상화  
 또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 데이터 바인딩된 자식 콘텐츠를 자동으로 "가상화"하는 <xref:System.Windows.Controls.StackPanel> 요소의 변형을 제공합니다.  여기서 가상화라는 단어는 화면에 표시되는 항목에 따라 많은 수의 데이터 항목에서 개체의 하위 집합이 생성되는 기술을 가리킵니다.  특정 시점에 화면에 표시되는 것보다 많은 개수의 UI 요소를 생성하는 것은 메모리 및 프로세서 측면에서 비효율적입니다.  <xref:System.Windows.Controls.VirtualizingPanel>이 제공하는 기능을 통해 <xref:System.Windows.Controls.VirtualizingStackPanel>은 표시되는 항목을 계산하고, <xref:System.Windows.Controls.ListBox> 또는 <xref:System.Windows.Controls.ListView>와 같은 <xref:System.Windows.Controls.ItemsControl>의 <xref:System.Windows.Controls.ItemContainerGenerator>를 사용하여 표시되는 항목에 대한 요소만 만듭니다.  
  
 성능을 최적화하기 위해 이러한 항목에 대한 표시 개체는 화면에 보이는 경우에만 생성되거나 활성 상태를 유지합니다.  컨트롤의 가시 영역에 더 이상 존재하지 않는 표시 개체는 제거될 수 있습니다.  이는 데이터 개체가 로컬 컬렉션에 전혀 존재하지 않고 필요에 따라 스트리밍되는 데이터 가상화와 구별되어야 합니다.  
  
 아래 표에서는 5000개의 <xref:System.Windows.Controls.TextBlock> 요소를 <xref:System.Windows.Controls.StackPanel> 및 <xref:System.Windows.Controls.VirtualizingStackPanel>에 추가 및 렌더링하는 데 경과된 시간을 보여 줍니다.  이 시나리오에서 측정 값은 텍스트 문자열을 <xref:System.Windows.Controls.ItemsControl> 개체의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성에 연결하는 시간부터 패널 요소가 텍스트 문자열을 표시할 때까지의 시간을 나타냅니다.  
  
|**호스트 패널**|**렌더링 시간\(ms\)**|  
|----------------|----------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## 참고 항목  
 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [응용 프로그램 성능 계획](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [하드웨어 이용](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [기타 성능 권장 사항](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)