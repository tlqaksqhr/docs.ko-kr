---
title: "연결된 이벤트 개요 | Microsoft Docs"
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
  - "연결된 이벤트[WPF], 정의"
  - "연결된 이벤트[WPF], 시나리오"
  - "연결된 이벤트와 라우트된 이벤트 비교[WPF]"
  - "라우트된 이벤트로 연결된 이벤트 지원[WPF]"
  - "연결된 이벤트를 라우트된 이벤트로 정의[WPF]"
  - "연결된 이벤트 처리[WPF]"
ms.assetid: 2c40eae3-80e4-4a45-ae09-df6c9ab4d91e
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 연결된 이벤트 개요
[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]은 *연결된 이벤트*라고 하는 이벤트의 형식과 언어 구성 요소를 정의합니다.  연결된 이벤트 개념을 사용하면 실제로 이벤트를 정의하거나 상속하는 요소가 아닌 임의의 요소에 특정 이벤트에 대한 처리기를 추가할 수 있습니다.  이 경우 이벤트를 발생시키는 개체나 인스턴스를 처리하는 대상 모두 이벤트를 정의하거나 다른 방식으로 "소유"하지 않습니다.  
  
   
  
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목에서는 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md) 및 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)를 학습한 것으로 간주합니다.  
  
<a name="Syntax"></a>   
## 연결된 이벤트 구문  
 연결된 이벤트에는 연결된 이벤트 사용을 지원하기 위해 백업 코드에서 사용해야 하는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 구문과 코딩 패턴이 있습니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 구문에서는 연결된 이벤트를 이벤트 이름만으로 지정하는 것이 아니라 소유 형식과 이벤트 이름을 점\(.\)으로 구분하여 지정합니다.  이벤트 이름은 소유 형식의 이름으로 한정되므로 연결된 이벤트 구문을 사용하면 모든 연결된 이벤트를 인스턴스화할 수 있는 모든 요소에 연결할 수 있습니다.  
  
 예를 들어 다음은 사용자 지정 `NeedsCleaning` 연결된 이벤트에 대한 처리기를 연결하는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 구문입니다.  
  
 [!code-xml[WPFAquariumSln#AE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 `aqua:` 접두사에 주의하십시오. 이 경우에는 연결된 이벤트가 매핑된 사용자 지정 xmlns에서 오는 사용자 지정 이벤트이므로 이 접두사가 필요합니다.  
  
<a name="WPFImplements"></a>   
## WPF에서 연결된 이벤트를 구현하는 방법  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 연결된 이벤트는 <xref:System.Windows.RoutedEvent> 필드를 기반으로 하며 발생된 후에 트리를 통해 라우트됩니다.  일반적으로 연결된 이벤트의 소스\(이벤트를 발생시킨 개체\)는 시스템 또는 서비스 소스이므로, 이벤트를 발생시킨 코드를 실행하는 개체는 요소 트리에 직접 포함되지 않습니다.  
  
<a name="Scenarios"></a>   
## 연결된 이벤트 시나리오  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 연결된 이벤트가 정적 <xref:System.Windows.Input.Mouse> 클래스 또는 <xref:System.Windows.Controls.Validation> 클래스를 통해 활성화되는 이벤트와 같이 서비스 수준 추상화가 있는 특정 기능 영역에 존재합니다.  서비스와 상호 작용하거나 서비스를 사용하는 클래스는 연결된 이벤트 구문의 이벤트를 사용하거나 클래스를 서비스 기능에 통합하는 방식과 관련된 라우트 이벤트로 연결된 이벤트를 노출할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 다양한 연결된 이벤트가 정의되지만 연결된 이벤트를 직접 사용하거나 처리하는 경우는 매우 드뭅니다.  일반적으로 연결된 이벤트는 아키텍처 용도로 사용되지만, 그 후 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 이벤트 "래퍼"를 기반으로 하여 연결되지 않는 라우트된 이벤트로 전달됩니다.  
  
 예를 들어 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 또는 코드에서 연결된 이벤트 구문을 처리하는 대신, <xref:System.Windows.UIElement>에 <xref:System.Windows.UIElement.MouseDown>을 사용하면 해당 <xref:System.Windows.UIElement>에서 기본 연결된 이벤트 <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=fullName>을 보다 쉽게 처리할 수 있습니다.  연결된 이벤트를 사용하면 장래에 입력 장치를 확장할 수 있으므로 아키텍처 용도로 사용할 수 있습니다.  가상 장치에서는 마우스 입력을 시뮬레이션하기 위해 <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=fullName>을 발생시키기만 하면 됩니다. 이를 위해 <xref:System.Windows.Input.Mouse>에서 파생시킬 필요가 없습니다.  하지만 이 시나리오에는 이벤트를 처리하는 코드가 필요하며 연결된 이벤트의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 처리는 이 시나리오와 관련이 없습니다.  
  
<a name="Handling"></a>   
## WPF에서 연결된 이벤트 처리  
 연결된 이벤트를 처리하는 프로세스와 사용자가 작성할 처리기 코드는 기본적으로 라우트된 이벤트의 경우와 동일합니다.  
  
 일반적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 연결된 이벤트는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 라우트된 이벤트와 크게 다르지 않습니다.  두 이벤트의 차이점은 이벤트가 발생하는 방식과 클래스에서 멤버로 노출되는 방식입니다. 특히 클래스에서 멤버로 노출되는 방식은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 처리기 구문에도 영향을 미칩니다.  
  
 하지만 앞서 설명한 것처럼 기존의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 연결된 이벤트는 특별히 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 처리에 사용하기 위한 것은 아닙니다.  그보다는 합성 과정에서 합성 요소를 통해 부모 요소에 상태를 보고하는 것이 이 이벤트의 용도인데, 이 경우 이벤트는 주로 코드로 발생하고 관련 부모 클래스의 클래스 처리에 의존합니다.  예를 들어 <xref:System.Windows.Controls.Primitives.Selector> 내의 항목은 연결된 <xref:System.Windows.Controls.Primitives.Selector.Selected> 이벤트를 발생시킵니다. 그러면 이 이벤트는 <xref:System.Windows.Controls.Primitives.Selector> 클래스로 처리되는 클래스가 되고 그 후 <xref:System.Windows.Controls.Primitives.Selector> 클래스에 의해 다른 라우트된 이벤트인 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>로 변환됩니다.  라우트된 이벤트와 클래스 처리에 대한 자세한 내용은 [라우트된 이벤트를 처리된 것으로 표시 및 클래스 처리](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)를 참조하십시오.  
  
<a name="Custom"></a>   
## 고유한 연결된 이벤트를 라우트된 이벤트로 정의  
 공용 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기본 클래스에서 파생시키는 경우 클래스에 특정 패턴 메서드를 포함시키고 기본 클래스에 이미 있는 유틸리티 메서드를 사용하여 고유한 연결된 이벤트를 구현할 수 있습니다.  
  
 패턴은 다음과 같습니다.  
  
-   매개 변수 두 개가 있는 `Add*Handler` 메서드.  첫 번째 매개 변수는 이벤트를 식별해야 하며 식별된 이벤트는 메서드 이름에서 \* 기호가 있는 이름과 일치해야 합니다.  두 번째 매개 변수는 추가할 처리기입니다.  이 메서드는 반환 값이 없는 공개 및 정적 메서드여야 합니다.  
  
-   매개 변수 두 개가 있는 `Remove*Handler` 메서드.  첫 번째 매개 변수는 이벤트를 식별해야 하며 식별된 이벤트는 메서드 이름에서 \* 기호가 있는 이름과 일치해야 합니다.  두 번째 매개 변수는 제거할 처리기입니다.  이 메서드는 반환 값이 없는 공개 및 정적 메서드여야 합니다.  
  
 연결된 이벤트 처리기 특성이 요소에 선언될 경우 `Add*Handler` 접근자 메서드를 사용하면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 빠르게 처리할 수 있습니다.  또한 `Add*Handler` 및 `Remove*Handler` 메서드를 사용하면 코드를 통해 이벤트 처리기 저장소에 액세스하여 연결된 이벤트를 이용할 수 있습니다.  
  
 이 일반 패턴은 지정된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 판독기를 구현할 때 지원 언어 및 아키텍처에서 기반 이벤트를 식별하는 데 서로 다른 스키마를 사용할 수 있기 때문에 아직 프레임워크에 실질적으로 구현할 정도로 정밀하지는 않습니다.  이것이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 연결된 이벤트를 라우트된 이벤트로 구현하는 이유 중 하나입니다. 이벤트\(<xref:System.Windows.RoutedEvent>\)에 사용할 식별자는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트 시스템에 이미 정의되어 있습니다.  또한 이벤트 라우팅은 연결된 이벤트의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 언어 수준 개념에서 자연스러운 구현 확장입니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 연결된 이벤트에 `Add*Handler`를 구현하는 과정에서는 라우트된 이벤트와 처리기를 인수로 사용하는 <xref:System.Windows.UIElement.AddHandler%2A>를 호출합니다.  
  
 이 구현 전략과 라우트된 이벤트 시스템은 일반적으로 연결된 이벤트의 처리를 <xref:System.Windows.UIElement> 파생 클래스나 <xref:System.Windows.ContentElement> 파생 클래스로 제한합니다. 이는 이러한 클래스에만 <xref:System.Windows.UIElement.AddHandler%2A>가 구현되어 있기 때문입니다.  
  
 예를 들어 다음 코드에서는 연결된 이벤트를 라운트된 이벤트로 선언하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 연결된 이벤트 전략을 사용하여 소유자 클래스 `Aquarium`에서 `NeedsCleaning` 연결된 이벤트를 정의합니다.  
  
 [!code-csharp[WPFAquariumSln#AECode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 실제로, 연결된 이벤트 식별자 필드를 설정하는 데 사용되는 메서드인 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>는 연결되지 않은 라우트된 이벤트를 등록하는 데 사용되는 메서드와 동일한 메서드입니다.  연결된 이벤트와 라우트된 이벤트는 모두 중앙의 내부 저장소에 등록됩니다.  이 이벤트 저장소를 구현하면 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)에서 설명하는 "인터페이스 역할을 하는 이벤트"를 개념적으로 고려해 볼 수 있습니다.  
  
<a name="Raising"></a>   
## WPF 연결된 이벤트 발생시키기  
 일반적인 경우에는 코드에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 정의된 기존의 연결된 이벤트를 발생시킬 필요가 없습니다.  이러한 이벤트는 일반 "서비스" 개념 모델을 따르며 <xref:System.Windows.Input.InputManager>와 같은 서비스 클래스가 이벤트를 발생시키는 역할을 합니다.  
  
 하지만 <xref:System.Windows.RoutedEvent>에 있는 연결된 이벤트를 기반으로 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 모델에 기반한 사용자 지정 연결된 이벤트를 정의하는 경우 <xref:System.Windows.UIElement.RaiseEvent%2A>를 사용하여 모든 <xref:System.Windows.UIElement> 또는 <xref:System.Windows.ContentElement>에서 연결된 이벤트를 발생시킬 수 있습니다.  연결된 이벤트 또는 연결되지 않은 이벤트를 모두 포함하여 라우트된 이벤트를 발생시키려면 요소 트리에서 특정 요소를 이벤트 소스로 선언해야 합니다. 이러한 소스는 <xref:System.Windows.UIElement.RaiseEvent%2A> 호출자로 보고됩니다.  트리에서 어떤 요소가 소스로 보고되는지는 서비스에 따라 다릅니다.  
  
## 참고 항목  
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)   
 [WPF에 대한 XAML 및 사용자 지정 클래스](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)