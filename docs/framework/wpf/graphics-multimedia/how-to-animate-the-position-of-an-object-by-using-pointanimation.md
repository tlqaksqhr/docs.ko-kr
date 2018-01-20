---
title: "방법: PointAnimation을 사용하여 개체 위치에 애니메이션 효과 주기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f741770077a90bef33d75640726019496fe8eb8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a>방법: PointAnimation을 사용하여 개체 위치에 애니메이션 효과 주기
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.PointAnimation> 따라 개체를 애니메이션 효과를 줄 클래스는 <xref:System.Windows.Shapes.Path>합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 타원을 이동는 <xref:System.Windows.Shapes.Path> 한 지점에서 다른 화면에 있습니다. 이 예제에서 애니메이션 효과 적용 하의 위치는 <xref:System.Windows.Media.EllipseGeometry> 를 사용 하 여 <xref:System.Windows.Media.Animation.PointAnimation> 애니메이션 효과를 줄는 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성입니다.  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Animation.PointAnimation>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.EllipseGeometry>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A>  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [그래픽 및 멀티미디어](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)  
 [애니메이션 및 타이밍](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
