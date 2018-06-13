---
title: 잉크 입력 컨트롤 만들기
ms.date: 03/30/2017
helpviewer_keywords:
- ink strokes [WPF], managing
- managing ink strokes [WPF]
- ink input control [WPF]
- input from mouse [WPF], accepting
- mouse input [WPF], accepting
- ink [WPF], rendering
- ink strokes [WPF], collecting
- rendering ink [WPF]
- collecting ink strokes [WPF]
- DynamicRenderer objects [WPF]
- StylusPlugIn objects [WPF]
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
ms.openlocfilehash: b3dc71182b7553a429bb17e1888a4108ceb3e286
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541059"
---
# <a name="creating-an-ink-input-control"></a>잉크 입력 컨트롤 만들기
컨트롤을 만들 수는 사용자 지정 하는 동적 및 정적으로 잉크를 렌더링 합니다. 즉, 사용자가 스트로크를 일으키는 잉크 "배치" 태블릿 펜 고 잉크 후 표시에 추가 된 컨트롤을 클립보드에서 붙여 넣은 태블릿 펜을 통해 또는 파일에서 로드 표시를 그릴 때 잉크를 렌더링 합니다. 잉크를 동적으로 렌더링 하려면 컨트롤을 사용 해야는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>합니다. 잉크를 정적으로 렌더링 하려면 스타일러스 이벤트 메서드를 재정의 해야 (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>, 및 <xref:System.Windows.UIElement.OnStylusUp%2A>)를 수집 하 <xref:System.Windows.Input.StylusPoint> 데이터를 스트로크를 만들고 추가 하는 프로그램 <xref:System.Windows.Controls.InkPresenter> (잉크를 렌더링 하는 컨트롤에).  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
-   [방법: 스타일러스 포인트 데이터 수집 및 잉크 스트로크 만들기](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
-   [방법: 마우스 입력을 허용 하도록 컨트롤을 사용 하도록 설정](#EnablingYourControlToAcceptInputTromTheMouse)  
  
-   [정리 및](#PuttingItTogether)  
  
-   [추가 플러그 인 및 DynamicRenderers를 사용 하 여](#UsingAdditionalPluginsAndDynamicRenderers)  
  
-   [결론](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a>방법: 스타일러스 포인트 데이터 수집 및 잉크 스트로크 만들기  
 스트로크를 수집 하 고 잉크를 관리 하는 컨트롤을 만들려면 다음을 수행.  
  
1.  클래스를 파생 <xref:System.Windows.Controls.Control> 에서 파생 된 클래스 중 하나 또는 <xref:System.Windows.Controls.Control>와 같은 <xref:System.Windows.Controls.Label>합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2.  추가 <xref:System.Windows.Controls.InkPresenter> 을 설정 하 고는 클래스는 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성을 새 <xref:System.Windows.Controls.InkPresenter>합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3.  연결는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> 의 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 에 <xref:System.Windows.Controls.InkPresenter> 호출 하 여는 <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> 메서드를 추가 하 고는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 에 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션입니다. 이 통해는 <xref:System.Windows.Controls.InkPresenter> 을 잉크로 설정 하면 제어 스타일러스 지점 데이터를 수집 합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4.  <xref:System.Windows.UIElement.OnStylusDown%2A> 메서드를 재정의합니다.  이 방법에 대 한 호출을 사용 하 여 스타일러스 캡처 <xref:System.Windows.Input.Stylus.Capture%2A>합니다. 스타일러스를 캡처하여를 계속 받으려면 컨트롤은 <xref:System.Windows.UIElement.StylusMove> 및 <xref:System.Windows.UIElement.StylusUp> 위에 있는 컨트롤의 경계를 벗어나 하는 경우에 이벤트입니다. 필수 엄격 하 게 하지만 효율적인 사용자 환경을 가급적 아닙니다. 새 <xref:System.Windows.Input.StylusPointCollection> 수집 하기 위해 <xref:System.Windows.Input.StylusPoint> 데이터입니다. 초기 집합을 마지막으로 추가 <xref:System.Windows.Input.StylusPoint> 데이터를는 <xref:System.Windows.Input.StylusPointCollection>합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5.  재정의 <xref:System.Windows.UIElement.OnStylusMove%2A> 메서드를 추가 하 고는 <xref:System.Windows.Input.StylusPoint> 데이터를는 <xref:System.Windows.Input.StylusPointCollection> 앞에서 만든 개체입니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6.  재정의 <xref:System.Windows.UIElement.OnStylusUp%2A> 메서드는 새 <xref:System.Windows.Ink.Stroke> 와 <xref:System.Windows.Input.StylusPointCollection> 데이터입니다. 새 추가 <xref:System.Windows.Ink.Stroke> 하기 위해 생성는 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> 의 컬렉션은 <xref:System.Windows.Controls.InkPresenter> 스타일러스 캡처를 해제 하 고 있습니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a>방법: 마우스 입력을 허용 하도록 컨트롤을 사용 하도록 설정  
 응용 프로그램에 위의 컨트롤을 추가 하 고 실행 한 마우스를 사용 하 여 입력 장치로 스트로크 유지 되지 않습니다을 알 수 있습니다. 선을 마우스 입력된 장치로 사용 되는 유지 하려면 다음을 수행 합니다.  
  
1.  재정의 <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> 을 새로 만듭니다 <xref:System.Windows.Input.StylusPointCollection> 이벤트가 발생할 때 마우스의 위치를 받고을 만들는 <xref:System.Windows.Input.StylusPoint> 지점 데이터를 사용 하 고 추가 <xref:System.Windows.Input.StylusPoint> 에 <xref:System.Windows.Input.StylusPointCollection>합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2.  <xref:System.Windows.UIElement.OnMouseMove%2A> 메서드를 재정의합니다. 이벤트가 발생 한 경우는 마우스의 상대 위치를 받고을 만들는 <xref:System.Windows.Input.StylusPoint> 지점 데이터를 사용 하 여 합니다.  추가 <xref:System.Windows.Input.StylusPoint> 에 <xref:System.Windows.Input.StylusPointCollection> 앞에서 만든 개체입니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3.  <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 메서드를 재정의합니다.  새 <xref:System.Windows.Ink.Stroke> 와 <xref:System.Windows.Input.StylusPointCollection> 데이터를 새 추가 <xref:System.Windows.Ink.Stroke> 하기 위해 생성는 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> 의 컬렉션은 <xref:System.Windows.Controls.InkPresenter>합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## <a name="putting-it-together"></a>정리 및  
 다음 예제는 사용자가 마우스 또는 펜을 사용 하는 경우 잉크를 수집 하는 사용자 지정 컨트롤입니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a>추가 플러그 인 및 DynamicRenderers를 사용 하 여  
 사용자 지정 컨트롤에는 InkCanvas 같이 사용자 지정을 가질 수 있습니다 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 및 추가 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 개체입니다. 이를 추가 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션입니다. 순서는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 개체에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 렌더링 될 때 잉크의 모양에 영향을 줍니다. 있다고 가정 하면는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 호출 `dynamicRenderer` 및 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 호출 `translatePlugin` 태블릿 펜에서 잉크를 오프셋입니다. 경우 `translatePlugin` 은 첫 번째 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, 및 `dynamicRenderer` 는 두 번째 사용자가 펜 "이동" 하 잉크 오프셋 됩니다. 경우 `dynamicRenderer` 처음, 및 `translatePlugin` 는 두 번째 사용자가 펜 뗄 때까지 잉크 오프셋 되지 것입니다.  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## <a name="conclusion"></a>결론  
 수집 하 여 스타일러스 이벤트 메서드를 재정의 하 여 잉크를 렌더링 하는 컨트롤을 만들 수 있습니다. 컨트롤을 직접 만들어서 파생 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 클래스를 삽입 하는에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, 디지털 잉크 상상할 수 있는 거의 모든 동작을 구현할 수 있습니다. 에 액세스할 수 있는 <xref:System.Windows.Input.StylusPoint> 것으로 데이터는 생성으로 사용자 지정할 수 있도록 <xref:System.Windows.Input.Stylus> 입력 하 고 응용 프로그램에 따라 화면에 렌더링 합니다. 이러한 하위 수준 액세스를 갖고 있으므로 <xref:System.Windows.Input.StylusPoint> 데이터를 잉크 컬렉션을 구현 하 고 응용 프로그램에 대 한 최적의 성능으로 렌더링 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [고급 잉크 처리](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)  
 [액세스 및 조작을 펜 입력](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
