---
title: "방법: 키 프레임을 사용하여 포인트에 애니메이션 효과 주기"
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
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c115d31c6ace26f8fd9dd6cff3fdeead89eea33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a>방법: 키 프레임을 사용하여 포인트에 애니메이션 효과 주기
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> 애니메이션 효과를 줄 클래스는 <xref:System.Windows.Point>합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 삼각형 경로를 따라 타원을 이동합니다. 이 예제에서는 사용는 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> 애니메이션 효과를 줄 클래스는 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성의는 <xref:System.Windows.Media.EllipseGeometry>합니다. 이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.  
  
1.  인스턴스를 사용 하 여 첫 번째 0.5 초 동안는 <xref:System.Windows.Media.Animation.LinearPointKeyFrame> 해당 시작 위치에서 일정 한 비율로 타원 경로 따라 이동 하는 클래스입니다. 같은 키 프레임 선형 <xref:System.Windows.Media.Animation.LinearPointKeyFrame> 값 사이의 선형 보간을 부드러운를 만듭니다.  
  
2.  다음의 끝 중 0.5 초에서 사용 하는 <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> 갑자기 경로 따라 타원 다음 위치로 이동 하는 클래스입니다. 과 같은 불연속 키 프레임 <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> 값 사이 갑자기 점프를 만듭니다.  
  
3.  마지막 2 초 동안의 인스턴스를 사용 하 여는 <xref:System.Windows.Media.Animation.SplinePointKeyFrame> 타원 시작 위치로 다시 이동 하려면 클래스입니다. 같은 스플라인 키 프레임 <xref:System.Windows.Media.Animation.SplinePointKeyFrame> 변수 값의 값을 따르는 사이의 전환을 만들려면는 <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> 속성입니다. 이 예제에서 애니메이션은 느리게 시작하다가 시간 세그먼트의 끝에 다가가면 기하급수적으로 빨라집니다.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [키 프레임 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.  
  
 이 예제의 코드 버전 다른 애니메이션 예제와 일관성을 위해 사용 하 여 한 <xref:System.Windows.Media.Animation.Storyboard> 적용 하는 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>합니다. 그러나 코드에서 단일 애니메이션을 적용할 때 더 간단 하 게 사용 하 여는 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 사용 하는 대신 메서드를 <xref:System.Windows.Media.Animation.Storyboard>합니다. 예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.EllipseGeometry>  
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [키 프레임 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
