---
title: "GDI+의 그래픽 경로"
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
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 022a591a1d646b154c2bd59a2f2ab21b78b9dbda
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="graphics-paths-in-gdi"></a><span data-ttu-id="bb804-102">GDI+의 그래픽 경로</span><span class="sxs-lookup"><span data-stu-id="bb804-102">Graphics Paths in GDI+</span></span>
<span data-ttu-id="bb804-103">경로 선, 사각형 및 간단한 곡선을 결합 하 여 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-103">Paths are formed by combining lines, rectangles, and simple curves.</span></span> <span data-ttu-id="bb804-104">설명한 대로 [벡터 그래픽 개요](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md) 다음과 같은 기본 빌딩 블록 그림 그리기에 대 한 가장 유용한 입증 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-104">Recall from the [Vector Graphics Overview](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md) that the following basic building blocks have proven to be the most useful for drawing pictures:</span></span>  
  
-   <span data-ttu-id="bb804-105">선</span><span class="sxs-lookup"><span data-stu-id="bb804-105">Lines</span></span>  
  
-   <span data-ttu-id="bb804-106">사각형</span><span class="sxs-lookup"><span data-stu-id="bb804-106">Rectangles</span></span>  
  
-   <span data-ttu-id="bb804-107">타원</span><span class="sxs-lookup"><span data-stu-id="bb804-107">Ellipses</span></span>  
  
-   <span data-ttu-id="bb804-108">타원</span><span class="sxs-lookup"><span data-stu-id="bb804-108">Arcs</span></span>  
  
-   <span data-ttu-id="bb804-109">다각형</span><span class="sxs-lookup"><span data-stu-id="bb804-109">Polygons</span></span>  
  
-   <span data-ttu-id="bb804-110">카디널 스플라인</span><span class="sxs-lookup"><span data-stu-id="bb804-110">Cardinal splines</span></span>  
  
-   <span data-ttu-id="bb804-111">3 차원 곡선 스플라인</span><span class="sxs-lookup"><span data-stu-id="bb804-111">Bézier splines</span></span>  
  
 <span data-ttu-id="bb804-112">GDI +에서 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체를 사용 하면 단일 단위로 이러한 빌딩 블록의 시퀀스를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-112">In GDI+, the <xref:System.Drawing.Drawing2D.GraphicsPath> object allows you to collect a sequence of these building blocks into a single unit.</span></span> <span data-ttu-id="bb804-113">선, 사각형, 다각형 및 곡선의 전체 시퀀스를 호출 하 여 그릴 수 있습니다는 <xref:System.Drawing.Graphics.DrawPath%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-113">The entire sequence of lines, rectangles, polygons, and curves can then be drawn with one call to the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="bb804-114">다음 그림에는 선, 호를 베 지 어 스플라인 및 카디널 스플라인을 결합 하 여 만든 경로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-114">The following illustration shows a path created by combining a line, an arc, a Bézier spline, and a cardinal spline.</span></span>  
  
 <span data-ttu-id="bb804-115">![경로](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span><span class="sxs-lookup"><span data-stu-id="bb804-115">![Path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span></span>  
  
## <a name="using-a-path"></a><span data-ttu-id="bb804-116">경로 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="bb804-116">Using a Path</span></span>  
 <span data-ttu-id="bb804-117"><xref:System.Drawing.Drawing2D.GraphicsPath> 을 그릴 수 있도록 항목의 시퀀스를 만들기 위한 다음 메서드를 제공 하는 클래스: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (카디널 스플라인 용) 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-117">The <xref:System.Drawing.Drawing2D.GraphicsPath> class provides the following methods for creating a sequence of items to be drawn: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (for cardinal splines), and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span></span> <span data-ttu-id="bb804-118">이러한 메서드의 오버 로드 됩니다. 즉, 각 메서드는 여러 가지 다른 매개 변수 목록을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-118">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="bb804-119">예를 들어 한 변형 된 개체가의 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 메서드 4 개의 정수 및 다른 변형이 수신는 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 메서드 두 수신 <xref:System.Drawing.Point> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-119">For example, one variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives four integers, and another variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="bb804-120">경로에 선, 사각형 및 베 지 어 스플라인을 추가 하기 위한 메서드는 한 번의 호출 경로에 여러 개의 항목을 추가 하는 동반 메서드가: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-120">The methods for adding lines, rectangles, and Bézier splines to a path have plural companion methods that add several items to the path in a single call: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span></span> <span data-ttu-id="bb804-121">또한는 <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> 메서드는 도우미 메서드가 <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, 폐곡선 또는 원형 경로에 추가 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-121">Also, the <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> methods have companion methods, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, that add a closed curve or pie to the path.</span></span>  
  
 <span data-ttu-id="bb804-122">패스를 그릴 하려면는 <xref:System.Drawing.Graphics> 개체는 <xref:System.Drawing.Pen> 개체 및 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-122">To draw a path, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="bb804-123"><xref:System.Drawing.Graphics> 개체 제공는 <xref:System.Drawing.Graphics.DrawPath%2A> 메서드, 및 <xref:System.Drawing.Pen> 개체는 경로 렌더링 하는 데 사용 하는 줄의 색, 너비 등의 속성에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-123">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPath%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the path.</span></span> <span data-ttu-id="bb804-124"><xref:System.Drawing.Drawing2D.GraphicsPath> 개체의 선 및 곡선의 경로 구성 하는 순서를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-124">The <xref:System.Drawing.Drawing2D.GraphicsPath> object stores the sequence of lines and curves that make up the path.</span></span> <span data-ttu-id="bb804-125"><xref:System.Drawing.Pen> 개체 및 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체를 인수로 전달 되는 <xref:System.Drawing.Graphics.DrawPath%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="bb804-125">The <xref:System.Drawing.Pen> object and the <xref:System.Drawing.Drawing2D.GraphicsPath> object are passed as arguments to the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="bb804-126">다음 예제에서는 줄, 타원, 및 되는 베 지 어 스플라인을 구성 되는 경로 그립니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-126">The following example draws a path that consists of a line, an ellipse, and a Bézier spline:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 <span data-ttu-id="bb804-127">다음 그림의 경로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-127">The following illustration shows the path.</span></span>  
  
 <span data-ttu-id="bb804-128">![경로](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span><span class="sxs-lookup"><span data-stu-id="bb804-128">![Path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span></span>  
  
 <span data-ttu-id="bb804-129">선, 사각형 및 곡선으로 분할 경로 추가 하는 것 외에도 경로에 경로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-129">In addition to adding lines, rectangles, and curves to a path, you can add paths to a path.</span></span> <span data-ttu-id="bb804-130">이 옵션을 사용 하면 대규모의 복잡 한 경로 형성 하는 기존 경로 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-130">This allows you to combine existing paths to form large, complex paths.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 <span data-ttu-id="bb804-131">경로에 추가할 수 있습니다 다른 두 개의 항목이: 문자열 및 파이 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-131">There are two other items you can add to a path: strings and pies.</span></span> <span data-ttu-id="bb804-132">원형에는 타원의 내부의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-132">A pie is a portion of the interior of an ellipse.</span></span> <span data-ttu-id="bb804-133">다음 예제에서는 호, 카디널 스플라인을, 문자열, 및 원형에서 경로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-133">The following example creates a path from an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 <span data-ttu-id="bb804-134">다음 그림의 경로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-134">The following illustration shows the path.</span></span> <span data-ttu-id="bb804-135">경로를; 연결 하지 않은 참고 호, 카디널 스플라인을, 문자열 및 원형 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb804-135">Note that a path does not have to be connected; the arc, cardinal spline, string, and pie are separated.</span></span>  
  
 <span data-ttu-id="bb804-136">![경로](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span><span class="sxs-lookup"><span data-stu-id="bb804-136">![Paths](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb804-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb804-137">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [<span data-ttu-id="bb804-138">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="bb804-138">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="bb804-139">방법: 그리는 데 필요한 그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="bb804-139">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="bb804-140">경로 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="bb804-140">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
