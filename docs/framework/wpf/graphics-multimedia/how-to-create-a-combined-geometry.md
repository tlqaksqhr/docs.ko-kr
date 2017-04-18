---
title: "방법: 결합된 기하 도형 만들기 | Microsoft Docs"
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
  - "기하 도형 결합"
  - "기하 도형, 결합"
  - "그래픽, 기하 도형 결합"
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 결합된 기하 도형 만들기
이 예제에서는 기하 도형을 결합하는 방법을 보여 줍니다.  두 기하 도형을 결합하려면 <xref:System.Windows.Media.CombinedGeometry>를 사용합니다.  결합할 두 기하 도형에 <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 속성을 설정하고 기하 도형의 결합 방법을 결정하는 <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> 속성을 `Union`, `Intersect`, `Exclude` 또는 `Xor`로 설정합니다.  
  
 둘 이상의 기하 도형으로 복합 기하 도형을 만들려면 <xref:System.Windows.Media.GeometryGroup>을 사용합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.CombinedGeometry>가 `Exclude`라는 기하 도형 결합 모드로 정의됩니다.  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>를 모두 반지름은 같지만 중심이 50만큼 오프셋된 원으로 정의합니다.  
  
 [!code-xml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 ![Exclude 결합 모드의 결과](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.png "mil\_task\_combined\_geometry\_exclude")  
Exclude 모드로 결합된 기하 도형  
  
 다음 태그에서는 <xref:System.Windows.Media.CombinedGeometry>가 `Intersect`라는 결합 모드로 정의됩니다.  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>를 모두 반지름은 같지만 중심이 50만큼 오프셋된 원으로 정의합니다.  
  
 [!code-xml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 ![Intersect 결합 모드의 결과](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.png "mil\_task\_combined\_geometry\_intersect")  
Intersect 모드로 결합된 기하 도형  
  
 다음 태그에서는 <xref:System.Windows.Media.CombinedGeometry>가 `Union`이라는 결합 모드로 정의됩니다.  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>를 모두 반지름은 같지만 중심이 50만큼 오프셋된 원으로 정의합니다.  
  
 [!code-xml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 ![Union 결합 모드의 결과](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.png "mil\_task\_combined\_geometry\_union")  
Union 모드로 결합된 기하 도형  
  
 다음 태그에서는 <xref:System.Windows.Media.CombinedGeometry>가 `Xor`이라는 결합 모드로 정의됩니다.  <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> 및 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>를 모두 반지름은 같지만 중심이 50만큼 오프셋된 원으로 정의합니다.  
  
 [!code-xml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 ![Xor 결합 모드의 결과](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.png "mil\_task\_combined\_geometry\_xor")  
Xor 모드로 결합된 기하 도형