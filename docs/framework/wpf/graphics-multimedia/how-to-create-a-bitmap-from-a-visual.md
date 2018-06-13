---
title: '방법: Visual로 비트맵 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: 4735474d00712598cb5e41fad289e8f568d83a48
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559768"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a><span data-ttu-id="b29b2-102">방법: Visual로 비트맵 만들기</span><span class="sxs-lookup"><span data-stu-id="b29b2-102">How to: Create a Bitmap from a Visual</span></span>
<span data-ttu-id="b29b2-103">비트맵을 만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Visual>합니다.</span><span class="sxs-lookup"><span data-stu-id="b29b2-103">This example shows how you can create a bitmap from a <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="b29b2-104">A <xref:System.Windows.Media.DrawingVisual> 사용 하 여 렌더링 <xref:System.Windows.Media.FormattedText>합니다.</span><span class="sxs-lookup"><span data-stu-id="b29b2-104">A <xref:System.Windows.Media.DrawingVisual> is rendered with <xref:System.Windows.Media.FormattedText>.</span></span> <span data-ttu-id="b29b2-105"><xref:System.Windows.Media.Visual> 다음에 렌더링 되는 <xref:System.Windows.Media.Imaging.RenderTargetBitmap> 지정된 된 텍스트의 비트맵을 만드는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29b2-105">The <xref:System.Windows.Media.Visual> is then rendered to the <xref:System.Windows.Media.Imaging.RenderTargetBitmap> creating a bitmap of the given text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b29b2-106">예제</span><span class="sxs-lookup"><span data-stu-id="b29b2-106">Example</span></span>  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a><span data-ttu-id="b29b2-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b29b2-107">See Also</span></span>  
 <xref:System.Windows.Media.DrawingContext>  
 [<span data-ttu-id="b29b2-108">이미징 개요</span><span class="sxs-lookup"><span data-stu-id="b29b2-108">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [<span data-ttu-id="b29b2-109">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="b29b2-109">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="b29b2-110">DrawingVisual 개체 사용</span><span class="sxs-lookup"><span data-stu-id="b29b2-110">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
