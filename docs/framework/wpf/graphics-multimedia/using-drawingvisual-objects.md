---
title: DrawingVisual 개체 사용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual layer [WPF], DrawingVisual objects
- DrawingVisual objects in visual layer [WPF]
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
ms.openlocfilehash: e76ac22d4b8205576c8ed9ab67482c143a52fbd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="using-drawingvisual-objects"></a>DrawingVisual 개체 사용
이 항목에서는 사용 하는 방법에 대해 간략하게 <xref:System.Windows.Media.DrawingVisual> 개체에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시각적 계층입니다.  
  
<a name="drawingvisual_object"></a>   
## <a name="drawingvisual-object"></a>DrawingVisual 개체  
 <xref:System.Windows.Media.DrawingVisual> 은 간단한 그리기 도형, 이미지 또는 텍스트를 렌더링 하는 데 사용 되는 클래스입니다. 이 클래스는 성능을 향상시키는 레이아웃이나 이벤트 처리를 제공하지 않으므로 간단한 클래스로 간주됩니다. 이러한 이유 때문에 그리기는 배경 및 클립 아트에 적합합니다.  
  
<a name="drawingvisual_host_container"></a>   
## <a name="drawingvisual-host-container"></a>DrawingVisual 호스트 컨테이너  
 사용 하려면 <xref:System.Windows.Media.DrawingVisual> 개체를 개체에 대 한 호스트 컨테이너를 만들어야 합니다. 컨테이너 개체에서 파생 되어야 합니다는 <xref:System.Windows.FrameworkElement> 를 지 원하는 레이아웃 및 이벤트 처리를 제공 하는 클래스는 <xref:System.Windows.Media.DrawingVisual> 클래스입니다. 호스트 컨테이너 개체는 주 목적이 자식 개체를 포함하는 것이므로 표시 가능한 속성을 표시하지 않습니다. 그러나는 <xref:System.Windows.UIElement.Visibility%2A> 호스트 컨테이너의 속성으로 설정 되어 있어야 <xref:System.Windows.Visibility.Visible>, 그렇지 않으면 해당 자식 요소의 표시 되지 것입니다.  
  
 시각적 개체 참조를 저장 해야 하는 시각적 개체에 대 한 호스트 컨테이너 개체를 만들 때 한 <xref:System.Windows.Media.VisualCollection>합니다. 사용 하 여는 <xref:System.Windows.Media.VisualCollection.Add%2A> 메서드를 호스트 컨테이너에 시각적 개체를 추가 합니다. 다음 예제에서는 호스트 컨테이너 개체 만들어지고 세 시각적 개체에 추가 됩니다 해당 <xref:System.Windows.Media.VisualCollection>합니다.  
  
 [!code-csharp[DrawingVisualSample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
>  위의 코드 예제가 발췌된 전체 코드 샘플을 보려면 [DrawingVisuals를 사용하여 적중 테스트 샘플](http://go.microsoft.com/fwlink/?LinkID=159994)을 참조하세요.  
  
<a name="creating_drawingvisual_objects"></a>   
## <a name="creating-drawingvisual-objects"></a>DrawingVisual 개체 만들기  
 만들 때 한 <xref:System.Windows.Media.DrawingVisual> 개체를 그리기 내용이 없는 합니다. 개체의 검색 하 여 텍스트, 그래픽 또는 이미지 콘텐츠를 추가할 수 있습니다 <xref:System.Windows.Media.DrawingContext> 를 그리기 및 합니다. A <xref:System.Windows.Media.DrawingContext> 호출 하 여 반환 되는 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> 의 메서드는 <xref:System.Windows.Media.DrawingVisual> 개체입니다.  
  
 에 사각형을 그리는 <xref:System.Windows.Media.DrawingContext>를 사용 하 여는 <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> 의 메서드는 <xref:System.Windows.Media.DrawingContext> 개체입니다. 다른 형식의 콘텐츠를 그리기 위한 비슷한 메서드가 존재합니다. 로 드로잉 콘텐츠를 끝나면는 <xref:System.Windows.Media.DrawingContext>, 호출의 <xref:System.Windows.Media.DrawingContext.Close%2A> 을 닫는 메서드는 <xref:System.Windows.Media.DrawingContext> 콘텐츠를 유지 합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingVisual> 개체가 만들어지고에 사각형을 그립니다 해당 <xref:System.Windows.Media.DrawingContext>합니다.  
  
 [!code-csharp[DrawingVisualSample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## <a name="creating-overrides-for-frameworkelement-members"></a>FrameworkElement 멤버에 대한 재정의 만들기  
 호스트 컨테이너 개체는 시각적 개체의 컬렉션을 관리합니다. 호스트 컨테이너는 구현 된 파생에 대 한 멤버 재정의이 위해서는 <xref:System.Windows.FrameworkElement> 클래스입니다.  
  
 다음 목록에서는 재정의해야 하는 두 멤버에 대해 설명합니다.  
  
-   <xref:System.Windows.FrameworkElement.GetVisualChild%2A>: 자식 요소 컬렉션에서 지정된 된 인덱스의 자식을 반환합니다.  
  
-   <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A>:이 요소 내 시각적 자식 요소의 수를 가져옵니다.  
  
 다음 예제에서는 두에 대 한 재정의가 <xref:System.Windows.FrameworkElement> 멤버를 구현 합니다.  
  
 [!code-csharp[DrawingVisualSample#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## <a name="providing-hit-testing-support"></a>적중 테스트 지원 제공  
 하지만 컨테이너 개체에서 표시 되는 모든 속성을 표시 하지 않는 경우에 이벤트 처리를 제공할 수 있습니다-해당 <xref:System.Windows.UIElement.Visibility%2A> 속성으로 설정 되어 있어야 <xref:System.Windows.Visibility.Visible>합니다. 이 경우 왼쪽 마우스 단추 놓기와 같은 마우스 이벤트를 트래핑할 수 있는 호스트 컨테이너에 대한 이벤트 처리 루틴을 만들 수 있습니다. 이벤트 처리 루틴 적중 테스트를 호출 하 여 구현할 수는 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드. 메서드의 <xref:System.Windows.Media.HitTestResultCallback> 매개 변수는 적중 횟수 테스트의 결과 동작을 결정 하는 데 사용할 수 있는 사용자 정의 프로시저를 참조 합니다.  
  
 다음 예제에서는 호스트 컨테이너 개체 및 해당 자식에 대해 적중 테스트 지원이 구현됩니다.  
  
 [!code-csharp[DrawingVisualSample#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.DrawingVisual>  
 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>  
 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [시각적 계층에서 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
