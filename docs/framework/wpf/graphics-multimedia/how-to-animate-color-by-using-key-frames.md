---
title: '방법: 키 프레임을 사용하여 색에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 7d89a1f9c24c93bd6b05265092bde09e8cf6eff5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-color-by-using-key-frames"></a>방법: 키 프레임을 사용하여 색에 애니메이션 효과 주기
애니메이션 효과 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 의 <xref:System.Windows.Media.SolidColorBrush> 키 프레임을 사용 하 여 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> 애니메이션 효과를 줄 클래스는 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 속성의는 <xref:System.Windows.Media.SolidColorBrush>합니다. 이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.  
  
1.  인스턴스를 사용 하 여 첫 번째 2 초 동안는 <xref:System.Windows.Media.Animation.LinearColorKeyFrame> 점진적으로 녹색에서 빨간색으로 색을 변경 하는 클래스입니다. 같은 키 프레임 선형 <xref:System.Windows.Media.Animation.LinearColorKeyFrame> 값 사이의 부드러운 선형 전환을 만듭니다.  
  
2.  다음의 끝 중 0.5 초에서 사용 하는 <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> 클래스를 신속 하 게 노란색으로 빨강에서 색을 변경 합니다. 과 같은 불연속 키 프레임 <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> 급격 한 변경과 값 간에 즉, 만들고 애니메이션의이 부분의 색 변경 신속 하 게 발생 효과입니다.  
  
3.  마지막 2 초 동안의 인스턴스를 사용 하 여는 <xref:System.Windows.Media.Animation.SplineColorKeyFrame> 다시 색을 변경 하려면 클래스-녹색에서 노랑 다시이 이번 합니다. 같은 스플라인 키 프레임 <xref:System.Windows.Media.Animation.SplineColorKeyFrame> 변수 값의 값을 따르는 사이의 전환을 만들려면는 <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> 속성입니다. 이 예제에서 색 변화는 느리게 시작하다가 시간 세그먼트의 끝에 다가가면 기하급수적으로 빨라집니다.  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>  
 <xref:System.Windows.Media.SolidColorBrush>  
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>  
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [키 프레임 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
