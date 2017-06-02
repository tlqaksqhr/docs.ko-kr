---
title: "성능 최적화: 2차원 그래픽 및 이미징 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "2차원 그래픽"
  - "그리기, 성능 최적화"
  - "그래픽, 성능"
  - "이미지, 성능 최적화"
  - "이미징, 성능 최적화"
  - "도형, 성능 최적화"
ms.assetid: e335601e-28c8-4d64-ba27-778fffd55f72
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 성능 최적화: 2차원 그래픽 및 이미징
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 응용 프로그램 요구 사항에 맞게 최적화할 수 있는 광범위한 2차원 그래픽 및 이미징 기능을 제공합니다.  이 항목에서는 이러한 영역에서의 성능 최적화에 대한 정보를 제공합니다.  
  
   
  
<a name="Drawing_and_Shapes"></a>   
## 그리기 및 도형  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 그래픽 그리기 콘텐츠를 나타내기 위해 <xref:System.Windows.Media.Drawing> 및 <xref:System.Windows.Shapes.Shape> 개체를 모두 제공합니다.  그러나 <xref:System.Windows.Media.Drawing> 개체는 <xref:System.Windows.Shapes.Shape> 개체보다 간단한 구문이며 더 나은 성능 특성을 제공합니다.  
  
 <xref:System.Windows.Shapes.Shape>를 사용하면 그래픽 도형을 화면에 그릴 수 있습니다.  <xref:System.Windows.Shapes.Shape> 개체는 <xref:System.Windows.FrameworkElement> 클래스에서 파생되므로 패널 및 대부분의 컨트롤 내에 사용될 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 그래픽 및 렌더링 서비스에 대한 여러 계층의 액세스를 제공합니다.  최상위 계층에서 <xref:System.Windows.Shapes.Shape> 개체는 사용이 간편하고 레이아웃 및 이벤트 처리와 같은 많은 유용한 기능을 제공합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 바로 사용할 수 있는 여러 Shape 개체를 제공합니다.  모든 Shape 개체는 <xref:System.Windows.Shapes.Shape> 클래스에서 상속됩니다.  사용 가능한 Shape 개체에는 <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline> 및 <xref:System.Windows.Shapes.Rectangle>이 있습니다.  
  
 반면에 <xref:System.Windows.Media.Drawing> 개체는 <xref:System.Windows.FrameworkElement> 클래스에서 파생되지 않으며 도형, 이미지 및 텍스트를 렌더링하기 위한 보다 가벼운 구현을 제공합니다.  
  
 다음과 같은 네 가지 형식의 <xref:System.Windows.Media.Drawing> 개체가 있습니다.  
  
-   <xref:System.Windows.Media.GeometryDrawing> \- 도형을 그립니다.  
  
-   <xref:System.Windows.Media.ImageDrawing> \- 이미지를 그립니다.  
  
-   <xref:System.Windows.Media.GlyphRunDrawing> \- 텍스트를 그립니다.  
  
-   <xref:System.Windows.Media.DrawingGroup> \- 다른 그리기를 그립니다.  다른 그리기를 단일 합성 그리기로 결합하려면 그리기 그룹을 사용합니다.  
  
 <xref:System.Windows.Media.GeometryDrawing> 개체는 기하 도형 콘텐츠를 렌더링하는 데 사용됩니다.  <xref:System.Windows.Media.Geometry> 클래스 및 이 클래스에서 파생되는 구체적인 클래스\(예: <xref:System.Windows.Media.CombinedGeometry>, <xref:System.Windows.Media.EllipseGeometry> 및 <xref:System.Windows.Media.PathGeometry>\)는 2차원 그래픽을 렌더링하는 방식뿐만 아니라 적중 테스트 및 클리핑 지원을 제공합니다.  Geometry 개체를 사용하면 컨트롤 영역을 정의하거나 이미지에 적용할 클립 영역을 정의하는 등의 작업을 수행할 수 있습니다.  Geometry 개체는 사각형 및 원과 같은 단순 영역 또는 둘 이상의 Geometry 개체에서 만들어진 복합 영역이 될 수 있습니다.  더 복잡한 기하 도형 영역은 <xref:System.Windows.Media.ArcSegment>, <xref:System.Windows.Media.BezierSegment> 및 <xref:System.Windows.Media.QuadraticBezierSegment>와 같은 <xref:System.Windows.Media.PathSegment> 파생 개체를 결합하여 만들 수 있습니다.  
  
 겉으로 보기에 <xref:System.Windows.Media.Geometry> 클래스와 <xref:System.Windows.Shapes.Shape> 클래스는 매우 비슷합니다.  둘 다 2차원 그래픽을 렌더링하는 데 사용되고 해당 클래스에서 파생되는 유사한 구체적인 클래스\(예: <xref:System.Windows.Media.EllipseGeometry> 및 <xref:System.Windows.Shapes.Ellipse>\)를 가집니다.  그러나 두 클래스 집합 사이에는 중요한 차이점이 존재합니다.  예를 들어 자신을 그리는 기능과 같은 <xref:System.Windows.Shapes.Shape> 클래스의 일부 기능이 <xref:System.Windows.Media.Geometry> 클래스에는 없습니다.  Geometry 개체를 그리려면 DrawingContext, Drawing 또는 Path\(Path가 Shape라는 것에 주의\)와 같은 또 다른 클래스를 사용하여 그리기 작업을 수행해야 합니다.  채우기, 스트로크 및 스트로크 두께와 같은 렌더링 속성이 Geometry 개체를 그리는 클래스에서 있는 반면에 Shape 개체는 이러한 속성을 포함합니다.  이 차이를 보여 주는 한 가지 예로, Geometry 개체는 원과 같은 영역을 정의하는 반면에 Shape 개체는 영역을 정의하고 영역 채우기 및 윤곽선 그리기 방법을 정의하며 레이아웃 시스템에 참여할 수 있습니다.  
  
 <xref:System.Windows.Shapes.Shape> 개체가 <xref:System.Windows.FrameworkElement> 클래스에서 파생되므로 이러한 개체를 사용하면 응용 프로그램에서 메모리 사용량이 크게 증가할 수 있습니다.  그래픽 콘텐츠에 <xref:System.Windows.FrameworkElement> 기능이 실제로 필요하지 않은 경우 보다 간단한 <xref:System.Windows.Media.Drawing> 개체를 사용해 보십시오.  
  
 <xref:System.Windows.Media.Drawing> 개체에 대한 자세한 내용은 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)를 참조하십시오.  
  
<a name="StreamGeometry_Objects"></a>   
## StreamGeometry 개체  
 <xref:System.Windows.Media.StreamGeometry> 개체는 기하 도형을 만들기 위해 <xref:System.Windows.Media.PathGeometry> 대신 사용할 수 있는 간단한 개체입니다.  복잡한 기하 도형을 설명해야 할 경우 <xref:System.Windows.Media.StreamGeometry>를 사용합니다.  <xref:System.Windows.Media.StreamGeometry>는 많은 <xref:System.Windows.Media.PathGeometry> 개체를 처리는 데 최적화되었으며 여러 개별 <xref:System.Windows.Media.PathGeometry> 개체를 처리할 때와 비교하여 보다 나은 성능을 제공합니다.  
  
 다음 예제에서는 특성 구문을 사용하여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 삼각형 <xref:System.Windows.Media.StreamGeometry>를 만듭니다.  
  
 [!code-xml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 <xref:System.Windows.Media.StreamGeometry> 개체에 대한 자세한 내용은 [StreamGeometry를 사용하여 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md)를 참조하십시오.  
  
<a name="DrawingVisual_Objects"></a>   
## DrawingVisual 개체  
 <xref:System.Windows.Media.DrawingVisual> 개체는 도형, 이미지 또는 텍스트를 렌더링하는 데 사용되는 간단한 그리기 클래스입니다.  이 클래스는 성능을 향상시키는 레이아웃이나 이벤트 처리를 제공하지 않으므로 간단한 클래스로 간주됩니다.  이러한 이유 때문에 그리기는 배경 및 클립 아트에 적합합니다.  자세한 내용은 [DrawingVisual 개체 사용](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)을 참조하십시오.  
  
<a name="Images"></a>   
## 이미지  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이미징은 이전 버전의 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]보다 크게 향상된 이미징 기능을 제공합니다.  비트맵을 표시하거나 공용 컨트롤에 이미지를 사용하는 등의 이미징 기능은 이전에 주로 Microsoft Windows GDI\(그래픽 장치 인터페이스\) 또는 Microsoft Windows GDI\+ API\(응용 프로그래밍 인터페이스\)에 의해 처리되었습니다.  이러한 API는 기준 이미징 기능은 제공했지만 코덱 확장성 및 고품질 이미지 지원 등과 같은 기능이 없었습니다.  WPF 이미징 API는 GDI 및 GDI\+의 단점을 극복하고 응용 프로그램 내에서 이미지를 표시 및 사용하기 위한 새로운 APO 집합을 제공하도록 다시 디자인되었습니다.  
  
 이미지를 사용할 경우 더 나은 성능을 얻기 위한 다음 권장 사항을 고려하십시오.  
  
-   응용 프로그램에서 축소판 이미지로 표시해야 할 경우 크기를 줄인 버전의 이미지를 만드십시오.  기본적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 이미지를 로드하여 전체 크기로 디코딩합니다.  축소판 버전의 이미지만 필요한 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 이미지를 전체 크기로 디코딩한 다음 축소판 크기로 배율 조정하는 것은 불필요할 작업입니다.  이러한 불필요한 오버헤드를 방지하려면 이미지를 축소판 크기로 디코딩하도록 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 요청하거나 축소판 크기 이미지를 로드하도록 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 요청하면 됩니다.  
  
-   이미지를 항상 기본 크기가 아니라 원하는 크기로 디코딩하십시오.  위에 언급한 것처럼 이미지를 기본 전체 크기가 아니라 원하는 크기로 디코딩하도록 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 요청합니다.  이렇게 하면 응용 프로그램의 작업이 줄어들 뿐만 아니라 실행 속도가 빨라집니다.  
  
-   가능한 경우 이미지를 여러 이미지로 연결된 영사 슬라이드와 같은 단일 이미지로 결합합니다.  
  
-   자세한 내용은 [이미징 개요](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)를 참조하십시오.  
  
### BitmapScalingMode  
 비트맵의 배율에 애니메이션 효과를 주면 기본 고품질 이미지 다시 만들기 알고리즘에 시스템 리소스가 많이 사용되므로 프레임 속도가 떨어지고 애니메이션이 끊길 수 있습니다.  <xref:System.Windows.Media.RenderOptions> 개체의 <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> 속성을 <xref:System.Windows.Media.BitmapScalingMode>로 설정하면 비트맵의 배율을 조정할 때 보다 부드러운 애니메이션을 만들 수 있습니다.  <xref:System.Windows.Media.BitmapScalingMode> 모드는 이미지를 처리할 때 품질 최적화 알고리즘에서 속도 최적화 알고리즘으로 전환하도록 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 렌더링 엔진에 지시합니다.  
  
 다음 예제에서는 Image 개체에 대한 <xref:System.Windows.Media.BitmapScalingMode>를 설정하는 방법을 보여 줍니다.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### CachingHint  
 기본적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 <xref:System.Windows.Media.DrawingBrush> 및 <xref:System.Windows.Media.VisualBrush>와 같은 <xref:System.Windows.Media.TileBrush> 개체의 렌더링된 콘텐츠를 캐시하지 않습니다.  화면에서 <xref:System.Windows.Media.TileBrush>의 내용이나 사용이 변경되지 않는 정적인 시나리오의 경우 이 방법은 비디오 메모리를 절약할 수 있기 때문에 유용합니다.  그러나 정적 <xref:System.Windows.Media.DrawingBrush>나 <xref:System.Windows.Media.VisualBrush>가 회전하는 3차원 개체 표면에 매핑되는 경우와 같이 정적 내용이 있는 <xref:System.Windows.Media.TileBrush>가 비정적 방법으로 사용되는 경우 이 방법은 유용하지 않습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 기본 동작은 콘텐츠가 변경되지 않는 경우에도 프레임마다 <xref:System.Windows.Media.DrawingBrush> 또는 <xref:System.Windows.Media.VisualBrush>의 전체 콘텐츠를 다시 렌더링하는 것입니다.  
  
 <xref:System.Windows.Media.RenderOptions> 개체의 <xref:System.Windows.Media.RenderOptions.CachingHint%2A> 속성을 <xref:System.Windows.Media.CachingHint>로 설정하면 바둑판식으로 배열된 Brush 개체의 캐시된 버전을 사용하여 성능을 향상시킬 수 있습니다.  
  
 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> 및 <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> 속성 값은 배율 변경에 따라 <xref:System.Windows.Media.TileBrush> 개체를 다시 생성할 시기를 결정하는 상대 크기 값입니다.  예를 들어, <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> 속성을 2.0으로 설정하면 <xref:System.Windows.Media.TileBrush>의 캐시는 해당 크기가 현재 캐시 크기의 두 배를 넘을 경우에만 다시 생성되어야 합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.DrawingBrush>에 대한 캐싱 힌트 옵션을 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## 참고 항목  
 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [응용 프로그램 성능 계획](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [하드웨어 이용](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [개체 동작](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [기타 성능 권장 사항](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)   
 [애니메이션에 대한 유용한 정보](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)