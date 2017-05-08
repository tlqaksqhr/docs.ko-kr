---
title: "방법: 사각형에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "애니메이션, 사각형"
  - "사각형, 애니메이션 적용"
ms.assetid: 572ffb95-790d-4ace-adbf-b2ea8a90e75b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 사각형에 애니메이션 효과 주기
이 예제에서는 사각형의 크기와 위치의 변경에 대해 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.RectAnimation> 클래스의 인스턴스를 사용하여 <xref:System.Windows.Media.RectangleGeometry>의 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 속성에 애니메이션 효과를 줌으로써 사각형의 해당 크기와 위치의 변경에 대해 애니메이션 효과를 적용합니다.  
  
 [!code-csharp[BasicAnimations_snip#RectAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/RectAnimationExample.cs#rectanimationwholepage)]
 [!code-vb[BasicAnimations_snip#RectAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/RectAnimationExample.vb#rectanimationwholepage)]  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.RectAnimation>   
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>   
 <xref:System.Windows.Media.RectangleGeometry>   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [그래픽 및 멀티미디어](../../../../docs/framework/wpf/graphics-multimedia/index.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)   
 [Animation and Timing](http://msdn.microsoft.com/ko-kr/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)