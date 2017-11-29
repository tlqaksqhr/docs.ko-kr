---
title: "GDI+의 다각형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 740a454873976e407843c417a7b09e5a5218398d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="polygons-in-gdi"></a><span data-ttu-id="dade4-102">GDI+의 다각형</span><span class="sxs-lookup"><span data-stu-id="dade4-102">Polygons in GDI+</span></span>
<span data-ttu-id="dade4-103">다각형은 세 개 이상의 직선 면으로 폐쇄형된 도형입니다.</span><span class="sxs-lookup"><span data-stu-id="dade4-103">A polygon is a closed shape with three or more straight sides.</span></span> <span data-ttu-id="dade4-104">예를 들어 삼각형 세 면 있는 다각형 사각형은 네 면 있는 다각형 있고, 오각형은 5 면 합니다.</span><span class="sxs-lookup"><span data-stu-id="dade4-104">For example, a triangle is a polygon with three sides, a rectangle is a polygon with four sides, and a pentagon is a polygon with five sides.</span></span> <span data-ttu-id="dade4-105">다음 그림에는 여러 다각형과 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dade4-105">The following illustration shows several polygons.</span></span>  
  
 <span data-ttu-id="dade4-106">![다각형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span><span class="sxs-lookup"><span data-stu-id="dade4-106">![Polygons](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span></span>  
  
## <a name="drawing-a-polygon"></a><span data-ttu-id="dade4-107">다각형을 그리기</span><span class="sxs-lookup"><span data-stu-id="dade4-107">Drawing a Polygon</span></span>  
 <span data-ttu-id="dade4-108">다각형을 그리려면 하려면는 <xref:System.Drawing.Graphics> 개체는 <xref:System.Drawing.Pen> 개체 및 배열을 <xref:System.Drawing.Point> (또는 <xref:System.Drawing.PointF>) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dade4-108">To draw a polygon, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and an array of <xref:System.Drawing.Point> (or <xref:System.Drawing.PointF>) objects.</span></span> <span data-ttu-id="dade4-109"><xref:System.Drawing.Graphics> 개체는 제공 된 <xref:System.Drawing.Graphics.DrawPolygon%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="dade4-109">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="dade4-110"><xref:System.Drawing.Pen> 개체 너비 다각형, 및 배열에 렌더링 하는 데 선의 색과 같은 특성이 저장 <xref:System.Drawing.Point> 개체를 직선으로 연결 포인트를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="dade4-110">The <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the polygon, and the array of <xref:System.Drawing.Point> objects stores the points to be connected by straight lines.</span></span> <span data-ttu-id="dade4-111"><xref:System.Drawing.Pen> 개체와 배열을 <xref:System.Drawing.Point> 개체를 인수로 전달 되는 <xref:System.Drawing.Graphics.DrawPolygon%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="dade4-111">The <xref:System.Drawing.Pen> object and the array of <xref:System.Drawing.Point> objects are passed as arguments to the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="dade4-112">다음 예제에서는 3 면 다각형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="dade4-112">The following example draws a three-sided polygon.</span></span> <span data-ttu-id="dade4-113">세 개의 요소는 `myPointArray`: (0, 0) (50, 30) (30, 60)입니다.</span><span class="sxs-lookup"><span data-stu-id="dade4-113">Note that there are only three points in `myPointArray`: (0, 0), (50, 30), and (30, 60).</span></span> <span data-ttu-id="dade4-114"><xref:System.Drawing.Graphics.DrawPolygon%2A> 메서드에서 선을 그려 다각형을 자동으로 닫습니다 (30, 60) (0, 0) 하 여 시작 지점으로 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="dade4-114">The <xref:System.Drawing.Graphics.DrawPolygon%2A> method automatically closes the polygon by drawing a line from (30, 60) back to the starting point (0, 0).</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 <span data-ttu-id="dade4-115">다음 그림에는 다각형 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dade4-115">The following illustration shows the polygon.</span></span>  
  
 <span data-ttu-id="dade4-116">![다각형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span><span class="sxs-lookup"><span data-stu-id="dade4-116">![Polygon](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dade4-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dade4-117">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="dade4-118">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="dade4-118">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="dade4-119">방법: 펜 만들기</span><span class="sxs-lookup"><span data-stu-id="dade4-119">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
