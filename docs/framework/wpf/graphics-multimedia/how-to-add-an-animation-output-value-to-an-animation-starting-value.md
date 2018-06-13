---
title: '방법: 애니메이션 시작 값에 애니메이션 출력 값 추가'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
ms.openlocfilehash: 7f60a3cd3fc88c5bb2460864be6cee008dc672fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557627"
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a><span data-ttu-id="59531-102">방법: 애니메이션 시작 값에 애니메이션 출력 값 추가</span><span class="sxs-lookup"><span data-stu-id="59531-102">How to: Add an Animation Output Value to an Animation Starting Value</span></span>
<span data-ttu-id="59531-103">이 예제에는 애니메이션 출력 값을 애니메이션 시작 값에 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59531-103">This example shows how to add an animation output value to an animation starting value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59531-104">예제</span><span class="sxs-lookup"><span data-stu-id="59531-104">Example</span></span>  
 <span data-ttu-id="59531-105"><xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> 속성 애니메이션된 속성의 시작 값 (기본값)에 추가 하는 애니메이션의 출력 값을 설치할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="59531-105">The <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property specifies whether you want the output value of an animation added to the starting value (base value) of an animated property.</span></span> <span data-ttu-id="59531-106">사용할 수는 <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> 가장 기본적인 애니메이션 및 대부분의 키 프레임 애니메이션 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="59531-106">You can use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="59531-107">자세한 내용은 참조 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) 및 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="59531-107">For more information, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) and [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="59531-108">다음 예제를 사용 하 여 결과 보여 줍니다.는 <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> 속성을 <xref:System.Windows.Media.Animation.DoubleAnimation> 를 사용 하 고는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> 속성 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>합니다.</span><span class="sxs-lookup"><span data-stu-id="59531-108">The following example shows the effect of using the <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimation> and using the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> property with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="59531-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59531-109">See Also</span></span>  
 [<span data-ttu-id="59531-110">주기가 반복되는 동안 애니메이션 값 누적</span><span class="sxs-lookup"><span data-stu-id="59531-110">Accumulate Animation Values During Repeat Cycles</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [<span data-ttu-id="59531-111">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="59531-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="59531-112">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="59531-112">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="59531-113">애니메이션 및 타이밍</span><span class="sxs-lookup"><span data-stu-id="59531-113">Animation and Timing</span></span>](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="59531-114">방법 항목</span><span class="sxs-lookup"><span data-stu-id="59531-114">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
