---
title: "GDI+의 브러시 및 채워진 도형"
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
- brushes [Windows Forms], GDI+
- filled shapes [Windows Forms], GDI+
- shapes [Windows Forms], GDI+
- GDI+, brushes
- GDI+, filled shapes
- gradient brushes
- brushes [Windows Forms], gradient
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89f0a7c86a83222030d9b50e20228f32e85ce730
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="brushes-and-filled-shapes-in-gdi"></a><span data-ttu-id="97116-102">GDI+의 브러시 및 채워진 도형</span><span class="sxs-lookup"><span data-stu-id="97116-102">Brushes and Filled Shapes in GDI+</span></span>
<span data-ttu-id="97116-103">사각형, 타원, 등의 닫힌된 셰이프 개요와 내부 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97116-103">A closed shape, such as a rectangle or an ellipse, consists of an outline and an interior.</span></span> <span data-ttu-id="97116-104">윤곽선 펜으로 그려지고 브러시로 내부 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="97116-104">The outline is drawn with a pen and the interior is filled with a brush.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="97116-105">닫힌 도형의 내부를 채우는 브러시는 여러 클래스 제공: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, 및 <xref:System.Drawing.Drawing2D.PathGradientBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="97116-105"> provides several brush classes for filling the interiors of closed shapes: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, and <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span></span> <span data-ttu-id="97116-106">이 클래스는 모두에서 상속 된 <xref:System.Drawing.Brush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="97116-106">All of these classes inherit from the <xref:System.Drawing.Brush> class.</span></span> <span data-ttu-id="97116-107">다음 그림에서는 단색 브러시 채워진 사각형 및 타원 빗살 무늬 브러시 채워진 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97116-107">The following illustration shows a rectangle filled with a solid brush and an ellipse filled with a hatch brush.</span></span>  
  
 <span data-ttu-id="97116-108">![채워진 모양](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span><span class="sxs-lookup"><span data-stu-id="97116-108">![Filled Shapes](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span></span>  
  
## <a name="solid-brushes"></a><span data-ttu-id="97116-109">단색 브러시</span><span class="sxs-lookup"><span data-stu-id="97116-109">Solid Brushes</span></span>  
 <span data-ttu-id="97116-110">닫힌된 셰이프를 채울 하려면의 인스턴스는 <xref:System.Drawing.Graphics> 클래스 및 <xref:System.Drawing.Brush>합니다.</span><span class="sxs-lookup"><span data-stu-id="97116-110">To fill a closed shape, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Brush>.</span></span> <span data-ttu-id="97116-111">인스턴스는 <xref:System.Drawing.Graphics> 클래스와 같은 메서드를 제공 <xref:System.Drawing.Graphics.FillRectangle%2A> 및 <xref:System.Drawing.Graphics.FillEllipse%2A>, 및 <xref:System.Drawing.Brush> 채우기, 색 및 패턴 등의 특성을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="97116-111">The instance of the <xref:System.Drawing.Graphics> class provides methods, such as <xref:System.Drawing.Graphics.FillRectangle%2A> and <xref:System.Drawing.Graphics.FillEllipse%2A>, and the <xref:System.Drawing.Brush> stores attributes of the fill, such as color and pattern.</span></span> <span data-ttu-id="97116-112"><xref:System.Drawing.Brush> fill 메서드를 인수 중 하나로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97116-112">The <xref:System.Drawing.Brush> is passed as one of the arguments to the fill method.</span></span> <span data-ttu-id="97116-113">다음 코드 예제에서는 빨간색 단색으로 타원을 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97116-113">The following code example shows how to fill an ellipse with a solid red color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#121](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  <span data-ttu-id="97116-114">브러시는 앞의 예제에서 형식의 <xref:System.Drawing.SolidBrush>에서 상속한 <xref:System.Drawing.Brush>합니다.</span><span class="sxs-lookup"><span data-stu-id="97116-114">In the preceding example, the brush is of type <xref:System.Drawing.SolidBrush>, which inherits from <xref:System.Drawing.Brush>.</span></span>  
  
## <a name="hatch-brushes"></a><span data-ttu-id="97116-115">빗살 무늬 브러시</span><span class="sxs-lookup"><span data-stu-id="97116-115">Hatch Brushes</span></span>  
 <span data-ttu-id="97116-116">빗살 무늬 브러시 도형을 채우는 전경색, 배경색 및 해치 스타일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97116-116">When you fill a shape with a hatch brush, you specify a foreground color, a background color, and a hatch style.</span></span> <span data-ttu-id="97116-117">전경색은 해칭의 색입니다.</span><span class="sxs-lookup"><span data-stu-id="97116-117">The foreground color is the color of the hatching.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#122](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="97116-118">50 개 이상의 해치 스타일; 제공 다음 그림에 표시 된 세 가지 스타일은 <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, 및 <xref:System.Drawing.Drawing2D.HatchStyle.Cross>합니다.</span><span class="sxs-lookup"><span data-stu-id="97116-118"> provides more than 50 hatch styles; the three styles shown in the following illustration are <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, and <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span></span>  
  
 <span data-ttu-id="97116-119">![채워진 모양](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span><span class="sxs-lookup"><span data-stu-id="97116-119">![Filled Shapes](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span></span>  
  
## <a name="texture-brushes"></a><span data-ttu-id="97116-120">질감 브러시</span><span class="sxs-lookup"><span data-stu-id="97116-120">Texture Brushes</span></span>  
 <span data-ttu-id="97116-121">질감 브러시와 패턴 비트맵에 저장 된 셰이프를 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97116-121">With a texture brush, you can fill a shape with a pattern stored in a bitmap.</span></span> <span data-ttu-id="97116-122">예를 들어, 다음 그림은 라는 디스크 파일에 저장 `MyTexture.bmp`합니다.</span><span class="sxs-lookup"><span data-stu-id="97116-122">For example, suppose the following picture is stored in a disk file named `MyTexture.bmp`.</span></span>  
  
 <span data-ttu-id="97116-123">![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span><span class="sxs-lookup"><span data-stu-id="97116-123">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span></span>  
  
 <span data-ttu-id="97116-124">다음 코드 예제에 저장 된 그림을 반복 하 여 타원을 채우는 방법을 보여 줍니다. `MyTexture.bmp`합니다.</span><span class="sxs-lookup"><span data-stu-id="97116-124">The following code example shows how to fill an ellipse by repeating the picture stored in `MyTexture.bmp`.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#123](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 <span data-ttu-id="97116-125">다음 그림에서는 채워진된 타원을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97116-125">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="97116-126">![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span><span class="sxs-lookup"><span data-stu-id="97116-126">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span></span>  
  
## <a name="gradient-brushes"></a><span data-ttu-id="97116-127">그라데이션 브러시</span><span class="sxs-lookup"><span data-stu-id="97116-127">Gradient Brushes</span></span>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="97116-128">두 종류의 그라데이션 브러시를 제공 합니다: 선형 및 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="97116-128"> provides two kinds of gradient brushes: linear and path.</span></span> <span data-ttu-id="97116-129">선형 그라데이션 브러시에 따라 점차 도형에서 가로, 세로 또는 대각선 방향으로 변경 하는 색으로 도형 채우기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97116-129">You can use a linear gradient brush to fill a shape with color that changes gradually as you move across the shape horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="97116-130">다음 코드 예제는 타원의 왼쪽된 가장자리에서 맨 오른쪽으로 이동 하면 파랑에서 녹색으로 변경 하는 가로 그라데이션 브러시로 타원을 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97116-130">The following code example shows how to fill an ellipse with a horizontal gradient brush that changes from blue to green as you move from the left edge of the ellipse to the right edge.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#124](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 <span data-ttu-id="97116-131">다음 그림에서는 채워진된 타원을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97116-131">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="97116-132">![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span><span class="sxs-lookup"><span data-stu-id="97116-132">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span></span>  
  
 <span data-ttu-id="97116-133">가장자리를 향해 셰이프의 가운데 간에 이동할 때 색을 변경 하려면 경로 그라데이션 브러시를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97116-133">A path gradient brush can be configured to change color as you move from the center of a shape toward the edge.</span></span>  
  
 <span data-ttu-id="97116-134">![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span><span class="sxs-lookup"><span data-stu-id="97116-134">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span></span>  
  
 <span data-ttu-id="97116-135">경로 그라데이션 브러시는 매우 유연 합니다.</span><span class="sxs-lookup"><span data-stu-id="97116-135">Path gradient brushes are quite flexible.</span></span> <span data-ttu-id="97116-136">다음 그림에서에서 변경 내용 점진적으로 가운데에 빨간색 각 꼭 짓 서로 다른 세 색에에서 있는 삼각형을 채우는 데 사용 되는 그라데이션 브러시입니다.</span><span class="sxs-lookup"><span data-stu-id="97116-136">The gradient brush used to fill the triangle in the following illustration changes gradually from red at the center to each of three different colors at the vertices.</span></span>  
  
 <span data-ttu-id="97116-137">![채워진 도형](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span><span class="sxs-lookup"><span data-stu-id="97116-137">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97116-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97116-138">See Also</span></span>  
 <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 [<span data-ttu-id="97116-139">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="97116-139">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="97116-140">방법: Windows Form에 채워진 사각형 그리기</span><span class="sxs-lookup"><span data-stu-id="97116-140">How to: Draw a Filled Rectangle on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-rectangle-on-a-windows-form.md)  
 [<span data-ttu-id="97116-141">방법: Windows Form에 채워진 타원 그리기</span><span class="sxs-lookup"><span data-stu-id="97116-141">How to: Draw a Filled Ellipse on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-ellipse-on-a-windows-form.md)
