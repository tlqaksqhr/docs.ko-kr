---
title: '방법: 주기가 반복되는 동안 애니메이션 값 누적'
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: 7b954a388549f1bc6f3fa6ec1bcb2df61cc4e045
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a>방법: 주기가 반복되는 동안 애니메이션 값 누적
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 반복 주기에 대해 애니메이션 값을 누적 하는 속성입니다.  
  
## <a name="example"></a>예제  
 사용 하 여는 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 반복 주기에 대해 애니메이션의 기본 값을 누적 하는 속성입니다. 예를 들어, 애니메이션 9 번 반복을 설정 하는 경우 (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9 x")와 10 %15부터 애니메이션 효과를 주는 속성을 설정 (= 10에서 = 15), 속성에 애니메이션 효과 10에서 15 15 두 번째 주기 동안 20-첫 번째 주기 동안 25 세 번째 주기 등과 하는 동안 20%에서 합니다. 따라서 각 애니메이션 주기가 기준 값으로 이전 애니메이션 주기에서 끝 값을 사용합니다.  
  
 사용할 수는 `IsCumulative` 가장 기본적인 애니메이션 및 대부분의 키 프레임 애니메이션 속성입니다. 자세한 내용은 참조 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) 및 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)합니다.  
  
 다음 예에서는 4 개의 사각형의 너비에 애니메이션을 적용 하 여이 동작을 보여 줍니다. 예:  
  
-   애니메이션을 사용 하 여 첫 번째 사각형 적용 <xref:System.Windows.Media.Animation.DoubleAnimation> 설정 하 고는 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 속성을 `true`합니다.  
  
-   애니메이션을 사용 하 여 두 번째 사각형 적용 <xref:System.Windows.Media.Animation.DoubleAnimation> 설정 하 고는 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 속성의 기본값을 `false`합니다.  
  
-   애니메이션을 사용 하 여 세 번째 사각형 적용 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 설정 하 고는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> 속성을 `true`합니다.  
  
-   애니메이션을 사용 하 여 마지막 사각형 적용 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 설정 하 고는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> 속성을 `false`합니다.  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 시작 값에 애니메이션 출력 값 추가](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)  
 [애니메이션 반복](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
