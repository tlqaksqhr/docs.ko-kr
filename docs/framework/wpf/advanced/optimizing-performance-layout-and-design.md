---
title: "성능 최적화: 레이아웃 및 디자인 | Microsoft Docs"
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
  - "디자인 고려 사항"
  - "레이아웃 단계"
  - "레이아웃, 성능 최적화"
ms.assetid: 005f4cda-a849-448b-916b-38d14d9a96fe
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 성능 최적화: 레이아웃 및 디자인
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램의 디자인 작업은 레이아웃 계산과 개체 참조의 유효성 검사 과정에서 불필요한 오버헤드를 초래하여 성능에 영향을 줄 수 있습니다.  또한 개체 생성 작업은 특히 런타임에 응용 프로그램의 성능 특성에 영향을 줄 수 있습니다.  
  
 이 항목에서는 이러한 영역에서 성능과 관련된 권장 사항을 제공합니다.  
  
## Layout  
 "레이아웃 과정"이라는 용어는 <xref:System.Windows.Controls.Panel> 파생 개체의 자식 컬렉션에 속한 멤버를 측정 및 정렬한 다음 화면에 그리는 프로세스를 말합니다.  레이아웃 과정은 많은 계산이 요구되는 프로세스이며 컬렉션의 자식 수가 많을수록 더 많은 수의 계산이 필요합니다.  예를 들어 컬렉션의 자식 <xref:System.Windows.UIElement> 개체가 해당 위치를 변경할 때마다 레이아웃 시스템에 의한 새 처리 과정이 트리거될 수 있습니다.  개체 특성과 레이아웃 동작 간의 긴밀한 관계로 인해 레이아웃 시스템을 호출하는 이벤트의 형식을 이해하는 것이 중요합니다.  레이아웃 과정의 불필요한 호출을 가능한 많이 줄이면 응용 프로그램의 성능이 향상됩니다.  
  
 레이아웃 시스템은 컬렉션의 각 자식 멤버에 대해 두 개의 과정인 측정 과정 및 정렬 과정을 수행합니다.  각 자식 개체는 고유한 특정 레이아웃 동작을 제공하기 위해 <xref:System.Windows.UIElement.Measure%2A> 및 <xref:System.Windows.UIElement.Arrange%2A> 메서드의 재정의된 고유한 구현을 제공합니다.  가장 간단한 레이아웃은 화면에서 크기 조정, 배치 및 그리기를 수행할 요소가 되는 재귀 시스템입니다.  
  
-   자식 <xref:System.Windows.UIElement> 개체는 먼저 핵심 속성이 측정되도록 하여 레이아웃 프로세스를 시작합니다.  
  
-   <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A> 및 <xref:System.Windows.FrameworkElement.Margin%2A>과 같은 크기와 관련된 개체의 <xref:System.Windows.FrameworkElement> 속성이 평가됩니다.  
  
-   <xref:System.Windows.Controls.DockPanel>의 <xref:System.Windows.Controls.DockPanel.Dock%2A> 속성 또는 <xref:System.Windows.Controls.StackPanel>의 <xref:System.Windows.Controls.StackPanel.Orientation%2A> 속성과 같은 <xref:System.Windows.Controls.Panel> 관련 논리가 적용됩니다.  
  
-   모든 자식 개체가 측정된 후 콘텐츠가 정렬 또는 배치됩니다.  
  
-   자식 개체의 컬렉션이 화면에 그려집니다.  
  
 다음 작업 중 하나가 발생할 경우 레이아웃 과정 프로세스가 다시 호출됩니다.  
  
-   자식 개체가 컬렉션에 추가될 경우  
  
-   <xref:System.Windows.FrameworkElement.LayoutTransform%2A>이 자식 개체에 적용될 경우  
  
-   <xref:System.Windows.UIElement.UpdateLayout%2A> 메서드가 자식 개체에 대해 호출될 경우  
  
-   측정 또는 정렬 과정에 영향을 주는 메타데이터로 표시된 [종속성 속성](GTMT)의 값에 변경이 발생할 경우  
  
### 가능한 가장 효율적인 패널 사용  
 레이아웃 프로세스의 복잡도는 사용하는 <xref:System.Windows.Controls.Panel> 파생 요소의 레이아웃 동작에 따라 직접적으로 좌우됩니다.  예를 들어 <xref:System.Windows.Controls.Grid> 또는 <xref:System.Windows.Controls.StackPanel> 컨트롤은 <xref:System.Windows.Controls.Canvas> 컨트롤보다 훨씬 많은 기능을 제공합니다.  기능이 많이 제공될수록 성능 비용이 증가합니다.  따라서 <xref:System.Windows.Controls.Grid> 컨트롤이 제공하는 기능이 필요하지 않은 경우 <xref:System.Windows.Controls.Canvas> 또는 사용자 지정 패널과 같은 더 적은 비용이 드는 대체 방법을 사용해야 합니다.  
  
 자세한 내용은 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)를 참조하십시오.  
  
### RenderTransform을 대체하는 대신 업데이트  
 <xref:System.Windows.Media.Transform>을 <xref:System.Windows.UIElement.RenderTransform%2A> 속성 값으로 대체하는 대신에 업데이트할 수 있습니다.  애니메이션과 관련된 시나리오가 특히 이러한 경우에 해당합니다.  기존 <xref:System.Windows.Media.Transform>을 업데이트하면 불필요한 레이아웃 계산이 시작되지 않습니다.  
  
### 하향식 트리 빌드  
 [논리 트리](GTMT)에서 노드가 추가 또는 제거될 경우 노드의 부모 및 모든 자식에서 속성 무효화가 발생합니다.  결과적으로 이미 유효성이 검사된 노드에서 불필요한 무효화의 비용을 방지하기 위해 항상 하향식 생성 패턴을 따라야 합니다.  다음 표에서는 각 수준에 단일 <xref:System.Windows.Controls.TextBlock> 및 <xref:System.Windows.Controls.DockPanel>이 있는 150개 수준 깊이의 트리를 하향식 및 상향식으로 빌드할 때의 실행 속도 차이를 보여 줍니다.  
  
|**동작**|**트리 빌드\(ms 단위\)**|**렌더링—트리 빌드 포함\(ms 단위\)**|  
|------------|------------------------|-------------------------------|  
|상향식|366|454|  
|하향식|11|96|  
  
 다음 코드 예제에서는 트리를 하향식으로 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[Performance#PerformanceSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet1)]
 [!code-vb[Performance#PerformanceSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet1)]  
  
 논리 트리에 대한 자세한 내용은 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)를 참조하십시오.  
  
## 참고 항목  
 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [응용 프로그램 성능 계획](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [하드웨어 이용](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [개체 동작](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [기타 성능 권장 사항](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)   
 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)