---
title: "WPF 아키텍처 | Microsoft Docs"
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
  - "선호도 스레드"
  - "아키텍처"
  - "연결된 속성"
  - "클래스, System.Object"
  - "클래스, System.Threading.DispatcherObject"
  - "클래스, System.Windows.Controls.Control"
  - "클래스, System.Windows.DependencyObject"
  - "클래스, System.Windows.FrameworkElement"
  - "클래스, System.Windows.Media.Visual"
  - "클래스, System.Windows.UIElement"
  - "CommandBindings"
  - "구성 요소, unmanaged"
  - "Control 클래스"
  - "데이터 템플릿"
  - "DependencyObject 클래스"
  - "DispatcherObject 클래스"
  - "FrameworkElement 클래스"
  - "INotifyPropertyChange 인터페이스"
  - "인터페이스, INotifyPropertyChange"
  - "milcore"
  - "페인터의 알고리즘"
  - "속성, 연결됨"
  - "스토리보드"
  - "System.Object 클래스"
  - "System.Threading.DispatcherObject 클래스"
  - "System.Windows.Controls.Control 클래스"
  - "System.Windows.DependencyObject 클래스"
  - "System.Windows.FrameworkElement 클래스"
  - "System.Windows.Media.Visual 클래스"
  - "System.Windows.UIElement 클래스"
  - "스레드, 선호도"
  - "UIElement 클래스"
  - "관리되지 않는 구성 요소"
  - "Visual 클래스"
ms.assetid: 8579c10b-76ab-4c52-9691-195ce02333c8
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# WPF 아키텍처
이 항목에서는 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 클래스 계층의 둘러보기를 제공합니다.  이 항목은 대부분의 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 주요 하위 시스템을 다루며 이들이 어떻게 상호 작용하는지를 설명하며,  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 설계자가 선택한 몇 가지 사항에 대해서 자세히 설명합니다.  
  
   
  
<a name="System_Object"></a>   
## System.Object  
 기본 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 프로그래밍 모델은 관리 코드를 통해 노출됩니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 초기 디자인 단계에서는 시스템의 관리되는 구성 요소와 관리되지 않는 구성 요소를 정확하게 구분하는 방법에 대한 많은 논쟁이 있었습니다.  [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]에서는 보다 생산적이며 강력한 개발 작업을 수행하는 데 유용한 여러 기능\(메모리 관리, 오류 처리, 공용 형식 시스템 등\)을 제공하지만 이러한 이점에는 대가가 따릅니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 주요 구성 요소는 아래 그림에 설명되어 있습니다.  다이어그램의 빨간색 섹션\(PresentationFramework, PresentationCore 및 milcore\)은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 주요 코드 부분입니다.  이 중에서 하나\(milcore\)만 관리되지 않는 구성 요소입니다.  milcore는 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)]와의 긴밀한 통합을 위해 비관리 코드로 작성되어 있습니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서의 모든 디스플레이는 [!INCLUDE[TLA2#tla_dx](../../../../includes/tla2sharptla-dx-md.md)] 엔진을 통해 수행되므로 효율적인 하드웨어 및 소프트웨어 렌더링을 허용합니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에는 메모리 및 실행에 대한 세부적인 제어도 필요합니다.  milcore에 있는 컴포지션 엔진은 성능의 영향을 크게 받으므로 성능을 높이기 위해 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]의 여러 이점을 포기해야 했습니다.  
  
 ![.NET Framework 내 WPF의 위치](../../../../docs/framework/wpf/advanced/media/wpf-architect1.png "wpf\_architect1")  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 관리되는 부분과 관리되지 않는 부분 간 통신에 대해서는 이 항목의 뒷부분에서 설명합니다.  관리되는 프로그래밍 모델의 나머지 부분은 아래에 설명되어 있습니다.  
  
<a name="System_Threading_DispatcherObject"></a>   
## System.Threading.DispatcherObject  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에 있는 대부분의 개체는 동시성 및 스레딩을 처리하기 위한 기본 구문을 제공하는 <xref:System.Windows.Threading.DispatcherObject>에서 파생됩니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 디스패처에 의해 구현된 메시징 시스템을 기반으로 합니다.  이는 친숙한 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 메시지 펌프와 유사하게 작동합니다. 사실 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 디스패처는 User32 메시지를 사용하여 크로스 스레드 호출을 수행합니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 동시성을 논의할 때는 두 가지 핵심 개념인 디스패처와 스레드 선호도를 반드시 이해해야 합니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 디자인 단계에서 목표는 단일 실행 스레드로 이동하되 스레드가 아닌 "선호" 모델로 이동하는 것이었습니다.  스레드 선호도는 구성 요소가 마치 실행 스레드인 것처럼 일부 유형의 상태를 저장할 때 발생합니다.  이에 대한 가장 일반적인 형태는 TLS\(스레드 로컬 저장소\)를 사용하여 상태를 저장하는 것입니다.  스레드 선호도는 각 논리적 실행 스레드가 운영 체제에서 하나의 실제 스레드에만 소속될 수 있도록 합니다. 따라서 메모리를 많이 소비할 수 있습니다.  결국 WPF의 스레딩 모델은 스레드 선호도가 있는 단일 스레딩된 실행의 기존 User32 스레딩 모델과 계속 동기화됩니다.  이에 대한 주요 이유는 상호 운용성 때문입니다. [!INCLUDE[TLA2#tla_ole2.0](../../../../includes/tla2sharptla-ole2-0-md.md)], 클립보드, Internet Explorer 등의 시스템의 경우 모두 STA\(단일 스레드 선호도\) 실행이 필요합니다.  
  
 STA 스레딩이 포함된 개체가 있다면 스레드 간에 통신하고 올바른 스레드에 있는지를 확인할 수 있는 방법이 필요합니다.  여기에서 디스패처의 역할이 필요합니다.  디스패처는 우선 순위가 지정된 여러 개의 큐가 있는 기본 메시지 디스패치 시스템입니다.  메시지의 예로 원시 입력 알림\(마우스 이동\), 프레임워크 기능\(레이아웃\) 또는 사용자 명령\(이 메서드 실행\)을 들 수 있습니다.  <xref:System.Windows.Threading.DispatcherObject>에서 파생하여 STA 동작이 있는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 개체를 만들면 생성 시 디스패처에 포인터가 지정됩니다.  
  
<a name="System_Windows_DependencyObject"></a>   
## System.Windows.DependencyObject  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 빌드하는 데 사용된 기본 아키텍처 방법 중 하나는 메서드나 이벤트보다 속성을 선호하는 것이었습니다.  속성은 선언적이며 동작 대신 의도를 보다 쉽게 지정할 수 있습니다.  또한 모델 중심 또는 데이터 중심의 시스템을 지원하여 사용자 인터페이스 콘텐츠를 표시했습니다.  이 방법을 통해 응용 프로그램의 동작을 보다 효과적으로 제어하기 위해 사용자가 바인딩할 수 있는 것보다 더 많은 속성을 의도적으로 만들 수 있었습니다.  
  
 시스템에서 더 많은 부분을 속성에서 제어할 수 있게 만들기 위해 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]이 제공하는 것보다 다양한 속성 시스템이 필요했습니다.  간단한 예로 변경 알림을 들 수 있습니다.  양방향 바인딩을 사용하기 위해서는 바인드의 양쪽이 변경 알림을 지원해야 합니다.  동작이 속성 값에 연결되려면 속성 값이 변경될 때 알림을 받아야 합니다.  [!INCLUDE[TLA#tla_netframewk](../../../../includes/tlasharptla-netframewk-md.md)]에는 개체가 변경 알림을 게시할 수 있는 **INotifyPropertyChange** 인터페이스가 있습니다. 하지만 이 인터페이스는 선택 사항입니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 <xref:System.Windows.DependencyObject> 형식에서 파생된 보다 다양한 속성 시스템을 제공합니다.  속성 시스템은 속성 식 간의 종속성을 추적하고 종속성이 변경될 때 속성 값의 유효성을 자동으로 다시 검사하는 면에서 진정한 "종속성" 속성 시스템입니다.  예를 들어 <xref:System.Windows.Controls.Control.FontSize%2A>와 같이 상속하는 속성이 있는 경우에는 값을 상속하는 요소의 부모에서 속성이 변경되면 시스템이 자동으로 업데이트됩니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 속성 시스템의 기반은 속성 식의 개념입니다.  이 첫 릴리스의 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 속성 식 시스템이 닫혀 있고 식이 모두 프레임워크의 일부로 제공됩니다.  속성 시스템에 하드 코드된 상속, 스타일 설정 또는 데이터 바인딩이 없고 대신 프레임워크 내의 이후 계층에 의해 제공되는 이유는 식 때문입니다.  
  
 속성 시스템은 밀도가 낮은 속성 값 저장소도 제공합니다.  개체에 수십 또는 수백 개의 속성이 있을 수 있고 대부분의 값은 기본 상태\(상속됨, 스타일에 의해 설정됨 등\)로 되어 있으므로 개체의 모든 인스턴스에서 모든 속성을 정의할 필요는 없습니다.  
  
 속성 시스템의 마지막 새 기능은 [연결된 속성](GTMT)이라는 개념입니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 요소는 컴퍼지션 및 구성 요소 재사용 원칙에 따라 빌드됩니다.  <xref:System.Windows.Controls.Grid> 레이아웃 요소와 같은 일부 포함 요소가 해당 동작을 제어하기 위해 자식 요소에 대한 추가 데이터를 필요로 하는 경우가 종종 있습니다\(예: 행\/열 정보\).  이러한 모든 속성을 모든 요소와 연결하는 대신 개체가 다른 개체에 대한 속성 정의를 제공할 수 있습니다.  이는 JavaScript의 "expando" 기능과 유사합니다.  
  
<a name="System_Windows_Media_Visual"></a>   
## System.Windows.Media.Visual  
 시스템이 정의되면 다음 단계는 화면에서 픽셀을 그리는 것입니다.  <xref:System.Windows.Media.Visual> 클래스는 시각적 개체 트리를 빌드하기 위해 각각의 선택적인 포함 그리기 명령과 해당 명령을 렌더링하는 방법\(클리핑, 변환 등\)에 대한 메타데이터를 제공합니다.  <xref:System.Windows.Media.Visual>은 매우 간단하고 유연하므로 대부분의 기능에 공개 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 노출이 없고 이러한 기능이 보호되는 콜백 기능에 크게 의존합니다.  
  
 <xref:System.Windows.Media.Visual>은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 컴퍼지션 시스템의 진정한 진입점입니다.  <xref:System.Windows.Media.Visual>은 두 하위 시스템인 관리되는 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]와 관리되지 않는 milcore 사이의 연결 지점입니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 milcore에 의해 관리되는 관리되지 않는 데이터 구조를 이동하여 데이터를 표시합니다.  컴포지션 노드라고 하는 이 구조는 각 노드에 렌더링 명령이 있는 계층적 디스플레이 트리를 나타냅니다.  아래 그림의 오른쪽에 있는 이 트리에는 메시징 프로토콜을 통해서만 액세스할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 프로그래밍할 때는 이 메시징 프로토콜을 통해 컴포지션 트리와 내부적으로 통신하는 <xref:System.Windows.Media.Visual> 요소 및 파생 형식을 만듭니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에 있는 각 <xref:System.Windows.Media.Visual>이 하나 또는 여러 개의 컴포지션 노드를 만들거나 하나도 만들지 않을 수 있습니다.  
  
 ![Windows Presentation Foundation 시각적 트리](../../../../docs/framework/wpf/advanced/media/wpf-architecture2.png "wpf\_architecture2")  
  
 여기에서 알아 두어야 할 매우 중요한 아키텍처 정보가 있습니다. 그것은 바로 시각 요소 및 그리기 명령의 전체 트리가 캐시된다는 사실입니다.  그래픽 측면에서 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 유지된 렌더링 시스템을 사용합니다.  이로 인해 시스템은 사용자 코드에 대한 콜백을 차단하는 컴포지션 시스템 없이 높은 화면 주사율로 다시 그릴 수 있습니다.  따라서 응답하지 않는 응용 프로그램이 나타나지 않게 됩니다.  
  
 다이어그램에서 놓치기 쉬운 또 다른 중요한 정보는 시스템이 실제로 컴포지션을 수행하는 방법입니다.  
  
 User32 및 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)]에서 시스템은 즉각적인 모드 클리핑 시스템으로 작동합니다.  구성 요소를 렌더링해야 할 때는 시스템이 구성 요소가 픽셀과 닿을 수 없는 곳의 바깥에 클리핑 경계를 설정한 다음 구성 요소가 해당 상자에서 픽셀을 그려야 합니다.  이 시스템은 무언가 변경될 때 영향을 받는 구성 요소만 처리하면 되기 때문에 메모리가 제약된 시스템에서 잘 작동합니다. 단일 픽셀의 색상에 두 개의 구성 요소가 관여하는 경우는 없습니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 "페인터 알고리즘" 그리기 모델을 사용합니다.  즉, 각 구성 요소를 클리핑하는 대신 각 구성 요소가 디스플레이의 뒤쪽에서 앞쪽으로 렌더링해야 합니다.  따라서 각 구성 요소가 이전 구성 요소의 디스플레이에 그릴 수 있습니다.  이 모델의 장점은 복잡하고 부분적인 투명 모양이 가능하다는 것입니다.  User32\/ [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)]를 만들었을 때와 달리 오늘날의 현대적인 그래픽 하드웨어에서는 이 모델이 상대적으로 빠릅니다.  
  
 앞에서 언급했듯이 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 핵심 방법은 보다 선언적인 "속성 중심의" 프로그래밍 모델로 이동하는 것입니다.  시각적 시스템에서는 두 가지 흥미로운 장소에서 이러한 이동이 눈에 띕니다.  
  
 첫째, 유지된 모드 그래픽 시스템을 고려해 보면 명령적 DrawLine\/DrawLine 형식 모델에서 데이터 지향 모델인 new Line\(\)\/new Line\(\)으로 이동하는 것입니다.  이러한 데이터 중심 렌더링으로의 이동으로 인해 속성을 사용하여 그리기 지침에 대한 복잡한 작업을 표현할 수 있습니다.  <xref:System.Windows.Media.Drawing>에서 파생되는 형식은 실제로 렌더링해야 할 개체 모델입니다.  
  
 둘째, 애니메이션 시스템을 평가할 경우 거의 모든 내용이 선언적인 것을 볼 수 있습니다.  개발자가 다음 위치 또는 다음 색상을 계산하도록 하는 대신 애니메이션을 애니메이션 개체의 속성 집합으로 표현할 수 있습니다.  그런 다음 이 애니메이션은 개발자 또는 디자이너의 의도\(예: 5초 이내에 이 단추를 다른 곳으로 이동\)를 표현할 수 있으며 시스템은 이를 완료하기 위한 가장 효율적인 방법을 파악할 수 있습니다.  
  
<a name="System_Windows_UIElement"></a>   
## System.Windows.UIElement  
 <xref:System.Windows.UIElement>는 레이아웃, 입력 및 이벤트를 비롯한 핵심 하위 시스템을 정의합니다.  
  
 레이아웃은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 핵심 개념입니다.  대부분의 시스템에는 고정된 레이아웃 모델 집합\(HTML은 세 가지 레이아웃 모델인 흐름, 절대 및 테이블을 지원함\)이 있거나 레이아웃 모델이 아예 없습니다\(User32는 실제로 절대 위치 지정만 지원함\).  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 개발자 및 디자이너가 명령적 논리 대신 속성 값을 중심으로 운영될 수 있는 유연하고 확장 가능한 레이아웃 모델을 원한다는 가정에서 출발했습니다.  <xref:System.Windows.UIElement> 수준에서 레이아웃의 기본 계약이 도입되었습니다. 즉, <xref:System.Windows.UIElement.Measure%2A> 및 <xref:System.Windows.UIElement.Arrange%2A>가 있는 2단계 모델이 전달됩니다.  
  
 <xref:System.Windows.UIElement.Measure%2A>는 구성 요소가 차지할 크기를 결정합니다.  최적의 위치 및 크기를 결정하기 위해 부모 요소가 자식에게 여러 번 측정을 요구할 수 있는 상황이 많기 때문에 <xref:System.Windows.UIElement.Arrange%2A>와 별도의 단계입니다.  부모 요소가 자식 요소에게 측정을 요구한다는 사실은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 또 다른 주요 방법인 콘텐츠에 맞는 크기를 나타냅니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 모든 컨트롤은 콘텐츠의 기본 크기에 따라 크기가 조정됩니다.  이에 따라 지역화가 훨씬 간단해지고 크기 조정에 따른 요소의 동적 레이아웃이 가능합니다.  <xref:System.Windows.UIElement.Arrange%2A> 단계로 인해 부모가 각 자식을 배치하고 최종 크기를 결정할 수 있습니다.  
  
 대개 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 출력 측면, 즉 <xref:System.Windows.Media.Visual> 및 관련 개체에 대해 많은 시간을 할애하여 설명하지만  입력 측면에도 새로운 내용이 매우 많습니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 입력 모델에서 가장 근본적인 변화는 입력 이벤트가 시스템을 통해 라우트되는 일관된 모델입니다.  
  
 입력은 커널 모드 장치 드라이버의 신호로 시작되며 Windows 커널 및 User32가 관련된 복잡한 프로세스를 통해 올바른 프로세스 및 스레드로 라우트됩니다.  입력에 해당하는 User32 메시지가 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]로 라우트되면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 원시 입력 메시지로 변환되고 디스패처로 전송됩니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 원시 입력 이벤트를 여러 개의 실제 이벤트로 변환하여 "MouseEnter"와 같은 기능이 시스템의 낮은 수준에서 구현될 수 있도록 합니다. 이 경우 이러한 기능의 배달이 보장됩니다.  
  
 각 입력 이벤트는 최소한 두 개의 이벤트인 "미리 보기" 이벤트와 실제 이벤트로 변환됩니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에 있는 모든 이벤트는 요소 트리를 통해 라우트되는 개념입니다.  이벤트는 트리의 대상에서 시작하여 루트로 위로 이동할 경우에는 "버블링"된다고 하고, 루트에서 시작하여 대상으로 아래로 이동할 경우에는 "터널링"된다고 합니다.  입력 미리 보기 이벤트는 터널링되어 트리에 있는 각 요소가 이벤트를 필터링하거나 이벤트에 대한 작업을 수행할 수 있는 기회를 제공합니다.  그런 다음 일반\(미리 보기 아님\) 이벤트가 대상에서 루트로 위로 버블링됩니다.  
  
 이러한 터널링 단계와 버블링 단계 간의 구분으로 인해 컴포지션 영역에서 키보드 액셀러레이터 같은 기능이 일관된 방식으로 구현됩니다.  User32에서는 지원하고자 하는 모든 가속기를 포함하는 단일 글로벌 테이블을 보유하여 키보드 액셀러레이터를 구현합니다\(예: "새로 만들기"에 Ctrl\+N 매핑\).  응용 프로그램의 디스패처에서는 User32의 입력 메시지를 탐지하고 등록된 액셀러레이터와 일치하는 것이 있는지 확인하는 **TranslateAccelerator**를 호출합니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 시스템이 완전히 "구성 가능"하기 때문에, 즉 모든 요소가 키보드 액셀러레이터를 처리하고 사용할 수 있기 때문에 이 방법이 작동하지 않습니다.  입력에 이 2단계 모델을 사용하면 구성 요소가 자체적인 "TranslateAccelerator"를 구현할 수 있습니다.  
  
 이 단계를 더욱 발전시키기 위해 <xref:System.Windows.UIElement>는 CommandBindings라는 개념도 도입합니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 명령 시스템에서는 개발자가 명령 끝점의 측면에서 기능을 정의할 수 있습니다. 즉, <xref:System.Windows.Input.ICommand>를 구현하는 기능을 정의할 수 있습니다.  명령 바인딩을 통해 요소가 입력 제스처\(예: Ctrl\+N\)와 명령\(예: 새로 만들기\) 사이의 매핑을 정의할 수 있습니다.  입력 제스처와 명령 정의는 모두 확장이 가능하며 사용 중에 함께 연결될 수 있습니다.  최종 사용자가 응용 프로그램 내에서 사용할 키 바인딩을 사용자 지정하는 작업 등이 간단해집니다.  
  
 항목의 이 시점에서는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 "핵심" 기능, 즉 PresentationCore 어셈블리에 구현된 기능에 초점이 맞춰집니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]를 빌드할 때는 기초 부분\(예: **Measure** 및 **Arrange**과의 레이아웃 계약\)과 프레임워크 부분\(예: <xref:System.Windows.Controls.Grid> 같은 특정 레이아웃의 구현\) 사이가 완전히 구분되는 것이 원하는 결과였습니다.  목표는 외부 개발자가 필요한 경우 자체적인 프레임워크를 만들 수 있도록 스택의 아래쪽에 확장 가능성 지점을 제공하는 것이었습니다.  
  
<a name="System_Windows_FrameworkElement"></a>   
## System.Windows.FrameworkElement  
 <xref:System.Windows.FrameworkElement>는 두 가지 방식으로 살펴 볼 수 있는데  한 가지는 여기서 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 낮은 계층에 도입되는 하위 시스템에 대한 정책 및 사용자 지정 집합을 소개한다는 것이며,  다른 한 가지는 새로운 하위 시스템 집합을 소개한다는 것입니다.  
  
 <xref:System.Windows.FrameworkElement>에 의해 도입된 기본 정책은 응용 프로그램 레이아웃에 대한 것입니다.  <xref:System.Windows.FrameworkElement>는 <xref:System.Windows.UIElement>에 의해 도입된 기본 레이아웃 계약을 기반으로 하며 레이아웃 제작자가 속성 중심 레이아웃 의미 체계 집합의 일관성을 보다 쉽게 유지할 수 있도록 레이아웃 "슬롯" 개념을 추가합니다.  <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>, <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> 등의 속성은 레이아웃 컨테이너 내의 일관된 동작을 <xref:System.Windows.FrameworkElement>에서 파생된 모든 구성 요소에 제공합니다.  
  
 <xref:System.Windows.FrameworkElement>는 보다 쉬운 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 노출을 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 핵심 계층에 있는 여러 기능에 제공합니다.  예를 들어 <xref:System.Windows.FrameworkElement>를 사용하면 <xref:System.Windows.FrameworkElement.BeginStoryboard%2A> 메서드를 통해 애니메이션에 직접 액세스할 수 있습니다.  <xref:System.Windows.Media.Animation.Storyboard>는 속성 집합에 대해 여러 애니메이션을 스크립팅할 수 있는 방법을 제공합니다.  
  
 <xref:System.Windows.FrameworkElement>가 도입하는 가장 중요한 두 가지 항목은 데이터 바인딩 및 스타일입니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 데이터 바인딩 시스템은 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 또는 [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)]을 사용하여 응용 프로그램 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]를 만든 사용자에게 비교적 친숙해야 합니다.  이러한 각 시스템에는 특정 요소에 있는 하나 이상의 속성을 데이터 조각에 바인딩하려고 한다는 것을 간단하게 표현할 수 있는 방법이 있습니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 속성 바인딩, 변환 및 목록 바인딩을 완전히 지원합니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 데이터 바인딩의 가장 흥미로운 기능 중 하나는 새로 도입된 데이터 템플릿입니다.  데이터 템플릿을 사용하면 어떤 데이터 조각을 시각화해야 하는지를 선언적으로 명시할 수 있습니다.  데이터에 바인딩할 수 있는 사용자 지정 사용자 인터페이스를 만드는 대신 역으로, 생성될 디스플레이를 데이터가 결정하도록 할 수 있습니다.  
  
 스타일 지정은 실제로는 데이터 바인딩의 간단한 형태입니다.  스타일 지정을 사용하면 공유된 정의에 있는 속성 집합을 하나 이상의 요소 인스턴스에 바인딩할 수 있습니다.  스타일은 명시적 참조\(<xref:System.Windows.FrameworkElement.Style%2A> 속성 설정\)를 통해 또는 스타일과 요소의 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 형식을 연결하는 암시적 방법을 통해 요소에 적용됩니다.  
  
<a name="System_Windows_Controls_Control"></a>   
## System.Windows.Controls.Control  
 컨트롤의 가장 중요한 기능은 템플릿 설정입니다.  WPF의 컴퍼지션 시스템을 유지된 모드 렌더링 시스템으로 생각하는 경우에는 템플릿 설정을 통해 컨트롤이 매개 변수가 있는 선언적 방식으로 렌더링되고 있음을 설명할 수 있습니다.  <xref:System.Windows.Controls.ControlTemplate>은 실제로는 자식 요소 집합을 만들기 위한 스크립트가 컨트롤에 의해 제공되는 속성에 대한 바인딩과 결합된 것일 뿐입니다.  
  
 <xref:System.Windows.Controls.Control>은 <xref:System.Windows.Controls.Control.Foreground%2A>, <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Padding%2A> 등의 스톡 속성 집합을 제공합니다. 템플릿 제작자는 이러한 속성 집합을 사용하여 컨트롤의 디스플레이를 사용자 지정할 수 있습니다.  컨트롤 구현은 데이터 모델 및 상호 작용 모델을 제공합니다.  상호 작용 모델은 명령 집합\(예: 창 닫기\)과 입력 제스처에 대한 바인딩\(예: 창의 위쪽 모서리에 있는 빨간색 X 클릭\)을 정의합니다.  데이터 모델은 상호 작용 모델을 사용자 지정하거나 디스플레이를 사용자 지정하기 위한 속성 집합을 제공합니다. 사용자 지정 대상은 템플릿에 의해 결정됩니다.  
  
 데이터 모델\(속성\), 상호 작용 모델\(명령 및 이벤트\) 및 디스플레이 모델\(템플릿\)이 이렇게 구분됨에 따라 컨트롤의 모양 및 동작을 완전히 사용자 지정할 수 있습니다.  
  
 컨트롤 데이터 모델의 공통적인 측면은 콘텐츠 모델입니다.  <xref:System.Windows.Controls.Button> 같은 컨트롤에서 <xref:System.Object> 형식의 "Content"라는 속성을 볼 수 있습니다.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 및 [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)]에서 이 속성은 일반적으로 문자열이지만 단추에 입력할 수 있는 콘텐츠 유형이 제한됩니다.  단추의 콘텐츠는 간단한 문자열, 복잡한 데이터 개체 또는 전체 요소 트리일 수가 있습니다.  데이터 개체의 경우 데이터 템플릿이 사용되어 디스플레이를 구성합니다.  
  
<a name="Summary"></a>   
## 요약  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 동적인 데이터 중심 프레젠테이션 시스템을 만들 수 있도록 디자인되었습니다.  시스템의 모든 부분은 동작을 구현하는 속성 집합을 통해 개체를 만듭니다.  데이터 바인딩은 시스템의 기초적인 부분이며 모든 계층과 통합됩니다.  
  
 일반 응용 프로그램은 디스플레이를 만든 다음 일부 데이터에 바인딩합니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서는 컨트롤에 대한 모든 것과 디스플레이의 모든 측면이 일부 데이터 바인딩 형식에 의해 생성됩니다.  단추 내의 텍스트는 단추 내에 구성된 컨트롤을 만들고 해당 디스플레이를 단추의 콘텐츠 속성에 바인딩하여 표시됩니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 기반 응용 프로그램의 개발을 시작하면 매우 친숙하다는 느낌을 받을 것입니다.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 또는 [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)]을 사용하는 것과 거의 똑같은 방법으로 속성을 설정하고, 개체를 사용하고, 데이터를 바인딩할 수 있습니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 아키텍처를 보다 자세히 살펴 보면 근본적으로 데이터를 응용 프로그램의 핵심 요소로 처리하는 보다 다양한 응용 프로그램을 만들 수 있는 가능성이 있다는 사실을 발견하게 될 것입니다.  
  
## 참고 항목  
 <xref:System.Windows.Media.Visual>   
 <xref:System.Windows.UIElement>   
 <xref:System.Windows.Input.ICommand>   
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.Threading.DispatcherObject>   
 <xref:System.Windows.Input.CommandBinding>   
 <xref:System.Windows.Controls.Control>   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [레이아웃](../../../../docs/framework/wpf/advanced/layout.md)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)