---
title: "방법: 기하학적 경로를 사용하여 개체 회전 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "기하학적 경로 개체 회전"
  - "기하학적 경로를 기준으로 개체 회전"
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 기하학적 경로를 사용하여 개체 회전
이 예제에서 정의 된 기하학적 경로 따라 개체 회전 (피벗) 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.PathGeometry> 개체입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 세 개의 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 사각형 기하학적 경로 따라 이동 하는 개체입니다.  
  
-   첫 번째 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 애니메이션을 적용 한 <xref:System.Windows.Media.RotateTransform> 사각형에 적용 되는 합니다. 애니메이션 각도 값을 생성합니다. 경로 따라 회전 (피벗) 사각형을 수 있습니다.  
  
-   다른 두 개체에 애니메이션 효과 주기는 <xref:System.Windows.Media.TranslateTransform.X%2A> 및 <xref:System.Windows.Media.TranslateTransform.Y%2A> 의 값을 <xref:System.Windows.Media.TranslateTransform> 사각형에 적용 되는 합니다. 경로 따라 가로 및 세로로 이동 하는 사각형을 확인 합니다.  
  
 [!code-xml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 기하학적 경로 사용 하 여 개체를 회전 하는 다른 방법은 사용 하는 것을 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 개체 및 설정의 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 속성을 `true`합니다. 자세한 내용 및 예제에 대 한 참조 [기하학적 경로 (매트릭스 애니메이션)를 사용 하 여 개체 회전](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md)합니다.  
  
 전체 샘플을 참조 하십시오. [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)   
 [경로 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)