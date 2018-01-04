---
title: "선과 곡선의 앤티 앨리어싱"
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
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b8552f185a93b688555dbcfab3da9d28d9bfde6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="antialiasing-with-lines-and-curves"></a><span data-ttu-id="e8767-102">선과 곡선의 앤티 앨리어싱</span><span class="sxs-lookup"><span data-stu-id="e8767-102">Antialiasing with Lines and Curves</span></span>
<span data-ttu-id="e8767-103">사용 하는 경우 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 선을 그리려면, 시작 지점 및 끝 줄 지점을 제공 하지만 줄에서 개별 픽셀에 대 한 정보를 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-103">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, you provide the starting point and ending point of the line, but you do not have to provide any information about the individual pixels on the line.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="e8767-104">픽셀 특정 디스플레이 장치에 줄을 표시 하도록 설정 됩니다 확인 하려면 디스플레이 드라이버 소프트웨어와 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-104"> works in conjunction with the display driver software to determine which pixels will be turned on to show the line on a particular display device.</span></span>  
  
## <a name="aliasing"></a><span data-ttu-id="e8767-105">별칭 지정</span><span class="sxs-lookup"><span data-stu-id="e8767-105">Aliasing</span></span>  
 <span data-ttu-id="e8767-106">에 바로 빨간색 선이 지점 (4, 2)에서 점 (16, 10)로 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-106">Consider the straight red line that goes from the point (4, 2) to the point (16, 10).</span></span> <span data-ttu-id="e8767-107">좌표 시스템의 왼쪽 위 모퉁이에 원점 측정 단위를은 픽셀이 고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-107">Assume the coordinate system has its origin in the upper-left corner and that the unit of measure is the pixel.</span></span> <span data-ttu-id="e8767-108">또한 아래로 오른쪽와 y 축 지점에 x 축이 가리키는지 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-108">Also assume that the x-axis points to the right and the y-axis points down.</span></span> <span data-ttu-id="e8767-109">다음 그림에는 빨간색의 다양 한 색상 배경에 그려지는 선이 확대해 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-109">The following illustration shows an enlarged view of the red line drawn on a multicolored background.</span></span>  
  
 <span data-ttu-id="e8767-110">![선, 앤티 앨리어싱 없음](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span><span class="sxs-lookup"><span data-stu-id="e8767-110">![Line, no antialiasing](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span></span>  
  
 <span data-ttu-id="e8767-111">줄을 렌더링 하는 데 빨간색 픽셀은 불투명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-111">The red pixels used to render the line are opaque.</span></span> <span data-ttu-id="e8767-112">줄에는 부분적으로 투명 하 게 픽셀이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-112">There are no partially transparent pixels in the line.</span></span> <span data-ttu-id="e8767-113">이러한 유형의 줄 렌더링을 사용 하면 선이 가변된 모양 및 약간 계단 처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-113">This type of line rendering gives the line a jagged appearance, and the line looks somewhat like a staircase.</span></span> <span data-ttu-id="e8767-114">이 기술의 선을 계단식으로 표시할 앨리어싱이 라고 합니다. 계단 이론적인 줄에 대 한 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-114">This technique of representing a line with a staircase is called aliasing; the staircase is an alias for the theoretical line.</span></span>  
  
## <a name="antialiasing"></a><span data-ttu-id="e8767-115">앤티 앨리어싱</span><span class="sxs-lookup"><span data-stu-id="e8767-115">Antialiasing</span></span>  
 <span data-ttu-id="e8767-116">줄을 렌더링 하기 위한 보다 정교한 기법에서는 불투명 한 픽셀과 함께 반투명 픽셀로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-116">A more sophisticated technique for rendering a line involves using partially transparent pixels along with opaque pixels.</span></span> <span data-ttu-id="e8767-117">줄에는 정도 따라 빨간색과 배경색을 혼합 하 또는 픽셀 순수 빨간색으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-117">Pixels are set to pure red, or to some blend of red and the background color, depending on how close they are to the line.</span></span> <span data-ttu-id="e8767-118">이 유형의 렌더링 앤티 앨리어싱 라고 하며 결과 육안에 게 더 부드러운는 선이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-118">This type of rendering is called antialiasing and results in a line that the human eye perceives as more smooth.</span></span> <span data-ttu-id="e8767-119">다음 그림에서는 특정 픽셀 앤티 앨리어싱 선을 위해 배경색과 혼합 되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-119">The following illustration shows how certain pixels are blended with the background to produce an antialiased line.</span></span>  
  
 <span data-ttu-id="e8767-120">![선 앤티 앨리어싱](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span><span class="sxs-lookup"><span data-stu-id="e8767-120">![Antialiasing a Line](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span></span>  
  
 <span data-ttu-id="e8767-121">라고도 함, 다듬기 앤티 앨리어싱 곡선에 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-121">Antialiasing, also called smoothing, can also be applied to curves.</span></span> <span data-ttu-id="e8767-122">다음 그림에서는 확대해 평활된 타원을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-122">The following illustration shows an enlarged view of a smoothed ellipse.</span></span>  
  
 <span data-ttu-id="e8767-123">![곡선 앤티 앨리어싱](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span><span class="sxs-lookup"><span data-stu-id="e8767-123">![Antialiasing Curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span></span>  
  
 <span data-ttu-id="e8767-124">다음 그림에는 실제 크기에 한 번 앤티 앨리어싱 앤티 앨리어싱 없이 한 번에 같은 타원 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-124">The following illustration shows the same ellipse in its actual size, once without antialiasing and once with antialiasing.</span></span>  
  
 <span data-ttu-id="e8767-125">![앤티 앨리어싱 예](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span><span class="sxs-lookup"><span data-stu-id="e8767-125">![Antialiasing example](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span></span>  
  
 <span data-ttu-id="e8767-126">선과 곡선의 앤티 앨리어싱 사용 하는 그리려는 인스턴스를 만들고는 <xref:System.Drawing.Graphics> 클래스 및 설정의 <xref:System.Drawing.Graphics.SmoothingMode%2A> 속성을 <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> 또는 <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>합니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-126">To draw lines and curves that use antialiasing, create an instance of the <xref:System.Drawing.Graphics> class and set its <xref:System.Drawing.Graphics.SmoothingMode%2A> property to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> or <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span></span> <span data-ttu-id="e8767-127">다음 중 하나를 호출 하는의 그리기 메서드 같은 <xref:System.Drawing.Graphics> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e8767-127">Then call one of the drawing methods of that same <xref:System.Drawing.Graphics> class.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a><span data-ttu-id="e8767-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8767-128">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>  
 [<span data-ttu-id="e8767-129">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="e8767-129">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="e8767-130">방법: 텍스트에 앤티 앨리어싱 사용</span><span class="sxs-lookup"><span data-stu-id="e8767-130">How to: Use Antialiasing with Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)
