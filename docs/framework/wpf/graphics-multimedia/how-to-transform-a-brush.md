---
title: "방법: 브러시 변환 | Microsoft Docs"
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
  - "브러시, 콘텐츠 회전"
  - "브러시, Transform 속성"
  - "브러시 콘텐츠 회전"
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 브러시 변환
이 예제에서는 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 및 <xref:System.Windows.Media.Brush.Transform%2A> 변환 속성을 사용하여 <xref:System.Windows.Media.Brush> 개체를 변환하는 방법을 보여 줍니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.RotateTransform>을 사용하여 <xref:System.Windows.Media.ImageBrush>의 콘텐츠를 45도 회전합니다.  
  
 다음 그림은 각각 <xref:System.Windows.Media.RotateTransform>이 없는 경우, <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성에 <xref:System.Windows.Media.RotateTransform>이 적용된 경우, <xref:System.Windows.Media.Brush.Transform%2A> 속성에 <xref:System.Windows.Media.RotateTransform>에 적용된 경우에 해당하는 <xref:System.Windows.Media.ImageBrush>를 보여 줍니다.  
  
 ![Brush RelativeTransform 및 Transform 설정](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk\_graphicsmm\_transformandrelativetransform")  
  
## 예제  
 첫 번째 예제에서는 <xref:System.Windows.Media.RotateTransform>을 <xref:System.Windows.Media.ImageBrush>의 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성에 적용합니다.  <xref:System.Windows.Media.RotateTransform> 개체의 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성은 모두 이 콘텐츠 중심 점의 상대적 좌표인 0.5로 설정됩니다.  그 결과 <xref:System.Windows.Media.ImageBrush> 콘텐츠가 중심 점을 기준으로 회전합니다.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 두 번째 예제에서도 <xref:System.Windows.Media.RotateTransform>을 <xref:System.Windows.Media.ImageBrush>에 적용하지만 이 예제에서는 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 속성 대신 <xref:System.Windows.Media.Brush.Transform%2A> 속성을 사용합니다.  
  
 브러시 중심을 기준으로 회전하기 위해 예제에서는 <xref:System.Windows.Media.RotateTransform> 개체의 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성을 절대 좌표로 설정합니다.  브러시는 175 x 90[픽셀](GTMT)의 사각형을 칠하기 때문에 사각형의 중심 점은 \(87.5, 45\)입니다.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <xref:System.Windows.Media.Brush.RelativeTransform%2A> 및 <xref:System.Windows.Media.Brush.Transform%2A> 속성의 작동 방식에 대한 설명은 [브러시 변환 개요](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)를 참조하십시오.  
  
 전체 샘플을 보려면 [Brushes 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)을 참조하십시오.  브러시에 대한 자세한 내용은 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)를 참조하십시오.  
  
## 참고 항목  
 [브러시 변환 개요](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)   
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)