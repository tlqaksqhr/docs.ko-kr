---
title: "Geometry 개요 | Microsoft Docs"
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
  - "클래스, 기하 도형"
  - "CombinedGeometry 클래스"
  - "EllipseGeometry 클래스"
  - "기하 도형 클래스"
  - "그래픽, 기하 도형 클래스"
  - "LineGeometry 클래스"
  - "PathGeometry 클래스"
  - "RectangleGeometry 클래스"
ms.assetid: 9fba8934-98b7-4af6-82f6-f4ef887f963a
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Geometry 개요
이 개요에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Media.Geometry> 클래스를 사용하여 도형을 설명하는 방법에 대해 설명합니다.  이 항목에서는 <xref:System.Windows.Media.Geometry> 개체와 <xref:System.Windows.Shapes.Shape> 요소의 차이점도 비교합니다.  
  
   
  
<a name="wcpsdk_graphics_geometry_introduction"></a>   
## Geometry란?  
 <xref:System.Windows.Media.Geometry> 클래스와 이 클래스에서 파생되는 <xref:System.Windows.Media.EllipseGeometry>, <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.CombinedGeometry> 등의 클래스를 사용하면 2차원 도형의 기하 도형을 설명할 수 있습니다.  이러한 기하학적 설명은 도형을 정의하여 화면 그리기, 적중 테스트 및 클립 영역 정의 등의 여러 용도에 사용됩니다.  기하 도형을 사용하여 애니메이션 경로를 정의할 수도 있습니다.  
  
 <xref:System.Windows.Media.Geometry> 개체는 사각형 및 원과 같은 단순 영역이나 둘 이상의 기하 도형 개체로 이루어진 복합 영역일 수 있습니다.  원호와 곡선을 설명하는 데 사용할 수 있는 <xref:System.Windows.Media.PathGeometry> 및 <xref:System.Windows.Media.StreamGeometry> 클래스를 사용하여 보다 복잡한 복합 기하 도형을 만들 수 있습니다.  
  
 <xref:System.Windows.Media.Geometry>는 <xref:System.Windows.Freezable> 형식이므로 <xref:System.Windows.Media.Geometry> 개체는 몇 가지 특수한 기능을 제공합니다. 예를 들어 [리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)로 선언하거나, 여러 개체 간에 공유하거나, 읽기 전용으로 설정하여 성능을 향상할 수 있으며, 복제하거나, 스레드로부터 안전하게 보호할 수 있습니다.  <xref:System.Windows.Freezable> 개체에서 제공하는 여러 기능에 대한 자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
<a name="wcpsdk_graphics_geometry_geometryandshapes"></a>   
## Geometry 및Shape  
 <xref:System.Windows.Media.Geometry> 및 <xref:System.Windows.Shapes.Shape> 클래스는 모두 2차원 도형을 설명한다는 점에서 유사한 듯 보이지만\(예를 들어 <xref:System.Windows.Media.EllipseGeometry> 및 <xref:System.Windows.Shapes.Ellipse> 비교\) 중요한 차이점이 있습니다.  
  
 그 중 하나는 <xref:System.Windows.Media.Geometry> 클래스는 <xref:System.Windows.Freezable> 클래스에서 상속하는 반면 <xref:System.Windows.Shapes.Shape> 클래스는 <xref:System.Windows.FrameworkElement>에서 상속합니다.  <xref:System.Windows.Shapes.Shape> 개체는 요소이므로 자체를 렌더링하고 레이아웃 시스템에 참여할 수 있지만 <xref:System.Windows.Media.Geometry> 개체는 그럴 수 없습니다.  
  
 <xref:System.Windows.Shapes.Shape> 개체는 <xref:System.Windows.Media.Geometry> 개체보다 더 쉽게 사용할 수 있지만 <xref:System.Windows.Media.Geometry> 개체는 더욱 다양한 방식으로 사용할 수 있습니다.  <xref:System.Windows.Shapes.Shape> 개체는 2차원 그래픽을 렌더링하는 데 사용되는 반면 <xref:System.Windows.Media.Geometry> 개체는 2차원 그래픽의 기하학적 영역을 정의하거나, 클리핑 영역을 정의하거나, 적중 회수 테스트 영역을 정의하는 등에 사용할 수 있습니다.  
  
### 경로 도형  
 하나의 <xref:System.Windows.Shapes.Shape>인 <xref:System.Windows.Shapes.Path> 클래스에서는 실제로 <xref:System.Windows.Media.Geometry>를 사용하여 해당 콘텐츠를 설명합니다.   <xref:System.Windows.Media.Geometry>를 사용하여 <xref:System.Windows.Shapes.Path>의 <xref:System.Windows.Shapes.Path.Data%2A> 속성을 설정하고 해당 <xref:System.Windows.Shapes.Shape.Fill%2A> 및 <xref:System.Windows.Shapes.Shape.Stroke%2A> 속성을 설정하면 <xref:System.Windows.Media.Geometry>를 렌더링할 수 있습니다.  
  
<a name="commonproperties"></a>   
## Geometry를 사용하는 공용 속성  
 앞의 단원에서 설명한 바와 같이 다른 개체에서 도형 그리기, 애니메이션 효과 적용 및 클리핑과 같은 다양한 용도로 Geometry 개체를 사용할 수 있습니다.  다음 표에서는 <xref:System.Windows.Media.Geometry> 개체를 사용하는 속성이 있는 여러 클래스를 보여 줍니다.  
  
|형식|Property|  
|--------|--------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>|  
|<xref:System.Windows.Media.DrawingGroup>|<xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>|  
|<xref:System.Windows.Media.GeometryDrawing>|<xref:System.Windows.Media.GeometryDrawing.Geometry%2A>|  
|<xref:System.Windows.Shapes.Path>|<xref:System.Windows.Shapes.Path.Data%2A>|  
|<xref:System.Windows.UIElement>|<xref:System.Windows.UIElement.Clip%2A>|  
  
<a name="wcpsdk_graphics_geometry_geometrytypes"></a>   
## 단순한 기하 도형 형식  
 모든 기하 도형의 기본 클래스는 추상 클래스 <xref:System.Windows.Media.Geometry>입니다.  <xref:System.Windows.Media.Geometry> 클래스에서 파생되는 클래스는 대략 단순 기하 도형, 경로 기하 도형 및 복합 기하 도형의 세 가지 범주로 묶을 수 있습니다.  
  
 단순 기하 도형 클래스는 <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry> 및 <xref:System.Windows.Media.EllipseGeometry>를 포함하며 선, 사각형, 원과 같은 기본적인 기하학 도형을 만드는 데 사용됩니다.  
  
-   <xref:System.Windows.Media.LineGeometry>는 선의 시작점과 끝점을 지정하여 정의합니다.  
  
-   <xref:System.Windows.Media.RectangleGeometry>는 사각형의 상대적 위치와 높이 및 너비를 지정하는 <xref:System.Windows.Rect> 구조체를 사용하여 정의합니다.  <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> 및 <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A>속성을 설정하여 모퉁이가 둥근 사각형을 만들 수 있습니다.  
  
-   <xref:System.Windows.Media.EllipseGeometry>는 중심점, x 반지름 및 y 반지름으로 정의합니다.  다음 예제에서는 렌더링 및 클리핑하기 위한 단순 기하 도형을 만드는 방법을 보여 줍니다.  
  
 이와 같은 도형 및 보다 복잡한 도형을 <xref:System.Windows.Media.PathGeometry>를 사용하거나 기하 도형 개체를 결합하여 만들 수 있지만 이러한 클래스를 사용하면 이러한 기본적인 기하 도형을 더 간단하게 만들 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.LineGeometry>를 만들고 렌더링하는 방법을 보여 줍니다.  앞에서 설명한 대로 <xref:System.Windows.Media.Geometry> 개체는 자신을 그릴 수 없으므로 이 예제에서는 <xref:System.Windows.Shapes.Path> 도형을 사용하여 선을 렌더링합니다.  선에는 면적이 없으므로 <xref:System.Windows.Shapes.Path>의 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성을 설정해도 아무 영향이 없습니다. 대신 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성만 지정합니다.  다음 그림에서는 이 예제를 실행한 결과를 보여 줍니다.  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.png "graphicsmm\_line")  
\(10,20\)에서 \(100,130\) 사이에 그린 LineGeometry  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 다음 예제에서는 <xref:System.Windows.Media.EllipseGeometry>를 만들고 렌더링하는 방법을 보여 줍니다.  이 예제에서는 <xref:System.Windows.Media.EllipseGeometry>의 <xref:System.Windows.Media.EllipseGeometry.Center%2A>를 점 `50,50`으로 설정하고 x 반지름 및 y 반지름을 모두 `50`으로 설정하여 지름이 100인 원을 만듭니다.  Path 요소의 Fill 속성에 값\(여기서는 <xref:System.Windows.Media.Brushes.Gold%2A>\)을 할당하여 타원의 내부를 그립니다.  다음 그림에서는 이 예제를 실행한 결과를 보여 줍니다.  
  
 ![EllipseGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-ellipse.png "graphicsmm\_ellipse")  
\(50,50\)에 그린 EllipseGeometry  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmellipsegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmellipsegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMEllipseGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmellipsegeometryexample)]  
  
 다음 예제에서는 <xref:System.Windows.Media.RectangleGeometry>를 만들고 렌더링하는 방법을 보여 줍니다.  사각형의 위치와 치수는 <xref:System.Windows.Rect> 구조체를 사용하여 정의합니다.  위치는 `50,50`으로 지정하고 높이와 너비를 모두 `25`로 지정하여 정사각형을 만듭니다.  다음 그림에서는 이 예제를 실행한 결과를 보여 줍니다.  
  
 ![RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.png "graphicsmm\_rectangle")  
50,50에 그린 RectangleGeometry  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 다음 예제에서는 <xref:System.Windows.Media.EllipseGeometry>를 이미지의 클리핑 영역으로 사용하는 방법을 보여 줍니다.  <xref:System.Windows.FrameworkElement.Width%2A>를 200으로, <xref:System.Windows.FrameworkElement.Height%2A>를 150으로 지정하여 <xref:System.Windows.Controls.Image> 개체를 정의합니다.  <xref:System.Windows.Media.EllipseGeometry.RadiusX%2A> 값은 100, <xref:System.Windows.Media.EllipseGeometry.RadiusY%2A> 값은 75, <xref:System.Windows.Media.EllipseGeometry.Center%2A> 값은 100,75인 <xref:System.Windows.Media.EllipseGeometry>를 이미지의 <xref:System.Windows.UIElement.Clip%2A> 속성으로 설정합니다.  그러면 타원 영역 내에 있는 이미지 부분만 표시됩니다.  다음 그림에서는 이 예제를 실행한 결과를 보여 줍니다.  
  
 ![클리핑이 있는 이미지와 없는 이미지](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clipexample.png "graphicsmm\_clipexample")  
Image 컨트롤을 클리핑하는 데 사용된 EllipseGeometry  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmimageclipgeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmimageclipgeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMImageClipGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmimageclipgeometryexample)]  
  
<a name="wcpsdk_graphics_geometry_pathgeometry"></a>   
## 경로 기하 도형  
 <xref:System.Windows.Media.PathGeometry> 클래스 및 이에 해당하는 간단한 <xref:System.Windows.Media.StreamGeometry> 클래스는 원호, 곡선 및 선으로 구성된 여러 복잡한 그림을 설명할 수 있는 방법을 제공합니다.  
  
 <xref:System.Windows.Media.PathGeometry>의 핵심은 <xref:System.Windows.Media.PathFigure> 개체의 컬렉션입니다. 이와 같은 이름이 지정된 까닭은 각 그림이 <xref:System.Windows.Media.PathGeometry>에서 개별 도형을 설명하기 때문입니다.  각 <xref:System.Windows.Media.PathFigure> 자체는 각각 그림의 세그먼트를 설명하는 하나 이상의 <xref:System.Windows.Media.PathSegment> 개체로 구성됩니다.  
  
 세그먼트에는 여러 가지 형식이 있습니다.  
  
|세그먼트 형식|설명|예제|  
|-------------|--------|--------|  
|<xref:System.Windows.Media.ArcSegment>|두 점 사이에 타원형 원호를 만듭니다.|[타원형 원호 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md).|  
|<xref:System.Windows.Media.BezierSegment>|두 점 사이에 입방형 3차원 곡선을 만듭니다.|[입방형 3차원 곡선 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md).|  
|<xref:System.Windows.Media.LineSegment>|두 점 사이에 선을 만듭니다.|[PathGeometry에 LineSegment 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)|  
|<xref:System.Windows.Media.PolyBezierSegment>|일련의 입방형 3차원 곡선을 만듭니다.|<xref:System.Windows.Media.PolyBezierSegment> 형식 페이지를 참조하십시오.|  
|<xref:System.Windows.Media.PolyLineSegment>|일련의 선을 만듭니다.|<xref:System.Windows.Media.PolyLineSegment> 형식 페이지를 참조하십시오.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|일련의 정방형 3차원 곡선을 만듭니다.|<xref:System.Windows.Media.PolyQuadraticBezierSegment> 페이지를 참조하십시오.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|정방형 3차원 곡선을 만듭니다.|[정방형 3차원 곡선 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md).|  
  
 <xref:System.Windows.Media.PathFigure>의 세그먼트는 각 세그먼트의 끝점이 다음 세그먼트의 시작점이 되어 하나의 기하학적 도형으로 결합됩니다.  <xref:System.Windows.Media.PathFigure>의 <xref:System.Windows.Media.PathFigure.StartPoint%2A> 속성은 첫 번째 세그먼트가 그려지는 점을 지정합니다.  이후의 각 세그먼트는 이전 세그먼트의 끝점에서 시작됩니다.  예를 들어 `10,50`에서 `10,150`까지 이어지는 수직선을 정의하려면 <xref:System.Windows.Media.PathFigure.StartPoint%2A> 속성을 `10,50`으로 설정하고 <xref:System.Windows.Media.LineSegment.Point%2A> 속성이 `10,150`으로 설정된 <xref:System.Windows.Media.LineSegment>를 만듭니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.LineSegment>를 사용하여 단일 <xref:System.Windows.Media.PathFigure>로 구성되는 단순 <xref:System.Windows.Media.PathGeometry>를 만들고 <xref:System.Windows.Shapes.Path> 요소를 사용하여 이를 표시합니다.  <xref:System.Windows.Media.PathFigure> 개체의 <xref:System.Windows.Media.PathFigure.StartPoint%2A>를 `10,20`으로 설정하고 <xref:System.Windows.Media.LineSegment>를 끝점 `100,130`으로 정의합니다.  다음 그림에서는 이 예제에서 만든 <xref:System.Windows.Media.PathGeometry>를 보여 줍니다.  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.png "graphicsmm\_line")  
단일 LineSegment를 포함하는 PathGeometry  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrylineexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrylineexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryLineExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrylineexample)]  
  
 이 예제를 앞의 <xref:System.Windows.Media.LineGeometry> 예제와 비교해 보는 것이 좋습니다.  <xref:System.Windows.Media.PathGeometry>에 사용된 구문이 단순 <xref:System.Windows.Media.LineGeometry>에 사용된 구문보다 훨씬 자세하고 이 경우 <xref:System.Windows.Media.LineGeometry> 클래스를 사용하는 것이 실용적일 수 있지만 <xref:System.Windows.Media.PathGeometry>의 자세한 구문에서는 매우 상세하고 복잡한 기하학적 영역을 고려합니다.  
  
 더욱 복잡한 기하 도형은 <xref:System.Windows.Media.PathSegment> 개체를 조합하여 만들 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.BezierSegment>, <xref:System.Windows.Media.LineSegment> 및 <xref:System.Windows.Media.ArcSegment>를 사용하여 도형을 만듭니다.  이 예제에서는 먼저 이전 세그먼트의 끝점인 시작점, 끝점\(<xref:System.Windows.Media.BezierSegment.Point3%2A>\) 및 두 개의 제어점\(<xref:System.Windows.Media.BezierSegment.Point1%2A> 및 <xref:System.Windows.Media.BezierSegment.Point2%2A>\)의 네 점을 정의하여 입방형 3차원 곡선을 만듭니다.  입방형 3차원 곡선의 두 제어점은 자석과 같은 역할을 하여 직선이 될 수 있는 부분을 서로 끌어당겨 곡선을 만듭니다.  첫 번째 제어점인 <xref:System.Windows.Media.BezierSegment.Point1%2A>은 곡선의 시작 부분에 영향을 주고, 두 번째 제어점인 <xref:System.Windows.Media.BezierSegment.Point2%2A>는 곡선의 끝 부분에 영향을 줍니다.  
  
 이 예제에서는 그런 다음 앞에 있는 <xref:System.Windows.Media.BezierSegment>의 끝점과 <xref:System.Windows.Media.LineSegment> 속성으로 지정한 점 사이에 <xref:System.Windows.Media.LineSegment>를 그립니다.  
  
 이 예제에서는 그런 다음 앞에 있는 <xref:System.Windows.Media.LineSegment>의 끝점과 <xref:System.Windows.Media.ArcSegment.Point%2A> 속성으로 지정한 점 사이에 <xref:System.Windows.Media.ArcSegment>를 그립니다.  또한 이 예제에서는 원호의 x 및 y 반지름\(<xref:System.Windows.Media.ArcSegment.Size%2A>\), 회전 각도\(<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>\), 결과 원호의 각도 크기를 표시하는 플래그\(<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>\) 및 원호를 그리는 방향을 표시하는 값\(<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>\)을 지정합니다.  다음 그림에서는 이 예제에서 만든 도형을 보여 줍니다.  
  
 ![PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path2.png "graphicsmm\_path2")  
PathGeometry  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexexample)]  
  
 <xref:System.Windows.Media.PathGeometry> 내에 여러 <xref:System.Windows.Media.PathFigure> 개체를 사용하여 훨씬 더 복잡한 기하 도형을 만들 수 있습니다.  
  
 다음 예제에서는 각각 여러 <xref:System.Windows.Media.PathSegment> 개체를 포함하는 두 개의 <xref:System.Windows.Media.PathFigure> 개체를 사용하여 <xref:System.Windows.Media.PathGeometry>를 만듭니다.  위의 예제에 있는 <xref:System.Windows.Media.PathFigure>와 <xref:System.Windows.Media.PolyLineSegment> 및 <xref:System.Windows.Media.QuadraticBezierSegment>를 포함하는 <xref:System.Windows.Media.PathFigure>를 사용합니다.  <xref:System.Windows.Media.PolyLineSegment>는 점 배열로 정의하고 <xref:System.Windows.Media.QuadraticBezierSegment>는 제어점과 끝점으로 정의합니다.  다음 그림에서는 이 예제에서 만든 도형을 보여 줍니다.  
  
 ![PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-path.png "graphicsmm\_path")  
여러 그림을 포함하는 PathGeometry  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmpathgeometrycomplexmultiexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmpathgeometrycomplexmultiexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMPathGeometryComplexMultiExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmpathgeometrycomplexmultiexample)]  
  
### StreamGeometry  
 <xref:System.Windows.Media.PathGeometry> 클래스처럼 <xref:System.Windows.Media.StreamGeometry>는 곡선, 원호 및 선을 포함할 수 있는 복잡한 기하 도형을 정의합니다.  그러나 <xref:System.Windows.Media.PathGeometry>와 달리 <xref:System.Windows.Media.StreamGeometry>의 콘텐츠에서는 데이터 바인딩, 애니메이션 또는 수정을 지원하지 않습니다.  복잡한 기하 도형을 설명해야 하지만 데이터 바인딩, 애니메이션 및 수정에 대한 지원에 따른 오버헤드를 원하지 않는 경우 <xref:System.Windows.Media.StreamGeometry>를 사용합니다.  <xref:System.Windows.Media.StreamGeometry> 클래스는 효율성으로 인해 표시기\(adorner\)를 설명하기에 적합합니다.  
  
 예제를 보려면 [StreamGeometry를 사용하여 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md)를 참조하십시오.  
  
### 경로 태그 구문  
 <xref:System.Windows.Media.PathGeometry> 및 <xref:System.Windows.Media.StreamGeometry> 형식에서는 특수한 일련의 이동 및 그리기 명령을 사용하여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 특성 구문을 지원합니다.  자세한 내용은 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)을 참조하십시오.  
  
<a name="wcpsdk_graphics_geometry_introduction2"></a>   
## 복합 기하 도형  
 복합 기하 도형 개체는 <xref:System.Windows.Media.GeometryGroup> 및 <xref:System.Windows.Media.CombinedGeometry>를 사용하여 만들거나 정적 <xref:System.Windows.Media.Geometry> 메서드 <xref:System.Windows.Media.Geometry.Combine%2A>을 호출하여 만들 수 있습니다.  
  
-   <xref:System.Windows.Media.CombinedGeometry> 개체 및 <xref:System.Windows.Media.Geometry.Combine%2A> 메서드는 부울 연산을 수행하여 두 기하 도형에서 정의하는 영역을 결합합니다.  영역이 없는 <xref:System.Windows.Media.Geometry> 개체는 삭제됩니다.  이러한 두 개의 기하 도형도 복합 기하 도형이 될 수 있지만 두 개의 <xref:System.Windows.Media.Geometry> 개체만 결합할 수 있습니다.  
  
-   <xref:System.Windows.Media.GeometryGroup> 클래스는 포함하는 <xref:System.Windows.Media.Geometry> 개체를 해당 영역을 결합하지 않고 통합합니다.  원하는 수의 <xref:System.Windows.Media.Geometry> 개체를 <xref:System.Windows.Media.GeometryGroup>에 추가할 수 있습니다.  예제를 보려면 [복합 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)를 참조하십시오.  
  
 <xref:System.Windows.Media.GeometryGroup> 개체를 사용하면 결합 작업을 수행하지 않으므로 <xref:System.Windows.Media.CombinedGeometry> 개체나 <xref:System.Windows.Media.Geometry.Combine%2A> 메서드를 사용하는 것보다 성능상 이점이 있습니다.  
  
<a name="combindgeometriessection"></a>   
## 결합된 기하 도형  
 앞의 단원에서 설명한 바와 같이 <xref:System.Windows.Media.CombinedGeometry> 개체 및 <xref:System.Windows.Media.Geometry.Combine%2A> 메서드는 자신들이 포함하는 기하 도형에서 정의하는 영역을 결합합니다.  <xref:System.Windows.Media.GeometryCombineMode> 열거형은 기하 도형을 결합하는 방법을 지정합니다.  <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> 속성의 가능한 값은 <xref:System.Windows.Media.GeometryCombineMode>, <xref:System.Windows.Media.GeometryCombineMode>, <xref:System.Windows.Media.GeometryCombineMode> 및 <xref:System.Windows.Media.GeometryCombineMode>입니다.  
  
 다음 예제에서는 공용 구조체의 결합 모드를 사용하여 <xref:System.Windows.Media.CombinedGeometry>를 정의합니다.  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>를 모두 반지름은 같지만 중심이 50만큼 오프셋된 원으로 정의합니다.  
  
 [!code-xml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Union 결합 모드의 결과](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.png "mil\_task\_combined\_geometry\_union")  
  
 다음 예제에서는 <xref:System.Windows.Media.GeometryCombineMode>의 결합 모드를 사용하여 <xref:System.Windows.Media.CombinedGeometry>를 정의합니다.  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>를 모두 반지름은 같지만 중심이 50만큼 오프셋된 원으로 정의합니다.  
  
 [!code-xml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Xor 결합 모드의 결과](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.png "mil\_task\_combined\_geometry\_xor")  
  
 다른 예제를 보려면 [복합 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md) 및 [결합된 기하 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-combined-geometry.md)를 참조하십시오.  
  
<a name="freezable_features"></a>   
## Freezable 기능  
 <xref:System.Windows.Media.Geometry> 클래스는 <xref:System.Windows.Freezable> 클래스에서 상속되므로 몇 가지 특수한 기능을 제공합니다. 예를 들어 <xref:System.Windows.Media.Geometry> 개체를 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)에서와 같이 선언하거나, 여러 개체 간에 공유하거나, 읽기 전용으로 설정하여 성능을 향상시킬 수 있으며, 복제하거나, 스레드로부터 안전하게 보호할 수 있습니다.  <xref:System.Windows.Freezable> 개체에서 제공하는 여러 기능에 대한 자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
<a name="othergeometryfeatures"></a>   
## 기타 Geometry 기능  
 <xref:System.Windows.Media.Geometry> 클래스에서는 다음과 같은 유용한 유틸리티 메서드를 제공합니다.  
  
-   <xref:System.Windows.Media.Geometry.GetArea%2A> \- <xref:System.Windows.Media.Geometry>의 면적을 가져옵니다.  
  
-   <xref:System.Windows.Media.Geometry.FillContains%2A> \- Geometry에 다른 <xref:System.Windows.Media.Geometry>가 포함되어 있는지 여부를 확인합니다.  
  
-   <xref:System.Windows.Media.Geometry.StrokeContains%2A> \- <xref:System.Windows.Media.Geometry>의 스트로크에 지정한 점이 포함되는지 여부를 확인합니다.  
  
 전체 메서드 목록을 보려면 <xref:System.Windows.Media.Geometry> 클래스를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Geometry>   
 <xref:System.Windows.Media.PathGeometry>   
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.GeometryDrawing>   
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)