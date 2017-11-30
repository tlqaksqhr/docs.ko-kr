---
title: "기본 요소 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 270388b8e3dda0342ba74187d8dc45616d0e769d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="base-elements-overview"></a>기본 요소 개요
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스에는 [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] 설명서에서 일반적으로 기본 요소 클래스라고 하는 네 가지 클래스에서 파생된 클래스가 많습니다. 이러한 클래스는 <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement>, <xref:System.Windows.ContentElement>, 및 <xref:System.Windows.FrameworkContentElement>합니다. <xref:System.Windows.DependencyObject> 클래스도 관련 되는지, 둘 다의 공통 기본 클래스 이므로 <xref:System.Windows.UIElement> 및<xref:System.Windows.ContentElement>  
 
  
<a name="base_apis"></a>   
## <a name="base-element-apis-in-wpf-classes"></a>WPF 클래스의 기본 요소 API  
 둘 다 <xref:System.Windows.UIElement> 및 <xref:System.Windows.ContentElement> 에서 파생 된 <xref:System.Windows.DependencyObject>, 경로 다소 다르지만 통해 합니다. 이 수준에서 분할 방법을 다루는 <xref:System.Windows.UIElement> 또는 <xref:System.Windows.ContentElement> 사용자 인터페이스 및 응용 프로그램에서 서비스가 제공 용도 위해 기능에서 사용 됩니다. <xref:System.Windows.UIElement>또한 <xref:System.Windows.Media.Visual> 하위 그래픽 지원 내부 표시 하는 클래스는 클래스 계층 구조는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]합니다. <xref:System.Windows.Media.Visual>독립적인 직사각형 화면 영역을 정의 하 여 렌더링 프레임 워크를 제공 합니다. 실제로 <xref:System.Windows.UIElement> 은는 큰 개체 모델을 지 원하는 요소를 렌더링 하는 의도 및 콘텐츠 모델은 더 개방적, 서로 다른 수 있도록 직사각형 화면 영역으로 표현할 수 있는 영역으로 레이아웃은 요소의 조합 합니다. <xref:System.Windows.ContentElement>파생 되지 않습니다 <xref:System.Windows.Media.Visual>; 해당 모델은 한 <xref:System.Windows.ContentElement> 판독기나 뷰어 다음 요소를 해석 및 전체를 생성 하는 등 다른 작업에 의해 사용 될 것 <xref:System.Windows.Media.Visual> 에 대 한 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 사용 하도록 합니다. 특정 <xref:System.Windows.UIElement> 콘텐츠 호스트를: 하나 이상의 호스팅 및 렌더링을 제공 <xref:System.Windows.ContentElement> 클래스 (<xref:System.Windows.Controls.DocumentViewer> 은 이러한 클래스의 예제). <xref:System.Windows.ContentElement>내에서 약간 더 작게 개체 모델을 사용 하 여 요소에 대 한 기본 클래스와 더 많이 처리 정보를 텍스트 또는 문서 콘텐츠를 호스팅할 수로 사용 되는 <xref:System.Windows.UIElement>합니다.  
  
### <a name="framework-level-and-core-level"></a>프레임워크 수준 및 코어 수준  
 <xref:System.Windows.UIElement>에 대 한 기본 클래스 역할을 <xref:System.Windows.FrameworkElement>, 및 <xref:System.Windows.ContentElement> 에 대 한 기본 클래스 역할을 <xref:System.Windows.FrameworkContentElement>합니다. 이 다음 수준의 클래스를 사용하는 이유는 WPF 프레임워크 수준과 분리된 WPF 코어 수준을 지원하기 위한 것입니다. [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]가 PresentationCore 어셈블리와 PresentationFramework 어셈블리 간에 분할되는 방식에도 이러한 분할이 존재합니다. WPF 프레임워크 수준은 프레젠테이션을 위한 레이아웃 관리자의 구현을 포함하여 기본 응용 프로그램 요구 사항을 충족하는 보다 완벽한 솔루션을 제공합니다. WPF 코어 수준은 추가 어셈블리의 오버헤드 없이 대부분의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용할 수 있습니다. 가장 일반적인 응용 프로그램 개발 시나리오의 경우 이러한 수준 간의 구분이 거의 문제가 되지 않습니다. 일반적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 전체적으로 고려하여 WPF 프레임워크 수준과 WPF 코어 수준을 구분하지 않아도 됩니다. 전체 솔루션에 이미 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 컴퍼지션 및 레이아웃 구현이 있는 경우와 같이 응용 프로그램 디자인에서 WPF 프레임워크 수준 기능의 실질적인 상당한 부분을 대체하도록 선택하는 경우에는 이러한 수준 구분에 대해 알고 있어야 합니다.  
  
<a name="subclassing_elements"></a>   
## <a name="choosing-which-element-to-derive-from"></a>파생될 요소 선택  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]을 확장하는 사용자 지정 클래스를 만드는 가장 실질적인 방법은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스 중 하나에서 기존 클래스 계층 구조를 통해 필요한 기능을 가능한 많이 얻을 수 있는 클래스가 파생되는 것입니다. 이 섹션에서는 상속할 클래스를 결정하는 데 도움이 되는 가장 중요한 세 가지 요소 클래스와 함께 제공되는 기능을 나열합니다.  
  
 컨트롤을 구현 하는 경우 인데에서 파생 시키기 위한 일반적인 이유 중 하나는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스를 싶을 실용적인 컨트롤, 컨트롤 패밀리 기본 클래스에 해당 하는 클래스 또는 파생에서 최소한의 <xref:System.Windows.Controls.Control> 기본 클래스입니다. 몇 가지 지침과 실제 예제는 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)를 참조하세요.  
  
 컨트롤을 만들지 않고 계층 구조의 더 높은 수준에 있는 클래스에서 파생되어야 하는 경우 다음 섹션이 각 기본 요소 클래스에 정의된 특성에 대한 지침으로 사용됩니다.  
  
 파생 되는 클래스를 만들면 <xref:System.Windows.DependencyObject>, 다음과 같은 기능을 상속 합니다.  
  
-   <xref:System.Windows.DependencyObject.GetValue%2A>및 <xref:System.Windows.DependencyObject.SetValue%2A> 지원 및 일반 속성 시스템에서 지원 합니다.  
  
-   종속성 속성 및 종속성 속성으로 구현되는 연결된 속성을 사용할 수 있는 기능  
  
 파생 되는 클래스를 만들면 <xref:System.Windows.UIElement>를 상속 하는 이외에서 제공 하는 다음 기능이 <xref:System.Windows.DependencyObject>:  
  
-   애니메이션 속성 값에 대한 기본 지원 - 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하세요.  
  
-   기본 입력 이벤트 지원 및 명령 지원 - 자세한 내용은 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md) 및 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)를 참조하세요.  
  
-   레이아웃 시스템에 정보를 제공하도록 재정의될 수 있는 가상 메서드  
  
 파생 되는 클래스를 만들면 <xref:System.Windows.FrameworkElement>를 상속 하는 이외에서 제공 하는 다음 기능이 <xref:System.Windows.UIElement>:  
  
-   스타일 지정 및 스토리보드 지원 - 자세한 내용은 참조 <xref:System.Windows.Style> 및 [적기](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)합니다.  
  
-   데이터 바인딩 지원 - 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하세요.  
  
-   동적 리소스 참조 지원 - 자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하세요.  
  
-   속성 값 상속 지원 및 프레임워크 서비스(예: 데이터 바인딩, 스타일 또는 레이아웃의 프레임워크 구현)에 대한 속성 조건을 보고하는 데 도움이 되는 메타데이터의 기타 플래그 - 자세한 내용은 [프레임워크 속성 메타데이터](../../../../docs/framework/wpf/advanced/framework-property-metadata.md)를 참조하세요.  
  
-   논리 트리의 개념 - 자세한 내용은 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)를 참조하세요.  
  
-   레이아웃 시스템의 실제 WPF 프레임 워크 수준 구현에 대 한 지원을 포함 하는 <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> 재정의 검색할 수 있는 레이아웃에 영향을 해당 속성을 변경 합니다.  
  
 파생 되는 클래스를 만들면 <xref:System.Windows.ContentElement>를 상속 하는 이외에서 제공 하는 다음 기능이 <xref:System.Windows.DependencyObject>:  
  
-   애니메이션 지원 - 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하세요.  
  
-   기본 입력 이벤트 지원 및 명령 지원 - 자세한 내용은 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md) 및 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)를 참조하세요.  
  
 파생 되는 클래스를 만들면 <xref:System.Windows.FrameworkContentElement>를 제공한 다음 기능을 얻을 수 <xref:System.Windows.ContentElement>:  
  
-   스타일 지정 및 스토리보드 지원 - 자세한 내용은 참조 <xref:System.Windows.Style> 및 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)합니다.  
  
-   데이터 바인딩 지원 - 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하세요.  
  
-   동적 리소스 참조 지원 - 자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하세요.  
  
-   속성 값 상속 지원 및 프레임워크 서비스(예: 데이터 바인딩, 스타일 또는 레이아웃의 프레임워크 구현)에 대한 속성 조건을 보고하는 데 도움이 되는 메타데이터의 기타 플래그 - 자세한 내용은 [프레임워크 속성 메타데이터](../../../../docs/framework/wpf/advanced/framework-property-metadata.md)를 참조하세요.  
  
-   레이아웃 시스템 수정 사항에 대 한 액세스를 상속 하지 않습니다 (예: <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>). 레이아웃 시스템 구현에서 사용할 수 있는 <xref:System.Windows.FrameworkElement>합니다. 그러나 상속는 <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> 레이아웃을 미치고 참여할 콘텐츠 호스트에 보고 하는 속성에 대 한 변경 내용을 검색할 수 있는 재정의 합니다.  
  
 컨텐츠 모델은 다양한 클래스에서 사용할 수 있도록 문서화되어 있습니다. 클래스의 콘텐츠 모델은 파생될 적절한 클래스를 찾을 때 고려해야 할 요소입니다. 자세한 내용은 [WPF 콘텐츠 모델](../../../../docs/framework/wpf/controls/wpf-content-model.md)을 참조하세요.  
  
<a name="other_base_classes"></a>   
## <a name="other-base-classes"></a>기타 기본 클래스  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject>에 대 한 지원을 제공는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스레딩 모델 및에 대 한 모든 개체를 만들 수 있도록 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 연관 되어야 하는 응용 프로그램은 <xref:System.Windows.Threading.Dispatcher>합니다. 파생 되지 않은 경우에 <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject>, 또는 <xref:System.Windows.Media.Visual>에서 파생 하는 것이 좋습니다 <xref:System.Windows.Threading.DispatcherObject> 사용 하려면이 스레딩 모델을 지원 합니다. 자세한 내용은 [스레딩 모델](../../../../docs/framework/wpf/advanced/threading-model.md)을 참조하세요.  
  
### <a name="visual"></a>시각적 개체  
 <xref:System.Windows.Media.Visual>일반적으로 직사각형 영역에 대 한 시각적 표시를 필요로 하는 2D 개체의 개념을 구현 합니다. 실제 렌더링 한 <xref:System.Windows.Media.Visual> (이 자체 포함)는 다른 클래스에서 발생 하지만 <xref:System.Windows.Media.Visual> 클래스는 다양 한 수준에서 렌더링 프로세스에서 사용 되는 알려진된 형식을 제공 합니다. <xref:System.Windows.Media.Visual>적중 테스트를 구현 하지만 적중 테스트 결과 보고 하는 이벤트를 노출 하지 않습니다 (이러한 데이터베이스는 <xref:System.Windows.UIElement>). 자세한 내용은 [시각적 계층 프로그래밍](../../../../docs/framework/wpf/graphics-multimedia/visual-layer-programming.md)을 참조하세요.  
  
### <a name="freezable"></a>Freezable  
 <xref:System.Windows.Freezable>변경할 수 없는 개체가 필요한 또는 성능상의 이유로 필요한 경우 개체의 복사본을 생성 하는 방법을 제공 하 여 변경할 수 있는 개체의 불변성을 시뮬레이션 합니다. <xref:System.Windows.Freezable> 형식은 기본 특정 기 하 도형 및 브러시도 애니메이션 같은 그래픽 요소를 제공 합니다. 특히, 한 <xref:System.Windows.Freezable> 않습니다는 <xref:System.Windows.Media.Visual>; 하위 속성이 포함 되는 속성을 포함할 수 있습니다 때는 <xref:System.Windows.Freezable> 다른 개체의 속성 값이 입력에 적용 되 이러한 하위 속성이 렌더링에 영향을 줄 수 있습니다. 자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하세요.  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable>이 <xref:System.Windows.Freezable> 특히 애니메이션 컨트롤 계층에서에서 추가 하거나 일부 유틸리티 멤버 현재 애니메이션 적용된 속성을 구분할 수 있도록 되는 속성과 클래스를 파생 합니다.  
  
### <a name="control"></a>컨트롤  
 <xref:System.Windows.Controls.Control>컨트롤 또는 구성 요소는 기술에 따라 다양 표현 되는 개체의 형식에 대 한 원하는 기본 클래스가입니다. 일반적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 클래스는 UI 컨트롤을 직접 나타내거나 컨트롤 컴퍼지션에 밀접하게 참여하는 클래스입니다. 기본 기능은 <xref:System.Windows.Controls.Control> 컨트롤 템플릿 기능입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Control>  
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [WPF 아키텍처](../../../../docs/framework/wpf/advanced/wpf-architecture.md)
