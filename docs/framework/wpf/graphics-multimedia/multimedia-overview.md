---
title: "멀티미디어 개요 | Microsoft Docs"
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
  - "미디어"
  - "멀티미디어"
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 멀티미디어 개요
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 멀티미디어 기능을 사용하면 오디오 및 비디오를 응용 프로그램에 통합하여 사용자 환경을 개선할 수 있습니다. 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 멀티미디어 기능을 소개합니다.  
  
   
  
<a name="mediaapi"></a>   
## 미디어 API  
 오디오 또는 비디오 콘텐츠를 제공하는 데에는 <xref:System.Windows.Controls.MediaElement> 및 <xref:System.Windows.Media.MediaPlayer> 클래스가 모두 사용됩니다.  이러한 클래스는 대화형으로 제어하거나 시계를 사용하여 제어할 수 있습니다.  이러한 클래스는 [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 컨트롤에서 미디어를 재생하는 데 사용할 수 있습니다. 사용할 클래스는 경우에 따라 달라집니다.  
  
 <xref:System.Windows.Controls.MediaElement>는 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)에서 지원하는 <xref:System.Windows.UIElement>이며 많은 컨트롤의 콘텐츠로 사용될 수 있습니다.  이는 코드뿐만 아니라 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서도 사용할 수 있습니다. 반면 <xref:System.Windows.Media.MediaPlayer>는 <xref:System.Windows.Media.Drawing> 개체를 위해 디자인되었으며 레이아웃을 지원하지 않습니다.  <xref:System.Windows.Media.MediaPlayer>를 사용하여 로드된 미디어는 <xref:System.Windows.Media.VideoDrawing>을 사용하거나 <xref:System.Windows.Media.DrawingContext>와의 직접적인 상호 작용을 통해서만 제공될 수 있습니다.  <xref:System.Windows.Media.MediaPlayer>는 XAML에서 사용될 수 없습니다.  
  
 그리기 개체 및 그리기 컨텍스트에 대한 자세한 내용은 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)를 참조하십시오.  
  
> [!NOTE]
>  응용 프로그램으로 미디어를 배포하는 경우 미디어 파일을 프로젝트 리소스로 사용할 수 없습니다.  대신 프로젝트 파일에서 미디어 형식을 `Content`로 설정하고 `CopyToOutputDirectory`를 `PreserveNewest` 또는 `Always`로 설정해야 합니다.  
  
<a name="mediaplaybackmodes"></a>   
## 미디어 재생 모드  
  
> [!NOTE]
>  <xref:System.Windows.Controls.MediaElement> 및 <xref:System.Windows.Media.MediaPlayer> 모두에는 유사한 멤버가 있습니다.  이 단원에 있는 링크를 사용하여 <xref:System.Windows.Controls.MediaElement> 클래스 멤버를 참조할 수 있습니다.  특별히 언급하지 않는 한 <xref:System.Windows.Controls.MediaElement> 클래스에서 링크가 지정된 멤버는 <xref:System.Windows.Media.MediaPlayer> 클래스에도 있습니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 미디어 재생을 이해하려면 미디어를 재생할 수 있는 다양한 모드를 이해해야 합니다.  <xref:System.Windows.Controls.MediaElement> 및 <xref:System.Windows.Media.MediaPlayer>는 모두 독립 모드와 시계 모드라는 서로 다른 두 가지 미디어 모드에서 사용할 수 있습니다.  미디어 모드는 <xref:System.Windows.Controls.MediaElement.Clock%2A> 속성에 의해 결정됩니다.  <xref:System.Windows.Controls.MediaElement.Clock%2A>이 `null`이면 미디어 개체가 독립 모드에 있습니다.  <xref:System.Windows.Controls.MediaElement.Clock%2A>이 null이 아니면 미디어 개체가 시계 모드에 있습니다.  기본적으로 미디어 개체는 독립 모드에 있습니다.  
  
### 독립 모드  
 독립 모드에서 미디어 콘텐츠는 미디어를 재생합니다.  독립 모드에서는 다음 옵션을 사용할 수 있습니다.  
  
-   미디어의 <xref:System.Uri>를 직접 지정할 수 있습니다.  
  
-   미디어 재생을 직접 제어할 수 있습니다.  
  
-   미디어의 <xref:System.Windows.Controls.MediaElement.Position%2A> 및 <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> 속성을 수정할 수 있습니다.  
  
 <xref:System.Windows.Controls.MediaElement> 개체의 <xref:System.Windows.Controls.MediaElement.Source%2A> 속성을 설정하거나 <xref:System.Windows.Media.MediaPlayer> 개체의 <xref:System.Windows.Media.MediaPlayer.Open%2A> 메서드를 호출하여 미디어를 로드합니다.  
  
 독립 모드에서 미디어 재생을 제어하려면 미디어 개체의 컨트롤 메서드를 사용합니다.  사용 가능한 컨트롤 메서드는 <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A> 및 <xref:System.Windows.Controls.MediaElement.Stop%2A>입니다.  <xref:System.Windows.Controls.MediaElement>에 대해서는 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>가 <xref:System.Windows.Controls.MediaState>로 설정된 경우에만 이러한 메서드를 사용하는 대화형 컨트롤을 사용할 수 있습니다.  미디어 개체가 시계 모드에 있는 경우에는 이러한 메서드를 사용할 수 없습니다.  
  
 독립 모드의 예제를 보려면 [MediaElement 제어\(재생, 일시 중지, 정지, 볼륨 및 속도\)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)를 참조하십시오.  
  
### 시계 모드  
 시계 모드에서는 <xref:System.Windows.Media.MediaTimeline>이 미디어를 재생합니다.  시계 모드의 특성은 다음과 같습니다.  
  
-   미디어의 <xref:System.Uri>는 <xref:System.Windows.Media.MediaTimeline>을 통해 간접적으로 설정됩니다.  
  
-   미디어 재생은 시계로 제어할 수 있습니다.  미디어 개체의 컨트롤 메서드는 사용할 수 없습니다.  
  
-   <xref:System.Windows.Media.MediaTimeline> 개체의 <xref:System.Windows.Media.MediaTimeline.Source%2A> 속성을 설정하고, 시간 표시 막대에서 시계를 만들고, 이 시계를 미디어 개체에 할당하여 미디어를 로드합니다.  <xref:System.Windows.Media.Animation.Storyboard> 내부의 <xref:System.Windows.Media.MediaTimeline>이 <xref:System.Windows.Controls.MediaElement>를 대상으로 하는 경우에도 미디어가 이러한 방식으로 로드됩니다.  
  
 시계 모드에서 미디어 재생을 제어하려면 <xref:System.Windows.Media.Animation.ClockController> 컨트롤 메서드를 사용해야 합니다.  <xref:System.Windows.Media.Animation.ClockController>는 <xref:System.Windows.Media.MediaClock>의 <xref:System.Windows.Media.Animation.ClockController> 속성에서 가져옵니다.  시계 모드에서 <xref:System.Windows.Controls.MediaElement> 또는 <xref:System.Windows.Media.MediaPlayer> 개체의 컨트롤 메서드를 사용하면 <xref:System.InvalidOperationException>이 throw됩니다.  
  
 시계 및 시간 표시 막대에 대한 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
 시계 모드의 예제를 보려면 [Storyboard를 사용하여 MediaElement 제어](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)를 참조하십시오.  
  
<a name="mediaelement"></a>   
## MediaElement 클래스  
 응용 프로그램에 미디어를 추가하는 것은 응용 프로그램의 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에 <xref:System.Windows.Controls.MediaElement> 컨트롤을 추가하고 포함하려는 미디어에 <xref:System.Uri>를 제공하는 것만큼 간단합니다.  [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10에서 지원하는 모든 미디어 형식은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서도 지원됩니다. 다음 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 <xref:System.Windows.Controls.MediaElement>를 간단히 사용하는 방법을 보여 줍니다.  
  
 [!code-xml[MediaElement_snip#SimpleMediaElementUsageWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 이 샘플에서 미디어는 로드되는 즉시 자동으로 재생됩니다.  미디어 재생이 끝나면 미디어가 닫히고 비디오 메모리를 비롯한 모든 미디어 리소스가 해제됩니다.  이는 <xref:System.Windows.Controls.MediaElement> 개체의 기본 동작이며 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 및 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 속성으로 제어됩니다.  
  
### MediaElement 제어  
 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 및 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 속성은 <xref:System.Windows.FrameworkElement.IsLoaded%2A>가 각각 `true` 또는 `false`일 때 <xref:System.Windows.Controls.MediaElement>의 동작을 제어합니다.  <xref:System.Windows.Controls.MediaState> 속성을 설정하면 미디어 재생 동작이 영향을 받습니다.  예를 들어 기본 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>는 <xref:System.Windows.Controls.MediaState>이고 기본 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>는 <xref:System.Windows.Controls.MediaState>입니다.  즉, <xref:System.Windows.Controls.MediaElement>가 로드되고 [미리 받기](GTMT)가 완료되는 즉시 미디어가 재생되기 시작합니다.  재생이 완료되면 미디어가 닫히고 모든 미디어 리소스가 해제됩니다.  
  
 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 및 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 속성으로만 미디어 재생을 제어할 수 있는 것은 아닙니다.  시계 모드에서 시계는 <xref:System.Windows.Controls.MediaElement>를 제어할 수 있고 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>가 <xref:System.Windows.Controls.MediaState>인 경우에는 대화형 컨트롤 메서드에 제어권이 있습니다.  <xref:System.Windows.Controls.MediaElement>는 다음 우선 순위를 평가하여 이러한 제어권 경쟁 상황을 처리합니다.  
  
1.  <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>.  미디어가 언로드될 때 적용됩니다.  이는 <xref:System.Windows.Media.MediaClock>이 <xref:System.Windows.Controls.MediaElement>에 연결되어 있는 경우에도 기본적으로 모든 미디어 리소스가 해제되도록 합니다.  
  
2.  <xref:System.Windows.Media.MediaClock>.  미디어에 <xref:System.Windows.Controls.MediaElement.Clock%2A>이 있으면 적용됩니다.  미디어가 언로드되면 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>가 <xref:System.Windows.Controls.MediaState>인 한 <xref:System.Windows.Media.MediaClock>이 적용됩니다.  시계 모드는 항상 <xref:System.Windows.Controls.MediaElement>의 로드된 동작을 재정의합니다.  
  
3.  <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>.  미디어가 로드될 때 적용됩니다.  
  
4.  대화형 컨트롤 메서드.  <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>가 <xref:System.Windows.Controls.MediaState>이면 적용됩니다.  사용 가능한 컨트롤 메서드는 <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A> 및 <xref:System.Windows.Controls.MediaElement.Stop%2A>입니다.  
  
### MediaElement 표시  
 <xref:System.Windows.Controls.MediaElement>를 표시하려면 이 요소에 렌더링할 콘텐츠가 있어야 하며 콘텐츠가 로드될 때까지 해당 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 및 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 속성이 0으로 설정됩니다.  오디오 전용 콘텐츠의 경우에는 이러한 속성이 항상 0입니다.  비디오 콘텐츠의 경우 <xref:System.Windows.Controls.MediaElement.MediaOpened> 이벤트가 발생하면 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 및 <xref:System.Windows.FrameworkElement.ActualHeight%2A>가 로드된 미디어의 크기를 보고합니다.  즉, <xref:System.Windows.FrameworkElement.Width%2A> 또는 <xref:System.Windows.FrameworkElement.Height%2A> 속성이 설정되지 않은 한 <xref:System.Windows.Controls.MediaElement>는 미디어가 로드될 때까지 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에서 실제 공간을 차지하지 않습니다.  
  
 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 모두 설정하면 미디어가 늘어나 <xref:System.Windows.Controls.MediaElement>에 대해 제공된 영역이 채워집니다.  미디어의 원래 [가로 세로 비율](GTMT)을 유지하려면 <xref:System.Windows.FrameworkElement.Width%2A> 또는 <xref:System.Windows.FrameworkElement.Height%2A> 속성 중 하나만 설정해야 하며 둘 다 설정해서는 안 됩니다.  <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 모두 설정하면 미디어가 고정된 요소 크기로 제공되며 이는 원하지 않는 동작일 수 있습니다.  
  
 고정된 크기의 요소가 제공되지 않도록 하려면 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 미디어를 [미리 받기](GTMT)합니다.  이는 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>를 <xref:System.Windows.Controls.MediaState> 또는 <xref:System.Windows.Controls.MediaState>로 설정하여 수행합니다.  <xref:System.Windows.Controls.MediaState> 상태에서는 미디어가 미리 받아져 첫 번째 프레임이 제공됩니다.  <xref:System.Windows.Controls.MediaState> 상태에서는 미디어가 [미리 받기](GTMT)되고 재생이 시작됩니다.  
  
<a name="mediaplayer"></a>   
## MediaPlayer 클래스  
 <xref:System.Windows.Controls.MediaElement> 클래스가 프레임워크 요소인 반면 <xref:System.Windows.Media.MediaPlayer> 클래스는 <xref:System.Windows.Media.Drawing> 개체에 사용되도록 디자인되었습니다.  그리기 개체는 성능 혜택을 얻기 위해 프레임워크 수준 기능을 사용하지 않거나 <xref:System.Windows.Freezable> 기능이 필요한 경우 사용됩니다.  <xref:System.Windows.Media.MediaPlayer>를 사용하면 응용 프로그램에 미디어 콘텐츠를 제공하면서 이러한 기능을 활용할 수 있습니다.  <xref:System.Windows.Controls.MediaElement>와 같이 <xref:System.Windows.Media.MediaPlayer>는 독립 모드 또는 시계 모드에서 사용될 수 있지만 <xref:System.Windows.Controls.MediaElement> 개체의 언로드 및 로드 상태는 제공되지 않습니다.  이를 통해 <xref:System.Windows.Media.MediaPlayer>의 재생 제어는 간단해집니다.  
  
### MediaPlayer 제어  
 <xref:System.Windows.Media.MediaPlayer>는 상태를 저장하지 않기 때문에 미디어 재생을 제어할 수 있는 방법이 두 가지 뿐입니다.  
  
1.  대화형 컨트롤 메서드.  독립 모드\(`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A> 속성\)일 때 적용됩니다.  
  
2.  <xref:System.Windows.Media.MediaClock>.  미디어에 <xref:System.Windows.Media.MediaPlayer.Clock%2A>이 있으면 적용됩니다.  
  
### MediaPlayer 표시  
 <xref:System.Windows.Media.MediaPlayer>에는 물리적 표현이 없기 때문에 기술적으로는 이를 표시할 수 없지만  <xref:System.Windows.Media.VideoDrawing> 클래스를 사용하여 <xref:System.Windows.Media.Drawing>에 미디어를 제공하는 데에는 사용할 수 있습니다.  다음 예제에서는 <xref:System.Windows.Media.VideoDrawing>을 사용하여 미디어를 표시하는 방법을 보여 줍니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <xref:System.Windows.Media.Drawing> 개체에 대한 자세한 내용은 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.DrawingGroup>   
 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)