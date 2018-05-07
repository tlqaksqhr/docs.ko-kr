---
title: '방법: AnimationClock을 사용하여 속성에 애니메이션 효과 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
ms.openlocfilehash: b8c64586d0dc5dc2e565fe4cb002e0f9cd4109af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a>방법: AnimationClock을 사용하여 속성에 애니메이션 효과 적용
사용 하는 방법을 보여 주는이 예제 <xref:System.Windows.Media.Animation.Clock> 속성에 애니메이션 효과를 줄 개체입니다.  
  
 종속성 속성에 애니메이션을 적용하는 방법에는 다음 세 가지가 있습니다.  
  
-   만들기는 <xref:System.Windows.Media.Animation.AnimationTimeline> 를 사용 하 여 해당 속성을 연결 된 <xref:System.Windows.Media.Animation.Storyboard>합니다.  
  
-   개체의를 사용 하 여 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 단일을 적용할 방법을 <xref:System.Windows.Media.Animation.AnimationTimeline> 대상 속성에 있습니다.  
  
-   만들기는 <xref:System.Windows.Media.Animation.AnimationClock> 에서 <xref:System.Windows.Media.Animation.AnimationTimeline> 속성에 적용 합니다.  
  
 <xref:System.Windows.Media.Animation.Storyboard> 개체 및 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 방법을 사용 하면 속성 애니메이션 효과를 직접 만들고 시계를 배포 하지 않고 (예제를 보려면 [속성 스토리 보드를 사용 하 여 애니메이션을 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) 및 [는 속성 없이 애니메이션을 적용 스토리 보드를 사용 하 여](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)); 클럭은 만들고 자동으로 배포 합니다.  
  
## <a name="example"></a>예제  
 만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Media.Animation.AnimationClock> 두 개의 비슷한 속성에 적용 합니다.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 대화형으로 제어 하는 방법을 보여 주는 예제는 <xref:System.Windows.Media.Animation.Clock> 시작 되 면 참조 [시계를 대화형으로 제어](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)  
 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
