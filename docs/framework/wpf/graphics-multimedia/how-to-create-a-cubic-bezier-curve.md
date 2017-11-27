---
title: "방법: 입방형 3차원 곡선 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35d4fad0634586d5d0c6ea85f276d6e76edb3f63
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-cubic-bezier-curve"></a><span data-ttu-id="0d59f-102">방법: 입방형 3차원 곡선 만들기</span><span class="sxs-lookup"><span data-stu-id="0d59f-102">How to: Create a Cubic Bezier Curve</span></span>
<span data-ttu-id="0d59f-103">이 예제에는 입방 형 3 차원 곡선을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d59f-103">This example shows how to create a cubic Bezier curve.</span></span> <span data-ttu-id="0d59f-104">입방 형 3 차원 곡선을을 만들려면 사용는 <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, 및 <xref:System.Windows.Media.BezierSegment> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0d59f-104">To create a cubic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.BezierSegment> classes.</span></span>  <span data-ttu-id="0d59f-105">기를 표시 하려면 사용을 <xref:System.Windows.Shapes.Path> 요소를 함께 사용 하거나 한 <xref:System.Windows.Media.GeometryDrawing> 또는 <xref:System.Windows.Media.DrawingContext>합니다.</span><span class="sxs-lookup"><span data-stu-id="0d59f-105">To display the resulting geometry, use a <xref:System.Windows.Shapes.Path> element, or use it with a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="0d59f-106">다음 예에서 입방 형 3 차원 곡선에서 그려집니다 (10, 100)에 (300, 100).</span><span class="sxs-lookup"><span data-stu-id="0d59f-106">In the following examples, a cubic Bezier curve is drawn from (10, 100) to (300, 100).</span></span> <span data-ttu-id="0d59f-107">곡선의 제어점에 (100, 0) 및 (200, 200).</span><span class="sxs-lookup"><span data-stu-id="0d59f-107">The curve has control points of (100, 0) and (200, 200).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d59f-108">예제</span><span class="sxs-lookup"><span data-stu-id="0d59f-108">Example</span></span>  
 <span data-ttu-id="0d59f-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="0d59f-109">[xaml]</span></span>  
  
 <span data-ttu-id="0d59f-110">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 약식된 태그 구문을 사용 하 여 경로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d59f-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use abbreviated markup syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 <span data-ttu-id="0d59f-111">[xaml]</span><span class="sxs-lookup"><span data-stu-id="0d59f-111">[xaml]</span></span>  
  
 <span data-ttu-id="0d59f-112">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 개체 태그를 사용 하 여 입방 형 3 차원 곡선을 그릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d59f-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw a cubic Bezier curve using object tags.</span></span> <span data-ttu-id="0d59f-113">다음 예제는 이전 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0d59f-113">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 <span data-ttu-id="0d59f-114">이 예제는 더 큰 샘플에 속합니다. 전체 샘플을 보려면 [기하 도형 샘플](http://go.microsoft.com/fwlink/?LinkID=159989)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d59f-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d59f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d59f-115">See Also</span></span>  
 [<span data-ttu-id="0d59f-116">타원형 원호 만들기</span><span class="sxs-lookup"><span data-stu-id="0d59f-116">Create an Elliptical Arc</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)  
 [<span data-ttu-id="0d59f-117">PathGeometry에 LineSegment 만들기</span><span class="sxs-lookup"><span data-stu-id="0d59f-117">Create a LineSegment in a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)  
 [<span data-ttu-id="0d59f-118">입방형 3차원 곡선 만들기</span><span class="sxs-lookup"><span data-stu-id="0d59f-118">Create a Cubic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)  
 [<span data-ttu-id="0d59f-119">정방형 3차원 곡선 만들기</span><span class="sxs-lookup"><span data-stu-id="0d59f-119">Create a Quadratic Bezier Curve</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)
