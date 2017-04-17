---
title: "방법: 사용자 지정 컨트롤에서 잉크 선택 | Microsoft Docs"
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
  - "컨트롤, 잉크 선택"
  - "사용자 지정 컨트롤, 잉크 선택"
  - "잉크, 사용자 지정 컨트롤에서 선택"
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 사용자 지정 컨트롤에서 잉크 선택
사용자 지정 컨트롤에 <xref:System.Windows.Ink.IncrementalLassoHitTester>를 추가하면 <xref:System.Windows.Controls.InkCanvas>가 올가미를 사용하여 잉크를 선택하는 것과 비슷하게 사용자가 올가미 도구를 사용하여 잉크를 선택하는 것을 지원하도록 컨트롤을 설정할 수 있습니다.  
  
 이 예제에서는 사용자가 잉크 지원 사용자 지정 컨트롤을 만드는 것에 대해 잘 알고 있다고 가정합니다.  잉크 입력을 허용하는 사용자 지정 컨트롤을 만들려면 [잉크 입력 컨트롤 만들기](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)를 참조하십시오.  
  
## 예제  
 사용자가 올가미를 그릴 때 <xref:System.Windows.Ink.IncrementalLassoHitTester>는 사용자가 올가미를 완성한 후 올가미 경로의 경계 안에 놓이게 될 스트로크를 예측합니다.  올가미 경로의 경계 안에 놓이게 될 것으로 확인된 스트로크가 선택되는 스트로크입니다.  선택된 스트로크는 선택이 취소될 수도 있습니다.  예를 들어 사용자가 올가미를 그리는 동안 방향을 반대로 바꾸는 경우 <xref:System.Windows.Ink.IncrementalLassoHitTester>가 일부 스트로크의 선택을 취소할 수도 있습니다.  
  
 올가미를 그리는 동안 <xref:System.Windows.Ink.IncrementalLassoHitTester>가 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> 이벤트를 발생시켜 사용자 지정 컨트롤이 이에 응답하도록 합니다.  예를 들어 사용자가 선택하거나 선택을 취소할 때 스트로크의 모양이 변경되도록 할 수 있습니다.  
  
## 잉크 모드 관리  
 올가미가 컨트롤의 잉크와 다른 형태로 나타나면 사용자에게 편리합니다.  이를 위해서는 사용자가 잉크로 쓰는지 아니면 선택하는지 여부를 사용자 지정 컨트롤이 추적해야 합니다.  가장 쉬운 방법은 사용자가 잉크로 쓰고 있음을 나타내는 값 하나와 사용자가 잉크를 선택하고 있음을 나타내는 또 다른 값 하나가 있는 열거형을 선언하는 것입니다.  
  
 [!code-csharp[HowToSelectInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 그런 다음 사용자가 잉크로 쓸 때와 잉크를 선택할 때 사용할 두 개의 <xref:System.Windows.Ink.DrawingAttributes>를 클래스에 추가합니다.  생성자에서 <xref:System.Windows.Ink.DrawingAttributes>를 초기화하고 두 <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> 이벤트를 동일한 이벤트 처리기에 연결합니다.  그런 다음 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>의 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> 속성을 잉크 <xref:System.Windows.Ink.DrawingAttributes>로 설정합니다.  
  
 [!code-csharp[HowToSelectInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 선택 모드를 노출하는 속성을 추가합니다.  사용자가 선택 모드를 변경하는 경우 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>의 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> 속성을 적절한 <xref:System.Windows.Ink.DrawingAttributes> 개체로 설정한 다음 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 속성을 <xref:System.Windows.Controls.InkPresenter>에 다시 연결합니다.  
  
 [!code-csharp[HowToSelectInk#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 응용 프로그램이 잉크 스트로크와 선택 스트로크의 모양을 확인할 수 있도록 <xref:System.Windows.Ink.DrawingAttributes>를 속성으로 노출합니다.  
  
 [!code-csharp[HowToSelectInk#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 <xref:System.Windows.Ink.DrawingAttributes> 개체의 속성이 변경되면 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A>을 <xref:System.Windows.Controls.InkPresenter>에 다시 연결해야 합니다.  <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> 이벤트의 이벤트 처리기에서 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A>을 <xref:System.Windows.Controls.InkPresenter>에 다시 연결합니다.  
  
 [!code-csharp[HowToSelectInk#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## IncrementalLassoHitTester 사용  
 선택된 스트로크가 포함된 <xref:System.Windows.Ink.StrokeCollection>을 만들어 초기화합니다.  
  
 [!code-csharp[HowToSelectInk#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 사용자가 잉크 또는 올가미를 사용할 때 스트로크를 그리기 시작하면 선택된 스트로크의 선택을 취소합니다.  그런 다음 사용자가 올가미를 그리는 경우 <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>를 호출하여 <xref:System.Windows.Ink.IncrementalLassoHitTester>를 만들고 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> 이벤트에 등록하고 <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>를 호출합니다.  이 코드는 별도의 메서드로 사용할 수 있으며 <xref:System.Windows.UIElement.OnStylusDown%2A> 및 <xref:System.Windows.UIElement.OnMouseDown%2A> 메서드에서 호출할 수 있습니다.  
  
 [!code-csharp[HowToSelectInk#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 사용자가 올가미를 그리는 동안 <xref:System.Windows.Ink.IncrementalLassoHitTester>에 스타일러스 포인트를 추가합니다.  <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A> 및 <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 메서드에서 다음 메서드를 호출합니다.  
  
 [!code-csharp[HowToSelectInk#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 사용자가 스트로크를 선택하고 선택 취소할 때 응답할 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=fullName> 이벤트를 처리합니다.  <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> 클래스에는 선택된 스트로크를 가져오는 <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A>와 선택 취소된 스트로크를 가져오는 <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> 속성이 있습니다.  
  
 [!code-csharp[HowToSelectInk#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 사용자가 올가미를 그리는 작업을 마치면 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> 이벤트에 대한 등록을 취소하고 <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>을 호출합니다.  
  
 [!code-csharp[HowToSelectInk#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## 종합  
 다음 예제는 사용자가 올가미를 사용하여 잉크를 선택하는 것을 지원하는 사용자 지정 컨트롤입니다.  
  
 [!code-csharp[HowToSelectInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## 참고 항목  
 <xref:System.Windows.Ink.IncrementalLassoHitTester>   
 <xref:System.Windows.Ink.StrokeCollection>   
 <xref:System.Windows.Input.StylusPointCollection>   
 [잉크 입력 컨트롤 만들기](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)