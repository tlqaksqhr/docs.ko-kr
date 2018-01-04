---
title: "방법: Polyline 요소를 사용하여 다중선 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b0b027aa34b310413fa02e81149292fabb40f79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="2f0f3-102">방법: Polyline 요소를 사용하여 다중선 그리기</span><span class="sxs-lookup"><span data-stu-id="2f0f3-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="2f0f3-103">사용 하 여 일련의 연결 된 줄은 다중선 그리는 방법을 보여 주는이 예제는 <xref:System.Windows.Shapes.Polyline> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f3-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="2f0f3-104">다중선을 그리려면 만들기는 <xref:System.Windows.Shapes.Polyline> 요소 및 사용 하 여 해당 <xref:System.Windows.Shapes.Polyline.Points%2A> 속성을 통해 이러한 셰이프 기능을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f3-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="2f0f3-105">마지막으로 사용 하 여는 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 획 줄에 표시 되지 않으므로 폴리라인에서 설명 하는 속성에 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f3-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f0f3-106">때문에 <xref:System.Windows.Shapes.Polyline> 요소는 닫힌된 셰이프는 <xref:System.Windows.Shapes.Shape.Fill%2A> 도형 윤곽선을 의도적으로 종결 하는 경우에 속성에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f3-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="2f0f3-107">와 닫힌된 셰이프를 만들려면는 <xref:System.Windows.Shapes.Shape.Fill%2A>를 사용 하 여 한 <xref:System.Windows.Shapes.Polygon> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f3-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="2f0f3-108">다음 예제에서는 두 개의 그립니다 <xref:System.Windows.Shapes.Polyline> 내부 요소는 <xref:System.Windows.Controls.Canvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f3-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f0f3-109">예</span><span class="sxs-lookup"><span data-stu-id="2f0f3-109">Example</span></span>  
 <span data-ttu-id="2f0f3-110">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 지점에 대 한 유효한 구문은 공백으로 구분 된 목록 쉼표로 구분 된 x 및 y 좌표 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f3-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="2f0f3-111">이 예제에서는 한 <xref:System.Windows.Controls.Canvas> 다중선을 포함 하 여 사용할 수 있습니다 폴리라인 요소 (및 다른 모든 셰이프 요소) 함께 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control> 비 텍스트 콘텐츠를 지 원하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f3-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="2f0f3-112">이 예제는 보다 큰 예제의 일부 전체 샘플을 참조 하십시오. [셰이프 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f0f3-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f0f3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f0f3-113">See Also</span></span>  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Shapes.Polygon>  
 <xref:System.Windows.Shapes.Shape>  
 [<span data-ttu-id="2f0f3-114">셰이프 요소 샘플</span><span class="sxs-lookup"><span data-stu-id="2f0f3-114">Shape Elements Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [<span data-ttu-id="2f0f3-115">WPF에서 Shape 및 기본 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="2f0f3-115">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
