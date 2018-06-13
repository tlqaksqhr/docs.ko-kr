---
title: '방법: 애니메이션 가속 또는 감속'
ms.date: 03/30/2017
helpviewer_keywords:
- decelerating animation [WPF]
- accelerating animation [WPF]
- animation [WPF], accelerating
- animation [WPF], decelerating
ms.assetid: 4f383b2c-f94d-4a4e-9a06-f56f5dae95f9
ms.openlocfilehash: b4bea64dbc88ce32c908289b9465b058c558a932
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555677"
---
# <a name="how-to-accelerate-or-decelerate-an-animation"></a><span data-ttu-id="4d88a-102">방법: 애니메이션 가속 또는 감속</span><span class="sxs-lookup"><span data-stu-id="4d88a-102">How to: Accelerate or Decelerate an Animation</span></span>
<span data-ttu-id="4d88a-103">이 예제에는 애니메이션을 가속화 하 고 시간이 지남에 따라 감속 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d88a-103">This example demonstrates how to make an animation accelerate and decelerate over time.</span></span> <span data-ttu-id="4d88a-104">다음 예제에서는 여러 사각형은 애니메이션 효과 적용 하 여 서로 다른 사용 하 여 애니메이션 <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> 및 <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d88a-104">In the following example, several rectangles are animated by animations with different <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> and <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d88a-105">예제</span><span class="sxs-lookup"><span data-stu-id="4d88a-105">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AccelDecelExample.xaml#1)]  
  
 <span data-ttu-id="4d88a-106">이 예제에서 코드는 생략 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4d88a-106">Code has been omitted from this example.</span></span> <span data-ttu-id="4d88a-107">전체 코드에 대 한 참조는 [애니메이션 타이밍 동작 샘플](http://go.microsoft.com/fwlink/?LinkID=159970)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d88a-107">For the complete code, see the [Animation Timing Behavior Sample](http://go.microsoft.com/fwlink/?LinkID=159970).</span></span>
