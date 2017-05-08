---
title: "방법: Visual로 비트맵 만들기 | Microsoft Docs"
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
  - "비트맵, 표시에서 렌더링"
  - "표시, 비트맵으로 렌더링"
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: Visual로 비트맵 만들기
이 예제에서는 <xref:System.Windows.Media.Visual>로 비트맵을 만드는 방법을 보여 줍니다.  <xref:System.Windows.Media.DrawingVisual>이 <xref:System.Windows.Media.FormattedText>로 렌더링됩니다.  그런 다음 <xref:System.Windows.Media.Visual>이 <xref:System.Windows.Media.Imaging.RenderTargetBitmap>으로 렌더링되어 지정된 텍스트에 대한 비트맵이 생성됩니다.  
  
## 예제  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## 참고 항목  
 <xref:System.Windows.Media.DrawingContext>   
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)   
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [DrawingVisual 개체 사용](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)