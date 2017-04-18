---
title: "방법: 시각적 요소의 기하 도형 적중 테스트 | Microsoft Docs"
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
  - "Geometry 개체, 구성 표시 개체"
  - "적중 테스트, Geometry 개체를 구성하는 표시 개체에"
  - "표시 개체, 적중 테스트"
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 시각적 요소의 기하 도형 적중 테스트
이 예제에서는 하나 이상의 <xref:System.Windows.Media.Geometry> 개체로 구성된 시각적 개체에 대해 [적중 테스트](GTMT)를 수행하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 메서드를 사용하는 시각적 개체에서 <xref:System.Windows.Media.DrawingGroup>을 검색하는 방법을 보여 줍니다.  그런 다음 <xref:System.Windows.Media.DrawingGroup>에 있는 각 그리기의 렌더링된 콘텐츠에 대해 적중 테스트를 수행하여 적중된 기하 도형을 확인합니다.  
  
> [!NOTE]
>  대개의 경우 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드를 사용하여 점이 시각적 요소의 렌더링된 콘텐츠와 교차하는지 여부를 확인합니다.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <xref:System.Windows.Media.Geometry.FillContains%2A> 메서드는 지정된 <xref:System.Windows.Point> 또는 <xref:System.Windows.Media.Geometry>를 사용하여 적중 테스트를 수행할 수 있게 해 주는 오버로드된 메서드입니다.  기하 도형이 스트로크되는 경우 스크로크는 채우기 경계 밖으로 확장될 수 있습니다.  경우에 따라 <xref:System.Windows.Media.Geometry.FillContains%2A>와 함께 <xref:System.Windows.Media.Geometry.StrokeContains%2A>를 호출할 수 있습니다.  
  
 또한 3차원 펴기의 목적으로 사용되는 <xref:System.Windows.Media.ToleranceType>을 제공할 수도 있습니다.  
  
> [!NOTE]
>  이 샘플에서는 기하 도형에 적용될 수 있는 모든 변환이나 클리핑을 고려하지 않습니다.  또한 직접 연결된 그리기가 없기 때문에 이 샘플은 스타일이 적용된 컨트롤에서는 작동하지 않습니다.  
  
## 참고 항목  
 [시각적 계층에서 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)   
 [기하 도형을 매개 변수로 사용하여 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-geometry-as-a-parameter.md)