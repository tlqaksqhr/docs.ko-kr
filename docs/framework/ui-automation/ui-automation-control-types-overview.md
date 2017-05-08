---
title: "UI Automation Control Types Overview | Microsoft Docs"
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
  - "UI Automation, control types"
  - "control types, UI Automation"
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
caps.latest.revision: 22
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 22
---
# UI Automation Control Types Overview
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 컨트롤 형식은 콤보 상자나 단추와 같은 특정 요소가 구현하는 컨트롤의 종류를 나타내기 위해 사용할 수 있는 알려진 식별자입니다.  
  
 알려진 식별자를 사용하면 보조 기술 장치가 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)]에서 사용 가능한 컨트롤의 형식 및 이 컨트롤을 조작하는 방식을 더 쉽게 확인할 수 있습니다.  
  
<a name="UI_Automation_Control_Type_Requisites"></a>   
## UI 자동화 컨트롤 형식 필수 요소  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 컨트롤 형식은 공급자가 충족해야 하는 일련의 조건을 제공합니다. 이러한 조건이 충족되는 경우 컨트롤은 특정 컨트롤 형식 이름을 사용할 수 있습니다. 각 컨트롤 형식에는 다음에 대한 조건이 있습니다.  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 컨트롤 패턴 \- 지원해야 하는 컨트롤 패턴, 선택 사항인 컨트롤 패턴, 컨트롤에서 지원해서는 안 되는 컨트롤 패턴  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 속성 값 \- 지원되는 속성 값  
  
-   [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리 구조 \- 컨트롤에 필요한 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 트리 구조  
  
 컨트롤이 특정 컨트롤 형식에 대한 조건을 충족한다면 <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> 속성 값이 해당 컨트롤 형식을 나타내는 것입니다.  
  
<a name="Current_UI_Automation_Control_Types"></a>   
## 현재 UI 자동화 컨트롤 형식  
 다음 목록에는 현재 제공되는 일련의 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 컨트롤 형식이 나옵니다.  
  
-   [UI Automation Support for the Button Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-button-control-type.md)  
  
-   [UI Automation Support for the Calendar Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-calendar-control-type.md)  
  
-   [UI Automation Support for the CheckBox Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-checkbox-control-type.md)  
  
-   [UI Automation Support for the ComboBox Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-combobox-control-type.md)  
  
-   [UI Automation Support for the DataGrid Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-datagrid-control-type.md)  
  
-   [UI Automation Support for the DataItem Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-dataitem-control-type.md)  
  
-   [UI Automation Support for the Document Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-document-control-type.md)  
  
-   [UI Automation Support for the Edit Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-edit-control-type.md)  
  
-   [UI Automation Support for the Group Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-group-control-type.md)  
  
-   [UI Automation Support for the Header Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-header-control-type.md)  
  
-   [UI Automation Support for the HeaderItem Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-headeritem-control-type.md)  
  
-   [UI Automation Support for the Hyperlink Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-hyperlink-control-type.md)  
  
-   [UI Automation Support for the Image Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-image-control-type.md)  
  
-   [UI Automation Support for the List Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-list-control-type.md)  
  
-   [UI Automation Support for the ListItem Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-listitem-control-type.md)  
  
-   [UI Automation Support for the Menu Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-menu-control-type.md)  
  
-   [UI Automation Support for the MenuBar Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)  
  
-   [UI Automation Support for the MenuItem Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-menuitem-control-type.md)  
  
-   [UI Automation Support for the Pane Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-pane-control-type.md)  
  
-   [UI Automation Support for the ProgressBar Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-progressbar-control-type.md)  
  
-   [UI Automation Support for the RadioButton Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-radiobutton-control-type.md)  
  
-   [UI Automation Support for the ScrollBar Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-scrollbar-control-type.md)  
  
-   [UI Automation Support for the Separator Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-separator-control-type.md)  
  
-   [UI Automation Support for the Slider Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-slider-control-type.md)  
  
-   [UI Automation Support for the Spinner Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md)  
  
-   [UI Automation Support for the SplitButton Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-splitbutton-control-type.md)  
  
-   [UI Automation Support for the StatusBar Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-statusbar-control-type.md)  
  
-   [UI Automation Support for the Tab Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-tab-control-type.md)  
  
-   [UI Automation Support for the TabItem Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-tabitem-control-type.md)  
  
-   [UI Automation Support for the Table Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-table-control-type.md)  
  
-   [UI Automation Support for the Text Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-text-control-type.md)  
  
-   [UI Automation Support for the Thumb Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-thumb-control-type.md)  
  
-   [UI Automation Support for the TitleBar Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-titlebar-control-type.md)  
  
-   [UI Automation Support for the ToolBar Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-toolbar-control-type.md)  
  
-   [UI Automation Support for the ToolTip Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-tooltip-control-type.md)  
  
-   [UI Automation Support for the Tree Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-tree-control-type.md)  
  
-   [UI Automation Support for the TreeItem Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-treeitem-control-type.md)  
  
-   [UI Automation Support for the Window Control Type](../../../docs/framework/ui-automation/ui-automation-support-for-the-window-control-type.md)  
  
## 참고 항목  
 <xref:System.Windows.Automation.ControlType>