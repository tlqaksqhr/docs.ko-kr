---
title: "방법: 경로를 따라 개체에 애니메이션 효과 주기(Double 애니메이션)"
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
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 60f662562422169bc7b234ed0136797294f0b39a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a>방법: 경로를 따라 개체에 애니메이션 효과 주기(Double 애니메이션)
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 클래스에 정의 된 경로 따라 개체를 이동 하는 <xref:System.Windows.Media.PathGeometry>합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 두 개의 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 사각형 기하학적 경로 따라 이동 하는 개체:  
  
-   첫 번째 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 애니메이션 효과 적용 된 <xref:System.Windows.Media.TranslateTransform.X%2A> 의 <xref:System.Windows.Media.TranslateTransform> 는 사각형에 적용 합니다. 이를 통해 사각형이 경로를 따라 가로로 이동하게 됩니다.  
  
-   두 번째 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 애니메이션 효과 적용 된 <xref:System.Windows.Media.TranslateTransform.Y%2A> 의 <xref:System.Windows.Media.TranslateTransform> 는 사각형에 적용 합니다. 이를 통해 사각형이 경로를 따라 세로로 이동하게 됩니다.  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 전체 샘플을 참조 하십시오. [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)합니다.  
  
 기하학적 경로 사용 하는 개체를 이동 하는 다른 방법은 사용 하는 것을 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 개체입니다. 예를 들어 참조 [애니메이션 개체를 따라 정도 경로 (매트릭스 애니메이션)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [경로 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
