---
title: '방법: JPEG 이미지 인코딩 및 디코딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding image formats [WPF]
- decoding JPEG images [WPF]
- encoding JPEG images [WPF]
- decoding image formats [WPF]
- JPEG decoding [WPF]
- JPEG encoding [WPF]
ms.assetid: b8cfde37-9f68-4911-a05e-51d8d7bdec7b
ms.openlocfilehash: 8eb3c2573ba23fa62550e7e60489b13a37eb7cc7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560011"
---
# <a name="how-to-encode-and-decode-a-jpeg-image"></a><span data-ttu-id="12611-102">방법: JPEG 이미지 인코딩 및 디코딩</span><span class="sxs-lookup"><span data-stu-id="12611-102">How to: Encode and Decode a JPEG Image</span></span>
<span data-ttu-id="12611-103">다음 예제에서는 암호 해독 하 고 인코딩하는 방법을 보여는 [!INCLUDE[TLA#tla_jpeg](../../../../includes/tlasharptla-jpeg-md.md)] 특정을 사용 하 여 이미지 <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> 및 <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="12611-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_jpeg](../../../../includes/tlasharptla-jpeg-md.md)] image using the specific <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> and <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12611-104">예제</span><span class="sxs-lookup"><span data-stu-id="12611-104">Example</span></span>  
 <span data-ttu-id="12611-105">디코딩하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] 를 사용 하 여 이미지는 <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> 에서 <xref:System.IO.FileStream>합니다.</span><span class="sxs-lookup"><span data-stu-id="12611-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] image using a <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#1)]
 [!code-csharp[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#1)]
 [!code-vb[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="12611-106">예제</span><span class="sxs-lookup"><span data-stu-id="12611-106">Example</span></span>  
 <span data-ttu-id="12611-107">인코딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Imaging.BitmapSource> 에 [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] 를 사용 하 여 이미지는 <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>합니다.</span><span class="sxs-lookup"><span data-stu-id="12611-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] image using a <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.</span></span>  
  
 [!code-cpp[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#4)]
 [!code-csharp[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#4)]
 [!code-vb[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#4)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="12611-108">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="12611-108">.NET Framework Security</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12611-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12611-109">See Also</span></span>  
 [<span data-ttu-id="12611-110">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="12611-110">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
