---
title: "방법: BMP 이미지 인코딩 및 디코딩 | Microsoft Docs"
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
  - "BMP 디코딩"
  - "BMP 인코딩"
  - "BMP 이미지 디코딩"
  - "이미지 형식 디코딩"
  - "BMP 이미지 인코딩"
  - "이미지 형식 인코딩"
ms.assetid: feb5ef27-28ac-40ab-bfc2-e0456990d32c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: BMP 이미지 인코딩 및 디코딩
다음 예제에서는 특정 <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> 및 <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> 개체를 사용하여 [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] 이미지를 디코딩 및 인코딩하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서는 <xref:System.Uri>에서 <xref:System.Windows.Media.Imaging.BmpBitmapDecoder>를 사용하여 [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] 이미지를 디코딩하는 방법을 보여 줍니다.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## 예제  
 이 예제에서는 <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>를 사용하여 <xref:System.Windows.Media.Imaging.BitmapSource>를 [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] 이미지로 인코딩하는 방법을 보여 줍니다.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## 참고 항목  
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)