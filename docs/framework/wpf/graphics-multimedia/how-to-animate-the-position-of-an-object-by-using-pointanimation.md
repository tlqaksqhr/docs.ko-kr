---
title: "방법: PointAnimation을 사용하여 개체 위치에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "애니메이션, PointAnimation"
  - "클래스, PointAnimation"
  - "그래픽[WPF], 애니메이션"
  - "PointAnimation 클래스"
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: PointAnimation을 사용하여 개체 위치에 애니메이션 효과 주기
이 예제에서는 <xref:System.Windows.Media.Animation.PointAnimation> 클래스를 사용하여 <xref:System.Windows.Shapes.Path> 경로를 따라 개체에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Shapes.Path>를 따라 화면의 한 지점에서 다른 지점으로 타원을 이동합니다.  이 예제에서는 <xref:System.Windows.Media.Animation.PointAnimation>을 사용하여 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성에 애니메이션 효과를 적용함으로써 <xref:System.Windows.Media.EllipseGeometry>의 위치에 애니메이션 효과를 줍니다.  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.PointAnimation>   
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.EllipseGeometry>   
 <xref:System.Windows.Media.EllipseGeometry.Center%2A>   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [그래픽 및 멀티미디어](../../../../docs/framework/wpf/graphics-multimedia/index.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)   
 [Animation and Timing](http://msdn.microsoft.com/ko-kr/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)