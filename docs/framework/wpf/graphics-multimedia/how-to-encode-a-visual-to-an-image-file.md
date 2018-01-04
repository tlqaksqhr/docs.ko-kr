---
title: "방법: 시각적 요소를 이미지 파일로 인코딩"
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
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 88a5d93c9c4726d1f6493df28d0a2a559394ef74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a><span data-ttu-id="3f3b1-102">방법: 시각적 요소를 이미지 파일로 인코딩</span><span class="sxs-lookup"><span data-stu-id="3f3b1-102">How to: Encode a Visual to an Image File</span></span>
<span data-ttu-id="3f3b1-103">인코딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Visual> 개체를 사용 하 여 이미지 파일에는 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 및 <xref:System.Windows.Media.Imaging.PngBitmapEncoder>합니다.</span><span class="sxs-lookup"><span data-stu-id="3f3b1-103">This example demonstrates how to encode a <xref:System.Windows.Media.Visual> object into an image file using a <xref:System.Windows.Media.Imaging.RenderTargetBitmap> and a <xref:System.Windows.Media.Imaging.PngBitmapEncoder>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f3b1-104">예</span><span class="sxs-lookup"><span data-stu-id="3f3b1-104">Example</span></span>  
 <span data-ttu-id="3f3b1-105"><xref:System.Windows.Media.DrawingVisual> 사용 하 여 만들어집니다는 <xref:System.Windows.Media.Imaging.BitmapImage> 및 <xref:System.Windows.Media.FormattedText> 으로 렌더링 되는 한 <xref:System.Windows.Media.Imaging.RenderTargetBitmap>합니다.</span><span class="sxs-lookup"><span data-stu-id="3f3b1-105">The <xref:System.Windows.Media.DrawingVisual> is created using a <xref:System.Windows.Media.Imaging.BitmapImage> and <xref:System.Windows.Media.FormattedText> which is rendered to a <xref:System.Windows.Media.Imaging.RenderTargetBitmap>.</span></span> <span data-ttu-id="3f3b1-106">렌더링 된 비트맵 다음 만드는 데 사용 되는 <xref:System.Windows.Media.Imaging.BitmapFrame> 에 추가 되는 <xref:System.Windows.Media.Imaging.PngBitmapEncoder> 새로 만들 수 [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3f3b1-106">The rendered bitmap is then used to create a <xref:System.Windows.Media.Imaging.BitmapFrame> which is added to the <xref:System.Windows.Media.Imaging.PngBitmapEncoder> to create a new [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] file.</span></span>  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 <span data-ttu-id="3f3b1-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> 이 예제에서는 임의의 파생 된 사용한 <xref:System.Windows.Media.Imaging.BitmapEncoder> 개체 이미지 파일을 만드는 사용 되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f3b1-107">A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> was used in this example but any of the derived <xref:System.Windows.Media.Imaging.BitmapEncoder> objects could have been used to create the image file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f3b1-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f3b1-108">See Also</span></span>  
 <xref:System.Windows.Media.DrawingContext>  
 [<span data-ttu-id="3f3b1-109">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="3f3b1-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [<span data-ttu-id="3f3b1-110">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="3f3b1-110">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="3f3b1-111">DrawingVisual 개체 사용</span><span class="sxs-lookup"><span data-stu-id="3f3b1-111">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
