---
title: WPF 브러시 개요
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1ef53da1febd6a49af8404e5889a728a1b7c649b
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="wpf-brushes-overview"></a>WPF 브러시 개요
모든 화면에 표시 되는 브러시 그려 졌 기 때문에 표시 됩니다. 예를 들어, 단추, 텍스트의 전경색 및 도형의 채우기의 배경을 설명 하는 브러시 사용 됩니다. 이 항목으로 그리기의 개념을 소개 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 브러시 및 예제를 제공 합니다. 브러시를 사용하여 간단한 단색부터 복잡한 패턴 및 이미지 집합에 이르는 모든 방식으로 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 개체를 그릴 수 있습니다.  
  
<a name="paintingwithbrush"></a>   
## <a name="painting-with-a-brush"></a>브러시를 사용 하 여 그리기  
 A <xref:System.Windows.Media.Brush> 영역 해당 출력을 "그립니다"입니다. 여러 브러시는 서로 다른 유형의 출력 합니다. 일부 브러시 그라데이션, 패턴, 이미지, 또는 그리기 있는 다른 사용자 단색으로 영역을 그립니다. 다음 그림은 다른 각 예를 보여 줍니다. <xref:System.Windows.Media.Brush> 형식입니다.  
  
 ![브러시 형식](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")  
브러시 예제  
  
 대부분의 시각적 개체를 사용 하면 그려지는 방법을 지정할 수 있습니다. 다음 표에서 몇 가지 일반적인 개체 및 사용할 수 있는 속성 한 <xref:System.Windows.Media.Brush>합니다.  
  
|클래스|브러시 속성|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 다음 섹션에서는 여러 가지 설명 <xref:System.Windows.Media.Brush> 형식 및 각각의 예제를 제공 합니다.  
  
<a name="paintwithsolidcolorbrush"></a>   
## <a name="paint-with-a-solid-color"></a>단색으로 그리기  
 A <xref:System.Windows.Media.SolidColorBrush> 단색으로 영역을 그립니다 <xref:System.Windows.Media.Color>합니다. 다양 한 방법으로 지정 하는 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 의 <xref:System.Windows.Media.SolidColorBrush>: 알파, 빨간색, 파란색 및 녹색 채널을 지정 하거나에서 제공 하는 미리 정의 된 색 중 하나를 사용할 수는 예를 들어는 <xref:System.Windows.Media.Colors> 클래스입니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Media.SolidColorBrush> 을 그리는 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle>합니다. 다음 그림에서는 그린된 사각형을 보여 줍니다.  
  
 ![SolidColorBrush를 사용 하 여 그린 사각형](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")  
SolidColorBrush를 사용 하 여 그린 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Media.SolidColorBrush> 클래스를 참조 하십시오. [단색 및 그라데이션 개요 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)합니다.  
  
<a name="paintwithlineargradientbrush"></a>   
## <a name="paint-with-a-linear-gradient"></a>선형 그라데이션으로 그리기  
 A <xref:System.Windows.Media.LinearGradientBrush> 선형 그라데이션으로 영역을 그립니다. 선형 그라데이션의 그라데이션 축 줄 두 개 이상의 색을 혼합합니다. 사용 하면 <xref:System.Windows.Media.GradientStop> 색을 지정 하는 그라데이션의과 해당 위치 개체입니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Media.LinearGradientBrush> 을 그리는 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle>합니다. 다음 그림에서는 그린된 사각형을 보여 줍니다.  
  
 ![LinearGradientBrush를 사용 하 여 그린 사각형](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")  
LinearGradientBrush를 사용 하 여 그린 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Media.LinearGradientBrush> 클래스를 참조 하십시오. [단색 및 그라데이션 개요 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)합니다.  
  
<a name="paintwithradialgradientbrush"></a>   
## <a name="paint-with-a-radial-gradient"></a>방사형 그라데이션으로 그리기  
 A <xref:System.Windows.Media.RadialGradientBrush> 방사형 그라데이션으로 영역을 그립니다. 방사형 그라데이션에서 원을 두 개 이상의 색을 혼합합니다. 와 마찬가지로 <xref:System.Windows.Media.LinearGradientBrush> 사용 클래스 <xref:System.Windows.Media.GradientStop> 색을 지정 하는 그라데이션의과 해당 위치 개체입니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Media.RadialGradientBrush> 을 그리는 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle>합니다. 다음 그림에서는 그린된 사각형을 보여 줍니다.  
  
 ![RadialGradientBrush를 사용 하 여 그린 사각형](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")  
RadialGradientBrush를 사용 하 여 그린 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Media.RadialGradientBrush> 클래스를 참조 하십시오. [단색 및 그라데이션 개요 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)합니다.  
  
<a name="paintwithimage"></a>   
## <a name="paint-with-an-image"></a>이미지 그리기  
 <xref:System.Windows.Media.ImageBrush> 영역을 그리며는 <xref:System.Windows.Media.ImageSource>합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.ImageBrush> 을 그리는 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle>합니다. 다음 그림에서는 그린된 사각형을 보여 줍니다.  
  
 ![ImageBrush로 그린 사각형](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")  
이미지를 사용 하 여 그린 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Media.ImageBrush> 클래스를 참조 하십시오. [이미지, 그리기, 및 시각적 개체를 사용 하 여 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)합니다.  
  
<a name="paintwithdrawing"></a>   
## <a name="paint-with-a-drawing"></a>그리기로 그리기  
 A <xref:System.Windows.Media.DrawingBrush> 영역을 그리며는 <xref:System.Windows.Media.Drawing>합니다. A <xref:System.Windows.Media.Drawing> 도형, 이미지, 텍스트 및 미디어에 포함 될 수 있습니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Media.DrawingBrush> 을 그리는 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle>합니다. 다음 그림에서는 그린된 사각형을 보여 줍니다.  
  
 ![DrawingBrush를 사용 하 여 그린 사각형](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")  
DrawingBrush를 사용 하 여 그린 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Media.DrawingBrush> 클래스를 참조 하십시오. [이미지, 그리기, 및 시각적 개체를 사용 하 여 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)합니다.  
  
<a name="paintwithvisual"></a>   
## <a name="paint-with-a-visual"></a>시각적 표시로 그리기  
 A <xref:System.Windows.Media.VisualBrush> 영역을 그리며는 <xref:System.Windows.Media.Visual> 개체입니다. 시각적 개체의 예로 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Page>, 및 <xref:System.Windows.Controls.MediaElement>합니다. A <xref:System.Windows.Media.VisualBrush> ; 다른 영역으로 응용 프로그램의 한 부분에서 콘텐츠 프로젝션에 하면 반사 효과 만들고 화면의 일부를 확대 하는 데 매우 유용 합니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Media.VisualBrush> 을 그리는 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle>합니다. 다음 그림에서는 그린된 사각형을 보여 줍니다.  
  
 ![VisualBrush를 사용 하 여 그린 사각형](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")  
VisualBrush를 사용 하 여 그린 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Media.VisualBrush> 클래스를 참조 하십시오. [이미지, 그리기, 및 시각적 개체를 사용 하 여 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)합니다.  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## <a name="paint-using-predefined-and-system-brushes"></a>미리 정의 된 및 시스템 브러시를 사용 하 여 그리기  
 Windows Presentation Foundation (WPF) 편의 위해 미리 정의 된 집합 및 시스템 개체를 그리는 데 사용할 수 있는 브러시를 제공 합니다.  
  
-   사용 가능한 미리 정의 된 브러시의 목록에 대 한 참조는 <xref:System.Windows.Media.Brushes> 클래스입니다. 미리 정의 된 브러시를 사용 하는 방법을 보여 주는 예제를 참조 하십시오. [를 단색으로 영역 그리기](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-solid-color.md)합니다.  
  
-   사용 가능한 시스템 브러시의 목록에 대 한 참조는 <xref:System.Windows.SystemColors> 클래스입니다. 예를 들어 참조 [시스템 브러시로 영역 그리기](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)합니다.  
  
<a name="commonbrushfeatures"></a>   
## <a name="common-brush-features"></a>일반적인 브러시 기능  
 <xref:System.Windows.Media.Brush> 개체를 제공는 <xref:System.Windows.Media.Brush.Opacity%2A> 투명 하 게 또는 반투명 브러시를 만드는 데 사용할 수 있는 속성입니다. <xref:System.Windows.Media.Brush.Opacity%2A> 값이 0 이면 브러시를 하는 동안 완전히 투명 한 <xref:System.Windows.Media.Brush.Opacity%2A> 값이 1 이면 브러시가 완전히 불투명 합니다. 다음 예제에서는 <xref:System.Windows.Media.Brush.Opacity%2A> 속성을 한 <xref:System.Windows.Media.SolidColorBrush> 25%로 만듭니다.  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 부분적으로 투명 한 색을 포함 하는 브러시, 색의 불투명도 값 브러시의 곱셈 불투명도 값으로 결합 되어 합니다. 예를 들어 브러시 불투명도 값이 0.5이 많고 브러시에 사용 되는 색도 불투명도 값이 0.5, 출력 색의 불투명도 값 0.25 합니다.  
  
> [!NOTE]
>  것이 더 효율적 사용 하 여 전체 요소의 불투명도 변경 하는 것 보다 브러시 불투명도 값을 변경 하려면 해당 <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType> 속성입니다.  
  
 회전, 크기 조정, 기울이기 및 브러시의 내용을 사용 하 여 번역할 수 있습니다는 <xref:System.Windows.Media.Brush.Transform%2A> 또는 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성입니다. 자세한 내용은 참조 [브러시 변환 개요](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)합니다.  
  
 되기 때문에 <xref:System.Windows.Media.Animation.Animatable> 개체 <xref:System.Windows.Media.Brush> 개체에 애니메이션을 적용할 수 있습니다. 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하세요.  
  
<a name="freezable_features"></a>   
### <a name="freezable-features"></a>Freezable 기능  
 상속 되므로 <xref:System.Windows.Freezable> 클래스는 <xref:System.Windows.Media.Brush> 클래스는 여러 가지 특수 기능을 제공: <xref:System.Windows.Media.Brush> 로 개체를 선언할 수 있습니다 [리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md), 여러 개체 간에 공유 및 복제 합니다. 또한 모든는 <xref:System.Windows.Media.Brush> 제외한 형식 <xref:System.Windows.Media.VisualBrush> 성능 향상을 위해 읽기 전용으로 만들 수 있으며 가집니다.  
  
 제공 하는 다른 기능에 대 한 자세한 내용은 <xref:System.Windows.Freezable> 개체 참조 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)합니다.  
  
 이유에 대 한 자세한 내용은 <xref:System.Windows.Media.VisualBrush> 개체 수 없으면이 고정 참조는 <xref:System.Windows.Media.VisualBrush> 유형 페이지.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Brush>  
 <xref:System.Windows.Media.Brushes>  
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [브러시 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)  
 [ImageBrush 샘플](http://go.microsoft.com/fwlink/?LinkID=160005)  
 [VisualBrush 샘플](http://go.microsoft.com/fwlink/?LinkID=160049)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/brushes-how-to-topics.md)  
 [기타 성능 권장 사항](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
