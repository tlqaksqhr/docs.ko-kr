---
title: '방법: GIF 이미지 인코딩 및 디코딩'
ms.date: 03/30/2017
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
ms.openlocfilehash: 9e432b5662843fe66cd8a8c445a3e4ec7c6d621b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558709"
---
# <a name="how-to-encode-and-decode-a-gif-image"></a><span data-ttu-id="3a8bf-102">방법: GIF 이미지 인코딩 및 디코딩</span><span class="sxs-lookup"><span data-stu-id="3a8bf-102">How to: Encode and Decode a GIF Image</span></span>
<span data-ttu-id="3a8bf-103">다음 예제에서는 암호 해독 하 고 인코딩하는 방법을 보여는 [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] 특정을 사용 하 여 이미지 <xref:System.Windows.Media.Imaging.GifBitmapDecoder> 및 <xref:System.Windows.Media.Imaging.GifBitmapEncoder> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8bf-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] image using the specific <xref:System.Windows.Media.Imaging.GifBitmapDecoder> and <xref:System.Windows.Media.Imaging.GifBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a8bf-104">예제</span><span class="sxs-lookup"><span data-stu-id="3a8bf-104">Example</span></span>  
 <span data-ttu-id="3a8bf-105">디코딩하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] 를 사용 하 여 이미지는 <xref:System.Windows.Media.Imaging.GifBitmapDecoder> 에서 <xref:System.IO.FileStream>합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8bf-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] image using a <xref:System.Windows.Media.Imaging.GifBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="3a8bf-106">예제</span><span class="sxs-lookup"><span data-stu-id="3a8bf-106">Example</span></span>  
 <span data-ttu-id="3a8bf-107">인코딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Imaging.BitmapSource> 에 [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] 를 사용 하 여 이미지는 <xref:System.Windows.Media.Imaging.GifBitmapEncoder>합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8bf-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] image using a <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="3a8bf-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a8bf-108">See Also</span></span>  
 [<span data-ttu-id="3a8bf-109">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="3a8bf-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
