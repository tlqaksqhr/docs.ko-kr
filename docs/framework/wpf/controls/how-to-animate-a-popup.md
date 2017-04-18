---
title: "방법: Popup에 애니메이션 효과 주기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "애니메이션, Popup 컨트롤"
  - "Popup 컨트롤, 애니메이션 적용"
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: Popup에 애니메이션 효과 주기
이 예제에서는 <xref:System.Windows.Controls.Primitives.Popup> 컨트롤에 애니메이션 효과를 주는 두 가지 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.Primitives.PopupAnimation> 속성을 <xref:System.Windows.Controls.Primitives.PopupAnimation> 값으로 설정하여 <xref:System.Windows.Controls.Primitives.Popup>이 나타날 때 "슬라이드 인" 효과를 적용합니다.  
  
 <xref:System.Windows.Controls.Primitives.Popup>을 회전하기 위해 이 예제에서는 <xref:System.Windows.Controls.Primitives.Popup>의 자식 요소인 <xref:System.Windows.Controls.Canvas>의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 <xref:System.Windows.Media.RotateTransform>을 할당합니다.  
  
 제대로 변환이 수행되려면 이 예제에서 <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> 속성을 `true`로 설정해야 합니다.  또한 <xref:System.Windows.Controls.Canvas> 콘텐츠의 <xref:System.Windows.FrameworkElement.Margin%2A>은 <xref:System.Windows.Controls.Primitives.Popup>이 회전할 수 있는 충분한 공간을 지정해야 합니다.  
  
 [!code-xml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.Button>을 클릭하면 발생하는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트가 애니메이션을 시작하는 <xref:System.Windows.Media.Animation.Storyboard>를 트리거하는 방법을 보여 줍니다.  
  
 [!code-xml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## 참고 항목  
 <xref:System.Windows.UIElement.RenderTransform%2A>   
 <xref:System.Windows.Controls.Primitives.BulletDecorator>   
 <xref:System.Windows.Media.RotateTransform>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 <xref:System.Windows.Controls.Primitives.Popup>   
 [방법 항목](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)   
 [Popup 개요](../../../../docs/framework/wpf/controls/popup-overview.md)