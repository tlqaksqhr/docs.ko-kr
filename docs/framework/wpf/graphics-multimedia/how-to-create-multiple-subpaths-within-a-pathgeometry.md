---
title: "방법: PathGeometry 내에 다중 하위 경로 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3a9a233df95f69a68c5410c5836dacd5ab2c239a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a>방법: PathGeometry 내에 다중 하위 경로 만들기
여러 하위 경로 만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.PathGeometry>합니다. 여러 하위 경로 만들려면 만듭니다는 <xref:System.Windows.Media.PathFigure> 각 하위 경로 대 한 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 개의 하위 경로 각 삼각형을 만듭니다.  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 여러 하위 경로 사용 하 여 만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Shapes.Path> 및 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성 구문입니다. 각 `M` 새 하위 경로 만들어이 예에서는 각각 삼각형을 그리는 두 개의 하위 경로 만듭니다.  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 (이 특성 구문 실제로 만드는 참고는 <xref:System.Windows.Media.StreamGeometry>, 간단한 버전의는 <xref:System.Windows.Media.PathGeometry>합니다. 자세한 내용은 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) 페이지를 참조하세요.)  
  
## <a name="see-also"></a>참고 항목  
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
