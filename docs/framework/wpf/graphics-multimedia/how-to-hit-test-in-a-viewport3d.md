---
title: '방법: Viewport3D의 적중 테스트'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D visuals [WPF], hit-testing for
- hit tests [WPF], for 3-D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: ab097e11490fda7a8e3b23c8749204f091271919
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-hit-test-in-a-viewport3d"></a>방법: Viewport3D의 적중 테스트
적중 횟수의 3D 시각적 개체에 대 한 테스트 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Viewport3D>합니다.  
  
 때문에 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 2D 및 3D 정보를 반환 합니다만 3D 결과 확인 하기 위해 테스트 결과 반복 하는 것이 불가능 합니다.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
 [!code-vb[HitTest3D#HitTest3D3DN4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]  
  
 <xref:System.Windows.Media.HitTestResultBehavior> 다음 코드에서 적중 횟수 테스트 결과 처리 하는 방법을 결정 합니다.  `UpdateResultInfo` 및 `UpdateMaterial` 로컬로 정의 된 메서드입니다.  
  
 [!code-csharp[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
 [!code-vb[HitTest3D#HitTest3D3DN5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]  
  
## <a name="see-also"></a>참고 항목  
 [3 차원 적중 테스트 샘플](http://go.microsoft.com/fwlink/?LinkID=159959)
