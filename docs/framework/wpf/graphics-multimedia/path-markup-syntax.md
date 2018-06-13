---
title: 경로 태그 구문
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: 86901f357c43dc7c0c1402bf313e674603eaccbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566771"
---
# <a name="path-markup-syntax"></a><span data-ttu-id="d490d-102">경로 태그 구문</span><span class="sxs-lookup"><span data-stu-id="d490d-102">Path Markup Syntax</span></span>
<span data-ttu-id="d490d-103">그러나 경로에 대해서는 [Shape 및 기본 그리기 개요 WPF에서에서](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md) 및 [기 하 도형 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md),이 항목에 자세히 설명 경로 지정 하는 데 강력 하 고 복잡 한 최소 언어 더 조밀 하 게 사용 하 여 기 하 도형 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-103">Paths are discussed in [Shapes and Basic Drawing in WPF Overview](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md) and the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md), however, this topic describes in detail the powerful and complex mini-language you can use to specify path geometries more compactly using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a><span data-ttu-id="d490d-104">전제 조건</span><span class="sxs-lookup"><span data-stu-id="d490d-104">Prerequisites</span></span>  
 <span data-ttu-id="d490d-105">이 항목을 이해 하려면의 기본 기능에 잘 알고 있어야 <xref:System.Windows.Media.Geometry> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-105">To understand this topic, you should be familiar with the basic features of <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="d490d-106">자세한 내용은 참조는 [기 하 도형 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-106">For more information, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
<a name="abouthisdocument"></a>   
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a><span data-ttu-id="d490d-107">StreamGeometry 및 PathFigureCollection 미니 언어</span><span class="sxs-lookup"><span data-stu-id="d490d-107">StreamGeometry and PathFigureCollection Mini-Languages</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="d490d-108"> 기하학적 경로 설명 하기 위해 미니 언어를 제공 하는 두 개의 클래스를 제공: <xref:System.Windows.Media.StreamGeometry> 및 <xref:System.Windows.Media.PathFigureCollection>합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-108"> provides two classes that provide mini-languages for describing geometric paths: <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.PathFigureCollection>.</span></span>  
  
-   <span data-ttu-id="d490d-109">사용 하면는 <xref:System.Windows.Media.StreamGeometry> 형식의 속성을 설정할 때 최소 언어 <xref:System.Windows.Media.Geometry>와 같은 <xref:System.Windows.UIElement.Clip%2A> 속성은 <xref:System.Windows.UIElement> 또는 <xref:System.Windows.Shapes.Path.Data%2A> 속성의는 <xref:System.Windows.Shapes.Path> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-109">You use the <xref:System.Windows.Media.StreamGeometry> mini-language when setting a property of type <xref:System.Windows.Media.Geometry>, such as the <xref:System.Windows.UIElement.Clip%2A> property of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Shapes.Path.Data%2A> property of a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="d490d-110">다음 예제에서는 특성 구문을 사용 하 여 한 <xref:System.Windows.Media.StreamGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-110">The following example uses attribute syntax to create a <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
-   <span data-ttu-id="d490d-111">사용 하면는 <xref:System.Windows.Media.PathFigureCollection> 설정 하는 경우 최소 언어는 <xref:System.Windows.Media.PathGeometry.Figures%2A> 속성은 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-111">You use the <xref:System.Windows.Media.PathFigureCollection> mini-language when setting the <xref:System.Windows.Media.PathGeometry.Figures%2A> property of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="d490d-112">다음 예제는 특성 구문을 사용 하 여 한 <xref:System.Windows.Media.PathFigureCollection> 에 대 한는 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-112">The following example uses a attribute syntax to create a <xref:System.Windows.Media.PathFigureCollection> for a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 <span data-ttu-id="d490d-113">앞의 예제에서 볼 수 있는 것처럼 두 개의 미니 언어는 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-113">As you can see from the preceding examples, the two mini-languages are very similar.</span></span> <span data-ttu-id="d490d-114">사용할 수는 항상는 <xref:System.Windows.Media.PathGeometry> 사용할 수 있는 경우에는 <xref:System.Windows.Media.StreamGeometry>너무; 어떤 언제 사용 하나요?</span><span class="sxs-lookup"><span data-stu-id="d490d-114">It's always possible to use a <xref:System.Windows.Media.PathGeometry> in any situation where you could use a <xref:System.Windows.Media.StreamGeometry>; so which one should you use?</span></span> <span data-ttu-id="d490d-115">사용 하 여 한 <xref:System.Windows.Media.StreamGeometry> 경로를 수정 하며 만든 후 필요 하지 않을 때 사용 하 여 한 <xref:System.Windows.Media.PathGeometry> 경로를 수정 해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="d490d-115">Use a <xref:System.Windows.Media.StreamGeometry> when you don't need to modify the path after creating it; use a <xref:System.Windows.Media.PathGeometry> if you do need to modify the path.</span></span>  
  
 <span data-ttu-id="d490d-116">간의 차이점에 대 한 자세한 내용은 <xref:System.Windows.Media.PathGeometry> 및 <xref:System.Windows.Media.StreamGeometry> 개체 참조는 [기 하 도형 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-116">For more information about the differences between <xref:System.Windows.Media.PathGeometry> and <xref:System.Windows.Media.StreamGeometry> objects, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
### <a name="a-note-about-white-space"></a><span data-ttu-id="d490d-117">공백에 대한 참고 사항</span><span class="sxs-lookup"><span data-stu-id="d490d-117">A Note about White Space</span></span>  
 <span data-ttu-id="d490d-118">간단히 말해서 이어지는 구문 섹션에는 단일 공백이 표시되지만 단일 공백이 표시되는 모든 위치에서 여러 개의 공백을 사용해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-118">For brevity, a single space is shown in the syntax sections that follow, but multiple spaces are also acceptable wherever a single space is shown.</span></span>  
  
 <span data-ttu-id="d490d-119">두 개의 숫자를 실제로 쉼표나 공백으로 구분할 필요는 없으나 결과 문자열이 모호하지 않는 한도에서만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-119">Two numbers don’t actually have to be separated by a comma or whitespace, but this can only be done when the resulting string is unambiguous.</span></span> <span data-ttu-id="d490d-120">예를 들어, `2..3` 은 실제로: "2"입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-120">For instance, `2..3` is actually two numbers: "2."</span></span> <span data-ttu-id="d490d-121">".3"의 두 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-121">And ".3".</span></span> <span data-ttu-id="d490d-122">마찬가지로, `2-3` 은 "2"와 "-3"입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-122">Similarly, `2-3` is "2" and "-3".</span></span> <span data-ttu-id="d490d-123">명령 앞뒤에는 공백이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-123">Spaces are not required before or after commands, either.</span></span>  
  
### <a name="syntax"></a><span data-ttu-id="d490d-124">구문</span><span class="sxs-lookup"><span data-stu-id="d490d-124">Syntax</span></span>  
 <span data-ttu-id="d490d-125">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 사용 구문에 대 한 특성을 <xref:System.Windows.Media.StreamGeometry> 는 선택적 구성 <xref:System.Windows.Media.FillRule> 값 및 하나 이상의 그림 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-125">The [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.StreamGeometry> is composed of an optional <xref:System.Windows.Media.FillRule> value and one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="d490d-126">StreamGeometry XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="d490d-126">StreamGeometry XAML Attribute Usage</span></span>|  
|-----------------------------------------|  
|<span data-ttu-id="d490d-127">`<` *object* *property* `="`[ `fillRule`] `figureDescription`[ `figureDescription`]\* `" ... />`</span><span class="sxs-lookup"><span data-stu-id="d490d-127">`<` *object* *property* `="`[ `fillRule`] `figureDescription`[ `figureDescription`]\* `" ... />`</span></span>|  
  
 <span data-ttu-id="d490d-128">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 사용 구문에 대 한 특성을 <xref:System.Windows.Media.PathFigureCollection> 하나 이상의 그림 설명으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-128">The [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.PathFigureCollection> is composed of one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="d490d-129">PathFigureCollection XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="d490d-129">PathFigureCollection XAML Attribute Usage</span></span>|  
|-----------------------------------------------|  
|<span data-ttu-id="d490d-130">`<` *object* *property* `="` `figureDescription`[ `figureDescription`]\* `" ... />`</span><span class="sxs-lookup"><span data-stu-id="d490d-130">`<` *object* *property* `="` `figureDescription`[ `figureDescription`]\* `" ... />`</span></span>|  
  
|<span data-ttu-id="d490d-131">용어</span><span class="sxs-lookup"><span data-stu-id="d490d-131">Term</span></span>|<span data-ttu-id="d490d-132">설명</span><span class="sxs-lookup"><span data-stu-id="d490d-132">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d490d-133">*fillRule*</span><span class="sxs-lookup"><span data-stu-id="d490d-133">*fillRule*</span></span>|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-134">지정 여부는 <xref:System.Windows.Media.StreamGeometry> 사용 하 여는 <xref:System.Windows.Media.FillRule.EvenOdd> 또는 <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-134">Specifies whether the <xref:System.Windows.Media.StreamGeometry> uses the <xref:System.Windows.Media.FillRule.EvenOdd> or <xref:System.Windows.Media.FillRule.Nonzero><xref:System.Windows.Media.PathGeometry.FillRule%2A>.</span></span><br /><br /> <span data-ttu-id="d490d-135">-   `F0` 지정 된 <xref:System.Windows.Media.FillRule.EvenOdd> 채우기 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-135">-   `F0` specifies the <xref:System.Windows.Media.FillRule.EvenOdd> fill rule.</span></span><br /><span data-ttu-id="d490d-136">-   `F1` 지정 된 <xref:System.Windows.Media.FillRule.Nonzero> 채우기 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-136">-   `F1` specifies the <xref:System.Windows.Media.FillRule.Nonzero> fill rule.</span></span><br /><br /> <span data-ttu-id="d490d-137">하위 경로 기본 동작을 사용 하 여이 명령을 생략 하면 <xref:System.Windows.Media.FillRule.EvenOdd>합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-137">If you omit this command, the subpath uses the default behavior, which is <xref:System.Windows.Media.FillRule.EvenOdd>.</span></span> <span data-ttu-id="d490d-138">이 명령을 지정하는 경우 맨 앞에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-138">If you specify this command, you must place it first.</span></span>|  
|<span data-ttu-id="d490d-139">*figureDescription*</span><span class="sxs-lookup"><span data-stu-id="d490d-139">*figureDescription*</span></span>|<span data-ttu-id="d490d-140">이동 명령, 그리기 명령 및 선택적 닫기 명령으로 구성된 그림입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-140">A figure composed of a move command, draw commands, and an optional close command.</span></span><br /><br /> <span data-ttu-id="d490d-141">`moveCommand` `drawCommands`  `[` `closeCommand` `]`</span><span class="sxs-lookup"><span data-stu-id="d490d-141">`moveCommand` `drawCommands`  `[` `closeCommand` `]`</span></span>|  
|<span data-ttu-id="d490d-142">*moveCommand*</span><span class="sxs-lookup"><span data-stu-id="d490d-142">*moveCommand*</span></span>|<span data-ttu-id="d490d-143">그림의 시작점을 지정하는 이동 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-143">A move command that specifies the start point of the figure.</span></span> <span data-ttu-id="d490d-144">참조는 [이동 명령을](#themovecommand) 섹션.</span><span class="sxs-lookup"><span data-stu-id="d490d-144">See the [Move Command](#themovecommand) section.</span></span>|  
|<span data-ttu-id="d490d-145">*drawCommands*</span><span class="sxs-lookup"><span data-stu-id="d490d-145">*drawCommands*</span></span>|<span data-ttu-id="d490d-146">그림의 콘텐츠를 설명하는 하나 이상의 그리기 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-146">One or more drawing commands that describe the figure's contents.</span></span> <span data-ttu-id="d490d-147">참조는 [그리기 명령](#drawcommands) 섹션.</span><span class="sxs-lookup"><span data-stu-id="d490d-147">See the [Draw Commands](#drawcommands) section.</span></span>|  
|<span data-ttu-id="d490d-148">*closeCommand*</span><span class="sxs-lookup"><span data-stu-id="d490d-148">*closeCommand*</span></span>|<span data-ttu-id="d490d-149">그림을 닫는 선택적 닫기 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-149">An optional close command that closes figure.</span></span> <span data-ttu-id="d490d-150">참조는 [닫기 명령을](#closecommand) 섹션.</span><span class="sxs-lookup"><span data-stu-id="d490d-150">See the [Close Command](#closecommand) section.</span></span>|  
  
<a name="themovecommand"></a>   
## <a name="move-command"></a><span data-ttu-id="d490d-151">이동 명령</span><span class="sxs-lookup"><span data-stu-id="d490d-151">Move Command</span></span>  
 <span data-ttu-id="d490d-152">새 그림의 시작점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-152">Specifies the start point of a new figure.</span></span>  
  
|<span data-ttu-id="d490d-153">구문</span><span class="sxs-lookup"><span data-stu-id="d490d-153">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="d490d-154">`M` *startPoint*</span><span class="sxs-lookup"><span data-stu-id="d490d-154">`M` *startPoint*</span></span><br /><br /> <span data-ttu-id="d490d-155">또는</span><span class="sxs-lookup"><span data-stu-id="d490d-155">- or -</span></span><br /><br /> <span data-ttu-id="d490d-156">`m` *startPoint*</span><span class="sxs-lookup"><span data-stu-id="d490d-156">`m` *startPoint*</span></span>|  
  
|<span data-ttu-id="d490d-157">용어</span><span class="sxs-lookup"><span data-stu-id="d490d-157">Term</span></span>|<span data-ttu-id="d490d-158">설명</span><span class="sxs-lookup"><span data-stu-id="d490d-158">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d490d-159">*startPoint*</span><span class="sxs-lookup"><span data-stu-id="d490d-159">*startPoint*</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-160">새 그림의 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-160">The start point of a new figure.</span></span>|  
  
 <span data-ttu-id="d490d-161">대문자 `M` 나타냅니다 `startPoint` 값이 절대 값인지; 소문자 `m` 나타냅니다 `startPoint` 이전 시점에 대 한 오프셋은 또는 (0, 0) 존재 하지 않는 경우.</span><span class="sxs-lookup"><span data-stu-id="d490d-161">An uppercase `M` indicates that `startPoint` is an absolute value; a lowercase `m` indicates that `startPoint` is an offset to the previous point, or (0,0) if none exists.</span></span> <span data-ttu-id="d490d-162">이동 명령 뒤에 여러 점을 나열하는 경우 선 명령을 지정했어도 해당 점으로 선이 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-162">If you list multiple points after the move command, a line is drawn to those points though you specified the line command.</span></span>  
  
<a name="drawcommands"></a>   
## <a name="draw-commands"></a><span data-ttu-id="d490d-163">그리기 명령</span><span class="sxs-lookup"><span data-stu-id="d490d-163">Draw Commands</span></span>  
 <span data-ttu-id="d490d-164">그리기 명령은 여러 도형 명령으로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-164">A draw command can consist of several shape commands.</span></span> <span data-ttu-id="d490d-165">선, 수평선, 수직선, 입방형 3차원 곡선, 정방형 3차원 곡선, 부드러운 입방형 3차원 곡선, 부드러운 정방형 3차원 곡선 및 타원형 호 등의 도형 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-165">The following shape commands are available: line, horizontal line, vertical line, cubic Bezier curve, quadratic Bezier curve, smooth cubic Bezier curve, smooth quadratic Bezier curve, and elliptical arc.</span></span>  
  
 <span data-ttu-id="d490d-166">대문자 또는 소문자를 사용하여 각 명령을 입력합니다. 대문자는 절대값을 나타내고 소문자는 상대값을 나타냅니다. 해당 세그먼트에 대한 제어점은 이전 예제의 끝점을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-166">You enter each command by using either an uppercase or a lowercase letter: uppercase letters denote absolute values and lowercase letters denote relative values: the control points for that segment are relative to the end point of the preceding example.</span></span> <span data-ttu-id="d490d-167">동일한 형식의 둘 이상의 명령을 순차적으로 입력할 때 중복 명령 입력; 생략할 수 있습니다. 예를 들어 `L 100,200 300,400` 같습니다 `L 100,200 L 300,400`합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-167">When sequentially entering more than one command of the same type, you can omit the duplicate command entry; for example, `L 100,200 300,400` is equivalent to `L 100,200 L 300,400`.</span></span> <span data-ttu-id="d490d-168">다음 표에서 **이동** 및 **그리기** 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-168">The following table describes the **move** and **draw** commands.</span></span>  
  
### <a name="line-command"></a><span data-ttu-id="d490d-169">선 명령</span><span class="sxs-lookup"><span data-stu-id="d490d-169">Line Command</span></span>  
 <span data-ttu-id="d490d-170">현재 점과 지정된 끝점 간에 직선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-170">Creates a straight line between the current point and the specified end point.</span></span> <span data-ttu-id="d490d-171">`l 20 30` 및 `L 20,30` 은 유효한 예 **줄** 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-171">`l 20 30` and `L 20,30` are examples of valid **line** commands.</span></span>  
  
|<span data-ttu-id="d490d-172">구문</span><span class="sxs-lookup"><span data-stu-id="d490d-172">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="d490d-173">`L` *endPoint*</span><span class="sxs-lookup"><span data-stu-id="d490d-173">`L` *endPoint*</span></span><br /><br /> <span data-ttu-id="d490d-174">또는</span><span class="sxs-lookup"><span data-stu-id="d490d-174">- or -</span></span><br /><br /> <span data-ttu-id="d490d-175">`l` *endPoint*</span><span class="sxs-lookup"><span data-stu-id="d490d-175">`l` *endPoint*</span></span>|  
  
|<span data-ttu-id="d490d-176">용어</span><span class="sxs-lookup"><span data-stu-id="d490d-176">Term</span></span>|<span data-ttu-id="d490d-177">설명</span><span class="sxs-lookup"><span data-stu-id="d490d-177">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d490d-178">*endPoint*</span><span class="sxs-lookup"><span data-stu-id="d490d-178">*endPoint*</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-179">선의 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-179">The end point of the line.</span></span>|  

<span data-ttu-id="d490d-180">대문자 `L` 나타냅니다 `endPoint` 값이 절대 값인지; 소문자 `l` 나타냅니다 `endPoint` 이전 시점에 대 한 오프셋은 또는 (0, 0) 존재 하지 않는 경우.</span><span class="sxs-lookup"><span data-stu-id="d490d-180">An uppercase `L` indicates that `endPoint` is an absolute value; a lowercase `l` indicates that `endPoint` is an offset to the previous point, or (0,0) if none exists.</span></span>

### <a name="horizontal-line-command"></a><span data-ttu-id="d490d-181">수평선 명령</span><span class="sxs-lookup"><span data-stu-id="d490d-181">Horizontal Line Command</span></span>  
 <span data-ttu-id="d490d-182">현재 점과 지정된 x 좌표 간에 수평선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-182">Creates a horizontal line between the current point and the specified x-coordinate.</span></span> <span data-ttu-id="d490d-183">`H 90`은 유효한 수평선 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-183">`H 90` is an example of a valid horizontal line command.</span></span>

  
|<span data-ttu-id="d490d-184">구문</span><span class="sxs-lookup"><span data-stu-id="d490d-184">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="d490d-185">`H`  *x*</span><span class="sxs-lookup"><span data-stu-id="d490d-185">`H`  *x*</span></span><br /><br /> <span data-ttu-id="d490d-186">또는</span><span class="sxs-lookup"><span data-stu-id="d490d-186">- or -</span></span><br /><br /> <span data-ttu-id="d490d-187">`h`  *x*</span><span class="sxs-lookup"><span data-stu-id="d490d-187">`h`  *x*</span></span>|  
  
|<span data-ttu-id="d490d-188">용어</span><span class="sxs-lookup"><span data-stu-id="d490d-188">Term</span></span>|<span data-ttu-id="d490d-189">설명</span><span class="sxs-lookup"><span data-stu-id="d490d-189">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d490d-190">*x*</span><span class="sxs-lookup"><span data-stu-id="d490d-190">*x*</span></span>|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-191">선 끝점의 x 좌표입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-191">The x-coordinate of the end point of the line.</span></span>|  
  
<span data-ttu-id="d490d-192">대문자 `H` 나타냅니다 `x` 값이 절대 값인지; 소문자 `h` 나타냅니다 `x` 이전 시점에 대 한 오프셋은 또는 (0, 0) 존재 하지 않는 경우.</span><span class="sxs-lookup"><span data-stu-id="d490d-192">An uppercase `H` indicates that `x` is an absolute value; a lowercase `h` indicates that `x` is an offset to the previous point, or (0,0) if none exists.</span></span>
  
### <a name="vertical-line-command"></a><span data-ttu-id="d490d-193">수직선 명령</span><span class="sxs-lookup"><span data-stu-id="d490d-193">Vertical Line Command</span></span>  
 <span data-ttu-id="d490d-194">현재 점과 지정된 y 좌표 간에 수직선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-194">Creates a vertical line between the current point and the specified y-coordinate.</span></span> <span data-ttu-id="d490d-195">`v 90`은 유효한 수직선 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-195">`v 90` is an example of a valid vertical line command.</span></span>

  
|<span data-ttu-id="d490d-196">구문</span><span class="sxs-lookup"><span data-stu-id="d490d-196">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="d490d-197">`V`  *y*</span><span class="sxs-lookup"><span data-stu-id="d490d-197">`V`  *y*</span></span><br /><br /> <span data-ttu-id="d490d-198">또는</span><span class="sxs-lookup"><span data-stu-id="d490d-198">- or -</span></span><br /><br /> <span data-ttu-id="d490d-199">`v`  *y*</span><span class="sxs-lookup"><span data-stu-id="d490d-199">`v`  *y*</span></span>|  
  
|<span data-ttu-id="d490d-200">용어</span><span class="sxs-lookup"><span data-stu-id="d490d-200">Term</span></span>|<span data-ttu-id="d490d-201">설명</span><span class="sxs-lookup"><span data-stu-id="d490d-201">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d490d-202">*y*</span><span class="sxs-lookup"><span data-stu-id="d490d-202">*y*</span></span>|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-203">선 끝점의 y 좌표입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-203">The y-coordinate of the end point of the line.</span></span>|  

<span data-ttu-id="d490d-204">대문자 `V` 나타냅니다 `y` 값이 절대 값인지; 소문자 `v` 나타냅니다 `y` 이전 시점에 대 한 오프셋은 또는 (0, 0) 존재 하지 않는 경우.</span><span class="sxs-lookup"><span data-stu-id="d490d-204">An uppercase `V` indicates that `y` is an absolute value; a lowercase `v` indicates that `y` is an offset to the previous point, or (0,0) if none exists.</span></span>  
    
### <a name="cubic-bezier-curve-command"></a><span data-ttu-id="d490d-205">입방형 3차원 곡선 명령</span><span class="sxs-lookup"><span data-stu-id="d490d-205">Cubic Bezier Curve Command</span></span>  
 <span data-ttu-id="d490d-206">지정 된 두 개의 제어점을 사용 하 여 현재 지점과 지정한 끝점 간의 입방 형 3 차원 곡선을 만듭니다 (`controlPoint`1 및 `controlPoint`2).</span><span class="sxs-lookup"><span data-stu-id="d490d-206">Creates a cubic Bezier curve between the current point and the specified end point by using the two specified control points (`controlPoint`1 and `controlPoint`2).</span></span> <span data-ttu-id="d490d-207">`C 100,200 200,400 300,200`은 유효한 곡선 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-207">`C 100,200 200,400 300,200` is an example of a valid curve command.</span></span>  
  
|<span data-ttu-id="d490d-208">구문</span><span class="sxs-lookup"><span data-stu-id="d490d-208">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="d490d-209">`C` `controlPoint`1`controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="d490d-209">`C` `controlPoint`1`controlPoint`2`endPoint`</span></span><br /><br /> <span data-ttu-id="d490d-210">또는</span><span class="sxs-lookup"><span data-stu-id="d490d-210">- or -</span></span><br /><br /> <span data-ttu-id="d490d-211">`c` `controlPoint`1`controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="d490d-211">`c` `controlPoint`1`controlPoint`2`endPoint`</span></span>|  
  
|<span data-ttu-id="d490d-212">용어</span><span class="sxs-lookup"><span data-stu-id="d490d-212">Term</span></span>|<span data-ttu-id="d490d-213">설명</span><span class="sxs-lookup"><span data-stu-id="d490d-213">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d490d-214">`controlPoint`1</span><span class="sxs-lookup"><span data-stu-id="d490d-214">`controlPoint`1</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-215">곡선의 시작 접선을 결정하는 곡선의 첫 번째 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-215">The first control point of the curve, which determines the starting tangent of the curve.</span></span>|  
|<span data-ttu-id="d490d-216">`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="d490d-216">`controlPoint`2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-217">곡선의 끝 접선을 결정하는 곡선의 두 번째 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-217">The second control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-218">곡선을 그릴 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-218">The point to which the curve is drawn.</span></span>|  
  
### <a name="quadratic-bezier-curve-command"></a><span data-ttu-id="d490d-219">정방형 3차원 곡선 명령</span><span class="sxs-lookup"><span data-stu-id="d490d-219">Quadratic Bezier Curve Command</span></span>  
 <span data-ttu-id="d490d-220">지정 된 제어점을 사용 하 여 현재 지점과 지정한 끝점 사이 정방형 3 차원 곡선을 만듭니다 (`controlPoint`).</span><span class="sxs-lookup"><span data-stu-id="d490d-220">Creates a quadratic Bezier curve between the current point and the specified end point by using the specified control point (`controlPoint`).</span></span> <span data-ttu-id="d490d-221">`q 100,200 300,200`은 유효한 정방형 3차원 곡선 명령의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-221">`q 100,200 300,200` is an example of a valid quadratic Bezier curve command.</span></span>  
  
|<span data-ttu-id="d490d-222">구문</span><span class="sxs-lookup"><span data-stu-id="d490d-222">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="d490d-223">`Q` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="d490d-223">`Q` `controlPoint` `endPoint`</span></span><br /><br /> <span data-ttu-id="d490d-224">또는</span><span class="sxs-lookup"><span data-stu-id="d490d-224">- or -</span></span><br /><br /> <span data-ttu-id="d490d-225">`q` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="d490d-225">`q` `controlPoint` `endPoint`</span></span>|  
  
|<span data-ttu-id="d490d-226">용어</span><span class="sxs-lookup"><span data-stu-id="d490d-226">Term</span></span>|<span data-ttu-id="d490d-227">설명</span><span class="sxs-lookup"><span data-stu-id="d490d-227">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-228">곡선의 시작 및 끝 접선을 결정하는 곡선의 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-228">The control point of the curve, which determines the starting and ending tangents of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-229">곡선을 그릴 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-229">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-cubic-bezier-curve-command"></a><span data-ttu-id="d490d-230">부드러운 입방형 3차원 곡선 명령</span><span class="sxs-lookup"><span data-stu-id="d490d-230">Smooth cubic Bezier curve Command</span></span>  
 <span data-ttu-id="d490d-231">현재 점과 지정된 끝점 간에 입방형 3차원 곡선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-231">Creates a cubic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="d490d-232">첫 번째 제어점은 현재 점을 기준으로 이전 명령의 두 번째 제어점의 리플렉션으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-232">The first control point is assumed to be the reflection of the second control point of the previous command relative to the current point.</span></span> <span data-ttu-id="d490d-233">이전 명령이 없거나 이전 명령이 입방형 3차원 곡선 명령 또는 부드러운 입방 형 3차원 곡선 명령이 아닌 경우 첫 번째 제어점이 현재 점과 일치한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-233">If there is no previous command or if the previous command was not a cubic Bezier curve command or a smooth cubic Bezier curve command, assume the first control point is coincident with the current point.</span></span> <span data-ttu-id="d490d-234">두 번째 제어점, 곡선의 끝에 대 한 제어 지점으로 지정 `controlPoint`2입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-234">The second control point, the control point for the end of the curve, is specified by `controlPoint`2.</span></span> <span data-ttu-id="d490d-235">예를 들어 `S 100,200 200,300` 올바른 부드러운 입방 형 3 베 지 어 곡선 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-235">For example, `S 100,200 200,300` is a valid smooth cubic Bezier curve command.</span></span>  
  
|<span data-ttu-id="d490d-236">구문</span><span class="sxs-lookup"><span data-stu-id="d490d-236">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="d490d-237">`S` `controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="d490d-237">`S` `controlPoint`2`endPoint`</span></span><br /><br /> <span data-ttu-id="d490d-238">또는</span><span class="sxs-lookup"><span data-stu-id="d490d-238">- or -</span></span><br /><br /> <span data-ttu-id="d490d-239">`s` `controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="d490d-239">`s` `controlPoint`2`endPoint`</span></span>|  
  
|<span data-ttu-id="d490d-240">용어</span><span class="sxs-lookup"><span data-stu-id="d490d-240">Term</span></span>|<span data-ttu-id="d490d-241">설명</span><span class="sxs-lookup"><span data-stu-id="d490d-241">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d490d-242">`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="d490d-242">`controlPoint`2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-243">곡선의 끝 접선을 결정하는 곡선의 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-243">The control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-244">곡선을 그릴 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-244">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a><span data-ttu-id="d490d-245">부드러운 정방형 3차원 곡선 명령</span><span class="sxs-lookup"><span data-stu-id="d490d-245">Smooth quadratic Bezier curve Command</span></span>  
 <span data-ttu-id="d490d-246">현재 점과 지정된 끝점 간에 정방형 3차원 곡선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-246">Creates a quadratic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="d490d-247">제어점은 현재 점을 기준으로 이전 명령의 제어점의 리플렉션으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-247">The control point is assumed to be the reflection of the control point of the previous command relative to the current point.</span></span> <span data-ttu-id="d490d-248">이전 명령이 없거나 이전 명령이 정방형 3차원 곡선 명령 또는 부드러운 정방 형 3차원 곡선 명령이 아닌 경우 제어점이 현재 점과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-248">If there is no previous command or if the previous command was not a quadratic Bezier curve command or a smooth quadratic Bezier curve command, the control point is coincident with the current point.</span></span>  
  
|<span data-ttu-id="d490d-249">구문</span><span class="sxs-lookup"><span data-stu-id="d490d-249">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="d490d-250">`T` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="d490d-250">`T` `controlPoint` `endPoint`</span></span><br /><br /> <span data-ttu-id="d490d-251">또는</span><span class="sxs-lookup"><span data-stu-id="d490d-251">- or -</span></span><br /><br /> <span data-ttu-id="d490d-252">`t` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="d490d-252">`t` `controlPoint` `endPoint`</span></span>|  
  
|<span data-ttu-id="d490d-253">용어</span><span class="sxs-lookup"><span data-stu-id="d490d-253">Term</span></span>|<span data-ttu-id="d490d-254">설명</span><span class="sxs-lookup"><span data-stu-id="d490d-254">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-255">곡선의 시작 접선을 결정하는 곡선의 제어점입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-255">The control point of the curve, which determines the starting and tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-256">곡선을 그릴 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-256">The point to which the curve is drawn.</span></span>|  
  
### <a name="elliptical-arc-command"></a><span data-ttu-id="d490d-257">타원형 호 명령</span><span class="sxs-lookup"><span data-stu-id="d490d-257">Elliptical Arc Command</span></span>  
 <span data-ttu-id="d490d-258">현재 점과 지정된 끝점 간에 타원형 호를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-258">Creates an elliptical arc between the current point and the specified end point.</span></span>  
  
|<span data-ttu-id="d490d-259">구문</span><span class="sxs-lookup"><span data-stu-id="d490d-259">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="d490d-260">`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="d490d-260">`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span></span><br /><br /> <span data-ttu-id="d490d-261">또는</span><span class="sxs-lookup"><span data-stu-id="d490d-261">- or -</span></span><br /><br /> <span data-ttu-id="d490d-262">`a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="d490d-262">`a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span></span>|  
  
|<span data-ttu-id="d490d-263">용어</span><span class="sxs-lookup"><span data-stu-id="d490d-263">Term</span></span>|<span data-ttu-id="d490d-264">설명</span><span class="sxs-lookup"><span data-stu-id="d490d-264">Description</span></span>|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-265">원호의 X 및 y 반지름입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-265">The x- and y-radius of the arc.</span></span>|  
|`rotationAngle`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-266">타원의 회전 각도입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-266">The rotation of the ellipse, in degrees.</span></span>|  
|`isLargeArcFlag`|<span data-ttu-id="d490d-267">호의 각도가 180도보다 커야 하면 1로 설정하고, 그렇지 않으면 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-267">Set to 1 if the angle of the arc should be 180 degrees or greater; otherwise, set to 0.</span></span>|  
|`sweepDirectionFlag`|<span data-ttu-id="d490d-268">호가 양의 각도 방향으로 그려지면 1로 설정하고, 그렇지 않으면 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-268">Set to 1 if the arc is drawn in a positive-angle direction; otherwise, set to 0.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-269">호를 그리는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-269">The point to which the arc is drawn.</span></span>|  
  
<a name="closecommand"></a>   
## <a name="the-close-command"></a><span data-ttu-id="d490d-270">닫기 명령</span><span class="sxs-lookup"><span data-stu-id="d490d-270">The Close Command</span></span>  
 <span data-ttu-id="d490d-271">현재 그림을 끝내고 현재 점을 그림의 시작 점에 연결하는 선을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-271">Ends the current figure and creates a line that connects the current point to the starting point of the figure.</span></span> <span data-ttu-id="d490d-272">이 명령은 그림의 마지막 세그먼트와 첫 번째 세그먼트 사이에 선 조인(모서리)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-272">This command creates a line-join (corner) between the last segment and the first segment of the figure.</span></span>  
  
|<span data-ttu-id="d490d-273">구문</span><span class="sxs-lookup"><span data-stu-id="d490d-273">Syntax</span></span>|  
|------------|  
|`Z`<br /><br /> <span data-ttu-id="d490d-274">또는</span><span class="sxs-lookup"><span data-stu-id="d490d-274">- or -</span></span><br /><br /> `z`|  

<a name="pointsyntax"></a>   
## <a name="point-syntax"></a><span data-ttu-id="d490d-275">점 구문</span><span class="sxs-lookup"><span data-stu-id="d490d-275">Point Syntax</span></span>  
 <span data-ttu-id="d490d-276">점의 x 및 y 좌표를 설명 합니다. 여기서 (0, 0)은 왼쪽된 위 모퉁이입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-276">Describes the x- and y-coordinates of a point where (0,0) is the top left corner.</span></span>
  
|<span data-ttu-id="d490d-277">구문</span><span class="sxs-lookup"><span data-stu-id="d490d-277">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="d490d-278">`x` `,` `y`</span><span class="sxs-lookup"><span data-stu-id="d490d-278">`x` `,` `y`</span></span><br /><br /> <span data-ttu-id="d490d-279">또는</span><span class="sxs-lookup"><span data-stu-id="d490d-279">- or -</span></span><br /><br /> <span data-ttu-id="d490d-280">`x` `y`</span><span class="sxs-lookup"><span data-stu-id="d490d-280">`x` `y`</span></span>|  
  
|<span data-ttu-id="d490d-281">용어</span><span class="sxs-lookup"><span data-stu-id="d490d-281">Term</span></span>|<span data-ttu-id="d490d-282">설명</span><span class="sxs-lookup"><span data-stu-id="d490d-282">Description</span></span>|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-283">점의 X 좌표입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-283">The x-coordinate of the point.</span></span>|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="d490d-284">점의 Y 좌표입니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-284">The y-coordinate of the point.</span></span>|  
  
<a name="specialvalues"></a>   
## <a name="special-values"></a><span data-ttu-id="d490d-285">특수 값</span><span class="sxs-lookup"><span data-stu-id="d490d-285">Special Values</span></span>  
 <span data-ttu-id="d490d-286">표준 숫자 값 대신 다음과 같은 특수 값을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-286">Instead of a standard numerical value, you can also use the following special values.</span></span> <span data-ttu-id="d490d-287">이러한 값은 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-287">These values are case-sensitive.</span></span>  
  
 <span data-ttu-id="d490d-288">Infinity</span><span class="sxs-lookup"><span data-stu-id="d490d-288">Infinity</span></span>  
 <span data-ttu-id="d490d-289">나타냅니다 <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-289">Represents <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="d490d-290">-Infinity</span><span class="sxs-lookup"><span data-stu-id="d490d-290">-Infinity</span></span>  
 <span data-ttu-id="d490d-291">나타냅니다 <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-291">Represents <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="d490d-292">NaN</span><span class="sxs-lookup"><span data-stu-id="d490d-292">NaN</span></span>  
 <span data-ttu-id="d490d-293">나타냅니다 <xref:System.Double.NaN?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-293">Represents <xref:System.Double.NaN?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="d490d-294">과학적 표기법을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-294">You may also use scientific notation.</span></span> <span data-ttu-id="d490d-295">예를 들어 `+1.e17` 유효한 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d490d-295">For example, `+1.e17` is a valid value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d490d-296">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d490d-296">See Also</span></span>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.StreamGeometry>  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Media.PathFigureCollection>  
 [<span data-ttu-id="d490d-297">WPF에서 Shape 및 기본 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="d490d-297">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [<span data-ttu-id="d490d-298">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="d490d-298">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="d490d-299">방법 항목</span><span class="sxs-lookup"><span data-stu-id="d490d-299">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)
