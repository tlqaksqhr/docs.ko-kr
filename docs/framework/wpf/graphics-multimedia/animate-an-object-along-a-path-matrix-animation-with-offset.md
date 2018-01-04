---
title: "방법: 경로를 따라 개체에 애니메이션 효과 주기(오프셋이 누적된 매트릭스 애니메이션)"
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
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5259e930060a8ac6118d232f08d02193a6a1b300
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a>방법: 경로를 따라 개체에 애니메이션 효과 주기(오프셋이 누적된 매트릭스 애니메이션)
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 반복 경로 따라 개체를 해당 오프셋 누적 애니메이션이 클래스 값입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 애니메이션 효과를 줄 개체는 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 속성은 <xref:System.Windows.Media.MatrixTransform> 단추에 적용 합니다. 그 결과 단추가 곡선 경로를 따라 움직입니다.  
  
 또한이 예제에서는 설정는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> 속성을 `true`, 애니메이션 반복에 따라 누적에 애니메이션 효과 준된 매트릭스의 오프셋이 있습니다. 오프셋이 누적되므로 애니메이션이 반복되면 단추는 시작 위치로 재설정되는 것이 아니라 화면을 가로질러 더 크게 움직입니다.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 없지만 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> 속성 반복 해 서 축적 오프셋된 값으로 인해, 회전 값은 누적 발생 하지 않는 것입니다. 누적 회전 값을 설정 애니메이션의 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 및 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> 속성을 `true`합니다.  
  
 전체 샘플을 참조 하십시오. [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)합니다. 애니메이션 효과 적용 하는 방법을 보여 주는 예제는 <xref:System.Windows.Media.Matrix> 오프셋이 누적 없이 경로 따라 값을 참조 [애니메이션 개체를 따라 정도 경로 (매트릭스 애니메이션)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [경로 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
