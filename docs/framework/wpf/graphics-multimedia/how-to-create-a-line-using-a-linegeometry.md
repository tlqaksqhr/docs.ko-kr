---
title: "방법: LineGeometry를 사용하여 선 만들기"
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
helpviewer_keywords: graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 487a5ffaf952450c6196f5fe0d00fd249177b054
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a>방법: LineGeometry를 사용하여 선 만들기
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.LineGeometry> 줄을 설명 하는 클래스입니다. A <xref:System.Windows.Media.LineGeometry> 시작 및 끝 지점을 사용 하 여 정의 됩니다.  
  
## <a name="example"></a>예  
 만들고 렌더링 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Media.LineGeometry>합니다.  A <xref:System.Windows.Shapes.Path> 요소를 사용 하는 줄을 렌더링 합니다.  또한 선에 영역이 없는 이후는 <xref:System.Windows.Shapes.Path> 개체의 <xref:System.Windows.Shapes.Shape.Fill%2A> 지정 되지 않았습니다; 대신는 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성을 사용 합니다.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.gif "graphicsmm_line")  
(10,20)부터 (100,130)까지 그린 LineGeometry  
  
 다른 간단한 기 하 도형 클래스 포함 <xref:System.Windows.Media.LineGeometry> 및 <xref:System.Windows.Media.EllipseGeometry>합니다. 이 기 하이 도형 뿐만 아니라 더 복잡 한 프로젝트로 만들 수도 있습니다를 사용 하는 <xref:System.Windows.Media.PathGeometry> 또는 <xref:System.Windows.Media.StreamGeometry>합니다. 자세한 내용은 참조는 [기 하 도형 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [복합 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [PathGeometry를 사용하여 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
