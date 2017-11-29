---
title: "방법: Win32 호스트 컨테이너를 사용하여 적중 테스트"
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
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9a5cb77a53cbb106593b70d618bab67ef816e901
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a>방법: Win32 호스트 컨테이너를 사용하여 적중 테스트
내에서 시각적 개체를 만들 수는 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 시각적 개체에 대 한 창 컨테이너 호스트를 제공 하 여이 창을 합니다. 포함된 시각적 개체에 대한 이벤트 처리를 제공하려면 호스트 창 컨테이너의 메시지 필터 루프에 전달된 메시지를 처리합니다. 참조 [자습서: Win32 응용 프로그램에서 시각적 개체 호스팅](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md) 에서 시각적 개체를 호스트 하는 방법에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창.  
  
## <a name="example"></a>예제  
 다음 코드에 대 한 마우스 이벤트 처리기를 설정 하는 방법을 보여 줍니다는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 시각적 개체에 대 한 호스트 컨테이너로 사용 되는 창입니다.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 다음 예제에 대 한 응답으로 특정 마우스 이벤트 트래핑 적중 횟수 테스트를 설정 하는 방법을 보여 줍니다.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <xref:System.Windows.Interop.HwndSource> 개체가 나타내는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 내에서 콘텐츠는 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 창. 값은 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 의 속성은 <xref:System.Windows.Interop.HwndSource> 개체 시각적 트리 계층의 최상위 노드를 나타냅니다.  
  
 적중 횟수 테스트에 전체 샘플 Win32 호스트 컨테이너를 사용 하 여 개체에 대 한 참조 [Win32 상호 운용성 샘플을 사용 하 여 적중 테스트](http://go.microsoft.com/fwlink/?LinkID=159995)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Interop.HwndSource>  
 [시각적 계층에서 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [자습서: Win32 응용 프로그램에서 시각적 개체 호스팅](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)
