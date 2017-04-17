---
title: "스타일러스에서 입력 가로채기 | Microsoft Docs"
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
  - "아키텍처, System.Windows.Input.StylusPlugIns"
  - "InkCanvas, 플러그 인 추가"
  - "플러그 인, 스타일러스"
  - "StylusPlugIns 아키텍처"
  - "System.Windows.Input.StylusPlugIns 아키텍처"
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 스타일러스에서 입력 가로채기
<xref:System.Windows.Input.StylusPlugIns> 아키텍처에서는 <xref:System.Windows.Input.Stylus> 입력 및 디지털 잉크 <xref:System.Windows.Ink.Stroke> 개체 생성에 대한 하위 수준 제어를 구현하는 메커니즘을 제공합니다.  <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 클래스에서는 사용자 지정 동작을 구현하고 최적의 성능을 위해 스타일러스 장치를 통해 입력되는 데이터 스트림에 해당 동작을 적용하는 메커니즘을 제공합니다.  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
-   [아키텍처](#Architecture)  
  
-   [스타일러스 플러그 인 구현](#ImplementingStylusPlugins)  
  
-   [InkCanvas에 플러그 인 추가](#AddingYourPluginToAnInkCanvas)  
  
-   [결론](#Conclusion)  
  
<a name="Architecture"></a>   
## 아키텍처  
 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>은 [Microsoft Windows XP Tablet PC Edition Software Development Kit 1.7](http://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409)의 [Accessing and Manipulating Pen Input](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)에 설명되어 있는 [StylusInput](http://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) API의 진화된 형태입니다.  
  
 각 <xref:System.Windows.UIElement>에는 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>인 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성이 있습니다.  요소의 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>을 추가하면 <xref:System.Windows.Input.StylusPoint> 데이터가 생성될 때 이 데이터를 조작할 수 있습니다.  <xref:System.Windows.Input.StylusPoint> 데이터는 <xref:System.Windows.Input.StylusPoint.X%2A> 및 <xref:System.Windows.Input.StylusPoint.Y%2A> 포인트 데이터뿐만 아니라 <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> 데이터를 비롯하여 시스템 디지타이저가 지원하는 모든 속성으로 구성됩니다.  
  
 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>을 추가하면 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 개체가 <xref:System.Windows.Input.Stylus> 장치를 통해 입력되는 데이터 스트림에 직접 삽입됩니다.  플러그 인이 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션에 추가되는 순서에 따라 플러그 인에서 <xref:System.Windows.Input.StylusPoint> 데이터를 받는 순서가 결정됩니다.  예를 들어 입력을 특정 영역으로 제한하는 필터 플러그 인을 추가한 다음 작성되는 제스처를 인식하는 플러그 인을 추가한 경우 제스처를 인식하는 플러그 인은 필터링된 <xref:System.Windows.Input.StylusPoint> 데이터를 받습니다.  
  
<a name="ImplementingStylusPlugins"></a>   
## 스타일러스 플러그 인 구현  
 플러그 인을 구현하려면 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>에서 클래스를 파생시킵니다.  이 클래스는 <xref:System.Windows.Input.Stylus>를 통해 입력되는 데이터 스트림에 적용됩니다.  이 클래스에서 <xref:System.Windows.Input.StylusPoint> 데이터 값을 수정할 수 있습니다.  
  
> [!CAUTION]
>  <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>에서 예외를 throw하거나 예외를 일으키면 응용 프로그램이 종료되므로  <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>을 사용하는 컨트롤을 철저하게 테스트하여 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>이 예외를 throw하지 않는 것이 확실한 경우에만 컨트롤을 사용해야 합니다.  
  
 다음 예제에서는 <xref:System.Windows.Input.Stylus> 장치를 통해 데이터가 입력될 때 <xref:System.Windows.Input.StylusPoint> 데이터에서 <xref:System.Windows.Input.StylusPoint.X%2A> 및 <xref:System.Windows.Input.StylusPoint.Y%2A> 값을 수정하여 스타일러스 입력을 제한하는 플러그 인을 보여 줍니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## InkCanvas에 플러그 인 추가  
 사용자 지정 플러그 인을 사용하는 가장 쉬운 방법은 InkCanvas에서 파생된 클래스를 구현한 다음 <xref:System.Windows.UIElement.StylusPlugIns%2A> 속성에 추가하는 것입니다.  
  
 다음 예제에서는 잉크를 필터링하는 사용자 지정 <xref:System.Windows.Controls.InkCanvas>를 보여 줍니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 응용 프로그램에 `FilterInkCanvas`를 추가하고 응용 프로그램을 실행하면 사용자가 스트로크를 완성할 때까지 잉크가 영역 제한을 받지 않는다는 것을 알 수 있습니다.  이것은 <xref:System.Windows.Controls.InkCanvas>에 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>이며 이미 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션의 멤버인 <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> 속성이 있기 때문입니다.  <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션에 추가한 사용자 지정 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>은 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>가 <xref:System.Windows.Input.StylusPoint> 데이터를 받은 후에 데이터를 받습니다.  결과적으로 사용자가 펜을 들어 스트로크를 끝낼 때까지 <xref:System.Windows.Input.StylusPoint> 데이터가 필터링되지 않습니다.  사용자가 그리는 동안 잉크를 필터링하려면 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> 앞에 `FilterPlugin`을 삽입해야 합니다.  
  
 다음 C\# 코드에서는 잉크를 그릴 때 필터링하는 사용자 지정 <xref:System.Windows.Controls.InkCanvas>를 보여 줍니다.  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## 결론  
 고유한 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> 클래스를 파생시켜 <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> 컬렉션에 삽입하면 디지털 잉크 동작을 크게 향상시킬 수 있습니다.  또한 <xref:System.Windows.Input.StylusPoint> 데이터가 생성될 때 이 데이터에 바로 액세스할 수 있으므로 <xref:System.Windows.Input.Stylus> 입력을 사용자 지정할 수 있습니다.  이렇듯 <xref:System.Windows.Input.StylusPoint> 데이터에 대한 하위 수준 액세스가 제공되므로 응용 프로그램에 사용할 잉크 컬렉션을 구현하고 최적의 성능으로 렌더링할 수 있습니다.  
  
## 참고 항목  
 [고급 잉크 처리](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)   
 [Accessing and Manipulating Pen Input](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)