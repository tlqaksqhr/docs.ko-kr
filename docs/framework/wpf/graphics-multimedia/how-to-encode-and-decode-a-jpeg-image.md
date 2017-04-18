---
title: "방법: JPEG 이미지 인코딩 및 디코딩 | Microsoft Docs"
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
  - "이미지 형식 디코딩"
  - "JPEG 이미지 디코딩"
  - "이미지 형식 인코딩"
  - "JPEG 이미지 인코딩"
  - "JPEG 디코딩"
  - "JPEG 인코딩"
ms.assetid: b8cfde37-9f68-4911-a05e-51d8d7bdec7b
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: JPEG 이미지 인코딩 및 디코딩
다음 예제에서는 특정 <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> 및 <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> 개체를 사용하여 [!INCLUDE[TLA#tla_jpeg](../../../../includes/tlasharptla-jpeg-md.md)] 이미지를 디코딩 및 인코딩하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서는 <xref:System.IO.FileStream>에서 <xref:System.Windows.Media.Imaging.JpegBitmapDecoder>를 사용하여 [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] 이미지를 디코딩하는 방법을 보여 줍니다.  
  
 [!code-cpp[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#1)]
 [!code-csharp[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#1)]
 [!code-vb[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#1)]  
  
## 예제  
 이 예제에서는 <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>를 사용하여 <xref:System.Windows.Media.Imaging.BitmapSource>를 [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] 이미지로 인코딩하는 방법을 보여 줍니다.  
  
 [!code-cpp[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#4)]
 [!code-csharp[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#4)]
 [!code-vb[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#4)]  
  
## .NET Framework 보안  
  
## 참고 항목  
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)