---
title: '방법: 배경으로 사용된 이미지의 가로 세로 비율 유지'
ms.date: 03/30/2017
helpviewer_keywords:
- aspect ratios of background images [WPF], preserving
- brushes [WPF], preserving aspect ratios of background images
- background images [WPF], preserving aspect ratios
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
ms.openlocfilehash: 906033b43ba657acc873f12a00000189db6796ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-preserve-the-aspect-ratio-of-an-image-used-as-a-background"></a>방법: 배경으로 사용된 이미지의 가로 세로 비율 유지
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성은 <xref:System.Windows.Media.ImageBrush> 이미지의 가로 세로 비율을 유지 하기 위해 합니다.  
  
 기본적으로 사용 하는 경우는 <xref:System.Windows.Media.ImageBrush> 영역을 그리는, 해당 콘텐츠를 늘이는을 출력 영역을 완전히 채웁니다. 출력 영역과 이미지의 가로 세로 비율이 다르면 이미지가 확장되면서 왜곡됩니다.  
  
 있도록는 <xref:System.Windows.Media.ImageBrush> 해당 이미지의 가로 세로 비율 유지, 설정 된 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 <xref:System.Windows.Media.Stretch.Uniform> 또는 <xref:System.Windows.Media.Stretch.UniformToFill>합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 개의 <xref:System.Windows.Media.ImageBrush> 두 개의 사각형을 그리는 데 개체입니다. 각 사각형은 300 × 150픽셀 크기이며 각각 300 x 300픽셀 이미지를 포함합니다. <xref:System.Windows.Media.TileBrush.Stretch%2A> 첫 번째는 브러시 속성 <xref:System.Windows.Media.Stretch.Uniform>, 및 <xref:System.Windows.Media.TileBrush.Stretch%2A> 두 번째는 브러시 속성 <xref:System.Windows.Media.Stretch.UniformToFill>합니다.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 다음 그림에 나와 있는 첫 번째 브러시를 출력 한 <xref:System.Windows.Media.TileBrush.Stretch%2A> 설정인 <xref:System.Windows.Media.Stretch.Uniform>합니다.  
  
 ![Uniform 늘이기를 사용한 ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.jpg "graphicsmm_ImageBrushUniformStretch")  
  
 다음 그림에서는 두 번째 브러시를 출력 한 <xref:System.Windows.Media.TileBrush.Stretch%2A> 설정인 <xref:System.Windows.Media.Stretch.UniformToFill>합니다.  
  
 ![UniformToFill 늘이기를 사용한 ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.jpg "graphicsmm_ImageBrushUniformToFillStretch")  
  
 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성 다른 동일 하 게 작동 <xref:System.Windows.Media.TileBrush> 개체, 즉,에 대 한 <xref:System.Windows.Media.DrawingBrush> 및 <xref:System.Windows.Media.VisualBrush>합니다. 에 대 한 자세한 내용은 <xref:System.Windows.Media.ImageBrush> 및 다른 <xref:System.Windows.Media.TileBrush> 개체 참조 [이미지, 그리기, 및 시각적 개체를 사용 하 여 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)합니다.  
  
 또한 있는지 확인 하지만 <xref:System.Windows.Media.TileBrush.Stretch%2A> 지정 나타나며 방법을 <xref:System.Windows.Media.TileBrush> 콘텐츠를 출력 영역에 맞게 늘리면 실제로 지정 방법을 <xref:System.Windows.Media.TileBrush> 콘텐츠 기본 타일에 맞게 늘어납니다. 자세한 내용은 <xref:System.Windows.Media.TileBrush>을 참조하세요.  
  
 이 코드 예제는 제공 된 큰 예제의 일부는 <xref:System.Windows.Media.ImageBrush> 클래스입니다. 전체 샘플을 참조 하십시오. [ImageBrush 샘플](http://go.microsoft.com/fwlink/?LinkID=160005)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.TileBrush>  
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
