---
title: '방법: 카디널 스플라인 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cardinal splines [Windows Forms], drawing
- drawing [Windows Forms], cardinal splines
- graphics [Windows Forms], cardinal splines
ms.assetid: a4a41e80-4461-4b47-b6bd-2c5e68881994
ms.openlocfilehash: 3ad06eb28e1d8e6b5d5f4a77e545f174d8a68d9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525062"
---
# <a name="how-to-draw-cardinal-splines"></a><span data-ttu-id="e57c7-102">방법: 카디널 스플라인 그리기</span><span class="sxs-lookup"><span data-stu-id="e57c7-102">How to: Draw Cardinal Splines</span></span>
<span data-ttu-id="e57c7-103">카디널 스플라인 주어진된 점의 집합을 통해 원활 하 게 전달 되는 곡선입니다.</span><span class="sxs-lookup"><span data-stu-id="e57c7-103">A cardinal spline is a curve that passes smoothly through a given set of points.</span></span> <span data-ttu-id="e57c7-104">카디널 스플라인 그리기, 하려면 만듭니다는 <xref:System.Drawing.Graphics> 개체를 가리키는 배열 주소 전달는 <xref:System.Drawing.Graphics.DrawCurve%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="e57c7-104">To draw a cardinal spline, create a <xref:System.Drawing.Graphics> object and pass the address of an array of points to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span>  
  
### <a name="drawing-a-bell-shaped-cardinal-spline"></a><span data-ttu-id="e57c7-105">종 모양 카디널 스플라인 그리기</span><span class="sxs-lookup"><span data-stu-id="e57c7-105">Drawing a Bell-Shaped Cardinal Spline</span></span>  
  
-   <span data-ttu-id="e57c7-106">다음 예제에서는 5 개의 지정 된 점을 통해 전달 되는 종 모양의 카디널 스플라인을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="e57c7-106">The following example draws a bell-shaped cardinal spline that passes through five designated points.</span></span> <span data-ttu-id="e57c7-107">다음 그림에서는 5 개의 점과 곡선을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e57c7-107">The following illustration shows the curve and five points.</span></span>  
  
     <span data-ttu-id="e57c7-108">![카디널 스플라인](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")</span><span class="sxs-lookup"><span data-stu-id="e57c7-108">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1.png "CardinalSpline1")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#21)]  
  
### <a name="drawing-a-closed-cardinal-spline"></a><span data-ttu-id="e57c7-109">폐쇄형된 카디널 스플라인 그리기</span><span class="sxs-lookup"><span data-stu-id="e57c7-109">Drawing a Closed Cardinal Spline</span></span>  
  
-   <span data-ttu-id="e57c7-110">사용 하 여는 <xref:System.Drawing.Graphics.DrawClosedCurve%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스 되는 폐쇄형된 카디널 스플라인을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="e57c7-110">Use the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method of the <xref:System.Drawing.Graphics> class to draw a closed cardinal spline.</span></span> <span data-ttu-id="e57c7-111">폐쇄형된 카디널 스플라인 곡선 배열에서 마지막 점을 계속 하 고 첫 번째 포인터는 배열에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57c7-111">In a closed cardinal spline, the curve continues through the last point in the array and connects with the first point in the array.</span></span> <span data-ttu-id="e57c7-112">다음 예제에서는 6 개의 지정 된 점을 통과 하는 폐쇄형된 카디널 스플라인을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="e57c7-112">The following example draws a closed cardinal spline that passes through six designated points.</span></span> <span data-ttu-id="e57c7-113">다음 그림에서는 6 개 포인트에 따라 닫힌된 스플라인 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e57c7-113">The following illustration shows the closed spline along with the six points.</span></span>  
  
 <span data-ttu-id="e57c7-114">![카디널 스플라인](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")</span><span class="sxs-lookup"><span data-stu-id="e57c7-114">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline1a.png "CardinalSpline1A")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#22)]  
  
### <a name="changing-the-bend-of-a-cardinal-spline"></a><span data-ttu-id="e57c7-115">카디널 스플라인 굴곡 변경</span><span class="sxs-lookup"><span data-stu-id="e57c7-115">Changing the Bend of a Cardinal Spline</span></span>  
  
-   <span data-ttu-id="e57c7-116">카디널 스플라인의 장력 인수를 전달 하 여 굴곡 방식을 변경는 <xref:System.Drawing.Graphics.DrawCurve%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="e57c7-116">Change the way a cardinal spline bends by passing a tension argument to the <xref:System.Drawing.Graphics.DrawCurve%2A> method.</span></span> <span data-ttu-id="e57c7-117">다음 예제에서는 동일한 점 집합이 통과 하는 세 개의 카디널 스플라인을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="e57c7-117">The following example draws three cardinal splines that pass through the same set of points.</span></span> <span data-ttu-id="e57c7-118">다음 그림에서는 세 가지 스플라인 해당 장력 값과 함께 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e57c7-118">The following illustration shows the three splines along with their tension values.</span></span> <span data-ttu-id="e57c7-119">참고는 장력이 0 인 점 직선으로 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57c7-119">Note that when the tension is 0, the points are connected by straight lines.</span></span>  
  
 <span data-ttu-id="e57c7-120">![카디널 스플라인](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")</span><span class="sxs-lookup"><span data-stu-id="e57c7-120">![Cardinal Spline](../../../../docs/framework/winforms/advanced/media/cardinalspline2.png "CardinalSpline2")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#23)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e57c7-121">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e57c7-121">Compiling the Code</span></span>  
 <span data-ttu-id="e57c7-122">앞의 예제에서는 Windows Forms에서 사용 하도록 설계 되었으며 필요한 <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수는 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="e57c7-122">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e57c7-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e57c7-123">See Also</span></span>  
 [<span data-ttu-id="e57c7-124">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="e57c7-124">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="e57c7-125">곡선 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="e57c7-125">Constructing and Drawing Curves</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)
