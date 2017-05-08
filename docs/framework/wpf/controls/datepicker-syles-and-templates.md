---
title: "DatePicker 스타일 및 템플릿 | Microsoft Docs"
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
  - "ControlTemplate[WPF], DatePicker"
  - "DatePicker[WPF], 스타일 및 템플릿"
  - "요소[WPF], DatePicker"
  - "상태[WPF], DatePicker"
  - "스타일[WPF], DatePicker"
  - "템플릿[WPF], DatePicker"
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# DatePicker 스타일 및 템플릿
이 항목에서는 <xref:System.Windows.Controls.DatePicker> 컨트롤의 스타일 및 템플릿에 대해 설명합니다.  기본 <xref:System.Windows.Controls.ControlTemplate>을 수정하여 컨트롤에 고유한 모양을 지정할 수 있습니다.  자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하십시오.  
  
## DatePicker 요소  
 다음 표에서는 <xref:System.Windows.Controls.DatePicker> 컨트롤의 명명된 요소를 보여 줍니다.  
  
||||  
|-|-|-|  
|파트|형식|설명|  
|PART\_Root|<xref:System.Windows.Controls.Grid>|컨트롤의 루트입니다.|  
|PART\_Button|<xref:System.Windows.Controls.Button>|<xref:System.Windows.Controls.Calendar>를 열고 닫는 단추입니다.|  
|PART\_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|날짜를 입력할 수 있는 텍스트 상자입니다.|  
|PART\_Popup|<xref:System.Windows.Controls.Primitives.Popup>|<xref:System.Windows.Controls.DatePicker> 컨트롤에 대한 팝업입니다.|  
  
## DatePicker 상태  
 다음 표에서는 <xref:System.Windows.Controls.DatePicker> 컨트롤의 시각적 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|보통|CommonStates|기본 상태입니다.|  
|Disabled|CommonStates|<xref:System.Windows.Controls.DatePicker>를 사용할 수 없습니다.|  
|Valid|ValidationStates|이 컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용하며 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `false`입니다.|  
|InvalidFocused|ValidationStates|컨트롤에 포커스가 있는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
|InvalidUnfocused|ValidationStates|컨트롤에 포커스가 없는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
  
## DatePickerTextBox 요소  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 컨트롤의 명명된 요소를 보여 줍니다.  
  
||||  
|-|-|-|  
|파트|형식|설명|  
|PART\_Watermark|<xref:System.Windows.Controls.ContentControl>|<xref:System.Windows.Controls.DatePicker>의 초기 텍스트가 들어 있는 요소입니다.|  
|PART\_ContentElement|<xref:System.Windows.FrameworkElement>|<xref:System.Windows.FrameworkElement>를 포함할 수 있는 시각적 요소입니다.  <xref:System.Windows.Controls.TextBox>의 텍스트가 이 요소에 표시됩니다.|  
  
## DatePickerTextBox 상태  
 다음 표에서는 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 컨트롤의 시각적 상태를 보여 줍니다.  
  
||||  
|-|-|-|  
|VisualState 이름|VisualStateGroup 이름|설명|  
|보통|CommonStates|기본 상태입니다.|  
|Disabled|CommonStates|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>를 사용할 수 없습니다.|  
|MouseOver|CommonStates|마우스 포인터가 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 위에 있습니다.|  
|ReadOnly|CommonStates|사용자는 <xref:System.Windows.Controls.Primitives.DatePickerTextBox>의 텍스트를 변경할 수 없습니다.|  
|Focused|FocusStates|컨트롤에 포커스가 있습니다.|  
|Unfocused|FocusStates|컨트롤에 포커스가 없습니다.|  
|Watermarked|WatermarkStates|초기 텍스트를 표시하는 컨트롤입니다.  <xref:System.Windows.Controls.Primitives.DatePickerTextBox>가 텍스트를 입력하지 않았거나 날짜를 선택하지 않은 상태입니다.|  
|Unwatermarked|WatermarkStates|사용자가 <xref:System.Windows.Controls.Primitives.DatePickerTextBox>에 텍스트를 입력하지 않았거나 <xref:System.Windows.Controls.DatePicker>에서 날짜를 선택하지 않았습니다.|  
|Valid|ValidationStates|이 컨트롤은 <xref:System.Windows.Controls.Validation> 클래스를 사용하며 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `false`입니다.|  
|InvalidFocused|ValidationStates|컨트롤에 포커스가 있는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
|InvalidUnfocused|ValidationStates|컨트롤에 포커스가 없는 경우 연결된 속성 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=fullName>는 `true`입니다.|  
  
## DatePicker ControlTemplate 예제  
 다음 예제에서는 <xref:System.Windows.Controls.DatePicker> 컨트롤에 대한 <xref:System.Windows.Controls.ControlTemplate>을 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[ControlTemplateExamples#DatePicker](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
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