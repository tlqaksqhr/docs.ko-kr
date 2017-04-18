---
title: "UI Automation and Microsoft Active Accessibility | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Active Accessibility"
  - "UI Automation, Active Accessibility compared to"
  - "UI Automation, Microsoft Active Accessibility"
  - "Active Accessibility, UI Automation compared to"
ms.assetid: 87bee662-0a3e-4232-a421-20e7a5968321
caps.latest.revision: 24
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 23
---
# UI Automation and Microsoft Active Accessibility
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)]는 응용 프로그램을 액세스할 수 있도록 했던 이전 솔루션입니다.[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]은 [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)]의 새로운 접근성 모델로서 보조 기술 제품 및 자동 테스트 도구의 요구를 충족시키기 위한 것입니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]은 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]를 통해 다양한 개선 사항을 제공합니다.  
  
 이 항목에서는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]의 주요 기능에 대해 설명하고 이러한 기능이 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]와 어떻게 다른지 설명합니다.  
  
<a name="Programming_Languages_compare"></a>   
## 프로그래밍 언어  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]는 이중 인터페이스 지원과 함께 [!INCLUDE[TLA#tla_com](../../../includes/tlasharptla-com-md.md)]을 기반으로 하므로 C\/C\+\+, [!INCLUDE[TLA#tla_vb6](../../../includes/tlasharptla-vb6-md.md)] 및 스크립팅 언어로 프로그래밍 가능합니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\(표준 컨트롤에 대한 클라이언트 쪽 공급자 라이브러리 포함\)은 관리되는 코드로 작성되므로 [!INCLUDE[TLA#tla_vcshrp](../../../includes/tlasharptla-vcshrp-md.md)] 또는 [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]을 사용하여 UI 자동화 클라이언트 응용 프로그램을 쉽게 프로그래밍할 수 있습니다. 인터페이스 구현인 UI 자동화 공급자는 관리되는 코드 또는 C\/C\+\+로 작성할 수 있습니다.  
  
<a name="Support_in_Windows_Presentation_Foundation_"></a>   
## Windows Presentation Foundation에서의 지원  
 [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)]는 사용자 인터페이스를 만들기 위한 새 모델입니다.[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] 요소에는 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]에 대한 기본 지원이 포함되지 않습니다. 하지만 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 클라이언트에 대한 브리징 지원이 포함된 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]을 지원합니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대해 특별히 작성된 클라이언트만 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]의 접근성 기능\(예: 다양한 텍스트 지원\)을 활용할 수 있습니다.  
  
<a name="Servers_and_Clients_compare"></a>   
## 서버 및 클라이언트  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]에서, 서버와 클라이언트 직접 통신하며 이러한 통신은 대부분 서버의 `IAccessible` 구현을 통해 이루어집니다.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서, 핵심 서비스는 서버\(공급자라고 함\)와 클라이언트 사이에 있습니다. 핵심 서비스 공급자는 공급자가 구현한 인터페이스를 호출하고, 요소에 대한 고유한 런타임 식별자 생성 등과 같은 추가적인 서비스를 제공합니다. 클라이언트 응용 프로그램은  라이브러리 함수를 사용하여 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 서비스를 호출합니다.  
  
 UI 자동화 공급자는 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 클라이언트에 정보를 제공할 수 있으며, [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 서버는 UI 자동화 클라이언트 응용 프로그램에 정보를 제공할 수 있습니다. 그러나 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]만큼 많은 정보를 노출하지 않기 때문에 두 모델이 완전히 호환되지는 않습니다.  
  
<a name="UI_Elements_compare"></a>   
## UI 요소  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]는 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 요소를 `IAccessible` 인터페이스 또는 자식 식별자로 제공합니다. 두 `IAccessible` 포인터를 비교하여 동일한 요소를 참조하는지 확인하기는 어렵습니다.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서, 모든 요소는 <xref:System.Windows.Automation.AutomationElement> 개체로 표시됩니다. 요소의 고유한 런타임 식별자를 비교하는 같음 연산자 또는 <xref:System.Windows.Automation.AutomationElement.Equals%2A> 메서드를 사용하여 비교합니다.  
  
<a name="Tree_Views_and_Navigation_compare"></a>   
## 트리 뷰 및 탐색  
 화면의 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 요소는 데스크톱이 루트, 응용 프로그램 창이 직계 자식, 응용 프로그램 내의 요소가 추가적인 하위 항목인 트리 구조로 표시될 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]에서, 최종 사용자와 관련되지 않은 여러 자동화 요소가 트리에 노출됩니다. 클라이언트 응용 프로그램은 모든 요소를 확인하여 의미 있는 요소를 파악해야 합니다.  
  
 UI 자동화 클라이언트 응용 프로그램은 필터링된 뷰를 통해 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]를 표시합니다. 이 뷰에는 사용자에게 정보를 제공하거나 상호 작용을 활성화하는 등 필요한 요소만 포함됩니다. 컨트롤 요소만 미리 정의된 뷰와 콘텐츠 요소만 미리 정의된 뷰를 사용할 수 있습니다. 또한 응용 프로그램이 사용자 지정 뷰를 정의할 수 있습니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]은 사용자에게 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]를 설명하고 응용 프로그램과 상호 작용할 수 있도록 도와주는 작업을 간소화합니다.  
  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]에서, 요소 간 탐색은 공간\(예: 화면 왼쪽에 있는 요소로 이동\), 논리적\(예: 다음 메뉴 항목으로 이동 또는 대화 상자 내에서 탭 순서대로 다음 항목으로 이동\), 계층적\(예: 컨테이너의 첫 번째 자식 이동 또는 자식에서 부모로 이동\) 이동 방법 중 하나로 수행됩니다. 계층적 탐색의 경우, 자식 요소가 `IAccessible`을 구현하는 개체가 아닐 수도 있기 때문에 복잡한 방법입니다.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서, 모든 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 요소는 동일한 기본 기능을 지원하는 <xref:System.Windows.Automation.AutomationElement> 개체입니다. \(공급자의 관점에서 보면 이 개체는 <xref:System.Windows.Automation.Provider.IRawElementProviderSimple>에서 상속된 인터페이스를 구현하는 개체입니다.\) 탐색은 주로 계층 구조입니다. 부모에서 자식으로, 한 형제에서 다른 형제로 탐색합니다. \(형제 간 탐색은 탭 순서를 따를 수 있기 때문에 논리적 요소가 있습니다.\)<xref:System.Windows.Automation.TreeWalker> 클래스를 사용하여 트리의 필터링된 뷰를 통해 시작점에서 탐색할 수 있습니다.<xref:System.Windows.Automation.AutomationElement.FindFirst%2A> 및 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>을 사용하여 특정 자식 또는 하위 항목을 탐색할 수도 있습니다. 예를 들어, 지정된 컨트롤 패턴을 지원하는 대화 상자 내에서 모든 요소를 쉽게 검색할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서의 탐색은 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]에서 보다 일관적입니다. 드롭다운 목록 및 팝업 창과 같은 일부 요소는 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 트리에 두 번 나타나며, 이러한 요소를 탐색하면 예기치 않은 결과가 발생할 수 있습니다. 사실상 Rebar 컨트롤에 대해 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]를 올바르게 구현하는 것은 불가능합니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]을 사용하면 부모 재지정 및 위치 변경이 가능하므로, 창 소유권에 의해 계층 구조가 적용되더라도 트리에서 요소를 원하는 위치에 배치할 수 있습니다.  
  
<a name="Roles_and_Control_Types"></a>   
## 역할 및 컨트롤 형식  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]는 `accRole` 속성\(`IAccessible::get_actRole`\)을 사용하여 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]에서 ROLE\_SYSTEM\_SLIDER 또는 ROLE\_SYSTEM\_MENUITEM과 같은 요소의 역할 설명을 검색합니다. 요소의 역할을 통해 사용 가능한 기능을 알 수 있습니다.`IAccessible::accSelect` 및 `IAccessible::accDoDefaultAction`과 같은 고정 메서드를 사용하여 컨트롤과 상호 작용할 수 있습니다. 클라이언트 응용 프로그램과 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 간의 상호 작용은 `IAccessible`을 통해서 수행할 수 있는 작업으로 제한됩니다.  
  
 한편, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]은 주로 예상 기능에서 요소의 컨트롤 형식\(<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> 속성으로 설명됨\)을 분리합니다. 기능은 특수화된 인터페이스의 구현을 통해 공급자가 지원하는 컨트롤 패턴에 의해 결정됩니다. 컨트롤 패턴을 조합하여 특정 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 요소가 지원하는 전체 기능 집합을 설명할 수 있습니다. 일부 공급자는 특정 컨트롤 패턴을 지원하는 데 필요합니다. 예를 들어, 확인란에 대한 공급자는 Toggle 컨트롤 패턴을 지원해야 합니다. 기타 공급자는 하나 이상의 컨트롤 패턴 집합을 지원하는 데 필요합니다. 예를 들어, 단추는 Toggle 또는 Invoke를 지원해야 합니다. 컨트롤 패턴을 지원하지 않는 공급자도 있습니다. 예를 들어 이동, 크기 조정 또는 도킹할 수 없는 창에는 컨트롤 패턴이 없습니다.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]은 <xref:System.Windows.Automation.ControlType.Custom> 속성으로 식별되고 <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty> 속성으로 설명할 수 있는 사용자 지정 컨트롤을 지원합니다.  
  
 다음 표에서는 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 역할과 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 컨트롤 형식의 매핑을 보여줍니다.  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 역할|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 컨트롤 형식|  
|--------------------------------------------------------------------|----------------------------------------------------------------------------------|  
|ROLE\_SYSTEM\_PUSHBUTTON|단추|  
|ROLE\_SYSTEM\_CLIENT|일정|  
|ROLE\_SYSTEM\_CHECKBUTTON|확인란|  
|ROLE\_SYSTEM\_COMBOBOX|콤보 상자|  
|ROLE\_SYSTEM\_CLIENT|사용자 지정|  
|ROLE\_SYSTEM\_LIST|데이터 표|  
|ROLE\_SYSTEM\_LISTITEM|데이터 항목|  
|ROLE\_SYSTEM\_DOCUMENT|문서|  
|ROLE\_SYSTEM\_TEXT|편집|  
|ROLE\_SYSTEM\_GROUPING|그룹화|  
|ROLE\_SYSTEM\_LIST|머리글|  
|ROLE\_SYSTEM\_COLUMNHEADER|헤더 항목|  
|ROLE\_SYSTEM\_LINK|하이퍼링크|  
|ROLE\_SYSTEM\_GRAPHIC|이미지|  
|ROLE\_SYSTEM\_LIST|목록|  
|ROLE\_SYSTEM\_LISTITEM|목록 항목|  
|ROLE\_SYSTEM\_MENUPOPUP|메뉴|  
|ROLE\_SYSTEM\_MENUBAR|메뉴 모음|  
|ROLE\_SYSTEM\_MENUITEM|Menu item|  
|ROLE\_SYSTEM\_PANE|창|  
|ROLE\_SYSTEM\_PROGRESSBAR|진행률 표시줄|  
|ROLE\_SYSTEM\_RADIOBUTTON|라디오 단추|  
|ROLE\_SYSTEM\_SCROLLBAR|스크롤 막대|  
|ROLE\_SYSTEM\_SEPARATOR|구분 기호|  
|ROLE\_SYSTEM\_SLIDER|슬라이더|  
|ROLE\_SYSTEM\_SPINBUTTON|Spinner|  
|ROLE\_SYSTEM\_SPLITBUTTON|분할 단추|  
|ROLE\_SYSTEM\_STATUSBAR|상태 표시줄|  
|ROLE\_SYSTEM\_PAGETABLIST|탭|  
|ROLE\_SYSTEM\_PAGETAB|탭 항목|  
|ROLE\_SYSTEM\_TABLE|표|  
|ROLE\_SYSTEM\_STATICTEXT|텍스트|  
|ROLE\_SYSTEM\_INDICATOR|Thumb|  
|ROLE\_SYSTEM\_TITLEBAR|제목 표시줄|  
|ROLE\_SYSTEM\_TOOLBAR|도구 모음|  
|ROLE\_SYSTEM\_TOOLTIP|도구 설명|  
|ROLE\_SYSTEM\_OUTLINE|Tree|  
|ROLE\_SYSTEM\_OUTLINEITEM|트리 항목|  
|ROLE\_SYSTEM\_WINDOW|창|  
  
 다른 컨트롤 형식에 대한 자세한 내용은 [UI Automation Control Types](../../../docs/framework/ui-automation/ui-automation-control-types.md)을 참조하세요.  
  
<a name="States_and_Properties"></a>   
## 상태 및 속성  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]에서, 요소는 속성의 공통 집합을 지원하고 일부 속성\(예: `accState`\)은 요소의 역할에 따라 다양한 사항을 설명해야 합니다. 서버는 요소와 관련이 없더라도 속성을 반환하는 `IAccessible`의 모든 메서드를 구현해야 합니다.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]은 더 많은 속성을 정의하며, 그중 일부는 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]에서 상태에 해당합니다. 일부 속성은 모든 요소에 공통되지만 컨트롤 형식과 컨트롤 패턴에만 관련된 속성도 있습니다. 속성은 고유한 식별자로 구분되며, 대부분의 속성은 단일 메서드 <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> 또는 <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>를 사용하여 검색할 수 있습니다.<xref:System.Windows.Automation.AutomationElement.Current%2A> 및 <xref:System.Windows.Automation.AutomationElement.Cached%2A> 속성 접근자에서 다양한 속성을 쉽게 검색할 수도 있습니다.  
  
 UI 자동화 공급자는 관련이 없는 속성을 구현할 필요가 없지만 지원하지 않는 속성에 대해 `null` 값을 반환할 수 있습니다. 또한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 핵심 서비스는 기본 창 공급자에서 일부 속성을 가져올 수 있으며, 이러한 속성은 공급자가 명시적으로 구현하는 속성과 병합됩니다.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]는 기타 여러 속성을 지원하는 것 이외에도 하나의 프로세스 간 호출로 여러 속성을 검색할 수 있도록 허용하여 더 높은 성능을 제공합니다.  
  
 다음 표는 두 모델에서 속성 간의 상관 관계를 보여줍니다.  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 속성 접근자|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성 ID|주의|  
|------------------------------------------------------------------------|---------------------------------------------------------------------------------|--------|  
|`get_accKeyboardShortcut`|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty> 또는 <xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|둘 다 있는 경우 `AccessKeyProperty`가 우선적으로 적용됩니다.|  
|`get_accName`|<xref:System.Windows.Automation.AutomationElement.NameProperty>|``|  
|`get_accRole`|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|컨트롤 형식에 대한 역할 매핑은 이전 표를 참조하세요.|  
|`get_accValue`|<xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=fullName>|ValuePattern 또는 RangeValuePattern을 지원하는 컨트롤 형식에만 유효합니다. RangeValue 값은 MSAA 동작과 일관되도록 0\-100으로 정규화됩니다. 값 항목은 문자열을 사용합니다.|  
|`get_accHelp`|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>||  
|`accLocation`|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>||  
|`get_accDescription`|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서는 지원되지 않습니다.|`accDescription`은 MSAA 내에서 명확한 사양이 없기 때문에, 공급자가 이 속성에 다양한 정보를 배치합니다.|  
|`get_accHelpTopic`|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서는 지원되지 않습니다.||  
  
 다음 표는 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 상태 상수에 해당하는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성을 보여줍니다.  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 상태|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성|상태 변경 트리거 여부|  
|--------------------------------------------------------------------|------------------------------------------------------------------------------|------------------|  
|STATE\_SYSTEM\_CHECKED|확인란의 경우, <xref:System.Windows.Automation.TogglePattern.ToggleStateProperty><br /><br /> 라디오 단추의 경우, <xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|Y|  
|STATE\_SYSTEM\_COLLAPSED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> \= <xref:System.Windows.Automation.ExpandCollapseState>|Y|  
|STATE\_SYSTEM\_EXPANDED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> \= <xref:System.Windows.Automation.ExpandCollapseState>또는 <xref:System.Windows.Automation.ExpandCollapseState>|Y|  
|STATE\_SYSTEM\_FOCUSABLE|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|N|  
|STATE\_SYSTEM\_FOCUSED|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|N|  
|STATE\_SYSTEM\_HASPOPUP|메뉴 항목에 대해 <xref:System.Windows.Automation.ExpandCollapsePattern>|N|  
|STATE\_SYSTEM\_INVISIBLE|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> \= True이며 <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>가 <xref:System.Windows.Automation.NoClickablePointException> 발생|N|  
|STATE\_SYSTEM\_LINKED|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> \=<br /><br /> <xref:System.Windows.Automation.ControlType.Hyperlink>|N|  
|STATE\_SYSTEM\_MIXED|<xref:System.Windows.Automation.TogglePattern.TogglePatternInformation.ToggleState%2A> \= <xref:System.Windows.Automation.ToggleState>|N|  
|STATE\_SYSTEM\_MOVEABLE|<xref:System.Windows.Automation.TransformPattern.CanMoveProperty>|N|  
|STATE\_SYSTEM\_MUTLISELECTABLE|<xref:System.Windows.Automation.SelectionPattern.CanSelectMultipleProperty>|N|  
|STATE\_SYSTEM\_OFFSCREEN|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> \= True|N|  
|STATE\_SYSTEM\_PROTECTED|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|N|  
|STATE\_SYSTEM\_READONLY|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty?displayProperty=fullName> 및 <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty?displayProperty=fullName>|N|  
|STATE\_SYSTEM\_SELECTABLE|<xref:System.Windows.Automation.SelectionItemPattern>이 지원됨|N|  
|STATE\_SYSTEM\_SELECTED|<xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|N|  
|STATE\_SYSTEM\_SIZEABLE|<xref:System.Windows.Automation.TransformPattern.TransformPatternInformation.CanResize%2A>|N|  
|STATE\_SYSTEM\_UNAVAILABLE|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|Y|  
  
 다음 상태는 대부분의 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 컨트롤 서버에서 구현되지 않았거나 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 해당 항목이 없습니다.  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 상태|설명|  
|--------------------------------------------------------------------|--------|  
|STATE\_SYSTEM\_BUSY|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서 사용할 수 없음|  
|STATE\_SYSTEM\_DEFAULT|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서 사용할 수 없음|  
|STATE\_SYSTEM\_ANIMATED|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서 사용할 수 없음|  
|STATE\_SYSTEM\_EXTSELECTABLE|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 서버에서 폭넓게 구현되지 않음|  
|STATE\_SYSTEM\_MARQUEED|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 서버에서 폭넓게 구현되지 않음|  
|STATE\_SYSTEM\_SELFVOICING|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 서버에서 폭넓게 구현되지 않음|  
|STATE\_SYSTEM\_TRAVERSED|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서 사용할 수 없음|  
|STATE\_SYSTEM\_ALERT\_HIGH|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 서버에서 폭넓게 구현되지 않음|  
|STATE\_SYSTEM\_ALERT\_MEDIUM|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 서버에서 폭넓게 구현되지 않음|  
|STATE\_SYSTEM\_ALERT\_LOW|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 서버에서 폭넓게 구현되지 않음|  
|STATE\_SYSTEM\_FLOATING|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 서버에서 폭넓게 구현되지 않음|  
|STATE\_SYSTEM\_HOTTRACKED|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서 사용할 수 없음|  
|STATE\_SYSTEM\_PRESSED|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서 사용할 수 없음|  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성 식별자의 전체 목록을 보려면 [UI Automation Properties Overview](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)를 참조하세요.  
  
<a name="uiautomation_events_compare"></a>   
## 이벤트  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]에서와는 달리, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]의 이벤트 메커니즘은 Windows 이벤트 라우팅\(창 핸들과 밀접하게 연결\)을 사용하지 않으며 후크를 설정하는 데 클라이언트 응용 프로그램이 필요하지 않습니다. 이벤트에 대한 구독은 특정 이벤트뿐만 아니라 트리의 특정 부분에 대해서도 미세하게 조정할 수 있습니다. 공급자는 이벤트가 수신 대기하고 있는 사항을 추적하여 이벤트 발생을 미세 조정할 수 있습니다.  
  
 요소가 이벤트 콜백에 직접 전달되므로 클라이언트는 이벤트를 발생하는 요소를 쉽게 검색할 수 있습니다. 클라이언트가 이벤트를 구독할 때 캐시 요청이 활성화되어 있으면 요소의 속성이 자동으로 프리페치됩니다.  
  
 다음 표는 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] WinEvents와 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트의 상관 관계를 보여줍니다.  
  
|WinEvent|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트 식별자|  
|--------------|-----------------------------------------------------------------------------------|  
|EVENT\_OBJECT\_ACCELERATORCHANGE|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty> 속성 변경|  
|EVENT\_OBJECT\_CONTENTSCROLLED|연결된 스크롤 막대의 <xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> 또는 <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> 속성 변경|  
|EVENT\_OBJECT\_CREATE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_DEFACTIONCHANGE|동일한 요소 없음|  
|EVENT\_OBJECT\_DESCRIPTIONCHANGE|정확하게 해당하는 요소가 없습니다. <xref:System.Windows.Automation.AutomationElement.HelpTextProperty> 또는 <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty> 속성 변경이 이에 해당할 수 있습니다.|  
|EVENT\_OBJECT\_DESTROY|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_FOCUS|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT\_OBJECT\_HELPCHANGE|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty> 변경|  
|EVENT\_OBJECT\_HIDE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_LOCATIONCHANGE|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> 속성 변경|  
|EVENT\_OBJECT\_NAMECHANGE|<xref:System.Windows.Automation.AutomationElement.NameProperty> 속성 변경|  
|EVENT\_OBJECT\_PARENTCHANGE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_REORDER|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]에 일관적으로 사용되지 않았습니다. 직접적인 해당 이벤트가 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 정의되지 않았습니다.|  
|EVENT\_OBJECT\_SELECTION|<xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>|  
|EVENT\_OBJECT\_SELECTIONADD|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent>|  
|EVENT\_OBJECT\_SELECTIONREMOVE|<xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent>|  
|EVENT\_OBJECT\_SELECTIONWITHIN|동일한 요소 없음|  
|EVENT\_OBJECT\_SHOW|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_STATECHANGE|다양한 속성 변경 이벤트|  
|EVENT\_OBJECT\_VALUECHANGE|<xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=fullName> 및 <xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=fullName> 변경|  
|EVENT\_SYSTEM\_ALERT|동일한 요소 없음|  
|EVENT\_SYSTEM\_CAPTUREEND|동일한 요소 없음|  
|EVENT\_SYSTEM\_CAPTURESTART|동일한 요소 없음|  
|EVENT\_SYSTEM\_CONTEXTHELPEND|동일한 요소 없음|  
|EVENT\_SYSTEM\_CONTEXTHELPSTART|동일한 요소 없음|  
|EVENT\_SYSTEM\_DIALOGEND|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|  
|EVENT\_SYSTEM\_DIALOGSTART|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|  
|EVENT\_SYSTEM\_DRAGDROPEND|동일한 요소 없음|  
|EVENT\_SYSTEM\_DRAGDROPSTART|동일한 요소 없음|  
|EVENT\_SYSTEM\_FOREGROUND|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT\_SYSTEM\_MENUEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT\_SYSTEM\_MENUPOPUPEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT\_SYSTEM\_MENUPOPUPSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT\_SYSTEM\_MENUSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT\_SYSTEM\_MINIMIZEEND|<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty> 속성 변경|  
|EVENT\_SYSTEM\_MINIMIZESTART|<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty> 속성 변경|  
|EVENT\_SYSTEM\_MOVESIZEEND|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> 속성 변경|  
|EVENT\_SYSTEM\_MOVESIZESTART|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty> 속성 변경|  
|EVENT\_SYSTEM\_SCROLLINGEND|<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> or <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> 속성 변경|  
|EVENT\_SYSTEM\_SCROLLINGSTART|<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> or <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> 속성 변경|  
|EVENT\_SYSTEM\_SOUND|동일한 요소 없음|  
|EVENT\_SYSTEM\_SWITCHEND|동일한 요소가 없지만 <xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent> 이벤트는 새 응용 프로그램이 포커스를 받았음을 신호로 알립니다.|  
|EVENT\_SYSTEM\_SWITCHSTART|동일한 요소 없음|  
|동일한 요소 없음|<xref:System.Windows.Automation.MultipleViewPattern.CurrentViewProperty> 속성 변경|  
|동일한 요소 없음|<xref:System.Windows.Automation.ScrollPattern.HorizontallyScrollableProperty> 속성 변경|  
|동일한 요소 없음|<xref:System.Windows.Automation.ScrollPattern.VerticallyScrollableProperty> 속성 변경|  
|동일한 요소 없음|<xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty> 속성 변경|  
|동일한 요소 없음|<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> 속성 변경|  
|동일한 요소 없음|<xref:System.Windows.Automation.ScrollPattern.HorizontalViewSizeProperty> 속성 변경|  
|동일한 요소 없음|<xref:System.Windows.Automation.ScrollPattern.VerticalViewSizeProperty> 속성 변경|  
|동일한 요소 없음|<xref:System.Windows.Automation.TogglePattern.ToggleStateProperty> 속성 변경|  
|동일한 요소 없음|<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty> 속성 변경|  
|동일한 요소 없음|<xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent> 이벤트|  
|동일한 요소 없음|<xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent>|  
  
<a name="Security_compare"></a>   
## 보안  
 일부 `IAccessible` 사용자 지정 시나리오에서는 기본 `IAccessible`의 줄바꿈과 이를 호출해야 합니다. 부분적으로 신뢰할 수 있는 구성 요소는 코드 경로에 중간자로 사용할 수 없기 때문에 보안에 영향을 줍니다.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 모델에서는 다른 공급자 코드를 통해 호출하는 데 공급자가 필요하지 않습니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 핵심 서비스는 필요한 모든 집계를 수행합니다.  
  
## 참고 항목  
 [UI Automation Fundamentals](../../../docs/framework/ui-automation/index.md)