---
title: '방법: BetweenShowDelay 속성 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolTip control [WPF], BetweenShowDelay time property
- BetweenShowDelay time property [WPF]
ms.assetid: 984ea76d-f2a2-4326-a02e-f97ec3d036d6
ms.openlocfilehash: 7d48fb859ec6d37abd2490bc718d58cbdaa67f13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552716"
---
# <a name="how-to-use-the-betweenshowdelay-property"></a><span data-ttu-id="c01ef-102">방법: BetweenShowDelay 속성 사용</span><span class="sxs-lookup"><span data-stu-id="c01ef-102">How to: Use the BetweenShowDelay Property</span></span>
<span data-ttu-id="c01ef-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 도구 설명 신속 하 게 표시 되도록 시간 속성-거의 없거나 전혀 없이 지연 되어 — 사용자로 이동 하면 마우스 포인터 한 도구 설명에서 직접 다른 합니다.</span><span class="sxs-lookup"><span data-stu-id="c01ef-103">This example shows how to use the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> time property so that tooltips appear quickly—with little or no delay—when a user moves the mouse pointer from one tooltip directly to another.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c01ef-104">예제</span><span class="sxs-lookup"><span data-stu-id="c01ef-104">Example</span></span>  
 <span data-ttu-id="c01ef-105">다음 예제에서는 <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> 속성이 1 초인 (1000 밀리초)로 설정 되어 및 <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> 모두의 도구 설명에 대 한 2 초 (2000 밀리초)로 설정 된 <xref:System.Windows.Shapes.Ellipse> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="c01ef-105">In the following example, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> property is set to one second (1000 milliseconds) and the <xref:System.Windows.Controls.ToolTipService.BetweenShowDelay%2A> is set to two seconds (2000 milliseconds) for the tooltips of both <xref:System.Windows.Shapes.Ellipse> controls.</span></span> <span data-ttu-id="c01ef-106">타원 중 하나에 대 한 도구 설명을 표시 하 고 다음 마우스 포인터를 이동 다른 타원에 일시 중지 하 고 2 초 내에 두 번째 타원의 도구 설명 바로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c01ef-106">If you display the tooltip for one of the ellipses and then move the mouse pointer to another ellipse within two seconds and pause on it, the tooltip of the second ellipse displays immediately.</span></span>  
  
 <span data-ttu-id="c01ef-107">다음 시나리오 중 하나에서 <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> 적용 되 고 표시 될 때까지 1 초에 두 번째 타원은 도구 설명에 이르게:</span><span class="sxs-lookup"><span data-stu-id="c01ef-107">In either of the following scenarios, the <xref:System.Windows.Controls.ToolTipService.InitialShowDelay%2A> applies, which causes the tooltip for the second ellipse to wait one second before it appears:</span></span>  
  
-   <span data-ttu-id="c01ef-108">두 번째 단추는 시간을 이동 하는 데 걸리는 경우 2 초 이상.</span><span class="sxs-lookup"><span data-stu-id="c01ef-108">If the time it takes to move to the second button is more than two seconds.</span></span>  
  
-   <span data-ttu-id="c01ef-109">도구 설명은 첫 번째 타원은 시간 간격의 시작 부분에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c01ef-109">If the tooltip is not visible at the beginning of the time interval for the first ellipse.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
[!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
## <a name="see-also"></a><span data-ttu-id="c01ef-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c01ef-110">See Also</span></span>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [<span data-ttu-id="c01ef-111">방법 항목</span><span class="sxs-lookup"><span data-stu-id="c01ef-111">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [<span data-ttu-id="c01ef-112">도구 설명 개요</span><span class="sxs-lookup"><span data-stu-id="c01ef-112">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)
