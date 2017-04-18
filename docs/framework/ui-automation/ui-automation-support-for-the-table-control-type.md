---
title: "UI Automation Support for the Table Control Type | Microsoft Docs"
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
  - "TableControl type"
  - "control types, Table"
  - "UI Automation, Table control type"
ms.assetid: 9050dde5-6469-4c83-abb7-f861c24ff985
caps.latest.revision: 21
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 21
---
# UI Automation Support for the Table Control Type
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 이 항목에서는 Table 컨트롤 형식에 대한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 지원 정보를 제공합니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서, 컨트롤 형식은 <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> 속성을 사용하기 위해 컨트롤이 충족해야 하는 조건 집합입니다. 이 조건에는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리 구조, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성 값, 컨트롤 패턴에 대한 특정 지침이 포함됩니다.  
  
 테이블 컨트롤에 텍스트의 행과 열이 포함되고, 선택적으로 행 헤더와 열 헤더가 포함됩니다.  
  
 다음 섹션에서는 Table 컨트롤 형식에 필요한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리 구조, 속성, 컨트롤 패턴, 이벤트를 정의합니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 요구 사항은 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] 또는 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)]의 모든 테이블 컨트롤에 적용됩니다.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## 필요한 UI 자동화 트리 구조  
 다음 표는 테이블 컨트롤과 관련된 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리의 컨트롤 뷰 및 콘텐츠 뷰를 보여주고 각 뷰에 포함될 수 있는 내용에 대해 설명합니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리에 대한 자세한 내용은 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)를 참조하세요.  
  
|컨트롤 뷰|콘텐츠 뷰|  
|-----------|-----------|  
|표<br /><br /> -   Header\(0 또는 1개\)<br />-   Text\(0 또는 1개\)<br />-   다양한 컨트롤\(0개 이상\)|표<br /><br /> -   Text \(0개 이상\)<br />-   다양한 컨트롤\(0개 이상\)|  
  
 테이블 컨트롤에 행 또는 열 헤더가 있으면 UI 자동화 트리의 컨트롤 뷰에 이 헤더가 노출되어야 합니다. 콘텐츠 뷰의 경우, TablePattern을 사용하여 액세스할 수 있기 때문에 이 정보를 노출할 필요가 없습니다.  
  
<a name="Required_UI_Automation_Properties"></a>   
## 필요한 UI 자동화 속성  
 다음 표에서는 값 또는 정의가 테이블 컨트롤과 특별히 관련된 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성을 나열하여 보여줍니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성에 대한 자세한 내용은 [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)를 참조하세요.  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성|값|노트|  
|------------------------------------------------------------------------------|-------|--------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|메모를 참조하세요.|이 속성의 값은 응용 프로그램의 모든 컨트롤에서 고유해야 합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|메모를 참조하세요.|전체 컨트롤이 포함된 가장 바깥쪽 사각형입니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|메모를 참조하세요.|경계 사각형이 없는 경우 지원됩니다. 경계 사각형 내의 일부 지점이 클릭 가능하지 않으며 특수화된 적중 테스트를 수행하는 경우 클릭 가능한 지점을 재정의하고 제공하세요.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|메모를 참조하세요.|컨트롤이 키보드 포커스를 받을 수 있으면 해당 컨트롤은 이 속성을 지원해야 합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|메모를 참조하세요.|테이블 컨트롤은 일반적으로 정적 텍스트 레이블에서 이름을 가져옵니다. 정적 텍스트 레이블이 없는 경우, 테이블 용도를 설명하기 위해 항상 사용할 수 있어야 하는 Name 속성을 할당해야 합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|메모를 참조하세요.|정적 텍스트 레이블이 있는 경우, 이 속성은 컨트롤의 자동화 요소에 대한 참조를 노출해야 합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|표|이 값은 모든 UI 프레임워크에 대해 동일합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"table"|Table 컨트롤 형식에 해당하는 지역화된 문자열입니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|메모를 참조하세요.|테이블 용도에 대한 자세한 정보가 NameProperty 액세스로 충분히 설명되지 않을 경우에는 이 속성을 통해 노출되어야 합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.DescribedByProperty>|메모를 참조하세요.|다른 UI 요소\(예: 테이블에 대한 설명이 포함된 텍스트 요소\)로 테이블에 주석이 지정된 경우, DescribedBy 속성이 텍스트 컨트롤의 자동화 요소에 대한 참조를 노출해야 합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|테이블 컨트롤은 항상 콘텐츠여야 합니다.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|테이블 컨트롤은 항상 컨트롤이어야 합니다.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## 필요한 UI 자동화 컨트롤 패턴  
 다음 표에서는 테이블 컨트롤에서 지원되는 데 필요한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 컨트롤 패턴을 나열하여 보여줍니다. 컨트롤 패턴에 대한 자세한 내용은 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)를 참조하세요.  
  
|컨트롤 패턴|지원|노트|  
|------------|--------|--------|  
|<xref:System.Windows.Automation.Provider.IGridProvider>|예|테이블 컨트롤은 항상 이 컨트롤 패턴을 지원합니다. 이 컨트롤에 포함된 항목에 표에 제공되는 데이터가 있기 때문입니다.|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider>|예\(자식 개체에 필요\)|테이블의 내부 개체는 GridItem 및 TableItem 컨트롤 패턴을 지원해야 합니다. 테이블이 다른 테이블에 속하는 경우가 아니라면, 테이블 자체에서 GridItem 또는 TableItem 컨트롤 패턴을 지원할 필요가 없습니다.|  
|<xref:System.Windows.Automation.Provider.ITableProvider>|예|테이블 컨트롤에 콘텐츠와 연관된 헤더를 사용할 수 있는 기능이 항상 있습니다.|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider>|예\(자식 개체에 필요\)|테이블의 내부 개체는 GridItem 및 TableItem 컨트롤 패턴을 지원해야 합니다. 테이블이 다른 테이블에 속하는 경우가 아니라면, 테이블 자체에서 GridItem 또는 TableItem 컨트롤 패턴을 지원할 필요가 없습니다.|  
  
<a name="Required_UI_Automation_Events"></a>   
## 필요한 UI 자동화 이벤트  
 다음 표에서는 모든 테이블 컨트롤에서 지원되는 데 필요한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트를 나열하여 보여줍니다. 이벤트에 대한 자세한 내용은 [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md)를 참조하세요.  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 이벤트|지원|노트|  
|-------------------------------------------------------------------------------|--------|--------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> 속성 변경 이벤트.|필수|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> 속성 변경 이벤트.|필수|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> 속성 변경 이벤트.|필수|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|필수|없음|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|필수|없음|  
  
## 참고 항목  
 <xref:System.Windows.Automation.ControlType.Table>   
 [UI Automation Control Types Overview](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)   
 [UI Automation Overview](../../../docs/framework/ui-automation/ui-automation-overview.md)