---
title: "성능 최적화: 기타 권장 사항"
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
- Terminal Services rendering [WPF]
- opacity [WPF]
- hit-test objects [WPF]
- ScrollBarVisibility enumeration [WPF]
- brushes [WPF], performance
ms.assetid: d028cc65-7e97-4a4f-9859-929734eaf40d
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e45296befd51af5e4b03f123241efba030fd3754
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="optimizing-performance-other-recommendations"></a>성능 최적화: 기타 권장 사항
<a name="introduction"></a> 이 항목에서는 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md) 섹션의 항목 내용에 추가되는 성능 권장 사항을 제공합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [브러시의 불투명도와 요소의 불투명도 비교](#Opacity)  
  
-   [개체 탐색](#Navigation_Objects)  
  
-   [대형 3D 화면에서의 적중 횟수 테스트](#Hit_Testing)  
  
-   [CompositionTarget.Rendering 이벤트](#CompositionTarget_Rendering_Event)  
  
-   [ScrollBarVisibility=Auto 사용 안 함](#Avoid_Using_ScrollBarVisibility)  
  
-   [시작 시간을 줄이도록 글꼴 캐시 서비스 구성](#FontCache)  
  
<a name="Opacity"></a>   
## <a name="opacity-on-brushes-versus-opacity-on-elements"></a>브러시의 불투명도와 요소의 불투명도 비교  
 사용 하는 경우는 <xref:System.Windows.Media.Brush> 설정 하는 <xref:System.Windows.Shapes.Shape.Fill%2A> 또는 <xref:System.Windows.Shapes.Shape.Stroke%2A> 요소의 하는 것이 설정의 <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> 는 설정 하는 대신 값 요소의 <xref:System.Windows.UIElement.Opacity%2A> 속성입니다. 요소의 수정 <xref:System.Windows.UIElement.Opacity%2A> 속성으로 지정 하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 임시 화면을 만듭니다.  
  
<a name="Navigation_Objects"></a>   
## <a name="navigation-to-object"></a>개체 탐색  
 <xref:System.Windows.Navigation.NavigationWindow> 개체에서 파생 <xref:System.Windows.Window> 을 집계 하 여 주로 콘텐츠 탐색 지원을 사용 하도록 확장 <xref:System.Windows.Navigation.NavigationService> 및 저널 합니다. 클라이언트 영역을 업데이트할 수 있습니다 <xref:System.Windows.Navigation.NavigationWindow> 지정 하 여 한 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 또는 개체입니다. 다음 샘플에서는 이러한 두 가지 방법을 보여 줍니다.  
  
 [!code-csharp[Performance#PerformanceSnippet14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 각 <xref:System.Windows.Navigation.NavigationWindow> 개체에 해당 창에서 사용자의 탐색 기록을 기록 하는 저널 합니다. 저널의 목적 중 하나는 사용자가 단계를 다시 수행할 수 있도록 하는 것입니다.  
  
 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]를 사용하여 탐색하면 저널에서는 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 참조만 저장합니다. 이는 페이지를 다시 방문할 때마다 동적으로 다시 구성하기 때문에 페이지가 복잡할 경우 많은 시간이 걸릴 수도 있습니다. 이 경우 저널 저장 비용은 낮지만 페이지를 다시 구성하는 시간이 오래 걸릴 수 있습니다.  
  
 개체를 사용하여 탐색하면 저널에서 개체의 전체 시각적 트리를 저장합니다. 즉, 페이지를 다시 방문할 때마다 페이지를 다시 구성하지 않고 바로 렌더링합니다. 이 경우 저널 저장 비용은 높지만 페이지를 다시 구성하는 시간이 줄어듭니다.  
  
 사용 하는 경우는 <xref:System.Windows.Navigation.NavigationWindow> 개체 저널링 지원 응용 프로그램의 성능에 미치는 영향에 점을 명심 해야 합니다. 자세한 내용은 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)를 참조하세요.  
  
<a name="Hit_Testing"></a>   
## <a name="hit-testing-on-large-3d-surfaces"></a>대형 3D 화면에서의 적중 횟수 테스트  
 대형 3D 화면에서의 적중 횟수 테스트는 CPU 사용 면으로 볼 때 성능에 영향을 미치는 작업입니다. 3D 화면에 애니메이션 효과를 주는 경우 특히 더 영향을 미칩니다. 이러한 화면에서 적중 횟수 테스트가 필요 없는 경우에는 적중 횟수 테스트를 사용하지 마세요. 개체에서 파생 된 <xref:System.Windows.UIElement> 수 적중 테스트를 해제할 설정 하 여는 <xref:System.Windows.UIElement.IsHitTestVisible%2A> 속성을 `false`합니다.  
  
<a name="CompositionTarget_Rendering_Event"></a>   
## <a name="compositiontargetrendering-event"></a>CompositionTarget.Rendering 이벤트  
 <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> 이벤트로 인해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에 지속적으로 애니메이션을 적용 합니다. 이 이벤트를 사용하는 경우 기회가 될 때마다 이 이벤트를 분리하세요.  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>   
## <a name="avoid-using-scrollbarvisibilityauto"></a>ScrollBarVisibility=Auto 사용 안 함  
 가능 하면 항상 사용 하지 않도록는 <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> 에 대 한 값은 `HorizontalScrollBarVisibility` 및 `VerticalScrollBarVisibility` 속성입니다. 이러한 속성에 대해 정의 된 <xref:System.Windows.Controls.RichTextBox>, <xref:System.Windows.Controls.ScrollViewer>, 및 <xref:System.Windows.Controls.TextBox> 개체 및 연결된 된 속성에 대 한 다른 이름으로 <xref:System.Windows.Controls.ListBox> 개체입니다. 대신, 설정 <xref:System.Windows.Controls.ScrollBarVisibility> 를 <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>, <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>, 또는 <xref:System.Windows.Controls.ScrollBarVisibility.Visible>합니다.  
  
 <xref:System.Windows.Controls.ScrollBarVisibility.Auto> 사례에 대 한 값을 사용할 공간은 제한 하 고 필요한 경우에 스크롤 막대를 표시 해야 합니다. 예를 들어이 하 유용할 수 있습니다 <xref:System.Windows.Controls.ScrollBarVisibility> 값과 <xref:System.Windows.Controls.ListBox> 반대인 30 개의 항목이 <xref:System.Windows.Controls.TextBox> 수백 줄의 텍스트입니다.  
  
<a name="FontCache"></a>   
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a>시작 시간을 줄이도록 글꼴 캐시 서비스 구성  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 글꼴 캐시 서비스는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 간에 글꼴 데이터를 공유합니다. 서비스가 실행되고 있지 않은 경우 처음 실행하는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서 이 서비스가 시작됩니다. [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]를 사용하면 “[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 글꼴 캐시 3.0.0.0” 서비스를 “수동(기본값)”에서 “자동(지연된 시작)”으로 설정하여 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램의 초기 시작 시간을 줄일 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 성능 계획](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [하드웨어 이용](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [개체 동작](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [애니메이션에 대한 유용한 정보](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)
