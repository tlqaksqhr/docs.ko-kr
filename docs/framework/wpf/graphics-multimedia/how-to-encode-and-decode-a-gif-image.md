---
title: "방법: GIF 이미지 인코딩 및 디코딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding GIF images [WPF]
- encoding image formats [WPF]
- decoding GIF images [WPF]
- decoding image formats [WPF]
- GIF decoding [WPF]
- GIF encoding [WPF]
ms.assetid: 9cdd9ec7-71eb-444b-b9e3-991958461163
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f7832e4197ef5c3a764da265a393b654db013876
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-encode-and-decode-a-gif-image"></a>방법: GIF 이미지 인코딩 및 디코딩
다음 예제에서는 암호 해독 하 고 인코딩하는 방법을 보여는 [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] 특정을 사용 하 여 이미지 <xref:System.Windows.Media.Imaging.GifBitmapDecoder> 및 <xref:System.Windows.Media.Imaging.GifBitmapEncoder> 개체입니다.  
  
## <a name="example"></a>예제  
 디코딩하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] 를 사용 하 여 이미지는 <xref:System.Windows.Media.Imaging.GifBitmapDecoder> 에서 <xref:System.IO.FileStream>합니다.  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a>예제  
 인코딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Imaging.BitmapSource> 에 [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] 를 사용 하 여 이미지는 <xref:System.Windows.Media.Imaging.GifBitmapEncoder>합니다.  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a>참고 항목  
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
