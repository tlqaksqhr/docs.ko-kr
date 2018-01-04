---
title: "방법: 선형 그라데이션 만들기"
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
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 33979decf37e9adb29d94a6602a43f992d93aaa1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="4c075-102">방법: 선형 그라데이션 만들기</span><span class="sxs-lookup"><span data-stu-id="4c075-102">How to: Create a Linear Gradient</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="4c075-103">가로, 세로, 및 대각선 선형 그라데이션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-103"> provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="4c075-104">기본적으로 선형 그라데이션 색 균일 하 게 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="4c075-105">그러나 균일 하지 않은 방식으로 색이 변경 되도록 선형 그라데이션을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  
  
 <span data-ttu-id="4c075-106">다음 예제에서는 줄, 타원 및 사각형 가로 선형 그라데이션 브러시로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-106">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
 <span data-ttu-id="4c075-107"><xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> 네 개의 인수를 받는 생성자: 두 점과 두 가지 색입니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-107">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="4c075-108">첫 번째 지점 (0, 10) 첫 번째 색 (빨강)으로 연결 되며 두 번째 색 (파랑)와 연결 된 두 번째 점 (200, 10).</span><span class="sxs-lookup"><span data-stu-id="4c075-108">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="4c075-109">와 마찬가지로, 그린 선 (0, 10)에 (200, 10) 빨강에서 파랑 점진적으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-109">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="4c075-110">점 (50, 10) 및 (200, 10)에서 10 개 기준 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-110">The 10s in the points (50, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="4c075-111">중요 한 것은 두 지점 동일한 두 번째 좌표 있는지-으로 연결 되도록에 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-111">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="4c075-112">타원 및 사각형에서에서 변경할 수도 점진적으로 빨강을 200으로 0에서 가로 좌표 면 파란색입니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-112">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="4c075-113">다음은 줄, 타원 및 사각형입니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-113">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="4c075-114">색 그라데이션이 반복 됨 자체 200 이외의 증가 하면 가로 좌표 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-114">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 <span data-ttu-id="4c075-115">![선형 그라데이션](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")</span><span class="sxs-lookup"><span data-stu-id="4c075-115">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")</span></span>  
  
### <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="4c075-116">가로 선형 그라데이션을 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="4c075-116">To use horizontal linear gradients</span></span>  
  
-   <span data-ttu-id="4c075-117">불투명 빨강 및 불투명 파란색에서 세 번째와 네 번째 인수로 각각 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-117">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="4c075-118">앞의 예제에서 200에서 가로 좌표 0 가로 좌표에서 이동 색상 구성 선형으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-118">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="4c075-119">예를 들어 첫 번째 좌표가 0과 200 사이의 중간 지점 0에서 255 사이의 중간에 있는 파란색 구성 요소를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-119">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="4c075-120">다른 색이 변하는 그라데이션의 한쪽 가장자리에서 방식을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-120"> allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="4c075-121">검정에서 다음 표에 따라 빨강으로 변경 하는 그라데이션 브러시를 만들려고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-121">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="4c075-122">가로 좌표</span><span class="sxs-lookup"><span data-stu-id="4c075-122">Horizontal coordinate</span></span>|<span data-ttu-id="4c075-123">RGB 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4c075-123">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="4c075-124">0</span><span class="sxs-lookup"><span data-stu-id="4c075-124">0</span></span>|<span data-ttu-id="4c075-125">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="4c075-125">(0, 0, 0)</span></span>|  
|<span data-ttu-id="4c075-126">40</span><span class="sxs-lookup"><span data-stu-id="4c075-126">40</span></span>|<span data-ttu-id="4c075-127">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="4c075-127">(128, 0, 0)</span></span>|  
|<span data-ttu-id="4c075-128">200</span><span class="sxs-lookup"><span data-stu-id="4c075-128">200</span></span>|<span data-ttu-id="4c075-129">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="4c075-129">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="4c075-130">가로 좌표는 0에서 200 하는 방법의 20%만 때 빨강 구성 농도가 절반은 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-130">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="4c075-131">다음 예에서는 <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> 속성은 <xref:System.Drawing.Drawing2D.LinearGradientBrush> 세 가지 상대 농도 세 가지 상대 위치를 연결할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-131">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> property of a <xref:System.Drawing.Drawing2D.LinearGradientBrush> object to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="4c075-132">앞의 표에서 같이 0.5 상대 강도 0.2의 상대 위치와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-132">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="4c075-133">코드는 타원 및 사각형 그라데이션 브러시를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-133">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="4c075-134">다음은 결과 타원 및 사각형입니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-134">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 <span data-ttu-id="4c075-135">![선형 그라데이션](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")</span><span class="sxs-lookup"><span data-stu-id="4c075-135">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")</span></span>  
  
### <a name="to-customize-linear-gradients"></a><span data-ttu-id="4c075-136">선형 그라데이션 사용자 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="4c075-136">To customize linear gradients</span></span>  
  
-   <span data-ttu-id="4c075-137">불투명 한 검정색 및 불투명 빨간색 세 번째와 네 번째 인수로 각각 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-137">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="4c075-138">이전 예제에서 그라데이션 가로; 되었습니다. 즉, 색 가로 줄 이동 하면 점진적으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-138">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="4c075-139">세로 그라데이션 및 대각선 그라데이션을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-139">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="4c075-140">에 점 (0, 0) 및 (200, 100)를 전달 하는 다음 예제는 <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-140">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="4c075-141">파란색 연관 (0, 0)와 연결 되는 녹색 (200, 100).</span><span class="sxs-lookup"><span data-stu-id="4c075-141">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="4c075-142">선형 그라데이션 브러시로 (펜 굵기 10)이 있는 선 및 타원 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-142">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="4c075-143">다음 그림에는 줄과 타원 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-143">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="4c075-144">참고는 타원 변경 내용에서 색 점진적으로 하나를 따라 이동 하면 줄 하는 통과 한 줄에 병렬 (0, 0) 및 (200, 100).</span><span class="sxs-lookup"><span data-stu-id="4c075-144">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 <span data-ttu-id="4c075-145">![선형 그라데이션](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")</span><span class="sxs-lookup"><span data-stu-id="4c075-145">![Linear Gradient](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")</span></span>  
  
### <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="4c075-146">대각선 선형 그라데이션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4c075-146">To create diagonal linear gradients</span></span>  
  
-   <span data-ttu-id="4c075-147">불투명 파란색 아이콘과 불투명 녹색 세 번째와 네 번째 인수로 각각 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c075-147">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="4c075-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c075-148">See Also</span></span>  
 [<span data-ttu-id="4c075-149">그라데이션 브러시를 사용하여 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="4c075-149">Using a Gradient Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)  
 [<span data-ttu-id="4c075-150">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="4c075-150">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
