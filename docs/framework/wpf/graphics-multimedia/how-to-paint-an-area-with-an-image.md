---
title: "방법: 이미지로 영역 그리기 | Microsoft Docs"
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
  - "브러시, 이미지로 그리기"
  - "이미지, 그리기"
  - "그리기, 이미지로"
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 이미지로 영역 그리기
이 예제에서는 <xref:System.Windows.Media.ImageBrush> 클래스를 사용하여 이미지로 영역을 그리는 방법을 보여 줍니다.  <xref:System.Windows.Media.ImageBrush>는 해당 <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 속성에 지정된 단일 이미지를 표시합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.ImageBrush>를 사용하여 단추의 <xref:System.Windows.Controls.Control.Background%2A>를 그립니다.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 기본적으로 <xref:System.Windows.Media.ImageBrush>는 현재 그리고 있는 영역을 완전히 채우도록 이미지를 늘립니다.  앞의 예제에서는 단추를 채우기 위해 이미지가 늘어나는데 이 경우 이미지가 왜곡될 수 있습니다.  <xref:System.Windows.Media.TileBrush>의 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 <xref:System.Windows.Media.Stretch> 또는 <xref:System.Windows.Media.Stretch>로 설정하여 브러시가 이미지의 [가로 세로 비율](GTMT)을 유지하도록 하면 이 동작을 제어할 수 있습니다.  
  
 <xref:System.Windows.Media.ImageBrush>의 <xref:System.Windows.Media.TileBrush.Viewport%2A> 및 <xref:System.Windows.Media.TileBrush.TileMode%2A> 속성을 설정하면 반복되는 패턴을 만들 수 있습니다.  다음 예제에서는 이미지에서 만들어진 패턴을 사용하여 단추를 그립니다.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <xref:System.Windows.Media.ImageBrush> 클래스에 대한 자세한 내용은 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)를 참조하십시오.  
  
 이 코드 예제는 <xref:System.Windows.Media.ImageBrush> 클래스에 대해 제공되는 보다 큰 예제의 일부입니다.  전체 샘플을 보려면 [ImageBrush 샘플](http://go.microsoft.com/fwlink/?LinkID=160005)을 참조하십시오.  
  
## 참고 항목  
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)