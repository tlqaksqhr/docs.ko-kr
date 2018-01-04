---
title: "Drawing 개체 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ImageDrawing objects [WPF]
- GlyphRunDrawing objects [WPF]
- GeometryDrawing objects [WPF]
- drawings [WPF], about drawings
- Drawing objects [WPF]
- DrawingGroup objects [WPF]
ms.assetid: 9b5ce5c0-e204-4320-a7a8-0b2210d62f88
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: abdc98a6fbf48a30f2f5702e7c2d78396381de6c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="drawing-objects-overview"></a>Drawing 개체 개요
이 항목에서는 소개 <xref:System.Windows.Media.Drawing> 개체를 효율적으로 셰이프, 비트맵, 텍스트 및 미디어를 그리는 데 사용 하는 방법에 설명 합니다. 사용 하 여 <xref:System.Windows.Media.Drawing> 개체 클립 아트를 만들 때 사용 하 여 페인트는 <xref:System.Windows.Media.DrawingBrush>, 사용 또는 <xref:System.Windows.Media.Visual> 개체입니다.  
  
 
  
<a name="whatisadrawingsection"></a>   
## <a name="what-is-a-drawing-object"></a>그리기 개체란?  
 A <xref:System.Windows.Media.Drawing> 셰이프, 비트맵, 비디오 또는 텍스트 줄을 등의 내용이 표시 개체에 설명 합니다. 그리기 형식마다 다른 콘텐츠 형식을 설명합니다. 다음은 여러 그리기 개체 형식을 보여 주는 목록입니다.  
  
-   <xref:System.Windows.Media.GeometryDrawing>-도형을 그립니다.  
  
-   <xref:System.Windows.Media.ImageDrawing>– 이미지를 그립니다.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing>-텍스트를 그립니다.  
  
-   <xref:System.Windows.Media.VideoDrawing>-오디오 또는 비디오 파일을 재생 됩니다.  
  
-   <xref:System.Windows.Media.DrawingGroup>-다른 도면을 그립니다. 다른 그리기를 단일 합성 그리기로 결합하려면 그리기 그룹을 사용합니다.  
  
 <xref:System.Windows.Media.Drawing>개체는 다목적입니다. 여러 가지 방법으로 사용할 수는 <xref:System.Windows.Media.Drawing> 개체입니다.  
  
-   사용 하 여 이미지 형식으로 표시할 수 있습니다는 <xref:System.Windows.Media.DrawingImage> 및 <xref:System.Windows.Controls.Image> 제어 합니다.  
  
-   함께 사용할 수는 <xref:System.Windows.Media.DrawingBrush> 와 같은 개체를 그리는 데는 <xref:System.Windows.Controls.Page.Background%2A> 의 <xref:System.Windows.Controls.Page>합니다.  
  
-   모양을 설명 하기 위해 사용할 수 있습니다는 <xref:System.Windows.Media.DrawingVisual>합니다.  
  
-   내용을 열거 하는 데 사용할 수는 <xref:System.Windows.Media.Visual>합니다.  
  
 WPF는 도형, 비트맵, 텍스트 및 미디어를 그릴 수 있는 다른 형식의 개체를 제공합니다. 예를 들어 사용할 수도 있습니다 <xref:System.Windows.Shapes.Shape> 도형을 그릴 개체 및 <xref:System.Windows.Controls.MediaElement> 컨트롤 비디오 응용 프로그램에 추가할 수 있습니다. 따라서 언제 사용 하나요 <xref:System.Windows.Media.Drawing> 개체? 성능을 향상 시키는 프레임 워크 수준 기능을 무시 하거나 필요한 경우 <xref:System.Windows.Freezable> 기능입니다. 때문에 <xref:System.Windows.Media.Drawing> 개체에 대 한 지원 부족 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md), 입력 및 초점을 맞추고 성능을 제공 하므로 배경, 클립 아트를 설명 하 고는 데 적합 <xref:System.Windows.Media.Visual> 개체입니다.  
  
 유형이 <xref:System.Windows.Freezable> 개체 <xref:System.Windows.Media.Drawing> 다음을 포함 하는 몇 가지 특수 기능을 사용 하는 개체:로 선언할 수 있습니다 [리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)개선 하기 위해 읽기 전용으로 설정 하는 여러 개체 간에 공유 성능, 복제 및 가집니다. 제공 하는 다른 기능에 대 한 자세한 내용은 <xref:System.Windows.Freezable> 개체 참조는 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)합니다.  
  
<a name="drawinggeometriessection"></a>   
## <a name="draw-a-shape"></a>도형 그리기  
 도형 그리기를 사용 하는 <xref:System.Windows.Media.GeometryDrawing>합니다. 기 하 도형 그리기 <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> 하십시오 그리려는 셰이프를 기술 하는 속성의 <xref:System.Windows.Media.GeometryDrawing.Brush%2A> 도형의 내부를 그리는 방법을, 속성에 설명 및 해당 <xref:System.Windows.Media.GeometryDrawing.Pen%2A> 속성 윤곽선을 그리는 해야 하는 방법에 대해 설명 합니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Media.GeometryDrawing> 도형을 그릴 수 있습니다. 모양을 설명는 <xref:System.Windows.Media.GeometryGroup> 와 두 개의 <xref:System.Windows.Media.EllipseGeometry> 개체입니다. 도형의 내부가 그려지는와 <xref:System.Windows.Media.LinearGradientBrush> 윤곽선을 사용 하 여 그린 및는 <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>합니다.  
  
 이 예제에서는 다음 항목을 만듭니다 <xref:System.Windows.Media.GeometryDrawing>합니다.  
  
 ![개의 GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 전체 예제를 보려면 [GeometryDrawing 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-geometrydrawing.md)를 참조하세요.  
  
 다른 <xref:System.Windows.Media.Geometry> 와 같은 클래스 <xref:System.Windows.Media.PathGeometry> 곡선과 원호를 만들어서 보다 복잡 한 도형을 만들 수 있습니다. 에 대 한 자세한 내용은 <xref:System.Windows.Media.Geometry> 개체 참조는 [기 하 도형 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)합니다.  
  
 다른 방법으로 사용 하지 않는 도형을 그릴 수에 대 한 자세한 내용은 <xref:System.Windows.Media.Drawing> 개체 참조 [Shape 및 기본 그리기 개요 WPF에서에서](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)합니다.  
  
<a name="drawingimagessection"></a>   
## <a name="draw-an-image"></a>이미지 그리기  
 이미지를 그리기 위해 사용 하는 <xref:System.Windows.Media.ImageDrawing>합니다. <xref:System.Windows.Media.ImageDrawing> 개체의 <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> 을 그리려면 이미지를 설명 하는 속성 및 해당 <xref:System.Windows.Media.ImageDrawing.Rect%2A> 속성 이미지를 그릴 영역을 정의 합니다.  
  
 다음 예제에서는 (75,75)에 있는 사각형에 100 x 100픽셀 이미지를 그립니다. 다음 그림에서는 <xref:System.Windows.Media.ImageDrawing> 예제에서 만든 합니다. 회색 테두리의 범위를 표시 하기 위해 추가 되었습니다는 <xref:System.Windows.Media.ImageDrawing>합니다.  
  
 ![100으로 100 ImageDrawing 그립니다 &#40; 75, 75 &#41; ] (../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm_simple_imagedrawing_offset")  
100 x 100 ImageDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 이미지에 대한 자세한 내용은 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)를 참조하세요.  
  
<a name="playmedia"></a>   
## <a name="play-media-code-only"></a>미디어 재생(코드만 해당)  
  
> [!NOTE]
>  선언할 수는 있지만 <xref:System.Windows.Media.VideoDrawing> 에 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]만 할 수 있습니다 로드 하 고 코드를 사용 하 여 해당 미디어를 재생 합니다. 비디오를 재생 하려면 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 사용 하 여 한 <xref:System.Windows.Controls.MediaElement> 대신 합니다.  
  
 오디오 또는 비디오 파일을 재생 하려면 사용 하는 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer>합니다. 미디어를 로드하고 재생하는 방법에는 다음 두 가지가 있습니다. 첫 번째 사용 하는 한 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 고 두 번째 방법은 직접 만들 <xref:System.Windows.Media.MediaTimeline> 를 사용 하는 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing>합니다.  
  
> [!NOTE]
>  응용 프로그램을 사용하여 미디어를 배포하는 경우 이미지의 경우처럼 미디어 파일을 프로젝트 리소스로 사용할 수 없습니다. 대신 프로젝트 파일에서 미디어 형식을 `Content`로 설정하고 `CopyToOutputDirectory`를 `PreserveNewest` 또는 `Always`로 설정해야 합니다.  
  
 직접 만들지 않고 미디어를 재생 하려면 <xref:System.Windows.Media.MediaTimeline>, 다음 단계를 수행 합니다.  
  
1.  <xref:System.Windows.Media.MediaPlayer> 개체를 만듭니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2.  사용 하 여는 <xref:System.Windows.Media.MediaPlayer.Open%2A> 메서드 미디어 파일을 로드 합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3.  <xref:System.Windows.Media.VideoDrawing>를 만듭니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4.  크기와 위치를 설정 하 여 미디어를 그리는 지정는 <xref:System.Windows.Media.VideoDrawing.Rect%2A> 의 속성은 <xref:System.Windows.Media.VideoDrawing>합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5.  설정의 <xref:System.Windows.Media.VideoDrawing.Player%2A> 의 속성은 <xref:System.Windows.Media.VideoDrawing> 와 <xref:System.Windows.Media.MediaPlayer> 사용자가 만든 합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6.  사용 하 여는 <xref:System.Windows.Media.MediaPlayer.Play%2A> 의 메서드는 <xref:System.Windows.Media.MediaPlayer> 미디어 재생을 시작 합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 다음 예제에서는 한 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer> 비디오 파일을 한 번 재생 합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 제어할 추가 타이밍 미디어를 사용 하 여 한 <xref:System.Windows.Media.MediaTimeline> 와 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 개체입니다. <xref:System.Windows.Media.MediaTimeline> 비디오를 반복 해야 하는지 여부를 지정할 수 있습니다. 사용 하는 <xref:System.Windows.Media.MediaTimeline> 와 <xref:System.Windows.Media.VideoDrawing>, 다음 단계를 수행 합니다.  
  
1.  선언 된 <xref:System.Windows.Media.MediaTimeline> 타이밍 동작을 설정 합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2.  만들기는 <xref:System.Windows.Media.MediaClock> 에서 <xref:System.Windows.Media.MediaTimeline>합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3.  만들기는 <xref:System.Windows.Media.MediaPlayer> 사용 하는 <xref:System.Windows.Media.MediaClock> 설정 하려면 해당 <xref:System.Windows.Media.MediaPlayer.Clock%2A> 속성입니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4.  만들기는 <xref:System.Windows.Media.VideoDrawing> 할당는 <xref:System.Windows.Media.MediaPlayer> 에 <xref:System.Windows.Media.VideoDrawing.Player%2A> 의 속성은 <xref:System.Windows.Media.VideoDrawing>합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 다음 예제에서는 <xref:System.Windows.Media.MediaTimeline> 와 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 비디오를 반복 해 서 재생 합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 유의 사용 하는 경우는 <xref:System.Windows.Media.MediaTimeline>, 대화형 사용 하 여 <xref:System.Windows.Media.Animation.ClockController> 에서 반환 된는 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 속성의는 <xref:System.Windows.Media.MediaClock> 재생을 제어 하려면 미디어의 대화형 메서드 대신 <xref:System.Windows.Media.MediaPlayer>합니다.  
  
<a name="drawtext"></a>   
## <a name="draw-text"></a>텍스트 그리기  
 텍스트를 그리는 데 사용 하는 <xref:System.Windows.Media.GlyphRunDrawing> 및 <xref:System.Windows.Media.GlyphRun>합니다. 다음 예제에서는 한 <xref:System.Windows.Media.GlyphRunDrawing> "Hello World" 텍스트를 그리는 합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xaml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 A <xref:System.Windows.Media.GlyphRun> 고정 형식의 문서 표시 및 인쇄 시나리오와 함께 사용할 하위 수준 개체입니다. 화면에 텍스트를 그리는 데 보다 간단한 방법을 사용 하는 것을 <xref:System.Windows.Controls.Label> 또는 <xref:System.Windows.Controls.TextBlock>합니다. 에 대 한 자세한 내용은 <xref:System.Windows.Media.GlyphRun>, 참조는 [glyphrun이 만들어집니다 개체 및 문자 모양 요소 소개](../../../../docs/framework/wpf/advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) 개요입니다.  
  
<a name="compositedrawingssection"></a>   
## <a name="composite-drawings"></a>합성 그리기  
 A <xref:System.Windows.Media.DrawingGroup> 를 단일 복합 그리기로 여러 개의 그리기가 결합할 수 있습니다. 사용 하 여 한 <xref:System.Windows.Media.DrawingGroup>, 도형, 이미지 및 텍스트를 하나로 결합할 수 있습니다 <xref:System.Windows.Media.Drawing> 개체입니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingGroup> 결합할 두 <xref:System.Windows.Media.GeometryDrawing> 개체 및 <xref:System.Windows.Media.ImageDrawing> 개체입니다. 이 예제의 결과는 다음과 같습니다.  
  
 ![여러 개의 그리기가 있는 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")  
합성 그리기  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 A <xref:System.Windows.Media.DrawingGroup> 를 내용 불투명 마스크, 변환, 비트맵 효과 및 기타 작업을 적용할 수 있습니다. <xref:System.Windows.Media.DrawingGroup>작업은 다음과 같은 순서로 적용 됩니다: <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>, 차례로 <xref:System.Windows.Media.DrawingGroup.Transform%2A>합니다.  
  
 다음 그림에서는 순서는 <xref:System.Windows.Media.DrawingGroup> 작업이 적용 됩니다.  
  
 ![DrawingGroup 작업의 순서](../../../../docs/framework/wpf/graphics-multimedia/media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
DrawingGroup 작업의 순서  
  
 다음 표에서 조작 하는 데 사용할 수 속성 설명는 <xref:System.Windows.Media.DrawingGroup> 개체의 콘텐츠입니다.  
  
|속성|설명|그림|  
|--------------|-----------------|------------------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|변경의 선택한 부분이의 불투명도 <xref:System.Windows.Media.DrawingGroup> 내용입니다. 예제를 보려면 [방법: 그리기의 불투명도 제어](http://msdn.microsoft.com/en-us/68580652-7d32-4d27-93cc-a5148cf4d5ee)를 참조하세요.|![불투명도 마스크가 있는 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-opmask.png "graphicsmm_opmask")|  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|불투명도 균일 하 게 변경는 <xref:System.Windows.Media.DrawingGroup> 내용입니다. 이 속성을 사용 하 여 확인 하는 <xref:System.Windows.Media.Drawing> 투명 하 게 또는 부분적으로 투명 합니다. 예제를 보려면 [방법: 도면에 불투명 마스크 적용](http://msdn.microsoft.com/en-us/d77b420b-9be2-479c-a45e-82f4da30eb9f)을 참조하세요.|![여러 불투명도 설정의 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-opacity.png "graphicsmm_opacity")|  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|적용 되는 <xref:System.Windows.Media.Effects.BitmapEffect> 에 <xref:System.Windows.Media.DrawingGroup> 내용을 합니다. 예제를 보려면 [방법: 그리기에 BitmapEffect 적용](http://msdn.microsoft.com/en-us/c5b1de83-8d09-47fb-96db-5f174471f4b5)을 참조하세요.|![BlurBitmapEffect가 적용된 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-bitmap.png "graphicsmm_bitmap")|  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|클립은 <xref:System.Windows.Media.DrawingGroup> 사용 하 여을 설명 영역에는 콘텐츠는 <xref:System.Windows.Media.Geometry>합니다. 예제를 보려면 [방법: 그림 자르기](http://msdn.microsoft.com/en-us/1f7d8a2c-c3c2-42cb-a542-e6796f9fb058)를 참조하세요.|![정의된 클립 영역이 있는 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clipgeom.png "graphicsmm_clipgeom")|  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|지정된 지침에 따라 장치 독립적 픽셀을 장치 픽셀에 맞춥니다. 이 속성은 매우 세부적인 그래픽이 낮은 DPI 디스플레이에 선명하게 렌더링되도록 하는 데 유용합니다. 예제를 보려면 [Drawing에 GuidelineSet 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-a-guidelineset-to-a-drawing.md)을 참조하세요.|![GuidelineSet이 있는 DrawingGroup과 없는 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")|  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|변환 된 <xref:System.Windows.Media.DrawingGroup> 내용입니다. 예제를 보려면 [방법: 그리기에 변환 적용](http://msdn.microsoft.com/en-us/0d525f2b-682d-4d67-9660-cf46929fbabd)을 참조하세요.|![회전된 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rotate.png "graphicsmm_rotate")|  
  
<a name="usingimagedrawing"></a>   
## <a name="display-a-drawing-as-an-image"></a>그리기를 이미지로 표시  
 표시 하는 <xref:System.Windows.Media.Drawing> 와 <xref:System.Windows.Controls.Image> 컨트롤을 사용 하 여는 <xref:System.Windows.Media.DrawingImage> 로 <xref:System.Windows.Controls.Image> 컨트롤의 <xref:System.Windows.Controls.Image.Source%2A> 설정는 <xref:System.Windows.Media.DrawingImage> 개체의 <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> 속성을 표시 하려는 드로잉을 합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingImage> 및 <xref:System.Windows.Controls.Image> 컨트롤을 표시 한 <xref:System.Windows.Media.GeometryDrawing>합니다. 이 예제의 결과는 다음과 같습니다.  
  
 ![개의 GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## <a name="paint-an-object-with-a-drawing"></a>Drawing으로 개체 그리기  
 A <xref:System.Windows.Media.DrawingBrush> 유형 그리기 개체를 사용 하 여 영역을 칠하는 브러시입니다. 그리기 기능으로 거의 모든 그래픽 개체를 그리는 데 사용할 수 있습니다. <xref:System.Windows.Media.Drawing> 속성은 <xref:System.Windows.Media.DrawingBrush> 설명 해당 <xref:System.Windows.Media.DrawingBrush.Drawing%2A>합니다. 렌더링 하는 <xref:System.Windows.Media.Drawing> 와 <xref:System.Windows.Media.DrawingBrush>, 브러시를 사용 하 여 브러시에 추가 <xref:System.Windows.Media.Drawing> 속성 및 사용을 그래픽 칠하는 브러시 패널 또는 컨트롤 같은 개체입니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Media.DrawingBrush> 을 그리는 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle> 에서 만들어진 패턴으로는 <xref:System.Windows.Media.GeometryDrawing>합니다. 이 예제의 결과는 다음과 같습니다.  
  
 ![A: 타일 식 DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm_drawingbrush_geometrydrawing")  
DrawingBrush에 GeometryDrawing 사용  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 <xref:System.Windows.Media.DrawingBrush> 클래스는 다양 한 늘이기 및 해당 콘텐츠를 바둑판식으로 배열에 대 한 옵션을 제공 합니다. 에 대 한 자세한 내용은 <xref:System.Windows.Media.DrawingBrush>, 참조는 [이미지, 그리기, 및 시각적 개체를 사용 하 여 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md) 개요입니다.  
  
<a name="renderingwithvisualsection"></a>   
## <a name="render-a-drawing-with-a-visual"></a>시각적 표시로 그림 렌더링  
 A <xref:System.Windows.Media.DrawingVisual> 그리기를 렌더링 하도록 디자인 된 시각적 개체의 형식입니다. 시각적 계층에서 직접 작업하는 방식은 고도로 사용자 지정된 그래픽 환경을 구축하려는 개발자를 위한 옵션이지만 이 개요에서는 설명되지 않습니다. 자세한 내용은 [DrawingVisual 개체 사용](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)을 참조하세요.  
  
<a name="drawingcontextobjects"></a>   
## <a name="drawingcontext-objects"></a>DrawingContext 개체  
 <xref:System.Windows.Media.DrawingContext> 클래스 채울 수 있습니다는 <xref:System.Windows.Media.Visual> 또는 <xref:System.Windows.Media.Drawing> 시각적 콘텐츠를 사용 합니다. 이러한 많은 하위 그래픽 개체를 사용 하 여 한 <xref:System.Windows.Media.DrawingContext> 그래픽 콘텐츠 매우 효율적으로 설명 하므로 합니다.  
  
 하지만 <xref:System.Windows.Media.DrawingContext> 그리기 메서드 그리기 메서드와 비슷합니다는 <xref:System.Drawing.Graphics?displayProperty=nameWithType> 유형, 것은 실제로 매우 다릅니다. <xref:System.Windows.Media.DrawingContext>유지 모드 그래픽 시스템을 사용 하는 동안는 <xref:System.Drawing.Graphics?displayProperty=nameWithType> 직접 실행 모드 그래픽 시스템 형식이 사용 되었습니다. 사용 하는 경우는 <xref:System.Windows.Media.DrawingContext> 개체의 명령, 실제로 렌더링 명령 집합을 저장 하는 (정확한 저장소 메커니즘을 제공 하는 개체의 형식에 따라 다르지만 <xref:System.Windows.Media.DrawingContext>) 하는 나중에 사용할 그래픽으로; 시스템 개체의 형식에 따라 달라 집니다. [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 그래픽 시스템의 작동 방식에 대한 자세한 내용은 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)를 참조하세요.  
  
 그러나 직접 인스턴스화는 <xref:System.Windows.Media.DrawingContext>; 얻을 수 있습니다, 특정 메서드를 직접와 같은 <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>합니다.  
  
<a name="enumeratevisualcontents"></a>   
## <a name="enumerate-the-contents-of-a-visual"></a>시각적 개체의 콘텐츠 열거  
 기타 다른 용도, <xref:System.Windows.Media.Drawing> 도 개체의 내용을 열거 하기 위한 개체 모델을 제공는 <xref:System.Windows.Media.Visual>합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 를 검색할 메서드는 <xref:System.Windows.Media.DrawingGroup> 값은 <xref:System.Windows.Media.Visual> 고이 열거 합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Drawing>  
 <xref:System.Windows.Media.DrawingGroup>  
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/drawings-how-to-topics.md)
