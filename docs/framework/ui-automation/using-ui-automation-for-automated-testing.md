---
title: "자동화된 테스트를 위해 UI 자동화 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automated testing
- testing, UI Automation
- UI Automation, automated testing
ms.assetid: 3a0435c0-a791-4ad7-ba92-a4c1d1231fde
caps.latest.revision: "26"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: f1a56f8f9c2f7e2b817290c89ba4eaf1ae71955e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="using-ui-automation-for-automated-testing"></a>자동화된 테스트를 위해 UI 자동화 사용
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 이 개요에서는 자동화된 테스트 시나리오에서 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 이 프레임워크로서 프로그래밍 방식 액세스에 얼마나 유용한지에 대해 설명합니다.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 은 모든 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] 프레임워크가 접근성이 좋고 쉽게 자동화되는 방법으로 복잡하고 다양한 기능을 노출할 수 있도록 하는 통합된 개체 모델을 제공합니다.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 은 [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)]의 후속 작업으로 개발되었습니다. [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 는 컨트롤 및 응용 프로그램에 액세스할 수 있도록 하는 솔루션을 제공하기 위해 설계된 기존 프레임워크입니다. [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 는 접근성 및 자동화 요구 사항이 매우 비슷하여 현재의 역할로 개선되었지만 테스트 자동화를 염두에 두고 개발된 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]은 접근성을 위한 보다 정교한 솔루션을 제공할 뿐만 아니라, 자동화된 테스트를 위한 강력한 기능을 제공하기 위해 특별히 설계되었습니다. 예를 들어, [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 는 단일 인터페이스를 사용하여 UI에 대한 정보를 노출하고 AT 제품에 필요한 정보를 수집하며, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 은 이 두 모델을 분리합니다.  
  
 공급자와 클라이언트 모두 자동화된 테스트 도구로 유용하게 사용할 수 있도록 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 을 구현해야 합니다. UI 자동화 공급자는 [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)] 운영 체제를 기반으로 하는 Microsoft Word, Excel 및 타사 응용 프로그램 또는 컨트롤입니다. UI 자동화 클라이언트에는 자동화된 테스트 스크립트 및 보조 기술 응용 프로그램이 포함됩니다.  
  
> [!NOTE]
>  이 개요는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]의 새로운 기능 및 향상된 자동화 테스트 기능을 보여주기 위한 것입니다. 이 개요는 접근성 기능에 대한 정보를 제공하기 위한 것이 아니며, 필요한 경우가 아니면 접근성을 다루지 않습니다.  
  
<a name="Using_UI_Automation_During_Development"></a>   
## <a name="ui-automation-in-a-provider"></a>공급자의 UI 자동화  
 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 를 자동화하기 위해 응용 프로그램 또는 컨트롤 개발자는 최종 사용자가 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 개체에서 표준 키보드 및 마우스 조작을 통해 수행할 수 있는 작업이 무엇인지 살펴봐야 합니다.  
  
 이러한 주요 작업이 확인되면, 해당 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 컨트롤 패턴(즉, [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 요소의 기능 및 동작을 미러링하는 컨트롤 패턴)을 컨트롤에 구현해야 합니다. 예를 들어, 콤보 상자 컨트롤의 사용자 상호 작용에는(예:대화 상자 실행) 일반적으로 콤보 상자를 확장 또는 축소하여 항목 목록을 숨기거나 표시하고, 목록에서 항목을 선택하고, 키보드 입력을 통해 새로운 값을 추가하는 작업이 포함됩니다.  
  
> [!NOTE]
>  다른 접근성 모델에서, 개발자는 개별 단추, 메뉴 또는 다른 컨트롤에서 직접 정보를 수집해야 합니다. 그러나 모든 컨트롤 형식은 수십 개의 작은 변형과 함께 제공됩니다. 즉, 누름 단추의 변형 10개가 동일한 방법으로 작동되고 동일한 기능을 수행한다고 해도 이들 모두는 고유한 컨트롤로 처리되어야 합니다. 이러한 컨트롤이 기능적으로 동일한지 알 수 있는 방법은 없습니다. 컨트롤 패턴은 이러한 공통적인 컨트롤 동작을 나타내기 위해 개발되었습니다. 자세한 내용은 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)을 참조하세요.  
  
<a name="Implementing_UI_Automation"></a>   
### <a name="implementing-ui-automation"></a>UI 자동화 구현  
 앞에서 언급했듯이, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서 제공되는 통합된 모델을 사용하지 않고 테스트 도구와 개발자는 프레임워크에서 컨트롤의 속성과 동작을 노출하기 위해서는 프레임워크 관련 정보를 알아야 합니다. [!INCLUDE[TLA2#tla_win](../../../includes/tla2sharptla-win-md.md)] , [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]및 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)]를 비롯하여, [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)]운영 체제 내에는 언제든지 여러 개의 다른 UI 프레임워크가 있을 수 있으므로 비슷한 컨트롤이 포함된 여러 응용 프로그램을 테스트하는 것은 어려울 수 있습니다. 예를 들어, 다음 표에서는 단추 컨트롤과 연결된 이름 (또는 텍스트)를 검색하는 데 필요한 프레임워크 관련 속성 이름에 대해 간략하게 설명하고 해당되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성 하나를 보여 줍니다.  
  
|UI 자동화 컨트롤 형식|UI 프레임워크|프레임워크 관련 속성|UI 자동화 속성|  
|--------------------------------|------------------|---------------------------------|----------------------------|  
|단추|Windows Presentation Foundation|콘텐츠|NameProperty|  
|단추|Win32|캡션|NameProperty|  
|이미지|HTML|alt|NameProperty|  
  
 UI 자동화 공급자는 컨트롤의 프레임워크 관련 속성을 해당 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성에 매핑하는 작업을 담당합니다.  
  
 공급자에서 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 구현에 대한 정보는 [UI Automation Providers for Managed Code](../../../docs/framework/ui-automation/ui-automation-providers-for-managed-code.md)를 참조하세요. 컨트롤 패턴 구현 정보는 [UI Automation Control Patterns](../../../docs/framework/ui-automation/ui-automation-control-patterns.md) 및 [UI Automation Text Pattern](../../../docs/framework/ui-automation/ui-automation-text-pattern.md)에서 볼 수 있습니다.  
  
<a name="Testing_with_UI_Automation"></a>   
## <a name="ui-automation-in-a-client"></a>클라이언트에서 UI 자동화  
 대부분의 자동화된 테스트 도구 및 시나리오에서는 사용자 인터페이스의 일관적이고 반복적인 조작을 목표로 하고 있습니다. 이러한 목표에는 컨트롤 그룹에서 수행되는 일련의 일반 작업에 반복되는 테스트 스크립트의 기록과 재생에서의 단위 테스트 관련 컨트롤이 포함될 수 있습니다.  
  
 자동화된 응용 프로그램에서 발생하는 복잡함 중 하나는 테스트와 동적 대상을 동기화하는 것이 어렵다는 점입니다. 현재 실행 중인 응용 프로그램의 목록을 표시하는 목록 상자 컨트롤(Windows 작업 관리자에 포함된)을 예로 들 수 있습니다. 목록 상자의 항목은 테스트 응용 프로그램의 컨트롤 외부에서 동적으로 업데이트되기 때문에, 목록 상자의 특정 항목 선택을 일관적으로 반복하는 것은 불가능합니다. 테스트 응용 프로그램의 컨트롤 외부에 있는 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 에서 단순 포커스 변경을 반복하려는 경우에도 이와 비슷한 문제가 발생할 수 있습니다.  
  
<a name="Programmatic_Access"></a>   
### <a name="programmatic-access"></a>프로그래밍 방식 액세스  
 프로그래밍 방식의 액세스는 기존의 마우스 및 키보드 입력으로 노출되는 모든 상호 작용 및 환경을 코드를 통해 모방할 수 있는 기능을 제공합니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 을 사용하면 5개의 구성 요소를 통해 프로그래밍 방식의 액세스를 사용할 수 있습니다.  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리는 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]구조를 통해 탐색을 용이하게 합니다. 트리는 hWnd의 컬렉션에서 빌드됩니다. 자세한 내용은 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)을 참조하세요.  
  
-   자동화 요소는 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]의 개별 구성 요소입니다. 이러한 요소는 hWnd보다 더 세부적인 경우가 많습니다. 자세한 내용은 [UI Automation Control Types Overview](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)을 참조하세요.  
  
-   자동화 속성은 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 요소에 대한 특정 정보를 제공합니다. 자세한 내용은 [UI Automation Properties Overview](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)을 참조하십시오.  
  
-   컨트롤 패턴은 컨트롤 기능의 특정 측면을 정의하며 속성, 메서드, 이벤트 및 구조 정보로 구성될 수 있습니다. 자세한 내용은 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)을 참조하세요.  
  
-   자동화 이벤트는 이벤트 알림 및 정보를 제공합니다. 자세한 내용은 [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md)을 참조하세요.  
  
<a name="Key_properties_critical_to_test_automation"></a>   
### <a name="key-properties-for-test-automation"></a>테스트 자동화에 대한 키 속성  
 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 내에서 모든 컨트롤을 고유하게 식별한 후에 찾을 수 있는 기능은 해당 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]에서 작동되는 자동화된 테스트 응용 프로그램에 대한 기본적인 사항을 제공합니다. 여기에 도움이 되는 클라이언트 및 공급자에 사용되는 몇 가지 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 속성이 있습니다.  
  
#### <a name="automationid"></a>AutomationID  
 형제 항목에서 자동화 요소를 고유하게 식별합니다. 제품이 여러 언어로 제공되는 경우, 일반적으로 지역화되는<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> 와 같은 속성과 달리 <xref:System.Windows.Automation.AutomationElement.NameProperty> 는 지역화되지 않습니다. [Use the AutomationID Property](../../../docs/framework/ui-automation/use-the-automationid-property.md)을 참조하세요.  
  
> [!NOTE]
>  <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> 에서는 자동화 트리 전체에서 고유한 ID를 보장하지 않습니다. 예를 들어, 응용 프로그램에는 여러 개의 최상위 메뉴가 있는 메뉴 컨트롤과 여러 개의 자식 메뉴 항목이 포함될 수 있습니다. 이러한 보조 메뉴 항목은 "Item1, Item 2, Item3 등"과 같이 일반적인 체계로 식별되어 최상위 메뉴 항목에서 자식에 대한 중복 식별자가 허용될 수 있습니다.  
  
#### <a name="controltype"></a>ControlType  
 자동화 요소가 나타내는 컨트롤 형식을 식별합니다. 컨트롤 형식에 대한 지식에서 중요한 정보를 유추할 수 있습니다. [UI Automation Control Types Overview](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)을 참조하세요.  
  
#### <a name="nameproperty"></a>NameProperty  
 컨트롤을 식별하거나 설명하는 텍스트 문자열입니다. <xref:System.Windows.Automation.AutomationElement.NameProperty> 는 지역화할 수 있으므로 주의해서 사용해야 합니다. [UI Automation Properties Overview](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)을 참조하세요.  
  
<a name="Steps_Required_To_Automate_the_UI_in_a_Test_Application"></a>   
### <a name="implementing-ui-automation-in-a-test-application"></a>테스트 응용 프로그램에서 UI 자동화 구현  
  
|||  
|-|-|  
|UI 자동화 참조를 추가합니다.|다음은 UI 자동화 클라이언트에 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] dll이 필요한 이유입니다.<br /><br /> -에 대 한 액세스를 제공 하는 UIAutomationClient.dll은 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클라이언트 쪽 Api입니다.<br />-Uiautomationclientsideprovider.dll은 자동화 하는 기능을 제공 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 컨트롤입니다. [UI Automation Support for Standard Controls](../../../docs/framework/ui-automation/ui-automation-support-for-standard-controls.md)을 참조하세요.<br />-에 정의 된 특정 형식에 대 한 액세스를 제공 하는 UIAutomationTypes.dll [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]합니다.|  
|<xref:System.Windows.Automation> 네임스페이스를 추가합니다.|이 네임스페이스에는 텍스트 처리를 제외하고 UI 자동화 클라이언트에서 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 의 기능을 사용하는 데 필요한 모든 것이 포함됩니다.|  
|<xref:System.Windows.Automation.Text> 네임스페이스를 추가합니다.|이 네임스페이스에는 UI 자동화 클라이언트에서 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 텍스트 처리의 기능을 사용하는 데 필요한 모든 것이 포함됩니다.|  
|필요한 컨트롤 찾기|자동화된 테스트 스크립트가 자동화 트리 내에서 필요한 컨트롤을 나타내는 UI 자동화 요소를 찾습니다.<br /><br /> 여러 가지 방법을 통해 코드를 사용하여 UI 자동화 요소를 가져올 수 있습니다.<br /><br /> -쿼리는 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 를 사용 하는 <xref:System.Windows.Automation.Condition> 문. 여기에는 일반적으로 언어 중립적인 <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> 가 사용됩니다. **참고:** 는 <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> 을 항목별로 정리할 수 Inspect.exe 같은 도구를 사용 하 여 가져올 수는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 컨트롤의 속성입니다. <br /><br /> -사용는 <xref:System.Windows.Automation.TreeWalker> 전체를 트래버스해야 하는 클래스 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리 또는 해당 하위 집합입니다.<br />포커스를 추적 합니다.<br />-컨트롤 hWnd를 사용 합니다.<br />-마우스 커서의 위치와 같은 화면 위치를 사용 합니다.<br /><br /> [Obtaining UI Automation Elements](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)을 참조하세요.|  
|컨트롤 패턴 가져오기|컨트롤 패턴은 기능이 비슷한 컨트롤에 대한 일반적인 동작을 노출합니다.<br /><br /> 테스트가 필요한 컨트롤을 찾은 후에, 자동화된 테스트 스크립트는 UI 자동화 요소에서 필요한 컨트롤 패턴을 가져옵니다. 예를 들면, 일반적인 단추 기능에 대한 <xref:System.Windows.Automation.InvokePattern> 컨트롤 패턴 또는 창 기능에 대한 <xref:System.Windows.Automation.WindowPattern> 컨트롤 패턴이 있습니다.<br /><br /> [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)을 참조하세요.|  
|UI 자동화|이제 자동화된 테스트 스크립트는 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 컨트롤 패턴이 노출하는 정보 및 기능을 사용하여 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 프레임워크에서 필요한 모든 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 를 제어할 수 있습니다.|  
  
<a name="Supporting_tools"></a>   
## <a name="related-tools-and-technologies"></a>관련 도구 및 기술  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]을 통해 자동화된 테스트를 지원하는 다양한 관련 도구 및 기술이 있습니다.  
  
-   Inspect.exe는는 [!INCLUDE[TLA#tla_gui](../../../includes/tlasharptla-gui-md.md)] 수집 하는 데 사용할 수 있는 응용 프로그램 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 공급자 및 클라이언트 개발 및 디버깅에 대 한 정보입니다. Inspect.exe에 포함 되어는 [!INCLUDE[TLA#tla_winfxsdk](../../../includes/tlasharptla-winfxsdk-md.md)]합니다.  
  
-   MSAABridge는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 정보를 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 클라이언트에 노출합니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 을 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 에 브리징하는 주요 목표는 기존 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] 클라이언트가 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]을 구현한 모든 프레임워크와 상호 작용하도록 하는 것입니다.  
  
<a name="Security"></a>   
## <a name="security"></a>보안  
 보안 정보는 [UI Automation Security Overview](../../../docs/framework/ui-automation/ui-automation-security-overview.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [UI 자동화 기본 사항](../../../docs/framework/ui-automation/index.md)
