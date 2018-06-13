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
ms.locfileid: "33556941"
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a><span data-ttu-id="8a208-102">방법: 4원수를 사용하여 3차원 회전에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="8a208-102">How to: Animate a 3-D Rotation Using Quaternions</span></span>
<span data-ttu-id="8a208-103">이 예제에는 쿼터 니 언를 사용 하 여 3 차원 개체의 회전 애니메이션 효과 적용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8a208-103">This example shows how to animate a rotation of a 3-D object using quaternions.</span></span>  
  
 <span data-ttu-id="8a208-104">다음 코드는 <xref:System.Windows.Media.Media3D.QuaternionRotation3D> 에 대 한 값으로 사용 되는 <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> 속성은 <xref:System.Windows.Media.Media3D.RotateTransform3D>합니다.</span><span class="sxs-lookup"><span data-stu-id="8a208-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="8a208-105">이 <xref:System.Windows.Media.Media3D.QuaternionRotation3D> 으로 애니메이션는 <xref:System.Windows.Media.Animation.QuaternionAnimation> 내는 <xref:System.Windows.Media.Animation.Storyboard> 아래 코드를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a208-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="8a208-106">예제</span><span class="sxs-lookup"><span data-stu-id="8a208-106">Example</span></span>  
 <span data-ttu-id="8a208-107">다음 코드에서는 전체 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8a208-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="8a208-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a208-108">See Also</span></span>  
 [<span data-ttu-id="8a208-109">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="8a208-109">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="8a208-110">3차원 장면 만들기</span><span class="sxs-lookup"><span data-stu-id="8a208-110">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="8a208-111">3차원 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="8a208-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="8a208-112">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="8a208-112">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="8a208-113">Storyboard를 사용하여 3차원 회전에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="8a208-113">Animate a 3-D Rotation Using Storyboards</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)  
 [<span data-ttu-id="8a208-114">Rotation3DAnimation을 사용하여 3차원 회전에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="8a208-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
