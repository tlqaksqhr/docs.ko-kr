---
title: ListBox 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ListBox
- templates [WPF], ListBox
- states [WPF], ListBox
- ControlTemplate [WPF], ListBox
- parts [WPF], ListBox
- ListBox [WPF], styles and templates
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
ms.openlocfilehash: f1e651914530fe847bb411a79ff39e3b15be7784
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457816"
---
# <a name="listbox-styles-and-templates"></a>ListBox 스타일 및 템플릿
이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.ListBox> 제어 합니다. 기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다. 자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.  
  
## <a name="listbox-parts"></a>ListBox 파트  
 <xref:System.Windows.Controls.ListBox> 컨트롤에는 명명된 된 요소가 있습니다.  
  
 만들 때 한 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ListBox>, 서식 파일에 포함 될 수 있습니다는 <xref:System.Windows.Controls.ItemsPresenter> 내는 <xref:System.Windows.Controls.ScrollViewer>합니다. (의 <xref:System.Windows.Controls.ItemsPresenter> 각 항목에 표시 됩니다는 <xref:System.Windows.Controls.ListBox>; <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤할 수)입니다.  경우는 <xref:System.Windows.Controls.ItemsPresenter> 의 직계 자식이 없는 <xref:System.Windows.Controls.ScrollViewer>를 지정 해야 합니다는 <xref:System.Windows.Controls.ItemsPresenter> 이름, `ItemsPresenter`합니다.  
  
## <a name="listbox-states"></a>ListBox 상태  
 다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.ListBox> 제어 합니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|유효|ValidationStates|컨트롤이 유효합니다.|  
|InvalidFocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|컨트롤이 유효하지 않고 컨트롤에 포커스가 없습니다.|  
  
## <a name="listboxitem-parts"></a>ListBoxItem 파트  
 <xref:System.Windows.Controls.ListBoxItem> 컨트롤에는 명명된 된 요소가 있습니다.  
  
## <a name="listboxitem-states"></a>ListBoxItem 상태  
 다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.ListBox> 제어 합니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|-|-|-|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 컨트롤 위에 있습니다.|  
|사용 안 함|CommonStates|항목을 사용할 수 없습니다.|  
|포커스 있음|FocusStates|항목에 포커스가 있습니다.|  
|포커스 없음|FocusStates|항목에 포커스가 없습니다.|  
|선택 취소|SelectionStates|항목이 선택되어 있지 않습니다.|  
|선택함|SelectionStates|항목이 선택된 currentlyplate입니다.|  
|SelectedUnfocused|SelectionStates|항목이 선택되었지만 항목에 포커스가 없습니다.|  
|유효|ValidationStates|컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.|  
  
## <a name="listbox-controltemplate-example"></a>ListBox ControlTemplate 예제  
 다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.ListBoxItem> 컨트롤입니다.  
  
 [!code-xaml[ControlTemplateExamples#ListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
 앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Control 스타일 및 템플릿](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [컨트롤 사용자 지정](../../../../docs/framework/wpf/controls/control-customization.md)  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
