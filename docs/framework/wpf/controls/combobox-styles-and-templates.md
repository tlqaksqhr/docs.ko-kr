---
title: "ComboBox 스타일 및 템플릿 | Microsoft Docs"
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
  - "ComboBox[WPF], 스타일 및 템플릿"
  - "ControlTemplate[WPF], ComboBox"
  - "요소[WPF], ComboBox"
  - "상태[WPF], ComboBox"
  - "스타일[WPF], ComboBox"
  - "템플릿[WPF], ComboBox"
ms.assetid: b0662fa1-16d7-4320-b26b-c1804e565a44
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# ComboBox 스타일 및 템플릿
이 항목에서는 <xref:System.Windows.Controls.ComboBox> 컨트롤의 스타일 및 템플릿에 대해 설명합니다.  기본 <xref:System.Windows.Controls.ControlTemplate>을 수정하여 컨트롤에 고유한 모양을 지정할 수 있습니다.  자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하십시오.  
  
## ComboBox 요소  
 다음 표에서는 <xref:System.Windows.Controls.ComboBox> 컨트롤의 명명된 요소를 보여 줍니다.  
  
||||  
|-|-|-|  
|파트|형식|설명|  
|PART\_EditableTextBox|<xref:System.Windows.Controls.TextBox>|<xref:System.Windows.Controls.ComboBox>의 텍스트를 포함합니다.|  
|PART\_Popup|<xref:System.Windows.Controls.Primitives.Popup>|콤보 상자의 항목이 포함된 드롭다운입니다.|  
  
 <xref:System.Windows.Controls.ComboBox>에 대한 <xref:System.Windows.Controls.ControlTemplate>을 만들 경우 템플릿의 <xref:System.Windows.Controls.ScrollViewer> 내에 <xref:System.Windows.Controls.ItemsPresenter>가 포함될 수 있습니다.  <xref:System.Windows.Controls.ItemsPresenter>는 각 항목을 <xref:System.Windows.Controls.ComboBox>에 표시하고 <xref:System.Windows.Controls.ScrollViewer>는 컨트롤 내에서 스크롤할 수 있도록 합니다.  <xref:System.Windows.Controls.ItemsPresenter>가 <xref:System.Windows.Controls.ScrollViewer>의 직계 자식이 아니면 <xref:System.Windows.Controls.ItemsPresenter>에 `ItemsPresenter`라는 이름을 지정해야 합니다.  
  
## ComboBox 상태  
 다음 표에서는 <xref:System.Windows.Controls.ComboBox> 컨트롤의 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|보통|CommonStates|기본 상태입니다.|  
|Disabled|CommonStates|컨트롤이 사용하지 않도록 설정되어 있습니다.|  
|MouseOver|CommonStates|마우스 포인터가 <xref:System.Windows.Controls.ComboBox> 컨트롤 위에 있습니다.|  
|Focused|FocusStates|컨트롤에 포커스가 있습니다.|  
|Unfocused|FocusStates|컨트롤에 포커스가 없습니다.|  
|FocusedDropDown|FocusStates|<xref:System.Windows.Controls.ComboBox>의 드롭다운에 포커스가 있습니다.|  
|Valid|ValidationStates|이 컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용하며 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `false`입니다.|  
|InvalidFocused|ValidationStates|컨트롤에 포커스가 있는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
|InvalidUnfocused|ValidationStates|컨트롤에 포커스가 없는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
|Editable|EditStates|<xref:System.Windows.Controls.ComboBox.IsEditable%2A> 속성이 `true`일 경우\(이 속성은|  
|Uneditable|EditStates|<xref:System.Windows.Controls.ComboBox.IsEditable%2A> 속성이 `false`일 경우\(이 속성은|  
  
## ComboBoxItem 요소  
 <xref:System.Windows.Controls.ComboBoxItem> 컨트롤에는 명명된 요소가 없습니다.  
  
## ComboBoxItem 상태  
 다음 표에서는 <xref:System.Windows.Controls.ComboBoxItem> 컨트롤의 상태를 나열합니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|보통|CommonStates|기본 상태입니다.|  
|Disabled|CommonStates|컨트롤이 사용하지 않도록 설정되어 있습니다.|  
|MouseOver|CommonStates|마우스 포인터가 <xref:System.Windows.Controls.ComboBox> 컨트롤 위에 있습니다.|  
|Focused|FocusStates|컨트롤에 포커스가 있습니다.|  
|Unfocused|FocusStates|컨트롤에 포커스가 없습니다.|  
|선택함|SelectionStates|항목이 현재 선택되어 있습니다.|  
|선택하지 않음|SelectionStates|항목이 선택되어 있지 않습니다.|  
|SelectedUnfocused|SelectionStates|항목이 선택되었지만 포커스가 없습니다.|  
|Valid|ValidationStates|이 컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용하며 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `false`입니다.|  
|InvalidFocused|ValidationStates|컨트롤에 포커스가 있는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
|InvalidUnfocused|ValidationStates|컨트롤에 포커스가 없는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
  
## ComboBox ControlTemplate 예제  
 다음 예제에서는 <xref:System.Windows.Controls.ComboBox> 컨트롤과 해당 연결 형식의 <xref:System.Windows.Controls.ControlTemplate>을 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[ControlTemplateExamples#ComboBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#combobox)]  
  
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