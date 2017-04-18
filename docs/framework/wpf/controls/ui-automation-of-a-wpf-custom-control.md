---
title: "WPF 사용자 지정 컨트롤의 UI 자동화 | Microsoft Docs"
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
  - "UI 자동화 적용 사용자 지정 컨트롤 [WPF]"
  - "사용자 지정 컨트롤에 적용 되는 접근성 [WPF]"
  - "내게 필요한 옵션 향상 사용자 지정 컨트롤 [WPF]"
  - "사용자 지정 컨트롤과 함께 사용 하 여 UI 자동화 [WPF]"
ms.assetid: 47b310fc-fbd5-4ce2-a606-22d04c6d4911
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# WPF 사용자 지정 컨트롤의 UI 자동화
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)]자동화 클라이언트가 검사 하거나 다양 한 플랫폼 및 프레임 워크의 사용자 인터페이스를 운영 하는 데 사용할 수 있는 일반화 된 단일 인터페이스를 제공 합니다. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]품질 보증 (테스트) 코드 및 사용자 인터페이스 요소를 검사 하 고 다른 코드에서 상호 작용은 사용자를 시뮬레이션할 화면 판독기와 같은 내게 필요한 옵션 지원 응용 프로그램을 모두 사용 합니다. 에 대 한 내용은 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 모든 플랫폼에서 내게 필요한 옵션을 참조 하십시오.  
  
 이 항목에서는 WPF 응용 프로그램에서 실행 되는 사용자 지정 컨트롤에 대 한 서버 쪽 UI 자동화 공급자를 구현 하는 방법을 설명 합니다. WPF는 지원 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 사용자 인터페이스 요소의 트리 기능과 유사한 피어 자동화 개체의 트리를 통해. 테스트 코드 및 내게 필요한 옵션 기능 자동화 피어 개체에 직접 사용 (in-process 코드)를 제공 하는 응용 프로그램에서 제공 하는 일반화 된 인터페이스를 통해 또는 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]합니다.  
  
 
  
<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>자동화 피어 클래스  
 WPF 컨트롤 지원 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 피어 클래스에서 파생 되는 트리를 통해 <xref:System.Windows.Automation.Peers.AutomationPeer>합니다. 규칙에 따라 피어 클래스 이름의 컨트롤 클래스 이름으로 시작 하 고 "AutomationPeer" 끝납니다. 예를 들어 <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> 에 대 한 피어 클래스는 <xref:System.Windows.Controls.Button> 클래스를 제어 합니다. 피어 클래스와 거의 동일한는 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 종류를 제어 하지만 관련 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 요소입니다. 자동화 코드를 통해 WPF 응용 프로그램에 액세스 하는 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 인터페이스 자동화 피어를 직접 사용 하지 않지만 동일한 프로세스 공간에서 자동화 코드 자동화 피어를 직접 사용할 수 있습니다.  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>기본 제공 자동화 피어 클래스  
 요소는 사용자에서 인터페이스 작업을 허용 하는지 또는 화면 판독기 응용 프로그램의 사용자에 게 필요한 정보가 포함 된 경우 자동화 피어 클래스를 구현 합니다. 모든 WPF 시각적 요소는 자동화 피어가 있습니다. 자동화 피어를 구현 하는 클래스의 예로 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.TextBox>, 및 <xref:System.Windows.Controls.Label>합니다. 자동화 피어를 구현 하지 않는 클래스의 예는 클래스에서 파생 되는 <xref:System.Windows.Controls.Decorator>와 같은 <xref:System.Windows.Controls.Border>, 및 클래스에 따라 <xref:System.Windows.Controls.Panel>와 같은 <xref:System.Windows.Controls.Grid> 및 <xref:System.Windows.Controls.Canvas>합니다.  
  
 기본 <xref:System.Windows.Controls.Control> 클래스에 해당 하는 피어 클래스가 없습니다. 파생 되는 사용자 지정 컨트롤에 해당 하는 피어 클래스가 필요한 경우 <xref:System.Windows.Controls.Control>에서 사용자 지정 피어 클래스를 파생 시켜야 <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>합니다.  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>파생 된 피어에 대 한 보안 고려 사항  
 자동화 피어 부분 신뢰 환경에서 실행 해야 합니다. UIAutomationClient 어셈블리의 코드는 부분 신뢰 환경에서 실행 하도록 구성 되지 않은 및 자동화 피어 코드를 해당 어셈블리를 참조할 수 없습니다. 대신, UIAutomationTypes 어셈블리의 클래스를 사용 해야 합니다. 예를 들어 사용 해야는 <xref:System.Windows.Automation.AutomationElementIdentifiers> 에 해당 하는 UIAutomationTypes 어셈블리에서 클래스는 <xref:System.Windows.Automation.AutomationElement> UIAutomationClient 어셈블리의 클래스입니다. 자동화 피어 코드에서 UIAutomationTypes 어셈블리를 참조 하지 않아도 안전 합니다.  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>피어 탐색  
 자동화 피어를 찾은 후 in-process 코드 탐색할 수 피어 트리는 개체를 호출 하 여 <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> 및 <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> 메서드. 간의 탐색 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 컨트롤 내에서 요소는 피어 구현에 의해 사용할 수는 <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> 메서드. UI 자동화 시스템; 컨트롤 내에 포함 된 하위 트리를 작성 하려면이 메서드를 호출 합니다. 예를 들어 목록 상자에서 항목을 나열 합니다. 기본 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=fullName> 메서드 자동화 피어 트리를 작성 하는 요소는 시각적 트리를 이동 합니다. 사용자 지정 컨트롤 자동화 클라이언트에서 정보를 전달 하거나 사용자 상호 작용을 허용 하는 요소의 자동화 피어를 반환 하는 자식 요소를 노출 하려면이 메서드를 재정의 합니다.  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>파생 된 피어 사용자 지정  
 파생 되는 모든 클래스 <xref:System.Windows.UIElement> 및 <xref:System.Windows.ContentElement> 보호 된 가상 메서드를 포함 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>합니다. WPF 호출 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 각 컨트롤에 대 한 자동화 피어 개체를 가져오려는 합니다. 자동화 코드는 컨트롤의 특징 및 기능에 대 한 정보 및 대화형 시뮬레이션 하 피어를 사용할 수 있습니다. 자동화를 지 원하는 사용자 지정 컨트롤을 재정의 해야 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 에서 파생 되는 클래스의 인스턴스를 반환 하 고 <xref:System.Windows.Automation.Peers.AutomationPeer>합니다. 예를 들어, 사용자 지정 컨트롤에서 파생 된 경우는 <xref:System.Windows.Controls.Primitives.ButtonBase> 클래스를 다음으로 반환 되는 개체 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 에서 파생 되어야 <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>합니다.  
  
 사용자 지정 컨트롤을 구현할 때에 고유한 사용자 지정 컨트롤에 특정 동작을 설명 하는 기본 자동화 피어 클래스에서 "핵심" 메서드를 재정의 해야 합니다.  
  
### <a name="override-oncreateautomationpeer"></a>OnCreateAutomationPeer 재정의  
 재정의 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 에서 직접 또는 간접적으로 파생 되어야 하는 공급자 개체를 반환 하도록 사용자 지정 컨트롤에 대 한 메서드 <xref:System.Windows.Automation.Peers.AutomationPeer>합니다.  
  
### <a name="override-getpattern"></a>GetPattern 재정의  
 서버 쪽의 몇 가지 구현 측면을 간소화 하는 자동화 피어 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 공급자, 하지만 사용자 지정 컨트롤 자동화 피어는 패턴 인터페이스 처리 계속 해야 합니다. 피어에 인터페이스의 구현을 제공 하 여 컨트롤 패턴 지원 비 WPF 공급자와 같이 <xref:System.Windows.Automation.Provider?displayProperty=fullName> 네임 스페이스와 같은 <xref:System.Windows.Automation.Provider.IInvokeProvider>합니다. 컨트롤 패턴 인터페이스 자체는 피어 또는 다른 개체에 의해 구현할 수 있습니다. 피어의 구현의 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 지정 된 패턴을 지 원하는 개체를 반환 합니다. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]호출 코드는 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> 메서드를 지정 하 고는 <xref:System.Windows.Automation.Peers.PatternInterface> 열거형 값입니다. 재정의 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> 지정된 된 패턴을 구현 하는 개체를 반환 해야 합니다. 컨트롤 패턴의 사용자 지정 구현을 없는 경우의 기본 형식 구현을 호출할 수 있습니다 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 패턴이 컨트롤 형식에 대해 지원 되지 않는 경우 해당 구현 나 null를 검색할 수 있습니다. NumericUpDown 컨트롤 사용자 지정 된 범위 내의 값으로 설정할 수 있습니다 예를 들어 있으므로 해당 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 피어를 구현 합니다는 <xref:System.Windows.Automation.Provider.IRangeValueProvider> 인터페이스입니다. 다음 예제와 어떻게 피어의 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> 메서드는에 응답 하는 <xref:System.Windows.Automation.Peers.PatternInterface?displayProperty=fullName> 값입니다.  
  
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
  
 패턴 처리에 대 한 하위 요소를 지정 하려면이 코드는 하위 요소 개체를 가져오거나 피어를 사용 하 여 만듭니다는 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> 설정 하는 메서드를는 <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> 현재 피어에는 새 피어의 속성 새 피어를 반환 합니다. 설정 <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> 하위 요소에 자동화 피어 트리에 나타나지 않도록 하위를 방지 하 고 지정 된 하위 요소에 의해 발생 하는 모든 이벤트에 지정 된 컨트롤에서 발생 한 것 처럼 <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>합니다. <xref:System.Windows.Controls.ScrollViewer> 컨트롤이 자동화 트리에 나타나지 않으면 및 생성 하는 스크롤 이벤트에서 만들어진 것으로 표시 된 <xref:System.Windows.Controls.ItemsControl> 개체입니다.  
  
### <a name="override-core-methods"></a>"Core" 메서드를 재정의 합니다.  
 자동화 코드 피어 클래스의 공용 메서드를 호출 하 여 컨트롤에 대 한 정보를 가져옵니다. 컨트롤에 대 한 정보를 제공 하려면 사용자 지정 컨트롤 구현이 기본 자동화 피어 클래스에서 제공 하는 것과 다른 경우 이름이 "핵심"로 끝나는 각 메서드를 재정의 합니다. 여기에 최소한 구현 해야는 <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> 및 <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> 메서드를 다음 예와에서 같이 합니다.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 구현 <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> 반환 하 여 컨트롤을 설명는 <xref:System.Windows.Automation.ControlType> 값입니다. 반환할 수 있지만 <xref:System.Windows.Automation.ControlType.Custom?displayProperty=fullName>, 컨트롤을 정확 하 게 설명 하는 경우 보다 구체적인 컨트롤 형식 중 하나를 반환 해야 합니다. 반환 값이 <xref:System.Windows.Automation.ControlType.Custom?displayProperty=fullName> 를 구현 하는 공급자에 대 한 추가 작업이 필요한 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], 및 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 클라이언트 제품 제어 구조, 키보드 상호 작용 및 가능한 컨트롤 패턴을 예상할 수 없는 경우.  
  
 구현 된 <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> 및 <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> 컨트롤 데이터 내용을 포함 되어는 대화형 사용자 인터페이스 (또는 둘 모두)에서 역할을 충족 하는지 여부를 나타내는 방법입니다. 기본적으로 두 메서드 모두 반환 `true`합니다. 이러한 설정을 자동화 도구 자동화 트리를 필터링 하려면 이러한 메서드를 사용할 수 있는 화면 판독기 등의 유용성이 향상 됩니다. 경우에 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 메서드 전송 패턴을 하위 피어, 하위 요소 피어의 처리 <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> 메서드는 하위 요소 피어 자동화 트리를 숨기려면 false를 반환할 수 있습니다. 예를 들어 스크롤는 <xref:System.Windows.Controls.ListBox> 에 의해 처리 됩니다는 <xref:System.Windows.Controls.ScrollViewer>, 및에 대 한 자동화 피어 <xref:System.Windows.Automation.Peers.PatternInterface?displayProperty=fullName> 에서 반환 되는 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 의 메서드는 <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> 와 연결 된는 <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>합니다. 따라서는 <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> 의 메서드는 <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> 반환 `false`하는 <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> 자동화 트리에 표시 되지 않습니다.  
  
 자동화 피어 사용자 컨트롤에 대 한 적절 한 기본값을 제공 해야 합니다. XAML 사용자 컨트롤을 참조 하는 코어 메서드의 피어 구현을 포함 하 여 재정의할 수는 참고 <xref:System.Windows.Automation.AutomationProperties> 특성입니다. 다음 XAML 사용자 지정 된 두 개는 단추를 만듭니다 하는 예를 들어 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 속성입니다.  
  
```xaml  
<Button AutomationProperties.Name="Special"   
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>패턴 공급자 구현  
 사용자 지정 공급자를 구현한 인터페이스는 소유 요소에서 직접 파생 된 경우에 명시적으로 선언 됩니다 <xref:System.Windows.Controls.Control>합니다. 다음 코드에 대 한 피어를 선언 하는 예를 들어 한 <xref:System.Windows.Controls.Control> 범위 값을 구현 하는 합니다.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 경우 소유 하는 컨트롤에서에서 파생 되는 특정 유형의 제어와 같은 <xref:System.Windows.Controls.Primitives.RangeBase>, 피어 동등한 파생된 피어 클래스에서 파생 될 수 있습니다. 피어에서 파생 된다는 경우 <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>의 기본 구현을 제공 하는 <xref:System.Windows.Automation.Provider.IRangeValueProvider>합니다. 다음 코드에는 이와 같은 피어의 선언을 보여 줍니다.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
 구현 예제를 참조 하십시오. [테마 및 UI 자동화 지원 샘플이 있는 NumericUpDown 사용자 지정 컨트롤](http://go.microsoft.com/fwlink/?LinkID=160025)합니다.  
  
### <a name="raise-events"></a>이벤트를 발생 시킵니다.  
 자동화 클라이언트 자동화 이벤트를 구독할 수 있습니다. 사용자 지정 컨트롤에는 호출 하 여 컨트롤 상태 변경을 보고 해야는 <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> 메서드. 속성 값이 변경 될 때 호출 되는 마찬가지로 <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> 메서드. 다음 코드에는 제어 코드 내에서 피어 개체를 가져와 이벤트를 발생 시키는 메서드를 호출 하는 방법을 보여 줍니다. 코드는 최적화로이 종류의 이벤트에 대 한 수신기가 있는지를 결정 합니다. 수신기가 있는 경우에 이벤트를 발생 시키는 불필요 한 오버 헤드를 방지 하 고 응답을 유지 하는 컨트롤을 지원 합니다.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>참고 항목  
 [UI 자동화 개요](../../../../docs/framework/ui-automation/ui-automation-overview.md)   
 [테마 및 UI 자동화 지원 샘플이 있는 NumericUpDown 사용자 지정 컨트롤](http://go.microsoft.com/fwlink/?LinkID=160025)   
 [서버 쪽 UI 자동화 공급자 구현](../../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)