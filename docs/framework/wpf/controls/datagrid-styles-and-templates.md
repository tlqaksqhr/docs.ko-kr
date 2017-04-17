---
title: "DataGrid 스타일 및 템플릿 | Microsoft Docs"
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
  - "ControlTemplate[WPF], DataGrid"
  - "DataGrid[WPF], 스타일 및 템플릿"
  - "요소[WPF], DataGrid"
  - "상태[WPF], DataGrid"
  - "스타일[WPF], DataGrid"
  - "템플릿[WPF], DataGrid"
ms.assetid: 9cb31d63-f148-4d25-b079-816e73f988c7
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# DataGrid 스타일 및 템플릿
이 항목에서는 <xref:System.Windows.Controls.DataGrid> 컨트롤의 스타일 및 템플릿에 대해 설명합니다.  기본 <xref:System.Windows.Controls.ControlTemplate>을 수정하여 컨트롤에 고유한 모양을 지정할 수 있습니다.  자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하십시오.  
  
## DataGrid 요소  
 다음 표에서는 <xref:System.Windows.Controls.DataGrid> 컨트롤의 명명된 요소를 보여 줍니다.  
  
||||  
|-|-|-|  
|파트|형식|설명|  
|PART\_ColumnHeadersPresenter|<xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>|열 머리글을 포함하는 행입니다.|  
  
 <xref:System.Windows.Controls.DataGrid>에 대한 <xref:System.Windows.Controls.ControlTemplate>을 만들 경우 템플릿의 <xref:System.Windows.Controls.ScrollViewer> 내에 <xref:System.Windows.Controls.ItemsPresenter>가 포함될 수 있습니다.  <xref:System.Windows.Controls.ItemsPresenter>는 각 항목을 <xref:System.Windows.Controls.DataGrid>에 표시하고 <xref:System.Windows.Controls.ScrollViewer>는 컨트롤 내에서 스크롤할 수 있도록 합니다.  <xref:System.Windows.Controls.ItemsPresenter>가 <xref:System.Windows.Controls.ScrollViewer>의 직계 자식이 아니면 <xref:System.Windows.Controls.ItemsPresenter>에 `ItemsPresenter`라는 이름을 지정해야 합니다.  
  
 <xref:System.Windows.Controls.DataGrid>의 기본 템플릿에는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤이 포함되어 있습니다.  <xref:System.Windows.Controls.ScrollViewer>에서 정의된 요소에 대한 자세한 내용은 [ScrollViewer 스타일 및 템플릿](../../../../docs/framework/wpf/controls/scrollviewer-styles-and-templates.md)을 참조하십시오.  
  
## DataGrid 상태  
 다음 표에서는 <xref:System.Windows.Controls.DataGrid> 컨트롤의 시각적 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|보통|CommonStates|기본 상태입니다.|  
|Disabled|CommonStates|컨트롤이 사용하지 않도록 설정되어 있습니다.|  
|InvalidFocused|ValidationStates|컨트롤이 잘못되었지만 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|컨트롤이 잘못되었으며 포커스가 없습니다.|  
|Valid|ValidationStates|컨트롤이 유효합니다.|  
  
## DataGridCell 요소  
 <xref:System.Windows.Controls.DataGridCell> 요소에는 명명된 요소가 없습니다.  
  
## DataGridCell 상태  
 다음 표에서는 <xref:System.Windows.Controls.DataGridCell> 요소의 시각적 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 셀 위에 있습니다.|  
|Focused|FocusStates|포커스가 있는 셀입니다.|  
|Unfocused|FocusStates|포커스가 없는 셀입니다.|  
|Current|CurrentStates|셀이 현재 셀입니다.|  
|기본|CurrentStates|셀이 현재 셀이 아닙니다.|  
|표시|InteractionStates|셀이 디스플레이 모드에 있습니다.|  
|편집|InteractionStates|셀이 편집 모드에 있습니다.|  
|선택함|SelectionStates|셀이 선택되어 있습니다.|  
|선택하지 않음|SelectionStates|셀이 선택되어 있지 않습니다.|  
|InvalidFocused|ValidationStates|셀이 잘못되었지만 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|셀이 잘못되었으며 포커스가 없습니다.|  
|Valid|ValidationStates|셀이 유효합니다.|  
  
## DataGridRow 요소  
 <xref:System.Windows.Controls.DataGridRow> 요소에는 명명된 요소가 없습니다.  
  
## DataGridRow 상태  
 다음 표에서는 <xref:System.Windows.Controls.DataGridRow> 요소의 시각적 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 행 위에 있습니다.|  
|MouseOver\_Editing|CommonStates|마우스 포인터가 행 위에 있으며 행이 편집 모드에 있습니다.|  
|MouseOver\_Selected|CommonStates|마우스 포인터가 행 위에 있으며 행이 선택되어 있습니다.|  
|MouseOver\_Unfocused\_Editing|CommonStates|마우스 포인터가 행 위에 있으며 행이 편집 모드에 있고 포커스가 없습니다.|  
|MouseOver\_Unfocused\_Selected|CommonStates|마우스 포인터가 행 위에 있으며 행이 선택되어 있고 포커스가 없습니다.|  
|Normal\_AlternatingRow|CommonStates|행이 교대로 반복되는 행입니다.|  
|Normal\_Editing|CommonStates|행이 편집 모드에 있습니다.|  
|Normal\_Selected|CommonStates|행이 선택되어 있습니다.|  
|Unfocused\_Editing|CommonStates|행이 편집 모드에 있고 포커스가 없습니다.|  
|Unfocused\_Selected|CommonStates|행이 선택되어 있고 포커스가 없습니다.|  
|InvalidFocused|ValidationStates|컨트롤이 잘못되었지만 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|컨트롤이 잘못되었으며 포커스가 없습니다.|  
|Valid|ValidationStates|컨트롤이 유효합니다.|  
  
## DataGridRowHeader 요소  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DataGridRowHeader> 요소의 명명된 요소를 보여 줍니다.  
  
||||  
|-|-|-|  
|파트|형식|설명|  
|PART\_TopHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|맨 위에서 행 머리글의 크기를 변경하는 데 사용되는 요소입니다.|  
|PART\_BottomHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|맨 아래에서 행 머리글의 크기를 변경하는 데 사용되는 요소입니다.|  
  
## DataGridRowHeader 상태  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DataGridRowHeader> 요소의 시각적 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 행 위에 있습니다.|  
|MouseOver\_CurrentRow|CommonStates|마우스 포인터가 행 위에 있으며 행이 현재 행입니다.|  
|MouseOver\_CurrentRow\_Selected|CommonStates|마우스 포인터가 행 위에 있으며 행이 현재 선택되어 있습니다.|  
|MouseOver\_EditingRow|CommonStates|마우스 포인터가 행 위에 있으며 행이 편집 모드에 있습니다.|  
|MouseOver\_Selected|CommonStates|마우스 포인터가 행 위에 있으며 행이 선택되어 있습니다.|  
|MouseOver\_Unfocused\_CurrentRow\_Selected|CommonStates|마우스 포인터가 행 위에 있으며 행이 현재 선택되어 있고 포커스가 없습니다.|  
|MouseOver\_Unfocused\_EditingRow|CommonStates|마우스 포인터가 행 위에 있으며 행이 편집 모드에 있고 포커스가 없습니다.|  
|MouseOver\_Unfocused\_Selected|CommonStates|마우스 포인터가 행 위에 있으며 행이 선택되어 있고 포커스가 없습니다.|  
|Normal\_CurrentRow|CommonStates|행이 현재 행입니다.|  
|Normal\_CurrentRow\_Selected|CommonStates|행이 현재 행이며 선택되어 있습니다.|  
|Normal\_EditingRow|CommonStates|행이 편집 모드에 있습니다.|  
|Normal\_Selected|CommonStates|행이 선택되어 있습니다.|  
|Unfocused\_CurrentRow\_Selected|CommonStates|행이 현재 행이며 선택되어 있고 포커스가 없습니다.|  
|Unfocused\_EditingRow|CommonStates|행이 편집 모드에 있고 포커스가 없습니다.|  
|Unfocused\_Selected|CommonStates|행이 선택되어 있고 포커스가 없습니다.|  
|InvalidFocused|ValidationStates|컨트롤이 잘못되었지만 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|컨트롤이 잘못되었으며 포커스가 없습니다.|  
|Valid|ValidationStates|컨트롤이 유효합니다.|  
  
## DataGridColumnHeadersPresenter 요소  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> 요소의 명명된 요소를 보여 줍니다.  
  
||||  
|-|-|-|  
|파트|형식|설명|  
|PART\_FillerColumnHeader|<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>|열 머리글의 자리 표시자입니다.|  
  
## DataGridColumnHeadersPresenter 상태  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> 요소의 시각적 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|InvalidFocused|ValidationStates|셀이 잘못되었지만 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|셀이 잘못되었으며 포커스가 없습니다.|  
|Valid|ValidationStates|셀이 유효합니다.|  
  
## DataGridColumnHeader 요소  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> 요소의 명명된 요소를 보여 줍니다.  
  
||||  
|-|-|-|  
|파트|형식|설명|  
|PART\_LeftHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|왼쪽에 있는 열 머리글의 크기를 변경하는 데 사용되는 요소입니다.|  
|PART\_RightHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|오른쪽에 있는 열 머리글의 크기를 변경하는 데 사용되는 요소입니다.|  
  
## DataGridColumnHeader 상태  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> 요소의 시각적 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 컨트롤 위에 있습니다.|  
|Pressed|CommonStates|컨트롤을 눌렀습니다.|  
|SortAscending|SortStates|이 열은 오름차순으로 정렬됩니다.|  
|SortDescending|SortStates|이 열은 내림차순으로 정렬됩니다.|  
|Unsorted|SortStates|열이 정렬되어 있지 않습니다.|  
|InvalidFocused|ValidationStates|컨트롤이 잘못되었지만 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|컨트롤이 잘못되었으며 포커스가 없습니다.|  
|Valid|ValidationStates|컨트롤이 유효합니다.|  
  
## DataGrid ControlTemplate 예제  
 다음 예제에서는 <xref:System.Windows.Controls.DataGrid> 컨트롤과 해당 연결 형식의 <xref:System.Windows.Controls.ControlTemplate>을 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[ControlTemplateExamples#DataGrid](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datagrid.xaml#datagrid)]  
  
 앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.  
  
 [!code-xml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 전체 샘플을 보려면          [Styling with ControlTemplates 샘플](http://go.microsoft.com/fwlink/?LinkID=160041)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.FrameworkElement.Style%2A>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Control 스타일 및 템플릿](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)   
 [컨트롤 사용자 지정](../../../../docs/framework/wpf/controls/control-customization.md)   
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)