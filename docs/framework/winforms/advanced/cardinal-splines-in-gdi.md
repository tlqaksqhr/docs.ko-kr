---
title: "GDI+의 카디널 스플라인"
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
- splines [Windows Forms], cardinal
- GDI+, cardinal splines
- cardinal splines
ms.assetid: 09b3797a-6294-422d-9adf-a5a0a7695c0c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b7653e05fff241f05836624ff02273fb8c24ef6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cardinal-splines-in-gdi"></a><span data-ttu-id="11ad3-102">GDI+의 카디널 스플라인</span><span class="sxs-lookup"><span data-stu-id="11ad3-102">Cardinal Splines in GDI+</span></span>
<span data-ttu-id="11ad3-103">카디널 스플라인에 더 큰 곡선을 형성 하는 개별 곡선 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-103">A cardinal spline is a sequence of individual curves joined to form a larger curve.</span></span> <span data-ttu-id="11ad3-104">스플라인을은 포인트와 장력 매개 변수 배열에 의해 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-104">The spline is specified by an array of points and a tension parameter.</span></span> <span data-ttu-id="11ad3-105">카디널 스플라인; 배열에서 각 지점 매끄럽게 통과 날카로운 모퉁이가 없고 및 곡선의 다듬기에 급격 한 변경 내용이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-105">A cardinal spline passes smoothly through each point in the array; there are no sharp corners and no abrupt changes in the tightness of the curve.</span></span> <span data-ttu-id="11ad3-106">다음 그림의 점과 집합의 각 요소를 통해 전달 되는 카디널 스플라인을 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-106">The following illustration shows a set of points and a cardinal spline that passes through each point in the set.</span></span>  
  
 <span data-ttu-id="11ad3-107">![카디널 스플라인](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art09.gif "Aboutgdip02_art09")</span><span class="sxs-lookup"><span data-stu-id="11ad3-107">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art09.gif "Aboutgdip02_art09")</span></span>  
  
## <a name="physical-and-mathematical-splines"></a><span data-ttu-id="11ad3-108">물리적 및 수학 곡선 스플라인</span><span class="sxs-lookup"><span data-stu-id="11ad3-108">Physical and Mathematical Splines</span></span>  
 <span data-ttu-id="11ad3-109">실제 스플라인은 목재 또는 유연한 기타 자료의 씬.</span><span class="sxs-lookup"><span data-stu-id="11ad3-109">A physical spline is a thin piece of wood or other flexible material.</span></span> <span data-ttu-id="11ad3-110">수학 스플라인 도입 되기 전에 디자이너는 곡선을 그리는 물리적 스플라인을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-110">Before the advent of mathematical splines, designers used physical splines to draw curves.</span></span> <span data-ttu-id="11ad3-111">디자이너는 스플라인 종이에 배치 하 고 주어진된 점의 집합에 고정할 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-111">A designer would place the spline on a piece of paper and anchor it to a given set of points.</span></span> <span data-ttu-id="11ad3-112">디자이너 만들 수는 곡선 스플라인 따라 그리는 방식으로 펜 또는 연필을 사용.</span><span class="sxs-lookup"><span data-stu-id="11ad3-112">The designer could then create a curve by drawing along the spline with a pen or pencil.</span></span> <span data-ttu-id="11ad3-113">지정 된 일련의 점으로 다양 한 물리적 스플라인의 속성에 따라 곡선을 향상 시킬 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-113">A given set of points could yield a variety of curves, depending on the properties of the physical spline.</span></span> <span data-ttu-id="11ad3-114">예를 들어 만들었을 높은 저항 잘 매우 유연한 스플라인 보다 다른 곡선을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-114">For example, a spline with a high resistance to bending would produce a different curve than an extremely flexible spline.</span></span>  
  
 <span data-ttu-id="11ad3-115">수학 스플라인에 대 한 수식은 수학적 스플라인에 의해 만들어진 곡선의 곡선 물리적 스플라인으로 만들어 졌 던 비슷합니다 되므로 유연한 막대의 속성에 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-115">The formulas for mathematical splines are based on the properties of flexible rods, so the curves produced by mathematical splines are similar to the curves that were once produced by physical splines.</span></span> <span data-ttu-id="11ad3-116">장력이 다른 물리적 스플라인 주어진된 점의 집합을 통해 다른 곡선을 생성 합니다, 처럼 수학 스플라인 장력 매개 변수에 대해 서로 다른 값으로는 주어진된 점의 집합을 통해 다른 곡선을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-116">Just as physical splines of different tension will produce different curves through a given set of points, mathematical splines with different values for the tension parameter will produce different curves through a given set of points.</span></span> <span data-ttu-id="11ad3-117">다음 그림에서는 동일한 점 집합을 통해 전달 되는 4 개의 카디널 스플라인 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-117">The following illustration shows four cardinal splines passing through the same set of points.</span></span> <span data-ttu-id="11ad3-118">각 스플라인 장력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-118">The tension is shown for each spline.</span></span> <span data-ttu-id="11ad3-119">0의 장력 점 간 최단 방식으로 (직선)를 사용 하 여 물리적 장력이 무한에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-119">A tension of 0 corresponds to infinite physical tension, forcing the curve to take the shortest way (straight lines) between points.</span></span> <span data-ttu-id="11ad3-120">1의 장력 스플라인을 이상 총 벤드는 경로 없음 물리적 장력에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-120">A tension of 1 corresponds to no physical tension, allowing the spline to take the path of least total bend.</span></span> <span data-ttu-id="11ad3-121">장력 값이 1 보다 큰, 곡선 긴 경로에 푸시 압축된 spring 처럼 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-121">With tension values greater than 1, the curve behaves like a compressed spring, pushed to take a longer path.</span></span>  
  
 <span data-ttu-id="11ad3-122">![카디널 스플라인](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art10.gif "Aboutgdip02_art10")</span><span class="sxs-lookup"><span data-stu-id="11ad3-122">![Cardinal Splines](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art10.gif "Aboutgdip02_art10")</span></span>  
  
 <span data-ttu-id="11ad3-123">앞의 그림에 4 개의 스플라인 시작 지점에 동일한 탄젠트 라인을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-123">The four splines in the preceding illustration share the same tangent line at the starting point.</span></span> <span data-ttu-id="11ad3-124">탄젠트는 곡선을 따라 다음 점으로 시작 지점에서 가져온 선입니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-124">The tangent is the line drawn from the starting point to the next point along the curve.</span></span> <span data-ttu-id="11ad3-125">마찬가지로, 공유의 탄젠트 끝점은 곡선의 끝점에서 이전 지점으로 그린 선입니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-125">Likewise, the shared tangent at the ending point is the line drawn from the ending point to the previous point on the curve.</span></span>  
  
 <span data-ttu-id="11ad3-126">카디널 스플라인 그리기, 하려면의 인스턴스는 <xref:System.Drawing.Graphics> 클래스는 <xref:System.Drawing.Pen>, 및의 배열을 <xref:System.Drawing.Point> 개체의 인스턴스는 <xref:System.Drawing.Graphics> 클래스를 제공는 <xref:System.Drawing.Graphics.DrawCurve%2A> 스플라인을 그립니다, 메서드 및 <xref:System.Drawing.Pen> 선 두께 및 색 등 스플라인의 특성을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-126">To draw a cardinal spline, you need an instance of the <xref:System.Drawing.Graphics> class, a <xref:System.Drawing.Pen>, and an array of <xref:System.Drawing.Point> objects The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawCurve%2A> method, which draws the spline, and the <xref:System.Drawing.Pen> stores attributes of the spline, such as line width and color.</span></span> <span data-ttu-id="11ad3-127">배열 <xref:System.Drawing.Point> 곡선은 통과 하는 지점을 저장 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-127">The array of <xref:System.Drawing.Point> objects stores the points that the curve will pass through.</span></span> <span data-ttu-id="11ad3-128">다음 코드 예제에는에 있는 요소를 통해 전달 되는 카디널 스플라인의 그리는 방법을 보여 줍니다 `myPointArray`합니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-128">The following code example shows how to draw a cardinal spline that passes through the points in `myPointArray`.</span></span> <span data-ttu-id="11ad3-129">세 번째 매개 변수는 장력 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ad3-129">The third parameter is the tension.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#31)]
 [!code-vb[LinesCurvesAndShapes#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="11ad3-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11ad3-130">See Also</span></span>  
 [<span data-ttu-id="11ad3-131">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="11ad3-131">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="11ad3-132">곡선 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="11ad3-132">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
