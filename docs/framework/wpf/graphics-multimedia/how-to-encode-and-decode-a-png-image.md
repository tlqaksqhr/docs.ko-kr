---
title: "방법: PNG 이미지 인코딩 및 디코딩 | Microsoft Docs"
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
  - "PNG 이미지 디코딩"
  - "이미지 형식 인코딩"
  - "PNG 이미지 인코딩"
  - "PNG 디코딩"
  - "PNG 인코딩"
ms.assetid: 3d31d186-af73-47f0-b5a7-c26ae46409a6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: PNG 이미지 인코딩 및 디코딩
다음 예제에서는 특정 <xref:System.Windows.Media.Imaging.PngBitmapDecoder> 및 <xref:System.Windows.Media.Imaging.PngBitmapEncoder> 개체를 사용하여 [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] 이미지를 디코딩 및 인코딩하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서는 <xref:System.IO.FileStream>에서 <xref:System.Windows.Media.Imaging.PngBitmapDecoder>를 사용하여 [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] 이미지를 디코딩하는 방법을 보여 줍니다.  
  
 [!code-cpp[PngBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#1)]
 [!code-csharp[PngBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#1)]
 [!code-vb[PngBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#1)]  
  
## 예제  
 이 예제에서는 <xref:System.Windows.Media.Imaging.PngBitmapEncoder>를 사용하여 <xref:System.Windows.Media.Imaging.BitmapSource>를 [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)] 이미지로 인코딩하는 방법을 보여 줍니다.  
  
 [!code-cpp[PngBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CPP/PngEncoderDecoder.cpp#4)]
 [!code-csharp[PngBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PngBitmapDecoderEncoder/CSharp/PngEncoderDecoder.cs#4)]
 [!code-vb[PngBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PngBitmapDecoderEncoder/VB/PngEncoderDecoder.vb#4)]  
  
## 참고 항목  
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)