---
title: "방법: Win32 호스트 컨테이너를 사용하여 적중 테스트 | Microsoft Docs"
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
  - "적중 테스트, Win32 호스트 컨테이너 사용"
  - "표시 개체, 적중 테스트"
  - "Win32 호스트 컨테이너, 적중 테스트에서 사용"
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: Win32 호스트 컨테이너를 사용하여 적중 테스트
시각적 개체에 대한 호스트 창 컨테이너를 제공하여 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 창 안에 시각적 개체를 만들 수 있습니다.  포함된 시각적 개체에 대한 이벤트 처리를 제공하기 위해 호스트 창 컨테이너의 메시지 필터 루프에 전달된 메시지를 처리합니다.  [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에서 시각적 개체를 호스팅하는 방법에 대한 자세한 내용은 [자습서: Win32 응용 프로그램에서 시각적 개체 호스팅](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)을 참조하십시오.  
  
## 예제  
 다음 코드에서는 시각적 개체의 호스트 컨테이너로 사용되는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에 대한 마우스 이벤트 처리기를 설정하는 방법을 보여 줍니다.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 다음 예제에서는 특정 마우스 이벤트 추적에 대한 응답으로 [적중 테스트](GTMT)를 설정하는 방법을 보여 줍니다.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <xref:System.Windows.Interop.HwndSource> 개체는 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 창 안에 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 콘텐츠를 표시합니다. <xref:System.Windows.Interop.HwndSource> 개체의 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 속성 값은 [시각적 트리](GTMT) 계층 구조의 최상위 노드를 나타냅니다.  
  
 Win32 호스트 컨테이너를 사용한 적중 테스트 개체에 대한 전체 샘플을 보려면 [Hit Test with Win32 Interoperation 샘플](http://go.microsoft.com/fwlink/?LinkID=159995)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Interop.HwndSource>   
 [시각적 계층에서 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)   
 [자습서: Win32 응용 프로그램에서 시각적 개체 호스팅](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)