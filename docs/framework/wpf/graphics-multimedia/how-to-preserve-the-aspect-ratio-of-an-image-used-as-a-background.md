---
title: "방법: 배경으로 사용된 이미지의 가로 세로 비율 유지 | Microsoft Docs"
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
  - "배경 이미지의 가로 세로 비율, 유지"
  - "배경 이미지, 가로 세로 비율 유지"
  - "브러시, 배경 이미지의 가로 세로 비율 유지"
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 배경으로 사용된 이미지의 가로 세로 비율 유지
이 예제에서는 <xref:System.Windows.Media.ImageBrush>의 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 사용하여 이미지의 [가로 세로 비율](GTMT)을 유지하는 방법을 보여 줍니다.  
  
 기본적으로 <xref:System.Windows.Media.ImageBrush>를 사용하여 영역을 그리는 경우 출력 영역을 완전히 채우도록 영역의 내용이 늘어납니다.  출력 영역과 이미지의 [가로 세로 비율](GTMT)이 다르면 이러한 늘이기로 인해 이미지가 왜곡됩니다.  
  
 <xref:System.Windows.Media.ImageBrush>가 이미지의 가로 세로 비율을 유지하도록 하려면 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성을 <xref:System.Windows.Media.Stretch> 또는 <xref:System.Windows.Media.Stretch>로 설정합니다.  
  
## 예제  
 다음 예제에서는 두 개의 <xref:System.Windows.Media.ImageBrush> 개체를 사용하여 두 개의 사각형을 그립니다.  각 사각형의 너비와 높이는 300 x 150[픽셀](GTMT)이고 각 사각형 안에는 300 x 300픽셀의 이미지가 포함됩니다.  첫 번째 브러시의 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성은 <xref:System.Windows.Media.Stretch>으로 설정되어 있고 두 번째 브러시의 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성은 <xref:System.Windows.Media.Stretch>로 설정되어 있습니다.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 다음 그림에서는 <xref:System.Windows.Media.TileBrush.Stretch%2A> 설정이 <xref:System.Windows.Media.Stretch>인 첫 번째 브러시의 출력을 보여 줍니다.  
  
 ![Uniform 늘이기를 사용한 ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.png "graphicsmm\_ImageBrushUniformStretch")  
  
 다음 그림에서는 <xref:System.Windows.Media.TileBrush.Stretch%2A> 설정이 <xref:System.Windows.Media.Stretch>인 두 번째 브러시의 출력을 보여 줍니다.  
  
 ![UniformToFill 늘이기를 사용한 ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.png "graphicsmm\_ImageBrushUniformToFillStretch")  
  
 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성은 <xref:System.Windows.Media.DrawingBrush> 및 <xref:System.Windows.Media.VisualBrush> 등 다른 <xref:System.Windows.Media.TileBrush> 개체에 대해서도 동일하게 작동합니다.  <xref:System.Windows.Media.ImageBrush> 및 다른 <xref:System.Windows.Media.TileBrush> 개체에 대한 자세한 내용은 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)를 참조하십시오.  
  
 또한 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성이 <xref:System.Windows.Media.TileBrush>의 내용을 해당 출력 영역에 맞게 늘리는 방법을 지정하는 것처럼 보이지만 실제로는 <xref:System.Windows.Media.TileBrush>가 해당 기본 바둑판식 배열에 맞게 내용을 늘리는 방법을 지정합니다.  자세한 내용은 <xref:System.Windows.Media.TileBrush>를 참조하십시오.  
  
 이 코드 예제는 <xref:System.Windows.Media.ImageBrush> 클래스에 대해 제공되는 보다 큰 예제의 일부입니다.  전체 샘플을 보려면 [ImageBrush 샘플](http://go.microsoft.com/fwlink/?LinkID=160005)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.TileBrush>   
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)