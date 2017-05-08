---
title: "방법: ImageDrawing을 사용하여 이미지 그리기 | Microsoft Docs"
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
  - "클래스, ImageDrawing"
  - "그리기, 이미지"
  - "그래픽, 이미지 그리기"
  - "ImageDrawing 클래스"
  - "이미지, 그리기"
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: ImageDrawing을 사용하여 이미지 그리기
이 예제에서는 <xref:System.Windows.Media.ImageDrawing>을 사용하여 이미지를 그리는 방법을 보여 줍니다.  <xref:System.Windows.Media.ImageDrawing>을 사용하면 <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage> 또는 <xref:System.Windows.Media.Visual>로 <xref:System.Windows.Media.ImageSource>를 표시할 수 있습니다.  이미지를 그리려면 <xref:System.Windows.Media.ImageDrawing>을 만든 다음 해당 <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=fullName> 및 <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=fullName> 속성을 설정합니다.  <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=fullName> 속성은 그리려는 이미지를 지정하고 <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=fullName> 속성은 각 이미지의 위치와 크기를 지정합니다.  
  
## 예제  
 다음 예제에서는 4개의 <xref:System.Windows.Media.ImageDrawing> 개체를 사용하여 합성 그리기를 만듭니다.  이 예제에서 생성되는 이미지는 다음과 같습니다.  
  
 ![여러 가지 DrawingImage 개체](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.png "graphicsmm\_ImageDrawingExample")  
4개의 ImageDrawing 개체  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xml[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 <xref:System.Windows.Media.ImageDrawing>을 사용하지 않고 간단히 이미지를 표시하는 방법을 보여 주는 예제는 [Image 요소 사용](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Freezable.Freeze%2A>   
 <xref:System.Windows.Controls.Image>   
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [PresentationOptions:Freeze 특성](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)