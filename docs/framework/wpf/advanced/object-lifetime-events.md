---
title: "개체 수명 이벤트 | Microsoft Docs"
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
  - "활성화된 이벤트"
  - "응용 프로그램 개체, 수명 이벤트"
  - "클래스, 프레임"
  - "클래스, NavigationWindow"
  - "Closed 이벤트"
  - "Closing 이벤트"
  - "ContentRendered 이벤트"
  - "Deactivated 이벤트"
  - "이벤트, Activated"
  - "이벤트, 닫힘"
  - "이벤트, Closing"
  - "이벤트, ContentRendered"
  - "이벤트, Deactivated"
  - "이벤트, 초기화됨"
  - "이벤트, 로드됨"
  - "이벤트, 언로드됨"
  - "이벤트 종료"
  - "Frame 클래스"
  - "Initialized 이벤트"
  - "개체의 수명 이벤트"
  - "Loaded 이벤트"
  - "NavigationWindow 클래스"
  - "개체의 수명 이벤트"
  - "Startup 이벤트"
  - "Unloaded 이벤트"
ms.assetid: face6fc7-465b-4502-bfe5-e88d2e729a78
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 개체 수명 이벤트
이 항목에서는 생성, 사용, 소멸이라는 개체 수명의 단계를 나타내는 특정 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트에 대해 설명합니다.  
  
   
  
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목에서는 독자가 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스의 기존 [종속성 속성](GTMT)의 사용자로서 종속성 속성을 이해하고 있으며 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 읽었다고 가정합니다.  이 항목의 예제를 실행하려면 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에 대해서도 이해하고 있어야 하며\([XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) 참조\) [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 작성 방법을 알고 있어야 합니다.  
  
<a name="intro"></a>   
## 개체 수명 이벤트  
 [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)] 관리 코드의 모든 개체는 생성, 사용, 소멸이라는 비슷한 일련의 수명 단계를 거칩니다.  대부분의 개체는 소멸 단계의 일부로 발생하는 종료 단계도 거칩니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 개체, 구체적으로 말해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 요소로 식별하는 시각적 개체도 일반적인 개체 수명 단계를 거칩니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로그래밍 및 응용 프로그램 모델에서는 이러한 단계를 일련의 이벤트로 노출합니다.  개체 수명 이벤트 측면에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 일반 요소, 창 요소, 탐색 호스트, 그리고 응용 프로그램 개체라는 네 가지 종류의 개체가 있습니다.  창 및 탐색 호스트는 시각적 개체\(요소\)라는 더 큰 그룹에도 포함됩니다.  이 항목에서는 모든 요소에 공통된 개체 수명 이벤트에 대해 설명하고 응용 프로그램 정의, 창 또는 탐색 호스트에 적용되는 특정 이벤트에 대해 소개합니다.  
  
<a name="common_events"></a>   
## 요소에 대한 공통 개체 수명 이벤트  
 모든 [WPF 프레임워크 수준](GTMT) 요소\(<xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>에서 파생되는 개체\)에는 <xref:System.Windows.FrameworkElement.Initialized>, <xref:System.Windows.FrameworkElement.Loaded> 및 <xref:System.Windows.FrameworkElement.Unloaded>라는 공통된 세 가지 개체 수명 이벤트가 있습니다.  
  
### Initialized  
 <xref:System.Windows.FrameworkElement.Initialized>는 가장 먼저 발생하며 개체 생성자를 호출하여 개체가 초기화되는 시점에 해당합니다.  이 이벤트는 초기화에 응답하여 발생하므로 이 이벤트가 발생하면 개체의 모든 속성이 설정되어 있음을 알 수 있습니다.  동적 리소스나 바인딩과 같은 식 사용의 경우는 예외입니다. 이러한 식은 평가되지 않은 식이 됩니다. 모든 속성이 설정되어 있어야 한다는 요구 사항으로 인해 태그에 정의된 중첩 요소에 의해 발생하는 일련의 <xref:System.Windows.FrameworkElement.Initialized> 이벤트는 요소 트리의 가장 아래에 있는 요소부터 시작하여 루트를 향해 부모 요소의 순서로 발생합니다.  순서가 이와 같은 이유는 부모\/자식 관계와 포함이 속성이고 따라서 부모는 속성을 채우는 자식 요소 또한 완전히 초기화되기 전에는 초기화를 보고할 수 없기 때문입니다.  
  
 <xref:System.Windows.FrameworkElement.Initialized> 이벤트에 대한 응답으로 처리기를 작성할 때는 처리기가 연결된 요소 트리\([논리 트리](GTMT) 또는 [시각적 트리](GTMT)\)의 다른 모든 요소가 만들어졌는지, 특히 부모 요소가 만들어지는지에 대해 어떤 것도 보장되지 않는다는 점을 고려해야 합니다.  멤버 변수가 null이거나 식 수준에서도 데이터 소스가 기본 바인딩으로 채워지지 않을 수도 있습니다.  
  
### Loaded  
 그 다음으로 <xref:System.Windows.FrameworkElement.Loaded>가 발생합니다.  <xref:System.Windows.FrameworkElement.Loaded> 이벤트는 최종 렌더링 전에, 레이아웃 시스템이 렌더링에 필요한 모든 값을 계산한 후에 발생합니다.  <xref:System.Windows.FrameworkElement.Loaded>가 발생하려면 요소가 포함되어 있는 논리 트리가 완전해야 하고 HWND 및 렌더링 화면을 제공하는 프레젠테이션 소스에 연결되어야 합니다.  표준 데이터 바인딩\(다른 속성 또는 직접 정의한 데이터 소스와 같은 로컬 소스에 대한 바인딩\)은 <xref:System.Windows.FrameworkElement.Loaded>가 발생하기 전에 발생합니다.  비동기 데이터 바인딩\(외부 또는 동적 소스\)이 발생할 수도 있지만 비동기라는 용어에서 유추할 수 있듯이 그 발생 여부를 보장할 수는 없습니다.  
  
 <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 발생시키는 메커니즘은 <xref:System.Windows.FrameworkElement.Initialized>와는 다릅니다.  <xref:System.Windows.FrameworkElement.Initialized> 이벤트는 전체 요소 트리의 직접적인 중재 없이 요소 별로 발생합니다.  반면 <xref:System.Windows.FrameworkElement.Loaded> 이벤트는 전체 요소 트리, 특히 [논리 트리](GTMT)의 중재를 통해 발생합니다.  트리의 모든 요소가 로드된 상태가 되면 먼저 루트 요소에서 <xref:System.Windows.FrameworkElement.Loaded> 이벤트가 발생한 다음  각 자식 요소에서 연속적으로 <xref:System.Windows.FrameworkElement.Loaded> 이벤트가 발생합니다.  
  
> [!NOTE]
>  이 동작은 겉으로는 [라우트된 이벤트](GTMT)에 대한 터널링과 비슷합니다.  하지만 이벤트에서 이벤트로 어떤 정보도 전달되지 않습니다.  각 이벤트는 항상 자신의 <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 처리할 기회를 가지며 이벤트 데이터를 처리된 것으로 표시해도 해당 요소가 아닌 다른 요소에는 어떠한 영향도 주지 않습니다.  
  
### Unloaded  
 <xref:System.Windows.FrameworkElement.Unloaded>는 마지막으로 발생하며 제거할 프레젠테이션 소스 또는 시각적 부모에 의해 시작됩니다.  <xref:System.Windows.FrameworkElement.Unloaded>가 발생하고 처리되고 나면 이벤트 소스 부모\(<xref:System.Windows.FrameworkElement.Parent%2A> 속성으로 결정됨\)에 해당하는 요소 또는 논리 트리나 시각적 트리의 위쪽에 있는 지정된 요소가 이미 해제되어 있을 수도 있습니다. 즉, 데이터 바인딩, 리소스 참조 및 스타일이 각자의 일반 값 또는 마지막으로 알려진 런타임 값으로 설정되어 있지 않을 수도 있습니다.  
  
<a name="application_model_elements"></a>   
## 개체 수명 이벤트 응용 프로그램 모델 요소  
 <xref:System.Windows.Application>, <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow> 및 <xref:System.Windows.Controls.Frame>은 요소에 대한 공통 개체 수명 이벤트를 기반으로 하는 응용 프로그램 모델 요소입니다.  이러한 요소는 특정 목적과 관련된 추가 이벤트를 사용하여 공통 개체 수명 이벤트를 확장합니다.  다음 항목에서 이에 대해 자세히 설명합니다.  
  
-   <xref:System.Windows.Application>: [응용 프로그램 관리 개요](../../../../docs/framework/wpf/app-development/application-management-overview.md).  
  
-   <xref:System.Windows.Window>: [WPF 창 개요](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md).  
  
-   <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow> 및 <xref:System.Windows.Controls.Frame>: [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
## 참고 항목  
 [종속성 속성 값 우선 순위](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)   
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)