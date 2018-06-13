---
title: '방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 7dc49bc6b3f9156507cb821bfc32b269365b206c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558542"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="8c007-102">방법: 키 프레임을 사용하여 개체에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="8c007-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="8c007-103">이 예제는 개체에 애니메이션을 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Page.Background%2A> 속성은 <xref:System.Windows.Controls.Page> 키 프레임을 사용 하 여 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c007-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c007-104">예제</span><span class="sxs-lookup"><span data-stu-id="8c007-104">Example</span></span>  
 <span data-ttu-id="8c007-105">다음 예제에서는 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 색 애니메이션 효과를 클래스에 대 한 변경의 <xref:System.Windows.Controls.Page.Background%2A> 속성의는 <xref:System.Windows.Controls.Page> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c007-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="8c007-106">예제 애니메이션 배경 브러시를 정기적으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8c007-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="8c007-107">이 애니메이션에 사용 하 여는 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 클래스 세 개의 서로 다른 키 프레임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8c007-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="8c007-108">애니메이션 키 프레임을 사용 하 여 다음과 같은 방식:</span><span class="sxs-lookup"><span data-stu-id="8c007-108">The animation uses key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="8c007-109">애니메이션 효과 인스턴스의 첫 번째 초 후에는 <xref:System.Windows.Media.LinearGradientBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c007-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="8c007-110">예제의이 섹션에서는 색을 빨간색 주황색 노랑에서 전환 되도록 배경색에 선형 그라데이션으로 표시할 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c007-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2.  <span data-ttu-id="8c007-111">애니메이션 효과의 인스턴스를 완료 한 다음 초에는 <xref:System.Windows.Media.RadialGradientBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c007-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="8c007-112">예제의이 섹션은 방사형 그라데이션 배경색으로 적용 하므로 색을 검정으로 파란색 흰색에서 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c007-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3.  <span data-ttu-id="8c007-113">애니메이션 효과의 인스턴스 세 번째 초 후에는 <xref:System.Windows.Media.DrawingBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c007-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="8c007-114">예제의이 섹션에서는 백그라운드에 체크 무늬 패턴을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8c007-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4.  <span data-ttu-id="8c007-115">애니메이션 다시 시작 되 고 무한 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c007-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c007-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 함께 사용할 수 있는 키 프레임의 유일한 종류는 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c007-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="8c007-117">같은 키 프레임 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> 즉에서 값을 급격 한 변경과 만들고,이 예에서 색 변경 갑자기 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="8c007-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="8c007-118">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c007-118">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c007-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c007-119">See Also</span></span>  
 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.Page.Background%2A>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>  
 <xref:System.Windows.Media.LinearGradientBrush>  
 <xref:System.Windows.Media.RadialGradientBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 [<span data-ttu-id="8c007-120">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="8c007-120">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="8c007-121">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="8c007-121">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
