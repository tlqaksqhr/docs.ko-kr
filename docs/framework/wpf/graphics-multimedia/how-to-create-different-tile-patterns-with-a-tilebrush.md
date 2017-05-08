---
title: "방법: TileBrush로 다른 바둑판식 배열 패턴 만들기 | Microsoft Docs"
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
  - "만들기, TileBrush로 바둑판 패턴"
  - "바둑판 패턴, 만들기"
  - "TileBrush, 바둑판 패턴 만들기"
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: TileBrush로 다른 바둑판식 배열 패턴 만들기
이 예제에서는 <xref:System.Windows.Media.TileBrush>의 <xref:System.Windows.Media.TileBrush.TileMode%2A> 속성을 사용하여 패턴을 만드는 방법을 보여 줍니다.  
  
 <xref:System.Windows.Media.TileBrush.TileMode%2A> 속성을 사용하면 <xref:System.Windows.Media.TileBrush>의 콘텐츠가 반복되는 방법, 즉 출력 영역을 채우도록 바둑판식으로 배열되는 방법을 지정할 수 있습니다.  패턴을 만들려면 <xref:System.Windows.Media.TileBrush.TileMode%2A>를 <xref:System.Windows.Media.TileMode>, <xref:System.Windows.Media.TileMode>, <xref:System.Windows.Media.TileMode> 또는 <xref:System.Windows.Media.TileMode>로 설정합니다.  그리는 영역보다 작게 나타나도록 <xref:System.Windows.Media.TileBrush>의 <xref:System.Windows.Media.TileBrush.Viewport%2A>도 설정해야 합니다. 그렇지 않으면 사용한 <xref:System.Windows.Media.TileBrush.TileMode%2A> 설정에 관계없이 바둑판이 하나만 생성됩니다.  
  
## 예제  
 다음 예제에서는 다섯 개의 <xref:System.Windows.Media.DrawingBrush> 개체를 만들고 각 개체에 서로 다른 <xref:System.Windows.Media.TileBrush.TileMode%2A> 설정을 지정하여 다섯 개의 사각형을 만드는 데 사용합니다.  이 예제에서는 <xref:System.Windows.Media.DrawingBrush> 클래스를 사용하여 <xref:System.Windows.Media.TileBrush.TileMode%2A> 동작을 보여 주지만 <xref:System.Windows.Media.TileBrush.TileMode%2A> 속성은 모든 <xref:System.Windows.Media.TileBrush> 개체, 즉 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush> 및 <xref:System.Windows.Media.DrawingBrush>에 대해 동일하게 작동합니다.  
  
 다음 그림에서는 이 예제가 만들어내는 결과를 보여 줍니다.  
  
 ![TileBrush 바둑판식 배열 예제 출력](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm\_DrawingBrushTileModeExample")  
TileMode 속성을 사용하여 만든 바둑판식 배열 패턴  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## 참고 항목  
 [TileBrush의 바둑판 크기 설정](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)   
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)