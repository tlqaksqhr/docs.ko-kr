---
title: '방법: 4원수를 사용하여 3차원 회전에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: 4c2a46aad1feeefe5c7c31ec192f46b8c891337f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a>방법: 4원수를 사용하여 3차원 회전에 애니메이션 효과 주기
이 예제에는 쿼터 니 언를 사용 하 여 3 차원 개체의 회전 애니메이션 효과 적용 하는 방법을 보여 줍니다.  
  
 다음 코드는 <xref:System.Windows.Media.Media3D.QuaternionRotation3D> 에 대 한 값으로 사용 되는 <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> 속성은 <xref:System.Windows.Media.Media3D.RotateTransform3D>합니다.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 이 <xref:System.Windows.Media.Media3D.QuaternionRotation3D> 으로 애니메이션는 <xref:System.Windows.Media.Animation.QuaternionAnimation> 내는 <xref:System.Windows.Media.Animation.Storyboard> 아래 코드를 사용 하 여 합니다.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a>예제  
 다음 코드에서는 전체 예제를 보여 줍니다.  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [3차원 장면 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Storyboard를 사용하여 3차원 회전에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [Rotation3DAnimation을 사용하여 3차원 회전에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
