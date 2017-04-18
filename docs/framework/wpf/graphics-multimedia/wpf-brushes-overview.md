---
title: "WPF 브러시 개요 | Microsoft Docs"
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
  - "브러시, 브러시 정보"
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# WPF 브러시 개요
모든 항목을 화면에서 볼 수 있는 것은 브러시로 그려졌기 때문입니다.  예를 들어 브러시는 단추의 배경, 텍스트의 전경 및 도형의 채우기를 나타나는 데 사용됩니다.  이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 브러시를 사용한 그리기의 개념을 소개하고 예제를 제공합니다.  브러시를 사용하면 간단한 단색부터 복잡한 패턴 및 이미지 집합에 이르기까지 모든 것을 사용하여 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 개체를 그릴 수 있습니다.  
  
<a name="paintingwithbrush"></a>   
## 브러시를 사용하여 그리기  
 <xref:System.Windows.Media.Brush>는 해당 출력으로 영역을 "그립니다".  여러 다른 브러시는 다른 유형의 출력을 가집니다.  일부 브러시는 영역을 단색으로 그리고 일부 브러시는 그라데이션, 패턴, 이미지 또는 그리기를 사용하여 그립니다.  다음 그림은 다른 각 <xref:System.Windows.Media.Brush> 형식의 예제를 보여 줍니다.  
  
 ![브러시 형식](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushtypes.png "graphicsmm\_brushtypes")  
브러시 예제  
  
 대부분의 시각적 개체를 사용하면 그려지는 방법을 지정할 수 있습니다.  다음 표에서는 <xref:System.Windows.Media.Brush>와 함께 사용할 수 있는 몇 가지 일반적인 개체 및 속성이 나열되어 있습니다.  
  
|클래스|브러시 속성|  
|---------|------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 다음 단원에서는 여러 다른 <xref:System.Windows.Media.Brush> 형식에 대해 설명하고 각각의 예제를 제공합니다.  
  
<a name="paintwithsolidcolorbrush"></a>   
## 단색으로 그리기  
 <xref:System.Windows.Media.SolidColorBrush>는 단색 <xref:System.Windows.Media.Color>로 영역을 그립니다.  <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.SolidColorBrush.Color%2A>를 지정하는 다양한 방법이 있습니다. 예를 들어 해당 알파, 빨간색, 파란색 및 녹색 채널을 지정하거나 <xref:System.Windows.Media.Colors> 클래스에 의해 제공된 미리 정의된 색 중 하나를 사용할 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.SolidColorBrush>를 사용하여 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.Shapes.Shape.Fill%2A>을 그립니다.  아래 그림에서는 코드에서 그린 사각형을 보여 줍니다.  
  
 ![SolidColorBrush를 사용하여 그린 사각형](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm\_brush\_ovw\_solidcolorbrush")  
SolidColorBrush를 사용하여 그린 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 <xref:System.Windows.Media.SolidColorBrush> 클래스에 대한 자세한 내용은 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)를 참조하십시오.  
  
<a name="paintwithlineargradientbrush"></a>   
## 선형 그라데이션으로 그리기  
 <xref:System.Windows.Media.LinearGradientBrush>는 선형 그라데이션으로 영역을 그립니다.  선형 그라데이션은 그라데이션 축인 하나의 선을 가로질러 둘 이상의 색을 혼합합니다.  <xref:System.Windows.Media.GradientStop> 개체를 사용하여 그라데이션의 색과 해당 위치를 지정합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.LinearGradientBrush>를 사용하여 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.Shapes.Shape.Fill%2A>을 그립니다.  아래 그림에서는 코드에서 그린 사각형을 보여 줍니다.  
  
 ![LinearGradientBrush를 사용하여 그린 사각형](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-lineargradientbrush.png "graphicsmm\_brush\_ovw\_lineargradientbrush")  
LinearGradientBrush를 사용하여 그린 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 <xref:System.Windows.Media.LinearGradientBrush> 클래스에 대한 자세한 내용은 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)를 참조하십시오.  
  
<a name="paintwithradialgradientbrush"></a>   
## 방사형 그라데이션으로 그리기  
 <xref:System.Windows.Media.RadialGradientBrush>는 방사형 그라데이션으로 영역을 그립니다.  방사형 그라데이션은 원을 가로질러 둘 이상의 색을 혼합합니다.  <xref:System.Windows.Media.LinearGradientBrush> 클래스와 마찬가지로 <xref:System.Windows.Media.GradientStop> 개체를 사용하여 그라데이션의 색과 해당 위치를 지정합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.RadialGradientBrush>를 사용하여 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.Shapes.Shape.Fill%2A>을 그립니다.  아래 그림에서는 코드에서 그린 사각형을 보여 줍니다.  
  
 ![RadialGradientBrush를 사용하여 그린 사각형](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-radialgradientbrush.png "graphicsmm\_brush\_ovw\_radialgradientbrush")  
RadialGradientBrush를 사용하여 그린 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 <xref:System.Windows.Media.RadialGradientBrush> 클래스에 대한 자세한 내용은 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)를 참조하십시오.  
  
<a name="paintwithimage"></a>   
## 이미지로 그리기  
 <xref:System.Windows.Media.ImageBrush>는 <xref:System.Windows.Media.ImageSource>로 영역을 그립니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.ImageBrush>를 사용하여 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.Shapes.Shape.Fill%2A>을 그립니다.  아래 그림에서는 코드에서 그린 사각형을 보여 줍니다.  
  
 ![ImageBrush로 그린 사각형](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-imagebrush.png "graphicsmm\_brush\_ovw\_imagebrush")  
이미지를 사용하여 그린 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 <xref:System.Windows.Media.ImageBrush> 클래스에 대한 자세한 내용은 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)를 참조하십시오.  
  
<a name="paintwithdrawing"></a>   
## 그리기로 그리기  
 <xref:System.Windows.Media.DrawingBrush>는 <xref:System.Windows.Media.Drawing>으로 영역을 그립니다.  <xref:System.Windows.Media.Drawing>은 도형, 이미지, 텍스트 및 미디어를 포함할 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingBrush>를 사용하여 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.Shapes.Shape.Fill%2A>을 그립니다.  아래 그림에서는 코드에서 그린 사각형을 보여 줍니다.  
  
 ![DrawingBrush를 사용하여 그린 사각형](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-drawingbrush.png "graphicsmm\_brush\_ovw\_drawingbrush")  
DrawingBrush를 사용하여 그린 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 <xref:System.Windows.Media.DrawingBrush> 클래스에 대한 자세한 내용은 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)를 참조하십시오.  
  
<a name="paintwithvisual"></a>   
## 시각적 표시로 그리기  
 <xref:System.Windows.Media.VisualBrush>는 <xref:System.Windows.Media.Visual> 개체로 영역을 그립니다.  시각적 표시 개체의 예로는 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Page> 및 <xref:System.Windows.Controls.MediaElement>가 있습니다.  또한 <xref:System.Windows.Media.VisualBrush>를 사용하면 응용 프로그램의 한 부분에서 다른 영역으로 콘텐츠를 투영할 수 있습니다. 이는 반사 효과를 만들고 화면의 일부를 확대하는 데 매우 유용합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.VisualBrush>를 사용하여 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.Shapes.Shape.Fill%2A>을 그립니다.  아래 그림에서는 코드에서 그린 사각형을 보여 줍니다.  
  
 ![VisualBrush를 사용하여 그린 사각형](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brush-ovw-visualbrush.png "graphicsmm\_brush\_ovw\_visualbrush")  
VisualBrush를 사용하여 그린 사각형  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 <xref:System.Windows.Media.VisualBrush> 클래스에 대한 자세한 내용은 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)를 참조하십시오.  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## 미리 정의된 브러시 및 시스템 브러시를 사용하여 그리기  
 편의상 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]는 개체를 그리는 데 사용할 수 있는 미리 정의된 브러시 및 시스템 브러시 집합을 제공합니다.  
  
-   사용 가능한 미리 정의된 브러시 목록은 <xref:System.Windows.Media.Brushes> 클래스를 참조하십시오.  미리 정의된 브러시를 사용하는 방법을 보여 주는 예제를 보려면 [단색으로 영역 그리기](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-solid-color.md)를 참조하십시오.  
  
-   사용 가능한 시스템 브러시 목록은 <xref:System.Windows.SystemColors> 클래스를 참조하십시오.  예제를 보려면 [시스템 브러시로 영역 그리기](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)를 참조하십시오.  
  
<a name="commonbrushfeatures"></a>   
## 일반 브러시 기능  
 <xref:System.Windows.Media.Brush> 개체는 브러시를 투명하게 또는 부분적으로 투명하게 만드는 데 사용할 수 있는 <xref:System.Windows.Media.Brush.Opacity%2A> 속성을 제공합니다.  <xref:System.Windows.Media.Brush.Opacity%2A> 값이 0이면 브러시가 완전히 투명해지고 <xref:System.Windows.Media.Brush.Opacity%2A> 값이 1이면 브러시가 완전히 불투명해집니다.  다음 예제에서는 <xref:System.Windows.Media.Brush.Opacity%2A> 속성을 사용하여 <xref:System.Windows.Media.SolidColorBrush>를 25% 불투명하게 만듭니다.  
  
 [!code-xml[BrushOverviewExamples_snip#OpacityExample1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 브러시에 부분적으로 투명한 색이 포함된 경우 색의 불투명도 값은 브러시의 불투명도 값과의 곱셈으로 결합됩니다.  예를 들어 브러시의 불투명도 값이 0.5이고 브러시에 사용된 색의 불투명도 값이 0.5인 경우 출력 색의 불투명도 값은 0.25입니다.  
  
> [!NOTE]
>  <xref:System.Windows.UIElement.Opacity%2A?displayProperty=fullName> 속성을 사용하여 전체 요소의 불투명도를 변경하는 것보다 브러시의 불투명도 값을 변경하는 것이 효율적입니다.  
  
 해당 <xref:System.Windows.Media.Brush.Transform%2A> 또는 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성을 사용하여 브러시 내용에 대해 회전, 배율 조정, 기울이기 및 변환을 수행할 수 있습니다.  자세한 내용은 [브러시 변환 개요](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Media.Brush> 개체는 <xref:System.Windows.Media.Animation.Animatable> 개체이므로 애니메이션 효과를 줄 수 있습니다.  자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
<a name="freezable_features"></a>   
### Freezable 기능  
 <xref:System.Windows.Freezable> 클래스에서 상속되는 <xref:System.Windows.Media.Brush> 클래스는 몇 가지 특수한 기능을 제공합니다. 예를 들어 <xref:System.Windows.Media.Brush> 개체를 [리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)로 선언하거나, 여러 개체 간에 공유하거나, 복제할 수 있습니다.  또한 <xref:System.Windows.Media.VisualBrush>를 제외한 모든 <xref:System.Windows.Media.Brush> 형식을 읽기 전용으로 만들어 성능을 향상시키고 스레드로부터 안전하게 만들 수 있습니다.  
  
 <xref:System.Windows.Freezable> 개체에서 제공하는 여러 기능에 대한 자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Media.VisualBrush> 개체를 고정할 수 없는 이유에 대한 자세한 내용은 <xref:System.Windows.Media.VisualBrush> 형식 페이지를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Brush>   
 <xref:System.Windows.Media.Brushes>   
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Brushes 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)   
 [ImageBrush 샘플](http://go.microsoft.com/fwlink/?LinkID=160005)   
 [VisualBrush 샘플](http://go.microsoft.com/fwlink/?LinkID=160049)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/brushes-how-to-topics.md)   
 [기타 성능 권장 사항](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)