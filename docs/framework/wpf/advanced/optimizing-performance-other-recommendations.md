---
title: "성능 최적화: 기타 권장 사항 | Microsoft Docs"
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
  - "브러시, 성능"
  - "개체 적중 테스트[WPF]"
  - "불투명도"
  - "ScrollBarVisibility 열거형"
  - "터미널 서비스 렌더링"
ms.assetid: d028cc65-7e97-4a4f-9859-929734eaf40d
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 성능 최적화: 기타 권장 사항
<a name="introduction"></a> 이 항목에서는 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md) 단원의 항목 내용에 추가되는 성능 권장 사항을 제공합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [브러시의 불투명과 요소의 불투명 비교](#Opacity)  
  
-   [개체 탐색](#Navigation_Objects)  
  
-   [대형 3차원 화면에서의 적중 테스트](#Hit_Testing)  
  
-   [CompositionTarget.Rendering 이벤트](#CompositionTarget_Rendering_Event)  
  
-   [ScrollBarVisibility\=Auto 사용 안 함](#Avoid_Using_ScrollBarVisibility)  
  
-   [시작 시간을 줄이도록 Font Cache Service 구성](#FontCache)  
  
<a name="Opacity"></a>   
## 브러시의 불투명과 요소의 불투명 비교  
 <xref:System.Windows.Media.Brush>를 사용하여 요소의 <xref:System.Windows.Shapes.Shape.Fill%2A> 또는 <xref:System.Windows.Shapes.Shape.Stroke%2A>를 설정하는 경우 요소의 <xref:System.Windows.UIElement.Opacity%2A> 속성을 설정하는 것보다 <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=fullName> 값을 설정하는 것이 더 좋습니다.  요소의 <xref:System.Windows.UIElement.Opacity%2A> 속성을 수정하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 임시 화면을 만듭니다.  
  
<a name="Navigation_Objects"></a>   
## 개체 탐색  
 <xref:System.Windows.Navigation.NavigationWindow> 개체는 <xref:System.Windows.Window>에서 파생되고 주로 <xref:System.Windows.Navigation.NavigationService> 및 저널을 집계하는 콘텐츠 탐색 지원을 통해 확장됩니다.  [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 또는 개체를 지정하여 <xref:System.Windows.Navigation.NavigationWindow>의 클라이언트 영역을 업데이트할 수 있습니다.  다음 샘플에서는 이러한 두 가지 방법을 보여 줍니다.  
  
 [!code-csharp[Performance#PerformanceSnippet14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 각 <xref:System.Windows.Navigation.NavigationWindow> 개체에는 해당 창에서의 사용자 탐색 기록을 기록하는 저널이 있습니다.  저널의 목적 중 하나는 사용자가 사용자의 단계를 다시 수행할 수 있도록 하는 것입니다.  
  
 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]를 사용하여 탐색하면 저널에서는 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 참조만 저장합니다.  이는 페이지를 다시 방문할 때마다 동적으로 다시 구성하기 때문에 페이지가 복잡할 경우 많은 시간이 걸릴 수도 있습니다.  이 경우 저널 저장 비용은 낮지만 페이지를 다시 구성하는 시간이 많이 걸릴 수 있습니다.  
  
 개체를 사용하여 탐색하면 저널에서는 개체의 전체 시각적 트리를 저장합니다.  즉, 페이지를 다시 방문할 때마다 페이지를 다시 구성하지 않고 바로 렌더링합니다.  이 경우 저널 저장 비용은 높지만 페이지를 다시 구성하는 시간이 줄어듭니다.  
  
 <xref:System.Windows.Navigation.NavigationWindow> 개체를 사용하는 경우에는 저널링 지원이 사용자 응용 프로그램의 성능에 미치는 영향에 대해 고려해야 합니다.  자세한 내용은 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)를 참조하십시오.  
  
<a name="Hit_Testing"></a>   
## 대형 3차원 화면에서의 적중 테스트  
 대형 3차원 화면에서의 적중 테스트는 CPU 사용 면으로 볼 때 성능에 영향을 미치는 작업입니다.  3차원 화면에 애니메이션 효과를 주는 경우 특히 더 영향을 미칩니다.  이러한 화면에서 적중 테스트가 필요 없는 경우에는 적중 테스트를 해제하십시오.  <xref:System.Windows.UIElement>에서 파생된 개체는 <xref:System.Windows.UIElement.IsHitTestVisible%2A> 속성을 `false`로 설정하여 적중 테스트를 해제할 수 있습니다.  
  
<a name="CompositionTarget_Rendering_Event"></a>   
## CompositionTarget.Rendering 이벤트  
 <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=fullName> 이벤트는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 계속 애니메이션 효과를 주도록 합니다.  이 이벤트를 사용하는 경우 상황에 따라 이 이벤트를 분리하십시오.  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>   
## ScrollBarVisibility\=Auto 사용 안 함  
 가능하면 `HorizontalScrollBarVisibility` 및 `VerticalScrollBarVisibility` 속성에 <xref:System.Windows.Controls.ScrollBarVisibility?displayProperty=fullName> 값을 사용하지 마십시오.  이러한 속성은 <xref:System.Windows.Controls.RichTextBox>, <xref:System.Windows.Controls.ScrollViewer> 및 <xref:System.Windows.Controls.TextBox> 개체에 대해 정의되고 <xref:System.Windows.Controls.ListBox> 개체의 연결 속성으로 정의됩니다.  대신 <xref:System.Windows.Controls.ScrollBarVisibility>를 <xref:System.Windows.Controls.ScrollBarVisibility>, <xref:System.Windows.Controls.ScrollBarVisibility> 또는 <xref:System.Windows.Controls.ScrollBarVisibility>로 설정하십시오.  
  
 <xref:System.Windows.Controls.ScrollBarVisibility> 값은 공간이 제한되어 스크롤바가 필요한 경우에 사용합니다.  예를 들어 텍스트 100줄을 제공하는 <xref:System.Windows.Controls.TextBox>보다 30개 항목의 <xref:System.Windows.Controls.ListBox>를 제공하는 이 <xref:System.Windows.Controls.ScrollBarVisibility> 값을 사용하는 것이 더 좋습니다.  
  
<a name="FontCache"></a>   
## 시작 시간을 줄이도록 Font Cache Service 구성  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Font Cache 서비스는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 간에 글꼴 데이터를 공유합니다.  서비스가 실행되고 있지 않은 경우 처음 실행하는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서 이 서비스를 시작합니다.  [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]를 사용하면 "[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Font Cache 3.0.0.0" 서비스를 "수동\(기본값\)"에서 "자동\(지연된 시작\)"으로 설정하여 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램의 초기 시작 시간을 줄일 수 있습니다.  
  
## 참고 항목  
 [응용 프로그램 성능 계획](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [하드웨어 이용](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [개체 동작](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [애니메이션에 대한 유용한 정보](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)