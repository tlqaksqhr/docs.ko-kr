---
title: "방법: 키 프레임을 사용하여 매트릭스에 애니메이션 효과 주기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 862e1afdcd823181dff0948fab43b1656b85f721
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a><span data-ttu-id="f8f80-102">방법: 키 프레임을 사용하여 매트릭스에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="f8f80-102">How to: Animate a Matrix by Using Key Frames</span></span>
<span data-ttu-id="f8f80-103">애니메이션 효과 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 의 속성을 <xref:System.Windows.Media.MatrixTransform> 키 프레임을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f80-103">This example shows how to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8f80-104">예</span><span class="sxs-lookup"><span data-stu-id="f8f80-104">Example</span></span>  
 <span data-ttu-id="f8f80-105">다음 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> 애니메이션 효과를 줄 클래스는 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 속성의는 <xref:System.Windows.Media.MatrixTransform>합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f80-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="f8f80-106">이 예제에서는 사용 된 <xref:System.Windows.Media.MatrixTransform> 모양 및 위치를 변환 하는 개체는 <xref:System.Windows.Controls.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f80-106">The example uses the <xref:System.Windows.Media.MatrixTransform> object to transform the appearance and position of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="f8f80-107">이 애니메이션에 사용 하 여는 <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> 클래스를 만드는 두 가지 키 프레임 및 된 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f80-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> class to create two key frames and does the following with them:</span></span>  
  
1.  <span data-ttu-id="f8f80-108">첫 번째 애니메이션 효과 적용 <xref:System.Windows.Media.Matrix> 첫 번째 0.2 초 동안 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f80-108">Animates the first <xref:System.Windows.Media.Matrix> during the first 0.2 seconds.</span></span> <span data-ttu-id="f8f80-109">예제에서는 변경 내용을 <xref:System.Windows.Media.Matrix.M11%2A> 및 <xref:System.Windows.Media.Matrix.M12%2A> 의 속성은 <xref:System.Windows.Media.Matrix>합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f80-109">The example changes the <xref:System.Windows.Media.Matrix.M11%2A> and <xref:System.Windows.Media.Matrix.M12%2A> properties of the <xref:System.Windows.Media.Matrix>.</span></span> <span data-ttu-id="f8f80-110">이러한 변경으로 인해 단추 늘어나고 왜곡 될를 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f80-110">This change causes the button to stretch and become skewed.</span></span> <span data-ttu-id="f8f80-111">또한 변경 하 여 예제는 <xref:System.Windows.Media.Matrix.OffsetX%2A> 및 <xref:System.Windows.Media.Matrix.OffsetY%2A> 속성 단추 위치를 변경 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f80-111">The example also changes the <xref:System.Windows.Media.Matrix.OffsetX%2A> and <xref:System.Windows.Media.Matrix.OffsetY%2A> properties so that the button changes position.</span></span>  
  
2.  <span data-ttu-id="f8f80-112">두 번째 애니메이션 효과 적용 <xref:System.Windows.Media.Matrix> 1.0 초에서.</span><span class="sxs-lookup"><span data-stu-id="f8f80-112">Animates the second <xref:System.Windows.Media.Matrix> at 1.0 seconds.</span></span> <span data-ttu-id="f8f80-113">단추는 단추는 더 이상 일치 하지 않아에 있든 동안 다른 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f80-113">The button moves to another position while the button is no longer skewed or stretched.</span></span>  
  
3.  <span data-ttu-id="f8f80-114">애니메이션을 무한 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f80-114">Repeats the animation indefinitely.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8f80-115">파생 된 키 프레임의 <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> 개체 만들기 값 사이 갑자기 점프, 애니메이션의 이동은 비정상적 즉, 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f80-115">Key frames that derive from the <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> object create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="f8f80-116">전체 샘플을 보려면 [키 프레임 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8f80-116">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8f80-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8f80-117">See Also</span></span>  
 <xref:System.Windows.Media.MatrixTransform.Matrix%2A>  
 <xref:System.Windows.Media.MatrixTransform>  
 [<span data-ttu-id="f8f80-118">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="f8f80-118">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="f8f80-119">키 프레임 방법 항목</span><span class="sxs-lookup"><span data-stu-id="f8f80-119">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
