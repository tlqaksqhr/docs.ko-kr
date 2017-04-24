---
title: "자습서: Win32 응용 프로그램에서 시각적 개체 호스팅 | Microsoft Docs"
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
  - "호스팅(hosting), Win32 코드의 표시 개체"
  - "Win32 코드의 표시 개체"
  - "Win32 코드, 표시 개체"
ms.assetid: f0e1600c-3217-43d5-875d-1864fa7fe628
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 자습서: Win32 응용 프로그램에서 시각적 개체 호스팅
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 응용 프로그램을 만들기 위한 다양한 환경을 제공합니다.  그러나 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 코드를 작성하는 데 많은 시간과 노력을 기울인 경우 이 코드를 다시 작성하는 대신 응용 프로그램에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기능을 추가하는 것이 더 효율적일 수 있습니다.  응용 프로그램에서 현재 동시에 사용되는 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 하위 시스템을 모두 지원할 수 있도록 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에 개체를 호스팅하는 메커니즘을 제공합니다.  
  
 이 자습서에서는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시각적 개체를 호스팅하는 샘플 응용 프로그램인 [Hit Test with Win32 Interoperation 샘플](http://go.microsoft.com/fwlink/?LinkID=159995)을 작성하는 방법을 설명합니다.  
  
   
  
<a name="requirements"></a>   
## 요구 사항  
 이 자습서에서는 사용자가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로그래밍의 기본 사항에 대해 잘 알고 있다고 가정합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로그래밍에 대한 소개는 [연습: WPF 시작](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)을 참조하십시오.  [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로그래밍에 대한 소개는 관련된 수많은 서적이 있지만, 특히 Charles Petzold의 *Programming Windows*가 도움이 될 것입니다.  
  
> [!NOTE]
>  이 자습서에는 관련 샘플에 있는 많은 코드 예제가 포함되어 있지만  편의상 전체 샘플 코드는 제공하지 않습니다.  전체 샘플 코드를 보려면 [Hit Test with Win32 Interoperation 샘플](http://go.microsoft.com/fwlink/?LinkID=159995)을 참조하십시오.  
  
<a name="creating_the_host_win32_window"></a>   
## 호스트 Win32 창 만들기  
 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 개체를 호스팅하는 데 핵심적인 역할을 하는 요소는 <xref:System.Windows.Interop.HwndSource> 클래스입니다.  이 클래스를 사용하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 개체를 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에 래핑하여 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에 자식 창으로 통합할 수 있습니다.  
  
 다음 예제에서는 시각적 개체의 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 컨테이너 창으로 <xref:System.Windows.Interop.HwndSource> 개체를 만드는 코드를 보여 줍니다.  [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창의 창 스타일, 위치 및 다른 매개 변수를 설정하려면 <xref:System.Windows.Interop.HwndSourceParameters> 개체를 사용합니다.  
  
 [!code-csharp[VisualsHitTesting#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
>  <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> 속성 값은 WS\_EX\_TRANSPARENT로 설정할 수 없습니다.  즉, 호스트 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창은 투명하게 만들 수 없습니다.  이 때문에 호스트 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창의 배경색은 부모 창과 동일한 배경색으로 설정됩니다.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## 호스트 Win32 창에 시각적 개체 추가  
 시각적 개체의 호스트 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 컨테이너 창을 만들면 창에 시각적 개체를 추가할 수 있습니다.  애니메이션과 같은 시각적 개체에 대한 변환이 호스트 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창의 경계 사각형을 벗어나지 않도록 할 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Interop.HwndSource> 개체를 만들어 여기에 시각적 개체를 추가하는 코드를 보여 줍니다.  
  
> [!NOTE]
>  <xref:System.Windows.Interop.HwndSource> 개체의 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 속성을 호스트 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에 추가하는 첫 번째 시각적 개체로 설정합니다.  루트 시각적 개체는 시각적 개체 트리의 최상위 노드를 정의합니다.  이후에 호스트 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에 추가하는 시각적 개체는 자식 개체로 추가됩니다.  
  
 [!code-csharp[VisualsHitTesting#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## Win32 메시지 필터 구현  
 시각적 개체용 호스트 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에는 응용 프로그램 큐에서 창으로 전송되는 메시지를 처리하기 위한 창 메시지 필터 프로시저가 필요합니다.  창 프로시저는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 시스템에서  입력 메시지나 창 관리 메시지와 같은 메시지를 수신합니다.  원하는 경우 고유의 창 프로시저에서 메시지를 처리하거나 기본 처리를 위해 시스템에 메시지를 전달할 수 있습니다.  
  
 사용자가 시각적 개체의 부모로 정의한 <xref:System.Windows.Interop.HwndSource> 개체는 사용자가 제공한 창 메시지 필터 프로시저를 참조해야 합니다.  <xref:System.Windows.Interop.HwndSource> 개체를 만들 때 창 프로시저를 참조하도록 <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> 속성을 설정합니다.  
  
 [!code-csharp[VisualsHitTesting#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 다음 예제에서는 왼쪽 및 오른쪽 마우스 단추 해제 메시지를 처리하는 코드를 보여 줍니다.  마우스 적중 위치의 좌표 값은 `lParam` 매개 변수 값에 포함되어 있습니다.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## Win32 메시지 처리  
 다음 예제의 코드는 호스트 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에 포함된 시각적 개체의 계층 구조에 대해 적중 테스트를 수행하는 방법을 보여 줍니다.  <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 메서드를 사용하여 루트 시각적 개체와 적중 테스트를 수행할 좌표 값을 지정하면 해당 지점이 시각적 개체의 기하 도형 안에 있는지 확인할 수 있습니다.  이 경우 루트 시각적 개체가 <xref:System.Windows.Interop.HwndSource> 개체의 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 속성 값입니다.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 시각적 개체에 적중 테스트를 수행하는 방법에 대한 자세한 내용은 [시각적 계층에서 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Interop.HwndSource>   
 [Hit Test with Win32 Interoperation 샘플](http://go.microsoft.com/fwlink/?LinkID=159995)   
 [시각적 계층에서 적중 테스트](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)