---
title: '방법: 키 프레임을 사용하여 매트릭스에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: edb7074dffab23810872f4347f5339270af86bd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557019"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>방법: 키 프레임을 사용하여 매트릭스에 애니메이션 효과 주기
애니메이션 효과 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 의 속성을 <xref:System.Windows.Media.MatrixTransform> 키 프레임을 사용 하 여 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> 애니메이션 효과를 줄 클래스는 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 속성의는 <xref:System.Windows.Media.MatrixTransform>합니다. 이 예제에서는 사용 된 <xref:System.Windows.Media.MatrixTransform> 모양 및 위치를 변환 하는 개체는 <xref:System.Windows.Controls.Button>합니다.  
  
 이 애니메이션에 사용 하 여는 <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> 클래스를 만드는 두 가지 키 프레임 및 된 다음 작업을 수행 합니다.  
  
1.  첫 번째 애니메이션 효과 적용 <xref:System.Windows.Media.Matrix> 첫 번째 0.2 초 동안 합니다. 예제에서는 변경 내용을 <xref:System.Windows.Media.Matrix.M11%2A> 및 <xref:System.Windows.Media.Matrix.M12%2A> 의 속성은 <xref:System.Windows.Media.Matrix>합니다. 이러한 변경으로 인해 단추 늘어나고 왜곡 될를 합니다. 또한 변경 하 여 예제는 <xref:System.Windows.Media.Matrix.OffsetX%2A> 및 <xref:System.Windows.Media.Matrix.OffsetY%2A> 속성 단추 위치를 변경 되도록 합니다.  
  
2.  두 번째 애니메이션 효과 적용 <xref:System.Windows.Media.Matrix> 1.0 초에서. 단추는 단추는 더 이상 일치 하지 않아에 있든 동안 다른 위치로 이동 합니다.  
  
3.  애니메이션을 무한 반복 합니다.  
  
> [!NOTE]
>  파생 된 키 프레임의 <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> 개체 만들기 값 사이 갑자기 점프, 애니메이션의 이동은 비정상적 즉, 합니다.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>  
 <xref:System.Windows.Media.MatrixTransform>  
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [키 프레임 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
