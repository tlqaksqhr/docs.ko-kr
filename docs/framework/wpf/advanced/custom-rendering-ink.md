---
title: "잉크 렌더링 사용자 지정 | Microsoft Docs"
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
  - "클래스, DynamicRenderer"
  - "클래스, InkCanvas"
  - "클래스, 스트로크"
  - "잉크 사용자 지정 렌더링"
  - "DynamicRenderer 클래스"
  - "잉크, 사용자 지정 렌더링"
  - "InkCanvas 클래스"
  - "Stroke 클래스"
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 잉크 렌더링 사용자 지정
스트로크의 <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> 속성을 사용하여 크기, 색, 형태 등 스트로크의 모양을 지정할 수 있습니다. 하지만 <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>로 가능한 것보다 더 많이 모양을 사용자 지정하려는 경우가 있을 수 있습니다.  에어 브러시, 유성 물감 등의 다른 많은 효과로 잉크를 렌더링하여 잉크 모양을 사용자 지정하려는 경우도 있을 수 있습니다.  [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]에서는 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 및 <xref:System.Windows.Ink.Stroke> 개체를 구현하여 잉크 렌더링을 사용자 지정할 수 있습니다.  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
-   [아키텍처](#Architecture)  
  
-   [DynamicRenderer 구현](#ImplementingADynamicRenderer)  
  
-   [Implementing a Custom Stroke](#ImplementingACustomStroke)  
  
-   [사용자 지정 InkCanvas 구현](#ImplementingACustomInkCanvas)  
  
-   [결론](#Conclusion)  
  
<a name="Architecture"></a>   
## 아키텍처  
 잉크 렌더링은 사용자가 잉크 표면에 잉크를 쓸 때 한 번 발생하고 잉크 지원 표면에 스트로크가 추가된 후에 다시 한 번 발생합니다.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>는 사용자가 디지타이저에서 태블릿 펜을 이동할 때 잉크를 렌더링하고 <xref:System.Windows.Ink.Stroke>는 요소에 추가된 후 자동으로 렌더링됩니다.  
  
 동적으로 잉크를 렌더링하는 경우 세 가지 클래스를 구현해야 합니다.  
  
1.  **DynamicRenderer**: <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>에서 파생되는 클래스를 구현합니다.  이 클래스는 스트로크를 그릴 때 이를 렌더링하는 특수 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>입니다.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>는 별도의 스레드에서 렌더링을 수행하므로 응용 프로그램 UI\(사용자 인터페이스\) 스레드가 차단된 경우에도 잉크 표면이 잉크를 수집할 수 있습니다.  스레딩 모델에 대한 자세한 내용은 [잉크 스레딩 모델](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md)을 참조하십시오.  스트로크를 동적으로 렌더링하도록 사용자 지정하려면 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> 메서드를 재정의합니다.  
  
2.  **Stroke**: <xref:System.Windows.Ink.Stroke>에서 파생되는 클래스를 구현합니다.  이 클래스는 <xref:System.Windows.Input.StylusPoint> 데이터가 <xref:System.Windows.Ink.Stroke> 개체로 변환된 후 이를 정적으로 렌더링하는 작업을 담당합니다.  스트로크의 정적 렌더링과 동적 렌더링을 일관되게 하려면 <xref:System.Windows.Ink.Stroke.DrawCore%2A> 메서드를 재정의합니다.  
  
3.  **InkCanvas:** <xref:System.Windows.Controls.InkCanvas>에서 파생되는 클래스를 구현합니다.  <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 속성에 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>를 할당합니다.  <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> 메서드를 재정의하고 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 속성에 사용자 지정 스트로크를 추가합니다.  이를 통해 잉크 모양이 일관되게 유지됩니다.  
  
<a name="ImplementingADynamicRenderer"></a>   
## DynamicRenderer 구현  
 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 클래스가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 표준 요소이기는 하지만 보다 전문적인 렌더링을 수행하려면 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>에서 파생되는 사용자 지정 DynamicRenderer를 만들고 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A> 메서드를 재정의해야 합니다.  
  
 다음 예제에서는 선형 그라데이션 브러시 효과를 사용하여 잉크를 그리는 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>를 보여 줍니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>   
## 사용자 지정 Stroke 구현  
 <xref:System.Windows.Ink.Stroke>에서 파생되는 클래스를 구현합니다.  이 클래스는 <xref:System.Windows.Input.StylusPoint> 데이터가 <xref:System.Windows.Ink.Stroke> 개체로 변환된 후 이를 렌더링하는 작업을 담당합니다.  실제 그리기를 수행하도록 <xref:System.Windows.Ink.Stroke.DrawCore%2A> 클래스를 재정의합니다.  
  
 <xref:System.Windows.Ink.Stroke.AddPropertyData%2A> 메서드를 사용하면 사용자 지정 Stroke 클래스에 사용자 지정 데이터를 저장할 수도 있습니다.  이 데이터는 보관된 스트로크 데이터와 함께 저장됩니다.  
  
 <xref:System.Windows.Ink.Stroke> 클래스로 적중 테스트를 수행할 수도 있습니다.  현재 클래스에 <xref:System.Windows.Ink.Stroke.HitTest%2A> 메서드를 재정의하여 고유의 적중 테스트 알고리즘을 구현할 수도 있습니다.  
  
 다음 C\# 코드는 <xref:System.Windows.Input.StylusPoint> 데이터를 3차원 스트로크로 렌더링하는 사용자 지정 <xref:System.Windows.Ink.Stroke> 클래스를 보여 줍니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>   
## 사용자 지정 InkCanvas 구현  
 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>와 스트로크를 사용하는 가장 쉬운 방법은 <xref:System.Windows.Controls.InkCanvas>에서 파생되는 클래스를 구현하여 사용하는 것입니다.  <xref:System.Windows.Controls.InkCanvas>에는 사용자가 스트로크를 그릴 때 스트로크가 렌더링되는 방법을 지정하는 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 속성이 있습니다.  
  
 <xref:System.Windows.Controls.InkCanvas>의 스트로크 렌더링을 사용자 지정하려면 다음을 수행합니다.  
  
-   <xref:System.Windows.Controls.InkCanvas>에서 파생되는 클래스를 만듭니다.  
  
-   <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=fullName> 속성에 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>를 할당합니다.  
  
-   <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> 메서드를 재정의합니다.  이 메서드에서 InkCanvas에 추가된 원래 스트로크를 제거합니다.  그런 다음 사용자 지정 스트로크를 만들어 <xref:System.Windows.Controls.InkCanvas.Strokes%2A> 속성에 추가하고, 사용자 지정 스트로크가 포함된 새 <xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs>를 사용하여 기본 클래스를 호출합니다.  
  
 다음 C\# 코드는 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>를 사용하여 사용자 지정 스트로크를 수집하는 사용자 지정 <xref:System.Windows.Controls.InkCanvas> 클래스를 보여 줍니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 <xref:System.Windows.Controls.InkCanvas>는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>를 두 개 이상 가질 수 있습니다.  원하는 개체를 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성에 추가하여 여러 개의 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 개체를 <xref:System.Windows.Controls.InkCanvas>에 추가할 수 있습니다.  
  
<a name="Conclusion"></a>   
## 결론  
 고유의 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>, <xref:System.Windows.Ink.Stroke>, 및 <xref:System.Windows.Controls.InkCanvas> 클래스를 파생시켜 잉크의 모양을 사용자 지정할 수 있습니다.  이러한 클래스는 모두 사용자가 스트로크를 그릴 때와 스트로크가 수집된 후의 모양이 일관되도록 만듭니다.  
  
## 참고 항목  
 [고급 잉크 처리](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)