---
title: '방법: 키 프레임을 사용하여 3차원 회전에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3-D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 085b2da20410d53fce6099131bf07249bde3209c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557624"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames"></a><span data-ttu-id="87d82-102">방법: 키 프레임을 사용하여 3차원 회전에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="87d82-102">How to: Animate a 3-D Rotation Using Key Frames</span></span>
<span data-ttu-id="87d82-103">다음 예에서 <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> 3D 개체가 해당 축 회전 애니메이션 효과 주는 "비틀 거리 면 서" 하는 동안 회전을 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87d82-103">In the following example, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> is used to make a 3D object rotate while its axis of rotation animates resulting in a "wobble".</span></span> <span data-ttu-id="87d82-104">이 애니메이션 다음 키 프레임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87d82-104">This animation uses the following key frames:</span></span>  
  
1.  <span data-ttu-id="87d82-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> 값 사이의 선형 보간을 부드러운 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87d82-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="87d82-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> 값 (보간 없음) 사이의 급격 한 "이동"을 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87d82-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="87d82-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> 변수 전환에 따라 값을 만드는 데 사용 되는 <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="87d82-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="87d82-108">아래 예에서 애니메이션의이 부분 서서히 시작 되 다가 시간 세그먼트의 끝으로, 갈수록 합니다.</span><span class="sxs-lookup"><span data-stu-id="87d82-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87d82-109">예제</span><span class="sxs-lookup"><span data-stu-id="87d82-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="87d82-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87d82-110">See Also</span></span>  
 [<span data-ttu-id="87d82-111">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="87d82-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="87d82-112">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="87d82-112">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="87d82-113">Storyboard를 사용하여 3차원 회전에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="87d82-113">Animate a 3-D Rotation Using Storyboards</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [<span data-ttu-id="87d82-114">Rotation3DAnimation을 사용하여 3차원 회전에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="87d82-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [<span data-ttu-id="87d82-115">4원수를 사용하여 3차원 회전에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="87d82-115">Animate a 3-D Rotation Using Quaternions</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)  
 [<span data-ttu-id="87d82-116">키 프레임을 사용하여 3차원 회전에 애니메이션 효과 주기(QuaternionAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="87d82-116">Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
