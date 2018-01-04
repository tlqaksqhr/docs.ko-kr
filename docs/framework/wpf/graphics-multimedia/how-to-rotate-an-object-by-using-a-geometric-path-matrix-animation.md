---
title: "방법: 기하학적 경로를 사용하여 개체 회전(매트릭스 애니메이션)"
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
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c001c0969e42c1eaadad6c029ae86009176b9eb7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a>방법: 기하학적 경로를 사용하여 개체 회전(매트릭스 애니메이션)
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 및 <xref:System.Windows.Media.MatrixTransform> (피벗)에 정의 된 기하학적 경로 따라 개체를 회전 하는 <xref:System.Windows.Media.PathGeometry> 개체입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 애니메이션 효과를 줄 개체는 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 속성은 <xref:System.Windows.Media.MatrixTransform>합니다. <xref:System.Windows.Media.MatrixTransform> 곡선된 경로 따라 이동으로 인해 및 단추에 적용 됩니다. 때문에 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 속성이 `true`, 사각형 경로의 탄젠트를 따라 회전 합니다.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 전체 샘플을 참조 하십시오. [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)합니다.  
  
 사용 되는 이전 샘플의 코드 버전은 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션 효과를 줄의 <xref:System.Windows.Media.EllipseGeometry>하나만 애니메이션이 적용 된 경우에 합니다. 코드에서에서 속성에 단일 애니메이션에 적용할 수 있는 더욱 손쉬운 방법을 사용 하는 것은 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드. 예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [경로 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)
