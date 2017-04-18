---
title: "방법: WDP 이미지 인코딩 및 디코딩 | Microsoft Docs"
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
  - "WDP 이미지 디코딩"
  - "이미지 형식 인코딩"
  - "WDP 이미지 인코딩"
  - "WDP 디코딩"
  - "WDP 인코딩"
ms.assetid: 911777d1-516b-49db-a87b-b54e31b18532
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: WDP 이미지 인코딩 및 디코딩
다음 예제에서는 특정 <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> 및 <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> 개체를 사용하여 [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)] 이미지를 디코딩 및 인코딩하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서는 <xref:System.Uri>에서 <xref:System.Windows.Media.Imaging.WmpBitmapDecoder>를 사용하여 [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] 이미지를 디코딩하는 방법을 보여 줍니다.  
  
 [!code-cpp[WdpBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#1)]
 [!code-csharp[WdpBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#1)]
 [!code-vb[WdpBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#1)]  
  
## 예제  
 이 예제에서는 <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>를 사용하여 <xref:System.Windows.Media.Imaging.BitmapSource>를 [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)] 이미지로 인코딩하는 방법을 보여 줍니다.  
  
 [!code-cpp[WdpBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#4)]
 [!code-csharp[WdpBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#4)]
 [!code-vb[WdpBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#4)]  
  
## 참고 항목  
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)