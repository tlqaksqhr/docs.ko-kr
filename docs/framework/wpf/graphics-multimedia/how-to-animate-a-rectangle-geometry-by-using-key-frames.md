---
title: "방법: 키 프레임을 사용하여 사각형에 애니메이션 효과 주기"
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
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f110bcea76a61d46932c9e1aacf27f6f3255a91
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>방법: 키 프레임을 사용하여 사각형에 애니메이션 효과 주기
애니메이션 효과 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 의 속성을 <xref:System.Windows.Media.RectangleGeometry> 키 프레임을 사용 하 여 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> 애니메이션 효과를 줄 클래스는 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 속성의는 <xref:System.Windows.Media.RectangleGeometry>합니다. 이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.  
  
1.  인스턴스를 사용 하 여 첫 번째 2 초 동안는 <xref:System.Windows.Media.Animation.LinearRectKeyFrame> 위치, 너비 및 사각형의 높이 점진적으로 변화를 애니메이션 효과를 줄 클래스입니다. 같은 키 프레임 선형 <xref:System.Windows.Media.Animation.LinearRectKeyFrame> 값 사이의 부드러운 선형 전환을 만듭니다.  
  
2.  다음의 끝 중 0.5 초에서 사용 하는 <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> 급격 하 게 줄입니다 사각형의 높이 클래스입니다. 과 같은 불연속 키 프레임 <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> 높이 감소 신속 하 게 발생 하 고 효과, 급격 한 변경과 값 간에 만듭니다.  
  
3.  마지막 2 초 동안의 인스턴스를 사용 하 여는 <xref:System.Windows.Media.Animation.SplineRectKeyFrame> 사각형의 원래 크기와 위치 다시 변경 하는 클래스입니다. 같은 스플라인 키 프레임 <xref:System.Windows.Media.Animation.SplineRectKeyFrame> 변수 값의 값을 따르는 사이의 전환을 만들려면는 <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> 속성입니다. 이 예제에서 변화는 느리게 시작하다가 시간 세그먼트의 끝에 다가가면 기하급수적으로 빨라집니다.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.RectangleGeometry>  
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>  
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>  
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [키 프레임 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
