---
title: "방법: 타원 또는 원 그리기 | Microsoft Docs"
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
  - "원, 그리기"
  - "원 그리기"
  - "타원 그리기"
  - "타원, 그리기"
  - "그래픽, 원 그리기"
  - "그래픽, 타원 그리기"
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 타원 또는 원 그리기
이 예제에서는 <xref:System.Windows.Shapes.Ellipse> 요소를 사용하여 타원 및 원을 그리는 방법을 보여 줍니다.  타원을 그리려면 <xref:System.Windows.Shapes.Ellipse> 요소를 만들고 이 요소의 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A>를 지정합니다.  타원 내부를 칠하는 데 사용할 <xref:System.Windows.Media.Brush>를 지정하려면 이 요소의 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성을 사용합니다.  타원의 윤곽선을 칠하는 데 사용할 <xref:System.Windows.Media.Brush>를 지정하려면 이 요소의 <xref:System.Windows.Shapes.Shape.Stroke%2A> 속성을 사용합니다.  <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성은 타원 윤곽선의 두께를 지정합니다.  
  
 원을 그리려면 <xref:System.Windows.Shapes.Ellipse> 요소의 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A>를 서로 동일하게 지정합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Canvas> 안에 네 개의 <xref:System.Windows.Shapes.Ellipse> 요소를 그립니다.  
  
## 예제  
 [!code-xml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 이 예제에서는 <xref:System.Windows.Controls.Canvas>에 타원을 넣었지만 텍스트가 아닌 콘텐츠를 지원하는 모든 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control>을 타원 요소뿐만 아니라 기타 모든 도형 요소와 함께 사용할 수 있습니다.  
  
 이 예제는 큰 샘플의 일부입니다. 전체 샘플을 보려면 [Shape Elements 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Shapes.Ellipse>   
 <xref:System.Windows.Shapes.Shape>   
 [Shape Elements 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)