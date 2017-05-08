---
title: "잉크 입력 컨트롤 만들기 | Microsoft Docs"
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
  - "잉크 스트로크 수집"
  - "DynamicRenderer 개체"
  - "잉크 입력 컨트롤"
  - "잉크 스트로크, 수집"
  - "잉크 스트로크, 관리"
  - "잉크, 렌더링(rendering)"
  - "마우스의 입력, 수락"
  - "잉크 스트로크 관리"
  - "마우스 입력, 수락"
  - "잉크 렌더링"
  - "StylusPlugIn 개체"
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 잉크 입력 컨트롤 만들기
동적으로 또는 정적으로 잉크를 렌더링하는 사용자 지정 컨트롤을 만들 수 있습니다.  즉, 태블릿 펜을 사용하거나, 클립보드에서 붙여 넣거나, 파일에서 로드하는 방법을 통해 사용자가 스트로크를 그릴 때 잉크를 렌더링하고, 잉크가 태블릿 펜에서 "흐르는 것처럼" 나타나도록 하고, 잉크가 컨트롤에 추가된 후 잉크를 표시합니다.  잉크를 동적으로 렌더링하려면 컨트롤은 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>를 사용해야 합니다.  잉크를 정적으로 렌더링하려면 스타일러스 이벤트 메서드\(<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A> 및 <xref:System.Windows.UIElement.OnStylusUp%2A>\)를 재정의하여 <xref:System.Windows.Input.StylusPoint> 데이터를 수집하고, 스트로크를 만들고, 컨트롤에 잉크를 렌더링하는 <xref:System.Windows.Controls.InkPresenter>에 이를 추가해야 합니다.  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
-   [방법: 스타일러스 포인트 데이터 수집 및 잉크 스트로크 만들기](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
-   [방법: 컨트롤이 마우스 입력을 받도록 설정](#EnablingYourControlToAcceptInputTromTheMouse)  
  
-   [종합](#PuttingItTogether)  
  
-   [추가 플러그 인 및 DynamicRenderer 사용](#UsingAdditionalPluginsAndDynamicRenderers)  
  
-   [결론](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## 방법: 스타일러스 포인트 데이터 수집 및 잉크 스트로크 만들기  
 잉크 스트로크를 수집하고 관리하는 컨트롤을 만들려면 다음을 수행합니다.  
  
1.  <xref:System.Windows.Controls.Control> 또는 <xref:System.Windows.Controls.Label>과 같은 <xref:System.Windows.Controls.Control>에서 파생된 클래스 중 하나에서 클래스를 파생시킵니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2.  <xref:System.Windows.Controls.InkPresenter>를 클래스에 추가하고 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성을 새 <xref:System.Windows.Controls.InkPresenter>로 설정합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3.  <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> 메서드를 호출하여 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>의 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A>을 <xref:System.Windows.Controls.InkPresenter>에 연결하고 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>를 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션에 추가합니다.  이렇게 하면 컨트롤에 의해 스타일러스 포인트 데이터가 수집될 때 <xref:System.Windows.Controls.InkPresenter>가 잉크를 표시할 수 있습니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4.  <xref:System.Windows.UIElement.OnStylusDown%2A> 메서드를 재정의합니다.  이 메서드에서 <xref:System.Windows.Input.Stylus.Capture%2A>에 대한 호출을 사용하여 스타일러스를 캡처합니다.  컨트롤은 스타일러스를 캡처함으로써 스타일러스가 컨트롤의 경계를 벗어나더라도 <xref:System.Windows.UIElement.StylusMove> 및 <xref:System.Windows.UIElement.StylusUp> 이벤트를 계속 수신합니다.  반드시 이렇게 해야 하는 것은 아니지만 사용자의 편리함을 위해 가급적이면 이 방법을 사용하는 것이 좋습니다.  <xref:System.Windows.Input.StylusPoint> 데이터를 수집하기 위해 새 <xref:System.Windows.Input.StylusPointCollection>을 만듭니다.  마지막으로, <xref:System.Windows.Input.StylusPoint> 데이터의 초기 집합을 <xref:System.Windows.Input.StylusPointCollection>에 추가합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5.  <xref:System.Windows.UIElement.OnStylusMove%2A> 메서드를 재정의하고 <xref:System.Windows.Input.StylusPoint> 데이터를 이전에 만든 <xref:System.Windows.Input.StylusPointCollection> 개체에 추가합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6.  <xref:System.Windows.UIElement.OnStylusUp%2A> 메서드를 재정의하고 <xref:System.Windows.Input.StylusPointCollection> 데이터로 새 <xref:System.Windows.Ink.Stroke>를 만듭니다.  이렇게 만든 새 <xref:System.Windows.Ink.Stroke>를 <xref:System.Windows.Controls.InkPresenter>의 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> 컬렉션에 추가하고 스타일러스 캡처를 해제합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## 방법: 컨트롤이 마우스 입력을 받도록 설정  
 이전 컨트롤을 응용 프로그램에 추가하고 실행한 다음 마우스를 입력 장치로 사용하면 스트로크가 지속되지 않음을 알 수 있습니다.  마우스를 입력 장치로 사용할 때 스트로크가 지속되게 하려면 다음을 수행합니다.  
  
1.  <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A>을 재정의하여 새 <xref:System.Windows.Input.StylusPointCollection>을 만듭니다. 이벤트가 발생했을 때 마우스의 위치를 가져온 다음 포인트 데이터를 사용하여 <xref:System.Windows.Input.StylusPoint>를 만들고 <xref:System.Windows.Input.StylusPoint>를 <xref:System.Windows.Input.StylusPointCollection>에 추가합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2.  <xref:System.Windows.UIElement.OnMouseMove%2A> 메서드를 재정의합니다.  이벤트가 발생했을 때 마우스의 위치를 가져오고 포인트 데이터를 사용하여 <xref:System.Windows.Input.StylusPoint>를 만듭니다.  앞서 만든 <xref:System.Windows.Input.StylusPointCollection> 개체에 <xref:System.Windows.Input.StylusPoint>를 추가합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3.  <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 메서드를 재정의합니다.  <xref:System.Windows.Input.StylusPointCollection> 데이터로 새 <xref:System.Windows.Ink.Stroke>를 만들고, 앞서 만든 새 <xref:System.Windows.Ink.Stroke>를 <xref:System.Windows.Controls.InkPresenter>의 <xref:System.Windows.Controls.InkPresenter.Strokes%2A> 컬렉션에 추가합니다.  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## 종합  
 다음은 사용자가 마우스 또는 펜을 사용할 때 잉크를 수집하는 사용자 지정 컨트롤의 예제입니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## 추가 플러그 인 및 DynamicRenderer 사용  
 이 사용자 지정 컨트롤에는 InkCanvas처럼 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>과 추가적인 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 개체가 있을 수 있습니다.  이를 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션에 추가합니다.  <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>에서 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 개체의 순서는 렌더링되는 잉크 모양에 영향을 줍니다.  `dynamicRenderer`라는 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>와 태블릿 펜에서 잉크를 오프셋하는 `translatePlugin`이라는 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>이 있다고 가정해 보겠습니다.  `translatePlugin`이 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>에서 첫 번째 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>이고 `dynamicRenderer`가 두 번째인 경우 사용자가 펜을 움직이면 "흐르는" 잉크가 오프셋됩니다.  `dynamicRenderer`가 첫 번째이고 `translatePlugin`이 두 번째이면 사용자가 펜을 들어 올리기 전까지는 잉크가 오프셋되지 않습니다.  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## 결론  
 스타일러스 이벤트 메서드를 재정의하여 잉크를 수집하고 렌더링하는 컨트롤을 만들 수 있습니다.  컨트롤을 직접 만들고, <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 클래스를 파생시키고, 이를 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>에 삽입하면 상상할 수 있는 거의 모든 동작을 디지털 잉크로 구현할 수 있습니다.  생성되는 <xref:System.Windows.Input.StylusPoint> 데이터에 액세스할 수 있으므로 <xref:System.Windows.Input.Stylus> 입력을 사용자 지정하여 응용 프로그램에 적합한 형태로 화면에 렌더링할 수 있습니다.  <xref:System.Windows.Input.StylusPoint> 데이터에 대한 하위 수준 액세스가 가능하므로 잉크 컬렉션을 구현하고 응용 프로그램에 최적의 성능으로 렌더링할 수 있습니다.  
  
## 참고 항목  
 [고급 잉크 처리](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)   
 [Accessing and Manipulating Pen Input](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)