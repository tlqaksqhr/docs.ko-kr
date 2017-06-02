---
title: "시각적 계층에서 적중 테스트 | Microsoft Docs"
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
  - "적중 테스트 기능"
  - "시각적 계층, 적중 테스트 기능"
ms.assetid: b1a64b61-14be-4d75-b89a-5c67bebb2c7b
caps.latest.revision: 42
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 41
---
# 시각적 계층에서 적중 테스트
이 항목에서는 시각적 계층에서 제공하는 적중 테스트 기능에 대해 간략하게 설명합니다.  적중 테스트를 사용하면 기하 도형 또는 점의 값이 <xref:System.Windows.Media.Visual>의 렌더링된 콘텐츠 내에 있는지 확인할 수 있습니다. 이 기능은 여러 개체를 선택하는 선택 영역과 같은 사용자 인터페이스 동작을 구현할 때 유용합니다.  
  
   
  
<a name="hit_testing_scenarios"></a>   
## 적중 테스트 시나리오  
 <xref:System.Windows.UIElement> 클래스는 지정한 좌표 값을 사용하여 요소에 대해 적중 테스트를 수행할 수 있는 <xref:System.Windows.UIElement.InputHitTest%2A> 메서드를 제공합니다.  대부분의 경우 <xref:System.Windows.UIElement.InputHitTest%2A> 메서드를 통해 요소에 대한 적중 테스트를 구현할 수 있지만  다음과 같이 시각적 계층에서 적중 테스트를 구현해야 하는 경우도 있습니다.  
  
-   <xref:System.Windows.UIElement>가 아닌 개체에 대해 적중 테스트를 수행하는 경우. <xref:System.Windows.Media.DrawingVisual> 또는 그래픽 개체와 같이 <xref:System.Windows.UIElement>가 아닌 개체에 대해 적중 테스트를 수행하는 경우가 여기에 해당합니다.  
  
-   기하 도형을 사용하여 적중 테스트를 수행하는 경우. 점의 좌표 값이 아니라 기하 도형 개체를 사용하여 적중 테스트를 수행해야 하는 경우가 여기에 해당합니다.  
  
-   여러 개체에 대해 적중 테스트를 수행하는 경우. 서로 겹쳐진 개체와 같이 여러 개체에 대해 적중 테스트를 수행해야 하는 경우가 여기에 해당합니다.  이때 첫 번째 요소뿐만 아니라 기하 도형이나 점을 교차하는 모든 시각적 요소에 대해 결과를 얻을 수 있습니다.  
  
-   <xref:System.Windows.UIElement> 적중 테스트 정책을 무시하는 경우. 요소가 비활성화되었는지, 보이지 않게 설정되었는지 등의 요인을 고려하는 <xref:System.Windows.UIElement> 적중 테스트 정책을 무시해야 하는 경우가 여기에 해당합니다.  
  
> [!NOTE]
>  시각적 계층에서의 적중 테스트를 보여 주는 전체 코드 샘플은 [Hit Test Using DrawingVisuals 샘플](http://go.microsoft.com/fwlink/?LinkID=159994) 및 [Hit Test with Win32 Interoperation 샘플](http://go.microsoft.com/fwlink/?LinkID=159995)을 참조하십시오.  
  
<a name="hit_testing_support"></a>   
## 적중 테스트 지원  
 <xref:System.Windows.Media.VisualTreeHelper> 클래스의 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드를 사용하여 기하 도형 또는 점 좌표 값이 컨트롤 또는 그래픽 요소와 같은 지정된 개체의 렌더링된 콘텐츠 내에 있는지 여부를 확인할 수 있습니다.  예를 들어 적중 테스트를 사용하면 개체의 경계 사각형 내에서 클릭한 마우스 인스턴스가 원 기하 도형 내에 포함되는지 여부를 확인할 수 있습니다.  또한 적중 테스트의 기본 구현을 재정의하여 고유한 사용자 지정 적중 테스트 계산을 수행할 수도 있습니다.  
  
 다음 그림에서는 사각형이 아닌 개체의 영역과 해당 경계 사각형 사이의 관계를 보여 줍니다.  
  
 ![유효한 적정 테스트 영역의 다이어그램](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-visuals-hittest-1.png "wcpsdk\_mmgraphics\_visuals\_hittest\_1")  
올바른 적중 테스트 영역을 보여 주는 다이어그램  
  
<a name="hit_testing_and_z-order"></a>   
## 적중 테스트와 Z 순서  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 시각적 계층에서는 맨 위에 있는 개체뿐만 아니라 점이나 기하 도형 아래의 모든 개체에 대해서도 적중 테스트를 수행할 수 있습니다.  적중 테스트 결과는 [Z 순서](GTMT)로 반환됩니다.  그러나 적중 테스트할 [시각적 트리](GTMT)의 대상 영역은 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드에 매개 변수로 전달하는 시각적 개체에 따라 결정됩니다.  시각적 트리 전체를 적중 테스트하거나 그 중 일부만 적중 테스트할 수 있습니다.  
  
 다음 그림에서 원 개체는 사각형 개체와 삼각형 개체보다 위에 있습니다.  [Z 순서](GTMT) 값이 맨 위인 시각적 개체만 적중 테스트하려면 첫 번째 항목 이후에 <xref:System.Windows.Media.HitTestResultCallback>에서 <xref:System.Windows.Media.HitTestResultBehavior>을 반환하여 적중 테스트 순회를 중지하도록 시각적 개체에 대한 적중 테스트 열거형을 설정할 수 있습니다.  
  
 ![시각적 트리의 z 순서 다이어그램](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-visuals-hittest-2.png "wcpsdk\_mmgraphics\_visuals\_hittest\_2")  
시각적 트리의 Z 순서를 보여 주는 다이어그램  
  
 특정 점이나 기하 도형 아래의 모든 시각적 개체를 열거하려면 <xref:System.Windows.Media.HitTestResultCallback>에서 <xref:System.Windows.Media.HitTestResultBehavior>를 반환합니다.  이렇게 하면 전체가 가려진 개체를 포함하여 다른 개체 아래에 있는 모든 시각적 개체에 대해 적중 테스트를 수행할 수 있습니다.  자세한 내용은 "적중 테스트 결과 콜백 사용" 단원의 샘플 코드를 참조하십시오.  
  
> [!NOTE]
>  투명한 시각적 개체도 적중 테스트할 수 있습니다.  
  
<a name="using_default_hit_testing"></a>   
## 기본 적중 테스트 사용  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드를 사용하여 시각적 개체와 테스트할 점의 좌표 값을 지정하면 해당 점이 시각적 개체의 기하 도형 내에 있는지 여부를 확인할 수 있습니다.  시각적 개체 매개 변수는 시각적 트리에서 적중 테스트 검색의 시작 지점을 나타냅니다.  해당 기하 도형에 좌표가 있는 시각적 트리에 시각적 개체가 있으면 <xref:System.Windows.Media.HitTestResult> 개체의 <xref:System.Windows.Media.HitTestResult.VisualHit%2A> 속성에 이 시각적 개체가 설정됩니다.  그런 후 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드에서 <xref:System.Windows.Media.HitTestResult>가 반환됩니다.  적중 테스트하는 시각적 하위 트리에 점이 포함되어 있지 않으면 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>가 `null`을 반환합니다.  
  
> [!NOTE]
>  기본 적중 테스트는 [Z 순서](GTMT)에서 맨 위에 있는 개체를 항상 반환합니다.  일부 또는 전체가 가려진 시각적 개체를 포함하여 모든 시각적 개체를 확인하려면 적중 테스트 결과 콜백을 사용해야 합니다.  
  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드에 점 매개 변수로 전달하는 좌표 값은 적중 테스트하는 대상 시각적 개체의 좌표 공간을 기준으로 상대적으로 지정해야 합니다.  예를 들어 부모 좌표 공간에서 \(100, 100\) 지점에 중첩된 시각적 개체를 정의한 경우, \(0, 0\) 지점에 있는 자식 시각적 개체를 적중 테스트하면 부모 좌표 공간의 \(100, 100\) 지점에서 적중 테스트를 수행하는 것과 동일합니다.  
  
 다음 코드에서는 적중 테스트에 사용되는 이벤트를 캡처하는 <xref:System.Windows.UIElement> 개체에 대해 마우스 이벤트 처리기를 설정하는 방법을 보여 줍니다.  
  
 [!code-csharp[HitTestingOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[HitTestingOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#100)]  
  
### 시각적 트리가 적중 테스트에 미치는 영향  
 시각적 트리의 시작 지점은 개체의 적중 테스트를 열거할 때 반환되는 개체를 결정합니다.  적중 테스트할 개체가 여러 개인 경우, 시각적 트리에서 시작 지점으로 사용하는 시각적 개체는 테스트할 모든 개체의 공통 상위 항목이어야 합니다.  예를 들어 다음 다이어그램에서 단추 요소와 그리기 시각적 요소를 모두 적중 테스트하려면 시각적 트리에서 두 요소의 공통 상위 항목, 즉  이 경우에는 캔버스 요소를 시작 지점으로 설정해야 합니다.  
  
 ![시각적 트리 계층 구조의 다이어그램](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-visuals-overview-01.png "wcpsdk\_mmgraphics\_visuals\_overview\_01")  
시각적 트리 계층 구조를 보여 주는 다이어그램  
  
> [!NOTE]
>  <xref:System.Windows.UIElement.IsHitTestVisible%2A> 속성은 <xref:System.Windows.UIElement>에서 파생된 개체를 렌더링된 해당 콘텐츠의 일부에서 적중 테스트 결과로 반환할 수 있는지 여부를 선언하는 값을 가져오거나 설정합니다.  이렇게 하면 시각적 트리를 선택적으로 변경하여 적중 테스트와 관련된 시각적 개체를 확인할 수 있습니다.  
  
<a name="using_a_hit_test_result_callback"></a>   
## 적중 테스트 결과 콜백 사용  
 기하 도형에 지정한 좌표 값이 있는 시각적 트리의 모든 시각적 개체를 열거할 수 있습니다.  이렇게 하면 전체 또는 일부가 다른 시각적 개체에 가려진 시각적 개체를 포함하여 모든 시각적 개체를 확인할 수 있습니다.  시각적 트리에 있는 시각적 개체를 열거하려면 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드와 함께 적중 테스트 콜백 함수를 사용합니다.  지정한 좌표 값이 시각적 개체 내에 있으면 시스템에서 적중 테스트 콜백 함수를 호출합니다.  
  
 적중 테스트 결과를 열거하는 동안에는 시각적 트리를 수정하는 다른 작업을 수행하면 안 됩니다.  시각적 트리에 대해 작업이 수행되는 동안 시각적 트리에서 개체를 추가하거나 제거하면 예기치 않은 동작이 발생할 수 있습니다.  <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드가 반환된 후에는 시각적 트리를 안심하고 수정할 수 있습니다.  적중 테스트 결과를 열거하는 동안 값을 저장할 수 있도록 <xref:System.Collections.ArrayList> 같은 데이터 구조를 제공할 수도 있습니다.  
  
 [!code-csharp[HitTestingOverview#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[HitTestingOverview#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#101)]  
  
 적중 테스트 콜백 메서드는 시각적 트리에서 특정 시각적 개체에 대한 적중 테스트가 식별될 때 수행할 작업을 정의합니다.  작업을 수행한 후에는 다른 시각적 개체의 열거를 계속할지 여부를 결정하는 <xref:System.Windows.Media.HitTestResultBehavior> 값을 반환합니다.  
  
 [!code-csharp[HitTestingOverview#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[HitTestingOverview#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#102)]  
  
> [!NOTE]
>  적중된 시각적 개체의 열거 순서는 [Z 순서](GTMT)를 따릅니다.  즉, [Z 순서](GTMT)가 맨 위인 시각적 개체가 가장 먼저 열거되고  나머지 시각적 개체는 [Z 순서](GTMT)에 따라 내림차순으로 열거됩니다.  이 열거 순서는 시각적 요소의 렌더링 순서와 같습니다.  
  
 적중 테스트 콜백 함수에서 <xref:System.Windows.Media.HitTestResultBehavior>을 반환하여 시각적 개체의 열거를 언제든지 중지할 수 있습니다.  
  
 [!code-csharp[HitTestingOverview#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#103)]
 [!code-vb[HitTestingOverview#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#103)]  
  
<a name="using_a_hit_test_filter_callback"></a>   
## 적중 테스트 필터 콜백 사용  
 선택적 요소인 적중 테스트 필터를 사용하여 적중 테스트 결과에 전달되는 개체를 제한할 수 있습니다.  이 필터를 사용하면 적중 테스트 결과에서 처리하지 않을 시각적 트리의 특정 부분을 무시할 수 있습니다.  적중 테스트 필터를 구현하려면 적중 테스트 필터 콜백 함수를 정의한 후 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드를 호출할 때 매개 변수 값으로 전달합니다.  
  
 [!code-csharp[HitTestingOverview#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#104)]
 [!code-vb[HitTestingOverview#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#104)]  
  
 선택적 요소인 적중 테스트 필터 콜백 함수를 제공하지 않으려면 `null` 값을 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드의 매개 변수로 전달합니다.  
  
 [!code-csharp[HitTestingOverview#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#105)]
 [!code-vb[HitTestingOverview#105](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#105)]  
  
 ![적중 테스트 필터를 사용하여 시각적 트리 정리](../../../../docs/framework/wpf/graphics-multimedia/media/filteredvisualtree-01.png "FilteredVisualTree\_01")  
표시 트리 잘라내기  
  
 적중 테스트 필터 콜백 함수를 사용하면 지정한 좌표가 렌더링된 콘텐츠 내에 있는 모든 시각적 요소를 열거할 수 있습니다.  그러나 적중 테스트 결과 콜백 함수에서 처리하지 않으려는 시각적 트리의 특정 분기를 무시할 수도 있습니다.  적중 테스트 필터 콜백 함수의 반환 값에 따라 표시 개체의 열거형에서 수행해야 하는 작업 유형이 결정됩니다.  예를 들어 반환 값이 <xref:System.Windows.Media.HitTestFilterBehavior>이면 적중 테스트 결과 열거형에서 현재 시각적 개체와 해당 자식을 제거할 수 있습니다.  이렇게 하면 적중 테스트 결과 콜백 함수가 해당 열거형에서 이러한 개체를 볼 수 없습니다.  개체의 시각적 트리를 잘라내면 적중 테스트 결과 열거형을 수행하는 동안 처리해야 하는 작업 양이 감소합니다.  다음 코드 예제에서는 필터가 레이블과 해당 하위 항목을 생략하고 나머지 모든 항목에 대해 적중 테스트를 수행합니다.  
  
 [!code-csharp[HitTestingOverview#106](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#106)]
 [!code-vb[HitTestingOverview#106](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#106)]  
  
> [!NOTE]
>  적중 테스트 결과 콜백이 호출되지 않은 상태에서 적중 테스트 필터 콜백이 호출되는 경우도 있습니다.  
  
<a name="overriding_default_hit_testing"></a>   
## 기본 적중 테스트 재정의  
 <xref:System.Windows.Media.Visual.HitTestCore%2A> 메서드를 재정의하여 시각적 개체의 기본 적중 테스트 기능을 재정의할 수 있습니다.  이렇게 할 경우 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드를 호출하면 재정의된 <xref:System.Windows.Media.Visual.HitTestCore%2A> 구현이 호출됩니다.  재정의된 메서드는 좌표가 시각적 개체의 렌더링된 콘텐츠 밖에 있더라도 적중 테스트가 시각적 개체의 경계 사각형 내에만 포함되면 호출됩니다.  
  
 [!code-csharp[HitTestingOverview#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#107)]
 [!code-vb[HitTestingOverview#107](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#107)]  
  
 시각적 개체의 렌더링된 콘텐츠와 경계 사각형 모두에 대해 적중 테스트를 수행해야 하는 경우도 있는데,  재정의된 <xref:System.Windows.Media.Visual.HitTestCore%2A> 메서드의 `PointHitTestParameters` 매개 변수 값을 기본 메서드 <xref:System.Windows.Media.Visual.HitTestCore%2A>의 매개 변수로 사용하면 시각적 개체의 경계 사각형에 대한 적중 테스트를 기반으로 작업을 수행한 후 시각적 개체의 렌더링된 콘텐츠에 대해 두 번째 적중 테스트를 수행할 수 있습니다.  
  
 [!code-csharp[HitTestingOverview#108](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/Window1.xaml.cs#108)]
 [!code-vb[HitTestingOverview#108](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/window1.xaml.vb#108)]  
  
## 참고 항목  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>   
 <xref:System.Windows.Media.HitTestResult>   
 <xref:System.Windows.Media.HitTestResultCallback>   
 <xref:System.Windows.Media.HitTestFilterCallback>   
 <xref:System.Windows.UIElement.IsHitTestVisible%2A>   
 [Hit Test Using DrawingVisuals 샘플](http://go.microsoft.com/fwlink/?LinkID=159994)   
 [Hit Test with Win32 Interoperation 샘플](http://go.microsoft.com/fwlink/?LinkID=159995)   
 [시각적 요소의 기하 도형 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)   
 [Win32 호스트 컨테이너를 사용하여 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-a-win32-host-container.md)