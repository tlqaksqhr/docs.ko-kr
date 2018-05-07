---
title: 잉크 렌더링 사용자 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom-rendering ink
- ink [WPF], custom-rendering
- classes [WPF], InkCanvas
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
ms.openlocfilehash: 2c627f757c1eccc37f57aea6880ffc8a362e5ddb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="custom-rendering-ink"></a>잉크 렌더링 사용자 지정
<xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> 선의 속성을 사용 하면 크기, 색, 모양, 같은 선의 모양을 지정할 수 있지만 기능 이외의 모양을 사용자 지정 하려는 경우가 있을 수 있습니다 <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> 허용 합니다. 에어브러시, 오일 페인트 및 다른 많은 효과가 있는 모양을 렌더링하여 잉크 모양을 사용자 지정하려는 경우도 있을 수 있습니다. (WPF (Windows Presentation Foundation)를 사용 하면 사용자 지정 하는 사용자 지정을 구현 하 여 잉크를 렌더링 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 및 <xref:System.Windows.Ink.Stroke> 개체입니다.  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
-   [아키텍처](#Architecture)  
  
-   [동적 렌더러 구현](#ImplementingADynamicRenderer)  
  
-   [사용자 지정 스트로크 구현](#ImplementingCustomStrokes)  
  
-   [사용자 지정 InkCanvas 구현](#ImplementingACustomInkCanvas)  
  
-   [결론](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>아키텍처  
 잉크 렌더링은 두 번 발생합니다. 사용자가 잉크 입력 표면에 잉크를 쓸 때 한 번 발생하고 잉크 지원 표면에 스트로크가 추가된 후에 다시 한 번 발생합니다. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 사용자가 디지타이저에서 태블릿 펜 잉크를 렌더링 및 <xref:System.Windows.Ink.Stroke> 요소에 추가 되 면 자체를 렌더링 합니다.  
  
 동적으로 잉크를 렌더링하는 경우 세 가지 클래스를 구현해야 합니다.  
  
1.  **DynamicRenderer**:에서 파생 되는 클래스를 구현 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>합니다. 이 클래스는 특수화 된 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 를 그릴 때 스트로크를 렌더링 합니다. <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 므로 잉크 표면에 잉크를 응용 프로그램 사용자 인터페이스 (UI) 스레드가 차단 되는 경우에 수집할 수 나타납니다 별도 스레드에서 렌더링을 수행 합니다. 스레딩 모델에 대한 자세한 내용은 [잉크 스레딩 모델](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md)을 참조하세요. 스트로크를 동적으로 렌더링을 사용자 지정 하려면 재정의 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> 메서드.  
  
2.  **스트로크**:에서 파생 되는 클래스를 구현 <xref:System.Windows.Ink.Stroke>합니다. 이 클래스는 정적으로 렌더링 된 <xref:System.Windows.Input.StylusPoint> 변환 된 후의 데이터는 <xref:System.Windows.Ink.Stroke> 개체입니다. 재정의 <xref:System.Windows.Ink.Stroke.DrawCore%2A> 획 해당 정적으로 렌더링 되도록 메서드는 동적 렌더링와 일치 합니다.  
  
3.  **InkCanvas:** 에서 파생 되는 클래스를 구현 <xref:System.Windows.Controls.InkCanvas>합니다. 사용자 지정 된 할당 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 에 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 속성입니다. 재정의 <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> 메서드를 사용자 지정 선을 추가 하 고는 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 속성입니다. 이를 통해 잉크 모양이 일관되게 유지됩니다.  
  
<a name="ImplementingADynamicRenderer"></a>   
## <a name="implementing-a-dynamic-renderer"></a>동적 렌더러 구현  
 하지만 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 클래스는의 척도로 활발 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 전문적인 렌더링을 수행 하려면,에서 파생 되는 사용자 지정 된 동적 렌더러를 만들어야 합니다는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 재정의 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> 메서드.  
  
 다음 예제에서는 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 선형 그라데이션 브러시 효과 사용 하 여 잉크를 그립니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>   
## <a name="implementing-custom-strokes"></a>사용자 지정 스트로크 구현  
 <xref:System.Windows.Ink.Stroke>에서 파생되는 클래스를 구현합니다. 이 클래스는 렌더링 <xref:System.Windows.Input.StylusPoint> 변환 된 후의 데이터는 <xref:System.Windows.Ink.Stroke> 개체입니다. 재정의 <xref:System.Windows.Ink.Stroke.DrawCore%2A> 실제 그리기를 수행 하는 클래스입니다.  
  
 Stroke 클래스를 사용 하 여 사용자 지정 데이터를 저장할 수도 수는 <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> 메서드. 이 데이터는 스트로크 데이터와 함께 저장되어 유지됩니다.  
  
 <xref:System.Windows.Ink.Stroke> 클래스 적중 테스트를 수행할 수도 있습니다. 고유의 적중 알고리즘을 재정의 하 여 테스트를 구현할 수도 있습니다는 <xref:System.Windows.Ink.Stroke.HitTest%2A> 현재 클래스에 메서드.  
  
 다음 C# 코드에서는 사용자 지정 <xref:System.Windows.Ink.Stroke> 렌더링 하는 클래스 <xref:System.Windows.Input.StylusPoint> 획 3 차원으로 데이터입니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>   
## <a name="implementing-a-custom-inkcanvas"></a>사용자 지정 InkCanvas 구현  
 사용자 지정을 사용 하는 가장 쉬운 방법은 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 에서 파생 되는 클래스를 구현 하는 선 및 <xref:System.Windows.Controls.InkCanvas> 이러한 클래스를 사용 하 여 합니다. <xref:System.Windows.Controls.InkCanvas> 에 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 획 사용자 그릴 때 렌더링 되는 방식을 지정 하는 속성입니다.  
  
 사용자 지정 선에서 렌더링 되는 <xref:System.Windows.Controls.InkCanvas> 에서 다음을 수행 합니다.  
  
-   파생 되는 클래스를 만듭니다는 <xref:System.Windows.Controls.InkCanvas>합니다.  
  
-   사용자 지정 할당 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 에 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType> 속성입니다.  
  
-   <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> 메서드를 재정의합니다. 이 메서드에서 InkCanvas에 추가된 원래 스트로크를 제거합니다. 그런 다음 사용자 지정 스트로크를 만들고에 추가 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 속성과 기본 클래스를 새 호출 <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs> 사용자 지정 스트로크를 포함 하 합니다.  
  
 다음 C# 코드에서는 사용자 지정 <xref:System.Windows.Controls.InkCanvas> 사용자 지정을 사용 하는 클래스 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 하 고 사용자 지정 스트로크를 수집 합니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 <xref:System.Windows.Controls.InkCanvas> 둘 이상의 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>합니다. 여러 개 추가할 수 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 개체는 <xref:System.Windows.Controls.InkCanvas> 에 추가 하 여는 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성입니다.  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>결론  
 사용자 고유의 파생 하 여 잉크의 모양을 사용자 지정할 수 있습니다 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, <xref:System.Windows.Ink.Stroke>, 및 <xref:System.Windows.Controls.InkCanvas> 클래스입니다. 이와 함께 이러한 클래스는 사용자가 스트로크를 그릴 때와 스트로크가 수집된 후의 모양이 일관되도록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [고급 잉크 처리](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)
