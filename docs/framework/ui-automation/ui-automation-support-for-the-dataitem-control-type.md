---
title: "DataItem 컨트롤 형식에 대한 UI 자동화 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, Data Item control type
- Data Item control type
- control types, Data Item
ms.assetid: 181708fd-2595-4c43-9abd-75811627d64c
caps.latest.revision: "36"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: be826cce87d428a156bb7a10d858e5848b2f1143
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ui-automation-support-for-the-dataitem-control-type"></a>DataItem 컨트롤 형식에 대한 UI 자동화 지원
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 이 항목에서는 DataItem 컨트롤 형식에 대한 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 지원 정보를 제공합니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 에서, 컨트롤 형식은 <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> 속성을 사용하기 위해 컨트롤이 충족해야 하는 조건 집합입니다. 이 조건에는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리 구조, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성 값, 컨트롤 패턴에 대한 특정 지침이 포함됩니다.  
  
 연락처 목록에 있는 항목은 데이터 항목 컨트롤의 예입니다. 데이터 항목 컨트롤에는 최종 사용자에게 유용한 정보가 들어있습니다. 이 항목에는 보다 다양한 정보가 들어 있기 때문에 단순 목록 항목보다 복잡합니다.  
  
 다음 섹션에서는 DataItem 컨트롤 형식에 필요한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리 구조, 속성, 컨트롤 패턴, 이벤트를 정의합니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 요구 사항은 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]또는 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)]의 모든 데이터 항목 컨트롤에 적용됩니다.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>필요한 UI 자동화 트리 구조  
 다음 표는 데이터 항목 컨트롤과 관련된 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리의 컨트롤 뷰 및 콘텐츠 뷰를 보여주고 각 뷰에 포함될 수 있는 내용에 대해 설명합니다. 에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리, 참조 [UI 자동화 트리 개요](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)합니다.  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리 - 컨트롤 뷰|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리-콘텐츠 뷰|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|DataItem<br /><br /> -다릅니다 (0 개 이상, 계층 구조로 구조화할 수 있음)|DataItem<br /><br /> -다릅니다 (0 개 이상, 계층 구조로 구조화할 수 있음)|  
  
 데이터 표의 데이터 항목 요소는 데이터 항목의 다른 레이어 또는 특정 표 요소(예: 텍스트, 이미지 또는 편집 컨트롤)를 비롯한 다양한 개체를 호스트할 수 있습니다. 데이터 항목 요소에 특정 개체 역할이 있으면, 이 요소는 특정 컨트롤 형식으로 노출되어야 합니다. 예를 들어, 표에 있는 선택 가능한 데이터 항목의 경우 ListItem 컨트롤 형식으로 노출되어야 합니다.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>필요한 UI 자동화 속성  
 다음 표에서는 값 또는 정의가 데이터 항목 컨트롤과 특별히 관련된 속성을 나열하여 보여 줍니다. 에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성 참조 [클라이언트에 대 한 UI 자동화 속성](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)합니다.  
  
|속성|값|노트|  
|--------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|메모를 참조하세요.|이 속성의 값은 응용 프로그램의 모든 컨트롤에서 고유해야 합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|메모를 참조하세요.|전체 컨트롤이 포함된 가장 바깥쪽 사각형입니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|메모를 참조하세요.|경계 사각형이 없는 경우 지원됩니다. 경계 사각형 내의 일부 지점이 클릭 가능하지 않으며 특수화된 적중 테스트를 수행하는 경우 클릭 가능한 지점을 재정의하고 제공하세요.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|DataItem|이 값은 모든 UI 프레임워크에 대해 동일합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|데이터 항목 컨트롤이 항상 콘텐츠여야 합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|데이터 항목 컨트롤이 항상 컨트롤이어야 합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|메모를 참조하세요.|컨트롤이 키보드 포커스를 받을 수 있으면 해당 컨트롤은 이 속성을 지원해야 합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemStatusProperty>|메모를 참조하세요.|컨트롤에 동적으로 업데이트되는 상태가 포함되어 있으면, 이 속성을 지원해야 요소의 상태가 변경될 때 보조 기술이 업데이트를 수신할 수 있습니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemTypeProperty>|메모를 참조하세요.|항목이 나타내는 내부 개체를 최종 사용자에게 전달하는 문자열 값입니다. 이 문자열의 예로는  "Media File" 또는 "Contact"가 있습니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|데이터 항목 컨트롤에는 정적 텍스트 레이블이 없습니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"data item"|DataItem 컨트롤 형식에 해당하는 지역화된 문자열입니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|메모를 참조하세요.|데이터 항목 컨트롤에는 사용자가 항목에 대해 가장 의미 있는 식별자로 연결할 사항과 관련된 기본 텍스트 요소가 항상 포함됩니다.|  
  
<a name="_Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>필요한 UI 자동화 컨트롤 패턴  
 다음 표에서는 모든 데이터 항목 컨트롤에서 지원되는 데 필요한 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 컨트롤 패턴을 나열하여 보여 줍니다. 컨트롤 패턴에 대한 자세한 내용은 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)를 참조하세요.  
  
|컨트롤 패턴|지원|노트|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|종속|데이터 항목을 확장하거나 축소하여 정보를 표시하고 숨길 수 있는 경우 Expand Collapse 패턴이 지원되어야 합니다.|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider>|종속|항목 간 공간을 탐색할 수 있는 컨테이너 내에서 데이터 항목의 컬렉션을 사용할 수 있으면 데이터 항목이 Grid Item 패턴을 지원합니다.|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider>|종속|모든 데이터 항목은 화면에 맞출 수 있는 것보다 많은 항목이 데이터 컨테이너에 들어 있을 때 Scroll Item 패턴을 통해 스크롤하여 볼 수 있는 기능을 지원합니다.|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|예|항목이 선택될 때 이를 나타내려면 모든 데이터 항목이 Selection Item 패턴을 지원해야 합니다.|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider>|종속|데이터 항목이 Data Grid 컨트롤 형식 내에 포함되어 있으면 이 패턴을 지원합니다.|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|종속|데이터 항목에 순환될 수 있는 상태가 포함된 경우.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|종속|데이터 항목의 기본 텍스트를 편집할 수 있는 경우 Value 패턴이 지원되어야 합니다.|  
  
<a name="Working_with_Data_Items_in_Large_Lists"></a>   
## <a name="working-with-data-items-in-large-lists"></a>긴 목록에서 데이터 항목 작업  
 대부분 긴 목록은 성능 향상에 도움을 주기 위해 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 프레임워크 내에서 가상화된 데이터입니다. 이런 이유로, UI 자동화 클라이언트는 컨테이너의 다른 항목에서와 같은 방법으로 전체 트리의 내용을 수집하기 위해 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 쿼리 기능을 사용할 수 없습니다. 클라이언트는 데이터 항목에서 전체 정보 집합에 액세스하기 전에 항목을 스크롤하여 볼 수 있도록 해야 합니다(또는 컨트롤을 확장하여 모든 중요 옵션 표시).  
  
 데이터 항목에 대해 `SetFocus` 요소의 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 를 호출하면 [!INCLUDE[TLA#tla_winexpl](../../../includes/tlasharptla-winexpl-md.md)] 케이스가 성공적으로 반환되고 데이터 항목 하위 트리 내에서 포커스가 편집으로 설정됩니다.  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>필요한 UI 자동화 이벤트  
 다음 표에서는 모든 데이터 항목 컨트롤에서 지원되는 데 필요한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트를 나열하여 보여 줍니다. 이벤트에 대한 자세한 내용은 [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md)를 참조하세요.  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트|지원|노트|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|필수|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> 속성 변경 이벤트.|필수|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> 속성 변경 이벤트.|필수|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> 속성 변경 이벤트.|필수|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> 속성 변경 이벤트.|필수|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|필수|없음|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|종속|없음|  
|<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> 속성 변경 이벤트.|종속|없음|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|필수|없음|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|필수|없음|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|필수|없음|  
|<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> 속성 변경 이벤트.|종속|없음|  
|<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> 속성 변경 이벤트.|종속|없음|  
  
<a name="Data_Item_Control_Type_Example"></a>   
## <a name="dataitem-control-type-example"></a>DataItem 컨트롤 형식 예제  
 다음 이미지는 열에 대한 다양한 정보를 지원하는 목록 뷰 컨트롤의 DataItem 컨트롤 형식을 보여 줍니다.  
  
 ![두 데이터 항목이 있는 목록 뷰 컨트롤의 그래픽](../../../docs/framework/ui-automation/media/uiauto-data-grid-detailed.GIF "uiauto_data_grid_detailed")  
  
 다음은 데이터 항목 컨트롤과 관련된 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리의 컨트롤 뷰 및 콘텐츠 보기입니다. 각 자동화 요소에 대한 컨트롤 패턴은 괄호 안에 표시됩니다. Group "Contoso"는 Data Grid 호스트 컨트롤 표의 일부이기도 합니다.  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리 - 컨트롤 뷰|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리-콘텐츠 뷰|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|-그룹 "Contoso" (Table, 그리드)<br />-DataItem "계정 Receivable.doc" (TableItem, GridItem, SelectionItem, 호출)<br />-이미지 "Accounts Receivable.doc"<br />--"Name" ("Accounts Receivable.doc" TableItem, GridItem, 값)을 편집 하는 중<br />-"수정한 날짜" 편집 (TableItem, GridItem, 값 "8/25/2006 오후 3시 29분")<br />--"크기" (GridItem, TableItem, 값 "11.0 KB)를 편집 하는 중<br />-DataItem "계정 Payable.doc" (TableItem, GridItem, SelectionItem, 호출)<br />-   ...|-그룹 "Contoso" (Table, 그리드)<br />-DataItem "계정 Receivable.doc" (TableItem, GridItem, SelectionItem, 호출)<br />-이미지 "Accounts Receivable.doc"<br />--"Name" ("Accounts Receivable.doc" TableItem, GridItem, 값)을 편집 하는 중<br />-"수정한 날짜" 편집 (TableItem, GridItem, 값 "8/25/2006 오후 3시 29분")<br />--"크기" (GridItem, TableItem, 값 "11.0 KB)를 편집 하는 중<br />-DataItem "계정 Payable.doc" (TableItem, GridItem, SelectionItem, 호출)<br />-   …|  
  
 표가 선택 가능한 항목의 목록을 나타내는 경우, 해당 UI 요소는 DataItem 컨트롤 형식이 아닌 ListItem 컨트롤 형식을 사용하여 노출할 수 있습니다. 앞의 예에서, Group("Contoso") 아래의 DataItem 요소("Accounts Receivable.doc" 및 "Accounts Payable.doc")는 SelectionItem 컨트롤 패턴을 이미 지원하기 때문에 ListItem 컨트롤 형식으로 노출하여 개선할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Automation.ControlType.DataItem>  
 [UI 자동화 컨트롤 형식 개요](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [UI 자동화 개요](../../../docs/framework/ui-automation/ui-automation-overview.md)
