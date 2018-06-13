---
title: '방법: OvalShape 및 RectangleShape 컨트롤을 사용하여 도형 그리기(Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OvalShape control [Visual Basic]
- shapes, drawing
- RectangleShape control [Visual Basic]
ms.assetid: 0275b4c6-7a13-46c8-90f3-61db308c6b5d
ms.openlocfilehash: f87865ba3aebe5739b87d6ae6bfeaa957af726d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33592277"
---
# <a name="how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls-visual-studio"></a><span data-ttu-id="0bfe3-102">방법: OvalShape 및 RectangleShape 컨트롤을 사용하여 도형 그리기(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="0bfe3-102">How to: Draw Shapes with the OvalShape and RectangleShape Controls (Visual Studio)</span></span>
<span data-ttu-id="0bfe3-103"><xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 컨트롤을 사용하여 디자인 타임과 런타임에 폼이나 컨테이너에서 원 또는 타원을 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> control to draw circles or ovals on a form or container, both at design time and at run time.</span></span> <span data-ttu-id="0bfe3-104"><xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 컨트롤을 사용하면 폼이나 컨테이너에서 정사각형, 직사각형 또는 모서리가 둥근 직사각형을 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-104">You can use the <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> control to draw squares, rectangles, or rectangles with rounded corners on a form or container.</span></span> <span data-ttu-id="0bfe3-105">이 컨트롤을 사용하여 디자인 타임 및 런타임에 도형을 그릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-105">You can also use this control to draw shapes both at design time and at run time.</span></span>  
  
 <span data-ttu-id="0bfe3-106">테두리 너비, 색 및 스타일을 변경하여 도형의 모양을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-106">You can customize the appearance of a shape by changing the width, color, and style of the border.</span></span> <span data-ttu-id="0bfe3-107">도형의 배경은 기본적으로 투명합니다. 단색, 패턴, 그라데이션 채우기(색 간 전환) 또는 이미지를 표시하도록 배경을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-107">The background of a shape is transparent by default; you can customize the background to display a solid color, a pattern, a gradient fill (transitioning from one color to another), or an image.</span></span>  
  
### <a name="to-draw-a-simple-shape-at-design-time"></a><span data-ttu-id="0bfe3-108">디자인 타임에 간단한 도형을 그리려면</span><span class="sxs-lookup"><span data-stu-id="0bfe3-108">To draw a simple shape at design time</span></span>  
  
1.  <span data-ttu-id="0bfe3-109">끌어서는 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 또는 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 에서 제어는 **Visual Basic PowerPacks** 탭 (참조를 설치 하려면 [Visual Basic Power Packs 컨트롤](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md))에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-109">Drag the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> or <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> control from the **Visual Basic PowerPacks** tab (to install, see [Visual Basic Power Packs Controls](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md))in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="0bfe3-110">크기 조정 및 이동 핸들을 끌어 도형의 크기와 위치를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-110">Drag the sizing and move handles to size and position the shape.</span></span>  
  
     <span data-ttu-id="0bfe3-111">크기 조정 하 고 변경 하 여 셰이프를 배치할 수도 있습니다는 `Size` 및 `Position` 속성에는 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-111">You can also size and position the shape by changing the `Size` and `Position` properties in the **Properties** window.</span></span>  
  
     <span data-ttu-id="0bfe3-112">모퉁이가 둥근 사각형을 만들려면 선택는 `CornerRadius` 속성에는 **속성** 창이 0 보다 큰 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-112">To create a rectangle with rounded corners, select the `CornerRadius` property in the **Properties** window and set it to a value that is greater than 0.</span></span>  
  
3.  <span data-ttu-id="0bfe3-113">에 **속성** 창에서 필요에 따라 추가 속성을 설정 하 여 도형의 모양을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-113">In the **Properties** window, optionally set additional properties to change the appearance of the shape.</span></span>  
  
### <a name="to-draw-a-simple-shape-at-run-time"></a><span data-ttu-id="0bfe3-114">런타임에 간단한 도형을 그리려면</span><span class="sxs-lookup"><span data-stu-id="0bfe3-114">To draw a simple shape at run time</span></span>  
  
1.  <span data-ttu-id="0bfe3-115">**프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-115">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="0bfe3-116">에 **참조 추가** 대화 상자에서 **Microsoft.VisualBasic.PowerPacks.VS**, 클릭 하 고 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-116">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="0bfe3-117">에 **코드 편집기**, 추가 `Imports` 또는 `using` 모듈 맨 위에 있는 문:</span><span class="sxs-lookup"><span data-stu-id="0bfe3-117">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="0bfe3-118">`Event` 프로시저에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-118">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.cs)]
     [!code-vb[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.vb)]  
  
## <a name="customizing-shapes"></a><span data-ttu-id="0bfe3-119">도형 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0bfe3-119">Customizing Shapes</span></span>  
 <span data-ttu-id="0bfe3-120">기본 설정을 사용하는 경우 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 및 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 컨트롤은 너비가 1픽셀이고 배경이 투명한 검은색 실선 테두리로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-120">When you use the default settings, the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> and <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controls are displayed with a solid black border that is one pixel wide and a transparent background.</span></span> <span data-ttu-id="0bfe3-121">속성을 설정하여 테두리의 너비, 스타일 및 색을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-121">You can change the width, style, and color of the border by setting properties.</span></span> <span data-ttu-id="0bfe3-122">추가 속성을 사용하면 도형의 배경을 단색, 패턴, 그라데이션 채우기 또는 이미지로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-122">Additional properties enable you to change the background of a shape to a solid color, a pattern, a gradient fill, or an image.</span></span>  
  
 <span data-ttu-id="0bfe3-123">도형의 배경색을 변경하기 전에 여러 속성이 상호 작용하는 방법을 파악해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-123">Before you change the background of a shape, you should know how several of the properties interact.</span></span>  
  
-   <span data-ttu-id="0bfe3-124"><xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A>로 설정되어 있지 않으면 <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque> 속성 설정을 사용해도 아무 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-124">The <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> property setting has no effect unless the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span></span>  
  
-   <span data-ttu-id="0bfe3-125"><xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>로 설정되어 있으면 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>는 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-125">If the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>, the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> overrides the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>.</span></span>  
  
-   <span data-ttu-id="0bfe3-126"><xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> 또는 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>과 같은 패턴 값으로 설정되어 있으면 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>에 해당 패턴이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-126">If the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property is set to a pattern value such as <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> or <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>, the pattern will be displayed in the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>.</span></span> <span data-ttu-id="0bfe3-127"><xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A>로 설정되어 있으면 배경은 <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-127">The background will be displayed in the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>, provided that the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span></span>  
  
-   <span data-ttu-id="0bfe3-128">그라데이션 채우기를 표시하려면 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> 속성을 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>로 설정해야 하며 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> 속성은 <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None> 이외의 값으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-128">In order to display a gradient fill, the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property must be set to <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid> and the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> property must be set to a value other than <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None>.</span></span>  
  
-   <span data-ttu-id="0bfe3-129"><xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> 속성을 이미지로 설정하면 다른 모든 배경 설정이 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-129">Setting the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> property to an image overrides all other background settings.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-custom-border"></a><span data-ttu-id="0bfe3-130">사용자 지정 테두리가 있는 원을 그리려면</span><span class="sxs-lookup"><span data-stu-id="0bfe3-130">To draw a circle that has a custom border</span></span>  
  
1.  <span data-ttu-id="0bfe3-131">끌어서는 `OvalShape` 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-131">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="0bfe3-132">에 **속성** 창에는 `Size` 속성을 설정 `Height` 및 `Width` 를 같은 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-132">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="0bfe3-133">`BorderColor` 속성을 원하는 색으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-133">Set the `BorderColor` property to the color that you want.</span></span>  
  
4.  <span data-ttu-id="0bfe3-134">`BorderStyle` 속성을 `Solid` 이외의 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-134">Set the `BorderStyle` property to any value other than `Solid`.</span></span>  
  
5.  <span data-ttu-id="0bfe3-135">`BorderWidth`를 픽셀 단위의 원하는 크기로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-135">Set the `BorderWidth` to the size that you want, in pixels.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-solid-fill"></a><span data-ttu-id="0bfe3-136">단색 채우기가 적용된 원을 그리려면</span><span class="sxs-lookup"><span data-stu-id="0bfe3-136">To draw a circle that has a solid fill</span></span>  
  
1.  <span data-ttu-id="0bfe3-137">끌어서는 `OvalShape` 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-137">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="0bfe3-138">에 **속성** 창에는 `Size` 속성을 설정 `Height` 및 `Width` 를 같은 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-138">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="0bfe3-139">`BackColor` 속성을 원하는 색으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-139">Set the `BackColor` property to the color that you want.</span></span>  
  
4.  <span data-ttu-id="0bfe3-140">`BackStyle` 속성을 `Opaque`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-140">Set the `BackStyle` property to `Opaque`.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-patterned-fill"></a><span data-ttu-id="0bfe3-141">무늬가 적용된 원을 그리려면</span><span class="sxs-lookup"><span data-stu-id="0bfe3-141">To draw a circle that has a patterned fill</span></span>  
  
1.  <span data-ttu-id="0bfe3-142">끌어서는 `OvalShape` 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-142">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="0bfe3-143">에 **속성** 창에는 `Size` 속성을 설정 `Height` 및 `Width` 를 같은 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-143">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="0bfe3-144">`BackColor` 속성을 배경에 사용할 색으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-144">Set the `BackColor` property to the color that you want for the background.</span></span>  
  
4.  <span data-ttu-id="0bfe3-145">`BackStyle` 속성을 `Opaque`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-145">Set the `BackStyle` property to `Opaque`.</span></span>  
  
5.  <span data-ttu-id="0bfe3-146">`FillColor` 속성을 무늬에 사용할 색으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-146">Set the `FillColor` property to the color that you want for the pattern.</span></span>  
  
6.  <span data-ttu-id="0bfe3-147">`FillStyle` 속성을 `Transparent` 또는 `Solid` 이외의 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-147">Set the `FillStyle` property to any value other than `Transparent` or `Solid`.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-gradient-fill"></a><span data-ttu-id="0bfe3-148">그라데이션 채우기가 적용된 원을 그리려면</span><span class="sxs-lookup"><span data-stu-id="0bfe3-148">To draw a circle that has a gradient fill</span></span>  
  
1.  <span data-ttu-id="0bfe3-149">끌어서는 `OvalShape` 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-149">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="0bfe3-150">에 **속성** 창에는 `Size` 속성을 설정 `Height` 및 `Width` 를 같은 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-150">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="0bfe3-151">`FillColor` 속성을 시작 색으로 사용할 색으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-151">Set the `FillColor` property to the color that you want for the starting color.</span></span>  
  
4.  <span data-ttu-id="0bfe3-152">`FillGradientColor` 속성을 종료 색으로 사용할 색으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-152">Set the `FillGradientColor` property to the color that you want for the ending color.</span></span>  
  
5.  <span data-ttu-id="0bfe3-153">`FillGradientStyle` 속성을 `None` 이외의 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-153">Set the `FillGradientStyle` property to a value other than `None`.</span></span>  
  
#### <a name="to-draw-a-circle-that-is-filled-with-an-image"></a><span data-ttu-id="0bfe3-154">이미지로 채워진 원을 그리려면</span><span class="sxs-lookup"><span data-stu-id="0bfe3-154">To draw a circle that is filled with an image</span></span>  
  
1.  <span data-ttu-id="0bfe3-155">끌어서는 `OvalShape` 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-155">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="0bfe3-156">에 **속성** 창에는 `Size` 속성을 설정 `Height` 및 `Width` 를 같은 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-156">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="0bfe3-157">선택 된 `BackgroundImage` 속성을 클릭은 **줄임표** 단추 (...).</span><span class="sxs-lookup"><span data-stu-id="0bfe3-157">Select the `BackgroundImage` property and click the **ellipsis** button (...).</span></span>  
  
4.  <span data-ttu-id="0bfe3-158">에 **리소스 선택** 대화 상자를 표시할 이미지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-158">In the **Select Resource** dialog box, select an image to display.</span></span> <span data-ttu-id="0bfe3-159">이미지 리소스가 표시 되 면 클릭 **가져오기** 이미지의 위치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-159">If no image resources are listed, click **Import** to browse to the location of an image.</span></span>  
  
5.  <span data-ttu-id="0bfe3-160">클릭 **확인** 여 이미지를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe3-160">Click **OK** to insert the image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bfe3-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bfe3-161">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>  
 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>  
 [<span data-ttu-id="0bfe3-162">Line 및 Shape 컨트롤 소개</span><span class="sxs-lookup"><span data-stu-id="0bfe3-162">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [<span data-ttu-id="0bfe3-163">방법: LineShape 컨트롤로 선 그리기</span><span class="sxs-lookup"><span data-stu-id="0bfe3-163">How to: Draw Lines with the LineShape Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
