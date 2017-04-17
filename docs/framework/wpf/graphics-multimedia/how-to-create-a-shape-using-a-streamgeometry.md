---
title: "방법: StreamGeometry를 사용하여 도형 만들기 | Microsoft Docs"
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
  - "클래스, StreamGeometry"
  - "그래픽[WPF], 도형"
  - "도형, StreamGeometry 클래스로 만들기"
  - "StreamGeometry 클래스"
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: StreamGeometry를 사용하여 도형 만들기
<xref:System.Windows.Media.StreamGeometry>는 도형을 만들기 위해 <xref:System.Windows.Media.PathGeometry> 대신 사용할 수 있는 간단한 클래스입니다.  복잡한 기하 도형을 설명해야 하지만 데이터 바인딩, 애니메이션 및 수정에 대한 지원에 따른 오버헤드를 원하지 않는 경우 <xref:System.Windows.Media.StreamGeometry>를 사용합니다.  예를 들어 <xref:System.Windows.Media.StreamGeometry> 클래스는 효율성으로 인해 표시기\(adorner\)를 설명하기에 적합합니다.  
  
## 예제  
 다음 예제에서는 특성 구문을 사용하여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 삼각형 <xref:System.Windows.Media.StreamGeometry>를 만듭니다.  
  
 [!code-xml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 <xref:System.Windows.Media.StreamGeometry> 특성 구문에 대한 자세한 내용은 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) 페이지를 참조하십시오.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.StreamGeometry>를 사용하여 코드로 삼각형을 정의합니다.  먼저 이 예제에서는 <xref:System.Windows.Media.StreamGeometry>를 만든 다음 <xref:System.Windows.Media.StreamGeometryContext>를 가져와 이를 통해 삼각형을 설명합니다.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.StreamGeometry> 및 <xref:System.Windows.Media.StreamGeometryContext>를 사용하는 메서드를 만들어 지정된 매개 변수를 기반으로 도형을 정의합니다.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## 참고 항목  
 <xref:System.Windows.Media.PathGeometry>   
 <xref:System.Windows.Media.StreamGeometry>   
 <xref:System.Windows.Media.StreamGeometryContext>   
 [PathGeometry를 사용하여 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)   
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)