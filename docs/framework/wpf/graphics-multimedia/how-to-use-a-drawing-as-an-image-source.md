---
title: "방법: 그림을 이미지 소스로 사용 | Microsoft Docs"
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
  - "그리기, 이미지 소스로"
  - "그래픽, 그리기, 이미지 소스로"
  - "이미지 소스, 그리기"
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 그림을 이미지 소스로 사용
이 예제에서는 <xref:System.Windows.Media.Drawing>을 <xref:System.Windows.Controls.Image> 컨트롤의<xref:System.Windows.Controls.Image.Source%2A>로 사용하는 방법을 보여 줍니다.  <xref:System.Windows.Controls.Image> 컨트롤을 사용하여 <xref:System.Windows.Media.Drawing>을 표시하려면 <xref:System.Windows.Media.DrawingImage>를 <xref:System.Windows.Controls.Image> 컨트롤의 <xref:System.Windows.Controls.Image.Source%2A>로 사용하고 <xref:System.Windows.Media.DrawingImage> 개체의 <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=fullName> 속성을 표시할 그리기로 설정하십시오.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.DrawingImage> 및 <xref:System.Windows.Controls.Image> 컨트롤을 사용하여 <xref:System.Windows.Media.GeometryDrawing>을 표시합니다.  이 예제의 결과는 다음과 같습니다.  
  
 ![타원 두 개의 GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## 참고 항목  
 <xref:System.Windows.Freezable.Freeze%2A>   
 [ImageDrawing을 사용하여 이미지 그리기](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)   
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [PresentationOptions:Freeze 특성](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)