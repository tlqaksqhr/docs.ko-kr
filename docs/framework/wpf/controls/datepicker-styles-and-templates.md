---
title: DatePicker 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], DatePicker
- DatePicker [WPF], styles and templates
- templates [WPF], DatePicker
- parts [WPF], DatePicker
- styles [WPF], DatePicker
- states [WPF], DatePicker
ms.assetid: c430a657-692f-44bd-a549-2341f92d6115
ms.openlocfilehash: 5123cf0ef78d46f5cec30109a34c17eaabe13b38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="datepicker-styles-and-templates"></a>DatePicker 스타일 및 템플릿
이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.DatePicker> 제어 합니다. 기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다. 자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.  
  
## <a name="datepicker-parts"></a>DatePicker 부분  
 다음 표에서 명명된 된 요소를 나열는 <xref:System.Windows.Controls.DatePicker> 제어 합니다.  
  
|파트|형식|설명|  
|-|-|-|  
|PART_Root|<xref:System.Windows.Controls.Grid>|컨트롤의 루트입니다.|  
|PART_Button|<xref:System.Windows.Controls.Button>|열고 닫는 단추는 <xref:System.Windows.Controls.Calendar>합니다.|  
|PART_TextBox|<xref:System.Windows.Controls.Primitives.DatePickerTextBox>|날짜를 입력할 수 있는 텍스트 상자입니다.|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|에 대 한 팝업은 <xref:System.Windows.Controls.DatePicker> 제어 합니다.|  
  
## <a name="datepicker-states"></a>DatePicker 상태  
 다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.DatePicker> 제어 합니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|사용 안 함|CommonStates|<xref:System.Windows.Controls.DatePicker> 을 사용할 수 없습니다.|  
|유효|ValidationStates|컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.|  
  
## <a name="datepickertextbox-parts"></a>DatePickerTextBox 부분  
 다음 표에서 명명된 된 요소를 나열는 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 제어 합니다.  
  
|파트|형식|설명|  
|-|-|-|  
|PART_Watermark|<xref:System.Windows.Controls.ContentControl>|에 초기 텍스트를 포함 하는 요소는 <xref:System.Windows.Controls.DatePicker>합니다.|  
|PART_ContentElement|<xref:System.Windows.FrameworkElement>|시각적 요소를 포함할 수 있는 한 <xref:System.Windows.FrameworkElement>합니다. 텍스트는 <xref:System.Windows.Controls.TextBox> 이 요소에 표시 됩니다.|  
  
## <a name="datepickertextbox-states"></a>DatePickerTextBox 상태  
 다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 제어 합니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|사용 안 함|CommonStates|<xref:System.Windows.Controls.Primitives.DatePickerTextBox> 을 사용할 수 없습니다.|  
|MouseOver|CommonStates|마우스 포인터가 위에 <xref:System.Windows.Controls.Primitives.DatePickerTextBox>합니다.|  
|ReadOnly|CommonStates|사용자의 텍스트를 변경할 수 없습니다는 <xref:System.Windows.Controls.Primitives.DatePickerTextBox>합니다.|  
|포커스 있음|FocusStates|컨트롤에 포커스가 있습니다.|  
|포커스 없음|FocusStates|컨트롤에 포커스가 없습니다.|  
|워터 마크를 삽입했습니다|WatermarkStates|컨트롤에는 초기 텍스트가 표시 됩니다.  <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 경우 사용자가 텍스트를 입력 하거나 날짜를 선택 하지는 상태입니다.|  
|Unwatermarked|WatermarkStates|사용자가 텍스트를 입력의 <xref:System.Windows.Controls.Primitives.DatePickerTextBox> 에서 날짜를 선택 하거나는 <xref:System.Windows.Controls.DatePicker>합니다.|  
|유효|ValidationStates|컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.|  
  
## <a name="datepicker-controltemplate-example"></a>DatePicker ControlTemplate 예제  
 다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.DatePicker> 제어 합니다.  
  
 [!code-xaml[ControlTemplateExamples#DatePicker](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datepicker.xaml#datepicker)]  
  
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
