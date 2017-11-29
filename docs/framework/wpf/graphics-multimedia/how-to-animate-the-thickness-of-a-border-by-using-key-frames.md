---
title: "방법: 키 프레임을 사용하여 테두리 두께에 애니메이션 효과 주기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08950b2b92bfcbd28472327f12a2ee49abfd9fed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="a894c-102">방법: 키 프레임을 사용하여 테두리 두께에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="a894c-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="a894c-103">애니메이션 효과 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Control.BorderThickness%2A> 속성은 <xref:System.Windows.Controls.Border>합니다.</span><span class="sxs-lookup"><span data-stu-id="a894c-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a894c-104">예제</span><span class="sxs-lookup"><span data-stu-id="a894c-104">Example</span></span>  
 <span data-ttu-id="a894c-105">다음 예제에서는 <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> 애니메이션 효과를 줄 클래스는 <xref:System.Windows.Controls.Control.BorderThickness%2A> 속성의는 <xref:System.Windows.Controls.Border>합니다.</span><span class="sxs-lookup"><span data-stu-id="a894c-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="a894c-106">이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a894c-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="a894c-107">인스턴스를 사용 하 여 첫 번째 0.5 초 동안는 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> 테두리의 두께 점진적으로 증가 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a894c-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="a894c-108">이 예제에서는 사용 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> 값 사이의 선형 한 부드러운 증가 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a894c-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2.  <span data-ttu-id="a894c-109">다음의 끝에 0.5 초에서 사용 하는 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> 테두리의 두께 갑자기 증가 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a894c-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="a894c-110">파생 된 것과 같은 불연속 키 프레임 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> 애니메이션의 이동은 비정상적, 값 간에 갑작스러운 점프 효과 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a894c-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3.  <span data-ttu-id="a894c-111">마지막 2 초 동안의 인스턴스를 사용 하 여는 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> 클래스 테두리의 두께를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="a894c-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="a894c-112">파생 된 것과 같은 스플라인 키 프레임 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> 변수 값의 값을 따르는 사이의 전환을 만들려면는 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a894c-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="a894c-113">이 키 프레임에서 애니메이션은 느리게 시작하다가 시간 세그먼트의 끝에 다가가면 기하급수적으로 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="a894c-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="a894c-114">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a894c-114">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a894c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a894c-115">See Also</span></span>  
 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>  
 [<span data-ttu-id="a894c-116">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="a894c-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="a894c-117">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="a894c-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)  
 [<span data-ttu-id="a894c-118">BorderThickness 값에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="a894c-118">Animate a BorderThickness Value</span></span>](../../../../docs/framework/wpf/controls/how-to-animate-a-borderthickness-value.md)
