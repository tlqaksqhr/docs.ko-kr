---
title: "방법: BorderThickness 값에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "애니메이션, 테두리 두께 변경"
  - "테두리 두께, 변경 내용에 애니메이션 적용"
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: BorderThickness 값에 애니메이션 효과 주기
이 예제에서는 <xref:System.Windows.Media.Animation.ThicknessAnimation> 클래스를 사용하여 테두리 두께 변화에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.ThicknessAnimation>을 사용하여 테두리 두께에 애니메이션 효과를 줍니다.  예제에서는 <xref:System.Windows.Controls.Border>의 <xref:System.Windows.Controls.Border.BorderThickness%2A> 속성을 사용합니다.  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 전체 샘플을 보려면 [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.ThicknessAnimation>   
 <xref:System.Windows.Controls.Border.BorderThickness%2A>   
 <xref:System.Windows.Controls.Border>   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Animation and Timing](http://msdn.microsoft.com/ko-kr/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)   
 [키 프레임을 사용하여 테두리 두께에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)