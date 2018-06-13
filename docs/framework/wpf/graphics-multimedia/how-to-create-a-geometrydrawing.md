---
title: '방법: GeometryDrawing 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: 713cecd10bfa62494c50c96cb8cbece69f7e5660
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560662"
---
# <a name="how-to-create-a-geometrydrawing"></a><span data-ttu-id="d1544-102">방법: GeometryDrawing 만들기</span><span class="sxs-lookup"><span data-stu-id="d1544-102">How to: Create a GeometryDrawing</span></span>
<span data-ttu-id="d1544-103">만들고 표시 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.GeometryDrawing>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1544-103">This example shows how to create and display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="d1544-104">A <xref:System.Windows.Media.GeometryDrawing> 채우기 개요와 연결 하 여 셰이프를 만들 수 있습니다는 <xref:System.Windows.Media.Pen> 및 <xref:System.Windows.Media.Brush> 와 <xref:System.Windows.Media.Geometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1544-104">A <xref:System.Windows.Media.GeometryDrawing> enables you to create shape with a fill and an outline by associating a <xref:System.Windows.Media.Pen> and a <xref:System.Windows.Media.Brush> with a <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="d1544-105"><xref:System.Windows.Media.GeometryDrawing.Geometry%2A> 도형의 구조를 설명는 <xref:System.Windows.Media.GeometryDrawing.Brush%2A> 도형의 채우기 설명 및 <xref:System.Windows.Media.GeometryDrawing.Pen%2A> 도형의 윤곽선에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1544-105">The <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describes the shape's structure, the <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describes the shape's fill, and the <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describes the shape's outline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1544-106">예제</span><span class="sxs-lookup"><span data-stu-id="d1544-106">Example</span></span>  
 <span data-ttu-id="d1544-107">다음 예제에서는 <xref:System.Windows.Media.GeometryDrawing> 셰이프를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1544-107">The following example uses a <xref:System.Windows.Media.GeometryDrawing> to render a shape.</span></span> <span data-ttu-id="d1544-108">모양을 설명는 <xref:System.Windows.Media.GeometryGroup> 와 두 개의 <xref:System.Windows.Media.EllipseGeometry> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d1544-108">The shape is described by a <xref:System.Windows.Media.GeometryGroup> and two <xref:System.Windows.Media.EllipseGeometry> objects.</span></span> <span data-ttu-id="d1544-109">도형의 내부가 그려지는와 <xref:System.Windows.Media.LinearGradientBrush> 윤곽선을 사용 하 여 그린 및는 <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1544-109">The shape's interior is painted with a <xref:System.Windows.Media.LinearGradientBrush> and its outline is drawn with a <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span></span> <span data-ttu-id="d1544-110"><xref:System.Windows.Media.GeometryDrawing> 를 사용 하 여 표시 되는 <xref:System.Windows.Media.ImageDrawing> 및 <xref:System.Windows.Controls.Image> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d1544-110">The <xref:System.Windows.Media.GeometryDrawing> is displayed using an <xref:System.Windows.Media.ImageDrawing> and an <xref:System.Windows.Controls.Image> element.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 <span data-ttu-id="d1544-111">다음 그림과 결과 <xref:System.Windows.Media.GeometryDrawing>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1544-111">The following illustration shows the resulting <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="d1544-112">![개의 GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="d1544-112">![A GeometryDrawing of two ellipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
  
 <span data-ttu-id="d1544-113">보다 복잡 한 그리기를 만들려면 여러 그리기 개체를 사용 하 여 그리기 단일 복합 결합할 수 있습니다는 <xref:System.Windows.Media.DrawingGroup>합니다.</span><span class="sxs-lookup"><span data-stu-id="d1544-113">To create more complex drawings, you can combine multiple drawing objects into a single composite drawing using a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1544-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1544-114">See Also</span></span>  
 <xref:System.Windows.Media.DrawingGroup>  
 [<span data-ttu-id="d1544-115">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="d1544-115">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="d1544-116">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="d1544-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="d1544-117">합성 그리기 만들기</span><span class="sxs-lookup"><span data-stu-id="d1544-117">Create a Composite Drawing</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)
