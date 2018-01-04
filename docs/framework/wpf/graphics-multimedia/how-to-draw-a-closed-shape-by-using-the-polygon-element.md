---
title: "방법: Polygon 요소를 사용하여 닫힌 도형 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0cf842c22238105510b13407d55c8c9773f84a70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a><span data-ttu-id="cb410-102">방법: Polygon 요소를 사용하여 닫힌 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="cb410-102">How to: Draw a Closed Shape by Using the Polygon Element</span></span>
<span data-ttu-id="cb410-103">사용 하 여 닫힌된 셰이프를 그리는 방법을 보여 주는이 예제는 <xref:System.Windows.Shapes.Polygon> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cb410-103">This example shows how to draw a closed shape by using the <xref:System.Windows.Shapes.Polygon> element.</span></span> <span data-ttu-id="cb410-104">폐쇄형된 도형 그리기를 만들는 <xref:System.Windows.Shapes.Polygon> 요소 및 사용 하 여 해당 <xref:System.Windows.Shapes.Polygon.Points%2A> 속성을 통해 도형의 꼭지점을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb410-104">To draw a closed shape, create a <xref:System.Windows.Shapes.Polygon> element and use its <xref:System.Windows.Shapes.Polygon.Points%2A> property to specify the vertices of a shape.</span></span> <span data-ttu-id="cb410-105">선이 그려집니다 자동으로 첫 번째 및 마지막 점을 연결 하는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb410-105">A line is automatically drawn that connects the first and last points.</span></span> <span data-ttu-id="cb410-106">마지막으로 지정 된 <xref:System.Windows.Shapes.Shape.Fill%2A>, 즉 <xref:System.Windows.Shapes.Shape.Stroke%2A>, 또는 둘 다 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb410-106">Finally, specify a <xref:System.Windows.Shapes.Shape.Fill%2A>, a <xref:System.Windows.Shapes.Shape.Stroke%2A>, or both.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb410-107">예</span><span class="sxs-lookup"><span data-stu-id="cb410-107">Example</span></span>  
 <span data-ttu-id="cb410-108">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 지점에 대 한 유효한 구문은 공백으로 구분 된 목록 쉼표로 구분 된 x 및 y 좌표 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="cb410-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 <span data-ttu-id="cb410-109">이 예제에서는 사용 하지는 않지만 <xref:System.Windows.Controls.Canvas> 다각형을 포함 하는 데 다각형 요소 (및 다른 모든 셰이프 요소) 함께 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control> 비 텍스트 콘텐츠를 지 원하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb410-109">Although the example uses a <xref:System.Windows.Controls.Canvas> to contain the polygons, you can use polygon elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="cb410-110">이 예제는 보다 큰 예제의 일부 전체 샘플을 참조 하십시오. [셰이프 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb410-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>
