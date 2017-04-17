---
title: "방법: 줄 또는 세그먼트 끝에서 끝 모양 수정 | Microsoft Docs"
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
  - "그래픽, Shape 끝 모양"
  - "Shape 요소, 끝 모양"
  - "Shape 요소, 끝"
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 줄 또는 세그먼트 끝에서 끝 모양 수정
이 예제에서는 열린 <xref:System.Windows.Shapes.Shape> 요소의 시작 또는 끝 모양을 수정하는 방법을 보여 줍니다.  열린 <xref:System.Windows.Shapes.Shape> 시작 부분의 끝 모양을 변경하려면 <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> 속성을 사용합니다.  열린 <xref:System.Windows.Shapes.Shape> 끝 부분의 끝 모양을 변경하려면 <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> 속성을 사용합니다.  사용 가능한 선의 끝 모양을 보려면 <xref:System.Windows.Media.PenLineCap> 열거형을 참조하십시오.  
  
> [!NOTE]
>  이 속성은 <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline> 또는 열린 <xref:System.Windows.Shapes.Path> 요소 같은 열린 도형에만 적용됩니다.  
  
 다음 예제에서는 네 개의 <xref:System.Windows.Shapes.Polyline> 요소를 그리고, 각 끝에 서로 다른 도형 집합을 사용합니다.  
  
## 예제  
 [!code-xml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 이 예제는 큰 샘플의 일부입니다. 전체 샘플을 보려면 [Shape Elements 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Shapes.Polyline>   
 <xref:System.Windows.Media.PenLineCap>