---
title: "DataGrid 스타일 및 템플릿"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], DataGrid
- ControlTemplate [WPF], DataGrid
- DataGrid [WPF], styles and templates
- templates [WPF], DataGrid
- styles [WPF], DataGrid
- parts [WPF], DataGrid
ms.assetid: 9cb31d63-f148-4d25-b079-816e73f988c7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b2dd7e47454cdfa806ce025d905073468f70f7cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="datagrid-styles-and-templates"></a>DataGrid 스타일 및 템플릿
이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.DataGrid> 제어 합니다. 기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다. 자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.  
  
## <a name="datagrid-parts"></a>DataGrid 부분  
 다음 표에서 명명된 된 요소를 나열는 <xref:System.Windows.Controls.DataGrid> 제어 합니다.  
  
|파트|형식|설명|  
|-|-|-|  
|PART_ColumnHeadersPresenter|<xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>|열 머리글을 포함 하는 행입니다.|  
  
 만들 때 한 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.DataGrid>, 서식 파일에 포함 될 수 있습니다는 <xref:System.Windows.Controls.ItemsPresenter> 내는 <xref:System.Windows.Controls.ScrollViewer>합니다. (의 <xref:System.Windows.Controls.ItemsPresenter> 각 항목에 표시 됩니다는 <xref:System.Windows.Controls.DataGrid>; <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤할 수)입니다.  경우는 <xref:System.Windows.Controls.ItemsPresenter> 의 직계 자식이 없는 <xref:System.Windows.Controls.ScrollViewer>를 지정 해야 합니다는 <xref:System.Windows.Controls.ItemsPresenter> 이름, `ItemsPresenter`합니다.  
  
 에 대 한 기본 서식 파일의 <xref:System.Windows.Controls.DataGrid> 포함 한 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다. 정의 된 요소에 대 한 자세한 내용은 <xref:System.Windows.Controls.ScrollViewer>, 참조 [ScrollViewer 스타일 및 템플릿](../../../../docs/framework/wpf/controls/scrollviewer-styles-and-templates.md)합니다.  
  
## <a name="datagrid-states"></a>DataGrid 상태  
 다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.DataGrid> 제어 합니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|사용 안 함|CommonStates|컨트롤이 비활성화되었습니다.|  
|InvalidFocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 없습니다.|  
|유효|ValidationStates|컨트롤이 유효합니다.|  
  
## <a name="datagridcell-parts"></a>DataGridCell 부분  
 <xref:System.Windows.Controls.DataGridCell> 요소에는 명명된 된 요소가 있습니다.  
  
## <a name="datagridcell-states"></a>DataGridCell 상태  
 다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.DataGridCell> 요소입니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 셀 위에 배치 됩니다.|  
|포커스 있음|FocusStates|셀에 포커스가 있습니다.|  
|포커스 없음|FocusStates|셀에 포커스가 없으면|  
|현재|CurrentStates|셀이 현재 셀입니다.|  
|기본|CurrentStates|셀의 현재 셀이 있습니다.|  
|표시|InteractionStates|셀의 표시 모드입니다.|  
|편집|InteractionStates|셀이 편집 모드에 있습니다.|  
|선택함|SelectionStates|셀이 선택 됩니다.|  
|선택 취소|SelectionStates|셀을 선택 하지 않았습니다.|  
|InvalidFocused|ValidationStates|셀 잘못 되었으며에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|셀 잘못 되었으며 포커스가 없습니다.|  
|유효|ValidationStates|셀이 유효 합니다.|  
  
## <a name="datagridrow-parts"></a>DataGridRow 부분  
 <xref:System.Windows.Controls.DataGridRow> 요소에는 명명된 된 요소가 있습니다.  
  
## <a name="datagridrow-states"></a>DataGridRow 상태  
 다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.DataGridRow> 요소입니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 행 위에 배치 됩니다.|  
|MouseOver_Editing|CommonStates|마우스 포인터가 행 위에 및 행이 편집 모드에 있습니다.|  
|MouseOver_Selected|CommonStates|마우스 포인터가 행 위에 및 행을 선택 합니다.|  
|MouseOver_Unfocused_Editing|CommonStates|마우스 포인터가 행 위에 행이 편집 모드를 및 포커스가 없으면, 합니다.|  
|MouseOver_Unfocused_Selected|CommonStates|마우스 포인터가 행 위에, 행을 선택한 포커스가 없는 합니다.|  
|Normal_AlternatingRow|CommonStates|교대로 반복 되는 행이입니다.|  
|Normal_Editing|CommonStates|행이 편집 모드에 있습니다.|  
|Normal_Selected|CommonStates|행이 선택 되어 있습니다.|  
|Unfocused_Editing|CommonStates|행이 편집 모드에 있고 포커스가 없습니다.|  
|Unfocused_Selected|CommonStates|행을 선택 및 포커스가 없는 합니다.|  
|InvalidFocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 없습니다.|  
|유효|ValidationStates|컨트롤이 유효합니다.|  
  
## <a name="datagridrowheader-parts"></a>DataGridRowHeader 부분  
 다음 표에서 명명된 된 요소를 나열는 <xref:System.Windows.Controls.Primitives.DataGridRowHeader> 요소입니다.  
  
|파트|형식|설명|  
|-|-|-|  
|PART_TopHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|위쪽에서 행 머리글의 크기를 조정 하는 데 사용 되는 요소입니다.|  
|PART_BottomHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|맨 아래에서 행 머리글의 크기를 조정 하는 데 사용 되는 요소입니다.|  
  
## <a name="datagridrowheader-states"></a>DataGridRowHeader 상태  
 다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.Primitives.DataGridRowHeader> 요소입니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 행 위에 배치 됩니다.|  
|MouseOver_CurrentRow|CommonStates|마우스 포인터가 행 위에 및 현재 행입니다.|  
|MouseOver_CurrentRow_Selected|CommonStates|마우스 포인터가 행 위에 및 행이 현재 선택 되어 있습니다.|  
|MouseOver_EditingRow|CommonStates|마우스 포인터가 행 위에 및 행이 편집 모드에 있습니다.|  
|MouseOver_Selected|CommonStates|마우스 포인터가 행 위에 및 행을 선택 합니다.|  
|MouseOver_Unfocused_CurrentRow_Selected|CommonStates|마우스 포인터가 행 위에 행이 현재 선택 및 포커스가 없는 합니다.|  
|MouseOver_Unfocused_EditingRow|CommonStates|마우스 포인터가 행 위에 행이 편집 모드를 및 포커스가 없으면, 합니다.|  
|MouseOver_Unfocused_Selected|CommonStates|마우스 포인터가 행 위에, 행을 선택한 포커스가 없는 합니다.|  
|Normal_CurrentRow|CommonStates|현재 행이입니다.|  
|Normal_CurrentRow_Selected|CommonStates|행이 현재 행을 선택 됩니다.|  
|Normal_EditingRow|CommonStates|행이 편집 모드에 있습니다.|  
|Normal_Selected|CommonStates|행이 선택 되어 있습니다.|  
|Unfocused_CurrentRow_Selected|CommonStates|행이 현재 행을 선택 및 포커스가 없는 합니다.|  
|Unfocused_EditingRow|CommonStates|행이 편집 모드에 있고 포커스가 없습니다.|  
|Unfocused_Selected|CommonStates|행을 선택 및 포커스가 없는 합니다.|  
|InvalidFocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 없습니다.|  
|유효|ValidationStates|컨트롤이 유효합니다.|  
  
## <a name="datagridcolumnheaderspresenter-parts"></a>DataGridColumnHeadersPresenter 부분  
 다음 표에서 명명된 된 요소를 나열는 <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> 요소입니다.  
  
|파트|형식|설명|  
|-|-|-|  
|PART_FillerColumnHeader|<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>|열 머리글에 대 한 자리 표시자입니다.|  
  
## <a name="datagridcolumnheaderspresenter-states"></a>DataGridColumnHeadersPresenter 상태  
 다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> 요소입니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|InvalidFocused|ValidationStates|셀 잘못 되었으며에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|셀 잘못 되었으며 포커스가 없습니다.|  
|유효|ValidationStates|셀이 유효 합니다.|  
  
## <a name="datagridcolumnheader-parts"></a>DataGridColumnHeader 부분  
 다음 표에서 명명된 된 요소를 나열는 <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> 요소입니다.  
  
|파트|형식|설명|  
|-|-|-|  
|PART_LeftHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|열 머리글 왼쪽의 크기를 조정 하는 데 사용 되는 요소입니다.|  
|PART_RightHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|열 머리글 오른쪽의 크기를 조정 하는 데 사용 되는 요소입니다.|  
  
## <a name="datagridcolumnheader-states"></a>DataGridColumnHeader 상태  
 다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> 요소입니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 컨트롤 위에 있습니다.|  
|누름|CommonStates|컨트롤을 눌렀습니다.|  
|오름차순 정렬|SortStates|열이 오름차순으로 정렬 됩니다.|  
|내림차순 정렬|SortStates|열이 내림차순 정렬 됩니다.|  
|정렬 되지 않은|SortStates|열이 정렬 되지 않습니다.|  
|InvalidFocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 없습니다.|  
|유효|ValidationStates|컨트롤이 유효합니다.|  
  
## <a name="datagrid-controltemplate-example"></a>DataGrid ControlTemplate 예제  
 다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.DataGrid> 컨트롤과 연결 된 해당 형식입니다.  
  
 [!code-xaml[ControlTemplateExamples#DataGrid](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datagrid.xaml#datagrid)]  
  
 앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 전체 샘플을 보려면 [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Control 스타일 및 템플릿](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [컨트롤 사용자 지정](../../../../docs/framework/wpf/controls/control-customization.md)  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
