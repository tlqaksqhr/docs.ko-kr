---
title: '방법: 키 프레임을 사용하여 문자열에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: 5219ce11667c84d3ceca380d5a4ddd52695736b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561061"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="70127-102">방법: 키 프레임을 사용하여 문자열에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="70127-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="70127-103">이 예제는 문자열에 애니메이션을 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성은 <xref:System.Windows.Controls.Button> 키 프레임을 사용 하 여 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="70127-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70127-104">예제</span><span class="sxs-lookup"><span data-stu-id="70127-104">Example</span></span>  
 <span data-ttu-id="70127-105">다음 예제에서는 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> 애니메이션 효과를 줄 클래스는 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성의는 <xref:System.Windows.Controls.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="70127-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="70127-106">이 예제에서 모든 키 프레임의 인스턴스를 사용 하 여는 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> 문자열 애니메이션 키 프레임을 사용 하 여 만든 분리 된 키 프레임에만 사용할 수 있으므로 클래스.</span><span class="sxs-lookup"><span data-stu-id="70127-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="70127-107">과 같은 불연속 키 프레임 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> 애니메이션에 대 한 변경 신속 하 게 발생 한, 값 간에 갑작스러운 점프 효과 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="70127-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="70127-108">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70127-108">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70127-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70127-109">See Also</span></span>  
 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.ContentControl.Content%2A>  
 <xref:System.Windows.Controls.Button>  
 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>  
 [<span data-ttu-id="70127-110">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="70127-110">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="70127-111">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="70127-111">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
