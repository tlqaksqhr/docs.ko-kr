---
title: "사용자 지정 가능한 모양이 있는 컨트롤 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], customizing
- VisualStateManager [WPF], managing the state of a control
- ControlTemplate [WPF], customizing appearance
- controls [WPF], defining the visual structure and behavior of
- customizing appearance [WPF], ControlTemplate
- managing control states [WPF], VisualStateManager
- VisualStateManager [WPF], best practice
ms.assetid: 9e356d3d-a3d0-4b01-a25f-2d43e4d53fe5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4e76e1d814df5946d0e0f946cbc8d55507a07c96
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="creating-a-control-that-has-a-customizable-appearance"></a>사용자 지정 가능한 모양이 있는 컨트롤 만들기
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]해당 모양을 사용자 지정할 수 있는 컨트롤을 만들 수가 있습니다. 예를 들어의 모양을 변경할 수 있습니다는 <xref:System.Windows.Controls.CheckBox> 어떤 설정을 제외 속성 작업을 수행 하려면 새 <xref:System.Windows.Controls.ControlTemplate>합니다. 다음 그림에서는 한 <xref:System.Windows.Controls.CheckBox> 기본값을 사용 하 <xref:System.Windows.Controls.ControlTemplate> 및 <xref:System.Windows.Controls.CheckBox> 사용자 지정을 사용 하 여 <xref:System.Windows.Controls.ControlTemplate>합니다.  
  
 ![기본 컨트롤 템플릿이 있는 확인란을 선택 합니다. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
기본 컨트롤 템플릿을 사용하는 확인란  
  
 ![사용자 지정 컨트롤 템플릿이 있는 확인란을 선택 합니다. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
사용자 지정 컨트롤 템플릿을 사용하는 확인란  
  
 컨트롤을 만들 때는 파트 및 상태 모델을 따르는 경우 컨트롤의 모양을 사용자 지정할 수 있습니다. Microsoft Expression Blend 등 디자이너 도구 컨트롤 이러한 종류의 응용 프로그램에서 사용자 지정할 수 있습니다이 모델에 따라 하면 되므로 파트 및 상태 모델을 지원 합니다.  이 항목에 파트 및 상태 모델 및 직접 컨트롤을 만들 때 사용 하는 방법에 설명 합니다. 이 항목에서는 사용자 지정 컨트롤의 예로 `NumericUpDown`을이 모델의 기본 원칙을 보여 줍니다.  `NumericUpDown` 컨트롤 사용자 거 나 낮출 수는 컨트롤의 단추를 클릭 하 여 사용 되는 숫자 값을 표시 합니다.  다음 그림에서는 `NumericUpDown` 이 항목에서 설명 하는 컨트롤입니다.  
  
 ![NumericUpDown 사용자 지정 컨트롤입니다. ] (../../../../docs/framework/wpf/controls/media/ndp-numericupdown.png "NDP_NumericUPDown")  
사용자 지정 NumericUpDown 컨트롤  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [필수 조건](#prerequisites)  
  
-   [파트 및 상태 모델](#parts_and_states_model)  
  
-   [ControlTemplate의 시각적 구조 및 컨트롤의 시각적 동작 정의](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)  
  
-   [코드에서 ControlTemplate의 부분을 사용 하 여](#using_parts_of_the_controltemplate_in_code)  
  
-   [컨트롤 계약 제공](#providing_the_control_contract)  
  
-   [전체 예제](#complete_example)  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>필수 구성 요소  
 이 항목에서는 새 하는 방법을 알고 있다고 가정 <xref:System.Windows.Controls.ControlTemplate> 는 기존 컨트롤에 대 한 익숙한 컨트롤 계약에서 요소는 내용에 설명 된 개념을 이해 하 고 [하 여 기존 컨트롤의 모양 사용자 지정 만들기는 ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)합니다.  
  
> [!NOTE]
>  상속 되는 컨트롤 모양을 사용자 지정할 수 있는 컨트롤을 만들려면 만들어야는 <xref:System.Windows.Controls.Control> 클래스 또는 해당 서브 클래스 이외의 다른 중 하나 <xref:System.Windows.Controls.UserControl>합니다.  상속 되는 컨트롤 <xref:System.Windows.Controls.UserControl> 신속 하 게 만들 수 있는 컨트롤은 되지만 사용 하지 않는 한 <xref:System.Windows.Controls.ControlTemplate> 및 모양을 사용자 지정할 수 없습니다.  
  
<a name="parts_and_states_model"></a>   
## <a name="parts-and-states-model"></a>파트 및 상태 모델  
 파트 및 상태 모델 시각적 구조 및 컨트롤의 시각적 동작을 정의 하는 방법을 지정 합니다. 파트 및 상태 모델을 수행 하려면 다음을 수행 해야 합니다.  
  
-   표시 구조 및 시각적 동작 정의 <xref:System.Windows.Controls.ControlTemplate> 컨트롤의 합니다.  
  
-   컨트롤의 논리 컨트롤 템플릿의 구성 요소와 상호 작용 하는 경우 특정 모범 사례를 따릅니다.  
  
-   에 포함 해야 하는 항목을 지정 하는 컨트롤 계약 제공는 <xref:System.Windows.Controls.ControlTemplate>합니다.  
  
 정의 하는 경우 시각적 구조 및 시각적 동작에는 <xref:System.Windows.Controls.ControlTemplate> 컨트롤의 응용 프로그램 작성자 및 변경할 수 시각적 구조 컨트롤의 시각적 동작 새 <xref:System.Windows.Controls.ControlTemplate> 코드를 작성 하는 대신 합니다.   작성자에 게 응용 프로그램에 알려 주는 컨트롤 계약을 제공 해야 <xref:System.Windows.FrameworkElement> 개체와 상태에 정의 되어야 합니다는 <xref:System.Windows.Controls.ControlTemplate>합니다. 부분과 상호 작용 하는 경우 몇 가지 모범 사례 따라야는 <xref:System.Windows.Controls.ControlTemplate> 컨트롤이 제대로 불완전 한 처리 되도록 <xref:System.Windows.Controls.ControlTemplate>합니다.  이러한 세 가지 원칙을 수행 하는 경우 응용 프로그램 작성자는 만들 수는 <xref:System.Windows.Controls.ControlTemplate> 정당한 컨트롤에 대 한 것 처럼 쉽게 수는 컨트롤에 대 한는 함께 제공 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.  다음 섹션에서는 이러한 권장 사항을 자세히에 대해 설명 합니다.  
  
<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>   
## <a name="defining-the-visual-structure-and-visual-behavior-of-a-control-in-a-controltemplate"></a>ControlTemplate의 시각적 구조 및 컨트롤의 시각적 동작 정의  
 컨트롤의 시각적 구조 및 시각적 동작에서 정의 파트 및 상태 모델을 사용 하 여 사용자 지정 컨트롤을 만들면 해당 <xref:System.Windows.Controls.ControlTemplate> 대신 해당 논리에서입니다.  컨트롤의 시각적 구조체가의 복합 <xref:System.Windows.FrameworkElement> 컨트롤 구성 하는 개체입니다.  시각적 동작은 특정 상태에 있을 때 컨트롤이 표시 되는 방법을 보여 줍니다.   만들기에 대 한 자세한 내용은 <xref:System.Windows.Controls.ControlTemplate> 시각적 구조 및 컨트롤의 시각적 동작을 지정 하는, 참조 [는 ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)합니다.  
  
 예제에서는 `NumericUpDown` 컨트롤, 시각적 구조에 두 개의 <xref:System.Windows.Controls.Primitives.RepeatButton> 컨트롤 및 <xref:System.Windows.Controls.TextBlock>합니다.  코드에 이러한 컨트롤을 추가 하는 경우는 `NumericUpDown` 생성자, 예를 들어-컨트롤 컨트롤의 위치를 변경할 수 없습니다.  코드에서 컨트롤의 시각적 구조 및 시각적 동작을 정의 하는 대신에 정의 해야 하는 <xref:System.Windows.Controls.ControlTemplate>합니다.  그런 다음 응용 프로그램 개발자는 단추 위치를 사용자 지정할 수 및 <xref:System.Windows.Controls.TextBlock> 발생 하는 동작을 지정 하 고 때 `Value` 가 음수 때문에 <xref:System.Windows.Controls.ControlTemplate> 대체 될 수 있습니다.  
  
 다음 예제에서는 시각적 구조를 보여 줍니다.는 `NumericUpDown` 포함 된 컨트롤은 <xref:System.Windows.Controls.Primitives.RepeatButton> 향상을 위해 `Value`, <xref:System.Windows.Controls.Primitives.RepeatButton> 감소 `Value`, 및 <xref:System.Windows.Controls.TextBlock> 표시할 `Value`합니다.  
  
 [!code-xaml[VSMCustomControl#VisualStructure](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]  
  
 시각적 동작은 `NumericUpDown` 컨트롤이 음수 값을 빨간색 글꼴로 된다는 점입니다.  변경 하는 경우는 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 의 <xref:System.Windows.Controls.TextBlock> 때 코드에서 `Value` 가 음수 이면는 `NumericUpDown` 빨간색 음수 값을 항상 표시 됩니다. 컨트롤의 시각적 동작을 지정 된 <xref:System.Windows.Controls.ControlTemplate> 추가 하 여 <xref:System.Windows.VisualState> 개체를 <xref:System.Windows.Controls.ControlTemplate>합니다.  다음 예제와 <xref:System.Windows.VisualState> 에 대 한 개체는 `Positive` 및 `Negative` 상태입니다.  `Positive`및 `Negative` (컨트롤은 항상 둘 중 하나)은 상호 배타적 이므로 예제에서는 배치는 <xref:System.Windows.VisualState> 개체를 하나의 <xref:System.Windows.VisualStateGroup>합니다.  컨트롤이 들어갈는 `Negative` 상태는 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 의 <xref:System.Windows.Controls.TextBlock> 빨간색으로 바뀝니다.  이 컨트롤에 있을 때의 `Positive` 상태는 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 를 반환 원래 값입니다.  정의 <xref:System.Windows.VisualState> 개체에 <xref:System.Windows.Controls.ControlTemplate> 에 대해 자세히 설명 [는 ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)합니다.  
  
> [!NOTE]
>  로 설정 된 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> 루트에 연결 <xref:System.Windows.FrameworkElement> 의 <xref:System.Windows.Controls.ControlTemplate>합니다.  
  
 [!code-xaml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
<a name="using_parts_of_the_controltemplate_in_code"></a>   
## <a name="using-parts-of-the-controltemplate-in-code"></a>코드에서 ControlTemplate의 부분을 사용 하 여  
 A <xref:System.Windows.Controls.ControlTemplate> 작성자 생략할 수 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.VisualState> 개체를 의도적으로 또는 실수로, 있지만 컨트롤의 논리는 제대로 작동 하려면 부분을 할 수 있습니다. 파트 및 상태 모델 지정 컨트롤에 유연 해야는 <xref:System.Windows.Controls.ControlTemplate> 없는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.VisualState> 개체입니다.  컨트롤을 throw 해서는 안 된 예외 또는 보고서 오류가 발생 하는 경우는 <xref:System.Windows.FrameworkElement>, <xref:System.Windows.VisualState>, 또는 <xref:System.Windows.VisualStateGroup> 없습니다는 <xref:System.Windows.Controls.ControlTemplate>합니다. 이 섹션에서는 상호 작용 하기 위한 권장 되는 방법을 설명 <xref:System.Windows.FrameworkElement> 개체 하 고 상태를 관리 합니다.  
  
### <a name="anticipate-missing-frameworkelement-objects"></a>누락 된 FrameworkElement 개체를 예상 합니다.  
 정의 하는 경우 <xref:System.Windows.FrameworkElement> 개체에 <xref:System.Windows.Controls.ControlTemplate>, 컨트롤의 논리는 그 중 일부와 상호 작용 해야 할 수 있습니다.  예를 들어는 `NumericUpDown` 제어 해당 단추의를 구독 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 늘리거나 `Value` 설정는 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성의는 <xref:System.Windows.Controls.TextBlock> 를 `Value`합니다. 사용자 지정 하는 경우 <xref:System.Windows.Controls.ControlTemplate> 생략는 <xref:System.Windows.Controls.TextBlock> 컨트롤이 해당 기능 중 일부를 잃을 있지만 컨트롤 해도 오류가 발생 하지 않도록 있어야 사용할 수 있기 단추, 또는입니다. 예를 들어 경우는 <xref:System.Windows.Controls.ControlTemplate> 변경 하는 단추가 없습니다 `Value`, `NumericUpDown` 해당 기능을 하지만 응용 프로그램을 사용 하 여 손실는 <xref:System.Windows.Controls.ControlTemplate> 계속 실행 됩니다.  
  
 다음 사례 컨트롤 누락 적절히 응답 방법을 사용 하면 <xref:System.Windows.FrameworkElement> 개체:  
  
1.  설정의 `x:Name` 각각에 대 한 특성 <xref:System.Windows.FrameworkElement> 코드에서 참조 해야 하는 합니다.  
  
2.  각각에 대 한 개인 속성 정의 <xref:System.Windows.FrameworkElement> 상호 작용 해야 하는 합니다.  
  
3.  구독 하 고에서 컨트롤이 처리 하는 모든 이벤트를 구독 취소는 <xref:System.Windows.FrameworkElement> 속성의 set 접근자입니다.  
  
4.  설정의 <xref:System.Windows.FrameworkElement> 에 정의 된 속성 2 단계는 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> 메서드. 이것은 가장 빠른 하는 <xref:System.Windows.FrameworkElement> 에 <xref:System.Windows.Controls.ControlTemplate> 컨트롤에 사용할 수 있습니다. 사용 하 여는 `x:Name` 의 <xref:System.Windows.FrameworkElement> 를 가져옵니다는 <xref:System.Windows.Controls.ControlTemplate>합니다.  
  
5.  확인 하는 <xref:System.Windows.FrameworkElement> 않습니다 `null` 해당 멤버에 액세스 하기 전에.  이 경우 `null`, 오류를 보고 하지 않습니다.  
  
 다음 예제에 나온 방법을 `NumericUpDown` 컨트롤과 간의 상호 작용 <xref:System.Windows.FrameworkElement> 앞의 목록에 권장 사항에 따라 개체입니다.  
  
 시각적 구조를 정의 하는 예제에는 `NumericUpDown` 컨트롤에 <xref:System.Windows.Controls.ControlTemplate>, <xref:System.Windows.Controls.Primitives.RepeatButton> 증가 하는 `Value` 가 해당 `x:Name` 특성이로 설정 `UpButton`합니다.  다음 예에서는 라는 속성을 선언 `UpButtonElement` 나타내는 <xref:System.Windows.Controls.Primitives.RepeatButton> 에 선언 된는 <xref:System.Windows.Controls.ControlTemplate>합니다. `set` 접근자 먼저 구독을 취소 단추의에 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 경우 `UpDownElement` 않습니다 `null`, 그런 다음 속성을 설정 및 구독에 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트입니다. 속성 정의 되지만 다른, 여기에 표시 되지 이기도 <xref:System.Windows.Controls.Primitives.RepeatButton>라는 `DownButtonElement`합니다.  
  
 [!code-csharp[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
 [!code-vb[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]  
  
 다음 예제와 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> 에 대 한는 `NumericUpDown` 제어 합니다.  이 예제에서는 사용는 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> 가져올 메서드를는 <xref:System.Windows.FrameworkElement> 에서 개체는 <xref:System.Windows.Controls.ControlTemplate>합니다.  예제 로부터 보호 하는 경우 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> 발견 한 <xref:System.Windows.FrameworkElement> 예상 되는 형식의 하지 않은 지정 된 이름의 합니다. 지정 된 된 요소를 무시 하는 것이 좋습니다 이기도 `x:Name` 있지만 잘못 된 형식이 된 합니다.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 앞의 예제에 표시 되는 사례를 따르면 있는지 컨트롤은 계속 실행 될 때 확인 된 <xref:System.Windows.Controls.ControlTemplate> 없습니다는 <xref:System.Windows.FrameworkElement>합니다.  
  
### <a name="use-the-visualstatemanager-to-manage-states"></a>사용 하 여 상태를 관리 하려면 VisualStateManager  
 <xref:System.Windows.VisualStateManager> 컨트롤의 상태 및 추적 상태를 전환 하는 데 필요한 논리를 수행 합니다. 추가 하는 경우 <xref:System.Windows.VisualState> 개체를 <xref:System.Windows.Controls.ControlTemplate>에 추가 <xref:System.Windows.VisualStateGroup> 추가 <xref:System.Windows.VisualStateGroup> 에 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> 연결 된 속성 있도록는 <xref:System.Windows.VisualStateManager> 에 액세스 하 합니다.  
  
 이전 예제를 보여 주는 반복 하는 다음 예제는 <xref:System.Windows.VisualState> 에 해당 하는 개체는 `Positive` 및 `Negative` 컨트롤의 상태입니다. <xref:System.Windows.Media.Animation.Storyboard> 에 `Negative` <xref:System.Windows.VisualState> 설정는 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 의 <xref:System.Windows.Controls.TextBlock> 빨간색입니다.   경우는 `NumericUpDown` 컨트롤이 `Negative` 상태 이면에서 스토리 보드는 `Negative` 상태가 시작 합니다.  그런 다음 <xref:System.Windows.Media.Animation.Storyboard> 에 `Negative` 컨트롤 돌아갈 때 중지 상태는 `Positive` 상태입니다.  `Positive` <xref:System.Windows.VisualState> 포함 하지 않아도 <xref:System.Windows.Media.Animation.Storyboard> 때문에 때는 <xref:System.Windows.Media.Animation.Storyboard> 에 대 한는 `Negative` 중지 되는 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 원래 색을 반환 합니다.  
  
 [!code-xaml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
 <xref:System.Windows.Controls.TextBlock> 는 이름이 지정 되며 하지만 <xref:System.Windows.Controls.TextBlock> 에 대 한 제어 계약에 없는 `NumericUpDown` 컨트롤의 논리 되지 참조 하기 때문에 <xref:System.Windows.Controls.TextBlock>합니다.  참조 되는 요소는 <xref:System.Windows.Controls.ControlTemplate> 이름을 가지 지만 제어 계약의 일부를 수 있기 때문에 필요 하지 않습니다 새 <xref:System.Windows.Controls.ControlTemplate> 컨트롤 필요가 없을 수도 해당 요소를 참조에 대 한 합니다.  예를 들어 만드는 사용자가 새 <xref:System.Windows.Controls.ControlTemplate> 에 대 한 `NumericUpDown` 나타내지 않을 `Value` 가 변경 하 여 음수는 <xref:System.Windows.Controls.Control.Foreground%2A>합니다.  그러면 두 코드와 <xref:System.Windows.Controls.ControlTemplate> 참조는 <xref:System.Windows.Controls.TextBlock> 이름으로 합니다.  
  
 컨트롤의 논리는 컨트롤의 상태를 변경 하는 일을 담당 합니다. 다음 예제에서는 `NumericUpDown` 컨트롤을 호출은 <xref:System.Windows.VisualStateManager.GoToState%2A> 다루지는 메서드는 `Positive` 상태의 `Value` 가 0 보다 크거나 및 `Negative` 상태의 `Value` 0 보다 작습니다.  
  
 [!code-csharp[VSMCustomControl#ValueStateChange](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
 [!code-vb[VSMCustomControl#ValueStateChange](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]  
  
 <xref:System.Windows.VisualStateManager.GoToState%2A> 메서드 시작 및 중지 스토리 보드를 적절 하 게 하는 데 필요한 논리를 수행 합니다. 컨트롤을 호출 하는 경우 <xref:System.Windows.VisualStateManager.GoToState%2A> 해당 상태를 변경 하는 <xref:System.Windows.VisualStateManager> 다음 작업을 수행 합니다.  
  
-   경우는 <xref:System.Windows.VisualState> 에 컨트롤 것인지는 <xref:System.Windows.Media.Animation.Storyboard>, 스토리 보드를 시작 합니다. 그런 다음은 <xref:System.Windows.VisualState> 가 컨트롤에서 제공 되는 <xref:System.Windows.Media.Animation.Storyboard>, 스토리 보드는 종료 합니다.  
  
-   지정 된 상태에 컨트롤이 이미 있으면 <xref:System.Windows.VisualStateManager.GoToState%2A> 아무 작업도 수행 하 고 반환 `true`합니다.  
  
-   지정 된 상태에 존재 하지 않는 경우는 <xref:System.Windows.Controls.ControlTemplate> 의 `control`, <xref:System.Windows.VisualStateManager.GoToState%2A> 아무 작업도 수행 하 고 반환 `false`합니다.  
  
#### <a name="best-practices-for-working-with-the-visualstatemanager"></a>VisualStateManager 사용 하기 위한 모범 사례  
 컨트롤의 상태를 유지 하기 위해 다음을 수행 하는 것이 좋습니다.  
  
-   속성을 사용 하 여 해당 상태를 추적 합니다.  
  
-   상태 간 전환 도우미 메서드를 만듭니다.  
  
 `NumericUpDown` 컨트롤이 사용 하는 `Value` 속성 인지 여부를 추적 하는 `Positive` 또는 `Negative` 상태입니다.  `NumericUpDown` 제어도 정의 `Focused` 및 `UnFocused` 상태, 트랙에서 <xref:System.Windows.UIElement.IsFocused%2A> 속성입니다. 기본적으로 컨트롤의 속성에 해당 하지 않는 상태를 사용 하는 경우 상태를 추적 하는 개인 속성이 정의할 수 있습니다.  
  
 모든 상태를 업데이트 하는 단일 메서드 호출을 중앙 집중화 된 <xref:System.Windows.VisualStateManager> 관리 가능한 코드를 유지 합니다. 다음 예제와 `NumericUpDown` 컨트롤의 도우미 메서드를 `UpdateStates`합니다. 때 `Value` 보다 크거나 0는 <xref:System.Windows.Controls.Control> 에 `Positive` 상태입니다.  때 `Value` 는 0 보다 작은 컨트롤은에 `Negative` 상태입니다.  때 <xref:System.Windows.UIElement.IsFocused%2A> 은 `true`, 컨트롤이 `Focused` 중인 상태이 고; 그렇지 않으면는 `Unfocused` 상태입니다.  컨트롤을 호출할 수 `UpdateStates` 때마다 어떤 상태를 변경 없이 상태를 변경 해야 합니다.  
  
 [!code-csharp[VSMCustomControl#UpdateStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
 [!code-vb[VSMCustomControl#UpdateStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]  
  
 에 상태 이름을 전달 하는 경우 <xref:System.Windows.VisualStateManager.GoToState%2A> 컨트롤이 있는 경우 이미 해당 상태의 <xref:System.Windows.VisualStateManager.GoToState%2A> 컨트롤의 현재 상태를 확인 하지 않아도 되므로 아무 것도 수행 합니다.  예를 들어 경우 `Value` 음수가에서 다른 음수 값에 대 한 스토리 보드로 변경는 `Negative` 상태 중단 되지 및 사용자 컨트롤의 변경을 표시 되지 것입니다.  
  
 <xref:System.Windows.VisualStateManager> 사용 하 여 <xref:System.Windows.VisualStateGroup> 개체를 호출할 때 종료 상태를 확인 하려면 <xref:System.Windows.VisualStateManager.GoToState%2A>합니다. 컨트롤은 항상 각각에 대해 하나의 상태 <xref:System.Windows.VisualStateGroup> 에 정의 된 해당 <xref:System.Windows.Controls.ControlTemplate> 동일한 다른 상태로 되 면 상태를 그대로 남겨 두기 및 <xref:System.Windows.VisualStateGroup>합니다. 예를 들어는 <xref:System.Windows.Controls.ControlTemplate> 의 `NumericUpDown` 제어 정의 `Positive` 및 `Negative` <xref:System.Windows.VisualState> 하나에서 개체 <xref:System.Windows.VisualStateGroup> 및 `Focused` 및 `Unfocused` <xref:System.Windows.VisualState> 다른 개체입니다. (볼 수 있습니다는 `Focused` 및 `Unfocused` <xref:System.Windows.VisualState> 에 정의 된는 [전체 예제](#complete_example) 컨트롤에서 발생 하는 경우이 항목의 섹션의 `Positive` 상태는 `Negative` 상태, 또는 그 반대로 참조할는 `Focused` 또는 `Unfocused` 상태입니다.  
  
 다음 세 일반적인 위치는 컨트롤의 상태가 변경 될 수 있습니다.  
  
-   경우는 <xref:System.Windows.Controls.ControlTemplate> 에 적용 되는 <xref:System.Windows.Controls.Control>합니다.  
  
-   속성이 변경 될 때입니다.  
  
-   이벤트가 발생 합니다.  
  
 다음 예제에 나와 업데이트의 상태는 `NumericUpDown` 이러한 경우에는 컨트롤입니다.  
  
 컨트롤의 상태를 업데이트 해야는 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> 메서드 올바른에 컨트롤이 표시 되도록 하면 상태로 <xref:System.Windows.Controls.ControlTemplate> 적용 됩니다. 다음 예제에서는 `UpdateStates` 에 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> 컨트롤에 적절 한 상태 인지 확인 합니다.  예를 들어, 만드는 `NumericUpDown` 컨트롤을 선택한 다음 설정의 <xref:System.Windows.Controls.Control.Foreground%2A> 녹색으로 및 `Value` -5입니다.  호출 하지 않으면 `UpdateStates` 때는 <xref:System.Windows.Controls.ControlTemplate> 에 적용 되는 `NumericUpDown` 컨트롤을 컨트롤에 없는 `Negative` 상태와 값은 빨강 대신 녹색입니다.  호출 해야 `UpdateStates` 에 컨트롤을 배치 하는 `Negative` 상태입니다.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 속성이 변경 될 때 컨트롤의 상태를 업데이트 해야 하는 경우가 많습니다. 다음 예에서는 전체 `ValueChangedCallback` 메서드. 때문에 `ValueChangedCallback` 될 때 호출 됩니다 `Value` 변경 되는 메서드 호출 `UpdateStates` 경우 `Value` 에서 양수 음수 또는 그 반대로 변경 합니다. 호출 하는 것이 좋습니다 `UpdateStates` 때 `Value` 변경 되지만 컨트롤 상태를 변경 되지 않으므로 경우 양수 또는 음수 유지 됩니다.  
  
 [!code-csharp[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
 [!code-vb[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]  
  
 이벤트가 발생 한 경우 상태를 업데이트 하려면 할 수도 있습니다. 다음 예제에서는 `NumericUpDown` 호출 `UpdateStates` 에 <xref:System.Windows.Controls.Control> 처리 하는 <xref:System.Windows.UIElement.GotFocus> 이벤트입니다.  
  
 [!code-csharp[VSMCustomControl#OnGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
 [!code-vb[VSMCustomControl#OnGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]  
  
 <xref:System.Windows.VisualStateManager> 컨트롤의 상태를 관리할 수 있습니다. 사용 하 여는 <xref:System.Windows.VisualStateManager>, 컨트롤 올바른 상태 간의 전환을 확인 합니다.  작업에 대 한이 섹션에 설명 된 권장 사항을 수행 하는 경우는 <xref:System.Windows.VisualStateManager>, 컨트롤의 코드는 읽기 쉽고 유지 됩니다.  
  
<a name="providing_the_control_contract"></a>   
## <a name="providing-the-control-contract"></a>컨트롤 계약 제공  
 컨트롤 계약을 제공 하도록 <xref:System.Windows.Controls.ControlTemplate> 작성자는 서식 파일에 배치 하 게 알 수 있습니다. 컨트롤 계약에는 세 가지 요소가 있습니다.  
  
-   컨트롤 논리가 사용하는 시각적 요소  
  
-   컨트롤의 상태 및 각 상태가 속해 있는 그룹  
  
-   컨트롤에 시각적으로 영향을 미치는 공용 속성  
  
 새 사람 <xref:System.Windows.Controls.ControlTemplate> 이름이 필요 <xref:System.Windows.FrameworkElement> 컨트롤의 논리를 사용 하는 개체는 각 개체 유형과 및 어떤 이름이 있습니다. A <xref:System.Windows.Controls.ControlTemplate> 작성자는 또한 컨트롤와 있을 수 있는 가능한 각 상태와의 이름을 알고 해야 <xref:System.Windows.VisualStateGroup> 상태입니다.  
  
 돌아가기는 `NumericUpDown` 예제에서는 컨트롤이 예상는 <xref:System.Windows.Controls.ControlTemplate> 다음 있어야 <xref:System.Windows.FrameworkElement> 개체:  
  
-   A <xref:System.Windows.Controls.Primitives.RepeatButton> 호출 `UpButton`합니다.  
  
-   A <xref:System.Windows.Controls.Primitives.RepeatButton> 호출`DownButton.`  
  
 컨트롤은 다음과 같은 상태가 될 수 있습니다.  
  
-   안에`ValueStates`<xref:System.Windows.VisualStateGroup>  
  
    -   `Positive`  
  
    -   `Negative`  
  
-   안에`FocusStates`<xref:System.Windows.VisualStateGroup>  
  
    -   `Focused`  
  
    -   `Unfocused`  
  
 응용 프로그램을 지정 하려면 <xref:System.Windows.FrameworkElement> 컨트롤이 예상 하는 개체를 사용 하는 <xref:System.Windows.TemplatePartAttribute>, 이름 및 예상 되는 요소의 형식을 지정 하는 합니다.  컨트롤의 가능한 상태를 지정 하려면 사용 된 <xref:System.Windows.TemplateVisualStateAttribute>, 및 상태의 이름을 지정 하는 <xref:System.Windows.VisualStateGroup> 에 속합니다.  배치는 <xref:System.Windows.TemplatePartAttribute> 및 <xref:System.Windows.TemplateVisualStateAttribute> 컨트롤의 클래스 정의에 있습니다.  
  
 컨트롤의 모양에 영향을 주는 모든 공용 속성 컨트롤 계약의 일부 이기도 합니다.  
  
 다음 예제에서는 지정 된 <xref:System.Windows.FrameworkElement> 개체 및 상태에 대 한는 `NumericUpDown` 제어 합니다.  
  
 [!code-csharp[VSMCustomControl#ControlContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
 [!code-vb[VSMCustomControl#ControlContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>완성된 예제  
 다음 예제는 전체 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 `NumericUpDown` 제어 합니다.  
  
 [!code-xaml[VSMCustomControl#NUDTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]  
  
 다음 예제에 대 한 논리는 `NumericUpDown`합니다.  
  
 [!code-csharp[VSMCustomControl#ControlLogic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
 [!code-vb[VSMCustomControl#ControlLogic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]  
  
## <a name="see-also"></a>참고 항목  
 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)  
 [컨트롤 사용자 지정](../../../../docs/framework/wpf/controls/control-customization.md)
