---
title: "방법: PathGeometry를 사용하여 도형 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31f77f0921bb018317834077f70e4623c47a4f7f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="14028-102">방법: PathGeometry를 사용하여 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="14028-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="14028-103">사용 하 여 도형을 만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.PathGeometry> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="14028-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="14028-104"><xref:System.Windows.Media.PathGeometry>개체는 하나 이상의 구성 됩니다 <xref:System.Windows.Media.PathFigure> 객체; 각 <xref:System.Windows.Media.PathFigure> 다른 "그림" 또는 셰이프를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="14028-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="14028-105">각 <xref:System.Windows.Media.PathFigure> 은 자체 구성 된 하나 이상의 <xref:System.Windows.Media.PathSegment> 각각 또는 도형의의 연결 된 부분을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="14028-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="14028-106">세그먼트 종류 <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, 및 <xref:System.Windows.Media.BezierSegment>합니다.</span><span class="sxs-lookup"><span data-stu-id="14028-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14028-107">예제</span><span class="sxs-lookup"><span data-stu-id="14028-107">Example</span></span>  
 <span data-ttu-id="14028-108">다음 예제에서는 한 <xref:System.Windows.Media.PathGeometry> 삼각형이 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="14028-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="14028-109"><xref:System.Windows.Media.PathGeometry> 를 사용 하 여 표시 되는 <xref:System.Windows.Shapes.Path> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="14028-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="14028-110">다음 그림은 이전 예제에서 만든 도형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14028-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="14028-111">![PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="14028-111">![A PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="14028-112">PathGeometry를 사용 하 여 만든 삼각형</span><span class="sxs-lookup"><span data-stu-id="14028-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="14028-113">앞의 예제에는 상대적으로 간단한 도형을, 삼각형을 만드는 방법을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="14028-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="14028-114">A <xref:System.Windows.Media.PathGeometry> 곡선을 포함 하는 보다 복잡 한 셰이프를 만들려면 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14028-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="14028-115">예제를 보려면 [타원형 호를 만들](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [입방 형 3 차원 곡선을 만들](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), 및 [정방형 3 차원 곡선을 만들](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="14028-115">For examples, see [Create an Elliptical Arc](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="14028-116">이 예제는 더 큰 샘플에 속합니다. 전체 샘플을 보려면 [기하 도형 샘플](http://go.microsoft.com/fwlink/?LinkID=159989)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14028-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14028-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14028-117">See Also</span></span>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [<span data-ttu-id="14028-118">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="14028-118">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="14028-119">기 하 도형 샘플</span><span class="sxs-lookup"><span data-stu-id="14028-119">Geometries Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159989)
