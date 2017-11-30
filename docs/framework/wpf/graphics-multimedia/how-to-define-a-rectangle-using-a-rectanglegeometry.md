---
title: "방법: RectangleGeometry를 사용하여 사각형 정의"
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
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 678d6f36c02c63825782b9f1c860285450a6a9f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a><span data-ttu-id="4a387-102">방법: RectangleGeometry를 사용하여 사각형 정의</span><span class="sxs-lookup"><span data-stu-id="4a387-102">How to: Define a Rectangle Using a RectangleGeometry</span></span>
<span data-ttu-id="4a387-103">이 예제에 사용 하는 방법에 설명 된 <xref:System.Windows.Media.RectangleGeometry> 사각형을 설명 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4a387-103">This example describes how to use the <xref:System.Windows.Media.RectangleGeometry> class to describe a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a387-104">예제</span><span class="sxs-lookup"><span data-stu-id="4a387-104">Example</span></span>  
 <span data-ttu-id="4a387-105">만들고 렌더링 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Media.RectangleGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="4a387-105">The following example shows how to create and render a <xref:System.Windows.Media.RectangleGeometry>.</span></span>  <span data-ttu-id="4a387-106">정의 된 상대적 위치와 사각형의 크기는 <xref:System.Windows.Rect> 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="4a387-106">The relative position and the dimensions of the rectangle are defined by a <xref:System.Windows.Rect> structure.</span></span> <span data-ttu-id="4a387-107">상대적 위치는 `50,50` 고 높이 너비를 모두 `25` 는 정사각형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4a387-107">The relative position is `50,50` and the height and the width are both `25` creating a square.</span></span> <span data-ttu-id="4a387-108">사각형의 내부로 그려집니다는 <xref:System.Windows.Media.Brushes.LemonChiffon%2A> 로 브러시 및 윤곽선을 그리는 <xref:System.Windows.Media.Brushes.Black%2A> 스트로크 두께를 `1`합니다.</span><span class="sxs-lookup"><span data-stu-id="4a387-108">The rectangle's interior is painted with a <xref:System.Windows.Media.Brushes.LemonChiffon%2A> brush and its outline is painted with a <xref:System.Windows.Media.Brushes.Black%2A> stroke with a thickness of `1`.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 <span data-ttu-id="4a387-109">![RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span><span class="sxs-lookup"><span data-stu-id="4a387-109">![A RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")</span></span>  
<span data-ttu-id="4a387-110">RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="4a387-110">RectangleGeometry</span></span>  
  
 <span data-ttu-id="4a387-111">이 예에서는 사용 되지만 <xref:System.Windows.Shapes.Path> 요소를 렌더링 하는 <xref:System.Windows.Media.RectangleGeometry>, 여러 가지 다른 방법으로 사용 하도록 <xref:System.Windows.Media.RectangleGeometry> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4a387-111">Although this example used a <xref:System.Windows.Shapes.Path> element to render the <xref:System.Windows.Media.RectangleGeometry>, there are many other ways to use <xref:System.Windows.Media.RectangleGeometry> objects.</span></span> <span data-ttu-id="4a387-112">예를 들어 한 <xref:System.Windows.Media.RectangleGeometry> 는 지정 하는 데 사용할 수는 <xref:System.Windows.UIElement.Clip%2A> 의 <xref:System.Windows.UIElement> 또는 <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> 의 <xref:System.Windows.Media.GeometryDrawing>합니다.</span><span class="sxs-lookup"><span data-stu-id="4a387-112">For example, a <xref:System.Windows.Media.RectangleGeometry> can be used to specify the <xref:System.Windows.UIElement.Clip%2A> of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> of a <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="4a387-113">다른 간단한 기 하 도형 클래스 포함 <xref:System.Windows.Media.LineGeometry> 및 <xref:System.Windows.Media.EllipseGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="4a387-113">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="4a387-114">이 기 하이 도형 뿐만 아니라 더 복잡 한 프로젝트로 만들 수도 있습니다를 사용 하는 <xref:System.Windows.Media.PathGeometry> 또는 <xref:System.Windows.Media.StreamGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="4a387-114">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a387-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a387-115">See Also</span></span>  
 [<span data-ttu-id="4a387-116">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="4a387-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="4a387-117">복합 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="4a387-117">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="4a387-118">PathGeometry를 사용하여 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="4a387-118">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
