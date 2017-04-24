---
title: "WPF에서 Shape 및 기본 그리기 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "기본 그리기"
  - "Shape 개체"
  - "도형, 도형 정보"
  - "벡터 그리기, 개요"
  - "벡터, 그리기"
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# WPF에서 Shape 및 기본 그리기 개요
이 항목에서는 <xref:System.Windows.Shapes.Shape> 개체를 사용하여 그리는 방법에 대해 간략하게 설명합니다.  <xref:System.Windows.Shapes.Shape>은 화면에 도형을 그릴 수 있도록 하는 <xref:System.Windows.UIElement>의 한 형식입니다.  이러한 개체는 UI 요소이므로 <xref:System.Windows.Shapes.Shape> 개체를 <xref:System.Windows.Controls.Panel> 요소 및 대부분의 컨트롤 내에 사용할 수 있습니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]은 그래픽 및 렌더링 서비스에 대한 여러 계층의 액세스를 제공합니다.  최상위 계층에서 <xref:System.Windows.Shapes.Shape> 개체는 사용이 간편하고 레이아웃 및 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 이벤트 시스템 참여와 같은 여러 유용한 기능을 제공합니다.  
  
   
  
<a name="shapes"></a>   
## 도형 개체  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 사용할 수 있는 여러 <xref:System.Windows.Shapes.Shape> 개체를 제공합니다.  모든 Shape 개체는 <xref:System.Windows.Shapes.Shape> 클래스에서 상속됩니다.  사용 가능한 도형 개체에는 <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline> 및 <xref:System.Windows.Shapes.Rectangle>이 있습니다. <xref:System.Windows.Shapes.Shape> 개체는 다음과 같은 공용 속성을 공유합니다.  
  
-   <xref:System.Windows.Shapes.Shape.Stroke%2A>: 도형의 윤곽선을 그리는 방식을 기술합니다.  
  
-   <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: 도형의 윤곽선 두께를 기술합니다.  
  
-   <xref:System.Windows.Shapes.Shape.Fill%2A>: 도형의 내부를 그리는 방식을 기술합니다.  
  
-   [장치 독립적 픽셀](GTMT) 단위로 측정되는 좌표 및 꼭짓점을 지정하는 데이터 속성  
  
 도형 개체는 <xref:System.Windows.UIElement>에서 파생되므로 패널 및 대부분의 컨트롤 내에 사용될 수 있습니다.  <xref:System.Windows.Controls.Canvas> 패널은 자식 개체의 절대 위치 지정을 지원하므로 복잡한 그리기에 특히 적합합니다.  
  
 <xref:System.Windows.Shapes.Line> 클래스를 사용하면 두 점 사이에 선을 그릴 수 있습니다.  다음 예제에서는 선 좌표 및 스트로크 속성을 지정하는 여러 가지 방법을 보여 줍니다.  
  
 [!code-xml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 다음 그림에서는 렌더링된 <xref:System.Windows.Shapes.Line>을 보여 줍니다.  
  
 ![선 설명](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-line2.png "shape\_ovw\_line2")  
  
 <xref:System.Windows.Shapes.Line> 클래스가 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성을 제공하지만 <xref:System.Windows.Shapes.Line>에는 영역이 없으므로 해당 속성을 설정해도 효과가 없습니다.  
  
 또 다른 일반적인 도형은 <xref:System.Windows.Shapes.Ellipse>입니다.  도형의 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 정의하여 <xref:System.Windows.Shapes.Ellipse>를 만듭니다.  원을 그리려면 <xref:System.Windows.FrameworkElement.Width%2A> 값과 <xref:System.Windows.FrameworkElement.Height%2A> 값이 같은 <xref:System.Windows.Shapes.Ellipse>를 지정합니다.  
  
 [!code-xml[ShapeOverviews#ShapesOVW1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 다음 그림에서는 렌더링된 <xref:System.Windows.Shapes.Ellipse> 예제를 보여 줍니다.  
  
 ![타원 설명](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipse2.png "shape\_ovw\_ellipse2")  
  
<a name="paths"></a>   
## 경로 및 기하 도형 사용  
 <xref:System.Windows.Shapes.Path> 클래스를 사용하면 곡선 및 복잡한 도형을 그릴 수 있습니다.  이러한 곡선 및 도형은 <xref:System.Windows.Media.Geometry> 개체를 사용하여 기술됩니다.  <xref:System.Windows.Shapes.Path>를 사용하려면 <xref:System.Windows.Media.Geometry>를 만들고 이를 사용하여 <xref:System.Windows.Shapes.Path> 개체의 <xref:System.Windows.Shapes.Path.Data%2A> 속성을 설정합니다.  
  
 선택할 수 있는 다양한 <xref:System.Windows.Media.Geometry> 개체가 있습니다.  <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry> 및 <xref:System.Windows.Media.EllipseGeometry> 클래스는 상대적으로 단순한 도형을 기술합니다.  보다 복잡한 도형을 만들거나 곡선을 만들려면 <xref:System.Windows.Media.PathGeometry>를 사용합니다.  
  
<a name="pathgeometry"></a>   
### PathGeometry 및 PathSegment  
 <xref:System.Windows.Media.PathGeometry> 개체는 하나 이상의 <xref:System.Windows.Media.PathFigure> 개체로 구성되며 각 <xref:System.Windows.Media.PathFigure>는 서로 다른 "모양"이나 도형을 나타냅니다.  각 <xref:System.Windows.Media.PathFigure>는 각각 모양 또는 도형의 연결된 부분을 나타내는 하나 이상의 <xref:System.Windows.Media.PathSegment> 개체로 구성됩니다.  세그먼트 종류에는 <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment> 및 <xref:System.Windows.Media.ArcSegment>가 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Shapes.Path>를 사용하여 정방형 3차원 곡선을 그립니다.  
  
 [!code-xml[geometrysample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 다음 그림에서는 렌더링된 도형을 보여 줍니다.  
  
 ![경로 설명](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path2.png "shape\_ovw\_path2")  
  
 <xref:System.Windows.Media.PathGeometry> 및 기타 <xref:System.Windows.Media.Geometry> 클래스에 대한 자세한 내용은 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)를 참조하십시오.  
  
<a name="pathdatastring"></a>   
### XAML 약식 구문  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서는 특수 약식 구문을 사용하여 <xref:System.Windows.Shapes.Path>를 기술할 수도 있습니다.  다음 예제에서는 약식 구문을 사용하여 복잡한 도형을 그립니다.  
  
```xaml  
<Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 다음 그림에서는 렌더링된 <xref:System.Windows.Shapes.Path>를 보여 줍니다.  
  
 ![경로 설명](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-path.png "shape\_ovw\_path")  
  
 <xref:System.Windows.Shapes.Path.Data%2A> 특성 문자열은 M으로 표시되는 "moveto" 명령으로 시작됩니다. 이 명령은 <xref:System.Windows.Controls.Canvas>의 좌표계에서 경로의 시작점을 설정합니다.  <xref:System.Windows.Shapes.Path> 데이터 매개 변수는 대\/소문자를 구분합니다.  대문자 M은 새로운 현재 지점의 절대 위치를 나타내고  소문자 m은 상대 좌표를 나타냅니다.  첫 번째 세그먼트는 \(100,200\)에서 시작해서 \(400,175\)에서 끝나는 입방형 [3차원 곡선](GTMT)으로, 두 개의 제어점인 \(100,25\)와 \(400,350\)을 사용하여 그려집니다.  이 세그먼트는 <xref:System.Windows.Shapes.Path.Data%2A> 특성 문자열에서 C 명령으로 표시됩니다.  여기서도 대문자 C는 절대 경로를 나타내고 소문자 c는 상대 경로를 나타냅니다.  
  
 두 번째 세그먼트는 이전 하위 경로의 끝점인 \(400,175\)에서 새로운 끝점인 \(280,175\)로 그려지는 선을 지정하는 절대 가로 "lineto" 명령 H로 시작됩니다.  이는 가로 "lineto" 명령이므로 지정된 값은 *x* 좌표입니다.  
  
 전체 경로 구문은 <xref:System.Windows.Shapes.Path.Data%2A> 참조 및 [PathGeometry를 사용하여 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)를 참조하십시오.  
  
<a name="fillpaint"></a>   
## 도형 그리기  
 <xref:System.Windows.Media.Brush> 개체는 도형의 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.Fill%2A>을 그리는 데 사용됩니다.  다음 예제에서는 <xref:System.Windows.Shapes.Ellipse>의 스트로크와 채우기를 지정합니다.  브러시 속성의 유효한 입력은 키워드 또는 16진수 색 값일 수 있습니다.  사용 가능한 색 키워드에 대한 자세한 내용은 <xref:System.Windows.Media> 네임스페이스에서 <xref:System.Windows.Media.Colors> 클래스의 속성을 참조하십시오.  
  
```  
  
<Canvas Background="LightGray">   
   <Ellipse  
      Canvas.Top="50"  
      Canvas.Left="50"  
      Fill="#FFFFFF00"  
      Height="75"  
      Width="75"  
      StrokeThickness="5"  
      Stroke="#FF0000FF"/>  
</Canvas>  
  
```  
  
 다음 그림에서는 렌더링된 <xref:System.Windows.Shapes.Ellipse>를 보여 줍니다.  
  
 ![모든 타원](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-ellipsefill.png "shape\_ovw\_ellipsefill")  
  
 속성 요소 구문을 사용하여 <xref:System.Windows.Media.SolidColorBrush> 개체를 명시적으로 만든 다음 도형을 단색으로 그릴 수도 있습니다.  
  
```  
  
<!-- This polygon shape uses pre-defined color values for its Stroke and  
     Fill properties.   
     The SolidColorBrush's Opacity property affects the fill color in   
     this case by making it slightly transparent (opacity of 0.4) so   
     that it blends with any underlying color. -->  
  
<Polygon  
    Points="300,200 400,125 400,275 300,200"  
    Stroke="Purple"   
    StrokeThickness="2">  
    <Polygon.Fill>  
       <SolidColorBrush Color="Blue" Opacity="0.4"/>  
    </Polygon.Fill>  
</Polygon>  
```  
  
 다음 그림에서는 렌더링된 도형을 보여 줍니다.  
  
 ![SolidColorBrush 설명](../../../../docs/framework/wpf/graphics-multimedia/media/shape-ovw-solidcolorbrush.png "shape\_ovw\_solidcolorbrush")  
  
 그라데이션, 이미지, 패턴 등을 사용하여 도형의 스트로크나 채우기를 그릴 수도 있습니다.  자세한 내용은 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)을 참조하십시오.  
  
<a name="stretchableshapessection"></a>   
## 확장 가능한 도형  
 <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline> 및 <xref:System.Windows.Shapes.Rectangle> 클래스에는 모두 <xref:System.Windows.Shapes.Shape.Stretch%2A> 속성이 있습니다.  이 속성은 <xref:System.Windows.Shapes.Shape> 개체의 콘텐츠\(그릴 도형\)를 확장하여 <xref:System.Windows.Shapes.Shape> 개체의 레이아웃 공간을 채우는 방식을 결정합니다.  <xref:System.Windows.Shapes.Shape> 개체의 레이아웃 공간은 명시적인 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 설정 또는 해당 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 설정으로 인해 레이아웃 시스템이 <xref:System.Windows.Shapes.Shape>에 할당한 공간입니다.  Windows Presentation Foundation의 레이아웃에 대한 자세한 내용은 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md) 개요를 참조하십시오.  
  
 Stretch 속성의 값은 다음 중 하나입니다.  
  
-   <xref:System.Windows.Media.Stretch>: <xref:System.Windows.Shapes.Shape> 개체의 콘텐츠가 확장되지 않습니다.  
  
-   <xref:System.Windows.Media.Stretch>: <xref:System.Windows.Shapes.Shape> 개체의 콘텐츠를 확장하여 해당 레이아웃 공간을 채웁니다.  가로 세로 비율은 유지되지 않습니다.  
  
-   <xref:System.Windows.Media.Stretch>: <xref:System.Windows.Shapes.Shape> 개체의 콘텐츠를 최대한 확장하여 해당 레이아웃 공간을 채웁니다. 원래의 가로 세로 비율이 유지됩니다.  
  
-   <xref:System.Windows.Media.Stretch>: <xref:System.Windows.Shapes.Shape> 개체의 콘텐츠를 확장하여 해당 레이아웃 공간을 완전히 채웁니다. 원래의 가로 세로 비율이 유지됩니다.  
  
 <xref:System.Windows.Shapes.Shape> 개체의 콘텐츠를 확장하면 확장 후에 <xref:System.Windows.Shapes.Shape> 개체의 윤곽선이 그려집니다.  
  
 다음 예제에서는 <xref:System.Windows.Shapes.Polygon>을 사용하여 \(0,0\)에서 \(0,1\)과 \(1,1\)로 이어지는 매우 작은 삼각형을 그립니다.  <xref:System.Windows.Shapes.Polygon> 개체의 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A>는 100으로 설정되고 해당 확장 속성은 Fill로 설정됩니다.  그 결과 <xref:System.Windows.Shapes.Polygon> 개체의 콘텐츠\(삼각형\)가 확장되어 더 큰 공간을 채우게 됩니다.  
  
```  
...  
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
...  
```  
  
```  
...  
PointCollection myPointCollection = new PointCollection();  
myPointCollection.Add(new Point(0,0));  
myPointCollection.Add(new Point(0,1));  
myPointCollection.Add(new Point(1,1));  
  
Polygon myPolygon = new Polygon();  
myPolygon.Points = myPointCollection;  
myPolygon.Fill = Brushes.Blue;  
myPolygon.Width = 100;  
myPolygon.Height = 100;  
myPolygon.Stretch = Stretch.Fill;  
myPolygon.Stroke = Brushes.Black;  
myPolygon.StrokeThickness = 2;  
...  
```  
  
<a name="transforms"></a>   
## 도형 변환  
 <xref:System.Windows.Media.Transform> 클래스는 2차원 평면에서 도형을 변환할 수 있는 방법을 제공합니다.  여러 가지 변환의 종류에는 회전\(<xref:System.Windows.Media.RotateTransform>\), 배율 조정\(<xref:System.Windows.Media.ScaleTransform>\), 기울이기\(<xref:System.Windows.Media.SkewTransform>\) 및 변환\(<xref:System.Windows.Media.TranslateTransform>\)이 있습니다.  
  
 도형에 가장 많이 적용하는 변환은 회전입니다.  도형을 회전하려면 <xref:System.Windows.Media.RotateTransform>을 만들고 해당 <xref:System.Windows.Media.RotateTransform.Angle%2A>을 지정합니다.  <xref:System.Windows.Media.RotateTransform.Angle%2A>이 45이면 해당 요소가 시계 방향으로 45도 회전되고, 90이면 90도 회전되는 방식입니다.  요소가 회전되는 중심점을 제어하려면 <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 속성을 설정합니다.  이러한 속성 값은 변환할 요소의 좌표 공간으로 표현됩니다.  <xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A>의 기본값은 0입니다.  마지막으로 <xref:System.Windows.Media.RotateTransform>을 요소에 적용합니다.  변환으로 인해 레이아웃이 변경되지 않도록 하려면 도형의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성을 설정합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.RotateTransform>을 사용하여 도형의 왼쪽 위 모퉁이인 \(0,0\)을 중심으로 도형을 45도 회전합니다.  
  
 [!code-xml[transformssample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 다음 예제에서는 다른 도형을 45도 회전합니다. 이번에는 \(25,50\) 지점을 중심으로 회전합니다.  
  
 [!code-xml[transformssample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 다음 그림에서는 두 가지 변환을 적용한 결과를 보여 줍니다.  
  
 ![여러 중심점을 사용한 45도 회전](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.png "wcpsdk\_graphicsmm\_rotatetransform45degrees")  
  
 이전 예제에서는 각 도형 개체에 변환을 하나씩 적용했습니다.  도형 또는 기타 UI 요소에 여러 변환을 적용하려면 <xref:System.Windows.Media.TransformGroup>을 사용합니다.  
  
## 참고 항목  
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [연습: WPF 시작](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)