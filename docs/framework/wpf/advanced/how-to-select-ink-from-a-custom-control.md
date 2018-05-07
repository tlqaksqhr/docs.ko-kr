---
title: '방법: 사용자 지정 컨트롤에서 잉크 선택'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
ms.openlocfilehash: 6c85855cda4f74d557539ed7aea3f725550512e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-select-ink-from-a-custom-control"></a>방법: 사용자 지정 컨트롤에서 잉크 선택
추가 하 여 프로그램 <xref:System.Windows.Ink.IncrementalLassoHitTester> 사용자 지정 컨트롤을 활성화 컨트롤 사용자 방식과 유사 하 게 올가미 도구를 사용 하 여 잉크를 선택할 수 있도록는 <xref:System.Windows.Controls.InkCanvas> 가 올가미로 잉크를 선택 합니다.  
  
 이 예에서는 잉크 지원 사용자 지정 컨트롤을 만드는 잘 알고 있다면 가정 합니다.  잉크 입력을 허용 하는 사용자 지정 컨트롤을 만들려면 참조 [잉크 입력 컨트롤을 만드는](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)합니다.  
  
## <a name="example"></a>예제  
 사용자가 올가미로 그리면는 <xref:System.Windows.Ink.IncrementalLassoHitTester> 예측 사용자 올가미 완료 된 후 올가미 경로의 경계 내로 획 될 예정입니다.  올가미 경로의 경계 내에 있도록 결정 된 선은 선택 중인 생각할 수 있습니다.  선택한 스트로크 선택 되지 않은 메시지가 될 수도 있습니다.  예를 들어, 사용자 올가미를 그리는 동안 방향을 반대로 <xref:System.Windows.Ink.IncrementalLassoHitTester> 몇 개의 스트로크를 선택 취소할 수 있습니다.  
  
 <xref:System.Windows.Ink.IncrementalLassoHitTester> 발생는 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> 올가미 사용자를 그리는 동안 응답 하도록 사용자 지정 컨트롤 수 있도록 하는 이벤트입니다.  예를 들어 사용자가 선택 하거나 선택을 취소할으로 선의 모양을 변경할 수 있습니다.  
  
## <a name="managing-the-ink-mode"></a>잉크 모드 관리  
 올가미 컨트롤에 대 한 잉크 다르게 나타나는 경우 사용자에 게 도움이 됩니다. 이를 위해 사용자 지정 컨트롤 해야 여부를 추적 사용자가 작성 하거나 잉크를 선택 합니다. 이 작업을 수행 하는 가장 쉬운 방법은 두 값을 사용 하 여 열거형을 선언 하는: 잉크 및을 나타내고 사용자 잉크 선택 하는 사용자가 쓰기를 나타내는 하나입니다.  
  
 [!code-csharp[HowToSelectInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 다음으로, 두 개의 추가 <xref:System.Windows.Ink.DrawingAttributes> 클래스: 1에서 사용자가 잉크 잉크를 선택할 때 사용할 때 사용 하도록 합니다.  생성자에서 초기화 된 <xref:System.Windows.Ink.DrawingAttributes> 및 둘 다 연결 <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> 동일한 이벤트 처리기에 이벤트입니다. 다음 설정의 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> 의 속성은 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 잉크 <xref:System.Windows.Ink.DrawingAttributes>합니다.  
  
 [!code-csharp[HowToSelectInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 선택 모드를 노출 하는 속성을 추가 합니다. 사용자 선택 모드가 변경 되 면 설정는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> 의 속성은 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 을 적절 한 <xref:System.Windows.Ink.DrawingAttributes> 개체 한 후 다시 연결는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 속성을는 <xref:System.Windows.Controls.InkPresenter>합니다.  
  
 [!code-csharp[HowToSelectInk#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 노출 된 <xref:System.Windows.Ink.DrawingAttributes> 응용 프로그램 잉크 스트로크와 선택의 모양을 결정할 수 있도록 속성으로.  
  
 [!code-csharp[HowToSelectInk#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 한 속성이 <xref:System.Windows.Ink.DrawingAttributes> 개체 변경는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 다시 연결 되어야 합니다는 <xref:System.Windows.Controls.InkPresenter>합니다.  에 대 한 이벤트 처리기에는 <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> 이벤트를 다시 연결는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 에 <xref:System.Windows.Controls.InkPresenter>합니다.  
  
 [!code-csharp[HowToSelectInk#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a>IncrementalLassoHitTester를 사용 하 여  
 만들기 및 초기화는 <xref:System.Windows.Ink.StrokeCollection> 선택한 스트로크를 포함 하 합니다.  
  
 [!code-csharp[HowToSelectInk#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 사용자가 스트로크를 그리는 데 시작 되 면 잉크 또는 올가미를 선택된 된 스트로크의 선택을 취소 합니다. 그런 다음 사용자는 올가미로 그릴 만듭니다는 <xref:System.Windows.Ink.IncrementalLassoHitTester> 호출 하 여 <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>를 구독 하는 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> 이벤트 및 호출 <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>합니다. 이 코드는 별도 메서드 수 있으며에서 호출 된 <xref:System.Windows.UIElement.OnStylusDown%2A> 및 <xref:System.Windows.UIElement.OnMouseDown%2A> 메서드.  
  
 [!code-csharp[HowToSelectInk#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 스타일러스 가리키는 추가 <xref:System.Windows.Ink.IncrementalLassoHitTester> 사용자 올가미를 그리는 동안 합니다.  다음 메서드를 호출 하는 <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, 및 <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 메서드.  
  
 [!code-csharp[HowToSelectInk#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 처리는 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> 사용자가 선택 하 고 선 기능도 선택 취소에 응답 하는 이벤트입니다.  <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> 클래스에는 <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> 및 <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> 스트로크를 가져오는 속성을 선택 했으며 선택 되지 않음, 각각.  
  
 [!code-csharp[HowToSelectInk#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 사용자가 그리기 올가미 완료 되 면에서 구독을 취소는 <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> 이벤트 및 호출 <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>합니다.  
  
 [!code-csharp[HowToSelectInk#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a>정리 및 모든.  
 다음 예제는 사용자 지정 컨트롤을 통해 사용자는 올가미로 잉크를 선택할 수입니다.  
  
 [!code-csharp[HowToSelectInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Ink.IncrementalLassoHitTester>  
 <xref:System.Windows.Ink.StrokeCollection>  
 <xref:System.Windows.Input.StylusPointCollection>  
 [잉크 입력 컨트롤 만들기](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)
