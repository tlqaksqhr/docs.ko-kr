---
title: "방법: 경로를 따라 개체에 애니메이션 효과 주기(Double 애니메이션) | Microsoft Docs"
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
  - "애니메이션, (double 애니메이션) 경로 따른 개체"
  - "double 애니메이션"
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 경로를 따라 개체에 애니메이션 효과 주기(Double 애니메이션)
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 클래스에 정의 된 경로 따라 개체를 이동 하는 <xref:System.Windows.Media.PathGeometry>합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 개체가 사각형 기하학적 경로 따라 이동 합니다.  
  
-   첫 번째 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 애니메이션을 적용 된 <xref:System.Windows.Media.TranslateTransform.X%2A> 의 <xref:System.Windows.Media.TranslateTransform> 는 사각형에 적용 합니다. 경로 따라 가로로 이동 하는 사각형을 수 있습니다.  
  
-   두 번째 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 애니메이션을 적용 된 <xref:System.Windows.Media.TranslateTransform.Y%2A> 의 <xref:System.Windows.Media.TranslateTransform> 는 사각형에 적용 합니다. 이 통해 사각형이 경로 따라 세로로 움직입니다.  
  
 [!code-xml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 전체 샘플을 참조 하십시오. [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)합니다.  
  
 기하학적 경로 사용 하는 개체를 이동 하는 다른 방법은 사용 하는 것을 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 개체입니다. 예를 들어 참조 [개체를 따라는 경로 (매트릭스 애니메이션)에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [경로 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)