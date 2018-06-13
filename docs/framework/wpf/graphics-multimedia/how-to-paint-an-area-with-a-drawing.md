---
title: '방법: Drawing으로 영역 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
ms.openlocfilehash: 222aa3fbb72ebaf15be3ed7f9804936e7e1187e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560905"
---
# <a name="how-to-paint-an-area-with-a-drawing"></a><span data-ttu-id="e67a5-102">방법: Drawing으로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="e67a5-102">How to: Paint an Area with a Drawing</span></span>
<span data-ttu-id="e67a5-103">이 예제에서는 그리기로 영역을 그리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e67a5-103">This example shows how to paint an area with a drawing.</span></span> <span data-ttu-id="e67a5-104">로 드로잉 영역을 그리는 데 사용 하는 <xref:System.Windows.Media.DrawingBrush> 와 하나 이상의 <xref:System.Windows.Media.Drawing> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e67a5-104">To paint an area with a drawing, you use a <xref:System.Windows.Media.DrawingBrush> and one or more <xref:System.Windows.Media.Drawing> objects.</span></span>   <span data-ttu-id="e67a5-105">다음 예제에서는 한 <xref:System.Windows.Media.DrawingBrush> 그림 두 타원으로 개체를 그리는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e67a5-105">The following example uses a <xref:System.Windows.Media.DrawingBrush> to paint an object with a drawing of two ellipses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e67a5-106">예제</span><span class="sxs-lookup"><span data-stu-id="e67a5-106">Example</span></span>  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 <span data-ttu-id="e67a5-107">다음 그림에서는 예제의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e67a5-107">The following illustration shows the example's output.</span></span>  
  
 <span data-ttu-id="e67a5-108">![DrawingBrush의 출력](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span><span class="sxs-lookup"><span data-stu-id="e67a5-108">![Output from a DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span></span>  
  
 <span data-ttu-id="e67a5-109">(셰이프의 가운데에 설명 된 이유로 흰색인 [복합 도형 채우기 제어](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-the-fill-of-a-composite-shape.md).)</span><span class="sxs-lookup"><span data-stu-id="e67a5-109">(The center of the shape is white for reasons described in     [Control the Fill of a Composite Shape](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-the-fill-of-a-composite-shape.md).)</span></span>  
  
 <span data-ttu-id="e67a5-110">설정 하 여 한 <xref:System.Windows.Media.DrawingBrush> 개체의 <xref:System.Windows.Media.TileBrush.Viewport%2A> 및 <xref:System.Windows.Media.TileBrush.TileMode%2A> 속성을 반복을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e67a5-110">By setting a <xref:System.Windows.Media.DrawingBrush> object's <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties, you can create a repeating pattern.</span></span> <span data-ttu-id="e67a5-111">다음 예제에서는 2개의 타원 그리기로 만든 패턴으로 개체를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="e67a5-111">The following example paints an object with a pattern created from a drawing of two ellipses.</span></span>  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 <span data-ttu-id="e67a5-112">다음 그림에는 바둑판식 나와 <xref:System.Windows.Media.DrawingBrush> 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e67a5-112">The following illustration shows the tiled <xref:System.Windows.Media.DrawingBrush> output.</span></span>  
  
 <span data-ttu-id="e67a5-113">![DrawingBrush의 바둑판식 출력](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span><span class="sxs-lookup"><span data-stu-id="e67a5-113">![Tiled output from a DrawingBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span></span>  
  
 <span data-ttu-id="e67a5-114">드로잉 브러시에 대 한 자세한 내용은 참조 [이미지, 그리기, 및 시각적 개체를 사용 하 여 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e67a5-114">For more information about drawing brushes, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span> <span data-ttu-id="e67a5-115">에 대 한 자세한 내용은 <xref:System.Windows.Media.Drawing> 개체 참조는 [그리기 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e67a5-115">For more information about <xref:System.Windows.Media.Drawing> objects, see the [Drawing Objects Overview](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).</span></span>
