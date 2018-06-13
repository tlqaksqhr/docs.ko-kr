---
title: '방법: 복합 도형 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: 6bb2a8a32938682af52343b971b840dbed16bcef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559973"
---
# <a name="how-to-create-a-composite-shape"></a><span data-ttu-id="74184-102">방법: 복합 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="74184-102">How to: Create a Composite Shape</span></span>
<span data-ttu-id="74184-103">사용 하 여 복합 셰이프를 만드는 방법을 보여 주는이 예제 <xref:System.Windows.Media.Geometry> 개체 하 고 표시를 사용 하 여는 <xref:System.Windows.Shapes.Path> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="74184-103">This example shows how to create composite shapes using <xref:System.Windows.Media.Geometry> objects and display them using a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="74184-104">다음 예제에서는 <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, 및 <xref:System.Windows.Media.RectangleGeometry> 함께 사용 되는 <xref:System.Windows.Media.GeometryGroup> 복합 셰이프를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="74184-104">In the following example, a <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, and a <xref:System.Windows.Media.RectangleGeometry> are used with a <xref:System.Windows.Media.GeometryGroup> to create a composite shape.</span></span> <span data-ttu-id="74184-105">기 하 도형이 다음 사용 하 여 그려집니다는 <xref:System.Windows.Shapes.Path> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="74184-105">The geometries are then drawn using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74184-106">예제</span><span class="sxs-lookup"><span data-stu-id="74184-106">Example</span></span>  
 [!code-xaml[GeometrySample#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 <span data-ttu-id="74184-107">다음 그림은 이전 예제에서 만든 도형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="74184-107">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="74184-108">![GeometryGroup을 사용 하 여 만든 복합 기 하 도형을](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span><span class="sxs-lookup"><span data-stu-id="74184-108">![A composite geometry created using a GeometryGroup](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span></span>  
<span data-ttu-id="74184-109">복합 기 하 도형</span><span class="sxs-lookup"><span data-stu-id="74184-109">Composite Geometry</span></span>  
  
 <span data-ttu-id="74184-110">사용 하 여 다각형, 곡선된 세그먼트를 사용 하 여 셰이프 등의 더 복잡 한 도형을 만들 수는 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="74184-110">More complex shapes, such as polygons and shapes with curved segments, may be created using a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="74184-111">사용 하 여 도형을 만드는 방법을 보여 주는 예제는 <xref:System.Windows.Media.PathGeometry>, 참조 [PathGeometry를 사용 하 여 도형을 만드는](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="74184-111">For an example showing how to create a shape using a <xref:System.Windows.Media.PathGeometry>, see [Create a Shape by Using a PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  <span data-ttu-id="74184-112">이 예제에 사용 하 여 화면 모양을 렌더링 하는 있지만 <xref:System.Windows.Shapes.Path> 요소인 <xref:System.Windows.Media.Geometry> 개체의 내용을 설명 하기 위해 사용할 수도 있습니다는 <xref:System.Windows.Media.GeometryDrawing> 또는 <xref:System.Windows.Media.DrawingContext>합니다.</span><span class="sxs-lookup"><span data-stu-id="74184-112">Although this example renders a shape to the screen using a <xref:System.Windows.Shapes.Path> element, <xref:System.Windows.Media.Geometry> objects may also be used to describe the contents of a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="74184-113">클리핑 및 적중 테스트에 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74184-113">They may also be used for clipping and hit-testing.</span></span>  
  
 <span data-ttu-id="74184-114">이 예제는 더 큰 샘플에 속합니다. 전체 샘플을 보려면 [기하 도형 샘플](http://go.microsoft.com/fwlink/?LinkID=159989)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74184-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>
