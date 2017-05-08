---
title: "방법: PathGeometry에 LineSegment 만들기 | Microsoft Docs"
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
  - "PathGeometry 클래스"
  - "PathGeometry 클래스"
  - "선 세그먼트를 만들기"
  - "그래픽 [WPF] 선 세그먼트"
ms.assetid: 0155ed47-a20d-49a7-a306-186d8e07fbc4
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: PathGeometry에 LineSegment 만들기
이 예제에는 선 세그먼트를 만드는 방법을 보여 줍니다. 선 세그먼트를 만들려면 사용은 <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, 및 <xref:System.Windows.Media.LineSegment> 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 그리기는 <xref:System.Windows.Media.LineSegment> 에서 (10, 50)을 (200, 70). 다음 그림에서는 결과 <xref:System.Windows.Media.LineSegment>; 그리드 배경 좌표계를 표시 하기 위해 추가 되었습니다.  
  
 ![PathFigure의 LineSegment](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment")  
(200,70) (10,&50;)에서 그려져 LineSegment  
  
 [xaml]  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 경로 나타낼 특성 구문을 사용할 수 있습니다.  
  
```xaml  
<Path Stroke="Black" StrokeThickness="1"    
  Data="M 10,50 L 200,70" />  
```  
  
 [xaml]  
  
 (실제로 만드는이 특성 구문에 <xref:System.Windows.Media.StreamGeometry>, 가벼운 버전의는 <xref:System.Windows.Media.PathGeometry>합니다. 자세한 내용은 참조는 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) 페이지입니다.)  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 개체 요소 구문을 사용 하 여 선 세그먼트를 그릴 수도 있습니다. 다음은 이전에 해당 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제입니다.  
  
```xaml  
<Path Stroke="Black" StrokeThickness="1">  
  <Path.Data>  
    <PathGeometry>  
      <PathFigure StartPoint="10,50">  
        <LineSegment Point="200,70" />  
      </PathFigure>  
    </PathGeometry>  
  </Path.Data>  
</Path>  
```  
  
```csharp  
PathFigure myPathFigure = new PathFigure();  
myPathFigure.StartPoint = new Point(10, 50);  
  
LineSegment myLineSegment = new LineSegment();  
myLineSegment.Point = new Point(200, 70);  
  
PathSegmentCollection myPathSegmentCollection = new PathSegmentCollection();  
myPathSegmentCollection.Add(myLineSegment);  
  
myPathFigure.Segments = myPathSegmentCollection;  
  
PathFigureCollection myPathFigureCollection = new PathFigureCollection();  
myPathFigureCollection.Add(myPathFigure);  
  
PathGeometry myPathGeometry = new PathGeometry();  
myPathGeometry.Figures = myPathFigureCollection;  
  
Path myPath = new Path();  
myPath.Stroke = Brushes.Black;  
myPath.StrokeThickness = 1;  
myPath.Data = myPathGeometry;  
```  
  
```vb  
Dim myPathFigure As New PathFigure()  
            myPathFigure.StartPoint = New Point(10, 50)  
  
            Dim myLineSegment As New LineSegment()  
            myLineSegment.Point = New Point(200, 70)  
  
            Dim myPathSegmentCollection As New PathSegmentCollection()  
            myPathSegmentCollection.Add(myLineSegment)  
  
            myPathFigure.Segments = myPathSegmentCollection  
  
            Dim myPathFigureCollection As New PathFigureCollection()  
            myPathFigureCollection.Add(myPathFigure)  
  
            Dim myPathGeometry As New PathGeometry()  
            myPathGeometry.Figures = myPathFigureCollection  
  
            Dim myPath As New Path()  
            myPath.Stroke = Brushes.Black  
            myPath.StrokeThickness = 1  
            myPath.Data = myPathGeometry  
```  
  
 이 예제는 더 큰 샘플;의 일부 전체 샘플에 대 한 참조는 [기 하 도형 샘플](http://go.microsoft.com/fwlink/?LinkID=159989)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.PathFigure>   
 <xref:System.Windows.Media.PathGeometry>   
 <xref:System.Windows.Media.GeometryDrawing>   
 <xref:System.Windows.Shapes.Path>   
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)