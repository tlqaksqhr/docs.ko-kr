---
title: "이미지, 그림 및 시각적 표시로 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- painting [WPF], with images
- painting with visuals [WPF]
- brushes [WPF], painting with images
- brushes [WPF], painting with visuals
ms.assetid: 779aac3f-8d41-49d8-8130-768244aa2240
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 01939eb8735e6764e0f0cba811091c7fdbd6797f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="painting-with-images-drawings-and-visuals"></a>이미지, 그림 및 시각적 표시로 그리기
이 항목에서는 사용 하는 방법을 설명 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, 및 <xref:System.Windows.Media.VisualBrush> 이미지를 영역을 그리는 개체는 <xref:System.Windows.Media.Drawing>, 또는 <xref:System.Windows.Media.Visual>합니다.  
    
  
<a name="prereqs"></a>   
## <a name="prerequisites"></a>필수 구성 요소  
 이 항목을 이해하려면 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 제공하는 다양한 형식의 브러시와 해당 기본 기능에 대해 잘 알고 있어야 합니다. 소개 내용을 보려면 [WPF 브러시 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md)를 참조하세요.  
  
<a name="image"></a>   
## <a name="paint-an-area-with-an-image"></a>이미지로 영역 그리기  
 <xref:System.Windows.Media.ImageBrush> 영역을 그리며는 <xref:System.Windows.Media.ImageSource>합니다. 가장 일반적인 유형의 <xref:System.Windows.Media.ImageSource> 를 사용 하는 <xref:System.Windows.Media.ImageBrush> 는 <xref:System.Windows.Media.Imaging.BitmapImage>, 비트맵 그래픽을 설명 하는 합니다. 사용할 수는 <xref:System.Windows.Media.DrawingImage> 사용 하 여 그릴는 <xref:System.Windows.Media.Drawing> 하지만 개체를 사용 하는 편이 <xref:System.Windows.Media.DrawingBrush> 대신 합니다. 에 대 한 자세한 내용은 <xref:System.Windows.Media.ImageSource> 개체 참조는 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)합니다.  
  
 으로 그리려면는 <xref:System.Windows.Media.ImageBrush>을 만듭니다는 <xref:System.Windows.Media.Imaging.BitmapImage> 비트맵 콘텐츠를 로드 하는 데 사용 합니다. 다음을 사용 하 여는 <xref:System.Windows.Media.Imaging.BitmapImage> 설정 하는 <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 의 속성은 <xref:System.Windows.Media.ImageBrush>합니다. 마지막으로 적용 된 <xref:System.Windows.Media.ImageBrush> 그리려고 할 개체에 있습니다.  [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 설정할 수도 있습니다는 <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 속성은 <xref:System.Windows.Media.ImageBrush> 로드할 이미지의 경로 사용 합니다.  
  
 모든 <xref:System.Windows.Media.Brush> 개체는 <xref:System.Windows.Media.ImageBrush> 셰이프, 패널, 컨트롤 및 텍스트와 같은 개체를 그리는 데 사용할 수 있습니다. 다음 그림에 나와 있는 얻을 수 있는 몇 가지 효과 <xref:System.Windows.Media.ImageBrush>합니다.  
  
 ![ImageBrush 출력 예제](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
ImageBrush로 그린 개체  
  
 기본적으로는 <xref:System.Windows.Media.ImageBrush> 까지 확장 되 면 완전히 영역을 채우도록 이미지를 그리고, 그려지는 영역 이미지 보다 다른 가로 세로 비율에 이미지 왜곡 될 수 있습니다. 변경 하 여이 동작을 변경할 수는 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성의 기본값에서 <xref:System.Windows.Media.Stretch.Fill> 를 <xref:System.Windows.Media.Stretch.None>, <xref:System.Windows.Media.Stretch.Uniform>, 또는 <xref:System.Windows.Media.Stretch.UniformToFill>합니다. 때문에 <xref:System.Windows.Media.ImageBrush> 의 형식인 <xref:System.Windows.Media.TileBrush>, 이미지 브러시 출력 영역을 채우는 방법을 정확 하 게 지정 하 고 패턴을 만들 수도 수 있습니다. 고급 항목에 대 한 자세한 내용은 <xref:System.Windows.Media.TileBrush> 기능 참조는 [TileBrush 개요](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)합니다.  
  
<a name="fillingpanelwithimage"></a>   
## <a name="example-paint-an-object-with-a-bitmap-image"></a>예제: 비트맵 이미지로 개체 그리기  
 다음 예제에서는 <xref:System.Windows.Media.ImageBrush> 을 그리는 <xref:System.Windows.Controls.Panel.Background%2A> 의 <xref:System.Windows.Controls.Canvas>합니다.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/ImageBrushExample.xaml#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/ImageBrushExample.cs#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMImageBrushAsCanvasBackgroundExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/imagebrushexample.vb#graphicsmmimagebrushascanvasbackgroundexamplewholepage)]  
  
<a name="drawingbrushintro"></a>   
## <a name="paint-an-area-with-a-drawing"></a>Drawing으로 영역 그리기  
 A <xref:System.Windows.Media.DrawingBrush> 셰이프, 텍스트, 이미지 및 비디오와 영역을 그릴 수 있습니다. 드로잉 브러시 내의 셰이프에 있습니다 자체 그려야 단색, 그라데이션, 이미지, 또는 다른 <xref:System.Windows.Media.DrawingBrush>합니다. 다음 그림에는의 몇 가지 사용 방법을 보여 줍니다.는 <xref:System.Windows.Media.DrawingBrush>합니다.  
  
 ![DrawingBrush 출력 예제](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-drawingbrushexamples.png "wcpsdk_mmgraphics_drawingbrushexamples")  
DrawingBrush로 그린 개체  
  
 A <xref:System.Windows.Media.DrawingBrush> 영역을 그리며는 <xref:System.Windows.Media.Drawing> 개체입니다. A <xref:System.Windows.Media.Drawing> 셰이프, 비트맵, 비디오 또는 텍스트 줄을 등의 내용이 표시 개체에 설명 합니다. 그리기 형식마다 다른 콘텐츠 형식을 설명합니다. 다음은 여러 그리기 개체 형식을 보여 주는 목록입니다.  
  
-   <xref:System.Windows.Media.GeometryDrawing>-도형을 그립니다.  
  
-   <xref:System.Windows.Media.ImageDrawing>– 이미지를 그립니다.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing>-텍스트를 그립니다.  
  
-   <xref:System.Windows.Media.VideoDrawing>-오디오 또는 비디오 파일을 재생 됩니다.  
  
-   <xref:System.Windows.Media.DrawingGroup>-다른 도면을 그립니다. 다른 그리기를 단일 합성 그리기로 결합하려면 그리기 그룹을 사용합니다.  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Media.Drawing> 개체 참조는 [그리기 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)합니다.  
  
 마찬가지로 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> 늘어나 해당 <xref:System.Windows.Media.DrawingBrush.Drawing%2A> 을 출력 영역을 채웁니다. 변경 하 여이 동작을 재정의할 수는 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성에서 기본 설정인 <xref:System.Windows.Media.Stretch.Fill>합니다. 자세한 내용은 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 참조하세요.  
  
<a name="fillingareawithdrawingbrushexample"></a>   
## <a name="example-paint-an-object-with-a-drawing"></a>예제: Drawing으로 개체 그리기  
 다음 예제에서는 3개의 타원 그림으로 개체를 그리는 방법을 보여 줍니다. A <xref:System.Windows.Media.GeometryDrawing> 줄임표에 설명 하는 데 사용 됩니다.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/DrawingBrushExample.xaml#graphicsmmdrawingbrushasbuttonbackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/DrawingBrushExample.cs#graphicsmmdrawingbrushasbuttonbackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMDrawingBrushAsButtonBackgroundExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/drawingbrushexample.vb#graphicsmmdrawingbrushasbuttonbackgroundexample1)]  
  
<a name="visualbrushsection"></a>   
## <a name="paint-an-area-with-a-visual"></a>시각적 표시로 영역 그리기  
 가장 용도가 넓은 함수로 고 모든 브러시의 강력한는 <xref:System.Windows.Media.VisualBrush> 영역을 그리며는 <xref:System.Windows.Media.Visual>합니다. A <xref:System.Windows.Media.Visual> 많은 유용한 그래픽 구성 요소의 상위 항목으로 사용 되는 하위 수준 그래픽 형식입니다. 예를 들어는 <xref:System.Windows.Window>, <xref:System.Windows.FrameworkElement>, 및 <xref:System.Windows.Controls.Control> 클래스는 모든 유형의 <xref:System.Windows.Media.Visual> 개체입니다. 사용 하는 <xref:System.Windows.Media.VisualBrush>, 거의 모든 영역을 적용할 수 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 그래픽 개체입니다.  
  
> [!NOTE]
>  하지만 <xref:System.Windows.Media.VisualBrush> 의 형식인 <xref:System.Windows.Freezable> 개체를 고정할 수 없습니다 (읽기 전용으로 설정) 하면 해당 <xref:System.Windows.Media.VisualBrush.Visual%2A> 속성 이외의 값으로 설정 됩니다 `null`합니다.  
  
 두 가지 방법으로 지정 하는 <xref:System.Windows.Media.VisualBrush.Visual%2A> 의 콘텐츠는 <xref:System.Windows.Media.VisualBrush>합니다.  
  
-   새 <xref:System.Windows.Media.Visual> 설정 하는 데 사용 된 <xref:System.Windows.Media.VisualBrush.Visual%2A> 속성의는 <xref:System.Windows.Media.VisualBrush>합니다. 예제를 보려면 다음에 나오는 [예제: 시각적 개체로 개체 그리기](#examplevisualbrush1)를 참조하세요.  
  
-   기존 사용 하 여 <xref:System.Windows.Media.Visual>, 대상의 복제 이미지를 만듦 <xref:System.Windows.Media.Visual>합니다. 사용할 수 있습니다는 <xref:System.Windows.Media.VisualBrush> 리플렉션 및 확대와 같은 흥미로운 효과 만들 수 있습니다. 예제를 보려면 [예제: 리플렉션 만들기](#examplevisualbrush2) 섹션을 참조하세요.  
  
 정의 하는 경우 새 <xref:System.Windows.Media.VisualBrush.Visual%2A> 에 대 한는 <xref:System.Windows.Media.VisualBrush> 있는지 <xref:System.Windows.Media.Visual> 는 <xref:System.Windows.UIElement> 레이아웃 시스템에서 실행 (예: 패널 또는 컨트롤)는 <xref:System.Windows.UIElement> 및 해당 자식 요소 때는 <xref:System.Windows.Media.VisualBrush.AutoLayoutContent%2A> 속성이로 설정 되어 `true`합니다. 그러나 루트 <xref:System.Windows.UIElement> 시스템의 나머지 부분에서 기본적으로 격리: 스타일 및 외부 레이아웃이이 경계를 인터넷 수 없습니다. 루트의 크기를 명시적으로 지정 해야 따라서 <xref:System.Windows.UIElement>만 부모 이기 때문에 <xref:System.Windows.Media.VisualBrush> 고 따라서 것 없습니다 자동으로 크기를 자체 그려지는 영역에 있습니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 레이아웃에 대한 자세한 내용은 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)을 참조하세요.  
  
 마찬가지로 <xref:System.Windows.Media.ImageBrush> 및 <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.VisualBrush> 늘어나 해당 콘텐츠를 출력 영역을 채웁니다. 변경 하 여이 동작을 재정의할 수는 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성에서 기본 설정인 <xref:System.Windows.Media.Stretch.Fill>합니다. 자세한 내용은 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 참조하세요.  
  
<a name="examplevisualbrush1"></a>   
## <a name="example-paint-an-object-with-a-visual"></a>예제: 시각적 개체로 개체 그리기  
 다음 예제에서는 여러 컨트롤과 패널을 사용해서 사각형을 그립니다.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/VisualBrushExample.xaml#graphicsmmvisualbrushasrectanglebackgroundexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/VisualBrushExample.cs#graphicsmmvisualbrushasrectanglebackgroundexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMVisualBrushAsRectangleBackgroundExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/visualbrushexample.vb#graphicsmmvisualbrushasrectanglebackgroundexample1)]  
  
<a name="examplevisualbrush2"></a>   
## <a name="example-create-a-reflection"></a>예제: 리플렉션 만들기  
 앞의 예제에는 새 만드는 방법을 보여 주었습니다 <xref:System.Windows.Media.Visual> 배경으로 사용 합니다. 사용할 수도 있습니다는 <xref:System.Windows.Media.VisualBrush> 기존의 시각적; 표시 하려면이 기능을 사용 하면 반사 및 확대와 같은 흥미로운 시각적 효과 만들 수 있습니다. 다음 예제에서는 <xref:System.Windows.Media.VisualBrush> 의 반사 만들기를 <xref:System.Windows.Controls.Border> 여러 요소가 들어 있는입니다. 다음 그림에서는 이 예제가 생성하는 출력을 보여 줍니다.  
  
 ![A 시각적 개체를 반영](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
반사된 표시 개체  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 화면의 일부를 확대하는 방법 및 리플렉션을 만드는 방법을 보여 주는 추가 예제를 보려면 [VisualBrush 샘플](http://go.microsoft.com/fwlink/?LinkID=160049)을 참조하세요.  
  
<a name="tilebrush"></a>   
## <a name="tilebrush-features"></a>TileBrush 기능  
 <xref:System.Windows.Media.ImageBrush><xref:System.Windows.Media.DrawingBrush>, 및 <xref:System.Windows.Media.VisualBrush> 유형의 <xref:System.Windows.Media.TileBrush> 개체입니다. <xref:System.Windows.Media.TileBrush>개체가 있는 다양 한 이미지, 그리기, 또는 시각적 표시로 영역을 그리는 방법에 대 한 제어를 제공 합니다. 예를 들어 늘어난 이미지만으로 영역을 그리기보다, 패턴을 만드는 일련의 이미지 타일을 사용하여 영역을 그릴 수 있습니다.  
  
 A <xref:System.Windows.Media.TileBrush> 에 세 가지 기본 구성 요소가: 콘텐츠, 타일 및 출력 영역입니다.  
  
 ![TileBrush 구성 요소](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
단일 타일이 있는 TileBrush의 구성 요소  
  
 ![바둑판식으로 배열 된 TileBrush의 구성 요소](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
여러 타일이 있는 TileBrush의 구성 요소  
  
 바둑판식 배열 기능에 대 한 자세한 내용은 <xref:System.Windows.Media.TileBrush> 개체 참조는 [TileBrush 개요](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.ImageBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 <xref:System.Windows.Media.VisualBrush>  
 <xref:System.Windows.Media.TileBrush>  
 [TileBrush 개요](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)  
 [WPF 브러시 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md)  
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [불투명 마스크 개요](../../../../docs/framework/wpf/graphics-multimedia/opacity-masks-overview.md)  
 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [ImageBrush 샘플](http://go.microsoft.com/fwlink/?LinkID=160005)  
 [VisualBrush 샘플](http://go.microsoft.com/fwlink/?LinkID=160049)
