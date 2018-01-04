---
title: "방법: TIFF 이미지 인코딩 및 디코딩"
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
- TIFF encoding [WPF]
- encoding TIFF images [WPF]
- encoding image formats [WPF]
- decoding TIFF images [WPF]
- decoding image formats [WPF]
- TIFF decoding [WPF]
ms.assetid: 1dfe3209-fc73-40e6-ad1c-71c1c58b3364
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee934158e1a3c72e728ce9cd87b0307deea8638a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-encode-and-decode-a-tiff-image"></a>방법: TIFF 이미지 인코딩 및 디코딩
다음 예제에서는 암호 해독 하 고 인코딩하는 방법을 보여는 [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)] 특정을 사용 하 여 이미지 <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> 및 <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> 개체입니다.  
  
## <a name="example"></a>예  
 디코딩하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] 를 사용 하 여 이미지는 <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> 에서 <xref:System.Uri>합니다.  
  
 [!code-cpp[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#1)]
 [!code-csharp[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#1)]
 [!code-vb[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#1)]  
  
## <a name="example"></a>예  
 인코딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Imaging.BitmapSource> 에 [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] 를 사용 하 여 이미지는 <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>합니다.  
  
 [!code-cpp[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#4)]
 [!code-csharp[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#4)]
 [!code-vb[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a>참고 항목  
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
