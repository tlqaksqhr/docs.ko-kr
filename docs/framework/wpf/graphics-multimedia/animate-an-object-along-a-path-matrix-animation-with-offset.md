---
title: "방법: 경로를 따라 개체에 애니메이션 효과 주기(오프셋이 누적된 매트릭스 애니메이션) | Microsoft Docs"
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
  - "오프셋 누적"
  - "애니메이션, 개체 (오프셋이 누적 된 매트릭스 애니메이션) 경로 따라"
  - "오프셋이 누적되는 매트릭스 애니메이션"
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 경로를 따라 개체에 애니메이션 효과 주기(오프셋이 누적된 매트릭스 애니메이션)
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 클래스를 경로 따라 개체에 애니메이션 효과 적용 및 오프셋을 누적 애니메이션이 반복 됨 값입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 애니메이션을 적용할 개체는 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 속성은 <xref:System.Windows.Media.MatrixTransform> 단추에 적용 합니다. 결과적으로, 단추 곡선된 경로 따라 이동합니다.  
  
 또한이 예제에서는 설정의 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> 속성을 `true`, 누적 애니메이션이 반복 됨에 따라 애니메이션된 매트릭스의 오프셋이 있습니다. 오프셋이 누적 되므로 단추 시작 위치를 다시 설정 하는 대신 애니메이션 반복 될 때 화면에서 멀리 이동 합니다.  
  
 [!code-xml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 하지만 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> 속성을 사용 하면 여러 번의 반복을 통해 누적 오프셋된 값, 회전 값은 누적을 발생 하지 않습니다. 회전 값을 누적 하려면 애니메이션의 설정 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 및 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> 속성을 `true`합니다.  
  
 전체 샘플을 참조 하십시오. [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)합니다. 애니메이션을 적용 하는 방법을 보여 주는 예제는 <xref:System.Windows.Media.Matrix> 오프셋이 누적 하지 않고 경로 따라 값을 참조 하십시오 [개체를 따라는 경로 (매트릭스 애니메이션)에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [경로 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)