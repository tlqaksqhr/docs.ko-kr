---
title: 브러시 변환 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], transformation properties
- properties [WPF], transformation
- transformation properties of brushes [WPF]
ms.assetid: 8b9bfc09-12fd-4cd5-b445-99949f27bc39
ms.openlocfilehash: 84a92ef8cab58f6362668cef3274edffa044e1b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557656"
---
# <a name="brush-transformation-overview"></a>브러시 변환 개요
두 변환 속성을 제공 하는 브러시 클래스: <xref:System.Windows.Media.Brush.Transform%2A> 및 <xref:System.Windows.Media.Brush.RelativeTransform%2A>합니다. 이러한 속성을 사용하여 브러시의 콘텐츠를 회전, 비율 크기 조정, 기울이기 및 변환할 수 있습니다. 이 항목에서는 이러한 두 속성 간의 차이점을 설명하고 사용 예제를 제공합니다.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>전제 조건  
 이 항목을 이해하려면 변환하는 브러시의 기능을 이해해야 합니다. 에 대 한 <xref:System.Windows.Media.LinearGradientBrush> 및 <xref:System.Windows.Media.RadialGradientBrush>, 참조는 [단색 및 그라데이션 개요 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)합니다. 에 대 한 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush>, 또는 <xref:System.Windows.Media.VisualBrush>, 참조 [이미지, 그리기, 및 시각적 개체를 사용 하 여 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)합니다. [변환 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)에 설명된 2D 변환에도 익숙해야 합니다.  
  
<a name="transformversusrelativetransform"></a>   
## <a name="differences-between-the-transform-and-relativetransform-properties"></a>Transform 및 RelativeTransform 속성 간 차이점  
 브러시의 변환을 적용 하는 경우 <xref:System.Windows.Media.Brush.Transform%2A> 중심을 관통 하는 방법에 대 한 브러시 내용을 변환 하려는 경우 그려지는 영역 크기를 파악 해야 하는 속성입니다. 그려지는 영역의 장치 독립적 픽셀 크기를 너비 200, 높이 150으로 가정합니다.  사용 하는 경우는 <xref:System.Windows.Media.RotateTransform> 가운데를 중심으로 45도 출력 브러시를 회전 하려면, 지정는 <xref:System.Windows.Media.RotateTransform> 는 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 100 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 75입니다.  
  
 브러시의 변환을 적용 하는 경우 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성을 출력 그려지는 영역에 매핑된 전에 해당 변환이 브러시에 적용 합니다. 다음 목록에서는 브러시 콘텐츠가 처리되고 변환되는 순서를 보여 줍니다.  
  
1.  브러시의 콘텐츠를 처리합니다. 에 대 한 한 <xref:System.Windows.Media.GradientBrush>, 즉, 그라데이션 영역을 결정 합니다. 에 대 한는 <xref:System.Windows.Media.TileBrush>, <xref:System.Windows.Media.TileBrush.Viewbox%2A> 매핑되는 <xref:System.Windows.Media.TileBrush.Viewport%2A>합니다. 이것이 브러시의 출력이 됩니다.  
  
2.  브러시의 출력을 1 x 1 변환 사각형에 프로젝션합니다.  
  
3.  브러시의 적용 <xref:System.Windows.Media.Brush.RelativeTransform%2A>, 있는 경우.  
  
4.  변환된 출력을 그릴 영역에 프로젝션합니다.  
  
5.  브러시의 적용 <xref:System.Windows.Media.Transform>, 있는 경우.  
  
 때문에 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 브러시의 출력이 변환 중심 1 x 1 사각형에 매핑되고 오프셋된 값이 상대 것으로 표시 하는 동안 적용 됩니다. 예를 들어, 사용 하는 경우는 <xref:System.Windows.Media.RotateTransform> 가운데를 중심으로 45도 출력 브러시를 회전 하려면, 지정는 <xref:System.Windows.Media.RotateTransform> 는 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 0.5 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 0.5입니다.  
  
 다음 그림으로 사용 하 여 45도 회전 된 여러 브러시의 출력이 나와 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 및 <xref:System.Windows.Media.Brush.Transform%2A> 속성입니다.  
  
 ![RelativeTransform 및 Transform 속성](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm_brushrelativetransform_transform_small")  
  
<a name="relativetransformandtilebrush"></a>   
## <a name="using-relativetransform-with-a-tilebrush"></a>TileBrush에서 RelativeTransform 사용  
 타일 브러시 다른 브러시 보다 더 복잡 한 이므로, 적용 한 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 하나에 예기치 않은 결과가 발생할 수 있습니다. 예를 들어 다음 이미지를 살펴보세요.  
  
 ![소스 이미지](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-1-original-image.jpg "graphicsmm_reltransform_1_original_image")  
  
 다음 예제에서는 <xref:System.Windows.Media.ImageBrush> 이전 이미지와 사각형 영역을 그리는 데 합니다. 적용 되는 <xref:System.Windows.Media.RotateTransform> 에 <xref:System.Windows.Media.ImageBrush> 개체의 <xref:System.Windows.Media.Brush.RelativeTransform%2A> , 속성을 설정 해당 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 <xref:System.Windows.Media.Stretch.UniformToFill>, 완전히 사각형을 채우는 데 늘 이미지의 가로 세로 비율을 유지 해야 하 합니다.  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
 ![변환된 출력](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-6-output.png "graphicsmm_reltransform_6_output")  
  
 이미지가 왜곡, 경우에 확인 브러시의 <xref:System.Windows.Media.TileBrush.Stretch%2A> 로 설정 된 <xref:System.Windows.Media.Stretch.UniformToFill>합니다. 브러시의 후 상대적 변형 적용 되기 때문에 이것이 <xref:System.Windows.Media.TileBrush.Viewbox%2A> 에 매핑된 해당 <xref:System.Windows.Media.TileBrush.Viewport%2A>합니다. 다음 목록에서는 프로세스의 각 단계를 설명합니다.  
  
1.  브러시의 내용을 프로젝트 (<xref:System.Windows.Media.TileBrush.Viewbox%2A>) 기본 바둑판 (<xref:System.Windows.Media.TileBrush.Viewport%2A>) 브러시를 사용 하 여 <xref:System.Windows.Media.TileBrush.Stretch%2A> 설정 합니다.  
  
     ![Viewbox를 뷰포트에 맞게 늘이기](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm_reltransform_2_viewbox_to_viewport")  
  
2.  기본 타일을 1 x 1 변환 사각형에 프로젝션합니다.  
  
     ![뷰포트를 변환 사각형에 매핑](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm_reltransform_3_output_to_transform")  
  
3.  적용 된 <xref:System.Windows.Media.RotateTransform>합니다.  
  
     ![상대 변환 적용](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm_reltransform_4_transform_rotate")  
  
4.  변환된 기본 타일을 그릴 영역에 프로젝션합니다.  
  
     ![변환된 브러시를 출력 영역으로 프로젝션](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm_reltransform_5_transform_to_output")  
  
<a name="rotateexample"></a>   
## <a name="example-rotate-an-imagebrush-45-degrees"></a>예제: ImageBrush를 45도 회전  
 다음 예제에서는 적용 한 <xref:System.Windows.Media.RotateTransform> 에 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성의는 <xref:System.Windows.Media.ImageBrush>합니다. <xref:System.Windows.Media.RotateTransform> 개체의 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성이 모두 설정 0.5로 내용 중심의 상대 좌표를 가리킵니다. 결과적으로 브러시 콘텐츠는 중심을 기준으로 회전합니다.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 다음 예제에서는 적용 됩니다. 한 <xref:System.Windows.Media.RotateTransform> 에 <xref:System.Windows.Media.ImageBrush>, 하지만 사용 하 여는 <xref:System.Windows.Media.Brush.Transform%2A> 속성 대신는 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성입니다. 회전의 중심을 브러시는 <xref:System.Windows.Media.RotateTransform> 개체의 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 절대 좌표를 설정 해야 합니다. 브러시에 의해 그려지는 사각형은 175 x 90 픽셀이기 때문에 중심점은 (87.5, 45)입니다.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 다음 그림과 브러시에 적용 된 변환으로 변환 하지 않고는 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성에 적용 된 변환 하 고는 <xref:System.Windows.Media.Brush.Transform%2A> 속성입니다.  
  
 ![Brush RelativeTransform 및 Transform 설정](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
 이 예제는 더 큰 샘플의 일부입니다. 전체 샘플을 보려면 [브러시 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)을 참조하세요. 브러시에 대한 자세한 내용은 [WPF 브러시 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Brush.Transform%2A>  
 <xref:System.Windows.Media.Brush.RelativeTransform%2A>  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.Brush>  
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
