---
title: "벡터 그래픽 개요"
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
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 603b76c999933f177a9e48ddb819562b8e4dd8f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="vector-graphics-overview"></a><span data-ttu-id="89c74-102">벡터 그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="89c74-102">Vector Graphics Overview</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="89c74-103">좌표계에 선, 사각형 및 기타 도형을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-103"> draws lines, rectangles, and other shapes on a coordinate system.</span></span> <span data-ttu-id="89c74-104">좌표 시스템의 다양 한에서 선택할 수 있지만 기본 좌표계 x 축이 오른쪽에 y 축은 아래쪽을 향하고 왼쪽 위 모퉁이에 원점에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-104">You can choose from a variety of coordinate systems, but the default coordinate system has the origin in the upper-left corner with the x-axis pointing to the right and the y-axis pointing down.</span></span> <span data-ttu-id="89c74-105">기본 좌표 시스템의 측정 단위 픽셀입니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-105">The unit of measure in the default coordinate system is the pixel.</span></span>  
  
## <a name="the-building-blocks-of-gdi"></a><span data-ttu-id="89c74-106">GDI +의 구성 요소</span><span class="sxs-lookup"><span data-stu-id="89c74-106">The Building Blocks of GDI+</span></span>  
 <span data-ttu-id="89c74-107">![벡터 그래픽](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span><span class="sxs-lookup"><span data-stu-id="89c74-107">![Vector graphic](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span></span>  
  
 <span data-ttu-id="89c74-108">컴퓨터 모니터의 점 그림 요소 또는 픽셀을 호출 하는 사각형 배열을에 디스플레이 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-108">A computer monitor creates its display on a rectangular array of dots called picture elements or pixels.</span></span> <span data-ttu-id="89c74-109">다음 모니터를 한 화면에 표시 하는 픽셀 수가 다릅니다 있으며 각 모니터에 표시 되는 픽셀 수 일반적으로 구성할 수 있습니다 어느 정도 까지는 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-109">The number of pixels that appear on the screen varies from one monitor to the next, and the number of pixels that appear on an individual monitor can usually be configured to some extent by the user.</span></span>  
  
 <span data-ttu-id="89c74-110">![벡터 그래픽](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span><span class="sxs-lookup"><span data-stu-id="89c74-110">![Vector graphic](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span></span>  
  
 <span data-ttu-id="89c74-111">사용 하는 경우 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 선, 사각형 또는 곡선을 그리려면 항목에 대 한 주요 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-111">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, rectangle, or curve, you provide certain key information about the item to be drawn.</span></span> <span data-ttu-id="89c74-112">예를 들어 두 점을 제공 하 여 줄을 지정할 수 있습니다 및 지정, 높이 및 너비를 제공 하 여 사각형을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-112">For example, you can specify a line by providing two points, and you can specify a rectangle by providing a point, a height, and a width.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="89c74-113">픽셀을 선, 사각형 또는 곡선을 표시 하도록 설정 해야 결정 하는 디스플레이 드라이버 소프트웨어와 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-113"> works in conjunction with the display driver software to determine which pixels must be turned on to show the line, rectangle, or curve.</span></span> <span data-ttu-id="89c74-114">다음 그림에서는 점 (12, 8) (4, 2) 점에서 선을 표시 하려면 켜져 있는 픽셀을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-114">The following illustration shows the pixels that are turned on to display a line from the point (4, 2) to the point (12, 8).</span></span>  
  
 <span data-ttu-id="89c74-115">![벡터 그래픽](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span><span class="sxs-lookup"><span data-stu-id="89c74-115">![Vector graphic](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span></span>  
  
 <span data-ttu-id="89c74-116">시간이 지남에 따라 특정 기본 빌딩 블록 입증 된 2 차원 그림을 만드는 데 가장 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-116">Over time, certain basic building blocks have proven to be the most useful for creating two-dimensional pictures.</span></span> <span data-ttu-id="89c74-117">지원 이러한 빌딩 블록 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 다음 목록에 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-117">These building blocks, which are all supported by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], are given in the following list:</span></span>  
  
-   <span data-ttu-id="89c74-118">선</span><span class="sxs-lookup"><span data-stu-id="89c74-118">Lines</span></span>  
  
-   <span data-ttu-id="89c74-119">사각형</span><span class="sxs-lookup"><span data-stu-id="89c74-119">Rectangles</span></span>  
  
-   <span data-ttu-id="89c74-120">타원</span><span class="sxs-lookup"><span data-stu-id="89c74-120">Ellipses</span></span>  
  
-   <span data-ttu-id="89c74-121">타원</span><span class="sxs-lookup"><span data-stu-id="89c74-121">Arcs</span></span>  
  
-   <span data-ttu-id="89c74-122">다각형</span><span class="sxs-lookup"><span data-stu-id="89c74-122">Polygons</span></span>  
  
-   <span data-ttu-id="89c74-123">카디널 스플라인</span><span class="sxs-lookup"><span data-stu-id="89c74-123">Cardinal splines</span></span>  
  
-   <span data-ttu-id="89c74-124">3차원 곡선 스플라인</span><span class="sxs-lookup"><span data-stu-id="89c74-124">Bezier splines</span></span>  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a><span data-ttu-id="89c74-125">그래픽 개체를 사용 하 여 그리기 위한 메서드</span><span class="sxs-lookup"><span data-stu-id="89c74-125">Methods For Drawing with a Graphics Object</span></span>  
 <span data-ttu-id="89c74-126"><xref:System.Drawing.Graphics> 클래스 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 위 목록에 항목을 그리기 위한 메서드를 제공: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (카디널 스플라인 용) 및 <xref:System.Drawing.Graphics.DrawBezier%2A>.</span><span class="sxs-lookup"><span data-stu-id="89c74-126">The <xref:System.Drawing.Graphics> class in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] provides the following methods for drawing the items in the previous list: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (for cardinal splines), and <xref:System.Drawing.Graphics.DrawBezier%2A>.</span></span> <span data-ttu-id="89c74-127">이러한 메서드의 오버 로드 됩니다. 즉, 각 메서드는 여러 가지 다른 매개 변수 목록을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-127">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="89c74-128">예를 들어 한 변형 된 개체가의 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드 수신는 <xref:System.Drawing.Pen> 개체와 다른 변형이 하는 동안 4 개의 정수는 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드 수신는 <xref:System.Drawing.Pen> 개체와 두 개의 <xref:System.Drawing.Point> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-128">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers, while another variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="89c74-129">선, 사각형 및 3 차원 곡선 스플라인 그리기 위한 메서드는 단일 호출에서 여러 항목을 그릴 동반 메서드: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, 및 <xref:System.Drawing.Graphics.DrawBeziers%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-129">The methods for drawing lines, rectangles, and Bézier splines have plural companion methods that draw several items in a single call: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, and <xref:System.Drawing.Graphics.DrawBeziers%2A>.</span></span> <span data-ttu-id="89c74-130">또한는 <xref:System.Drawing.Graphics.DrawCurve%2A> 메서드 도우미 메서드를가지고 <xref:System.Drawing.Graphics.DrawClosedCurve%2A>닫히는 연결 곡선의 끝 지점을 시작 하 여 곡선 지점, 합니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-130">Also, the <xref:System.Drawing.Graphics.DrawCurve%2A> method has a companion method, <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, that closes a curve by connecting the ending point of the curve to the starting point.</span></span>  
  
 <span data-ttu-id="89c74-131">모든 그리기 메서드에 <xref:System.Drawing.Graphics> 와 함께에서 작업 클래스는 <xref:System.Drawing.Pen> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-131">All of the drawing methods of the <xref:System.Drawing.Graphics> class work in conjunction with a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="89c74-132">모든 항목을 그리려면 개체 두 개 이상 만들어야 합니다:는 <xref:System.Drawing.Graphics> 개체 및 <xref:System.Drawing.Pen> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-132">To draw anything, you must create at least two objects: a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="89c74-133"><xref:System.Drawing.Pen> 개체 선 두께 및 색을 그릴 수 있도록 항목의 같은 특성을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-133">The <xref:System.Drawing.Pen> object stores attributes, such as line width and color, of the item to be drawn.</span></span> <span data-ttu-id="89c74-134"><xref:System.Drawing.Pen> 개체 그리기 메서드를 인수 중 하나로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89c74-134">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the drawing method.</span></span> <span data-ttu-id="89c74-135">예를 들어 한 변형 된 개체가의 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드 수신는 <xref:System.Drawing.Pen> 개체와 너비를 100, 50의 높이의 왼쪽 위 모퉁이를 사각형 그리기 다음 예에서 같이 4 개의 정수 (20, 10):</span><span class="sxs-lookup"><span data-stu-id="89c74-135">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers as shown in the following example, which draws a rectangle with a width of 100, a height of 50 and an upper-left corner of (20, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="89c74-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89c74-136">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="89c74-137">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="89c74-137">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="89c74-138">방법: 그리는 데 필요한 그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="89c74-138">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
