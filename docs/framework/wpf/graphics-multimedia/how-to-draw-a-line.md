---
title: "방법: 선 그리기 | Microsoft Docs"
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
  - "그리기, 선"
  - "그래픽[WPF], 선"
  - "선, 그리기"
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 선 그리기
이 예제에서는 <xref:System.Windows.Shapes.Line> 요소를 사용하여 선을 그리는 방법을 보여 줍니다.  
  
 선을 그리려면 <xref:System.Windows.Shapes.Line> 요소를 만들어야 합니다.  그런 다음 <xref:System.Windows.Shapes.Line.X1%2A> 및 <xref:System.Windows.Shapes.Line.Y1%2A> 속성을 사용하여 시작점을 설정하고 <xref:System.Windows.Shapes.Line.X2%2A> 및 <xref:System.Windows.Shapes.Line.Y2%2A> 속성을 사용하여 끝점을 설정합니다.  마지막으로, 스트로크가 없으면 선이 표시되지 않으므로 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>를 설정합니다.  
  
 선에는 내부 영역이 없기 때문에 선에 <xref:System.Windows.Shapes.Shape.Fill%2A> 요소를 설정하는 것은 아무런 의미가 없습니다.  
  
 다음 예제는 <xref:System.Windows.Controls.Canvas> 요소 안에 세 줄을 그립니다.  
  
## 예제  
 [!code-xml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 이 예제는 큰 샘플의 일부입니다. 전체 샘플을 보려면 [Shape Elements 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Shapes.Line>   
 [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037)