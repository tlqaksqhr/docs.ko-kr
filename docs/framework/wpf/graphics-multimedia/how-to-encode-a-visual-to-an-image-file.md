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
# <a name="how-to-encode-a-visual-to-an-image-file"></a>방법: 시각적 요소를 이미지 파일로 인코딩
인코딩하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Visual> 개체를 사용 하 여 이미지 파일에는 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 및 <xref:System.Windows.Media.Imaging.PngBitmapEncoder>합니다.  
  
## <a name="example"></a>예  
 <xref:System.Windows.Media.DrawingVisual> 사용 하 여 만들어집니다는 <xref:System.Windows.Media.Imaging.BitmapImage> 및 <xref:System.Windows.Media.FormattedText> 으로 렌더링 되는 한 <xref:System.Windows.Media.Imaging.RenderTargetBitmap>합니다. 렌더링 된 비트맵 다음 만드는 데 사용 되는 <xref:System.Windows.Media.Imaging.BitmapFrame> 에 추가 되는 <xref:System.Windows.Media.Imaging.PngBitmapEncoder> 새로 만들 수 [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)] 파일입니다.  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 A <xref:System.Windows.Media.Imaging.PngBitmapEncoder> 이 예제에서는 임의의 파생 된 사용한 <xref:System.Windows.Media.Imaging.BitmapEncoder> 개체 이미지 파일을 만드는 사용 되었을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.DrawingContext>  
 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [DrawingVisual 개체 사용](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
