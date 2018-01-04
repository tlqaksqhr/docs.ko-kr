---
title: "TreeView 스타일 및 템플릿"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], TreeView
- templates [WPF], TreeView
- parts [WPF], TreeView
- states [WPF], TreeView
- styles [WPF], TreeView
- TreeView [WPF], styles and templates
ms.assetid: a49adb77-0202-4caa-b94a-8bb110d7fa9a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ea6e7d26ad70eef3aae4678b922ef01bccc9450b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="treeview-styles-and-templates"></a>TreeView 스타일 및 템플릿
이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.TreeView> 제어 합니다. 기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다. 자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.  
  
## <a name="treeview-parts"></a>TreeView 부분  
 <xref:System.Windows.Controls.TreeView> 컨트롤에는 명명된 된 요소가 있습니다.  
  
 만들 때 한 <xref:System.Windows.Controls.ControlTemplate> 에 대 한 프로그램 <xref:System.Windows.Controls.TreeView>, 서식 파일에 포함 될 수 있습니다는 <xref:System.Windows.Controls.ItemsPresenter> 내는 <xref:System.Windows.Controls.ScrollViewer>합니다. (의 <xref:System.Windows.Controls.ItemsPresenter> 각 항목에 표시 됩니다는 <xref:System.Windows.Controls.TreeView>; <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤할 수)입니다.  경우는 <xref:System.Windows.Controls.ItemsPresenter> 의 직계 자식이 없는 <xref:System.Windows.Controls.ScrollViewer>를 지정 해야 합니다는 <xref:System.Windows.Controls.ItemsPresenter> 이름, `ItemsPresenter`합니다.  
  
## <a name="treeview-states"></a>TreeView 상태  
 다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.TreeView> 제어 합니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|유효|ValidationStates|컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.|  
  
## <a name="treeviewitem-parts"></a>TreeViewItem 부분  
 다음 표에서 명명된 된 요소를 나열는 <xref:System.Windows.Controls.TreeViewItem> 제어 합니다.  
  
|파트|형식|설명|  
|----------|----------|-----------------|  
|PART_Header|<xref:System.Windows.FrameworkElement>|헤더의 내용이 포함 된 시각적 요소는 <xref:System.Windows.Controls.TreeView> 제어 합니다.|  
  
## <a name="treeviewitem-states"></a>TreeViewItem 상태  
 다음 표에서 시각적 상태를 <xref:System.Windows.Controls.TreeViewItem> 제어 합니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|----------------------|---------------------------|-----------------|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 위에 <xref:System.Windows.Controls.TreeViewItem>합니다.|  
|사용 안 함|CommonStates|<xref:System.Windows.Controls.TreeViewItem> 을 사용할 수 없습니다.|  
|포커스 있음|FocusStates|<xref:System.Windows.Controls.TreeViewItem> 에 포커스가 있습니다.|  
|포커스 없음|FocusStates|<xref:System.Windows.Controls.TreeViewItem> 포커스가 없는 합니다.|  
|확장됨|ExpansionStates|<xref:System.Windows.Controls.TreeViewItem> 컨트롤을 확장 합니다.|  
|축소됨|ExpansionStates|<xref:System.Windows.Controls.TreeViewItem> 컨트롤이 축소 됩니다.|  
|HasItems|HasItemsStates|<xref:System.Windows.Controls.TreeViewItem> 항목이 있습니다.|  
|NoItems|HasItemsStates|<xref:System.Windows.Controls.TreeViewItem> 항목에 포함 되지 않습니다.|  
|선택함|SelectionStates|<xref:System.Windows.Controls.TreeViewItem> 을 선택 합니다.|  
|SelectedInactive|SelectionStates|<xref:System.Windows.Controls.TreeViewItem> 은 선택 되어 있지만 활성 상태가 아닙니다.|  
|선택 취소|SelectionStates|<xref:System.Windows.Controls.TreeViewItem> 선택 하지 않으면 합니다.|  
|유효|ValidationStates|컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.|  
  
## <a name="treeview-controltemplate-example"></a>TreeView ControlTemplate 예제  
 다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.TreeView> 컨트롤과 연결 된 해당 형식입니다.  
  
 [!code-xaml[ControlTemplateExamples#TreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
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
