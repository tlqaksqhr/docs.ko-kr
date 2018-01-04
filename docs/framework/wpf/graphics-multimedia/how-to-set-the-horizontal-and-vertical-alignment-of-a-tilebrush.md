---
title: "방법: TileBrush의 가로 및 세로 맞춤 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], alignment of
- vertical alignment of TileBrushes [WPF]
- aligning [WPF], TileBrushes
- horizontal alignment of Tilebrushes [WPF]
ms.assetid: 65ae89bd-9246-4c9e-bde4-2fb991d4060d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3dcbf4715c80f72178295c0b6abdc1272a055a8a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-horizontal-and-vertical-alignment-of-a-tilebrush"></a><span data-ttu-id="ba13f-102">방법: TileBrush의 가로 및 세로 맞춤 설정</span><span class="sxs-lookup"><span data-stu-id="ba13f-102">How to: Set the Horizontal and Vertical Alignment of a TileBrush</span></span>
<span data-ttu-id="ba13f-103">이 예제에서는 타일에서 콘텐츠의 가로 및 세로 맞춤을 제어하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-103">This example shows how to control the horizontal and vertical alignment of content in a tile.</span></span> <span data-ttu-id="ba13f-104">가로 및 세로 맞춤을 제어 하는 <xref:System.Windows.Media.TileBrush>를 사용 하 여 해당 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 및 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-104">To control the horizontal and vertical alignment of a <xref:System.Windows.Media.TileBrush>, use its <xref:System.Windows.Media.TileBrush.AlignmentX%2A> and <xref:System.Windows.Media.TileBrush.AlignmentY%2A> properties.</span></span>  
  
 <span data-ttu-id="ba13f-105"><xref:System.Windows.Media.TileBrush.AlignmentX%2A> 및 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 의 속성은 <xref:System.Windows.Media.TileBrush> 사용 되는 다음 조건 중 하나가 true 이면 경우:</span><span class="sxs-lookup"><span data-stu-id="ba13f-105">The <xref:System.Windows.Media.TileBrush.AlignmentX%2A> and <xref:System.Windows.Media.TileBrush.AlignmentY%2A> properties of a <xref:System.Windows.Media.TileBrush> are used when either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="ba13f-106"><xref:System.Windows.Media.TileBrush.Stretch%2A> 속성은 <xref:System.Windows.Media.Stretch.Uniform> 또는 <xref:System.Windows.Media.Stretch.UniformToFill> 및 <xref:System.Windows.Media.TileBrush.Viewbox%2A> 및 <xref:System.Windows.Media.TileBrush.Viewport%2A> 다른 가로 세로 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-106">The <xref:System.Windows.Media.TileBrush.Stretch%2A> property is <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill> and the <xref:System.Windows.Media.TileBrush.Viewbox%2A> and <xref:System.Windows.Media.TileBrush.Viewport%2A> have different aspect ratios.</span></span>  
  
-   <span data-ttu-id="ba13f-107"><xref:System.Windows.Media.TileBrush.Stretch%2A> 속성은 <xref:System.Windows.Media.Stretch.None> 및 <xref:System.Windows.Media.TileBrush.Viewbox%2A> 및 <xref:System.Windows.Media.TileBrush.Viewport%2A> 크기가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-107">The <xref:System.Windows.Media.TileBrush.Stretch%2A> property is <xref:System.Windows.Media.Stretch.None> and the <xref:System.Windows.Media.TileBrush.Viewbox%2A> and <xref:System.Windows.Media.TileBrush.Viewport%2A> are different sizes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba13f-108">예</span><span class="sxs-lookup"><span data-stu-id="ba13f-108">Example</span></span>  
 <span data-ttu-id="ba13f-109">콘텐츠를 정렬 하는 다음 예제는 <xref:System.Windows.Media.DrawingBrush>의 형식인 <xref:System.Windows.Media.TileBrush>, 타일의 왼쪽 위 모퉁이에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-109">The following example aligns the content of a <xref:System.Windows.Media.DrawingBrush>, which is a type of <xref:System.Windows.Media.TileBrush>, to the upper-left corner of its tile.</span></span> <span data-ttu-id="ba13f-110">예제에서는 콘텐츠를 정렬 하는 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 의 속성은 <xref:System.Windows.Media.DrawingBrush> 를 <xref:System.Windows.Media.AlignmentX.Left> 및 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 속성을 <xref:System.Windows.Media.AlignmentY.Top>합니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-110">To align the content, the example sets the <xref:System.Windows.Media.TileBrush.AlignmentX%2A> property of the <xref:System.Windows.Media.DrawingBrush> to <xref:System.Windows.Media.AlignmentX.Left> and the <xref:System.Windows.Media.TileBrush.AlignmentY%2A> property to <xref:System.Windows.Media.AlignmentY.Top>.</span></span> <span data-ttu-id="ba13f-111">이 예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-111">This example produces the following output.</span></span>  
  
 <span data-ttu-id="ba13f-112">![Top&#45;TileBrush; 왼쪽된 맞춤](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletopleft.png "graphicsmm_TileBrushAlignmentExampleTopLeft")</span><span class="sxs-lookup"><span data-stu-id="ba13f-112">![A TileBrush with top&#45;left alignment](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletopleft.png "graphicsmm_TileBrushAlignmentExampleTopLeft")</span></span>  
<span data-ttu-id="ba13f-113">콘텐츠가 왼쪽 위 구석에 정렬된 TileBrush</span><span class="sxs-lookup"><span data-stu-id="ba13f-113">TileBrush with content aligned to the upper-left corner</span></span>  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmentinline)]  
  
## <a name="example"></a><span data-ttu-id="ba13f-114">예</span><span class="sxs-lookup"><span data-stu-id="ba13f-114">Example</span></span>  
 <span data-ttu-id="ba13f-115">콘텐츠를 정렬 하는 다음 예제는 <xref:System.Windows.Media.DrawingBrush> 설정 하 여 타일의 오른쪽 아래 모서리에는 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 속성을 <xref:System.Windows.Media.AlignmentX.Right> 및 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 속성을 <xref:System.Windows.Media.AlignmentY.Bottom>합니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-115">The next example aligns the content of a <xref:System.Windows.Media.DrawingBrush> to the lower-right corner of its tile by setting the <xref:System.Windows.Media.TileBrush.AlignmentX%2A> property to <xref:System.Windows.Media.AlignmentX.Right> and the <xref:System.Windows.Media.TileBrush.AlignmentY%2A> property to <xref:System.Windows.Media.AlignmentY.Bottom>.</span></span> <span data-ttu-id="ba13f-116">예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-116">The example produces the following output.</span></span>  
  
 <span data-ttu-id="ba13f-117">![아래쪽 &#45;TileBrush; 오른쪽 맞춤](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomright.png "graphicsmm_TileBrushAlignmentExampleBottomRight")</span><span class="sxs-lookup"><span data-stu-id="ba13f-117">![A TileBrush with bottom&#45;right alignment](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomright.png "graphicsmm_TileBrushAlignmentExampleBottomRight")</span></span>  
<span data-ttu-id="ba13f-118">콘텐츠가 오른쪽 아래 구석에 정렬된 TileBrush</span><span class="sxs-lookup"><span data-stu-id="ba13f-118">TileBrush with content aligned to the lower-right corner</span></span>  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
## <a name="example"></a><span data-ttu-id="ba13f-119">예</span><span class="sxs-lookup"><span data-stu-id="ba13f-119">Example</span></span>  
 <span data-ttu-id="ba13f-120">콘텐츠를 정렬 하는 다음 예제는 <xref:System.Windows.Media.DrawingBrush> 설정 하 여 타일의 왼쪽 위 모퉁이에 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 속성을 <xref:System.Windows.Media.AlignmentX.Left> 및 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 속성을 <xref:System.Windows.Media.AlignmentY.Top>합니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-120">The next example aligns the content of a <xref:System.Windows.Media.DrawingBrush> to the upper-left corner of its tile by setting the <xref:System.Windows.Media.TileBrush.AlignmentX%2A> property to <xref:System.Windows.Media.AlignmentX.Left> and the <xref:System.Windows.Media.TileBrush.AlignmentY%2A> property to <xref:System.Windows.Media.AlignmentY.Top>.</span></span> <span data-ttu-id="ba13f-121">또한 설정는 <xref:System.Windows.Media.TileBrush.Viewport%2A> 및 <xref:System.Windows.Media.TileBrush.TileMode%2A> 의 <xref:System.Windows.Media.DrawingBrush> 타일 패턴을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-121">It also sets the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> of the <xref:System.Windows.Media.DrawingBrush> to produce a tile pattern.</span></span> <span data-ttu-id="ba13f-122">예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-122">The example produces the following output.</span></span>  
  
 <span data-ttu-id="ba13f-123">![Top&#45;인 바둑판된 모양의 TileBrush; 왼쪽된 맞춤](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletoplefttiled.png "graphicsmm_TileBrushAlignmentExampleTopLeftTiled")</span><span class="sxs-lookup"><span data-stu-id="ba13f-123">![A tiled TileBrush with top&#45;left alignment](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletoplefttiled.png "graphicsmm_TileBrushAlignmentExampleTopLeftTiled")</span></span>  
<span data-ttu-id="ba13f-124">콘텐츠가 기본 타일에서 왼쪽 위에 정렬된 타일 패턴</span><span class="sxs-lookup"><span data-stu-id="ba13f-124">Tile pattern with content aligned to upper-left in base tile</span></span>  
  
 <span data-ttu-id="ba13f-125">이 그림에서는 기본 타일을 강조해서 보여 주므로 해당 콘텐츠가 정렬되는 방식을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-125">The illustration highlights abase tile so that you can see how its content is aligned.</span></span> <span data-ttu-id="ba13f-126">다음에 유의 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 때문에 설정의 영향 없음의 콘텐츠는 <xref:System.Windows.Media.DrawingBrush> 가로로 기본 타일을 완전히 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-126">Notice that the <xref:System.Windows.Media.TileBrush.AlignmentX%2A> setting has no effect because the content of the <xref:System.Windows.Media.DrawingBrush> completely fills the base tile horizontally.</span></span>  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmenttiledinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmenttiledinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmenttiledinline)]  
  
## <a name="example"></a><span data-ttu-id="ba13f-127">예</span><span class="sxs-lookup"><span data-stu-id="ba13f-127">Example</span></span>  
 <span data-ttu-id="ba13f-128">콘텐츠를 정렬 하는 마지막 예제 <xref:System.Windows.Media.DrawingBrush> 설정 하 여 기본 타일의 오른쪽 아래에는 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 속성을 <xref:System.Windows.Media.AlignmentX.Right> 및 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 속성을 <xref:System.Windows.Media.AlignmentY.Bottom>합니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-128">The final example aligns the content of a tiled <xref:System.Windows.Media.DrawingBrush> to the lower-right of its base tile by setting the <xref:System.Windows.Media.TileBrush.AlignmentX%2A> property to <xref:System.Windows.Media.AlignmentX.Right> and the <xref:System.Windows.Media.TileBrush.AlignmentY%2A> property to <xref:System.Windows.Media.AlignmentY.Bottom>.</span></span> <span data-ttu-id="ba13f-129">예제의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-129">The example produces the following output.</span></span>  
  
 <span data-ttu-id="ba13f-130">![A 아래쪽 &#45;TileBrush 바둑판식; 맞춤을 마우스 오른쪽 단추로](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomrighttiled.png "graphicsmm_TileBrushAlignmentExampleBottomRightTiled")</span><span class="sxs-lookup"><span data-stu-id="ba13f-130">![A tiled TileBrush with bottom&#45;right alignment](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomrighttiled.png "graphicsmm_TileBrushAlignmentExampleBottomRightTiled")</span></span>  
<span data-ttu-id="ba13f-131">콘텐츠가 기본 타일에서 오른쪽 아래에 정렬된 타일 패턴</span><span class="sxs-lookup"><span data-stu-id="ba13f-131">Tile pattern with content aligned to lower-right in base tile</span></span>  
  
 <span data-ttu-id="ba13f-132">다시는 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 때문에 설정의 영향 없음의 콘텐츠는 <xref:System.Windows.Media.DrawingBrush> 가로로 기본 타일을 완전히 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-132">Again, the <xref:System.Windows.Media.TileBrush.AlignmentX%2A> setting has no effect because the content of the <xref:System.Windows.Media.DrawingBrush> completely fills the base tile horizontally.</span></span>  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
 <span data-ttu-id="ba13f-133">예제에서는 사용 <xref:System.Windows.Media.DrawingBrush> 보여 주기 위해 개체 방법을 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 및 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 속성이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-133">The examples use <xref:System.Windows.Media.DrawingBrush> objects to demonstrate how the <xref:System.Windows.Media.TileBrush.AlignmentX%2A> and <xref:System.Windows.Media.TileBrush.AlignmentY%2A> properties are used.</span></span> <span data-ttu-id="ba13f-134">이러한 속성에 대 한 모든 타일 브러시 동일 하 게 작동: <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.ImageBrush>, 및 <xref:System.Windows.Media.VisualBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="ba13f-134">These properties behave identically for all the tile brushes: <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.ImageBrush>, and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="ba13f-135">타일 브러시에 대한 자세한 내용은 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba13f-135">For more information about tile brushes, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba13f-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba13f-136">See Also</span></span>  
 <xref:System.Windows.Media.DrawingBrush>  
 <xref:System.Windows.Media.ImageBrush>  
 <xref:System.Windows.Media.VisualBrush>  
 [<span data-ttu-id="ba13f-137">이미지, 그림 및 시각적 표시로 그리기</span><span class="sxs-lookup"><span data-stu-id="ba13f-137">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
