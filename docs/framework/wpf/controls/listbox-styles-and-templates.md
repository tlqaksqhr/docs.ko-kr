---
title: "ListBox 스타일 및 템플릿 | Microsoft Docs"
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
  - "ControlTemplate[WPF], ListBox"
  - "ListBox[WPF], 스타일 및 템플릿"
  - "요소[WPF], ListBox"
  - "상태[WPF], ListBox"
  - "스타일[WPF], ListBox"
  - "템플릿[WPF], ListBox"
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# ListBox 스타일 및 템플릿
이 항목에서는 <xref:System.Windows.Controls.ListBox> 컨트롤의 스타일 및 템플릿에 대해 설명합니다.  기본 <xref:System.Windows.Controls.ControlTemplate>을 수정하여 컨트롤에 고유한 모양을 지정할 수 있습니다.  자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하십시오.  
  
## ListBox 요소  
 <xref:System.Windows.Controls.ListBox> 컨트롤에는 명명된 요소가 없습니다.  
  
 <xref:System.Windows.Controls.ListBox>에 대한 <xref:System.Windows.Controls.ControlTemplate>을 만들 경우 템플릿의 <xref:System.Windows.Controls.ScrollViewer> 내에 <xref:System.Windows.Controls.ItemsPresenter>가 포함될 수 있습니다.  <xref:System.Windows.Controls.ItemsPresenter>는 각 항목을 <xref:System.Windows.Controls.ListBox>에 표시하고 <xref:System.Windows.Controls.ScrollViewer>는 컨트롤 내에서 스크롤할 수 있도록 합니다.  <xref:System.Windows.Controls.ItemsPresenter>가 <xref:System.Windows.Controls.ScrollViewer>의 직계 자식이 아니면 <xref:System.Windows.Controls.ItemsPresenter>에 `ItemsPresenter`라는 이름을 지정해야 합니다.  
  
## ListBox 상태  
 다음 표에서는 <xref:System.Windows.Controls.ListBox> 컨트롤의 시각적 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|Valid|ValidationStates|컨트롤이 유효합니다.|  
|InvalidFocused|ValidationStates|컨트롤이 잘못되었지만 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|컨트롤이 잘못되었으며 포커스가 없습니다.|  
  
## ListBoxItem 요소  
 <xref:System.Windows.Controls.ListBoxItem> 컨트롤에는 명명된 요소가 없습니다.  
  
## ListBoxItem 상태  
 다음 표에서는 <xref:System.Windows.Controls.ListBox> 컨트롤의 시각적 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 컨트롤 위에 있습니다.|  
|Disabled|CommonStates|항목을 사용할 수 없습니다.|  
|Focused|FocusStates|항목에 포커스가 있습니다.|  
|Unfocused|FocusStates|항목에 포커스가 없습니다.|  
|선택하지 않음|SelectionStates|항목이 현재 선택되어 있습니다.|  
|선택함|SelectionStates|항목이 선택되어 있지 않습니다.|  
|SelectedUnfocused|SelectionStates|항목이 선택되었지만 포커스가 없습니다.|  
|Valid|ValidationStates|이 컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용하며 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `false`입니다.|  
|InvalidFocused|ValidationStates|컨트롤에 포커스가 있는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
|InvalidUnfocused|ValidationStates|컨트롤에 포커스가 없는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
  
## ListBox ControlTemplate 예제  
 다음 예제에서는 <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.ListBoxItem> 컨트롤에 대한 <xref:System.Windows.Controls.ControlTemplate>을 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[ControlTemplateExamples#ListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
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