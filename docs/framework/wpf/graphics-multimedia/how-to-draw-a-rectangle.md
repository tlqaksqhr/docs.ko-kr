---
title: '방법: 사각형 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 100f1a8062628e892e9a71b988bb2a8754ea6bad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561048"
---
# <a name="how-to-draw-a-rectangle"></a><span data-ttu-id="67588-102">방법: 사각형 그리기</span><span class="sxs-lookup"><span data-stu-id="67588-102">How to: Draw a Rectangle</span></span>
<span data-ttu-id="67588-103">사용 하 여 사각형을 그리는 방법을 보여 주는이 예제는 <xref:System.Windows.Shapes.Rectangle> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="67588-103">This example shows how to draw a rectangle by using the <xref:System.Windows.Shapes.Rectangle> element.</span></span>  
  
 <span data-ttu-id="67588-104">사각형을 그리려면 만들기는 <xref:System.Windows.Shapes.Rectangle> 요소를 지정 하 고 해당 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="67588-104">To draw a rectangle, create a <xref:System.Windows.Shapes.Rectangle> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="67588-105">사각형의 내부를 그리는 데 설정 해당 <xref:System.Windows.Shapes.Shape.Fill%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="67588-105">To paint the inside of the rectangle, set its <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="67588-106">사각형 윤곽선을 부여 하려면 사용 하 여 해당 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="67588-106">To give the rectangle an outline, use its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties.</span></span>  
  
 <span data-ttu-id="67588-107">모퉁이가 둥근 사각형을 선택적 지정 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 및 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="67588-107">To give the rectangle rounded corners, specify the optional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="67588-108"><xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 및 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 사각형의 모퉁이 둥글게 하는 데 사용 되는 타원의 x 축과 y 반지름 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67588-108">The <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties set the x-axis and y-axis radii of the ellipse that is used to round the corners of the rectangle.</span></span>  
  
 <span data-ttu-id="67588-109">다음 예제에서는 두 개의 <xref:System.Windows.Shapes.Rectangle> 요소를 그립니다는 <xref:System.Windows.Controls.Canvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="67588-109">In the following example, two <xref:System.Windows.Shapes.Rectangle> elements are drawn in a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="67588-110">첫 번째 사각형에는 <xref:System.Windows.Media.Brushes.Blue%2A> 내부 합니다.</span><span class="sxs-lookup"><span data-stu-id="67588-110">The first rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span></span> <span data-ttu-id="67588-111">두 번째 사각형에는 <xref:System.Windows.Media.Brushes.Blue%2A> 내부는 <xref:System.Windows.Media.Brushes.Black%2A> 윤곽선 및 모서리가 둥근된 합니다.</span><span class="sxs-lookup"><span data-stu-id="67588-111">The second rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior, a <xref:System.Windows.Media.Brushes.Black%2A> outline, and rounded corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67588-112">예제</span><span class="sxs-lookup"><span data-stu-id="67588-112">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 <span data-ttu-id="67588-113">이 예제에서는 한 <xref:System.Windows.Controls.Canvas> 사각형을 포함 하도록 사용할 수 있습니다 사각형 요소 (및 다른 모든 셰이프 요소) 함께 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control> 비 텍스트 콘텐츠를 지 원하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="67588-113">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the rectangles, you can use rectangle elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span> <span data-ttu-id="67588-114">사각형은 부분에 대해 배경을 제공 하는 데 특히 유용 실제로 <xref:System.Windows.Controls.Grid> 패널입니다.</span><span class="sxs-lookup"><span data-stu-id="67588-114">In fact, rectangles are particularly useful for providing backgrounds for portions of <xref:System.Windows.Controls.Grid> panels.</span></span> <span data-ttu-id="67588-115">예를 들어 참조는 [테이블 개요](../../../../docs/framework/wpf/advanced/table-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="67588-115">For an example, see the [Table Overview](../../../../docs/framework/wpf/advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="67588-116">이 예제는 보다 큰 예제의 일부 전체 샘플을 참조 하십시오. [셰이프 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)합니다.</span><span class="sxs-lookup"><span data-stu-id="67588-116">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67588-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67588-117">See Also</span></span>  
 <xref:System.Windows.Shapes.Rectangle>  
 [<span data-ttu-id="67588-118">셰이프 요소 샘플</span><span class="sxs-lookup"><span data-stu-id="67588-118">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [<span data-ttu-id="67588-119">WPF에서 Shape 및 기본 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="67588-119">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [<span data-ttu-id="67588-120">테이블 개요</span><span class="sxs-lookup"><span data-stu-id="67588-120">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
