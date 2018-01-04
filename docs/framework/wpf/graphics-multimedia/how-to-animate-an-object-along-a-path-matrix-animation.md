---
title: "방법: 경로를 따라 개체에 애니메이션 효과 주기(매트릭스 애니메이션)"
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
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eb1bbe43c7e1797d5943bf3da6b4aca22a11c3a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a>방법: 경로를 따라 개체에 애니메이션 효과 주기(매트릭스 애니메이션)
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 클래스에서 정의 된 경로 따라 개체를 애니메이션 효과를 주는 <xref:System.Windows.Media.PathGeometry>합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 다음을 수행하여 경로를 따라 개체에 애니메이션 효과를 줍니다.  
  
-   적용 한 <xref:System.Windows.Media.MatrixTransform> 개체로 이동할 수 있도록 합니다.  
  
-   경로 사용 하 여 정의 <xref:System.Windows.Media.PathGeometry>합니다.  
  
-   만듭니다는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 애니메이션 효과를 사용 하 여는 <xref:System.Windows.Media.Matrix> 의 속성은 <xref:System.Windows.Media.MatrixTransform>합니다. <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 사용는 <xref:System.Windows.Media.PathGeometry> 사용 하 여 생성 하 고 <xref:System.Windows.Media.Matrix> 값입니다.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 전체 샘플을 참조 하십시오. [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)합니다. 기하학적 경로 대 한 자세한 내용은 참조는 [기 하 도형 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [경로 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
