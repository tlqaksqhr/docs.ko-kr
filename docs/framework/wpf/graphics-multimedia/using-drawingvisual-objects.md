---
title: "DrawingVisual 개체 사용 | Microsoft Docs"
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
  - "시각적 계층의 DrawingVisual 개체"
  - "시각적 계층, DrawingVisual 개체"
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# DrawingVisual 개체 사용
이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시각적 계층에서 <xref:System.Windows.Media.DrawingVisual> 개체를 사용하는 방법을 간략하게 설명합니다.  
  
 이 항목에는 다음 단원이 포함되어 있습니다.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [DrawingVisual 개체](#drawing_visual_object)  
  
-   [DrawingVisual 호스트 컨테이너](#drawingvisual_host_container)  
  
-   [DrawingVisual 개체 만들기](#creating_drawingvisual_objects)  
  
-   [FrameworkElement 멤버 재정의 만들기](#creating_overrides)  
  
-   [적중 테스트 지원](#providing_hit_testing_support)  
  
-   [관련 항목](#seeAlsoToggle)  
  
<a name="drawingvisual_object"></a>   
## DrawingVisual 개체  
 <xref:System.Windows.Media.DrawingVisual>은 도형, 이미지 또는 텍스트를 렌더링하는 데 사용되는 간단한 그리기 클래스입니다.  이 클래스는 성능을 향상시키는 레이아웃이나 이벤트 처리를 제공하지 않으므로 간단한 클래스로 간주됩니다.  이러한 이유 때문에 그리기는 배경 및 클립 아트에 적합합니다.  
  
<a name="drawingvisual_host_container"></a>   
## DrawingVisual 호스트 컨테이너  
 <xref:System.Windows.Media.DrawingVisual> 개체를 사용하려면 개체의 호스트 컨테이너를 만들어야 합니다.  호스트 컨테이너 개체는 <xref:System.Windows.Media.DrawingVisual> 클래스에서 지원하지 않는 레이아웃 및 이벤트 처리 기능을 지원하는 <xref:System.Windows.FrameworkElement> 클래스에서 파생되어야 합니다.  호스트 컨테이너 개체의 기본 목적은 자식 개체를 포함하는 것이기 때문에 이 개체는 아무 속성도 표시하지 않습니다.  그러나 호스트 컨테이너의 <xref:System.Windows.UIElement.Visibility%2A> 속성은 반드시 <xref:System.Windows.Visibility>로 설정되어야 합니다. 그렇지 않으면 자식 요소가 표시되지 않습니다.  
  
 시각적 개체의 호스트 컨테이너 개체를 만들 때 시각적 개체 참조는 <xref:System.Windows.Media.VisualCollection>에 저장해야 합니다.  <xref:System.Windows.Media.VisualCollection.Add%2A> 메서드를 사용하여 시각적 개체를 호스트 컨테이너에 추가할 수 있습니다.  다음 예제에서는 호스트 컨테이너 개체를 만들고 해당 <xref:System.Windows.Media.VisualCollection>에 시각적 개체 세 개를 추가합니다.  
  
 [!code-csharp[DrawingVisualSample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
>  앞의 코드 예제를 추출한 전체 코드 샘플을 보려면 [Hit Test Using DrawingVisuals 샘플](http://go.microsoft.com/fwlink/?LinkID=159994)을 참조하십시오.  
  
<a name="creating_drawingvisual_objects"></a>   
## DrawingVisual 개체 만들기  
 <xref:System.Windows.Media.DrawingVisual> 개체를 만드는 경우 기본적으로 그리기 내용이 없는 개체가 생성됩니다.  개체의 <xref:System.Windows.Media.DrawingContext>를 검색하고 여기에 그림을 그려서 텍스트, 그래픽 또는 이미지 콘텐츠를 추가할 수 있습니다.  <xref:System.Windows.Media.DrawingVisual> 개체의 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> 메서드를 호출하면 <xref:System.Windows.Media.DrawingContext>가 반환됩니다.  
  
 <xref:System.Windows.Media.DrawingContext>에 사각형을 그리려면 <xref:System.Windows.Media.DrawingContext> 개체의 <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> 메서드를 사용합니다.  다른 종류의 콘텐츠를 그릴 수 있는 이와 유사한 다른 메서드도 있습니다.  <xref:System.Windows.Media.DrawingContext>에 콘텐츠 그리기를 마쳤으면 <xref:System.Windows.Media.DrawingContext.Close%2A> 메서드를 호출하여 <xref:System.Windows.Media.DrawingContext>를 닫고 콘텐츠를 유지합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingVisual> 개체를 만들고 해당 <xref:System.Windows.Media.DrawingContext>에 사각형을 그립니다.  
  
 [!code-csharp[DrawingVisualSample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## FrameworkElement 멤버 재정의 만들기  
 호스트 컨테이너 개체는 시각적 개체 컬렉션을 관리합니다.  그러기 위해서는 호스트 컨테이너가 파생된 <xref:System.Windows.FrameworkElement> 클래스의 멤버 재정의를 구현해야 합니다.  
  
 다음 목록에서는 재정의해야 하는 두 가지 멤버를 설명합니다.  
  
-   <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: 자식 요소 컬렉션에서 지정한 인덱스에 있는 자식을 반환합니다.  
  
-   <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>: 이 요소에 포함된 시각적 자식 요소의 개수를 가져옵니다.  
  
 다음 예제에서는 두 가지 <xref:System.Windows.FrameworkElement> 멤버의 재정의를 구현합니다.  
  
 [!code-csharp[DrawingVisualSample#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## 적중 테스트 지원  
 호스트 컨테이너 개체는 아무런 속성도 표시하지 않는 경우에도 이벤트 처리 기능을 제공할 수 있습니다. 단, 호스트 컨테이너 개체의 <xref:System.Windows.UIElement.Visibility%2A> 속성은 <xref:System.Windows.Visibility>로 설정되어 있어야 합니다.  이를 통해 사용자는 왼쪽 마우스 단추 놓기와 같은 마우스 이벤트를 트래핑하는 이벤트 처리 루틴을 호스트 컨테이너에 만들 수 있습니다.  그런 후 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드를 호출하여 이 이벤트 처리 루틴을 통해 적중 테스트를 구현할 수 있습니다.  이 메서드의 <xref:System.Windows.Media.HitTestResultCallback> 매개 변수는 적중 테스트 결과에 따른 작업을 결정하는 데 사용할 수 있는 사용자 정의 프로시저를 참조합니다.  
  
 다음 예제에서는 호스트 컨테이너 개체와 해당 자식에 대해 적중 테스트 지원을 구현합니다.  
  
 [!code-csharp[DrawingVisualSample#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## 참고 항목  
 <xref:System.Windows.Media.DrawingVisual>   
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>   
 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [시각적 계층에서 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)