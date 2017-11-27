---
title: "방법: 결합된 기하 도형 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2be0471f27d26b145cc29847a08bf3bc3b1d51ff
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-a-combined-geometry"></a>방법: 결합된 기하 도형 만들기
이 예제에는 기 하 도형을 결합 하는 방법을 보여 줍니다. 두 기 하 도형을 함께 사용 하려면 사용을 <xref:System.Windows.Media.CombinedGeometry> 개체입니다. 설정의 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 결합 및 설정 하려면 두 기 하 도형 사용 하 여 속성의 <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> 기 하 도형이 함께 결합할 수는 방법을 확인 하는 경우이 속성을 `Union`, `Intersect`, `Exclude`, 또는 `Xor`.  
  
 두 개 이상의 기 하 도형에서 복합 geometry를 만들려면 사용는 <xref:System.Windows.Media.GeometryGroup>합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Media.CombinedGeometry> 의 geometry 결합 모드를 사용 하 여 정의 `Exclude`합니다.  둘 다 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 50 원 반지름 하지만 센터 오프셋으로 정의 됩니다.  
  
 [!code-xaml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 ![결합 모드의 Exclude 결과](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")  
결합된 기 하 도형 제외  
  
 다음 태그에서는 <xref:System.Windows.Media.CombinedGeometry> 의 결합 모드를 사용 하 여 정의 `Intersect`합니다.  둘 다 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 50 원 반지름 하지만 센터 오프셋으로 정의 됩니다.  
  
 [!code-xaml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 ![결과 Intersect 결합 모드](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")  
Intersect 결합된 기 하 도형  
  
 다음 태그에서는 <xref:System.Windows.Media.CombinedGeometry> 의 결합 모드를 사용 하 여 정의 `Union`합니다.  둘 다 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 50 원 반지름 하지만 센터 오프셋으로 정의 됩니다.  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Union 결합 모드의 결과](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")  
결합 된 Geometry 합집합  
  
 다음 태그에서는 <xref:System.Windows.Media.CombinedGeometry> 의 결합 모드를 사용 하 여 정의 `Xor`합니다.  둘 다 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 50 원 반지름 하지만 센터 오프셋으로 정의 됩니다.  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Xor 결합 모드의 결과](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_union")  
Xor 결합된 기 하 도형
