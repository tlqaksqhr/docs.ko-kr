---
title: "방법: Storyboard를 사용하여 3차원 회전에 애니메이션 효과 주기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Storyboards [WPF]
- 3-D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3-D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 56839dfc5382f5dd56ec0b26d4aabe42536bf04e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-3-d-rotation-using-storyboards"></a><span data-ttu-id="c7fe0-102">방법: Storyboard를 사용하여 3차원 회전에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="c7fe0-102">How to: Animate a 3-D Rotation Using Storyboards</span></span>
<span data-ttu-id="c7fe0-103">다음 예제에서는 3D 개체가 "비틀" 애니메이션으로 회전 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> 및 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> 속성의는 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c7fe0-103">The following example shows how to make a 3D object rotate while it "wobbles" by animating the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> and <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> properties of an <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object.</span></span> <span data-ttu-id="c7fe0-104">이 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> 개체 3D 개체의 회전 변환을 지정 하 고 원하는 회전 효과가 만듭니다 하므로 해당 속성에 애니메이션을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7fe0-104">This <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object specifies the rotation transform of the 3D object and so animating its properties creates the desire rotation effect.</span></span> <span data-ttu-id="c7fe0-105">스토리 보드 내 <xref:System.Windows.Media.Animation.DoubleAnimation> 애니메이션 효과 적용 하는 데 사용 되는 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> 하는 동안 속성 <xref:System.Windows.Media.Animation.Vector3DAnimation> 애니메이션 효과 적용 하는 데 사용 되는 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c7fe0-105">Within the Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> property while <xref:System.Windows.Media.Animation.Vector3DAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7fe0-106">예제</span><span class="sxs-lookup"><span data-stu-id="c7fe0-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c7fe0-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7fe0-107">See Also</span></span>  
 [<span data-ttu-id="c7fe0-108">Rotation3DAnimation을 사용하여 3차원 회전에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="c7fe0-108">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)  
 [<span data-ttu-id="c7fe0-109">키 프레임을 사용하여 3차원 회전에 애니메이션 효과 주기(Rotation3DAnimationUsingKeyFrames)</span><span class="sxs-lookup"><span data-stu-id="c7fe0-109">Animate a 3-D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)  
 [<span data-ttu-id="c7fe0-110">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="c7fe0-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="c7fe0-111">Storyboard 개요</span><span class="sxs-lookup"><span data-stu-id="c7fe0-111">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
