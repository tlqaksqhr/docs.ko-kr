---
title: "방법: Popup에 애니메이션 효과 주기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 276c1a54cfdddcde84c0702f4e84f1dc6174bbda
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-popup"></a><span data-ttu-id="420fb-102">방법: Popup에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="420fb-102">How to: Animate a Popup</span></span>
<span data-ttu-id="420fb-103">애니메이션 효과 적용 하는 두 가지를 보여 주는이 예제는 <xref:System.Windows.Controls.Primitives.Popup> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="420fb-103">This example shows two ways to animate a <xref:System.Windows.Controls.Primitives.Popup> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="420fb-104">예제</span><span class="sxs-lookup"><span data-stu-id="420fb-104">Example</span></span>  
 <span data-ttu-id="420fb-105">다음 예에서는 <xref:System.Windows.Controls.Primitives.PopupAnimation> 속성의 값을 <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>,으로 구독이 <xref:System.Windows.Controls.Primitives.Popup> "슬라이드 기능에" 있으면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="420fb-105">The following example sets the <xref:System.Windows.Controls.Primitives.PopupAnimation> property to a value of <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, which causes the <xref:System.Windows.Controls.Primitives.Popup> to "slide-in" when it appears.</span></span>  
  
 <span data-ttu-id="420fb-106">회전 하기 위해는 <xref:System.Windows.Controls.Primitives.Popup>를 지정 하는이 예제는 <xref:System.Windows.Media.RotateTransform> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에는 <xref:System.Windows.Controls.Canvas>의 자식 요소인는 <xref:System.Windows.Controls.Primitives.Popup>합니다.</span><span class="sxs-lookup"><span data-stu-id="420fb-106">In order to rotate the <xref:System.Windows.Controls.Primitives.Popup>, this example assigns a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property on the <xref:System.Windows.Controls.Canvas>, which is the child element of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  
  
 <span data-ttu-id="420fb-107">이 예제에서는 제대로 작동 하려면 변환에 대 한 설정 해야 합니다는 <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="420fb-107">For the transform to work correctly, the example must set the <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> property to `true`.</span></span> <span data-ttu-id="420fb-108">또한는 <xref:System.Windows.FrameworkElement.Margin%2A> 에 <xref:System.Windows.Controls.Canvas> 콘텐츠는 충분 한 공간을 지정 해야 합니다는 <xref:System.Windows.Controls.Primitives.Popup> 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="420fb-108">In addition, the <xref:System.Windows.FrameworkElement.Margin%2A> on the <xref:System.Windows.Controls.Canvas> content must specify enough space for the <xref:System.Windows.Controls.Primitives.Popup> to rotate.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 <span data-ttu-id="420fb-109">다음 예제에서는 어떻게는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 발생 때는 <xref:System.Windows.Controls.Button> 를 클릭 하면 트리거는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션을 시작 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="420fb-109">The following example shows how a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which occurs when a <xref:System.Windows.Controls.Button> is clicked, triggers the <xref:System.Windows.Media.Animation.Storyboard> that starts the animation.</span></span>  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a><span data-ttu-id="420fb-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="420fb-110">See Also</span></span>  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Controls.Primitives.BulletDecorator>  
 <xref:System.Windows.Media.RotateTransform>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [<span data-ttu-id="420fb-111">방법 항목</span><span class="sxs-lookup"><span data-stu-id="420fb-111">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)  
 [<span data-ttu-id="420fb-112">팝업 개요</span><span class="sxs-lookup"><span data-stu-id="420fb-112">Popup Overview</span></span>](../../../../docs/framework/wpf/controls/popup-overview.md)
