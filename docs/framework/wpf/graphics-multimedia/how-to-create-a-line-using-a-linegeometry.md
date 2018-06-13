---
title: '방법: LineGeometry를 사용하여 선 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: 8db33fc5c611dcbcae50c71ada1c6b6f9fd9bd29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560471"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a><span data-ttu-id="47fc1-102">방법: LineGeometry를 사용하여 선 만들기</span><span class="sxs-lookup"><span data-stu-id="47fc1-102">How to: Create a Line Using a LineGeometry</span></span>
<span data-ttu-id="47fc1-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.LineGeometry> 줄을 설명 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="47fc1-103">This example shows how to use the <xref:System.Windows.Media.LineGeometry> class to describe a line.</span></span> <span data-ttu-id="47fc1-104">A <xref:System.Windows.Media.LineGeometry> 시작 및 끝 지점을 사용 하 여 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47fc1-104">A <xref:System.Windows.Media.LineGeometry> is defined by its start and end points.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47fc1-105">예제</span><span class="sxs-lookup"><span data-stu-id="47fc1-105">Example</span></span>  
 <span data-ttu-id="47fc1-106">만들고 렌더링 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Media.LineGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="47fc1-106">The following example shows how to create and render a <xref:System.Windows.Media.LineGeometry>.</span></span>  <span data-ttu-id="47fc1-107">A <xref:System.Windows.Shapes.Path> 요소를 사용 하는 줄을 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="47fc1-107">A <xref:System.Windows.Shapes.Path> element is used to render the line.</span></span>  <span data-ttu-id="47fc1-108">또한 선에 영역이 없는 이후는 <xref:System.Windows.Shapes.Path> 개체의 <xref:System.Windows.Shapes.Shape.Fill%2A> 지정 되지 않았습니다; 대신는 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47fc1-108">Since a line has no area, the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Shape.Fill%2A> is not specified; instead the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties are used.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 <span data-ttu-id="47fc1-109">![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")</span><span class="sxs-lookup"><span data-stu-id="47fc1-109">![A LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")</span></span>  
<span data-ttu-id="47fc1-110">(10,20)부터 (100,130)까지 그린 LineGeometry</span><span class="sxs-lookup"><span data-stu-id="47fc1-110">A LineGeometry drawn from (10,20) to (100,130)</span></span>  
  
 <span data-ttu-id="47fc1-111">다른 간단한 기 하 도형 클래스 포함 <xref:System.Windows.Media.LineGeometry> 및 <xref:System.Windows.Media.EllipseGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="47fc1-111">Other simple geometry classes include <xref:System.Windows.Media.LineGeometry> and <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="47fc1-112">이 기 하이 도형 뿐만 아니라 더 복잡 한 프로젝트로 만들 수도 있습니다를 사용 하는 <xref:System.Windows.Media.PathGeometry> 또는 <xref:System.Windows.Media.StreamGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="47fc1-112">These geometries, as well as more complex ones, can also be created using a <xref:System.Windows.Media.PathGeometry> or <xref:System.Windows.Media.StreamGeometry>.</span></span> <span data-ttu-id="47fc1-113">자세한 내용은 참조는 [기 하 도형 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="47fc1-113">For more information, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47fc1-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47fc1-114">See Also</span></span>  
 [<span data-ttu-id="47fc1-115">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="47fc1-115">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="47fc1-116">복합 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="47fc1-116">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="47fc1-117">PathGeometry를 사용하여 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="47fc1-117">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
