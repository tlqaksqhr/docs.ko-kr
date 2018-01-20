---
title: "그래픽 및 멀티미디어"
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
- media [WPF], features
- video effects [WPF]
- sound effects [WPF]
- animation [WPF], features
- graphics features [WPF]
- transition effects [WPF]
ms.assetid: 1817d9dc-3d6c-46cb-afc8-63b0bae35e37
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 013ae46e2d90a9eda42d33e95e590812489fa04b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="graphics-and-multimedia"></a><span data-ttu-id="30d1b-102">그래픽 및 멀티미디어</span><span class="sxs-lookup"><span data-stu-id="30d1b-102">Graphics and Multimedia</span></span>
<a name="introduction"></a>
<span data-ttu-id="30d1b-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]멀티미디어, 벡터 그래픽, 애니메이션 및 쉽게 흥미로운 사용자 인터페이스 및 콘텐츠를 작성 하는 개발자를 위한 콘텐츠 컴퍼지션에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides support for multimedia, vector graphics, animation, and content composition, making it easy for developers to build interesting user interfaces and content.</span></span> <span data-ttu-id="30d1b-104">[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]를 사용하여 벡터 그래픽이나 복잡한 애니메이션을 만든 후 미디어를 응용 프로그램에 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-104">Using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], you can create vector graphics or complex animations and integrate media into your applications.</span></span>  
  
 <span data-ttu-id="30d1b-105">이 항목에서는 그래픽, 전환 효과, 소리 및 비디오를 응용 프로그램에 추가할 수 있도록 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 그래픽, 애니메이션 및 미디어 기능을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-105">This topic introduces the graphics, animation, and media features of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], which enable you to add graphics, transition effects, sound, and video to your applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30d1b-106">Windows 서비스에서 WPF 유형을 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-106">Using WPF types in a Windows service is strongly discouraged.</span></span> <span data-ttu-id="30d1b-107">Windows 서비스에서 WPF 유형을 사용하려고 하면 서비스가 예상대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-107">If you attempt to use WPF types in a Windows service, the service may not work as expected.</span></span>   
  
<a name="whats_new_with_graphics_and_multimedia_in_wpf_4"></a>   
## <a name="whats-new-with-graphics-and-multimedia-in-wpf-4"></a><span data-ttu-id="30d1b-108">WPF 4에 포함된 그래픽 및 멀티미디어의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="30d1b-108">What's New with Graphics and Multimedia in WPF 4</span></span>  
 <span data-ttu-id="30d1b-109">그래픽 및 애니메이션에 관련해서 몇 가지 사항이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-109">Several changes have been made related to graphics and animations.</span></span>  
  
-   <span data-ttu-id="30d1b-110">레이아웃 조정</span><span class="sxs-lookup"><span data-stu-id="30d1b-110">Layout Rounding</span></span>  
  
     <span data-ttu-id="30d1b-111">개체 가장자리가 픽셀 장치 중앙에 놓이면 DPI 독립적 그래픽 시스템은 흐릿한 가장자리 또는 반투명 가장자리와 같은 렌더링 아티팩트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-111">When an object edge falls in the middle of a pixel device, the DPI-independent graphics system can create rendering artifacts, such as blurry or semi-transparent edges.</span></span> <span data-ttu-id="30d1b-112">이전 버전의 WPF에는 이러한 경우를 처리하는 데 도움이 되는 픽셀 맞추기 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-112">Previous versions of WPF included pixel snapping to help handle this case.</span></span> <span data-ttu-id="30d1b-113">Silverlight 2에서는 가장자리가 전체 픽셀 경계에 딱 맞게 요소를 이동하는 또 다른 방법인 레이아웃 조정이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-113">Silverlight 2 introduced layout rounding, which is another way to move elements so that edges fall on whole pixel boundaries.</span></span> <span data-ttu-id="30d1b-114">WPF에는 이제 레이아웃 반올림을와 지원는 <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> 연결 된 속성을 <xref:System.Windows.FrameworkElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-114">WPF now supports layout rounding with the <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> attached property on <xref:System.Windows.FrameworkElement>.</span></span>  
  
-   <span data-ttu-id="30d1b-115">캐시된 컴퍼지션</span><span class="sxs-lookup"><span data-stu-id="30d1b-115">Cached Composition</span></span>  
  
     <span data-ttu-id="30d1b-116">New를 사용 하 여 <xref:System.Windows.Media.BitmapCache> 및 <xref:System.Windows.Media.BitmapCacheBrush> 클래스, 복잡 한 비트맵으로 시각적 트리 부분을 캐시 하 고 렌더링 시간을 크게 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-116">By using the new <xref:System.Windows.Media.BitmapCache> and <xref:System.Windows.Media.BitmapCacheBrush> classes, you can cache a complex part of the visual tree as a bitmap and greatly improve rendering time.</span></span> <span data-ttu-id="30d1b-117">비트맵은 마우스 클릭 같은 사용자 입력에 응답하며, 브러시처럼 다른 요소에 칠할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-117">The bitmap remains responsive to user input, such as mouse clicks, and you can paint it onto other elements just like any brush.</span></span>  
  
-   <span data-ttu-id="30d1b-118">픽셀 셰이더 3 지원</span><span class="sxs-lookup"><span data-stu-id="30d1b-118">Pixel Shader 3 Support</span></span>  
  
     <span data-ttu-id="30d1b-119">WPF 4 기반으로 구축 된 <xref:System.Windows.Media.Effects.ShaderEffect> 픽셀 셰이더 (PS) 버전 3.0 사용 하 여 효과 쓰는 응용 프로그램을 허용 하 여 WPF 3.5 s p 1에 도입 된 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-119">WPF 4 builds on top of the <xref:System.Windows.Media.Effects.ShaderEffect> support introduced in WPF 3.5 SP1 by allowing applications to write effects by using Pixel Shader (PS) version 3.0.</span></span> <span data-ttu-id="30d1b-120">PS 3.0 셰이더 모델은 PS 2.0보다 더 정교해졌으며 지원되는 하드웨어에 더 많은 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-120">The PS 3.0 shader model is more sophisticated than PS 2.0, which allows for even more effects on supported hardware.</span></span>  
  
-   <span data-ttu-id="30d1b-121">감속/가속 함수</span><span class="sxs-lookup"><span data-stu-id="30d1b-121">Easing Functions</span></span>  
  
     <span data-ttu-id="30d1b-122">감속/가속 함수를 사용하여 애니메이션을 개선하고 동작을 좀 더 강력히 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-122">You can enhance animations with easing functions, which give you additional control over the behavior of animations.</span></span> <span data-ttu-id="30d1b-123">예를 들어 적용할 수 있습니다는 <xref:System.Windows.Media.Animation.ElasticEase> 에 애니메이션을 애니메이션 조정할 수 있는 동작을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-123">For example, you can apply an <xref:System.Windows.Media.Animation.ElasticEase> to an animation to give the animation a springy behavior.</span></span> <span data-ttu-id="30d1b-124">자세한 내용은에서 감속/가속 형식을 참조 하십시오.는 <xref:System.Windows.Media.Animation> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-124">For more information, see the easing types in the <xref:System.Windows.Media.Animation> namespace.</span></span>  
  
<a name="graphics_and_rendering"></a>   
## <a name="graphics-and-rendering"></a><span data-ttu-id="30d1b-125">그래픽 및 렌더링</span><span class="sxs-lookup"><span data-stu-id="30d1b-125">Graphics and Rendering</span></span>  
 <span data-ttu-id="30d1b-126">WPF는 고품질의 2차원 그래픽을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-126">WPF includes support for high quality 2-D graphics.</span></span> <span data-ttu-id="30d1b-127">기능으로는 브러시, 기하 도형, 이미지, 도형 및 변환 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-127">The functionality includes brushes, geometries, images, shapes and transformations.</span></span> <span data-ttu-id="30d1b-128">자세한 내용은 [그래픽](../../../../docs/framework/wpf/graphics-multimedia/graphics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30d1b-128">For more information, see [Graphics](../../../../docs/framework/wpf/graphics-multimedia/graphics.md).</span></span> <span data-ttu-id="30d1b-129">그래픽 요소 렌더링에 따라는 <xref:System.Windows.Media.Visual> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-129">The rendering of graphical elements is based on the <xref:System.Windows.Media.Visual> class.</span></span> <span data-ttu-id="30d1b-130">화면의 시각적 개체 구조는 시각적 트리로 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-130">The structure of visual objects on the screen is described by the visual tree.</span></span> <span data-ttu-id="30d1b-131">자세한 내용은 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30d1b-131">For more information, see [WPF Graphics Rendering Overview](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).</span></span>  
  
### <a name="2-d-shapes"></a><span data-ttu-id="30d1b-132">2차원 도형</span><span class="sxs-lookup"><span data-stu-id="30d1b-132">2-D Shapes</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="30d1b-133">는 다음 그림에 표시된 사각형 및 타원과 같은 일반적인 벡터 기반의 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 도형 라이브러리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-133"> provides a library of commonly used, vector-drawn [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] shapes, such as rectangles and ellipses, which the following illustration shows.</span></span>  
  
 <span data-ttu-id="30d1b-134">![타원 및 사각형](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure4.PNG "WPFIntroFigure4")</span><span class="sxs-lookup"><span data-stu-id="30d1b-134">![Ellipses and rectangles](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure4.PNG "WPFIntroFigure4")</span></span>  
  
 <span data-ttu-id="30d1b-135">이러한 내장 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 도형은 단순히 도형이 아닙니다. 키보드 및 마우스 입력을 포함하는 가장 일반적인 컨트롤에서 기대하는 많은 기능을 구현하는 프로그래밍 가능 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-135">These intrinsic [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] shapes are not just shapes: they are programmable elements that implement many of the features that you expect from most common controls, which include keyboard and mouse input.</span></span> <span data-ttu-id="30d1b-136">다음 예제에서는 처리 하는 방법을 보여 줍니다.는 <xref:System.Windows.UIElement.MouseUp> 클릭 하 여 발생 하는 이벤트는 <xref:System.Windows.Shapes.Ellipse> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-136">The following example shows how to handle the <xref:System.Windows.UIElement.MouseUp> event raised by clicking an <xref:System.Windows.Shapes.Ellipse> element.</span></span>  
  
```xaml  
<Window  
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
  x:Class="Window1" >  
  <Ellipse Fill="LightBlue" MouseUp="ellipseButton_MouseUp" />  
</Window>  
```  
  
```csharp  
public partial class Window1  : Window  
{  
    void ellipseButton_MouseUp(object sender, MouseButtonEventArgs e)  
    {  
        MessageBox.Show("You clicked the ellipse!");  
    }  
}  
```  
  
```vb  
Partial Public Class Window1  
    Inherits Window  
    Private Sub ellipseButton_MouseUp(ByVal sender As Object, ByVal e As MouseButtonEventArgs)  
        MessageBox.Show("You clicked the ellipse!")  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="30d1b-137">다음 그림에서는 이전 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 및 코드 숨김에 대한 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-137">The following illustration shows the output for the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind.</span></span>  
  
 <span data-ttu-id="30d1b-138">!["you clicked the ellipse&#33;" 텍스트가 있는 창](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure12.png "WPFIntroFigure12")</span><span class="sxs-lookup"><span data-stu-id="30d1b-138">![A window with the text "you clicked the ellipse&#33;"](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure12.png "WPFIntroFigure12")</span></span>  
  
 <span data-ttu-id="30d1b-139">자세한 내용은 [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30d1b-139">For more information, see [Shapes and Basic Drawing in WPF Overview](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md).</span></span> <span data-ttu-id="30d1b-140">기본 샘플을 보려면 [도형 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30d1b-140">For an introductory sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
### <a name="2-d-geometries"></a><span data-ttu-id="30d1b-141">2차원 기하 도형</span><span class="sxs-lookup"><span data-stu-id="30d1b-141">2-D Geometries</span></span>  
 <span data-ttu-id="30d1b-142">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 제공하는 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 도형으로 충분하지 않을 경우 기하 도형 및 경로에 대한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 지원을 사용하여 도형을 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-142">When the [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] shapes that [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides are not sufficient, you can use [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] support for geometries and paths to create your own.</span></span> <span data-ttu-id="30d1b-143">다음 그림에서는 기하 도형을 그리기 브러시로 사용하여 도형을 만들고 다른 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 요소를 클리핑하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-143">The following illustration shows how you can use geometries to create shapes, as a drawing brush, and to clip other [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] elements.</span></span>  
  
 <span data-ttu-id="30d1b-144">![Path의 다양한 용도](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure5.PNG "WPFIntroFigure5")</span><span class="sxs-lookup"><span data-stu-id="30d1b-144">![Various uses of a Path](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure5.PNG "WPFIntroFigure5")</span></span>  
  
 <span data-ttu-id="30d1b-145">자세한 내용은 [기하 도형 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30d1b-145">For more information, see [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span> <span data-ttu-id="30d1b-146">기본 샘플을 보려면 [기하 도형 샘플](http://go.microsoft.com/fwlink/?LinkID=159989)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30d1b-146">For an introductory sample, see [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
### <a name="2-d-effects"></a><span data-ttu-id="30d1b-147">2차원 효과</span><span class="sxs-lookup"><span data-stu-id="30d1b-147">2-D Effects</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="30d1b-148">에서는 다양한 효과 만드는 데 사용할 수 있는 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 클래스 라이브러리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-148"> provides a library of [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] classes that you can use to create a variety of effects.</span></span> <span data-ttu-id="30d1b-149">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 렌더링 기능은 그라데이션, 비트맵, 그림 및 비디오가 있는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소를 그리고 회전, 크기 조정 및 기울이기를 사용하여 조작하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-149">The [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] rendering capability of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] provides the ability to paint [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements that have gradients, bitmaps, drawings, and videos; and to manipulate them by using rotation, scaling, and skewing.</span></span> <span data-ttu-id="30d1b-150">다음 그림에서는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 브러시를 사용하여 획득할 수 있는 많은 효과의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-150">The following illustration gives an example of the many effects you can achieve by using [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] brushes.</span></span>  
  
 <span data-ttu-id="30d1b-151">![여러 브러시의 설명](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure6.PNG "WPFIntroFigure6")</span><span class="sxs-lookup"><span data-stu-id="30d1b-151">![Illustration of different brushes](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure6.PNG "WPFIntroFigure6")</span></span>  
  
 <span data-ttu-id="30d1b-152">자세한 내용은 [WPF 브러시 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30d1b-152">For more information, see [WPF Brushes Overview](../../../../docs/framework/wpf/graphics-multimedia/wpf-brushes-overview.md).</span></span> <span data-ttu-id="30d1b-153">기본 샘플을 보려면 [브러시 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30d1b-153">For an introductory sample, see [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
<a name="rendering"></a>   
## <a name="3-d-rendering"></a><span data-ttu-id="30d1b-154">3차원 렌더링</span><span class="sxs-lookup"><span data-stu-id="30d1b-154">3-D Rendering</span></span>  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="30d1b-155">에서는 더 흥미로운 레이아웃, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 및 데이터 시각화를 만들 수 있도록 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 그래픽 지원을 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에 통합하는 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 렌더링 기능 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-155"> provides a set of [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] rendering capabilities that integrate with [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] graphics support in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] in order for you to create more exciting layout, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], and data visualization.</span></span> <span data-ttu-id="30d1b-156">다음 그림과 같이 스펙트럼의 한쪽 끝에서 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 사용하여 [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] 이미지를 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 도형 표면 위에 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-156">At one end of the spectrum, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enables you to render [!INCLUDE[TLA2#tla_2d](../../../../includes/tla2sharptla-2d-md.md)] images onto the surfaces of [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] shapes, which the following illustration demonstrates.</span></span>  
  
 <span data-ttu-id="30d1b-157">![Visual3D 샘플 스크린샷](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure13.png "WPFIntroFigure13")</span><span class="sxs-lookup"><span data-stu-id="30d1b-157">![Visual3D sample screen shot](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure13.png "WPFIntroFigure13")</span></span>  
  
 <span data-ttu-id="30d1b-158">자세한 내용은 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30d1b-158">For more information, see [3-D Graphics Overview](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md).</span></span> <span data-ttu-id="30d1b-159">기본 샘플을 보려면 [3차원 단색 샘플](http://go.microsoft.com/fwlink/?LinkID=159964)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30d1b-159">For an introductory sample, see [3-D Solids Sample](http://go.microsoft.com/fwlink/?LinkID=159964).</span></span>  
  
<a name="animation"></a>   
## <a name="animation"></a><span data-ttu-id="30d1b-160">애니메이션</span><span class="sxs-lookup"><span data-stu-id="30d1b-160">Animation</span></span>  
 <span data-ttu-id="30d1b-161">애니메이션으로 컨트롤 및 요소가 커지거나, 흔들리거나, 회전하거나, 사라지도록 하여 흥미로운 페이지 전환 등을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-161">Use animation to make controls and elements grow, shake, spin, and fade; and to create interesting page transitions, and more.</span></span> <span data-ttu-id="30d1b-162">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 대부분의 속성에 애니메이션 효과를 줄 수 있을 뿐 아니라 대부분의 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 개체에도 애니메이션 효과를 줄 수 있으므로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 사용하여 만든 사용자 지정 개체에 애니메이션 효과를 줄 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-162">Because [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] enables you to animate most properties, not only can you animate most [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] objects, you can also use [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] to animate custom objects that you create.</span></span>  
  
 <span data-ttu-id="30d1b-163">![애니메이션 효과가 적용된 큐브의 이미지](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure7.png "WPFIntroFigure7")</span><span class="sxs-lookup"><span data-stu-id="30d1b-163">![Images of an animated cube](../../../../docs/framework/wpf/graphics-multimedia/media/wpfintrofigure7.png "WPFIntroFigure7")</span></span>  
  
 <span data-ttu-id="30d1b-164">자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30d1b-164">For more information, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="30d1b-165">기본 샘플을 보려면 [애니메이션 예제 갤러리](http://go.microsoft.com/fwlink/?LinkID=159969)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30d1b-165">For an introductory sample, see [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
<a name="media"></a>   
## <a name="media"></a><span data-ttu-id="30d1b-166">미디어</span><span class="sxs-lookup"><span data-stu-id="30d1b-166">Media</span></span>  
 <span data-ttu-id="30d1b-167">이미지, 비디오 및 오디오는 미디어를 통해 정보 및 사용자 환경을 전달하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-167">Images, video, and audio are media-rich ways of conveying information and user experiences.</span></span>  
  
### <a name="images"></a><span data-ttu-id="30d1b-168">이미지</span><span class="sxs-lookup"><span data-stu-id="30d1b-168">Images</span></span>  
 <span data-ttu-id="30d1b-169">아이콘, 배경 및 애니메이션 일부를 포함하는 이미지는 대부분의 응용 프로그램에서 핵심적인 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-169">Images, which include icons, backgrounds, and even parts of animations, are a core part of most applications.</span></span> <span data-ttu-id="30d1b-170">이미지를 자주 사용해야 하므로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 여러 가지 방법으로 이미지로 작업하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-170">Because you frequently need to use images, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] exposes the ability to work with them in a variety of ways.</span></span> <span data-ttu-id="30d1b-171">다음 그림에서는 해당 방법 중 하나만 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-171">The following illustration shows just one of those ways.</span></span>  
  
 <span data-ttu-id="30d1b-172">![스타일 샘플 스크린샷](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span><span class="sxs-lookup"><span data-stu-id="30d1b-172">![Styling sample screen shot](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")</span></span>  
  
 <span data-ttu-id="30d1b-173">자세한 내용은 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30d1b-173">For more information, see [Imaging Overview](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md).</span></span>  
  
### <a name="video-and-audio"></a><span data-ttu-id="30d1b-174">비디오 및 오디오</span><span class="sxs-lookup"><span data-stu-id="30d1b-174">Video and Audio</span></span>  
 <span data-ttu-id="30d1b-175">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 제공하는 그래픽 기능 중 핵심 기능은 비디오 및 오디오를 포함하는 멀티미디어로 작업할 수 있도록 지원하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-175">A core feature of the graphics capabilities of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] is to provide native support for working with multimedia, which includes video and audio.</span></span> <span data-ttu-id="30d1b-176">다음 예제에서는 미디어 플레이어를 응용 프로그램에 삽입하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-176">The following example shows how to insert a media player into an application.</span></span>  
  
```xaml  
<MediaElement Source="media\numbers.wmv" Width="450" Height="250" />  
```  
  
 <span data-ttu-id="30d1b-177"><xref:System.Windows.Controls.MediaElement>비디오와 오디오를 재생할 수 이며 사용자 지정은 쉽게 만들 수 있도록 충분히 확장 가능 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="30d1b-177"><xref:System.Windows.Controls.MediaElement> is capable of playing both video and audio, and is extensible enough to allow the easy creation of custom [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)].</span></span>  
  
 <span data-ttu-id="30d1b-178">자세한 내용은 [멀티미디어 개요](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30d1b-178">For more information, see the [Multimedia Overview](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30d1b-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30d1b-179">See Also</span></span>  
 <xref:System.Windows.Media>  
 <xref:System.Windows.Media.Animation>  
 <xref:System.Windows.Media.Media3D>  
 [<span data-ttu-id="30d1b-180">2차원 그래픽 및 이미징</span><span class="sxs-lookup"><span data-stu-id="30d1b-180">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [<span data-ttu-id="30d1b-181">WPF에서 Shape 및 기본 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="30d1b-181">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [<span data-ttu-id="30d1b-182">단색 및 그라데이션을 사용한 그리기 개요</span><span class="sxs-lookup"><span data-stu-id="30d1b-182">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="30d1b-183">이미지, 그림 및 시각적 표시로 그리기</span><span class="sxs-lookup"><span data-stu-id="30d1b-183">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [<span data-ttu-id="30d1b-184">애니메이션 및 타이밍</span><span class="sxs-lookup"><span data-stu-id="30d1b-184">Animation and Timing</span></span>](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="30d1b-185">3 차원 그래픽</span><span class="sxs-lookup"><span data-stu-id="30d1b-185">3-D Graphics</span></span>](http://msdn.microsoft.com/library/565c1f3c-235b-47de-b05b-3b53ed63f1b8)  
 [<span data-ttu-id="30d1b-186">멀티미디어</span><span class="sxs-lookup"><span data-stu-id="30d1b-186">Multimedia</span></span>](http://msdn.microsoft.com/library/44a8dcd0-80cb-4db0-a222-87cde68c2fac)
