---
title: '방법: 키 프레임을 사용하여 크기 변경에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 0c2828215527a285943a79920de51fa42fe7a8a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559894"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>방법: 키 프레임을 사용하여 크기 변경에 애니메이션 효과 주기
이 예제에서는 키 프레임을 사용하여 크기 변경에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> 애니메이션 효과를 줄 클래스는 <xref:System.Windows.Media.ArcSegment.Size%2A> 속성의는 <xref:System.Windows.Media.ArcSegment>합니다. 이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.  
  
1.  인스턴스를 사용 하 여 애니메이션의 첫 번째 0.5 초 동안는 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> 클래스를 점차적으로 호의 크기를 늘립니다. 같은 키 프레임 선형 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> 값 사이의 부드러운 선형 전환을 만듭니다.  
  
2.  다음의 끝에 0.5 초에서 사용 하는 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> 갑자기 크기를 늘리려면 원호의 클래스입니다. 과 같은 불연속 키 프레임 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> 크기 변화 갑자기 발생 한, 값 간에 갑작스러운 점프 효과 만듭니다.  
  
3.  인스턴스를 사용 하 여 마지막 두 초 동안는 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> 클래스 호의 크기를 늘리세요. 같은 스플라인 키 프레임 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> 변수 값의 값을 따르는 사이의 전환을 만들려면는 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> 속성입니다. 이 예제에서 원호의 크기는 처음에는 느리게 증가했다가 시간 세그먼트가 끝나면서 기하급수적으로 증가합니다.  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.ArcSegment.Size%2A>  
 <xref:System.Windows.Media.ArcSegment>  
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>  
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [키 프레임 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
