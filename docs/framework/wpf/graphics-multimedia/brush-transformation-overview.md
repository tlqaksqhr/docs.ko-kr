---
title: "브러시 변환 개요 | Microsoft Docs"
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
  - "브러시, 변환 속성"
  - "속성, 변환"
  - "브러시의 변환 속성"
ms.assetid: 8b9bfc09-12fd-4cd5-b445-99949f27bc39
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 브러시 변환 개요
브러시 클래스에서는 두 개의 변환 속성인 <xref:System.Windows.Media.Brush.Transform%2A> 및 <xref:System.Windows.Media.Brush.RelativeTransform%2A>을 제공합니다.  이 속성을 사용하여 브러시 내용에 대해 회전, 배율 조정, 기울이기 및 변환을 수행할 수 있습니다.  이 항목에서는 이러한 두 속성 간의 차이점에 대해 설명하고 사용 예를 제공합니다.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목을 이해하려면 변환하는 브러시의 기능을 잘 알고 있어야 합니다.  <xref:System.Windows.Media.LinearGradientBrush> 및 <xref:System.Windows.Media.RadialGradientBrush>에 대해서는 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)를 참조하십시오.  <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> 또는 <xref:System.Windows.Media.VisualBrush>에 대해서는 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)를 참조하십시오.  [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)에 설명되어 있는 2D 변환에 대해서도 잘 알고 있어야 합니다.  
  
<a name="transformversusrelativetransform"></a>   
## Transform 속성과 RelativeTransform 속성의 차이점  
 브러시의 <xref:System.Windows.Media.Brush.Transform%2A> 속성에 변환을 적용할 때 중심 점을 기준으로 브러시 내용을 변환하려면 그려지는 영역의 크기를 알고 있어야 합니다.  그려지는 영역이 [장치 독립적 픽셀](GTMT) 단위로 너비 200, 높이 150이라고 가정하십시오.  <xref:System.Windows.Media.RotateTransform>을 사용하여 중심 점을 기준으로 브러시의 출력을 45도 회전한 경우에는 <xref:System.Windows.Media.RotateTransform>의 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 값을 100으로, <xref:System.Windows.Media.RotateTransform.CenterY%2A> 값을 75로 지정한 것입니다.  
  
 브러시의 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성에 변환을 적용할 때 해당 변환은 그려지는 영역에 출력이 매핑되기 전에 브러시에 적용됩니다.  다음 목록에서는 브러시의 내용을 처리하고 변환하는 순서를 설명합니다.  
  
1.  브러시의 내용을 처리합니다.  <xref:System.Windows.Media.GradientBrush>의 경우 그라데이션 영역을 결정하는 것을 의미합니다.  <xref:System.Windows.Media.TileBrush>의 경우 <xref:System.Windows.Media.TileBrush.Viewbox%2A>가 <xref:System.Windows.Media.TileBrush.Viewport%2A>에 매핑됩니다.  이것이 브러시의 출력이 됩니다.  
  
2.  브러시의 출력을 1 x 1 변환 직사각형에 반영합니다.  
  
3.  브러시에 <xref:System.Windows.Media.Brush.RelativeTransform%2A>이 있으면 이를 적용합니다.  
  
4.  변환된 출력을 그릴 영역에 반영합니다.  
  
5.  브러시에 <xref:System.Windows.Media.Transform>이 있으면 이를 적용합니다.  
  
 <xref:System.Windows.Media.Brush.RelativeTransform%2A>은 브러시의 출력이 1 x 1 직사각형에 매핑되어 있는 동안 적용되기 때문에 변환 중앙 및 오프셋 값은 상대적인 것으로 나타납니다.  예를 들어 <xref:System.Windows.Media.RotateTransform>을 사용하여 중심 점을 기준으로 브러시의 출력을 45도 회전한 경우에는 <xref:System.Windows.Media.RotateTransform>의 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 값을 0.5로, <xref:System.Windows.Media.RotateTransform.CenterY%2A> 값을 0.5로 지정한 것입니다.  
  
 다음 그림은 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 및 <xref:System.Windows.Media.Brush.Transform%2A> 속성을 사용하여 45도 회전한 여러 브러시의 출력을 보여 줍니다.  
  
 ![RelativeTransform 및 Transform 속성](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-brushrelativetransform-transform-small.png "graphicsmm\_brushrelativetransform\_transform\_small")  
  
<a name="relativetransformandtilebrush"></a>   
## RelativeTransform과 TileBrush 함께 사용  
 바둑판식 배열 브러시는 다른 브러시보다 더 복잡하기 때문에 <xref:System.Windows.Media.Brush.RelativeTransform%2A>을 적용하면 예상치 못한 결과가 발생할 수 있습니다.  예를 들어 다음 이미지를 보십시오.  
  
 ![소스 이미지](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-1-original-image.png "graphicsmm\_reltransform\_1\_original\_image")  
  
 다음 예제는 <xref:System.Windows.Media.ImageBrush>를 사용하여 이전 이미지를 포함하는 직사각형 영역을 그립니다.  또한 <xref:System.Windows.Media.RotateTransform>을 <xref:System.Windows.Media.ImageBrush> 개체의 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성에 적용하고 해당 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 <xref:System.Windows.Media.Stretch>로 설정합니다. 이렇게 하면 직사각형을 완전히 채우기 위해 이미지를 늘릴 때 이미지의 가로 세로 비율이 유지됩니다.  
  
 [!code-xml[BrushOverviewExamples_snip#GraphicsMMRelativeTransformExample2Inline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/RelativeTransformIllustration.xaml#graphicsmmrelativetransformexample2inline)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
 ![변환된 출력](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-6-output.png "graphicsmm\_reltransform\_6\_output")  
  
 브러시의 <xref:System.Windows.Media.TileBrush.Stretch%2A>가 <xref:System.Windows.Media.Stretch>로 설정되었음에도 불구하고 이미지가 왜곡됩니다.  이것은 브러시의 <xref:System.Windows.Media.TileBrush.Viewbox%2A>가 해당 <xref:System.Windows.Media.TileBrush.Viewport%2A>에 매핑된 후에 상대적 변환이 적용되기 때문입니다.  다음 목록에서는 프로세스의 각 단계에 대해 설명합니다.  
  
1.  브러시의 <xref:System.Windows.Media.TileBrush.Stretch%2A> 설정을 사용하여 브러시의 내용\(<xref:System.Windows.Media.TileBrush.Viewbox%2A>\)을 해당 기본 바둑판식 배열\(<xref:System.Windows.Media.TileBrush.Viewport%2A>\)에 반영합니다.  
  
     ![Viewbox를 뷰포트에 맞게 늘이기](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-2-viewbox-to-viewport.png "graphicsmm\_reltransform\_2\_viewbox\_to\_viewport")  
  
2.  기본 바둑판식 배열을 1 x 1 변환 직사각형에 반영합니다.  
  
     ![뷰포트를 변환 사각형에 매핑](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-3-output-to-transform.png "graphicsmm\_reltransform\_3\_output\_to\_transform")  
  
3.  <xref:System.Windows.Media.RotateTransform>을 적용합니다.  
  
     ![상대 변환 적용](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-4-transform-rotate.png "graphicsmm\_reltransform\_4\_transform\_rotate")  
  
4.  변환된 기본 바둑판식 배열을 그릴 영역에 반영합니다.  
  
     ![변환된 브러시를 출력 영역으로 프로젝션](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-reltransform-5-transform-to-output.png "graphicsmm\_reltransform\_5\_transform\_to\_output")  
  
<a name="rotateexample"></a>   
## 예제: ImageBrush 45도 회전  
 다음 예제에서는 <xref:System.Windows.Media.RotateTransform>을 <xref:System.Windows.Media.ImageBrush>의 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성에 적용합니다.  <xref:System.Windows.Media.RotateTransform> 개체의 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성은 모두 이 내용 중심 점의 상대적 좌표인 0.5로 설정됩니다.  그 결과 브러시의 내용이 중심 점을 기준으로 회전합니다.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 다음 예제에서도 <xref:System.Windows.Media.RotateTransform>을 <xref:System.Windows.Media.ImageBrush>에 적용하지만 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성 대신 <xref:System.Windows.Media.Brush.Transform%2A> 속성을 사용합니다.  브러시 중심을 기준으로 회전하려면 <xref:System.Windows.Media.RotateTransform> 개체의 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성을 절대 좌표로 설정해야 합니다.  브러시는 175 x 90 픽셀의 사각형을 칠하기 때문에 사각형의 중심 점은 \(87.5, 45\)입니다.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 다음 그림은 변환 없는 브러시를 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성에 적용된 변환 및 <xref:System.Windows.Media.Brush.Transform%2A> 속성에 적용된 변환과 함께 보여 줍니다.  
  
 ![Brush RelativeTransform 및 Transform 설정](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk\_graphicsmm\_transformandrelativetransform")  
  
 이 예제는 보다 큰 예제의 일부입니다.  전체 샘플을 보려면 [Brushes 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)을 참조하십시오.  브러시에 대한 자세한 내용은 [WPF 브러시 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Brush.Transform%2A>   
 <xref:System.Windows.Media.Brush.RelativeTransform%2A>   
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.Brush>   
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)