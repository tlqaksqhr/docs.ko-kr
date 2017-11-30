---
title: "방법: 경로를 따라 개체에 애니메이션 효과 주기(포인트 애니메이션)"
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
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47cafab505bcbab7008385393bbacf093e264cd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a>방법: 경로를 따라 개체에 애니메이션 효과 주기(포인트 애니메이션)
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 애니메이션 효과를 줄 개체는 <xref:System.Windows.Point> 곡선된 경로 따라 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 이동는 <xref:System.Windows.Media.EllipseGeometry> 에 정의 된 경로 따라는 <xref:System.Windows.Media.PathGeometry>합니다. 타원 기 하 도형의 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성을는 <xref:System.Windows.Point> ; 애니메이션 효과 주기 있습니다 타원 기를 이동 하려면 해당 위치를 지정, 값의 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성입니다. 이 예제에서는 사용는 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 애니메이션 효과를 줄의 <xref:System.Windows.Media.EllipseGeometry> 개체의 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성입니다.  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 전체 샘플을 참조 하십시오. [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)합니다.  
  
 사용 되는 이전 샘플의 코드 버전은 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션 효과를 줄의 <xref:System.Windows.Media.EllipseGeometry>하나만 애니메이션이 적용 된 경우에 합니다. A <xref:System.Windows.Media.Animation.Storyboard> 동일한 이러한 애니메이션을 제어할 수 있으므로 여러 애니메이션을 적용 하는 가장 쉬운 방법은 방식은 <xref:System.Windows.Media.Animation.Storyboard>합니다. 그러나 코드를 사용 하는 경우 단일 애니메이션 속성에 적용할 수 있는 더욱 손쉬운 방법을 사용 하는 것은 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드. 예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [경로 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
