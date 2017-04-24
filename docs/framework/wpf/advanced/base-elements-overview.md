---
title: "기본 요소 개요 | Microsoft Docs"
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
  - "기본 요소"
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 기본 요소 개요
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스 중에는 [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] 설명서에서 일반적으로 기본 요소 클래스라고 하는 네 가지 클래스에서 파생된 클래스가 많습니다.  이 네 가지 클래스는 <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement>, <xref:System.Windows.ContentElement> 및 <xref:System.Windows.FrameworkContentElement>입니다.  <xref:System.Windows.DependencyObject> 클래스도 <xref:System.Windows.UIElement> 및 <xref:System.Windows.ContentElement>의 공통 기본 클래스이므로 관련이 있습니다.  
  
   
  
<a name="base_apis"></a>   
## WPF 클래스의 기본 요소 API  
 경로는 다소 다르지만 <xref:System.Windows.UIElement> 및 <xref:System.Windows.ContentElement>는 모두 <xref:System.Windows.DependencyObject>에서 파생됩니다.  이 수준에서 분리되는 이유는 <xref:System.Windows.UIElement> 또는 <xref:System.Windows.ContentElement>가 사용자 인터페이스에서 사용되는 방식과 응용 프로그램에서 수행하는 역할을 처리하기 위해서입니다.  <xref:System.Windows.UIElement>의 클래스 계층 구조에도 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 기반이 되는 하위 수준의 그래픽 지원을 노출하는 <xref:System.Windows.Media.Visual> 클래스가 있습니다.  <xref:System.Windows.Media.Visual>은 독립적인 직사각형 화면 영역을 정의하여 렌더링 프레임워크를 제공합니다.  실제로 <xref:System.Windows.UIElement>는 대형 개체 모델을 지원하는 요소를 위한 것으로, 직사각형 화면 영역으로 표현할 수 있는 영역으로 렌더링 및 배치되고 콘텐츠 모델이 더 개방적일 경우에는 서로 다른 요소를 조합할 수 있도록 만들어졌습니다.  <xref:System.Windows.ContentElement>는 <xref:System.Windows.Media.Visual>에서 파생되지 않습니다. 이 모델에서는 판독기나 뷰어와 같은 다른 개체가 <xref:System.Windows.ContentElement>를 사용하여 요소를 해석한 다음 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 사용할 수 있는 완전한 <xref:System.Windows.Media.Visual>을 생성합니다.  특정 <xref:System.Windows.UIElement> 클래스는 콘텐츠 호스트로 사용되어야 합니다. 이러한 클래스는 하나 이상의 <xref:System.Windows.ContentElement> 클래스\(예: <xref:System.Windows.Controls.DocumentViewer>\)에 대해 호스팅과 렌더링을 제공합니다.  <xref:System.Windows.ContentElement>는 개체 모델이 더 작고 <xref:System.Windows.UIElement> 내에서 호스팅할 수 있는 텍스트, 정보 또는 문서 콘텐츠를 더 많이 처리하는 요소의 기본 클래스로 사용됩니다.  
  
### 프레임워크 수준 및 코어 수준  
 <xref:System.Windows.UIElement>는 <xref:System.Windows.FrameworkElement>의 기본 클래스로 사용되며 <xref:System.Windows.ContentElement>는 <xref:System.Windows.FrameworkContentElement>의 기본 클래스로 사용됩니다.  이러한 다음 수준의 클래스가 있는 이유는 [WPF 프레임워크 수준](GTMT)에서 분리되어 있는 [WPF 코어 수준](GTMT)을 지원하기 위한 것입니다. PresentationCore 및 PresentationFramework 어셈블리 사이에서 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 나누는 방법에도 이러한 구분이 존재합니다.  [WPF 프레임워크 수준](GTMT)에서는 프레젠테이션을 위한 레이아웃 관리자 구현을 비롯하여 기본적인 응용 프로그램 요구 사항을 완벽하게 지원할 수 있습니다.  [WPF 코어 수준](GTMT)에서는 추가 어셈블리의 오버헤드 없이 대부분의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용할 수 있습니다.  대부분의 전형적인 응용 프로그램 개발 시나리오에서는 이러한 수준 구분이 거의 문제가 되지 않습니다. 일반적인 경우에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 하나의 단일 구조로 인식하고 [WPF 프레임워크 수준](GTMT)과 [WPF 코어 수준](GTMT)을 구분하지 않아도 됩니다.  하지만 전체 솔루션에 이미 고유한 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 컴퍼지션과 레이아웃이 구현되어 있는 경우처럼 응용 프로그램 디자인에서 상당한 양의 [WPF 프레임워크 수준](GTMT) 기능을 대체하는 경우에는 이 수준을 구분해야 합니다.  
  
<a name="subclassing_elements"></a>   
## 파생시킬 요소 선택  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 확장하는 사용자 지정 클래스를 만드는 가장 실용적인 방법은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스 중에서 기존 클래스 계층 구조를 통해 필요한 기능을 가장 많이 얻을 수 있는 클래스를 파생시키는 것입니다.  이 단원에서는 상속할 클래스를 결정할 때 도움이 되는 가장 중요한 세 가지 요소 클래스의 기능에 대해 설명합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스를 파생시키는 가장 일반적인 이유 중 하나는 컨트롤을 구현하기 위해서인데, 이 경우 대개는 실용적인 클래스, 컨트롤 패밀리 기본 클래스 또는 적어도 <xref:System.Windows.Controls.Control> 기본 클래스를 파생시키는 것이 좋습니다.  몇 가지 지침과 실제 예제는 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)를 참조하십시오.  
  
 컨트롤을 만드는 것이 아니라 계층 구조에서 더 높은 수준에 있는 클래스를 파생시켜야 하는 경우 다음 단원을 지침으로 사용하여 각 기본 요소 클래스에 정의되어 있는 특성에 대해 알아볼 수 있습니다.  
  
 <xref:System.Windows.DependencyObject>에서 파생되는 클래스를 만드는 경우 다음 기능이 상속됩니다.  
  
-   <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A> 지원과 일반 속성 시스템 지원  
  
-   [종속성 속성](GTMT) 및 [종속성 속성](GTMT)으로 구현된 [연결된 속성](GTMT)을 사용하는 기능  
  
 <xref:System.Windows.UIElement>에서 파생되는 클래스를 만드는 경우 <xref:System.Windows.DependencyObject>를 통해 제공되는 기능 외에 다음 기능이 추가로 상속됩니다.  
  
-   애니메이션이 적용된 속성 값에 대한 기본적인 지원.  자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
-   기본적인 입력 이벤트 지원과 명령 지원.  자세한 내용은 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md) 및 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)를 참조하십시오.  
  
-   레이아웃 시스템에 정보를 제공하도록 재정의할 수 있는 가상 메서드  
  
 <xref:System.Windows.FrameworkElement>에서 파생되는 클래스를 만드는 경우 <xref:System.Windows.UIElement>를 통해 제공되는 기능 외에 다음 기능이 추가로 상속됩니다.  
  
-   스타일 및 스토리보드 지원.  자세한 내용은 <xref:System.Windows.Style> 및 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)를 참조하십시오.  
  
-   데이터 바인딩 지원.  자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  
  
-   동적 리소스 참조 지원.  자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
-   속성 값 상속 지원과 데이터 바인딩, 스타일 또는 레이아웃의 프레임워크 구현 같은 속성 상태를 프레임워크 서비스에 보고할 수 있는 메타데이터의 기타 플래그.  자세한 내용은 [프레임워크 속성 메타데이터](../../../../docs/framework/wpf/advanced/framework-property-metadata.md)를 참조하십시오.  
  
-   [논리 트리](GTMT) 개념.  자세한 내용은 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)를 참조하십시오.  
  
-   레이아웃에 영향을 주는 속성 변경 내용을 검색할 수 있는 <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> 재정의를 비롯한 레이아웃 시스템의 실용적인 [WPF 프레임워크 수준](GTMT) 구현 지원  
  
 <xref:System.Windows.ContentElement>에서 파생되는 클래스를 만드는 경우 <xref:System.Windows.DependencyObject>를 통해 제공되는 기능 외에 다음 기능이 추가로 상속됩니다.  
  
-   애니메이션 지원.  자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
-   기본적인 입력 이벤트 지원과 명령 지원.  자세한 내용은 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md) 및 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.FrameworkContentElement>에서 파생되는 클래스를 만드는 경우 <xref:System.Windows.ContentElement>를 통해 제공되는 기능 외에 다음 기능을 추가로 얻게 됩니다.  
  
-   스타일 및 스토리보드 지원.  자세한 내용은 <xref:System.Windows.Style> 및 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
-   데이터 바인딩 지원.  자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  
  
-   동적 리소스 참조 지원.  자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
-   속성 값 상속 지원과 데이터 바인딩, 스타일 또는 레이아웃의 프레임워크 구현 같은 속성 상태를 프레임워크 서비스에 보고할 수 있는 메타데이터의 기타 플래그.  자세한 내용은 [프레임워크 속성 메타데이터](../../../../docs/framework/wpf/advanced/framework-property-metadata.md)를 참조하십시오.  
  
-   <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 같은 레이아웃 시스템 수정 사항에 대한 액세스는 상속되지 않습니다.  레이아웃 시스템 구현은 <xref:System.Windows.FrameworkElement>에서만 사용할 수 있습니다.  대신 레이아웃에 영향을 주는 변경 내용을 검색할 수 있으며 이러한 변경 내용을 콘텐츠 호스트에 보고할 수 있는 <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> 재정의가 상속됩니다.  
  
 콘텐츠 모델은 다양한 클래스에 사용할 수 있도록 문서화되어 있습니다.  클래스의 콘텐츠 모델은 파생시킬 적절한 클래스를 찾을 때 고려해야 할 요소입니다.  자세한 내용은 [WPF 콘텐츠 모델](../../../../docs/framework/wpf/controls/wpf-content-model.md)을 참조하십시오.  
  
<a name="other_base_classes"></a>   
## 기타 기본 클래스  
  
### DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject>는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스레딩 모델을 지원하며 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램용으로 만든 모든 개체를 <xref:System.Windows.Threading.Dispatcher>와 연결할 수 있게 합니다.  <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject> 또는 <xref:System.Windows.Media.Visual>을 파생시키지 않더라도 이 스레딩 모델을 지원하려면 <xref:System.Windows.Threading.DispatcherObject>에서 파생시키는 것을 고려해야 합니다.  자세한 내용은 [스레딩 모델](../../../../docs/framework/wpf/advanced/threading-model.md)을 참조하십시오.  
  
### Visual  
 <xref:System.Windows.Media.Visual>은 2D 개체의 개념을 구현하는데, 이를 위해서는 일반적으로 직사각형 영역 안에 시각적으로 표현해야 합니다.  <xref:System.Windows.Media.Visual>의 실제 렌더링은 클래스 자체에 포함되지 않은 다른 클래스에서 수행되지만 <xref:System.Windows.Media.Visual> 클래스는 다양한 수준의 렌더링 프로세스에서 사용되는 알려진 형식을 제공합니다.  <xref:System.Windows.Media.Visual>은 적중 테스트를 구현하지만 적중 테스트 결과\(<xref:System.Windows.UIElement>에 있음\)를 보고하는 이벤트는 노출하지 않습니다.  자세한 내용은 [시각적 계층 프로그래밍](../../../../docs/framework/wpf/graphics-multimedia/visual-layer-programming.md)을 참조하십시오.  
  
### Freezable  
 <xref:System.Windows.Freezable>은 성능상의 이유로 불변 개체가 필요한 경우 개체의 복사본을 생성하는 방식을 제공하여 변경 가능한 개체의 불변성을 시뮬레이션합니다.  <xref:System.Windows.Freezable> 형식은 기하 도형, 브러시 등의 그래픽 요소와 애니메이션에 공통으로 사용할 수 있는 기반입니다.  특히, <xref:System.Windows.Freezable>은 <xref:System.Windows.Media.Visual>이 아니므로 다른 개체의 속성 값을 채우기 위해 <xref:System.Windows.Freezable>이 적용될 때 하위 속성이 되는 속성을 유지할 수 있는데 이러한 하위 속성은 렌더링에 영향을 미칠 수 있습니다.  자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable>은 애니메이션 컨트롤 레이어와 몇 가지 유틸리티 멤버를 추가하여 현재 애니메이션이 적용되는 속성과 그렇지 않은 속성을 구분하는 <xref:System.Windows.Freezable> 파생 클래스입니다.  
  
### 컨트롤  
 <xref:System.Windows.Controls.Control>은 사용되는 기술에 따라 컨트롤 또는 구성 요소로 다양하게 불리는 개체 형식에 대한 기본 클래스입니다.  일반적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 클래스는 UI 컨트롤을 직접 표현하거나 컨트롤 컴퍼지션에 밀접하게 관여하는 클래스입니다.  <xref:System.Windows.Controls.Control>이 제공하는 기본 기능은 컨트롤 템플릿 기능입니다.  
  
## 참고 항목  
 <xref:System.Windows.Controls.Control>   
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)   
 [WPF 아키텍처](../../../../docs/framework/wpf/advanced/wpf-architecture.md)