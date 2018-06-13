---
title: B&#233;zier GDI +의 곡선 스플라인
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: 2e247ec2bcd57c2fb2f5c32f61d38a2e7a267ff1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517575"
---
# <a name="b233zier-splines-in-gdi"></a><span data-ttu-id="7c71e-102">B&#233;zier GDI +의 곡선 스플라인</span><span class="sxs-lookup"><span data-stu-id="7c71e-102">B&#233;zier Splines in GDI+</span></span>
<span data-ttu-id="7c71e-103">점이 4 개로 지정 된 곡선을 베 지 어 스플라인을: 두 끝점 (p1 및 p2) 및 두 개의 제어점 (c1, c2).</span><span class="sxs-lookup"><span data-stu-id="7c71e-103">A Bézier spline is a curve specified by four points: two end points (p1 and p2) and two control points (c1 and c2).</span></span> <span data-ttu-id="7c71e-104">곡선 p 1에서 시작 되 고 p 2에서 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="7c71e-104">The curve begins at p1 and ends at p2.</span></span> <span data-ttu-id="7c71e-105">곡선의 제어점 통해서도 전달 되지 않지만 제어점 자석과 곡선 특정 방향으로 가져와서 곡률 하는 방식에 영향을 주는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c71e-105">The curve does not pass through the control points, but the control points act as magnets, pulling the curve in certain directions and influencing the way the curve bends.</span></span> <span data-ttu-id="7c71e-106">다음 그림에서는 해당 끝점 및 제어점 함께 베 지 어 곡선을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c71e-106">The following illustration shows a Bézier curve along with its endpoints and control points.</span></span>  
  
 <span data-ttu-id="7c71e-107">![베 지 어 스플라인을](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span><span class="sxs-lookup"><span data-stu-id="7c71e-107">![Bezier Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span></span>  
  
 <span data-ttu-id="7c71e-108">곡선 p 1에서 시작 하 고 제어점 c 1을 향해 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c71e-108">The curve starts at p1 and moves toward the control point c1.</span></span> <span data-ttu-id="7c71e-109">P 1에서 곡선 접선은 p 1에서 c 1에 그려진 선입니다.</span><span class="sxs-lookup"><span data-stu-id="7c71e-109">The tangent line to the curve at p1 is the line drawn from p1 to c1.</span></span> <span data-ttu-id="7c71e-110">Endpoint p 2에서 접선은 c 2에서 p 2로 가져온 선입니다.</span><span class="sxs-lookup"><span data-stu-id="7c71e-110">The tangent line at the endpoint p2 is the line drawn from c2 to p2.</span></span>  
  
## <a name="drawing-bzier-splines"></a><span data-ttu-id="7c71e-111">3 차원 곡선 스플라인 그리기</span><span class="sxs-lookup"><span data-stu-id="7c71e-111">Drawing Bézier Splines</span></span>  
 <span data-ttu-id="7c71e-112">3 차원 곡선 스플라인 그리기, 하려면의 인스턴스는 <xref:System.Drawing.Graphics> 클래스 및 <xref:System.Drawing.Pen>합니다.</span><span class="sxs-lookup"><span data-stu-id="7c71e-112">To draw a Bézier spline, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Pen>.</span></span> <span data-ttu-id="7c71e-113">인스턴스는 <xref:System.Drawing.Graphics> 클래스를 제공는 <xref:System.Drawing.Graphics.DrawBezier%2A> 메서드, 및 <xref:System.Drawing.Pen> 너비는 곡선을 렌더링 하는 데 사용 되는 선의 색과 같은 특성을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c71e-113">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawBezier%2A> method, and the <xref:System.Drawing.Pen> stores attributes, such as width and color, of the line used to render the curve.</span></span> <span data-ttu-id="7c71e-114"><xref:System.Drawing.Pen> 에 대 한 인수 중 하나로 전달 되는 <xref:System.Drawing.Graphics.DrawBezier%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="7c71e-114">The <xref:System.Drawing.Pen> is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawBezier%2A> method.</span></span> <span data-ttu-id="7c71e-115">나머지 인수에 전달 된 <xref:System.Drawing.Graphics.DrawBezier%2A> 메서드는 끝점 및 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="7c71e-115">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawBezier%2A> method are the endpoints and the control points.</span></span> <span data-ttu-id="7c71e-116">다음 예제에서는 시작 지점 (0, 0)으로 베 지 어 스플라인을 그립니다 포인트 (40, 20) 및 (80, 150)을 제어 하 고 끝 지점 (100, 10):</span><span class="sxs-lookup"><span data-stu-id="7c71e-116">The following example draws a Bézier spline with starting point (0, 0), control points (40, 20) and (80, 150), and ending point (100, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 <span data-ttu-id="7c71e-117">다음 그림에서는 곡선, 제어 지점 및 두 개의 접선을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c71e-117">The following illustration shows the curve, the control points, and two tangent lines.</span></span>  
  
 <span data-ttu-id="7c71e-118">![베 지 어 스플라인을](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span><span class="sxs-lookup"><span data-stu-id="7c71e-118">![Bezier Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span></span>  
  
 <span data-ttu-id="7c71e-119">베 지 어 스플라인은 디자인 자동차 산업에 대 한 원래 피에르 베 지 어에서 개발한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7c71e-119">Bézier splines were originally developed by Pierre Bézier for design in the automotive industry.</span></span> <span data-ttu-id="7c71e-120">다양 한 유형의 컴퓨터 보조 디자인에 유용한 것으로 입증 된 이후로 하며 글꼴 윤곽선을 정의 하는 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c71e-120">They have since proven to be useful in many types of computer-aided design and are also used to define the outlines of fonts.</span></span> <span data-ttu-id="7c71e-121">베 지 어 스플라인을 다양 한 셰이프를 다음 그림에 나와 중 일부는 양도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c71e-121">Bézier splines can yield a wide variety of shapes, some of which are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="7c71e-122">![경로](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span><span class="sxs-lookup"><span data-stu-id="7c71e-122">![Paths](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c71e-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c71e-123">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [<span data-ttu-id="7c71e-124">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="7c71e-124">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="7c71e-125">곡선 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="7c71e-125">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)  
 [<span data-ttu-id="7c71e-126">방법: 그리는 데 필요한 그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="7c71e-126">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="7c71e-127">방법: 펜 만들기</span><span class="sxs-lookup"><span data-stu-id="7c71e-127">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
