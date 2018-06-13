---
title: '방법: 텍스트에 애니메이션 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: 56a12ca915cc320619a094df38d118eabf202734
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545440"
---
# <a name="how-to-apply-animations-to-text"></a><span data-ttu-id="07c4d-102">방법: 텍스트에 애니메이션 적용</span><span class="sxs-lookup"><span data-stu-id="07c4d-102">How to: Apply Animations to Text</span></span>
<span data-ttu-id="07c4d-103">애니메이션은 응용 프로그램의 텍스트 모양과 표시를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c4d-103">Animations can alter the display and appearance of text in your application.</span></span> <span data-ttu-id="07c4d-104">다음 예에서는 다양 한 유형의 애니메이션의 텍스트 표시에 영향을 사용 하 여 한 <xref:System.Windows.Controls.TextBlock> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4d-104">The following examples use different types of animations to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07c4d-105">예제</span><span class="sxs-lookup"><span data-stu-id="07c4d-105">Example</span></span>  
 <span data-ttu-id="07c4d-106">다음 예제에서는 한 <xref:System.Windows.Media.Animation.DoubleAnimation> 텍스트 블록의 너비를 애니메이션 효과를 주는 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4d-106">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the width of the text block.</span></span> <span data-ttu-id="07c4d-107">10초 동안 너비 값을 텍스트 블록의 너비에서 0으로 변경한 후 다시 너비 값을 반대로 변경하여 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4d-107">The width value changes from the width of the text block to 0 over a duration of 10 seconds, and then reverses the width values and continues.</span></span> <span data-ttu-id="07c4d-108">이러한 형식의 애니메이션은 지우기 효과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4d-108">This type of animation creates a wipe effect.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 <span data-ttu-id="07c4d-109">다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation> 에 텍스트 블록의 불투명도 애니메이션을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4d-109">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the opacity of the text block.</span></span> <span data-ttu-id="07c4d-110">5초 동안 불투명도 값을 1.0에서 0으로 변경한 다음 불투명 값을 반대로 변경하고 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4d-110">The opacity value changes from 1.0 to 0 over a duration of 5 seconds, and then reverses the opacity values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 <span data-ttu-id="07c4d-111">다음 다이어그램의 효과 보여 줍니다.는 <xref:System.Windows.Controls.TextBlock> 불투명도를 변경 하는 컨트롤 `1.00` 를 `0.00` 에 정의 된 5 초 간격 동안는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4d-111">The following diagram shows the effect of the <xref:System.Windows.Controls.TextBlock> control changing its opacity from `1.00` to `0.00` during the 5-second interval defined by the <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span></span>  
  
 <span data-ttu-id="07c4d-112">![불투명도 1.00에서 0.00으로 바뀌는 텍스트](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")</span><span class="sxs-lookup"><span data-stu-id="07c4d-112">![Text changing opacity from 1.00 to 0.00](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")</span></span>  
<span data-ttu-id="07c4d-113">1.00에서 0.00으로 변경하는 텍스트 불투명도</span><span class="sxs-lookup"><span data-stu-id="07c4d-113">Text Opacity changing from 1.00 to 0.00</span></span>  
  
 <span data-ttu-id="07c4d-114">다음 예제에서는 <xref:System.Windows.Media.Animation.ColorAnimation> 에 텍스트 블록의 전경 색 애니메이션을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4d-114">The following example uses a <xref:System.Windows.Media.Animation.ColorAnimation> to animate the foreground color of the text block.</span></span> <span data-ttu-id="07c4d-115">전경색 값을 5초 동안 한 색상에서 두 번째 색상으로 변경한 다음 색상 값을 반대로 변경하고 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4d-115">The foreground color value changes from one color to a second color over a duration of 5 seconds, and then reverses the color values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 <span data-ttu-id="07c4d-116">다음 예제에서는 한 <xref:System.Windows.Media.Animation.DoubleAnimation> 텍스트 블록을 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4d-116">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to rotate the text block.</span></span> <span data-ttu-id="07c4d-117">텍스트 블록은 20초 동안 전체 회전을 수행한 다음 회전을 계속 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4d-117">The text block performs a full rotation over a duration of 20 seconds, and then continues to repeat the rotation.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a><span data-ttu-id="07c4d-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07c4d-118">See Also</span></span>  
 [<span data-ttu-id="07c4d-119">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="07c4d-119">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
