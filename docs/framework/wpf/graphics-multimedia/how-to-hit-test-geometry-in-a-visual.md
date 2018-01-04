---
title: "방법: 시각적 요소의 기하 도형 적중 테스트"
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
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a990a43853e375c1c97f88dc6792932ad64c8d37
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>방법: 시각적 요소의 기하 도형 적중 테스트
하나 이상의 요소로 구성 된 시각적 개체에서 적중 횟수 테스트를 수행 하는 방법을 보여 주는이 예제 <xref:System.Windows.Media.Geometry> 개체입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 검색 하는 방법을 보여 줍니다.는 <xref:System.Windows.Media.DrawingGroup> 에서 사용 하는 시각적 개체는 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 메서드. 적중 횟수 테스트에 있는 각 그리기의 렌더링 된 콘텐츠에 대해 수행한 후의 <xref:System.Windows.Media.DrawingGroup> 기 하 도형을 적중 되었음을 확인 하려면.  
  
> [!NOTE]
>  대부분의 경우에서 사용는 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 점을 시각적 개체의 렌더링 된 콘텐츠의 모든 교차 하는지 여부를 결정 하는 메서드.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <xref:System.Windows.Media.Geometry.FillContains%2A> 적중 테스트는 지정 된를 사용 하 여 할 수 있는 오버 로드 된 메서드는 <xref:System.Windows.Point> 또는 <xref:System.Windows.Media.Geometry>합니다. 기하 도형에 스트로크를 적용할 경우 스트로크가 채우기 경계 밖으로 확장될 수 있습니다. 호출 하려는 수 있으며이 경우 <xref:System.Windows.Media.Geometry.StrokeContains%2A> 외에 <xref:System.Windows.Media.Geometry.FillContains%2A>합니다.  
  
 제공할 수도 있습니다는 <xref:System.Windows.Media.ToleranceType> 베 지 어 병합의 목적에 사용 되는 합니다.  
  
> [!NOTE]
>  이 샘플에서는 기하 도형에 적용될 수 있는 변환 또는 클리핑을 고려하지 않습니다. 또한 이 샘플은 직접 연결된 그림이 없으므로 스타일이 적용된 컨트롤에서 작동하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [시각적 계층에서 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [기하 도형을 매개 변수로 사용하여 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-geometry-as-a-parameter.md)
