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
ms.openlocfilehash: 916eab63938100daf91e6c1a5af31648a99108d0
ms.sourcegitcommit: f9e38d31288fe5962e6be5b0cc286da633482873
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37027969"
---
# <a name="how-to-encode-and-decode-a-jpeg-image"></a><span data-ttu-id="ee313-102">방법: JPEG 이미지 인코딩 및 디코딩</span><span class="sxs-lookup"><span data-stu-id="ee313-102">How to: Encode and decode a JPEG image</span></span>

<span data-ttu-id="ee313-103">다음 예제에서는 암호 해독 하 고 특정을 사용 하 여 JPEG 이미지를 인코딩하는 방법을 보여 <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> 및 <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ee313-103">The following examples show how to decode and encode a JPEG image using the specific <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> and <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> objects.</span></span>  
  
## <a name="example---decode-a-jpeg-image"></a><span data-ttu-id="ee313-104">예-JPEG 이미지 디코딩</span><span class="sxs-lookup"><span data-stu-id="ee313-104">Example - Decode a JPEG image</span></span>

<span data-ttu-id="ee313-105">사용 하 여 JPEG 이미지를 디코딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> 에서 <xref:System.IO.FileStream>합니다.</span><span class="sxs-lookup"><span data-stu-id="ee313-105">This example demonstrates how to decode a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#1)]
[!code-csharp[JpegBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#1)]
[!code-vb[JpegBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#1)]  
  
## <a name="example---encode-a-jpeg-image"></a><span data-ttu-id="ee313-106">예-JPEG 이미지 인코딩</span><span class="sxs-lookup"><span data-stu-id="ee313-106">Example - Encode a JPEG image</span></span>

<span data-ttu-id="ee313-107">인코딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Imaging.BitmapSource> 를 사용 하 여 이미지를 JPEG로는 <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>합니다.</span><span class="sxs-lookup"><span data-stu-id="ee313-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#4)]
[!code-csharp[JpegBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#4)]
[!code-vb[JpegBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="ee313-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="ee313-108">See also</span></span>

[<span data-ttu-id="ee313-109">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="ee313-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)