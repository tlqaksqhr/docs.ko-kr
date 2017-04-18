---
title: "Drawing 개체 개요 | Microsoft Docs"
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
  - "Drawing 개체"
  - "DrawingGroup 개체"
  - "그리기, 그리기 정보"
  - "GeometryDrawing 개체"
  - "GlyphRunDrawing 개체"
  - "ImageDrawing 개체"
ms.assetid: 9b5ce5c0-e204-4320-a7a8-0b2210d62f88
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Drawing 개체 개요
이 항목에서는 <xref:System.Windows.Media.Drawing> 개체를 소개하고 이 개체를 사용하여 도형, 비트맵, 텍스트 및 미디어를 효율적으로 그리는 방법을 설명합니다.  클립 아트를 만들거나, <xref:System.Windows.Media.DrawingBrush>를 사용하여 그리거나, <xref:System.Windows.Media.Visual> 개체를 사용할 때 <xref:System.Windows.Media.Drawing> 개체를 사용하십시오.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="whatisadrawingsection"></a>   
## Drawing 개체란?  
 <xref:System.Windows.Media.Drawing> 개체는 도형, 비트맵, 비디오 또는 텍스트 줄과 같은 표시 가능한 콘텐츠를 나타냅니다.  그리기 형식이 다르면 나타내는 콘텐츠 형식도 다릅니다.  다음은 여러 그리기 개체 형식을 보여 주는 목록입니다.  
  
-   <xref:System.Windows.Media.GeometryDrawing> \- 도형을 그립니다.  
  
-   <xref:System.Windows.Media.ImageDrawing> \- 이미지를 그립니다.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> \- 텍스트를 그립니다.  
  
-   <xref:System.Windows.Media.VideoDrawing> – 오디오 또는 비디오 파일을 재생합니다.  
  
-   <xref:System.Windows.Media.DrawingGroup> \- 기타 그림을 그립니다.  다른 그리기를 단일 합성 그리기로 결합하려면 그리기 그룹을 사용합니다.  
  
 <xref:System.Windows.Media.Drawing> 개체는 다목적입니다. 즉, 다양한 방식으로 <xref:System.Windows.Media.Drawing> 개체를 사용할 수 있습니다.  
  
-   <xref:System.Windows.Media.DrawingImage> 및 <xref:System.Windows.Controls.Image> 컨트롤을 사용하여 이 개체를 이미지로 표시할 수 있습니다.  
  
-   이 개체를 <xref:System.Windows.Media.DrawingBrush>와 함께 사용하여 <xref:System.Windows.Controls.Page>의 <xref:System.Windows.Controls.Page.Background%2A> 같은 개체를 그릴 수 있습니다.  
  
-   이 개체를 사용하여 <xref:System.Windows.Media.DrawingVisual>의 모양을 설명할 수 있습니다.  
  
-   이 개체를 사용하여 <xref:System.Windows.Media.Visual>의 내용을 열거할 수 있습니다.  
  
 WPF는 도형, 비트맵, 텍스트 및 미디어를 그릴 수 있는 다른 개체 형식을 제공합니다.  예를 들어 <xref:System.Windows.Shapes.Shape> 개체를 사용하여 도형을 그릴 수도 있으며 <xref:System.Windows.Controls.MediaElement> 컨트롤은 응용 프로그램에 비디오를 추가할 수 있는 또 다른 방법을 제공합니다.  그렇다면 <xref:System.Windows.Media.Drawing> 개체를 언제 사용해야 할까요?  프레임워크 수준 기능을 희생하여 성능을 높이거나 <xref:System.Windows.Freezable> 기능이 필요할 때 사용해야 합니다.  <xref:System.Windows.Media.Drawing> 개체는 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md), 입력 및 포커스에 대한 지원이 부족하기 때문에 배경, 클립 아트 그리고 <xref:System.Windows.Media.Visual> 개체가 있는 하위 수준 그리기를 설명하는 데 적합한 성능상의 이점이 제공됩니다.  
  
 <xref:System.Windows.Media.Drawing> 개체는 <xref:System.Windows.Freezable> 형식 개체이기 때문에 여러 가지 특수한 기능을 가집니다. 예를 들어 [리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)로 선언하거나, 여러 개체 간에 공유하거나, 읽기 전용으로 설정하여 성능을 향상할 수 있으며, 복제하거나, 스레드로부터 안전하게 보호할 수 있습니다.  <xref:System.Windows.Freezable> 개체에서 제공하는 여러 기능에 대한 자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
<a name="drawinggeometriessection"></a>   
## 도형 그리기  
 도형을 그리려면 <xref:System.Windows.Media.GeometryDrawing>을 사용하십시오.  기하 도형 그리기의 <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> 속성은 그릴 도형을 설명하고, <xref:System.Windows.Media.GeometryDrawing.Brush%2A> 속성은 도형의 내부를 칠하는 방법을 설명하고, <xref:System.Windows.Media.GeometryDrawing.Pen%2A> 속성은 윤곽을 그리는 방법을 설명합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.GeometryDrawing>을 사용하여 도형을 그립니다.  도형은 <xref:System.Windows.Media.GeometryGroup> 및 두 개의 <xref:System.Windows.Media.EllipseGeometry> 개체로 설명됩니다.  도형의 내부는 <xref:System.Windows.Media.LinearGradientBrush>를 사용하여 칠하고, 윤곽은 <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>을 사용하여 그립니다.  
  
 이 예제는 다음 <xref:System.Windows.Media.GeometryDrawing>을 만듭니다.  
  
 ![타원 두 개의 GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexampleinline)]
 [!code-xml[DrawingMiscSnippets_snip#GeometryDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexampleinline)]  
  
 전체 예제를 보려면 [GeometryDrawing 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-geometrydrawing.md)를 참조하십시오.  
  
 <xref:System.Windows.Media.PathGeometry> 같은 다른 <xref:System.Windows.Media.Geometry> 클래스를 사용하면 곡선 및 원호를 만들어 보다 복잡한 도형을 만들 수 있습니다.  <xref:System.Windows.Media.Geometry> 개체에 대한 자세한 내용은 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Media.Drawing> 개체를 사용하지 않는 도형을 그리는 다른 방법에 대한 자세한 내용은 [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)를 참조하십시오.  
  
<a name="drawingimagessection"></a>   
## 이미지 그리기  
 이미지를 그리려면 <xref:System.Windows.Media.ImageDrawing>을 사용하십시오.  <xref:System.Windows.Media.ImageDrawing> 개체의 <xref:System.Windows.Media.ImageDrawing.ImageSource%2A> 속성은 그릴 이미지를 설명하고, <xref:System.Windows.Media.ImageDrawing.Rect%2A> 속성은 이미지가 그려지는 영역을 정의합니다.  
  
 다음 예제에서는 \(75,75\)에 위치한 100 x 100 [픽셀](GTMT)의 직사각형 안에 이미지를 그립니다.  다음 그림에서는 이 예제에서 만든 <xref:System.Windows.Media.ImageDrawing>을 보여 줍니다.  <xref:System.Windows.Media.ImageDrawing>의 경계를 보여 주기 위해 회색 테두리가 추가되었습니다.  
  
 ![&#40;75,75&#41;에 그려진 100 x 100 ImageDrawing](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-imagedrawing-offset.png "graphicsmm\_simple\_imagedrawing\_offset")  
100 x 100 ImageDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawing100by100inline)]
 [!code-xml[DrawingMiscSnippets_snip#ImageDrawing100by100Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawing100by100inline)]  
  
 이미지에 대한 자세한 내용은 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)를 참조하십시오.  
  
<a name="playmedia"></a>   
## 미디어 재생\(코드 전용\)  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 <xref:System.Windows.Media.VideoDrawing>을 선언할 수는 있지만 코드를 사용해서만 해당 미디어를 로드하고 재생할 수 있습니다.  [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 비디오를 재생하려면 <xref:System.Windows.Controls.MediaElement>를 대신 사용하십시오.  
  
 오디오 또는 비디오 파일을 재생하려면 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer>를 사용합니다.  두 가지 방법으로 미디어를 로드하고 재생할 수 있습니다.  첫 번째 방법은 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing>만 사용하는 것이고, 두 번째 방법은 자체적인 <xref:System.Windows.Media.MediaTimeline>을 만들어서 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing>과 함께 사용하는 것입니다.  
  
> [!NOTE]
>  응용 프로그램으로 미디어를 배포하는 경우 이미지와 달리 미디어 파일은 프로젝트 리소스로 사용할 수 없습니다.  대신 프로젝트 파일에서 미디어 형식을 `Content`로 설정하고 `CopyToOutputDirectory`를 `PreserveNewest` 또는 `Always`로 설정해야 합니다.  
  
 자체적인 <xref:System.Windows.Media.MediaTimeline>을 만들지 않고 미디어를 재생하려면 다음 단계를 수행하십시오.  
  
1.  <xref:System.Windows.Media.MediaPlayer> 개체를 만듭니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline1)]  
  
2.  <xref:System.Windows.Media.MediaPlayer.Open%2A> 메서드를 사용하여 미디어 파일을 로드합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline2)]  
  
3.  <xref:System.Windows.Media.VideoDrawing>을 만듭니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline3)]  
  
4.  <xref:System.Windows.Media.VideoDrawing>의 <xref:System.Windows.Media.VideoDrawing.Rect%2A> 속성을 설정하여 미디어를 그릴 크기와 위치를 지정합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline4)]  
  
5.  직접 만든 <xref:System.Windows.Media.MediaPlayer>를 사용하여 <xref:System.Windows.Media.VideoDrawing>의 <xref:System.Windows.Media.VideoDrawing.Player%2A> 속성을 설정합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline5)]  
  
6.  <xref:System.Windows.Media.MediaPlayer>의 <xref:System.Windows.Media.MediaPlayer.Play%2A> 메서드를 사용하여 미디어 재생을 시작합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline6)]  
  
 다음 예제에서는 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer>를 사용하여 비디오 파일을 한 번 재생합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 미디어에 대한 추가적인 타이밍 제어권을 얻으려면 <xref:System.Windows.Media.MediaTimeline>을 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 개체와 함께 사용하십시오.  <xref:System.Windows.Media.MediaTimeline>을 통해 비디오의 반복 여부를 지정할 수 있습니다.  <xref:System.Windows.Media.MediaTimeline>을 <xref:System.Windows.Media.VideoDrawing>과 함께 사용하려면 다음 단계를 수행하십시오.  
  
1.  <xref:System.Windows.Media.MediaTimeline>을 선언하고 해당 타이밍 동작을 설정합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline1)]  
  
2.  <xref:System.Windows.Media.MediaTimeline>에서 <xref:System.Windows.Media.MediaClock>을 만듭니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline2)]  
  
3.  <xref:System.Windows.Media.MediaPlayer>를 만들고 <xref:System.Windows.Media.MediaClock>을 사용하여 해당 <xref:System.Windows.Media.MediaPlayer.Clock%2A> 속성을 설정합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline3)]  
  
4.  <xref:System.Windows.Media.VideoDrawing>을 만들고 <xref:System.Windows.Media.MediaPlayer>를 <xref:System.Windows.Media.VideoDrawing>의 <xref:System.Windows.Media.VideoDrawing.Player%2A> 속성에 할당합니다.  
  
     [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline4)]  
  
 다음 예제에서는 <xref:System.Windows.Media.MediaTimeline>을 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing>과 함께 사용하여 비디오를 반복 재생합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <xref:System.Windows.Media.MediaTimeline>을 사용할 때는 <xref:System.Windows.Media.MediaClock>의 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 속성에서 반환된 대화형 <xref:System.Windows.Media.Animation.ClockController>를 사용하여 <xref:System.Windows.Media.MediaPlayer>의 대화형 메서드 대신 미디어 재생을 제어합니다.  
  
<a name="drawtext"></a>   
## 텍스트 그리기  
 텍스트를 그리려면 <xref:System.Windows.Media.GlyphRunDrawing> 및 <xref:System.Windows.Media.GlyphRun>을 사용합니다.  다음 예제에서는 <xref:System.Windows.Media.GlyphRunDrawing>을 사용하여 "Hello World" 텍스트를 그립니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GlyphRunDrawingExample.cs#glyphrundrawingexampleinline)]
 [!code-xml[DrawingMiscSnippets_snip#GlyphRunDrawingExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GlyphRunExample.xaml#glyphrundrawingexampleinline)]  
  
 <xref:System.Windows.Media.GlyphRun>은 고정 형식 문서 표시 및 인쇄 시나리오에 사용할 수 있는 하위 수준 개체입니다.  <xref:System.Windows.Controls.Label> 또는 <xref:System.Windows.Controls.TextBlock>을 사용하면 보다 쉽게 텍스트를 화면에 그릴 수 있습니다.  <xref:System.Windows.Media.GlyphRun>에 대한 자세한 내용은 [GlyphRun 개체 및 Glyphs 요소 소개](../../../../docs/framework/wpf/advanced/introduction-to-the-glyphrun-object-and-glyphs-element.md) 개요를 참조하십시오.  
  
<a name="compositedrawingssection"></a>   
## 합성 그리기  
 <xref:System.Windows.Media.DrawingGroup>을 사용하면 여러 그리기를 단일 합성 그리기로 결합할 수 있습니다.  <xref:System.Windows.Media.DrawingGroup>을 사용하면 도형, 이미지 및 텍스트를 단일 <xref:System.Windows.Media.Drawing> 개체로 결합할 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingGroup>을 사용하여 두 개의 <xref:System.Windows.Media.GeometryDrawing> 개체와 <xref:System.Windows.Media.ImageDrawing> 개체를 결합합니다.  이 예제의 결과는 다음과 같습니다.  
  
 ![여러 개의 그리기가 있는 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.png "graphicsmm\_simple")  
합성 그리기  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <xref:System.Windows.Media.DrawingGroup>을 사용하여 해당 콘텐츠에 불투명 마스크, 변환, 비트맵 효과 및 기타 작업을 적용할 수도 있습니다.  <xref:System.Windows.Media.DrawingGroup> 작업은 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> 및 <xref:System.Windows.Media.DrawingGroup.Transform%2A>의 순서로 적용됩니다.  
  
 다음 그림에서는 <xref:System.Windows.Media.DrawingGroup> 작업이 적용되는 순서를 보여 줍니다.  
  
 ![DrawingGroup 작업의 순서](../../../../docs/framework/wpf/graphics-multimedia/media/graphcismm-drawinggroup-order.png "graphcismm\_drawinggroup\_order")  
DrawingGroup 작업의 순서  
  
 다음 표에서는 <xref:System.Windows.Media.DrawingGroup> 개체의 콘텐츠를 조작하는 데 사용할 수 있는 속성에 대해 설명합니다.  
  
|Property|설명|그림|  
|--------------|--------|--------|  
|<xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>|<xref:System.Windows.Media.DrawingGroup> 콘텐츠에서 선택한 부분의 불투명도를 변경합니다.  예제를 보려면 [How to: Control the Opacity of a Drawing](http://msdn.microsoft.com/ko-kr/68580652-7d32-4d27-93cc-a5148cf4d5ee)를 참조하십시오.||  
|<xref:System.Windows.Media.DrawingGroup.Opacity%2A>|<xref:System.Windows.Media.DrawingGroup> 콘텐츠의 불투명도를 균일하게 변경합니다.  이 속성을 사용하여 <xref:System.Windows.Media.Drawing>을 투명하게 또는 부분적으로 투명하게 만듭니다.  예제를 보려면 [How to: Apply an Opacity Mask to a Drawing](http://msdn.microsoft.com/ko-kr/d77b420b-9be2-479c-a45e-82f4da30eb9f)을 참조하십시오.||  
|<xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>|<xref:System.Windows.Media.Effects.BitmapEffect>를 <xref:System.Windows.Media.DrawingGroup> 콘텐츠에 적용합니다.  예제를 보려면 [How to: Apply a BitmapEffect to a Drawing](http://msdn.microsoft.com/ko-kr/c5b1de83-8d09-47fb-96db-5f174471f4b5)을 참조하십시오.||  
|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|<xref:System.Windows.Media.DrawingGroup> 콘텐츠를 <xref:System.Windows.Media.Geometry>를 사용하여 설명하는 영역에 클리핑합니다.  예제를 보려면 [How to: Clip a Drawing](http://msdn.microsoft.com/ko-kr/1f7d8a2c-c3c2-42cb-a542-e6796f9fb058)을 참조하십시오.||  
|<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>|지정된 지침에 따라 [장치 독립적 픽셀](GTMT)을 장치 픽셀에 맞춥니다.  이 속성은 매우 세부적인 그래픽이 낮은 DPI 디스플레이에서 선명하게 렌더링되도록 하는 데 유용합니다.  예제를 보려면 [Drawing에 GuidelineSet 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-a-guidelineset-to-a-drawing.md)을 참조하십시오.||  
|<xref:System.Windows.Media.DrawingGroup.Transform%2A>|<xref:System.Windows.Media.DrawingGroup> 콘텐츠를 변환합니다.  예제를 보려면 [How to: Apply a Transform to a Drawing](http://msdn.microsoft.com/ko-kr/0d525f2b-682d-4d67-9660-cf46929fbabd)을 참조하십시오.||  
  
<a name="usingimagedrawing"></a>   
## 그리기를 이미지로 표시  
 <xref:System.Windows.Controls.Image> 컨트롤을 사용하여 <xref:System.Windows.Media.Drawing>을 표시하려면 <xref:System.Windows.Media.DrawingImage>를 <xref:System.Windows.Controls.Image> 컨트롤의 <xref:System.Windows.Controls.Image.Source%2A>로 사용하고 <xref:System.Windows.Media.DrawingImage> 개체의 <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=fullName> 속성을 표시할 그리기로 설정하십시오.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingImage> 및 <xref:System.Windows.Controls.Image> 컨트롤을 사용하여 <xref:System.Windows.Media.GeometryDrawing>을 표시합니다.  이 예제의 결과는 다음과 같습니다.  
  
 ![타원 두 개의 GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
<a name="renderingwithdrawingbrushsection"></a>   
## 그림으로 개체 그리기  
 <xref:System.Windows.Media.DrawingBrush>는 그리기 개체로 영역을 그리는 브러시 유형입니다.  이를 사용하여 그림으로 모든 그래픽 요소를 그릴 수 있습니다.  <xref:System.Windows.Media.DrawingBrush>의 <xref:System.Windows.Media.Drawing> 속성은 해당 <xref:System.Windows.Media.DrawingBrush.Drawing%2A>을 설명합니다.  <xref:System.Windows.Media.DrawingBrush>를 사용하여 <xref:System.Windows.Media.Drawing>을 렌더링하려면 브러시의 <xref:System.Windows.Media.Drawing> 속성을 사용하여 이를 브러시에 추가하고 브러시를 사용하여 컨트롤 또는 패널 같은 그래픽 개체를 그리십시오.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingBrush>를 사용하여 <xref:System.Windows.Media.GeometryDrawing>에서 만든 패턴으로 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.Shapes.Shape.Fill%2A>을 그립니다.  이 예제의 결과는 다음과 같습니다.  
  
 ![바둑판식으로 배열된 DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-geometrydrawing.png "graphicsmm\_drawingbrush\_geometrydrawing")  
DrawingBrush와 함께 사용된 GeometryDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 <xref:System.Windows.Media.DrawingBrush> 클래스는 해당 콘텐츠를 늘이고 바둑판식으로 배열하는 다양한 옵션을 제공합니다.  <xref:System.Windows.Media.DrawingBrush>에 대한 자세한 내용은 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md) 개요를 참조하십시오.  
  
<a name="renderingwithvisualsection"></a>   
## Visual로 그리기 렌더링  
 <xref:System.Windows.Media.DrawingVisual>은 그리기를 렌더링하도록 디자인된 시각적 개체 형식입니다.  시각적 계층에서 직접 작업하는 것은 고도의 사용자 지정된 그래픽 환경을 빌드하려는 개발자를 위한 옵션이며 이 개요에 설명되어 있지 않습니다.  자세한 내용은 [DrawingVisual 개체 사용](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md) 개요를 참조하십시오.  
  
<a name="drawingcontextobjects"></a>   
## DrawingContext 개체  
 <xref:System.Windows.Media.DrawingContext> 클래스를 사용하면 <xref:System.Windows.Media.Visual> 또는 <xref:System.Windows.Media.Drawing>에 시각적 콘텐츠를 넣을 수 있습니다.  다수의 이러한 하위 수준 그래픽 개체는 그래픽 콘텐츠를 매우 효율적으로 설명하는 <xref:System.Windows.Media.DrawingContext>를 사용합니다.  
  
 <xref:System.Windows.Media.DrawingContext> 그리기 메서드와 <xref:System.Drawing.Graphics?displayProperty=fullName> 형식의 그리기 메서드는 비슷해 보이지만 실제로는 매우 다릅니다.  <xref:System.Windows.Media.DrawingContext>는 유지 모드 그래픽 시스템과 함께 사용되는 반면 <xref:System.Drawing.Graphics?displayProperty=fullName> 형식은 직접 실행 모드 그래픽 시스템과 함께 사용됩니다.  <xref:System.Windows.Media.DrawingContext> 개체의 그리기 명령을 사용할 때는 화면에 실시간으로 그려지는 것이 아니라 실제로는 그래픽 시스템에서 나중에 사용될 렌더링 명령 집합이 저장됩니다. 단, 정확한 저장 메커니즘은 <xref:System.Windows.Media.DrawingContext>를 제공하는 개체의 형식에 따라 달라집니다.  [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 그래픽 시스템의 작동 방식에 대한 자세한 내용은 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Media.DrawingContext>는 직접 인스턴스화할 수 없지만 <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=fullName> 및 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=fullName>과 같은 특정 메서드에서 그리기 컨텍스트를 가져올 수 있습니다.  
  
<a name="enumeratevisualcontents"></a>   
## Visual의 콘텐츠 열거  
 기타 다른 용도와 더불어 <xref:System.Windows.Media.Drawing> 개체는 <xref:System.Windows.Media.Visual>의 콘텐츠를 열거하기 위한 개체 모델을 제공합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 메서드를 사용하여 <xref:System.Windows.Media.Visual>의 <xref:System.Windows.Media.DrawingGroup> 값을 검색하고 이를 열거합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## 참고 항목  
 <xref:System.Windows.Media.Drawing>   
 <xref:System.Windows.Media.DrawingGroup>   
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/drawings-how-to-topics.md)