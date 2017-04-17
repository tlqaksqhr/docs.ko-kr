---
title: "방법: 시각적 요소를 이미지 파일로 인코딩 | Microsoft Docs"
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
  - "이미지 형식 인코딩"
  - "이미지 파일, 표시에서 인코딩"
  - "표시, 이미지 파일로 인코딩"
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: 시각적 요소를 이미지 파일로 인코딩
이 예제에서는 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 및 <xref:System.Windows.Media.Imaging.PngBitmapEncoder>를 사용하여 <xref:System.Windows.Media.Visual> 개체를 이미지 파일로 인코딩하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Media.DrawingVisual>은 <xref:System.Windows.Media.Imaging.RenderTargetBitmap>으로 렌더링되는 <xref:System.Windows.Media.Imaging.BitmapImage> 및 <xref:System.Windows.Media.FormattedText>를 사용하여 만들어집니다.  그런 다음, 렌더링된 비트맵을 사용하여 <xref:System.Windows.Media.Imaging.PngBitmapEncoder>에 추가되는 <xref:System.Windows.Media.Imaging.BitmapFrame>을 만들어 새 [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] 파일을 만듭니다.  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 이 예제에서는 <xref:System.Windows.Media.Imaging.PngBitmapEncoder>가 사용되었지만 파생된 <xref:System.Windows.Media.Imaging.BitmapEncoder> 개체라면 모두 이미지 파일을 만드는 데 사용할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Media.DrawingContext>   
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)   
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [DrawingVisual 개체 사용](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)