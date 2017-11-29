---
title: "방법: TileBrush로 다른 바둑판식 배열 패턴 만들기"
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
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6247f6a16cd8ab7be683d0d4d33aac021f3a2b32
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a><span data-ttu-id="40aa9-102">방법: TileBrush로 다른 바둑판식 배열 패턴 만들기</span><span class="sxs-lookup"><span data-stu-id="40aa9-102">How to: Create Different Tile Patterns with a TileBrush</span></span>
<span data-ttu-id="40aa9-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.TileBrush.TileMode%2A> 의 속성은 <xref:System.Windows.Media.TileBrush> 는 패턴을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="40aa9-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.TileBrush> to create a pattern.</span></span>  
  
 <span data-ttu-id="40aa9-104"><xref:System.Windows.Media.TileBrush.TileMode%2A> 속성을 통해 지정할 수 있습니다. 방법을의 콘텐츠는 <xref:System.Windows.Media.TileBrush> 반복, 즉, 출력 영역을 채우는 바둑판식으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40aa9-104">The <xref:System.Windows.Media.TileBrush.TileMode%2A> property enables you to specify how the content of a <xref:System.Windows.Media.TileBrush> is repeated, that is, tiled to fill an output area.</span></span> <span data-ttu-id="40aa9-105">설정 된 패턴을 만들려면는 <xref:System.Windows.Media.TileBrush.TileMode%2A> 를 <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, 또는 <xref:System.Windows.Media.TileMode.FlipXY>합니다.</span><span class="sxs-lookup"><span data-stu-id="40aa9-105">To create a pattern, you set the <xref:System.Windows.Media.TileBrush.TileMode%2A> to <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, or <xref:System.Windows.Media.TileMode.FlipXY>.</span></span> <span data-ttu-id="40aa9-106">설정 해야는 <xref:System.Windows.Media.TileBrush.Viewport%2A> 의 <xref:System.Windows.Media.TileBrush> 사용자; 칠하고 있는 영역 보다 작은 되도록 그렇지 않으면 단일 타일만 생성 된 상관 없이 있는 <xref:System.Windows.Media.TileBrush.TileMode%2A> 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="40aa9-106">You must also set the <xref:System.Windows.Media.TileBrush.Viewport%2A> of the <xref:System.Windows.Media.TileBrush> so that it is smaller than the area that you are painting; otherwise, only a single tile is produced, regardless which <xref:System.Windows.Media.TileBrush.TileMode%2A> setting you use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40aa9-107">예제</span><span class="sxs-lookup"><span data-stu-id="40aa9-107">Example</span></span>  
 <span data-ttu-id="40aa9-108">다음 예제에서는 5 <xref:System.Windows.Media.DrawingBrush> 개체, 각각 서로 다른 제공 <xref:System.Windows.Media.TileBrush.TileMode%2A> 설정과 하는 5 개의 사각형을 그리는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="40aa9-108">The following example creates five <xref:System.Windows.Media.DrawingBrush> objects, gives them each a different <xref:System.Windows.Media.TileBrush.TileMode%2A> setting, and uses them to paint five rectangles.</span></span> <span data-ttu-id="40aa9-109">이 예제에서는 <xref:System.Windows.Media.DrawingBrush> 보여 주기 위해 클래스 <xref:System.Windows.Media.TileBrush.TileMode%2A> 동작을는 <xref:System.Windows.Media.TileBrush.TileMode%2A> 속성이 모든에 대해 동일 하 게 작동 하는 <xref:System.Windows.Media.TileBrush> 개체, 즉,에 대 한 <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, 및 <xref:System.Windows.Media.DrawingBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="40aa9-109">Although this example uses the <xref:System.Windows.Media.DrawingBrush> class to demonstrate <xref:System.Windows.Media.TileBrush.TileMode%2A> behavior, the <xref:System.Windows.Media.TileBrush.TileMode%2A> property works identically for all the <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, and <xref:System.Windows.Media.DrawingBrush>.</span></span>  
  
 <span data-ttu-id="40aa9-110">다음 그림에서는 이 예제가 생성하는 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40aa9-110">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="40aa9-111">![예제 출력을 바둑판식으로 배열 된 TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span><span class="sxs-lookup"><span data-stu-id="40aa9-111">![TileBrush tiling example output](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span></span>  
<span data-ttu-id="40aa9-112">TileMode 속성을 사용 하 여 만든 타일 패턴</span><span class="sxs-lookup"><span data-stu-id="40aa9-112">Tile patterns created with the TileMode property</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="40aa9-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40aa9-113">See Also</span></span>  
 [<span data-ttu-id="40aa9-114">TileBrush의 바둑판 크기 설정</span><span class="sxs-lookup"><span data-stu-id="40aa9-114">Set the Tile Size for a TileBrush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)  
 [<span data-ttu-id="40aa9-115">이미지, 그림 및 시각적 표시로 그리기</span><span class="sxs-lookup"><span data-stu-id="40aa9-115">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
