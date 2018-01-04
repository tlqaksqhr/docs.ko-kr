---
title: "방법: 키 프레임을 사용하여 카메라 위치 및 방향에 애니메이션 효과 주기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 06e815ddd8beb48f80f13d93604773079fcffa06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="225d4-102">방법: 키 프레임을 사용하여 카메라 위치 및 방향에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="225d4-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="225d4-103">다음 예에서 <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> 의 위치에 애니메이션을 적용 하는 데 사용 되는 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 3D 장면에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="225d4-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="225d4-104">또한 <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> 3D 장면에 카메라가 가리키는 방향에 애니메이션을 적용 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="225d4-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="225d4-105">모두 이러한 애니메이션 일련의 애니메이션 효과 생성 하는 여러 키 프레임을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="225d4-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1.  <span data-ttu-id="225d4-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>및 <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> 부드러운 값 사이의 선형 보간을 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="225d4-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <span data-ttu-id="225d4-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>및 <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> 값 (보간 없음) 사이의 급격 한 "이동"을 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="225d4-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <span data-ttu-id="225d4-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>및 <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> 변수 전환에 따라 값을 만드는 데 사용 되는 <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="225d4-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="225d4-109">아래 예제에서 애니메이션 서서히 시작 되 다가 시간 세그먼트의 끝으로, 갈수록 합니다.</span><span class="sxs-lookup"><span data-stu-id="225d4-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="225d4-110">예</span><span class="sxs-lookup"><span data-stu-id="225d4-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="225d4-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="225d4-111">See Also</span></span>  
 [<span data-ttu-id="225d4-112">3차원 장면에서 카메라 위치 및 방향에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="225d4-112">Animate Camera Position and Direction in a 3D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-in-a-3d-scene.md)  
 [<span data-ttu-id="225d4-113">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="225d4-113">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
