---
title: "방법: 기하 도형을 매개 변수로 사용하여 적중 테스트"
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
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 32feb70a3b7a44a5a48f57fc2ecee912de4d39ef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a>방법: 기하 도형을 매개 변수로 사용하여 적중 테스트
적중 횟수 테스트를 사용 하 여 시각적 개체에서 수행 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Geometry> 적중 매개 변수를 테스트 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하 여 적중 횟수 테스트를 설정 하는 방법을 보여 줍니다. <xref:System.Windows.Media.GeometryHitTestParameters> 에 대 한는 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드. <xref:System.Windows.Point> 에 전달 되는 값은 `OnMouseDown` 메서드 만드는 데 사용 되는 <xref:System.Windows.Media.Geometry> 적중 횟수 테스트의 범위를 확대 하기 위해 개체입니다.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> 속성 <xref:System.Windows.Media.GeometryHitTestResult> 사용 하는 적중 횟수 테스트 결과 대 한 정보를 제공는 <xref:System.Windows.Media.Geometry> 적중 매개 변수를 테스트 합니다. 다음 그림에서는 적중 테스트 기하 도형(파란색 원)과 대상 시각적 개체의 렌더링된 콘텐츠(빨간색 사각형) 간 관계를 보여 줍니다.  
  
 ![사용 되는 IntersectionDetail의 다이어그램 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")  
적중 테스트 기하 도형과 대상 시각적 개체 간 교차  
  
 다음 예제는 적중 횟수 테스트 콜백을 구현 하는 방법을 보여 줍니다 때는 <xref:System.Windows.Media.Geometry> 적중 횟수 테스트 매개 변수로 사용 됩니다. `result` 매개 변수를 캐스팅 되는 <xref:System.Windows.Media.GeometryHitTestResult> 의 값을 검색 하기 위해는 <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> 속성입니다. 속성 값을 사용 하면 여부를 확인 하는 <xref:System.Windows.Media.Geometry> 적중 횟수 테스트 매개 변수는 완전히 또는 부분적으로 내에 포함 된 적중된 테스트 대상의 렌더링된 된 콘텐츠입니다. 이 경우 샘플 코드는 대상 경계 내에 완전히 포함된 시각적 개체 목록에 적중 테스트 결과를 추가하기만 합니다.  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  <xref:System.Windows.Media.HitTestResult> 콜백 때의 교차 지점 세부 정보는 호출할 수 없습니다 <xref:System.Windows.Media.IntersectionDetail.Empty>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [시각적 계층에서 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [시각적 요소의 기하 도형 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)
