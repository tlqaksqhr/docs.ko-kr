---
title: "방법: TileBrush의 바둑판 크기 설정 | Microsoft Docs"
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
  - "TileBrush, 타일 크기"
  - "TileBrush의 Viewport 속성"
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: TileBrush의 바둑판 크기 설정
이 예제에서는 <xref:System.Windows.Media.TileBrush>의 바둑판 크기를 설정하는 방법을 보여 줍니다.  <xref:System.Windows.Media.TileBrush>는 현재 그리고 있는 영역을 완전히 채우는 단일 바둑판을 생성합니다.  <xref:System.Windows.Media.TileBrush.Viewport%2A> 및 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 속성을 설정하면 이 동작을 재정의할 수 있습니다.  
  
 <xref:System.Windows.Media.TileBrush.Viewport%2A> 속성은 <xref:System.Windows.Media.TileBrush>의 바둑판 크기를 지정합니다.  기본적으로 <xref:System.Windows.Media.TileBrush.Viewport%2A> 속성의 값은 그리고 있는 영역의 크기에 상대적입니다.  <xref:System.Windows.Media.TileBrush.Viewport%2A> 속성에서 절대적인 바둑판 크기를 지정하도록 하려면 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 속성을 <xref:System.Windows.Media.BrushMappingMode>로 설정하십시오.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.TileBrush> 형식의 <xref:System.Windows.Media.ImageBrush>를 사용하여 사각형을 바둑판으로 그립니다.  또한 각 바둑판을 출력 영역\(사각형\)의 가로 50퍼센트, 세로 50퍼센트로 설정합니다.  그 결과 사각형에 네 개의 이미지가 그려집니다.  
  
 다음 그림에서는 이 예제의 출력을 보여 줍니다.  
  
 ![이미지 브러시를 사용한 바둑판식 배열 예제](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 다음 예제에서는 <xref:System.Windows.Media.ImageBrush>를 만들고 <xref:System.Windows.Media.TileBrush.Viewport%2A>를 `0,0,25,25`로, <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>를 <xref:System.Windows.Media.BrushMappingMode>로 설정한 다음 이를 사용하여 다른 사각형을 그립니다.  그 결과로 가로 25 [픽셀](GTMT), 세로 25 [픽셀](GTMT)인 바둑판이 브러시를 통해 만들어집니다.  
  
 다음 그림에서는 이 예제의 출력을 보여 줍니다.  
  
 ![Viewport가 0,0,0.25,0.25인 바둑판 모양의 TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 앞의 예제들은 보다 큰 샘플의 일부입니다.  전체 샘플을 보려면 [ImageBrush 샘플](http://go.microsoft.com/fwlink/?LinkID=160005)을 참조하십시오.  
  
 이 예제에서는 <xref:System.Windows.Media.ImageBrush> 클래스를 사용하지만 <xref:System.Windows.Media.TileBrush.Viewport%2A> 및 <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> 속성은 다른 <xref:System.Windows.Media.TileBrush> 개체, 즉 <xref:System.Windows.Media.DrawingBrush> 및 <xref:System.Windows.Media.VisualBrush>에 대해서도 동일하게 동작합니다.  <xref:System.Windows.Media.ImageBrush> 및 다른 <xref:System.Windows.Media.TileBrush> 개체에 대한 자세한 내용은 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.TileBrush>   
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [TileBrush로 다른 바둑판식 배열 패턴 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-different-tile-patterns-with-a-tilebrush.md)