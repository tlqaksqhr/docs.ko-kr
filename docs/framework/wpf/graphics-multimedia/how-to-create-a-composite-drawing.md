---
title: "방법: 합성 그리기 만들기 | Microsoft Docs"
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
  - "클래스, DrawingGroup"
  - "합성 그리기"
  - "DrawingGroup 클래스"
  - "그리기, 복합"
  - "그래픽, 합성 그리기"
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 합성 그리기 만들기
이 예제에서는 <xref:System.Windows.Media.DrawingGroup>을 통해 여러 <xref:System.Windows.Media.Drawing> 개체를 단일 합성 그리기로 결합하여 복잡한 그리기를 만드는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.DrawingGroup>을 사용하여 <xref:System.Windows.Media.GeometryDrawing> 및 <xref:System.Windows.Media.ImageDrawing> 개체로 합성 그리기를 만듭니다.  다음 그림에서는 이 예제가 만들어내는 결과를 보여 줍니다.  
  
 ![여러 개의 그리기가 있는 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.png "graphicsmm\_simple")  
DrawingGroup을 사용하여 만든 합성 그리기  
  
 회색 테두리는 그리기의 경계를 나타냅니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <xref:System.Windows.Media.DrawingGroup>을 사용하면 포함된 그리기에 <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> 설정, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A> 또는 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>을 적용할 수 있습니다.  <xref:System.Windows.Media.DrawingGroup>도 <xref:System.Windows.Media.Drawing>이기 때문에 다른 <xref:System.Windows.Media.DrawingGroup> 개체를 포함할 수 있습니다.  
  
 다음 예제는 이전 예제와 유사하지만 추가 <xref:System.Windows.Media.DrawingGroup> 개체를 사용하여 일부 그리기에 비트맵 효과와 불투명 마스크를 적용했습니다.  다음 그림에서는 이 예제가 만들어내는 결과를 보여 줍니다.  
  
 ![여러 개의 그리기가 있는 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.png "graphicsmm\_multiple")  
여러 DrawingGroup 개체로 구성된 합성 그리기  
  
 회색 테두리는 그리기의 경계를 나타냅니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 <xref:System.Windows.Media.Drawing> 개체에 대한 자세한 내용은 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>   
 <xref:System.Windows.Media.DrawingGroup.Transform%2A>   
 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>   
 <xref:System.Windows.Media.DrawingGroup.Opacity%2A>   
 <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>   
 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>   
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)