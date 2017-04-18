---
title: "방법: TileBrush의 가로 및 세로 맞춤 설정 | Microsoft Docs"
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
  - "맞추기, TileBrushe"
  - "TileBrushe의 가로 맞춤"
  - "TileBrush, 맞춤"
  - "TileBrushe의 세로 맞춤"
ms.assetid: 65ae89bd-9246-4c9e-bde4-2fb991d4060d
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: TileBrush의 가로 및 세로 맞춤 설정
이 예제에서는 바둑판식 배열에서 콘텐츠의 가로 및 세로 맞춤을 제어하는 방법을 보여 줍니다.  <xref:System.Windows.Media.TileBrush>의 가로 및 세로 맞춤을 제어하려면 해당 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 및 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 속성을 사용합니다.  
  
 다음 조건 중 하나에 해당되면 <xref:System.Windows.Media.TileBrush>의 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 및 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 속성을 사용합니다.  
  
-   <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성이 <xref:System.Windows.Media.Stretch> 또는 <xref:System.Windows.Media.Stretch>이고 <xref:System.Windows.Media.TileBrush.Viewbox%2A>와 <xref:System.Windows.Media.TileBrush.Viewport%2A>의 [가로 세로 비율](GTMT)이 서로 다릅니다.  
  
-   <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성이 <xref:System.Windows.Media.Stretch>이고 <xref:System.Windows.Media.TileBrush.Viewbox%2A>와 <xref:System.Windows.Media.TileBrush.Viewport%2A>의 크기가 서로 다릅니다.  
  
## 예제  
 다음 예제에서는 형식이 <xref:System.Windows.Media.TileBrush>인 <xref:System.Windows.Media.DrawingBrush>의 콘텐츠를 바둑판식 배열의 왼쪽 위 모퉁이에 맞춥니다.  이 예제에서는 <xref:System.Windows.Media.DrawingBrush>의 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 속성을 <xref:System.Windows.Media.AlignmentX>로 설정하고 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 속성을 <xref:System.Windows.Media.AlignmentY>으로 설정하여 콘텐츠를 맞춥니다.  이 예제의 결과는 다음과 같습니다.  
  
 ![왼쪽 위에 정렬된 TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletopleft.png "graphicsmm\_TileBrushAlignmentExampleTopLeft")  
콘텐츠가 왼쪽 위 모퉁이에 맞춰진 TileBrush  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmentinline)]
 [!code-xml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmentinline)]  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 속성을 <xref:System.Windows.Media.AlignmentX>로 설정하고 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 속성을 <xref:System.Windows.Media.AlignmentY>으로 설정하여 <xref:System.Windows.Media.DrawingBrush>의 콘텐츠를 해당 바둑판식 배열의 오른쪽 아래 모퉁이에 맞춥니다.  다음과 같이 출력됩니다.  
  
 ![오른쪽 아래에 정렬된 TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomright.png "graphicsmm\_TileBrushAlignmentExampleBottomRight")  
콘텐츠가 오른쪽 아래 모퉁이에 맞춰진 TileBrush  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 속성을 <xref:System.Windows.Media.AlignmentX>로 설정하고 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 속성을 <xref:System.Windows.Media.AlignmentY>로 설정하여 <xref:System.Windows.Media.DrawingBrush>의 콘텐츠를 해당 바둑판식 배열의 왼쪽 위 모퉁이에 맞춥니다.  또한 <xref:System.Windows.Media.DrawingBrush>의 <xref:System.Windows.Media.TileBrush.Viewport%2A> 및 <xref:System.Windows.Media.TileBrush.TileMode%2A>를 설정하여 바둑판식 배열 패턴을 만듭니다.  다음과 같이 출력됩니다.  
  
 ![바둑판식으로 왼쪽 위에 정렬된 TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletoplefttiled.png "graphicsmm\_TileBrushAlignmentExampleTopLeftTiled")  
콘텐츠가 기본 바둑판식 배열의 왼쪽 위에 맞춰진 바둑판식 배열 패턴  
  
 그림에서는 콘텐츠의 맞춤 방식을 볼 수 있도록 기본 바둑판식 배열이 강조 표시되어 있습니다.  <xref:System.Windows.Media.DrawingBrush>의 콘텐츠가 기본 바둑판식 배열을 가로로 완전히 채우므로 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 설정은 아무런 영향을 주지 않습니다.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmenttiledinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmenttiledinline)]
 [!code-xml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmenttiledinline)]  
  
## 예제  
 마지막 예제에서는 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 속성을 <xref:System.Windows.Media.AlignmentX>로 설정하고 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 속성을 <xref:System.Windows.Media.AlignmentY>로 설정하여 바둑판식으로 배열된 <xref:System.Windows.Media.DrawingBrush>의 콘텐츠를 해당 기본 바둑판식 배열의 오른쪽 아래에 맞춥니다.  다음과 같이 출력됩니다.  
  
 ![바둑판식으로 오른쪽 아래에 정렬된 TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomrighttiled.png "graphicsmm\_TileBrushAlignmentExampleBottomRightTiled")  
콘텐츠가 기본 바둑판식 배열의 오른쪽 아래에 맞춰진 바둑판식 배열 패턴  
  
 이때도 <xref:System.Windows.Media.DrawingBrush>의 콘텐츠가 기본 바둑판식 배열을 가로로 완전히 채우므로 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 설정은 아무런 영향을 주지 않습니다.  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
 앞의 여러 예제에서는 <xref:System.Windows.Media.DrawingBrush> 개체를 사용하여 <xref:System.Windows.Media.TileBrush.AlignmentX%2A> 및 <xref:System.Windows.Media.TileBrush.AlignmentY%2A> 속성을 사용하는 방법을 보여 줍니다.  이러한 속성은 <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush> 등의 모든 바둑판식 배열 브러시에 대해 동일하게 작동합니다.  바둑판식 배열 브러시에 대한 자세한 내용은 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.DrawingBrush>   
 <xref:System.Windows.Media.ImageBrush>   
 <xref:System.Windows.Media.VisualBrush>   
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)