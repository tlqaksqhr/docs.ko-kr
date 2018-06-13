---
title: '방법: 키 프레임을 사용하여 부울에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: d6273c08881e802595e831cafe120a5bec841c4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556928"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a><span data-ttu-id="f4f26-102">방법: 키 프레임을 사용하여 부울에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="f4f26-102">How to: Animate a Boolean by Using Key Frames</span></span>
<span data-ttu-id="f4f26-103">부울 속성 값에 애니메이션을 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Button> 키 프레임을 사용 하 여 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f26-103">This example shows how to animate the Boolean property value of a <xref:System.Windows.Controls.Button> control by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4f26-104">예제</span><span class="sxs-lookup"><span data-stu-id="f4f26-104">Example</span></span>  
 <span data-ttu-id="f4f26-105">다음 예제에서는 <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> 애니메이션 효과를 주는 클래스는 <xref:System.Windows.UIElement.IsEnabled%2A> 속성의는 <xref:System.Windows.Controls.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f26-105">The following example uses the <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> class to animate the <xref:System.Windows.UIElement.IsEnabled%2A> property of a <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="f4f26-106">인스턴스를 사용 하는이 예제의 모든 키 프레임의 <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f4f26-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> class.</span></span> <span data-ttu-id="f4f26-107">과 같은 불연속 키 프레임 <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> 애니메이션의 이동은 비정상적, 값 간에 갑작스러운 점프 효과 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f4f26-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="f4f26-108">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4f26-108">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4f26-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4f26-109">See Also</span></span>  
 <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>  
 <xref:System.Windows.UIElement.IsEnabled%2A>  
 <xref:System.Windows.Controls.Button>  
 [<span data-ttu-id="f4f26-110">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="f4f26-110">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="f4f26-111">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="f4f26-111">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
