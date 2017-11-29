---
title: "방법: 키 프레임을 사용하여 사각형에 애니메이션 효과 주기"
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
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b6c23f894b6fa93a3889356416bd95f61fff8beb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="452e5-102">방법: 키 프레임을 사용하여 사각형에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="452e5-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="452e5-103">애니메이션 효과 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 의 속성을 <xref:System.Windows.Media.RectangleGeometry> 키 프레임을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="452e5-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="452e5-104">예제</span><span class="sxs-lookup"><span data-stu-id="452e5-104">Example</span></span>  
 <span data-ttu-id="452e5-105">다음 예제에서는 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> 애니메이션 효과를 줄 클래스는 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 속성의는 <xref:System.Windows.Media.RectangleGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="452e5-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="452e5-106">이 애니메이션은 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="452e5-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="452e5-107">인스턴스를 사용 하 여 첫 번째 2 초 동안는 <xref:System.Windows.Media.Animation.LinearRectKeyFrame> 위치, 너비 및 사각형의 높이 점진적으로 변화를 애니메이션 효과를 줄 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="452e5-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="452e5-108">같은 키 프레임 선형 <xref:System.Windows.Media.Animation.LinearRectKeyFrame> 값 사이의 부드러운 선형 전환을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="452e5-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="452e5-109">다음의 끝 중 0.5 초에서 사용 하는 <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> 급격 하 게 줄입니다 사각형의 높이 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="452e5-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="452e5-110">과 같은 불연속 키 프레임 <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> 높이 감소 신속 하 게 발생 하 고 효과, 급격 한 변경과 값 간에 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="452e5-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3.  <span data-ttu-id="452e5-111">마지막 2 초 동안의 인스턴스를 사용 하 여는 <xref:System.Windows.Media.Animation.SplineRectKeyFrame> 사각형의 원래 크기와 위치 다시 변경 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="452e5-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="452e5-112">같은 스플라인 키 프레임 <xref:System.Windows.Media.Animation.SplineRectKeyFrame> 변수 값의 값을 따르는 사이의 전환을 만들려면는 <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="452e5-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="452e5-113">이 예제에서 변화는 느리게 시작하다가 시간 세그먼트의 끝에 다가가면 기하급수적으로 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="452e5-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="452e5-114">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="452e5-114">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="452e5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="452e5-115">See Also</span></span>  
 <xref:System.Windows.Media.RectangleGeometry>  
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>  
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>  
 [<span data-ttu-id="452e5-116">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="452e5-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="452e5-117">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="452e5-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
