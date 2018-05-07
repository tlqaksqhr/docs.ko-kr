---
title: '방법: 요소 기울이기'
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 8bd860a71253a55cb3148426dbb61cbd3477e95e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-skew-an-element"></a>방법: 요소 기울이기
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.SkewTransform> 요소 중심 되도록 합니다. 전단이라고도 하는 기울이기는 일관되지 않은 방식으로 좌표 공간을 늘리는 변환입니다. 일반적인 용도 중 하나는 <xref:System.Windows.Media.SkewTransform> 시뮬레이션 하는 데는 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 깊이 [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] 개체입니다.  
  
 사용 하 여는 <xref:System.Windows.Media.SkewTransform.CenterX%2A> 및 <xref:System.Windows.Media.SkewTransform.CenterY%2A> 중심을 지정 하는 속성의 지점는 <xref:System.Windows.Media.SkewTransform>합니다.  
  
 사용 하 여는 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 및 <xref:System.Windows.Media.SkewTransform.AngleY%2A> 속성 x 축 및 y 축 기울기 각도 지정 하 고이 축에 따라 현재 좌표계를 왜곡 시킬 수 있습니다.  
  
 기울이기 변환 효과 예측 하려면 다음을 고려해 야 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 원래 좌표계를 기준으로 x 축 값을 기울입니다. 따라서 프로그램 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 가 30 인 y 축 원점 통과 30도 회전 하 고 x 축으로 해당 원본에서 30도 값 오차입니다. 마찬가지로, 한 <xref:System.Windows.Media.SkewTransform.AngleY%2A> 30의 원점부터 30도 도형의 y 값을 기울입니다. 이것은 좌표 시스템을 x 또는 y축으로 30도만큼 변환(이동)하는 것과 같지 않습니다.  
  
 다음 예제에서는 45도 가로로 기울입니다는 <xref:System.Windows.Shapes.Rectangle> (0, 0)의 중심점부터 합니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 다음 예제에서는 45도 가로로 기울입니다는 <xref:System.Windows.Shapes.Rectangle> (25, 25 로부터) 중심점부터 합니다.  
  
 [!code-xaml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 다음 예제에서는 45도 세로 기울입니다는 <xref:System.Windows.Shapes.Rectangle> (25, 25 로부터) 중심점부터 합니다.  
  
 [!code-xaml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 다음 그림에서는 이 예제에서 사용되는 다양한 기울이기를 보여 줍니다.  
  
 ![SkewTransform 예제](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
세 개의 SkewTransform 예제 그림  
  
 전체 샘플을 보려면 [2차원 변환 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.SkewTransform>  
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
