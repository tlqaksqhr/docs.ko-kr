---
title: "라우트된 이벤트를 처리된 것으로 표시 및 클래스 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tunneling events [WPF]
- class listeners [WPF]
- listeners [WPF]
- Preview routed events [WPF]
- instance listeners [WPF]
- events [WPF], bubbling
- suppressing events [WPF]
- routed events [WPF], Preview
- composited controls [WPF]
- events [WPF], tunneling
- routed events [WPF], marking as handled
- controls [WPF], compositing
- events [WPF], suppressing
- bubbling events [WPF]
ms.assetid: 5e745508-4861-4b48-b5f6-5fc7ce5289d2
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0ec6bd76b6254b44dfacfd7f3d29341ece0a78f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="marking-routed-events-as-handled-and-class-handling"></a>라우트된 이벤트를 처리된 것으로 표시 및 클래스 처리
라우트된 이벤트의 처리기는 이벤트 데이터 내에서 이벤트를 처리된 것으로 표시할 수 있습니다. 이벤트를 처리하면 경로가 효과적으로 단축됩니다. 클래스 처리는 라우트된 이벤트를 통해 지원되는 프로그래밍 개념입니다. 클래스 처리기는 클래스의 모든 인스턴스에서 가장 먼저 호출되는 처리기를 사용하여 라우트된 특정 이벤트를 클래스 수준에서 처리할 수 있습니다.  
  

  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>필수 구성 요소  
 이 항목에서는 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)에 소개된 개념에 대해 설명합니다.  
  
<a name="When_to_Mark_Events_as_Handled"></a>   
## <a name="when-to-mark-events-as-handled"></a>이벤트를 처리된 것으로 표시하는 시점  
 값을 설정 하면는 <xref:System.Windows.RoutedEventArgs.Handled%2A> 속성을 `true` 이벤트 라우트된 이벤트에 대 한 데이터를이 라고 "처리 이벤트 표시"입니다. 기존 라우트된 이벤트를 사용하거나 새 라우트된 이벤트를 구현하는 응용 프로그램 작성자나 컨트롤 작성자가 라우트된 이벤트를 처리된 것으로 표시해야 하는 시점에 대한 절대적인 규칙은 없습니다. 대부분의 경우 라우트된 이벤트의 이벤트 데이터에 포함되어 있는 “처리됨”의 개념은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]로 노출되는 다양한 라우트된 이벤트뿐만 아니라 사용자 지정된 라우트된 이벤트에 대한 고유한 응용 프로그램의 응답에 제한된 프로토콜로 사용해야 합니다. “처리됨” 문제로 간주하는 또 다른 방법은 일반적으로 코드에서 의미 있고 비교적 완전한 방법으로 라우트된 이벤트에 응답한 경우 라우트된 이벤트를 처리된 것으로 표시하는 것입니다. 일반적으로 라우트된 이벤트 하나가 발생할 때마다 별도의 처리기를 구현해야 하는 의미 있는 응답은 하나만 있어야 합니다. 전달을 위해 둘 이상의 응답이 필요한 경우에는 라우트된 이벤트 시스템을 사용하는 대신 단일 처리기 내에서 연결되는 응용 프로그램 논리를 통해 필요한 코드를 구현해야 합니다. “의미 있는 상태”라는 개념 역시 주관적이며 응용 프로그램이나 코드에 따라 달라집니다. “의미 있는 응답” 예로는 포커스 설정, 공용 상태 수정, 시각적 표현에 영향을 미치는 속성 설정, 다른 새 이벤트 생성 등이 있습니다. 의미 없는 응답의 예로는 시각적 영향이나 프로그래밍 표현이 없는 전용 상태 수정, 이벤트 로깅, 이벤트 인수를 검사한 응답하지 않도록 선택하는 것 등이 포함됩니다.  
  
 라우트된 이벤트 시스템 동작 처리기에 추가 된 라우트된 이벤트의 처리 상태를 사용 하 여이 "의미 있는 응답" 모델에 도움이 되도록 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 또는의 일반적인 서명이 <xref:System.Windows.UIElement.AddHandler%2A> 라우트된 이벤트에 대 한 응답으로 호출 되지 않습니다 여기서 이벤트 데이터를 이미 처리 된 표시 됩니다. 처리기를 추가 하는 직접 이동 해야 합니다는 `handledEventsToo` 매개 변수 버전 (<xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>) 처리 하기 위해 이전 참가자에 의해 처리 된 것으로 표시 된 라우트된 이벤트의 이벤트 라우팅합니다.  
  
 경우에 따라서는 컨트롤 자체에서 특정 라우트된 이벤트를 처리된 것으로 표시합니다. 라우트된 이벤트가 처리된 것으로 표시되면 라우트된 이벤트에 응답하는 컨트롤의 작업이 컨트롤 구현에서 의미가 있거나 그 일부로 완료되었으므로 이벤트를 추가로 처리할 필요가 없다고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 작성자가 결정했다는 것입니다. 이 경우에는 대개 이벤트에 대한 클래스 처리기를 추가하거나 기본 클래스에 존재하는 클래스 처리기 가상 메서드 중 하나를 재정의하게 됩니다. 필요한 경우 이 이벤트 처리 문제를 해결할 수 있습니다. 자세한 내용은 이 항목 뒷부분에 있는 [컨트롤에서 억제하는 이벤트 문제 해결](#WorkingAroundEventSuppressionByControls)을 참조하세요.  
  
<a name="Preview_Events_vs__Bubbling_Events_and_Handling"></a>   
## <a name="preview-tunneling-events-vs-bubbling-events-and-event-handling"></a>“미리 보기”(터널링) 이벤트 대 버블링 이벤트와 이벤트 처리  
 라우트된 미리 보기 이벤트는 요소 트리에서 터널링 경로를 따르는 이벤트입니다. 명명 규칙에서 표현된 “미리 보기”는 라우트된 미리 보기(터널링) 이벤트가 그에 해당되는 라우트된 버블링 이벤트보다 먼저 발생한다는 입력 이벤트의 일반적인 원칙을 나타냅니다. 또한 터널링 및 버블링 쌍이 있는 라우트된 입력 이벤트는 고유한 처리 논리를 가집니다. 라우트된 터널링/미리 보기 이벤트가 이벤트 수신기에 의해 처리된 것으로 표시되면 라우트된 버블링 이벤트의 수신기가 이벤트를 받기 전에 라우트된 버블링 이벤트가 처리된 것으로 표시됩니다. 라우트된 터널링 및 버블링 이벤트는 기술적으로 서로 다른 이벤트이지만 동일한 이벤트 데이터 인스턴스를 공유하여 이 동작을 활성화합니다.  
  
 라우트된 터널링 및 버블링 이벤트 간의 연결은 특정 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스가 고유하게 선언된 라우트된 이벤트를 발생시키는 방식으로 내부적으로 구현되며 이는 쌍을 이루는 라우트된 입력 이벤트의 경우에도 해당됩니다. 하지만 이 클래스 수준 구현이 존재하지 않으면 라우트된 터널링 이벤트와 라우트된 버블링 이벤트 간에 이름 지정 체계를 공유하는 연결이 없습니다. 이와 같은 구현이 없으면 이 두 이벤트는 완전히 분리된 두 개의 라우트된 이벤트이며 차례로 발생하거나 이벤트 데이터를 공유하지 않습니다.  
  
 사용자 지정 클래스에서 라우트된 터널링/버블링 입력 이벤트를 구현하는 방법에 대한 자세한 내용은 [사용자 지정 라우트된 이벤트 만들기](../../../../docs/framework/wpf/advanced/how-to-create-a-custom-routed-event.md)를 참조하세요.  
  
<a name="Class_Handlers_and_Instance_Handlers"></a>   
## <a name="class-handlers-and-instance-handlers"></a>클래스 처리기 및 인스턴스 처리기  
 라우트된 이벤트에서는 클래스 수신기와 인스턴스 수신기라는 두 가지 종류의 이벤트 수신기를 사용합니다. 클래스 수신기 형식 특정 호출 하기 때문에 존재 <xref:System.Windows.EventManager> [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] ,<xref:System.Windows.EventManager.RegisterClassHandler%2A>, 정적 생성자에서 요소 기본 클래스에서 클래스 처리기 가상 메서드를 재정의 했기 합니다. 인스턴스 수신기를 하나 이상의 처리기가 연결 해당 라우트된 이벤트를 호출 하 여 특정 클래스 인스턴스/요소는 <xref:System.Windows.UIElement.AddHandler%2A>합니다. 기존 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 라우트된 이벤트를 호출할 <xref:System.Windows.UIElement.AddHandler%2A> 의 일부로 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 이벤트 래퍼 {}를 추가 및 제거 하는 이벤트의 {} 구현을 간단한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성을 통해 이벤트 처리기 연결의 메커니즘 구문을 사용 합니다. 따라서 간단한에도 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 사용는 <xref:System.Windows.UIElement.AddHandler%2A> 호출 합니다.  
  
 시각적 트리 내에 있는 요소는 등록된 처리기 구현이 있는지 확인됩니다. 이 처리기는 해당 라우트된 이벤트의 라우팅 전략 형식에 내재된 순서에 따라 경로에서 호출될 수 있습니다. 예를 들어 라우트된 버블링 이벤트는 라우트된 이벤트를 발생시킨 동일한 요소에 연결된 처리기를 먼저 호출합니다. 그런 다음 라우트된 이벤트는 다음 부모 요소로 “버블링”되며 응용 프로그램 루트 요소에 도달할 때까지 이 동작이 계속 수행됩니다.  
  
 버블링 경로의 루트 요소 관점에서 볼 때 클래스 처리 또는 라우트된 이벤트의 소스에 보다 가까운 요소가 이벤트 인수를 처리된 것으로 표시하는 처리기를 호출하면 루트 요소의 처리기가 호출되지 않으며 루트 요소에 도달할 때까지의 이벤트 경로가 효과적으로 단축됩니다. 하지만 클래스 처리기나 인스턴스 처리기가 라우트된 이벤트를 처리된 것으로 표시하는 경우에도 계속 호출되어야 함을 나타내는 특수한 조건을 사용하여 처리기를 추가할 수 있으므로 경로가 완전하게 중단되지는 않습니다. 이에 대한 자세한 내용은 이 항목 뒷부분에서 [이벤트가 처리된 것으로 표시된 경우에도 발생되는 인스턴스 처리기 추가](#AddingInstanceHandlersthatAreRaisedEvenWhenEventsareMarkedHandled)를 참조하세요.  
  
 이벤트 경로보다 더 하위 수준에서는 클래스의 지정된 인스턴스에 대해 동작하는 클래스 처리기가 여러 개 있을 수 있습니다. 이는 라우트된 이벤트의 클래스 처리 모델을 사용하면 클래스 계층 구조의 모든 가능한 클래스가 각 라우트된 이벤트에 대해 고유한 클래스 처리기를 등록할 수 있기 때문입니다. 각 클래스 처리기는 내부 저장소에 추가되고 응용 프로그램에 대한 이벤트 경로가 구성될 때 모두 이벤트 경로에 추가됩니다. 클래스 처리기는 가장 많이 파생된 클래스 처리기가 먼저 호출된 다음 후속 기본 클래스의 클래스 처리기가 다음으로 호출되는 방식으로 경로에 추가됩니다. 일반적으로 클래스 처리기는 이미 처리된 것으로 표시된 라우트된 이벤트에도 응답하도록 등록되지는 않습니다. 따라서 이 클래스 처리 메커니즘을 사용할 경우 다음 두 가지 중 하나를 선택할 수 있습니다.  
  
-   파생 클래스는 라우트된 이벤트를 처리된 것으로 표시하지 않는 처리기를 추가함으로써 기본 클래스에서 상속된 클래스 처리를 보완할 수 있습니다. 이는 기본 클래스 처리기가 파생 클래스 처리기보다 나중에 호출되기 때문에 가능합니다.  
  
-   파생 클래스는 라우트된 이벤트를 처리된 것으로 표시하는 클래스 처리기를 추가함으로써 기본 클래스의 클래스 처리를 대체할 수 있습니다. 이 접근 방식을 사용할 경우에는 시각적 모양, 상태 논리, 입력 처리 및 명령 처리 같은 측면에서 원래 기본 컨트롤 디자인이 변경될 수 있으므로 주의해야 합니다.  
  
<a name="Class_Handling_of_Routed_Events"></a>   
## <a name="class-handling-of-routed-events-by-control-base-classes"></a>컨트롤 기본 클래스를 사용한 라우트된 이벤트의 클래스 처리  
 이벤트 경로의 지정된 각 요소 노드에서 클래스 수신기는 요소에 있는 다른 모든 인스턴스 수신기보다 먼저 라우트된 이벤트에 응답할 수 있습니다. 따라서 특정 컨트롤 클래스 구현에서 더 이상 전파되지 않도록 라우트된 이벤트를 억제하거나 클래스의 기능인 라우트된 이벤트에 대한 특수 처리 기능을 제공하기 위해 클래스 처리기를 사용하는 경우가 있습니다. 예를 들어 특정 클래스의 컨텍스트에서 사용자 입력 조건이 의미하는 내용에 대한 보다 구체적인 사항이 들어 있는 고유한 클래스별 이벤트를 클래스에서 발생시킬 수 있습니다. 이 경우 클래스 구현에서는 보다 일반화된 라우트된 이벤트를 처리된 것으로 표시할 수 있습니다. 클래스 처리기는 일반적으로 않도록 추가 라우팅에 대 한 호출 되지 않습니다 공유 이벤트 데이터가 이미 표시 되는 이벤트 처리 하지만 예외적인 경우 이기도 한 <xref:System.Windows.EventManager.RegisterClassHandler%28System.Type%2CSystem.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> 라우트된 이벤트는 면도 호출할 클래스 처리기를 등록 하는 서명 처리 됨으로 표시 합니다.  
  
### <a name="class-handler-virtuals"></a>클래스 처리기 가상 메서드  
 일부 요소와 같은 기본 요소 특히 <xref:System.Windows.UIElement>, 노출 비어 "에서 * 이벤트" 및 "OnPreview\*이벤트" 공용 라우트된 이벤트의 목록에 해당 하는 가상 메서드. 이러한 가상 메서드를 재정의하여 해당 라우트된 이벤트에 대한 클래스 처리기를 구현할 수 있습니다. 기본 요소 클래스의 클래스 처리기에서 이러한 각 이벤트를 사용 하 여 라우팅될 때 이러한 가상 메서드를 등록할 <xref:System.Windows.EventManager.RegisterClassHandler%28System.Type%2CSystem.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29> 앞에서 설명한 대로 합니다. On\*Event 가상 메서드를 사용하면 각 형식에 대한 정적 생성자에서 특수한 초기화를 수행할 필요 없이 관련 라우트된 이벤트에 대한 클래스 처리를 훨씬 쉽게 구현할 수 있습니다. 예를 들어, 클래스에 대 한 처리를 추가할 수 있습니다는 <xref:System.Windows.UIElement.DragEnter> 모든 이벤트 <xref:System.Windows.UIElement> 재정의 하 여 파생 클래스는 <xref:System.Windows.UIElement.OnDragEnter%2A> 가상 메서드. 재정의할 때 라우트된 이벤트를 처리하거나, 다른 이벤트를 발생시키거나, 인스턴스의 요소 속성을 변경할 수 있는 클래스별 논리를 초기화하거나, 이러한 작업을 원하는 대로 조합하여 사용할 수 있습니다. 일반적으로 이벤트를 처리된 것으로 표시한 경우에도 이와 같은 재정의에서 기본 구현을 호출해야 합니다. 가상 메서드는 기본 클래스에 있으므로 기본 구현을 호출하는 것이 좋습니다. 각 가상 메서드에서 기본 구현을 호출하는 표준적인 보호된 가상 패턴은 라우트된 이벤트 클래스 처리의 기본 메커니즘을 대체하거나 해당 메커니즘과 유사하게 실행됩니다. 라우트된 이벤트 클래스 처리의 기본 메커니즘을 사용할 경우 가장 많이 파생된 클래스의 처리기부터 시작하여 기본 클래스 처리기에 이르기까지 클래스 계층 구조의 모든 클래스에 대한 클래스 처리기가 지정된 인스턴스에서 호출됩니다. 클래스에서 기본 클래스 처리 논리를 의도적으로 변경해야 하는 경우에만 기본 구현 호출을 생략해야 합니다. 기본 구현을 재정의한 코드 이전에 호출할지 이후에 호출할지는 구현 특성에 따라 달라집니다.  
  
#### <a name="input-event-class-handling"></a>입력 이벤트 클래스 처리  
 모든 클래스 처리기 가상 메서드는 공유된 이벤트 데이터가 이미 처리된 것으로 표시되지 않은 경우에만 호출되도록 등록됩니다. 또한 입력 이벤트의 경우에는 고유하게 터널링 버전과 버블링 버전이 대개 차례로 발생하고 이벤트 데이터를 공유합니다. 따라서 입력 이벤트의 클래스 처리기가 하나는 터널링 버전이고 다른 하나는 버블링 버전인 지정된 쌍에 대해서는 이벤트를 즉시 처리된 것으로 표시하지 않는 것이 좋습니다. 이벤트를 처리된 것으로 표시하도록 터널링 클래스 처리 가상 메서드를 구현하면 버블링 클래스 처리기가 호출되지 않을 뿐만 아니라 터널링 이벤트나 버블링 이벤트에 대해 정상적으로 등록된 인스턴스 처리기도 호출되지 않습니다.  
  
 노드에서 클래스 처리를 완료했으면 인스턴스 수신기를 처리할 차례입니다.  
  
<a name="AddingInstanceHandlersthatAreRaisedEvenWhenEventsareMarkedHandled"></a>   
## <a name="adding-instance-handlers-that-are-raised-even-when-events-are-marked-handled"></a>이벤트가 처리된 것으로 표시된 경우에도 발생되는 인스턴스 처리기 추가  
 <xref:System.Windows.UIElement.AddHandler%2A> 메서드 호출 되는 이벤트 시스템에서 이벤트에는 경로에서 처리 요소에 도달할 때마다 다른 처리기가 이미를 표시 하는 이벤트 데이터를 조정 하는 경우에 처리기를 추가할 수 있는 특정 오버 로드를 제공 합니다. 이벤트를 처리 합니다. 대개는 이 오버로드를 사용하지 않습니다. 일반적으로 여러 개의 최종 결과가 필요한 경우에도 요소 트리에서 이벤트가 처리된 위치와 관계없이 이벤트의 영향을 받을 수 있는 응용 프로그램 코드의 모든 영역을 조정하도록 처리기를 작성할 수 있습니다. 또한 특정 이벤트에 응답해야 하는 요소가 실제로 하나인 경우가 많으며 적절한 응용 프로그램 논리가 이미 있는 경우가 많습니다. 하지만 요소 트리의 다른 요소나 복합 컨트롤에서 이벤트를 처리된 것으로 표시했더라도 요소 트리의 경로에서 더 높은 수준이나 낮은 수준에 있는 다른 요소에서 고유한 처리기를 호출해야 하는 예외적인 경우에는 `handledEventsToo` 오버로드를 사용할 수 있습니다.  
  
#### <a name="when-to-mark-handled-events-as-unhandled"></a>이벤트를 처리되지 않은 것으로 표시하는 시점  
 일반적으로 처리 된 것으로 표시 된 라우트된 이벤트를 표시 하지 말아야 처리 되지 않은 (<xref:System.Windows.RoutedEventArgs.Handled%2A> 으로 다시 설정 `false`) 작업을 수행 하는 처리기로도 `handledEventsToo`합니다. 하지만 일부 입력 이벤트에는 트리의 한 위치에 상위 수준의 이벤트가 나타나고 다른 위치에는 하위 수준의 이벤트가 나타나는 경우 겹칠 수 있는 상위 수준 이벤트 표현과 하위 수준 이벤트 표현이 있습니다. 예를 들어, 여기서는 자식 요소가 이벤트를 수신 하는 상위 수준 키와 같은 경우를 살펴봅시다 <xref:System.Windows.UIElement.TextInput> 부모 요소와 같은 하위 수준 이벤트를 수신 대기 하는 동안 <xref:System.Windows.UIElement.KeyDown>합니다. 부모 요소가 하위 수준 이벤트를 처리할 경우, 이벤트를 먼저 처리해야 하는 자식 요소에서 상위 수준의 이벤트가 억제될 수 있습니다.  
  
 이러한 경우 부모 요소와 자식 요소 모두에 하위 수준 이벤트에 대한 처리기를 추가해야 합니다. 자식 요소 처리기 구현에서는 하위 수준 이벤트를 처리된 것으로 표시하지만 부모 요소 처리기 구현에서는 트리에서 상위에 있는 이후 요소(상위 수준 이벤트 포함)가 응답할 수 있도록 해당 이벤트를 다시 처리되지 않은 것으로 설정합니다. 그러나 이와 같은 상황은 거의 발생하지 않습니다.  
  
<a name="Deliberately_Suppressing_Input_Events_for_Control"></a>   
## <a name="deliberately-suppressing-input-events-for-control-compositing"></a>복합 컨트롤에 대한 입력 이벤트를 의도적으로 억제  
 라우트된 이벤트의 클래스 처리는 입력 이벤트 및 복합 컨트롤을 사용하는 시나리오에 주로 사용됩니다. 정의에 따라 복합 컨트롤은 여러 개의 실용적인 컨트롤이나 컨트롤 기본 클래스로 구성됩니다. 컨트롤 작성자가 전체 컨트롤을 단일 이벤트 소스로 보고하기 위해서 각 하위 구성 요소에서 발생할 수 있는 모든 가능한 입력 이벤트를 결합하려는 경우가 많습니다. 경우에 따라서는 컨트롤 작성자가 구성 요소 전체에서 이벤트를 억제하거나, 더 많은 정보를 제공하거나 더 구체적인 동작을 수행하는 구성 요소 정의 이벤트를 대체하는 경우가 있습니다. 모든 구성 요소를 만든 즉시 볼 수 있는 대표적인 예 어떻게는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> 결국로 확인 되는 직관적인 이벤트를 모든 마우스 이벤트를 처리:는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트입니다.  
  
 <xref:System.Windows.Controls.Button> 기본 클래스 (<xref:System.Windows.Controls.Primitives.ButtonBase>)에서 파생 <xref:System.Windows.Controls.Control> 차례로에서 파생 된 <xref:System.Windows.FrameworkElement> 및 <xref:System.Windows.UIElement>, 많은 컨트롤 입력된 처리에 사용할 수 없으면 필요한 이벤트 인프라 및는 <xref:System.Windows.UIElement> 수준입니다. 특히, <xref:System.Windows.UIElement> 일반 처리 <xref:System.Windows.Input.Mouse> 해당 경계 내에서 마우스 커서에 대 한 적중 횟수 테스트 처리 하는 가장 일반적인에 대 한 개별 이벤트를 제공 하는 이벤트 단추와 같은 작업 <xref:System.Windows.UIElement.MouseLeftButtonDown>합니다. <xref:System.Windows.UIElement>빈 가상 제공 <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> 에 대해 미리 등록된 클래스 처리기로 <xref:System.Windows.UIElement.MouseLeftButtonDown>, 및 <xref:System.Windows.Controls.Primitives.ButtonBase> 을 사용 하면 재정의 합니다. 마찬가지로, <xref:System.Windows.Controls.Primitives.ButtonBase> 사용 하 여 클래스에 대 한 처리기 <xref:System.Windows.UIElement.MouseLeftButtonUp>합니다. 를 전달 하는 이벤트 데이터는 재정의 구현은 표시 하는 <xref:System.Windows.RoutedEventArgs> 설정 처리 인스턴스 <xref:System.Windows.RoutedEventArgs.Handled%2A> 를 `true`, 않으며 동일한 이벤트 데이터를 다른 클래스 처리기에 대 한 경로가의 나머지 부분에서는 따라 및 또한를 인스턴스 처리기 또는 이벤트 setter 합니다. 또한는 <xref:System.Windows.Controls.Primitives.ButtonBase.OnMouseLeftButtonUp%2A> 재정의 다음으로 발생시킬지는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트입니다. 대부분의 수신기에 대 한 최종 결과 됩니다는 <xref:System.Windows.UIElement.MouseLeftButtonDown> 및 <xref:System.Windows.UIElement.MouseLeftButtonUp> 이벤트 "사라지고"으로 대체 됩니다 <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, 알려진이 이벤트가 생성 된 true 단추와 일부 하지에서 더 많은 의미를 포함 하는 이벤트 복합 단추 또는 다른 요소에서 완전히 피스 합니다.  
  
<a name="WorkingAroundEventSuppressionByControls"></a>   
### <a name="working-around-event-suppression-by-controls"></a>컨트롤에서 억제하는 이벤트 문제 해결  
 개별 컨트롤 내에서 이 이벤트 억제 동작이 응용 프로그램의 보다 일반적인 이벤트 처리 논리와 충돌하는 경우가 있습니다. 예를 들어 어떤 이유로 응용 프로그램에서 발생에 대 한 처리기 <xref:System.Windows.UIElement.MouseLeftButtonDown> 응용 프로그램 루트 요소에 있는 확인할 수 단추에 모든 마우스 클릭 호출 하지 않을 <xref:System.Windows.UIElement.MouseLeftButtonDown> 또는 <xref:System.Windows.UIElement.MouseLeftButtonUp> 루트 수준에는 처리기. 이 경우 이벤트 자체는 실제로 버블링되었습니다. 즉, 이벤트 경로는 실제로 종료되지 않지만 라우트된 이벤트 시스템이 해당 이벤트를 처리된 것으로 표시한 후 처리기 호출 동작을 변경합니다. 라우트된 이벤트의 단추에 도달 하면는 <xref:System.Windows.Controls.Primitives.ButtonBase> 클래스 처리 표시는 <xref:System.Windows.UIElement.MouseLeftButtonDown> 대체 하기 때문에 처리는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 더 의미 있는 이벤트입니다. 따라서 표준 <xref:System.Windows.UIElement.MouseLeftButtonDown> 경로의 상위에 추가로 처리기를 호출할 수는 있습니다. 이런 경우 두 가지 기술을 사용하여 처리기가 호출되게 할 수 있습니다.  
  
 첫 번째 방법은 의도적으로 사용 하 여 처리기를 추가 하는 `handledEventsToo` 의 서명을 <xref:System.Windows.UIElement.AddHandler%28System.Windows.RoutedEvent%2CSystem.Delegate%2CSystem.Boolean%29>합니다. 이 방법의 한계는 이벤트 처리기를 코드에서만 연결할 수 있고 태그에서는 연결할 수 없다는 것입니다. [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 통해 이벤트 처리기 이름을 이벤트 특성 값으로 지정하는 단순한 구문으로는 이 동작을 활성화할 수 없습니다.  
  
 두 번째 방법은 라우트된 이벤트의 터널링 버전과 버블링 버전의 쌍을 만드는 것으로, 입력 이벤트에 대해서만 사용할 수 있습니다. 이러한 라우트된 이벤트의 경우에는 미리 보기/터널링에 해당하는 라우트된 이벤트에 처리기를 대신 추가할 수 있습니다. 해당 라우트된 이벤트는 루트에서 시작하여 경로를 통해 터널링되므로 응용 프로그램의 요소 트리에서 특정 상위 요소 수준에 미리 보기 처리기가 연결되었다고 가정할 경우, 단추 클래스 처리 코드가 이벤트를 대신 처리하지 않습니다. 이 접근 방식을 사용할 경우 미리 보기 이벤트를 처리된 것으로 표시할 때 주의해야 합니다. 와 제공 된 예에 대 한 <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> 으로 이벤트를 표시 하는 경우 루트 요소에서 처리 되 고 <xref:System.Windows.RoutedEventArgs.Handled%2A> 처리기 구현에는 실제로 표시 하지 않으려면는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트입니다. 일반적으로 이 동작은 사용하지 않는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.EventManager>  
 [미리 보기 이벤트](../../../../docs/framework/wpf/advanced/preview-events.md)  
 [사용자 지정 라우트된 이벤트 만들기](../../../../docs/framework/wpf/advanced/how-to-create-a-custom-routed-event.md)  
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
