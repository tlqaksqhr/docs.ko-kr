---
title: "경로 애니메이션 개요"
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
- animation [WPF], paths
- path animations [WPF]
ms.assetid: 979c732c-df74-47a6-be96-8e07b3707d53
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 237dbe83fa52bb967d2f2429fb2beb021c084f23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="path-animations-overview"></a>경로 애니메이션 개요
<a name="introduction"></a> 이 항목에서는 기하학적 경로를 사용하여 출력 값을 생성할 수 있도록 하는 경로 애니메이션을 소개합니다. 경로 애니메이션은 복잡한 경로를 따라 개체를 이동하고 회전하는 데 유용합니다.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>필수 구성 요소  
 이 항목을 이해 하려면에 대해 잘 알고 있어야 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션 기능입니다. 애니메이션 기능에 대 한 소개를 참조 하십시오.는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)합니다.  
  
 사용 하기 때문에 <xref:System.Windows.Media.PathGeometry> 경로 애니메이션을 정의 하는 개체에 잘 알고 있어야도 <xref:System.Windows.Media.PathGeometry> 및 다양 한 유형의 <xref:System.Windows.Media.PathSegment> 개체입니다. 자세한 내용은 참조는 [기 하 도형 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)합니다.  
  
<a name="what_is_a_path_animation"></a>   
## <a name="what-is-a-path-animation"></a>경로 애니메이션이란?  
 경로 애니메이션의 형식인 <xref:System.Windows.Media.Animation.AnimationTimeline> 를 사용 하는 <xref:System.Windows.Media.PathGeometry> 입력으로 합니다. From, To, 설정 하는 대신 또는 속성에 의해 (From/하/By의 경우와 마찬가지로 애니메이션) 사용 하 여 키 프레임 (키 프레임 애니메이션에 대 한 사용) 또는, 기하학적 경로 정의 하 고 설정 하는 데 사용할는 `PathGeometry` 경로 애니메이션의 속성입니다. 경로 애니메이션은 진행되면서 경로에서 x, y 및 각도 정보를 읽고 해당 정보로 출력을 생성합니다.  
  
 경로 애니메이션은 복잡한 경로를 따라 개체에 애니메이션 효과를 주는 데 매우 유용합니다. 경로 따라 개체를 사용 하는 것을 이동 하는 한 가지 방법은 <xref:System.Windows.Media.MatrixTransform> 및 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 복잡 한 경로 따라 개체를 변환 합니다. 다음 예제를 사용 하 여이 기술을 보여 줍니다.는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 애니메이션 효과를 줄 개체는 <xref:System.Windows.Media.MatrixTransform.Matrix%2A> 속성은 <xref:System.Windows.Media.MatrixTransform>합니다. <xref:System.Windows.Media.MatrixTransform> 곡선된 경로 따라 이동으로 인해 및 단추에 적용 됩니다. 때문에 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 속성이 `true`, 사각형 경로의 탄젠트를 따라 회전 합니다.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 사용 되는 경로 구문에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제에서는 참조는 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) 개요입니다. 전체 샘플을 참조 하십시오. [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)합니다.  
  
 사용 하 여 속성 경로 애니메이션을 적용할 수 있습니다는 <xref:System.Windows.Media.Animation.Storyboard> 에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 코드, 또는 사용 하 여는 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 코드에서 메서드. 만들려는 경로 애니메이션을 사용할 수도 있습니다는 <xref:System.Windows.Media.Animation.AnimationClock> 하나 이상의 속성에 적용 합니다. 애니메이션을 적용 하기 위한 여러 가지 방법에 대 한 자세한 내용은 참조 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)합니다.  
  
<a name="animation_types"></a>   
## <a name="path-animation-types"></a>경로 애니메이션 형식  
 애니메이션은 속성 값을 생성하므로 속성 형식이 다르면 애니메이션 형식도 다릅니다. 사용 하는 속성에 애니메이션 효과를 줄는 <xref:System.Double> (같은 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성의는 <xref:System.Windows.Media.TranslateTransform>), 생성 하는 애니메이션을 사용 하 여 <xref:System.Double> 값. 사용 하는 속성에 애니메이션 효과를 주는 <xref:System.Windows.Point>를 생성 하는 애니메이션을 사용 하 여 <xref:System.Windows.Point> 값, 및 기타 등등.  
  
 애니메이션 클래스 경로에 속한는 <xref:System.Windows.Media.Animation> 네임 스페이스는 다음 명명 규칙을 사용 하 여:  
  
 *\<Type>* `AnimationUsingPath`  
  
 여기서 *\<Type>*은 클래스가 애니메이션을 적용하는 값의 형식입니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 다음 경로 애니메이션 클래스를 제공합니다.  
  
|속성 형식|해당 경로 애니메이션 클래스|예제|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[경로를 따라 개체에 애니메이션 효과 주기(Double 애니메이션)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[경로를 따라 개체에 애니메이션 효과 주기(Matrix 애니메이션)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[경로를 따라 개체에 애니메이션 효과 주기(포인트 애니메이션)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 A <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 생성 <xref:System.Windows.Media.Matrix> 에서 값을 해당 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>합니다. 와 함께 사용할 경우 한 <xref:System.Windows.Media.MatrixTransform>, <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 경로 따라 개체를 이동할 수 있습니다. 설정 하는 경우는 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 의 속성은 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 를 `true`, 경로 곡선에 따라 개체 회전 합니다.  
  
 A <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 생성 <xref:System.Windows.Point> 값에서 x 및 y-좌표의 해당 <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>합니다. 사용 하 여 한 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 사용 하는 속성에 애니메이션 효과를 주는 <xref:System.Windows.Point> 값, 경로 따라 개체를 이동할 수 있습니다. A <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 개체 회전할 수 없습니다.  
  
 A <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 생성 <xref:System.Double> 에서 값을 해당 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>합니다. 설정 하 여는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> 속성을 지정할 수 있습니다 여부는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 출력으로 x-좌표, y-좌표 또는 경로의 각도 사용 합니다. 사용할 수는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 개체 회전 하거나 x 축 또는 y 축을 따라 이동 합니다.  
  
<a name="pathanimationinput"></a>   
## <a name="path-animation-input"></a>경로 애니메이션 입력  
 각 경로 애니메이션 클래스를 제공는 <xref:System.Windows.Media.PathGeometry> 속성에는 입력을 지정 합니다. 경로 애니메이션이 사용 하 여는 <xref:System.Windows.Media.PathGeometry> 해당 출력 값을 생성 합니다. <xref:System.Windows.Media.PathGeometry> 클래스를 사용 하면 여러 복잡 한 그림 원호, 곡선 및 선 대 한 구성에 대해 설명 합니다.  
  
 핵심에는 <xref:System.Windows.Media.PathGeometry> 의 컬렉션인 <xref:System.Windows.Media.PathFigure> 이러한 개체는 개체가 각 그림에서 개별 도형을 설명 하기 때문에 그렇게 명명 된는 <xref:System.Windows.Media.PathGeometry>합니다. 각 <xref:System.Windows.Media.PathFigure> 하나 이상의 구성 <xref:System.Windows.Media.PathSegment> 그림의 세그먼트를 설명 하는 각 개체입니다.  
  
 세그먼트 형식은 다양합니다.  
  
|세그먼트 형식|설명|  
|------------------|-----------------|  
|<xref:System.Windows.Media.ArcSegment>|두 점 사이에 타원형 호를 만듭니다.|  
|<xref:System.Windows.Media.BezierSegment>|두 점 사이에 입방형 3차원 곡선을 만듭니다.|  
|<xref:System.Windows.Media.LineSegment>|두 점 사이에 선을 만듭니다.|  
|<xref:System.Windows.Media.PolyBezierSegment>|일련의 입방형 3차원 곡선을 만듭니다.|  
|<xref:System.Windows.Media.PolyLineSegment>|일련의 줄을 만듭니다.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|일련의 정방형 3차원 곡선을 만듭니다.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|정방형 3차원 곡선을 만듭니다.|  
  
 세그먼트에는 <xref:System.Windows.Media.PathFigure> 단일 기하학 다각형 셰이프를 다음 세그먼트의 시작 점으로 한 세그먼트의 끝점을 사용 하 여 결합 됩니다. <xref:System.Windows.Media.PathFigure.StartPoint%2A> 속성은 <xref:System.Windows.Media.PathFigure> 첫 번째 세그먼트를 그리기 시간을 지정 합니다. 각 후속 세그먼트는 이전 세그먼트의 끝점에서 시작합니다. 예를 들어 세로 선이 `10,50` 를 `10,150` 설정 하 여 정의할 수 있습니다는 <xref:System.Windows.Media.PathFigure.StartPoint%2A> 속성을 `10,50` 및 만들기는 <xref:System.Windows.Media.LineSegment> 와 <xref:System.Windows.Media.LineSegment.Point%2A> 의 속성 설정 `10,150`합니다.  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Media.PathGeometry> 개체 참조는 [기 하 도형 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)합니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 설정 하려면 특별 한 약식된 구문을 사용할 수도 있습니다는 <xref:System.Windows.Media.PathGeometry.Figures%2A> 속성은 <xref:System.Windows.Media.PathGeometry>합니다. 자세한 내용은 참조 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) 개요입니다.  
  
 사용 되는 경로 구문에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제에서는 참조는 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) 개요입니다.  
  
## <a name="see-also"></a>참고 항목  
 [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)  
 [경로 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
