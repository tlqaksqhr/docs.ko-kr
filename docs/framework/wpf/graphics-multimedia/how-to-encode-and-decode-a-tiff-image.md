---
title: "방법: TIFF 이미지 인코딩 및 디코딩 | Microsoft Docs"
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
  - "TIFF 이미지 디코딩"
  - "이미지 형식 인코딩"
  - "TIFF 이미지 인코딩"
  - "TIFF 디코딩"
  - "TIFF 인코딩"
ms.assetid: 1dfe3209-fc73-40e6-ad1c-71c1c58b3364
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: TIFF 이미지 인코딩 및 디코딩
다음 예제에서는 특정 <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> 및 <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> 개체를 사용하여 [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)] 이미지를 디코딩 및 인코딩하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서는 <xref:System.Uri>에서 <xref:System.Windows.Media.Imaging.TiffBitmapDecoder>를 사용하여 [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] 이미지를 디코딩하는 방법을 보여 줍니다.  
  
 [!code-cpp[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#1)]
 [!code-csharp[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#1)]
 [!code-vb[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#1)]  
  
## 예제  
 이 예제에서는 <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>를 사용하여 <xref:System.Windows.Media.Imaging.BitmapSource>를 [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] 이미지로 인코딩하는 방법을 보여 줍니다.  
  
 [!code-cpp[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#4)]
 [!code-csharp[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#4)]
 [!code-vb[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#4)]  
  
## 참고 항목  
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)