---
title: WPF 사용자 지정 컨트롤의 UI 자동화
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], applying UI automation
- accessibility [WPF], applying to custom controls
- custom controls [WPF], improving accessibility
- UI Automation [WPF], using with custom controls
ms.assetid: 47b310fc-fbd5-4ce2-a606-22d04c6d4911
ms.openlocfilehash: fbd19591c260b0ad160339b45fd762e7a87bbc74
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>WPF 사용자 지정 컨트롤의 UI 자동화
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)]에서는 자동화 클라이언트가 다양한 플랫폼 및 프레임워크의 사용자 인터페이스를 검사하거나 운영하는 데 사용할 수 있는 일반화된 단일 인터페이스를 제공합니다. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]를 통해 품질 보증(테스트) 코드 및 화면 읽기 프로그램과 같은 접근성 응용 프로그램은 사용자 인터페이스 요소를 검사하고 다른 코드에서 해당 요소에 대한 사용자 상호 작용을 시뮬레이트할 수 있습니다. 모든 플랫폼에서 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 자세한 내용은 접근성을 참조하세요.  
  
 이 항목에서는 WPF 응용 프로그램에서 실행되는 사용자 지정 컨트롤에 대한 서버 쪽 UI 자동화 공급자를 구현하는 방법을 설명합니다. WPF는 사용자 인터페이스 요소의 트리에 대응하는 피어 자동화 개체의 트리를 통해 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]를 지원합니다. 접근성 기능을 제공하는 응용 프로그램 및 테스트 코드는 자동화 피어 개체를 직접 사용(in-process 코드의 경우)하거나 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]에서 제공하는 일반화된 인터페이스를 통해 사용할 수 있습니다.  
  
 
  
<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>자동화 피어 클래스  
 WPF 지원을 제어 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 피어 클래스에서 파생 되는 트리를 통해 <xref:System.Windows.Automation.Peers.AutomationPeer>합니다. 규칙에 따라 피어 클래스 이름은 컨트롤 클래스 이름으로 시작하고 "AutomationPeer"로 끝납니다. 예를 들어 <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> 에 대 한 피어 클래스는 <xref:System.Windows.Controls.Button> 클래스를 제어 합니다. 피어 클래스는 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 컨트롤 형식과 거의 동일하지만 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 요소와 관련됩니다. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 인터페이스를 통해 WPF 응용 프로그램에 액세스하는 자동화 코드는 자동화 피어를 직접 사용하지 않지만 동일한 프로세스 공간의 자동화 코드는 자동화 피어를 직접 사용할 수 있습니다.  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>기본 제공 자동화 피어 클래스  
 요소는 사용자의 인터페이스 작업을 허용하는 경우 또는 화면 읽기 프로그램 응용 프로그램 사용자에게 필요한 정보를 포함하는 경우 자동화 피어 클래스를 구현합니다. 일부 WPF 시각적 요소에는 자동화 피어가 없습니다. 자동화 피어를 구현 하는 클래스의 예는 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.TextBox>, 및 <xref:System.Windows.Controls.Label>합니다. 자동화 피어를 구현 하지 않는 클래스의 예는 클래스에서 파생 되는 <xref:System.Windows.Controls.Decorator>와 같은 <xref:System.Windows.Controls.Border>, 및 클래스에 따라 <xref:System.Windows.Controls.Panel>와 같은 <xref:System.Windows.Controls.Grid> 및 <xref:System.Windows.Controls.Canvas>합니다.  
  
 기본 <xref:System.Windows.Controls.Control> 클래스에는 해당 피어 클래스가 없습니다. 파생 되는 사용자 지정 컨트롤에 해당 하는 피어 클래스가 필요한 경우 <xref:System.Windows.Controls.Control>에서 사용자 지정 피어 클래스를 파생 시켜야 <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>합니다.  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>파생된 피어의 보안 고려 사항  
 자동화 피어는 부분 신뢰 환경에서 실행되어야 합니다. UIAutomationClient 어셈블리의 코드는 부분 신뢰 환경에서 실행되도록 구성되지 않았으며 자동화 피어 코드는 해당 어셈블리를 참조해서는 안 됩니다. 대신 UIAutomationTypes 어셈블리의 클래스를 사용해야 합니다. 예를 들어 사용 해야는 <xref:System.Windows.Automation.AutomationElementIdentifiers> 에 해당 하는 UIAutomationTypes 어셈블리에서 클래스는 <xref:System.Windows.Automation.AutomationElement> UIAutomationClient 어셈블리의에서 클래스. 자동화 피어 코드에서 UIAutomationTypes 어셈블리를 참조해도 안전합니다.  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>피어 탐색  
 자동화 피어를 찾은 후에 처리 중인 코드에서 탐색할 수 피어 트리 개체의 호출 하 여 <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> 및 <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> 메서드. 간의 탐색 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 컨트롤 내에서 요소 피어의 구현에 의해 지원 되는 <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> 메서드. UI 자동화 시스템은 이 메서드를 호출하여 컨트롤 내에 포함된 하위 요소의 트리를 작성합니다(예: 목록 상자의 목록 항목). 기본 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType> 메서드 자동화 피어 트리를 만드는 요소의 시각적 트리를 이동 합니다. 사용자 지정 컨트롤은 자식 요소를 자동화 클라이언트에 노출하도록 이 메서드를 재정의하여 정보를 전달하거나 사용자 상호 작용을 허용하는 요소의 자동화 피어를 반환합니다.  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>파생된 피어의 사용자 지정  
 파생 되는 모든 클래스 <xref:System.Windows.UIElement> 및 <xref:System.Windows.ContentElement> 보호 된 가상 메서드를 포함 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>합니다. WPF 호출 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 각 컨트롤에 대 한 자동화 피어 개체를 가져오려는 합니다. 자동화 코드는 피어를 사용하여 컨트롤의 특성 및 기능에 대한 정보를 가져오고 대화형 사용을 시뮬레이트할 수 있습니다. 자동화를 지 원하는 사용자 지정 컨트롤 재정의 해야 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 에서 파생 되는 클래스의 인스턴스를 반환 하 고 <xref:System.Windows.Automation.Peers.AutomationPeer>합니다. 예를 들어, 사용자 지정 컨트롤에서 파생 되는 경우는 <xref:System.Windows.Controls.Primitives.ButtonBase> 클래스 후 반환 되는 개체 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 에서 파생 되어야 <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>합니다.  
  
 사용자 지정 컨트롤을 구현할 때 사용자 지정 컨트롤과 관련된 고유한 동작을 설명하는 "Core" 메서드를 기본 자동화 피어 클래스에서 재정의해야 합니다.  
  
### <a name="override-oncreateautomationpeer"></a>OnCreateAutomationPeer 재정의  
 재정의 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 에서 직접 또는 간접적으로 파생 되어야 하는 공급자 개체를 반환 하도록 사용자 지정 컨트롤에 대 한 메서드 <xref:System.Windows.Automation.Peers.AutomationPeer>합니다.  
  
### <a name="override-getpattern"></a>GetPattern 재정의  
 자동화 피어는 서버 쪽 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 공급자의 몇 가지 구현 측면을 간소화하지만 사용자 지정 컨트롤 자동화 피어는 패턴 인터페이스를 계속 처리해야 합니다. 비 WPF 공급자와 같은 피어에서 인터페이스의 구현을 제공 하 여 컨트롤 패턴을 지원할는 <xref:System.Windows.Automation.Provider?displayProperty=nameWithType> 네임 스페이스와 같은 <xref:System.Windows.Automation.Provider.IInvokeProvider>합니다. 컨트롤 패턴 인터페이스는 피어 자체 또는 다른 개체를 통해 구현할 수 있습니다. 피어의 구현의 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 지정한 패턴을 지 원하는 개체를 반환 합니다. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 호출 코드에서 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> 메서드를 지정 하 고는 <xref:System.Windows.Automation.Peers.PatternInterface> 열거형 값입니다. 재정의가 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> 지정된 된 패턴을 구현 하는 개체를 반환 해야 합니다. 컨트롤 패턴의 사용자 지정 구현을 없는 경우의 기본 형식 구현을 호출할 수 있습니다 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 패턴이 컨트롤 형식에 대해 지원 되지 않는 경우 해당 구현이 나 null 중 하나를 검색할 수 있습니다. NumericUpDown 컨트롤 사용자 지정 된 범위 내의 값으로 설정할 수 있습니다 예를 들어 있으므로 해당 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 피어 구현 합니다는 <xref:System.Windows.Automation.Provider.IRangeValueProvider> 인터페이스입니다. 다음 예제에서는 어떻게 피어의 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> 메서드의에 응답 하는 <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType> 값입니다.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 A <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> 메서드 패턴 공급자로 하위 지정할 수도 있습니다. 다음 코드 방법을 <xref:System.Windows.Controls.ItemsControl> 전송 스크롤 패턴 처리는 내부적 피어를 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다.  
  
```csharp  
public override object GetPattern(PatternInterface patternInterface)  
{  
    if (patternInterface == PatternInterface.Scroll)  
    {  
        ItemsControl owner = (ItemsControl) base.Owner;  
  
        // ScrollHost is internal to the ItemsControl class  
        if (owner.ScrollHost != null)  
        {  
            AutomationPeer peer = UIElementAutomationPeer.CreatePeerForElement(owner.ScrollHost);  
            if ((peer != null) && (peer is IScrollProvider))  
            {  
                peer.EventsSource = this;  
                return (IScrollProvider) peer;  
            }  
        }  
    }  
    return base.GetPattern(patternInterface);  
}  
```  
  
```vb  
Public Class Class1  
    Public Overrides Function GetPattern(ByVal patternInterface__1 As PatternInterface) As Object  
        If patternInterface1 = PatternInterface.Scroll Then  
            Dim owner As ItemsControl = DirectCast(MyBase.Owner, ItemsControl)  
  
            ' ScrollHost is internal to the ItemsControl class  
            If owner.ScrollHost IsNot Nothing Then  
                Dim peer As AutomationPeer = UIElementAutomationPeer.CreatePeerForElement(owner.ScrollHost)  
                If (peer IsNot Nothing) AndAlso (TypeOf peer Is IScrollProvider) Then  
                    peer.EventsSource = Me  
                    Return DirectCast(peer, IScrollProvider)  
                End If  
            End If  
        End If  
        Return MyBase.GetPattern(patternInterface1)  
    End Function  
End Class  
```  
  
 패턴 처리에 대 한 하위 요소를 지정 하려면이 코드는 하위 요소 개체를 가져오거나 사용 하 여 피어를 만듭니다는 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> 설정 하는 메서드를는 <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> 속성의 현재 피어에 새 피어 새 피어를 반환 합니다. 설정 <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> 하위 요소에 하위 자동화 피어 트리에 표시 되지 않으며 지정 하는 하위 요소에 의해 발생 하는 모든 이벤트에 지정 된 컨트롤에서 발생 한 것으로 <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>합니다. <xref:System.Windows.Controls.ScrollViewer> 컨트롤 자동화 트리에 나타나지 않으며 생성 하는 스크롤 이벤트에서 만들어진 것으로 표시 된 <xref:System.Windows.Controls.ItemsControl> 개체입니다.  
  
### <a name="override-core-methods"></a>"Core" 메서드 재정의  
 자동화 코드는 피어 클래스의 public 메서드를 호출하여 컨트롤에 대한 정보를 가져옵니다. 컨트롤에 대한 정보를 제공하려면 컨트롤 구현이 기본 자동화 피어 클래스에서 제공하는 구현과 다른 경우 이름이 "Core"로 끝나는 각 메서드를 재정의합니다. 여기에 최소한 컨트롤이 구현 해야는 <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> 및 <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> 메서드를 다음 예제와 같이 합니다.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 구현 <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> 컨트롤을 반환 하 여 설명는 <xref:System.Windows.Automation.ControlType> 값입니다. 반환할 수 있지만 <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>, 컨트롤을 정확 하 게 설명 하는 경우 보다 구체적인 컨트롤 형식 중 하나를 반환 해야 합니다. 반환 값이 <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> 구현 하는 공급자에 대 한 추가 작업이 필요한 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], 및 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 클라이언트 제품 제어 구조, 키보드 상호 작용 및 가능한 컨트롤 패턴을 예상할 수 없는 합니다.  
  
 구현 된 <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> 및 <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> 컨트롤 데이터 콘텐츠가 포함 되어 사용자 인터페이스 (또는 둘 다)에 대화형 역할을 수행 하는지 여부를 나타내는 방법입니다. 기본적으로 두 메서드 모두 `true`를 반환합니다. 이러한 설정에서는 화면 읽기 프로그램과 같은 자동화 도구의 유용성이 향상되며, 이러한 메서드를 사용하여 자동화 트리를 필터링할 수 있습니다. 경우에 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 메서드 전송 패턴 subelement 피어 이며 subelement 피어의 처리 <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> 메서드는 하위 요소 피어 자동화 트리를 숨기려면 false를 반환할 수 있습니다. 예를 들어 스크롤는 <xref:System.Windows.Controls.ListBox> 에 의해 처리 됩니다는 <xref:System.Windows.Controls.ScrollViewer>, 및에 대 한 자동화 피어 <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType> 에서 반환 되는 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 의 메서드는 <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> 와 연결 된는 <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>합니다. 따라서는 <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> 의 메서드는 <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> 반환 `false`되도록는 <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> 자동화 트리에 나타나지 않습니다.  
  
 자동화 피어는 컨트롤에 적절한 기본값을 제공해야 합니다. XAML 컨트롤을 참조 하는 포함 하 여 피어 구현을 코어 메서드의 재정의할 수 참고 <xref:System.Windows.Automation.AutomationProperties> 특성입니다. 예를 들어 다음 XAML에서는 사용자 지정된 두 가지 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 속성이 있는 단추를 만듭니다.  
  
```xaml  
<Button AutomationProperties.Name="Special"   
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>패턴 공급자 구현  
 사용자 지정 공급자에서 구현한 인터페이스는 소유 요소에서 직접 파생 되는 경우에 명시적으로 선언 됩니다 <xref:System.Windows.Controls.Control>합니다. 다음 코드에 대 한 피어를 선언 하는 예를 들어 한 <xref:System.Windows.Controls.Control> 범위 값을 구현 하는 합니다.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 컨트롤의 소유자와 같은 특정 컨트롤 형식에서 파생 된 경우 <xref:System.Windows.Controls.Primitives.RangeBase>, 피어 동등한 파생된 피어 클래스에서 파생 될 수 있습니다. 이 경우 피어에서 파생 <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>의 기본 구현을 제공 하는 <xref:System.Windows.Automation.Provider.IRangeValueProvider>합니다. 다음 코드에서는 이러한 피어의 선언을 보여 줍니다.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
 구현 예제는 [테마 및 UI 자동화 지원 샘플이 있는 NumericUpDown 사용자 지정 컨트롤](http://go.microsoft.com/fwlink/?LinkID=160025)을 참조하세요.  
  
### <a name="raise-events"></a>이벤트 발생  
 자동화 클라이언트는 자동화 이벤트를 구독할 수 있습니다. 사용자 지정 컨트롤 호출 하 여 컨트롤 상태 변경을 보고 해야 하는 <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> 메서드. 마찬가지로, 속성 값이 변경 될 때 호출 된 <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> 메서드. 다음 코드에서는 컨트롤 코드 내에서 피어 개체를 가져오고 메서드를 호출하여 이벤트를 발생시키는 방법을 보여 줍니다. 최적화 방법으로 코드는 이 이벤트 유형에 대한 수신기가 있는지 확인합니다. 수신기가 있는 경우에만 이벤트가 발생되면 불필요한 오버헤드를 방지하고 컨트롤이 응답 가능한 상태를 유지하는 데 도움이 됩니다.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>참고 항목  
 [UI 자동화 개요](../../../../docs/framework/ui-automation/ui-automation-overview.md)  
 [테마와 UI 자동화 지원 샘플이 있는 NumericUpDown 사용자 지정 컨트롤](http://go.microsoft.com/fwlink/?LinkID=160025)  
 [서버 쪽 UI 자동화 공급자 구현](../../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
