---
title: "GDI+의 개곡선 및 폐곡선"
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
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 14da32848978299a0d0651596bbfbfe17c2e0d53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="open-and-closed-curves-in-gdi"></a><span data-ttu-id="0b9ed-102">GDI+의 개곡선 및 폐곡선</span><span class="sxs-lookup"><span data-stu-id="0b9ed-102">Open and Closed Curves in GDI+</span></span>
<span data-ttu-id="0b9ed-103">다음 그림에서는 두 곡선으로 분할을 보여 줍니다: 개곡선 및 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-103">The following illustration shows two curves: one open and one closed.</span></span>  
  
 <span data-ttu-id="0b9ed-104">![개곡선 및 폐곡선](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span><span class="sxs-lookup"><span data-stu-id="0b9ed-104">![Open & Closed curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span></span>  
  
## <a name="managed-interface-for-curves"></a><span data-ttu-id="0b9ed-105">곡선에 대 한 관리 되는 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0b9ed-105">Managed Interface for Curves</span></span>  
 <span data-ttu-id="0b9ed-106">폐곡선 내부 있고 따라서 브러시를 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-106">Closed curves have an interior and therefore can be filled with a brush.</span></span> <span data-ttu-id="0b9ed-107"><xref:System.Drawing.Graphics> 클래스 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 폐쇄형된 도형 및 곡선을 채우기 위한 메서드를 제공: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, 및 <xref:System.Drawing.Graphics.FillRegion%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-107">The <xref:System.Drawing.Graphics> class in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] provides the following methods for filling closed shapes and curves: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, and <xref:System.Drawing.Graphics.FillRegion%2A>.</span></span> <span data-ttu-id="0b9ed-108">특정 브러시 형식 중 하나를 전달 해야 이러한 방법 중 하나를 호출할 때마다 (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, 또는 <xref:System.Drawing.Drawing2D.PathGradientBrush>)를 인수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-108">Whenever you call one of these methods, you must pass one of the specific brush types (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, or <xref:System.Drawing.Drawing2D.PathGradientBrush>) as an argument.</span></span>  
  
 <span data-ttu-id="0b9ed-109"><xref:System.Drawing.Graphics.FillPie%2A> 메서드는 참조 하는 <xref:System.Drawing.Graphics.DrawArc%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-109">The <xref:System.Drawing.Graphics.FillPie%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawArc%2A> method.</span></span> <span data-ttu-id="0b9ed-110">과 마찬가지로 <xref:System.Drawing.Graphics.DrawArc%2A> 메서드 개요는 타원의 부분을 그리는 <xref:System.Drawing.Graphics.FillPie%2A> 메서드는 타원의 내부를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-110">Just as the <xref:System.Drawing.Graphics.DrawArc%2A> method draws a portion of the outline of an ellipse, the <xref:System.Drawing.Graphics.FillPie%2A> method fills a portion of the interior of an ellipse.</span></span> <span data-ttu-id="0b9ed-111">다음 예제는 호를 그립니다 하 고 해당 부분의 타원의 내부를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-111">The following example draws an arc and fills the corresponding portion of the interior of the ellipse:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 <span data-ttu-id="0b9ed-112">다음 그림은 원호 및 채워진된 원형 차트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-112">The following illustration shows the arc and the filled pie.</span></span>  
  
 <span data-ttu-id="0b9ed-113">![개곡선 및 폐곡선](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span><span class="sxs-lookup"><span data-stu-id="0b9ed-113">![Open & Closed curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span></span>  
  
 <span data-ttu-id="0b9ed-114"><xref:System.Drawing.Graphics.FillClosedCurve%2A> 메서드는 참조 하는 <xref:System.Drawing.Graphics.DrawClosedCurve%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-114">The <xref:System.Drawing.Graphics.FillClosedCurve%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method.</span></span> <span data-ttu-id="0b9ed-115">두 방법 모두 끝점의 시작 지점에 연결 하 여 곡선을 자동으로 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-115">Both methods automatically close the curve by connecting the ending point to the starting point.</span></span> <span data-ttu-id="0b9ed-116">다음 예제에서는 통해 전달 되는 곡선을 그리는 데 (0, 0) (60, 20) 및 (40, 50).</span><span class="sxs-lookup"><span data-stu-id="0b9ed-116">The following example draws a curve that passes through (0, 0), (60, 20), and (40, 50).</span></span> <span data-ttu-id="0b9ed-117">다음, 곡선을 자동으로 연결 하 여 닫습니다 (40, 50) (0, 0) 하 여 시작 지점으로 및 내부 단색으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-117">Then, the curve is automatically closed by connecting (40, 50) to the starting point (0, 0), and the interior is filled with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <span data-ttu-id="0b9ed-118"><xref:System.Drawing.Graphics.FillPath%2A> 메서드는 경로는 별도 관련 파일의 내부를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-118">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the interiors of the separate pieces of a path.</span></span> <span data-ttu-id="0b9ed-119">경로 조각의 폐곡선 또는 셰이프를 형성 하지 않으면 경우는 <xref:System.Drawing.Graphics.FillPath%2A> 메서드 채우기 전에 경로의 해당 부분을 자동으로 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-119">If a piece of a path doesn't form a closed curve or shape, the <xref:System.Drawing.Graphics.FillPath%2A> method automatically closes that piece of the path before filling it.</span></span> <span data-ttu-id="0b9ed-120">다음 예제에서는 그리고 호, 카디널 스플라인을, string, 및 원형 구성 되는 경로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-120">The following example draws and fills a path that consists of an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 <span data-ttu-id="0b9ed-121">다음은 단색 채우기 없는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-121">The following illustration shows the path with and without the solid fill.</span></span> <span data-ttu-id="0b9ed-122">문자열의 텍스트를 되지만 채워지지, 여는 <xref:System.Drawing.Graphics.DrawPath%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-122">Note that the text in the string is outlined, but not filled, by the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="0b9ed-123"><xref:System.Drawing.Graphics.FillPath%2A> 내부 문자열에서 문자를 색칠 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="0b9ed-123">It is the <xref:System.Drawing.Graphics.FillPath%2A> method that paints the interiors of the characters in the string.</span></span>  
  
 <span data-ttu-id="0b9ed-124">![경로에 대 한 문자열](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span><span class="sxs-lookup"><span data-stu-id="0b9ed-124">![String in a path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b9ed-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b9ed-125">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Point?displayProperty=nameWithType>  
 [<span data-ttu-id="0b9ed-126">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="0b9ed-126">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="0b9ed-127">방법: 그리는 데 필요한 그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="0b9ed-127">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [<span data-ttu-id="0b9ed-128">경로 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="0b9ed-128">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
