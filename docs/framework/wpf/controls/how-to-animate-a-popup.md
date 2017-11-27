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
# <a name="how-to-animate-a-popup"></a>방법: Popup에 애니메이션 효과 주기
애니메이션 효과 적용 하는 두 가지를 보여 주는이 예제는 <xref:System.Windows.Controls.Primitives.Popup> 제어 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 <xref:System.Windows.Controls.Primitives.PopupAnimation> 속성의 값을 <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>,으로 구독이 <xref:System.Windows.Controls.Primitives.Popup> "슬라이드 기능에" 있으면 오류가 발생 합니다.  
  
 회전 하기 위해는 <xref:System.Windows.Controls.Primitives.Popup>를 지정 하는이 예제는 <xref:System.Windows.Media.RotateTransform> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에는 <xref:System.Windows.Controls.Canvas>의 자식 요소인는 <xref:System.Windows.Controls.Primitives.Popup>합니다.  
  
 이 예제에서는 제대로 작동 하려면 변환에 대 한 설정 해야 합니다는 <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> 속성을 `true`합니다. 또한는 <xref:System.Windows.FrameworkElement.Margin%2A> 에 <xref:System.Windows.Controls.Canvas> 콘텐츠는 충분 한 공간을 지정 해야 합니다는 <xref:System.Windows.Controls.Primitives.Popup> 회전 합니다.  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 다음 예제에서는 어떻게는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 발생 때는 <xref:System.Windows.Controls.Button> 를 클릭 하면 트리거는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션을 시작 하 합니다.  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Controls.Primitives.BulletDecorator>  
 <xref:System.Windows.Media.RotateTransform>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [방법 항목](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)  
 [팝업 개요](../../../../docs/framework/wpf/controls/popup-overview.md)
