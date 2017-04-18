---
title: "방법: 개체 회전 | Microsoft Docs"
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
  - "그래픽, 개체 회전"
  - "개체 회전"
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 개체 회전
이 예제에서는 개체를 회전하는 방법을 보여 줍니다.  예제에서는 우선 <xref:System.Windows.Media.RotateTransform>을 만든 다음 <xref:System.Windows.Media.RotateTransform.Angle%2A>을 도 단위로 지정합니다.  
  
 다음 예제에서는 <xref:System.Windows.Shapes.Polyline> 개체를 왼쪽 위 모퉁이를 중심으로 45도 회전합니다.  
  
## 예제  
 [!code-xml[Transforms_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <xref:System.Windows.Media.RotateTransform>의 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성은 개체가 회전하는 중심 점을 지정합니다.  이 중심 점은 변환된 요소의 좌표 공간으로 표현됩니다.  기본적으로 회전은 변환할 개체의 왼쪽 위 모퉁이인 \(0,0\)에 적용됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Shapes.Polyline> 개체를 \(25,50\) 지점을 중심으로 45도 시계 방향으로 회전합니다.  
  
 [!code-xml[Transforms_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 다음 그림에서는 두 개체에 <xref:System.Windows.Media.Transform>을 적용한 결과를 보여 줍니다.  
  
 ![여러 중심점을 사용한 45도 회전](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.png "wcpsdk\_graphicsmm\_rotatetransform45degrees")  
서로 다른 회전 중심을 기준으로 45도 회전하는 두 개체  
  
 이전 예제에서 <xref:System.Windows.Shapes.Polyline>은 <xref:System.Windows.UIElement>입니다.  <xref:System.Windows.Media.Transform>을 <xref:System.Windows.UIElement>의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 적용하면 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성을 사용하여 요소에 적용하는 모든 <xref:System.Windows.Media.Transform>의 원점을 지정할 수 있습니다.  <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성은 상대 좌표를 사용하므로 크기를 모르더라도 요소의 중심에 변환을 적용할 수 있습니다.  자세한 내용과 예제는 [상대 값을 사용하여 변환 원점 지정](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-the-origin-of-a-transform-by-using-relative-values.md)을 참조하십시오.  
  
 전체 샘플을 보려면 [2\-D Transforms 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Transform>   
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)