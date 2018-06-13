---
title: 멀티미디어 개요
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF]
- media [WPF]
ms.assetid: feb25b15-d741-4ac3-818f-1b19f63a3562
ms.openlocfilehash: 7a986125cff1ff4812528212fa3aee7689af1f16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566433"
---
# <a name="multimedia-overview"></a>멀티미디어 개요
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 멀티미디어 기능을 통해 오디오 및 비디오를 응용 프로그램에 통합하여 사용자 환경을 개선할 수 있습니다. 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 멀티미디어 기능을 소개합니다.  
  
 
  
<a name="mediaapi"></a>   
## <a name="media-api"></a>미디어 API  
 <xref:System.Windows.Controls.MediaElement> 및 <xref:System.Windows.Media.MediaPlayer> 클래스 오디오 또는 비디오 콘텐츠를 제공 하는 데 사용 됩니다. 이러한 클래스는 대화형으로 또는 클록을 통해 제어할 수 있습니다. 이러한 클래스는 미디어 재생을 위한 [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10 컨트롤에서 사용할 수 있습니다. 사용하는 클래스는 시나리오에 따라 달라집니다.  
  
 <xref:System.Windows.Controls.MediaElement> 이 <xref:System.Windows.UIElement> 으로 사용할 수 있는 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md) 여러 컨트롤의 내용으로 사용 될 수 있습니다. 코드 뿐만 아니라 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서도 사용할 수 있습니다. <xref:System.Windows.Media.MediaPlayer>를 위해 디자인 된 반면에 <xref:System.Windows.Media.Drawing> 개체 및 레이아웃을 지원 하지 합니다. 사용 하 여 로드 된 미디어는 <xref:System.Windows.Media.MediaPlayer> 만 사용 하 여 표시 수는 <xref:System.Windows.Media.VideoDrawing> 또는 직접 상호 작용 하 여는 <xref:System.Windows.Media.DrawingContext>합니다. <xref:System.Windows.Media.MediaPlayer> XAML에서 사용할 수 없습니다.  
  
 Drawing 개체 및 그리기 컨텍스트에 대한 자세한 내용은 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)를 참조하세요.  
  
> [!NOTE]
>  응용 프로그램을 사용하여 미디어를 배포하는 경우 미디어 파일을 프로젝트 리소스로 사용할 수 없습니다. 대신 프로젝트 파일에서 미디어 형식을 `Content`로 설정하고 `CopyToOutputDirectory`를 `PreserveNewest` 또는 `Always`로 설정해야 합니다.  
  
<a name="mediaplaybackmodes"></a>   
## <a name="media-playback-modes"></a>미디어 재생 모드  
  
> [!NOTE]
>  둘 다 <xref:System.Windows.Controls.MediaElement> 및 <xref:System.Windows.Media.MediaPlayer> 는 유사한 멤버가 있습니다. 이 섹션의 링크를 참조는 <xref:System.Windows.Controls.MediaElement> 클래스 멤버입니다. 구체적으로 언급 하지 않는 한 멤버는 연결에 <xref:System.Windows.Controls.MediaElement> 에서 클래스를 찾을 수도 있습니다는 <xref:System.Windows.Media.MediaPlayer> 클래스입니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 미디어 재생을 이해하려면 미디어를 재생할 수 있는 여러 다른 모드를 이해해야 합니다. 둘 다 <xref:System.Windows.Controls.MediaElement> 및 <xref:System.Windows.Media.MediaPlayer> 두 가지 미디어 모드, 독립 모드 및 클록 모드에서 사용할 수 있습니다. 미디어 모드에 의해 결정 되는 <xref:System.Windows.Controls.MediaElement.Clock%2A> 속성입니다. 때 <xref:System.Windows.Controls.MediaElement.Clock%2A> 은 `null`, 미디어 개체입니다. 독립 모드. 경우는 <xref:System.Windows.Controls.MediaElement.Clock%2A> 은 null이 아닌 미디어 개체가 클록 모드에 있기 합니다. 기본적으로 미디어 개체는 독립 모드입니다.  
  
### <a name="independent-mode"></a>독립 모드  
 독립 모드에서 미디어 콘텐츠는 미디어 재생을 주도합니다. 독립 모드에서는 다음과 같은 옵션을 사용할 수 있습니다.  
  
-   미디어의 <xref:System.Uri> 직접 지정할 수 있습니다.  
  
-   미디어 재생을 직접 제어할 수 있습니다.  
  
-   미디어의 <xref:System.Windows.Controls.MediaElement.Position%2A> 및 <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> 속성을 수정할 수 있습니다.  
  
 미디어 설정 하거나에 의해 로드 되는 <xref:System.Windows.Controls.MediaElement> 개체의 <xref:System.Windows.Controls.MediaElement.Source%2A> 속성 또는 호출 하 여는 <xref:System.Windows.Media.MediaPlayer> 개체의 <xref:System.Windows.Media.MediaPlayer.Open%2A> 메서드.  
  
 독립 모드에서 미디어 재생을 제어하려면 미디어 개체의 컨트롤 메서드를 사용할 수 있습니다. 사용 가능한 컨트롤 메서드는 <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, 및 <xref:System.Windows.Controls.MediaElement.Stop%2A>합니다. 에 대 한 <xref:System.Windows.Controls.MediaElement>, 이러한 메서드를 사용 하 여 대화형 컨트롤 에서만 사용 가능 시기는 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 로 설정 된 <xref:System.Windows.Controls.MediaState.Manual>합니다. 이러한 메서드는 미디어 개체가 클록 모드에 있을 때는 사용할 수 없습니다.  
  
 독립 모드의 예제를 보려면 [MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)를 참조하세요.  
  
### <a name="clock-mode"></a>클록 모드  
 시계 모드에서는 <xref:System.Windows.Media.MediaTimeline> 이 미디어를 재생 합니다. 클록 모드에는 다음과 같은 특징이 있습니다.  
  
-   미디어의 <xref:System.Uri> 통해 간접적으로 설정 되는 <xref:System.Windows.Media.MediaTimeline>합니다.  
  
-   미디어 재생을 클록으로 제어할 수 있습니다. 미디어 개체의 컨트롤 메서드를 사용할 수 없습니다.  
  
-   미디어 설정에 의해 로드 되는 <xref:System.Windows.Media.MediaTimeline> 개체의 <xref:System.Windows.Media.MediaTimeline.Source%2A> 속성을 타임 라인에서 시계를 만들고 미디어 개체를 시계를 할당 합니다. 미디어를 이러한 방식으로 로드도 때는 <xref:System.Windows.Media.MediaTimeline> 내는 <xref:System.Windows.Media.Animation.Storyboard> 대상은 <xref:System.Windows.Controls.MediaElement>합니다.  
  
 클록 모드로 미디어 재생을 제어 하는 <xref:System.Windows.Media.Animation.ClockController> 제어 메서드를 사용 해야 합니다. A <xref:System.Windows.Media.Animation.ClockController> 에서 가져온는 <xref:System.Windows.Media.Animation.ClockController> 의 속성은 <xref:System.Windows.Media.MediaClock>합니다. 컨트롤 메서드를 사용 하려고 한 <xref:System.Windows.Controls.MediaElement> 또는 <xref:System.Windows.Media.MediaPlayer> 클록 모드에서는 개체는 <xref:System.InvalidOperationException> throw 됩니다.  
  
 클록 및 타임라인에 대한 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하세요.  
  
 클록 모드 예제를 보려면 [Storyboard를 사용하여 MediaElement 제어](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)를 참조하세요.  
  
<a name="mediaelement"></a>   
## <a name="mediaelement-class"></a>MediaElement 클래스  
 응용 프로그램에 미디어를 추가 하는 것은 추가 처럼 간단할는 <xref:System.Windows.Controls.MediaElement> 컨트롤을 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 응용 프로그램의 제공 하는 <xref:System.Uri> 포함 시킬 미디어에 합니다. [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 10에서 지원하는 모든 미디어 형식이 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 지원됩니다. 다음 예제에서는의 간단한 사용은 <xref:System.Windows.Controls.MediaElement> 에서 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.  
  
 [!code-xaml[MediaElement_snip#SimpleMediaElementUsageWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaElement_snip/CSharp/SimpleUsage.xaml#simplemediaelementusagewholepage)]  
  
 이 샘플에서는 미디어가 로드되는 즉시 자동으로 재생됩니다. 미디어 재생이 완료되면 미디어가 닫히고 모든 미디어 리소스(비디오 메모리 포함)는 해제됩니다. 이 기본적으로는 <xref:System.Windows.Controls.MediaElement> 개체를 통해 제어 됩니다는 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 및 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 속성.  
  
### <a name="controlling-a-mediaelement"></a>MediaElement 제어  
 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 및 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 의 동작을 제어 하는 속성은 <xref:System.Windows.Controls.MediaElement> 때 <xref:System.Windows.FrameworkElement.IsLoaded%2A> 은 `true` 또는 `false`각각. <xref:System.Windows.Controls.MediaState> 는 속성이 미디어 재생 동작에 영향을으로 설정 됩니다. 예를 들어 기본 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 은 <xref:System.Windows.Controls.MediaState.Play> 및 기본 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 은 <xref:System.Windows.Controls.MediaState.Close>합니다. 즉으로 <xref:System.Windows.Controls.MediaElement> 로드 및 미리 받기 완료 되 면 미디어 재생 되기 시작 합니다. 재생이 완료되면 미디어가 닫히고 모든 미디어 리소스가 해제됩니다.  
  
 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 및 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 속성은 미디어 재생을 제어 하는 유일한 방법은 없습니다. 클록 모드로 시계를 제어할 수는 <xref:System.Windows.Controls.MediaElement> 대화형 제어 방법을 시기를 제어 하는 및의 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 은 <xref:System.Windows.Controls.MediaState.Manual>합니다. <xref:System.Windows.Controls.MediaElement> 다음과 같은 우선 순위를 평가 하 여 컨트롤에 대 한이 경합은이 처리 합니다.  
  
1.  <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A>. 미디어가 언로드될 때 적용됩니다. 이렇게 하면 기본적으로 모든 미디어 리소스가 해제 되는 경우에는 <xref:System.Windows.Media.MediaClock> 연결 된는 <xref:System.Windows.Controls.MediaElement>합니다.  
  
2.  <xref:System.Windows.Media.MediaClock>. 미디어의 경우에 <xref:System.Windows.Controls.MediaElement.Clock%2A>합니다. 미디어 언로드되면는 <xref:System.Windows.Media.MediaClock> 사항을 그대로 적용은 <xref:System.Windows.Controls.MediaElement.UnloadedBehavior%2A> 은 <xref:System.Windows.Controls.MediaState.Manual>합니다. 클록 모드는 항상 로드 동작을 재정의 <xref:System.Windows.Controls.MediaElement>합니다.  
  
3.  <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>. 미디어가 로드될 때 적용됩니다.  
  
4.  대화형 컨트롤 메서드. 적용 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 은 <xref:System.Windows.Controls.MediaState.Manual>합니다. 사용 가능한 컨트롤 메서드는 <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, <xref:System.Windows.Controls.MediaElement.Close%2A>, 및 <xref:System.Windows.Controls.MediaElement.Stop%2A>합니다.  
  
### <a name="displaying-a-mediaelement"></a>MediaElement 표시  
 표시 하는 <xref:System.Windows.Controls.MediaElement> 렌더링 하도록 있어야 하 고 미치게 될 해당 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 및 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 속성이 콘텐츠가 로드 될 때까지 0으로 설정 합니다. 오디오 전용 콘텐츠의 경우 이러한 속성은 항상 0입니다. 비디오 콘텐츠의 경우에 <xref:System.Windows.Controls.MediaElement.MediaOpened> 이벤트가 발생는 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 및 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 가 로드 된 미디어의 크기를 보고 합니다. 즉, 미디어 로드 될 때까지 <xref:System.Windows.Controls.MediaElement> 에 포함 된 실제 공간을 차지 하지 것입니다는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 경우가 아니면는 <xref:System.Windows.FrameworkElement.Width%2A> 또는 <xref:System.Windows.FrameworkElement.Height%2A> 속성이 설정 됩니다.  
  
 모두 설정 된 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성 미디어에 대해 제공 된 영역을 채우는 스트레치를 사용 하면는 <xref:System.Windows.Controls.MediaElement>합니다. 하거나 미디어의 원래 가로 세로 비율을 유지 하기 위해는 <xref:System.Windows.FrameworkElement.Width%2A> 또는 <xref:System.Windows.FrameworkElement.Height%2A> 속성 집합 중 하나만 사용 해야 합니다. 모두 설정 된 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성에 적합 하지 않을 수 있는 고정 된 요소 크기를 표시 하는 미디어에 발생 합니다.  
  
 고정 크기 요소를 유지하지 못하게 하기 위해 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 미디어를 미리 받을 수 있습니다. 설정 하 여 이렇게는 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 을 <xref:System.Windows.Controls.MediaState.Play> 또는 <xref:System.Windows.Controls.MediaState.Pause>합니다. 에 <xref:System.Windows.Controls.MediaState.Pause> 상태 이면 미디어를 미리 받고와 첫 번째 프레임을 표시 합니다. 에 <xref:System.Windows.Controls.MediaState.Play> 상태 이면 미디어를 미리 받고 재생을 시작 합니다.  
  
<a name="mediaplayer"></a>   
## <a name="mediaplayer-class"></a>MediaPlayer 클래스  
 여기서는 <xref:System.Windows.Controls.MediaElement> 클래스는 프레임 워크 요소는 <xref:System.Windows.Media.MediaPlayer> 클래스에서 사용할 수 있도록 설계는 <xref:System.Windows.Media.Drawing> 개체입니다. 성능을 향상 시키는 프레임 워크 수준 기능을 무시 하거나 해야 할 때 사용 되는 그리기 개체 <xref:System.Windows.Freezable> 기능입니다. <xref:System.Windows.Media.MediaPlayer> 응용 프로그램에서 미디어 콘텐츠를 제공 하는 동안 이러한 기능을 활용할 수 있습니다. 마찬가지로 <xref:System.Windows.Controls.MediaElement>, <xref:System.Windows.Media.MediaPlayer> 독립적인에서 사용할 수 있습니다 또는 모드 하지만 않습니다 하지 클록가 <xref:System.Windows.Controls.MediaElement> 개체의 언로드 및 상태를 로드 합니다. 재생 컨트롤 복잡도 감소이 <xref:System.Windows.Media.MediaPlayer>합니다.  
  
### <a name="controlling-mediaplayer"></a>MediaPlayer 제어  
 때문에 <xref:System.Windows.Media.MediaPlayer> 는 상태 비저장만 두 가지 미디어 재생을 제어할 수 있습니다.  
  
1.  대화형 컨트롤 메서드. 독립 모드에 있을 때 준비에서 (`null` <xref:System.Windows.Media.MediaPlayer.Clock%2A> 속성).  
  
2.  <xref:System.Windows.Media.MediaClock>. 미디어의 경우에 <xref:System.Windows.Media.MediaPlayer.Clock%2A>합니다.  
  
### <a name="displaying-a-mediaplayer"></a>MediaPlayer 표시  
 기술적으로 <xref:System.Windows.Media.MediaPlayer> 는 물리적 표현이 없기 때문에 표시할 수 없습니다. 그러나에서 미디어를 제공 하 사용할 수는 <xref:System.Windows.Media.Drawing> 를 사용 하는 <xref:System.Windows.Media.VideoDrawing> 클래스입니다. 다음 예제에서는 한 <xref:System.Windows.Media.VideoDrawing> 미디어를 표시 하려면.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 참조는 [그리기 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md) 에 대 한 자세한 내용은 <xref:System.Windows.Media.Drawing> 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.DrawingGroup>  
 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)
