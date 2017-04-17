---
title: "속성 변경 이벤트 | Microsoft Docs"
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
  - "change 이벤트[WPF], 속성"
  - "속성 트리거 만들기[WPF]"
  - "종속성 속성[WPF], change 이벤트"
  - "이벤트[WPF], 속성 값 변경"
  - "변경된 속성 이벤트 식별[WPF]"
  - "속성 변경 이벤트[WPF]"
  - "속성 변경 이벤트[WPF], 형식"
  - "속성 트리거[WPF]"
  - "속성 트리거[WPF], 정의"
  - "속성 값 변경 내용[WPF]"
ms.assetid: 0a7989df-9674-4cc1-bc50-5d8ef5d9c055
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 속성 변경 이벤트
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에는 속성 값 변경에 대한 응답으로 발생하는 몇 가지 이벤트가 정의되어 있습니다.  대개 이러한 속성은 [종속성 속성](GTMT)입니다.  이벤트 자체는 [라우트된 이벤트](GTMT)인 경우도 있고 표준 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 이벤트인 경우도 있습니다.  속성 변경은 일반적으로 속성이 변경된 개체에만 적용되나 요소 트리 전체에서 더욱 적절하게 라우트되는 속성 변경도 있으므로 이벤트 정의는 시나리오에 따라 다릅니다.  
  
## 속성 변경 이벤트 식별  
 속성 변경 보고 이벤트 중 일부는 시그니처 패턴 또는 명명 패턴을 통해 명시적으로 속성 변경 이벤트로 식별되지 않습니다.  일반적으로 [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)] 설명서의 이벤트 설명 부분에서는 이벤트가 속성 값 변경에 직접 연결되었는지 여부를 알려 주고 속성과 이벤트 사이의 상호 참조를 제공합니다.  
  
### RoutedPropertyChanged 이벤트  
 일부 이벤트는 속성 변경 이벤트에 명시적으로 사용되는 이벤트 데이터 형식과 대리자를 사용합니다.  이 경우 이벤트 데이터 형식은 <xref:System.Windows.RoutedPropertyChangedEventArgs%601>이고 대리자는 <xref:System.Windows.RoutedPropertyChangedEventHandler%601>입니다.  이벤트 데이터 및 대리자 모두 제네릭 형식 매개 변수를 사용합니다. 제네릭 형식 매개 변수는 처리기를 정의할 때 변경 속성의 실제 형식을 지정하는 데 사용됩니다.  이벤트 데이터에는 <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> 및 <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>라는 두 가지 속성이 있으며, 이 두 속성은 모두 이벤트 데이터에 형식 인수로 전달됩니다.  
  
 이름의 "Routed" 부분은 속성 변경 이벤트가 라우트된 이벤트로 등록되었음 나타냅니다.  속성 변경 이벤트를 라우트하면 컨트롤의 복합 파트인 자식 요소의 속성 값이 변경되었을 때 최상위 컨트롤에서 속성 변경 이벤트를 받을 수 있다는 장점이 있습니다.  예를 들어 <xref:System.Windows.Controls.Slider>와 같은 <xref:System.Windows.Controls.Primitives.RangeBase> 컨트롤을 통합하는 컨트롤을 만든 경우,  슬라이더 파트에서 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 속성 값이 변경되면 해당 파트 대신 부모 컨트롤에서 변경 내용을 처리하는 것이 좋습니다.  
  
 이전 값과 새 값을 모두 알 수 있기 때문에 이 이벤트 처리기를 속성 값에 대한 유효성 검사기로 사용할 수 있다고 생각할 수 있습니다.  그러나 대부분의 속성 변경 이벤트는 이러한 용도로 디자인되지 않았습니다.  일반적으로 이러한 값은 코드의 다른 논리 영역에서 처리되도록 제공되지만 이벤트 처리기 내에서 실제로 값을 변경하지 않는 것이 좋습니다. 값을 변경할 경우 처리기의 구현 방법에 따라서 예기치 않은 재귀가 발생할 수 있습니다.  
  
 속성이 사용자 지정 종속성 속성이거나, 인스턴스화 코드가 정의된 파생 클래스로 작업하는 경우에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템에 기본적으로 포함되어 있는 속성 시스템 콜백인 <xref:System.Windows.CoerceValueCallback>과 <xref:System.Windows.PropertyChangedCallback>을 통해 속성 변경을 보다 효과적으로 추적할 수 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템을 사용하여 유효성 검사 및 강제 변환을 수행하는 방법에 대한 자세한 내용은 [종속성 속성 콜백 및 유효성 검사](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md) 및 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)을 참조하십시오.  
  
### DependencyPropertyChanged 이벤트  
 속성 변경 이벤트 시나리오에는 <xref:System.Windows.DependencyPropertyChangedEventArgs> 및 <xref:System.Windows.DependencyPropertyChangedEventHandler> 형식도 사용됩니다.  이러한 속성 변경에 대한 이벤트는 표준 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 이벤트이기 때문에 라우트되지 않습니다.  <xref:System.Windows.DependencyPropertyChangedEventArgs>는 <xref:System.EventArgs>에서 파생되지 않는 예외적인 이벤트 데이터 보고 형식입니다. <xref:System.Windows.DependencyPropertyChangedEventArgs>는 클래스가 아니라 구조체입니다.  
  
 <xref:System.Windows.DependencyPropertyChangedEventArgs> 및 <xref:System.Windows.DependencyPropertyChangedEventHandler>를 사용하는 이벤트는 `RoutedPropertyChanged` 이벤트보다는 조금 더 보편적으로 사용됩니다.  이러한 형식을 사용하는 이벤트로는 <xref:System.Windows.UIElement.IsMouseCapturedChanged>를 예로 들 수 있습니다.  
  
 <xref:System.Windows.DependencyPropertyChangedEventArgs>도 <xref:System.Windows.RoutedPropertyChangedEventArgs%601>와 마찬가지로 속성의 이전 값과 새 값을 보고합니다.  또한 값을 처리하는 방법에 대한 고려 사항이 이 경우에도 동일하게 적용되므로 이벤트에 대한 응답으로 값을 변경하지 않는 것이 좋습니다.  
  
## 속성 트리거  
 속성 트리거는 속성 변경 이벤트와 매우 밀접하게 관련된 개념입니다.  속성 트리거는 스타일 또는 템플릿 내에서 생성되며, 속성 트리거를 사용하면 속성 트리거가 할당된 속성의 값을 기준으로 하는 조건부 동작을 만들 수 있습니다.  
  
 속성 트리거의 속성은 종속성 속성이며  일반적으로 읽기 전용입니다.  컨트롤에서 노출되는 종속성 속성의 이름이 "Is"로 시작하는 경우에는 해당 속성이 부분적으로나마 속성 트리거로 디자인되었음을 알 수 있습니다.  대개 이와 같은 이름을 갖는 속성은 읽기 전용 부울 종속성 속성입니다. 이 속성은 실시간 UI에 영향을 줄 수 있는 컨트롤 상태를 보고하는 데 주로 사용되기 때문에 속성 트리거가 될 수 있습니다.  
  
 이러한 속성 중 일부는 전용 속성 변경 이벤트를 사용합니다.  예를 들어 <xref:System.Windows.UIElement.IsMouseCaptured%2A> 속성은 <xref:System.Windows.UIElement.IsMouseCapturedChanged>라는 속성 변경 이벤트를 사용합니다.  이 속성 자체는 읽기 전용이고 속성 값은 입력 시스템에 의해 조정됩니다. 입력 시스템에서는 실시간 변경 사항이 발생할 때마다 <xref:System.Windows.UIElement.IsMouseCapturedChanged>를 발생시킵니다.  
  
 속성 트리거를 사용하여 속성 변경을 처리하면 실제 속성 변경 이벤트에 비해 작업이 제한됩니다.  
  
 속성 트리거는 완벽하게 일치하는 논리를 기초로 동작하기 때문에  사용자는 속성 및 트리거가 동작할 구체적인 값을 나타내는 값을 지정해야 합니다.  예를 들면 `<Setter Property="IsMouseCaptured" Value="true"> ... </Setter>`와 같이 지정합니다.  이러한 제한 때문에 대부분의 속성 트리거는 부울 속성 또는 각 값에 대해 트리거를 정의할 수 있을 정도로 가능한 값 범위가 제한된 전용 열거형 값을 갖는 속성에 대해 사용됩니다.  항목 수가 0에 도달했다가 속성 값이 다시 0 이외의 값으로 변경되는 경우를 고려하는 트리거는 따로 없기 때문에 이와 같이 특별한 값에 대해 속성 트리거를 사용할 수도 있습니다. 이 경우에는 0 이외의 다른 모든 값에 대해 트리거를 사용하는 대신 이벤트 처리기 코드를 사용하거나, 값이 0이 아닐 때 트리거 상태에서 다시 전환하는 기본 동작을 사용할 수 있습니다.  
  
 속성 트리거 구문은 프로그래밍 시 사용하는 "if" 문과 유사합니다.  트리거 조건이 true이면 속성 트리거의 "본문"이 "실행"됩니다.  속성 트리거의 "본문"은 코드가 아니라 태그이며  이 태그는 하나 이상의 <xref:System.Windows.Setter> 요소를 사용하여 스타일 또는 템플릿이 적용된 개체의 다른 속성을 설정하도록 제한됩니다.  
  
 가능한 값 범위가 광범위한 속성 트리거의 "if" 조건을 오프셋하려면 일반적으로 <xref:System.Windows.Setter>를 사용하여 동일한 속성 값을 기본값으로 설정하는 것이 좋습니다.  이렇게 하면 트리거 조건이 true인 경우에만 <xref:System.Windows.Trigger>에 포함된 setter가 우선적으로 적용되고, 트리거 조건이 false인 경우에는 <xref:System.Windows.Trigger>에 포함되지 않은 <xref:System.Windows.Setter>가 우선적으로 적용됩니다.  
  
 일반적으로 속성 트리거는 같은 요소에 대한 특정 속성의 상태에 따라 하나 이상의 모양 속성이 변경되는 시나리오에 사용하기 적합합니다.  
  
 속성 트리거에 대한 자세한 내용은 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)을 참조하십시오.  
  
## 참고 항목  
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)