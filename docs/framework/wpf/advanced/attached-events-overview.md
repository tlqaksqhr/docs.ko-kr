---
title: 연결된 이벤트 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handling attached events [WPF]
- defining attached events as routed events [WPF]
- attached events [WPF], scenarios for
- attached events vs. routed events [WPF]
- backing attached events with routed events [WPF]
- attached events [WPF], definition
ms.assetid: 2c40eae3-80e4-4a45-ae09-df6c9ab4d91e
ms.openlocfilehash: ae6d426d671c8bf034ebd86e768352914585d969
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541741"
---
# <a name="attached-events-overview"></a>연결된 이벤트 개요
[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]은 *연결된 이벤트*라는 이벤트의 유형 및 언어 구성 요소를 정의합니다. 연결된 이벤트의 개념을 사용하면 실제로 정의하거나 이벤트를 상속하는 요소가 아닌 임의의 요소에 특정 이벤트의 핸들러를 추가할 수 있습니다. 이 경우 이벤트를 잠재적으로 발생시키는 개체나 인스턴스를 처리하는 대상이 정의하지 않으며 또는 그렇지 않으면 이벤트를 "소유"합니다.  
  
 
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>전제 조건  
 이 항목에서는 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md) 및 [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)를 읽었다고 가정합니다.  
  
<a name="Syntax"></a>   
## <a name="attached-event-syntax"></a>연결된 이벤트 구문  
 연결된 이벤트에는 연결된 이벤트 사용량을 지원하기 위해 백업 코드에서 사용해야 하는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 구문 및 코딩 패턴이 있습니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 구문에서, 연결된 이벤트를 이벤트 이름 뿐만 아니라 소유 형식과 이벤트 이름을 점(.)으로 구분하여 지정합니다. 이벤트 이름이 소유 형식의 이름으로 정규화되기 때문에, 연결된 이벤트 구문을 모든 연결된 이벤트를 인스턴스화할 수 있는 모든 요소에 연결할 수 있습니다.  
  
 예를 들어, 다음은 사용자 지정 `NeedsCleaning` 연결된 이벤트에 대해 핸들러를 연결하기 위한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 구문입니다.  
  
 [!code-xaml[WPFAquariumSln#AE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 `aqua:` 접두사. 연결된 이벤트가 사용자 지정 맵핑된 xmlns에서 오는 사용자 지정 이벤트이기 때문에 이 경우에 접두사가 필요합니다.  
  
<a name="WPFImplements"></a>   
## <a name="how-wpf-implements-attached-events"></a>WPF가 연결된 이벤트를 구현하는 방법  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]연결 된 이벤트에 의해 지원 됩니다는 <xref:System.Windows.RoutedEvent> 필드 및 발생 된 후에 트리를 통해 라우팅됩니다. 일반적으로 연결된 이벤트(이벤트를 발생하는 개체)의 소스는 시스템이나 서비스 소스이며, 이벤트를 발생하는 코드를 실행하는 개체는 직접적인 요소 트리 파트가 아닙니다.  
  
<a name="Scenarios"></a>   
## <a name="scenarios-for-attached-events"></a>연결된 이벤트에 대한 시나리오  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]연결 된 이벤트는 특정 기능 영역에는 정적으로 사용 하도록 설정 하는 이벤트와 같은 서비스 수준 추상화는 <xref:System.Windows.Input.Mouse> 클래스 또는 <xref:System.Windows.Controls.Validation> 클래스입니다. 서비스와 상호 작용하거나 사용하는 클래스는 연결된 이벤트 구문에서 이벤트를 사용하거나, 클래스가 서비스의 기능을 통합하는 방법의 일부인 라우트된 이벤트로 연결된 이벤트를 나타내도록 선택할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 연결된 이벤트 수를 정의하는 경우, 연결된 이벤트를 사용하거나 직접 처리하는 시나리오는 매우 제한됩니다. 일반적으로 연결된 이벤트는 아키텍처 용도로 사용되지만 연결되지 않은([!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 이벤트 "래퍼"로 지원된) 라우트된 이벤트로 전달됩니다.  
  
 예를 들어, 기본 연결 된 이벤트 <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> 보다 쉽게 처리할 수 <xref:System.Windows.UIElement> 를 사용 하 여 <xref:System.Windows.UIElement.MouseDown> 그에 <xref:System.Windows.UIElement> 하거나 연결 된 이벤트 구문을 사용 하 여 처리 하는 대신에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 또는 코드입니다. 입력 장치의 향후 확장을 허용하므로 연결된 이벤트는 아키텍처의 용도로 사용됩니다. 가상 장치를 발생 시키는 하기만 하면 <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> 마우스 입력을 시뮬레이션 하기 위해와에서 파생 될 필요가 없습니다 <xref:System.Windows.Input.Mouse> 그러려면 합니다. 그러나 이 시나리오는 이벤트를 처리하는 코드를 포함하며 연결된 이벤트의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 처리는 이 시나리오와 관련이 없습니다.  
  
<a name="Handling"></a>   
## <a name="handling-an-attached-event-in-wpf"></a>WPF에서 연결된 이벤트 처리  
 연결된 이벤트를 처리하기 위한 프로세스 및 작성할 처리기 코드는 기본적으로 라우트된 이벤트의 경우와 동일합니다.  
  
 일반적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 연결된 이벤트는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 라우트된 이벤트와 크게 다르지 않습니다. 이벤트가 발생하는 방법 및 클래스에 의해 구성원으로 노출되는 방법에서 다릅니다([!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 처리기 구문에도 영향을 미침).  
  
 그러나 앞서 설명한 것처럼, 기존 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 연결된 이벤트는 특별히 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 처리에 사용되지 않습니다. 이벤트의 목적은 합성 이벤트가 작성 시 부모 요소에 상태를 보고할 수 있게 하는 것으로, 이 경우 이벤트는 일반적으로 코드에서 발생하며 관련 부모 클래스에서 처리하는 클래스에도 사용됩니다. 예를 들어, 내의 항목는 <xref:System.Windows.Controls.Primitives.Selector> 첨부 된 발생 <xref:System.Windows.Controls.Primitives.Selector.Selected> 클래스는 다음 이벤트 처리는 <xref:System.Windows.Controls.Primitives.Selector> 에서 잠재적으로 변환 하 고 클래스는 <xref:System.Windows.Controls.Primitives.Selector> 클래스를 다른 라우트된 이벤트로 <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> . 라우트된 이벤트 및 클래스 처리에 대한 자세한 내용은 [라우트된 이벤트를 처리된 것으로 표시 및 클래스 처리](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)를 참조하십시오.  
  
<a name="Custom"></a>   
## <a name="defining-your-own-attached-events-as-routed-events"></a>연결된 이벤트를 라우트된 이벤트로 정의  
 공통 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기본 클래스에서 파생되는 경우, 클래스에 특정 패턴 메서드를 포함하고 기본 클래스에 이미 있는 유틸리티 메서드를 사용하여 자신의 연결된 이벤트를 구현할 수 있습니다.  
  
 패턴은 다음과 같습니다.  
  
-   두 개의 매개 변수가 있는 메서드 `Add*Handler`. 첫 번째 매개 변수는 이벤트를 식별해야 하고 식별된 이벤트의 이름은 메서드 이름의 *과 일치해야 합니다. 두 번째 매개 변수는 추가할 처리기입니다. 메서드는 공용 및 반환 값이 없는 정적이어야 합니다.  
  
-   두 개의 매개변수가 있는 메서드 `Remove*Handler`. 첫 번째 매개 변수는 이벤트를 식별해야 하고 식별된 이벤트의 이름은 메서드 이름의 *과 일치해야 합니다. 두 번째 매개 변수는 제거할 처리기입니다. 메서드는 공용 및 반환 값이 없는 정적이어야 합니다.  
  
 연결된 이벤트 처리기 특성이 요소에서 선언될 때 `Add*Handler` 접근자 메서드는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 처리를 용이하게 합니다. `Add*Handler` 및 `Remove*Handler` 메서드도 연결된 이벤트에 대한 이벤트 처리기 저장소에 대한 코드 액세스를 사용합니다.  
  
 지정된 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 판독기 구현에 지원하는 언어 및 아키텍처의 기본 이벤트를 식별하기 위한 다른 스키마가 있을 수 있기 때문에 이 일반 패턴은 프레임워크에 실질적으로 구현할 수 있을 만큼 정확하지 않습니다. 이것이 이유 중 하나는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 라우트된 이벤트로 구현 연결 된 이벤트, 이벤트에 대해 사용할 수 있는 식별자 (<xref:System.Windows.RoutedEvent>)에서 이미 정의 된는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트 시스템입니다. 또한 이벤트 라우팅은 연결된 이벤트의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 언어 수준 개념에 대한 자연스러운 구현 확장입니다.  
  
 `Add*Handler` 에 대 한 구현을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 연결 된 이벤트의 호출으로 구성 됩니다는 <xref:System.Windows.UIElement.AddHandler%2A> 라우트된 이벤트와 인수로 처리기입니다.  
  
 이 구현 전략 및 라우트된 이벤트 시스템 일반적 연결 된 이벤트에 대 한 처리를 제한 하거나 <xref:System.Windows.UIElement> 파생 클래스 또는 <xref:System.Windows.ContentElement> 클래스만 없으므로 파생 클래스 <xref:System.Windows.UIElement.AddHandler%2A> 구현 합니다.  
  
 예를 들어, 라우트된 이벤트로 연결된 이벤트를 선언하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 연결된 이벤트 전략을 사용하여, 다음 코드는 소유자 클래스의 `NeedsCleaning` 연결된 소유자 클래스 `Aquarium` 정의합니다.  
  
 [!code-csharp[WPFAquariumSln#AECode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 메서드가 연결 된 이벤트 식별자 필드를 설정 하는 데 사용 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>는 연결 되지 않은 라우트된 이벤트를 등록 하는 데 사용 되는 동일한 방법과 실제로 합니다. 연결된 이벤트 및 라우트된 이벤트 모두 중앙 집중화된 내부 저장소에 등록됩니다. 이 이벤트 저장소 구현은 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)에서 설명하는 “인터페이스로서의 이벤트” 개념 고려 사항을 사용합니다.  
  
<a name="Raising"></a>   
## <a name="raising-a-wpf-attached-event"></a>WPF 연결된 이벤트 발생  
 일반적으로 기존 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 정의된 연결된 이벤트를 코드에서 발생시킬 필요가 없습니다. 이러한 이벤트는 일반 "서비스" 개념적 모델에 따라 및와 같은 서비스 클래스가 <xref:System.Windows.Input.InputManager> 이벤트를 발생 시키는 작업을 담당 합니다.  
  
 그러나 기반으로 하는 연결 된 사용자 지정 이벤트를 정의 하는 경우는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에 연결 된 이벤트 모델에 <xref:System.Windows.RoutedEvent>를 사용할 수 있습니다 <xref:System.Windows.UIElement.RaiseEvent%2A> 에서 연결 된 이벤트를 발생 시키는 <xref:System.Windows.UIElement> 또는 <xref:System.Windows.ContentElement>합니다. 이벤트 소스로 요소 트리에서 특정 요소를 선언 해야 (또는 연결 되지 않은) 라우트된 이벤트를 발생 시킨 해당 소스로 보고 되는 <xref:System.Windows.UIElement.RaiseEvent%2A> 호출자입니다. 트리에서 소스로 보고되는 요소 판별은 서비스에 따라 다릅니다.  
  
## <a name="see-also"></a>참고 항목  
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)  
 [WPF에 대한 XAML 및 사용자 지정 클래스](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
