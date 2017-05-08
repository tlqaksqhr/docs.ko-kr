---
title: "방법: 이벤트가 발생할 때 요소에 변환 적용 | Microsoft Docs"
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
  - "그래픽, 이벤트 응답으로 변환"
  - "LayoutTransform 속성"
  - "속성, LayoutTransform"
  - "속성, RenderTransform"
  - "RenderTransform 속성"
  - "이벤트 응답으로 변환"
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 이벤트가 발생할 때 요소에 변환 적용
이 예제에서는 이벤트가 발생할 때 <xref:System.Windows.Media.ScaleTransform>을 적용하는 방법을 보여 줍니다.  여기에서 보여 주는 개념은 다른 형식의 변환을 적용할 때 사용하는 개념과 동일합니다.  사용 가능한 변환 형식에 대한 자세한 내용은 <xref:System.Windows.Media.Transform> 클래스 또는 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)를 참조하십시오.  
  
 다음 두 가지 방법 중 하나를 사용하여 요소에 변환을 적용할 수 있습니다.  
  
-   레이아웃에 변환을 적용하지않으려면 요소의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성을 사용합니다.  
  
-   레이아웃에 변환을 적용하려면 요소의 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 속성을 사용합니다.  
  
 다음 예제에서는 단추의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 <xref:System.Windows.Media.ScaleTransform>을 적용합니다.  마우스를 단추 위로 이동하면 <xref:System.Windows.Media.ScaleTransform>의 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 및 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 속성이 `2`로 설정되어 단추가 더 커집니다.  마우스를 단추 바깥쪽으로 이동하면 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 및 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 속성이 `1`로 설정되어 단추가 원래 크기로 돌아갑니다.  
  
## 예제  
 [!code-xml[ButtonTransform#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## 참고 항목  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.ScaleTransform>   
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)   
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)