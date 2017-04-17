---
title: "방법: 상대 값을 사용하여 변환 원점 지정 | Microsoft Docs"
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
  - "그래픽, 변환 원본"
  - "변환 원본"
  - "변환, 원본"
ms.assetid: f4dbc29d-93c7-41cd-96d8-5cfd8624b470
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 상대 값을 사용하여 변환 원점 지정
이 예제에서는 상대 값을 사용하여 <xref:System.Windows.FrameworkElement>에 적용되는 <xref:System.Windows.UIElement.RenderTransform%2A>의 원점을 지정하는 방법을 보여 줍니다.  
  
 <xref:System.Windows.UIElement.RenderTransform%2A> 속성을 사용하여 <xref:System.Windows.FrameworkElement>에 대해 회전, 확장 또는 [기울이기](GTMT)를 수행할 때 기본 설정은 요소의 왼쪽 위 모퉁이에 변환을 적용하는 것입니다.  요소의 중심에서 회전, 확장 또는 기울이기를 수행하려는 경우에는 변환의 중심을 요소의 중심으로 설정하여 조정할 수 있습니다.  하지만 이렇게 하려면 요소의 크기를 알아야 합니다.  요소의 중심에 변환을 적용하는 보다 쉬운 방법은 변환 자체에 중심 값을 설정하는 대신 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성을 \(0.5, 0.5\)로 설정하는 것입니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.RotateTransform>을 사용하여 <xref:System.Windows.Controls.Button>을 시계 방향으로 45도 회전합니다.  예제에서는 중심을 지정하지 않기 때문에 단추는 왼쪽 위 모퉁이인 점 \(0, 0\)을 기준으로 회전합니다.  <xref:System.Windows.Media.RotateTransform>이 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 적용됩니다.  
  
 다음 그림에서는 다음 예제의 변환 결과를 보여 줍니다.  
  
 ![RenderTransform을 사용하여 변환된 단추](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformwithdefaultcenter.png "graphicsmm\_RenderTransformWithDefaultCenter")  
RenderTransform 속성을 사용한 시계 방향 45도 회전  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample1)]  
  
 다음 예제에서도 <xref:System.Windows.Media.RotateTransform>을 사용하여 <xref:System.Windows.Controls.Button>을 시계 방향으로 45도 회전하지만 이 예제에서는 단추의 <xref:System.Windows.UIElement.RenderTransformOrigin%2A>을 \(0.5, 0.5\)로 설정합니다.  그 결과 회전이 왼쪽 위 모퉁이가 아니라 단추의 중심에 적용됩니다.  
  
 다음 그림에서는 다음 예제의 변환 결과를 보여 줍니다.  
  
 ![가운데를 중심으로 변환된 단추](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rendertransformrelativecenter.png "graphicsmm\_RenderTransformRelativeCenter")  
RenderTransformOrigin이 \(0.5, 0.5\)인 RenderTransform 속성을 사용한 45도 회전  
  
 [!code-xml[Transforms_snip#GraphicsMMRotateButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/ButtonRotateTransformExample.xaml#graphicsmmrotatebuttonexample2)]  
  
 <xref:System.Windows.FrameworkElement> 개체 변환에 대한 자세한 내용은 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Transform>   
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)