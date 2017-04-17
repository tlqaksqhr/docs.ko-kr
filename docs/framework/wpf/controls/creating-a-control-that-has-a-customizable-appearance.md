---
title: "사용자 지정 가능한 모양이 있는 컨트롤 만들기 | Microsoft Docs"
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
  - "컨트롤[WPF], 사용자 지정"
  - "컨트롤[WPF], 표시 구조 및 동작 정의"
  - "ControlTemplate[WPF], 모양 사용자 지정"
  - "모양 사용자 지정[WPF], ControlTemplate"
  - "제어 상태 관리[WPF], VisualStateManager"
  - "VisualStateManager[WPF], 모범 사례"
  - "VisualStateManager[WPF], 컨트롤 상태 관리"
ms.assetid: 9e356d3d-a3d0-4b01-a25f-2d43e4d53fe5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 사용자 지정 가능한 모양이 있는 컨트롤 만들기
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]를 사용하면 모양을 사용자 지정할 수 있는 컨트롤을 만들 수 있습니다.  예를 들어 새 <xref:System.Windows.Controls.ControlTemplate>을 만들면 속성 설정을 통해 변경할 수 있는 것 이상으로 <xref:System.Windows.Controls.CheckBox>의 모양을 변경할 수 있습니다.  다음 그림에서는 기본 <xref:System.Windows.Controls.ControlTemplate>을 사용하는 <xref:System.Windows.Controls.CheckBox>와 사용자 지정 <xref:System.Windows.Controls.ControlTemplate>을 사용하는 <xref:System.Windows.Controls.CheckBox>를 보여 줍니다.  
  
 ![기본 컨트롤 템플릿이 있는 확인란](../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP\_CheckBoxDefault")  
기본 컨트롤 템플릿을 사용하는 확인란  
  
 ![사용자 지정 컨트롤 템플릿이 있는 확인란](../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP\_CheckBoxCustom")  
사용자 지정 컨트롤 템플릿을 사용하는 확인란  
  
 컨트롤을 만들 때 부분 및 상태 모델을 사용하면 컨트롤의 모양을 사용자 지정할 수 있습니다.  Microsoft Expression Blend와 같은 디자이너 도구는 부분 및 상태 모델을 지원하므로 이 모델을 따르는 경우 해당 종류의 응용 프로그램에서 컨트롤을 사용자 지정할 수 있습니다.  이 항목에서는 부분 및 상태 모델 및 컨트롤을 만들 때 이 모델을 사용하는 방법에 대해 설명합니다.  이 항목에서는 사용자 지정 컨트롤의 예로 `NumericUpDown`을 사용하여 이 모델의 원리를 보여 줍니다.  `NumericUpDown` 컨트롤은 사용자가 컨트롤의 단추를 클릭하여 늘리거나 줄일 수 있는 숫자 값을 표시합니다.  다음 그림에서는 이 항목에서 설명한 `NumericUpDown` 컨트롤을 보여 줍니다.  
  
 ![NumericUpDown 사용자 지정 컨트롤](../../../../docs/framework/wpf/controls/media/ndp-numericupdown.png "NDP\_NumericUPDown")  
사용자 지정 NumericUpDown 컨트롤  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [사전 요구 사항](#prerequisites)  
  
-   [부분 및 상태 모델](#parts_and_states_model)  
  
-   [ControlTemplate에서 컨트롤의 시각적 구조 및 시각적 동작 정의](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)  
  
-   [코드에서 ControlTemplate의 부분 사용](#using_parts_of_the_controltemplate_in_code)  
  
-   [컨트롤 계약 제공](#providing_the_control_contract)  
  
-   [완성된 예제](#complete_example)  
  
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목에서는 독자가 기존 컨트롤에 대한 새 <xref:System.Windows.Controls.ControlTemplate>을 만드는 방법을 알고 있으며 컨트롤 계약의 요소에 익숙하고 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)에 설명된 개념을 이해하고 있다고 가정합니다.  
  
> [!NOTE]
>  모양을 사용자 지정할 수 있는 컨트롤을 만들려면 <xref:System.Windows.Controls.Control> 클래스 또는 해당 서브클래스 중 <xref:System.Windows.Controls.UserControl> 이외의 클래스에서 상속하는 컨트롤을 만들어야 합니다.  <xref:System.Windows.Controls.UserControl>에서 상속하는 컨트롤은 빠르게 만들 수 있지만 <xref:System.Windows.Controls.ControlTemplate>을 사용하지 않으므로 모양을 사용자 지정할 수 없습니다.  
  
<a name="parts_and_states_model"></a>   
## 부분 및 상태 모델  
 부분 및 상태 모델에서는 컨트롤의 시각적 구조 및 시각적 동작을 정의하는 방법을 지정합니다.  부분 및 상태 모델을 사용하려면 다음을 수행해야 합니다.  
  
-   컨트롤의 <xref:System.Windows.Controls.ControlTemplate>에서 시각적 구조 및 시각적 동작을 정의합니다.  
  
-   컨트롤의 논리가 컨트롤 템플릿의 부분과 상호 작용하는 경우 특정 최선의 방법을 따릅니다.  
  
-   <xref:System.Windows.Controls.ControlTemplate>에 반드시 포함되어야 하는 내용을 지정하는 컨트롤 계약을 제공합니다.  
  
 컨트롤의 <xref:System.Windows.Controls.ControlTemplate>에 시각적 구조 및 시각적 동작을 정의한 경우 응용 프로그램 작성자는 코드를 작성하는 대신 새 <xref:System.Windows.Controls.ControlTemplate>을 만들어 컨트롤의 시각적 구조 및 시각적 동작을 변경할 수 있습니다.  <xref:System.Windows.Controls.ControlTemplate>에 정의해야 하는 <xref:System.Windows.FrameworkElement> 개체 및 상태를 지시하는 컨트롤 계약을 응용 프로그램 작성자에게 제공해야 합니다.  <xref:System.Windows.Controls.ControlTemplate>의 부분과 상호 작용할 때는 컨트롤이 불완전한 <xref:System.Windows.Controls.ControlTemplate>을 적절하게 처리할 수 있도록 최선의 방법을 따라야 합니다.  이 세 가지 원칙을 따른다면 응용 프로그램 작성자는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 제공되는 컨트롤의 경우와 마찬가지로 손쉽게 사용자 컨트롤에 대한 <xref:System.Windows.Controls.ControlTemplate>을 만들 수 있습니다.  다음 단원에서는 이러한 권장 사항에 대해 자세히 설명합니다.  
  
<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>   
## ControlTemplate에서 컨트롤의 시각적 구조 및 시각적 동작 정의  
 부분 및 상태 모델을 사용하여 사용자 지정 컨트롤을 만드는 경우에는 해당 논리 대신 해당 <xref:System.Windows.Controls.ControlTemplate>에 컨트롤의 시각적 구조 및 시각적 동작을 정의합니다.  컨트롤의 시각적 구조는 컨트롤을 구성하는 <xref:System.Windows.FrameworkElement> 개체를 합성한 것입니다.  시각적 동작은 컨트롤이 특정 상태에 있을 때 표시되는 방식입니다.  컨트롤의 시각적 구조 및 시각적 동작을 지정하는 <xref:System.Windows.Controls.ControlTemplate>을 만드는 방법에 대한 자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하십시오.  
  
 `NumericUpDown` 컨트롤 예제에서 시각적 구조는 두 개의 <xref:System.Windows.Controls.Primitives.RepeatButton> 컨트롤과 하나의 <xref:System.Windows.Controls.TextBlock>을 포함합니다.  `NumericUpDown` 컨트롤의 코드\(예: 해당 생성자 내부\)에서 이러한 컨트롤을 추가하는 경우 이 컨트롤의 위치를 변경할 수 없습니다.  컨트롤의 시각적 구조 및 시각적 동작을 코드에서 정의하는 대신 <xref:System.Windows.Controls.ControlTemplate>에서 정의해야 합니다.  이렇게 하면 <xref:System.Windows.Controls.ControlTemplate>을 교체할 수 있으므로 응용 프로그램 개발자는 단추 및 <xref:System.Windows.Controls.TextBlock>의 위치를 사용자 지정하고 `Value`가 음수일 때 발생하는 동작을 지정할 수 있습니다.  
  
 다음 예제에서는 `Value`를 늘리기 위한 <xref:System.Windows.Controls.Primitives.RepeatButton>, `Value`를 줄이기 위한 <xref:System.Windows.Controls.Primitives.RepeatButton> 및 `Value`를 표시하기 위한 <xref:System.Windows.Controls.TextBlock>을 포함하는 `NumericUpDown` 컨트롤의 시각적 구조를 보여 줍니다.  
  
 [!code-xml[VSMCustomControl#VisualStructure](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]  
  
 `NumericUpDown` 컨트롤의 시각적 동작은 값이 음수인 경우 값을 빨간색 글꼴로 표시하는 것입니다.  `Value`가 음수일 때 코드에서 <xref:System.Windows.Controls.TextBlock>의 <xref:System.Windows.Controls.TextBlock.Foreground%2A>를 변경하면 `NumericUpDown`은 항상 빨간색 음수 값을 표시하게 됩니다.  <xref:System.Windows.Controls.ControlTemplate>에 <xref:System.Windows.VisualState> 개체를 추가하여 <xref:System.Windows.Controls.ControlTemplate>에서 컨트롤의 시각적 동작을 지정합니다.  다음 예제에서는 `Positive` 및 `Negative` 상태에 대한 <xref:System.Windows.VisualState> 개체를 보여 줍니다.  `Positive`와 `Negative`는 상호 배타적이므로\(즉 컨트롤은 항상 둘 중 하나의 상태에만 존재할 수 있음\) 이 예제에서는 <xref:System.Windows.VisualState> 개체를 단일 <xref:System.Windows.VisualStateGroup>에 배치합니다.  컨트롤이 `Negative` 상태가 되면 <xref:System.Windows.Controls.TextBlock>의 <xref:System.Windows.Controls.TextBlock.Foreground%2A>가 빨간색이 됩니다.  컨트롤이 `Positive` 상태에 있으면 <xref:System.Windows.Controls.TextBlock.Foreground%2A>가 원래 값으로 돌아갑니다.  <xref:System.Windows.Controls.ControlTemplate>에서 <xref:System.Windows.VisualState> 개체를 정의하는 방법은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)에서 더 자세하게 설명합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Controls.ControlTemplate>의 루트 <xref:System.Windows.FrameworkElement>에는 연결된 속성 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=fullName>를 설정해야 합니다.  
  
 [!code-xml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
<a name="using_parts_of_the_controltemplate_in_code"></a>   
## 코드에서 ControlTemplate의 부분 사용  
 <xref:System.Windows.Controls.ControlTemplate> 작성자가 의도적이거나 실수로 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.VisualState> 개체를 빠뜨릴 수 있지만 컨트롤의 논리가 올바르게 작동하려면 이러한 부분이 있어야 합니다.  부분 및 상태 모델에 따르면 <xref:System.Windows.Controls.ControlTemplate>에 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.VisualState> 개체가 누락된 경우에도 컨트롤이 계속 작동할 수 있어야 합니다.  <xref:System.Windows.Controls.ControlTemplate>에 <xref:System.Windows.FrameworkElement>, <xref:System.Windows.VisualState>, 또는 <xref:System.Windows.VisualStateGroup>이 없더라도 컨트롤에서 예외를 throw하거나 오류를 보고해서는 안됩니다.  이 단원에서는 <xref:System.Windows.FrameworkElement> 개체와 상호 작용하고 상태를 관리하는 데 권장되는 방법에 대해 설명합니다.  
  
### 누락된 FrameworkElement 개체 예상  
 <xref:System.Windows.Controls.ControlTemplate>에 <xref:System.Windows.FrameworkElement> 개체를 정의하는 경우 컨트롤의 논리에서 이러한 개체 중 일부와 상호 작용해야 하는 경우가 있을 수 있습니다.  예를 들어 `NumericUpDown` 컨트롤은 단추의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 구독하여 `Value`를 늘리거나 줄이고 <xref:System.Windows.Controls.TextBlock>의 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성을 `Value`로 설정합니다.  사용자 지정 <xref:System.Windows.Controls.ControlTemplate>에 <xref:System.Windows.Controls.TextBlock> 또는 단추가 누락된 경우 컨트롤이 일부 기능을 상실하는 것은 허용되지만 컨트롤에서 오류가 발생해서는 안됩니다.  예를 들어 <xref:System.Windows.Controls.ControlTemplate>에 `Value`를 변경하는 단추가 없는 경우 `NumericUpDown`은 해당 기능을 상실하지만 <xref:System.Windows.Controls.ControlTemplate>을 사용하는 응용 프로그램은 계속하여 실행됩니다.  
  
 다음 방법을 사용하면 누락된 <xref:System.Windows.FrameworkElement> 개체에 컨트롤이 적절하게 응답할 수 있습니다.  
  
1.  코드에서 참조해야 하는 각 <xref:System.Windows.FrameworkElement>에 대해 `x:Name` 특성을 설정합니다.  
  
2.  상호 작용해야 하는 각 <xref:System.Windows.FrameworkElement>에 대해 전용 속성을 정의합니다.  
  
3.  <xref:System.Windows.FrameworkElement> 속성의 set 접근자에서 컨트롤이 처리하는 모든 이벤트를 구독 및 구독 취소합니다.  
  
4.  2단계에서 정의한 <xref:System.Windows.FrameworkElement> 속성을 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> 메서드에서 설정합니다.  이 시점에서 컨트롤은 처음으로 <xref:System.Windows.Controls.ControlTemplate>의 <xref:System.Windows.FrameworkElement>를 사용할 수 있게 됩니다.  `x:Name`을 사용하여 <xref:System.Windows.Controls.ControlTemplate>에서 <xref:System.Windows.FrameworkElement>를 가져옵니다.  
  
5.  해당 멤버에 액세스하기 전에 <xref:System.Windows.FrameworkElement>가 `null`이 아닌지 확인합니다.  `null`인 경우에도 오류를 보고하지 않습니다.  
  
 다음 예제에서는 앞의 목록에 있는 권장 사항에 맞게 `NumericUpDown` 컨트롤이 <xref:System.Windows.FrameworkElement> 개체와 상호 작용하는 방법을 보여 줍니다.  
  
 <xref:System.Windows.Controls.ControlTemplate>에서 `NumericUpDown` 컨트롤의 시각적 구조를 정의하는 예제에서 `Value`를 늘리는 <xref:System.Windows.Controls.Primitives.RepeatButton>의 `x:Name` 특성은 `UpButton`으로 설정됩니다.  다음 예제에서는 <xref:System.Windows.Controls.ControlTemplate>에 선언된 <xref:System.Windows.Controls.Primitives.RepeatButton>을 나타내는 `UpButtonElement`라는 속성을 선언합니다.  `UpDownElement`가 `null`이 아니면 `set` 접근자는 먼저 단추의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 대한 구독을 취소하고, 속성을 설정한 다음 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 구독합니다.  다른 <xref:System.Windows.Controls.Primitives.RepeatButton>에 대해서는 `DownButtonElement`라는 속성이 정의되지만 여기에 표시되지는 않습니다.  
  
 [!code-csharp[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
 [!code-vb[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]  
  
 다음 예제에서는 `NumericUpDown` 컨트롤에 대한 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>을 보여 줍니다.  이 예제에서는 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> 메서드를 사용하여 <xref:System.Windows.Controls.ControlTemplate>에서 <xref:System.Windows.FrameworkElement> 개체를 가져옵니다.  이 예제에서는 <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>가 지정된 이름을 가졌지만 예상한 형식이 아닌 <xref:System.Windows.FrameworkElement>를 찾는 경우에 대비합니다.  지정된 `x:Name`을 가지고 있지만 형식이 잘못된 요소를 무시하는 것도 최선의 방법에 포함됩니다.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 앞 예제에서 보여 준 방법을 따르면 <xref:System.Windows.Controls.ControlTemplate>에 <xref:System.Windows.FrameworkElement>가 없는 경우에도 컨트롤이 계속 실행됩니다.  
  
### VisualStateManager를 사용하여 상태 관리  
 <xref:System.Windows.VisualStateManager>는 컨트롤 상태를 추적하고 상태 간 전환에 필요한 논리를 수행합니다.  <xref:System.Windows.VisualState> 개체를 <xref:System.Windows.Controls.ControlTemplate>에 추가하는 경우 이 개체를 <xref:System.Windows.VisualStateGroup>에 추가하고 <xref:System.Windows.VisualStateGroup>을 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=fullName> 연결 속성에 추가하여 <xref:System.Windows.VisualStateManager>가 해당 개체에 액세스할 수 있도록 합니다.  
  
 다음 예제에서는 컨트롤의 `Positive` 및 `Negative` 상태에 해당하는 <xref:System.Windows.VisualState> 개체를 보여 주는 이전 예제를 반복합니다.  `Negative` <xref:System.Windows.VisualState>의 <xref:System.Windows.Media.Animation.Storyboard>는 <xref:System.Windows.Controls.TextBlock>의 <xref:System.Windows.Controls.TextBlock.Foreground%2A>를 빨간색으로 바꿉니다.  `NumericUpDown` 컨트롤이 `Negative` 상태에 있으면 `Negative` 상태의 스토리보드가 시작됩니다.  그런 다음 컨트롤이 `Positive` 상태로 돌아가면 `Negative` 상태의 <xref:System.Windows.Media.Animation.Storyboard>가 중지됩니다.  `Negative`에 대한 <xref:System.Windows.Media.Animation.Storyboard>가 중지되면 <xref:System.Windows.Controls.TextBlock.Foreground%2A>가 원래 색으로 돌아가므로 `Positive` <xref:System.Windows.VisualState>에는 <xref:System.Windows.Media.Animation.Storyboard>가 포함되지 않아도 됩니다.  
  
 [!code-xml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
 <xref:System.Windows.Controls.TextBlock>의 이름이 지정되지만 컨트롤의 논리에서 <xref:System.Windows.Controls.TextBlock>을 참조하지 않기 때문에 <xref:System.Windows.Controls.TextBlock>은 `NumericUpDown`에 대한 컨트롤 계약에 포함되지 않습니다.  <xref:System.Windows.Controls.ControlTemplate>에서 참조되는 요소에 이름이 있지만 컨트롤에 대한 새 <xref:System.Windows.Controls.ControlTemplate>이 해당 요소를 참조할 필요가 없기 때문에 컨트롤 계약에 포함되지 않아도 됩니다.  예를 들어 `NumericUpDown`에 대한 새 <xref:System.Windows.Controls.ControlTemplate>을 만드는 사용자가 <xref:System.Windows.Controls.Control.Foreground%2A>를 변경하여 `Value`가 negative인지 나타내지 않을 수 있습니다.  이러한 경우 코드와 <xref:System.Windows.Controls.ControlTemplate>은 모두 이름을 사용하여 <xref:System.Windows.Controls.TextBlock>을 참조하지 않습니다.  
  
 컨트롤 상태 변경은 컨트롤의 논리가 담당합니다.  다음 예제에서는 `NumericUpDown` 컨트롤이 `Value`가 0 이상일 때는 `Positive` 상태로, `Value`가 0보다 작을 때는 `Negative` 상태로 이동하기 위해 <xref:System.Windows.VisualStateManager.GoToState%2A> 메서드를 호출합니다.  
  
 [!code-csharp[VSMCustomControl#ValueStateChange](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
 [!code-vb[VSMCustomControl#ValueStateChange](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]  
  
 <xref:System.Windows.VisualStateManager.GoToState%2A> 메서드는 스토리보드를 적절히 시작하고 중지하는 데 필요한 논리를 수행합니다.  컨트롤이 해당 상태를 변경하기 위해 <xref:System.Windows.VisualStateManager.GoToState%2A>를 호출하면 <xref:System.Windows.VisualStateManager>는 다음 작업을 수행합니다.  
  
-   컨트롤이 이동하려는 <xref:System.Windows.VisualState>에 <xref:System.Windows.Media.Animation.Storyboard>가 있으면 해당 스토리보드가 시작됩니다.  컨트롤이 현재 속해 있는 <xref:System.Windows.VisualState>에 <xref:System.Windows.Media.Animation.Storyboard>가 있으면 해당 스토리보드는 종료됩니다.  
  
-   컨트롤이 이미 지정된 상태에 있으면 <xref:System.Windows.VisualStateManager.GoToState%2A>는 아무런 동작도 취하지 않고 `true`를 반환합니다.  
  
-   지정된 상태가 `control`의 <xref:System.Windows.Controls.ControlTemplate>에 없으면 <xref:System.Windows.VisualStateManager.GoToState%2A>는 아무런 동작도 취하지 않고 `false`를 반환합니다.  
  
#### VisualStateManager를 사용하는 최선의 방법  
 컨트롤의 상태를 유지 관리하기 위해 다음 작업을 수행하는 것이 좋습니다.  
  
-   속성을 사용하여 상태를 추적합니다.  
  
-   상태 간 전환을 위한 도우미 메서드를 만듭니다.  
  
 `NumericUpDown` 컨트롤은 해당 `Value` 속성을 사용하여 자신이 `Positive` 또는 `Negative` 중 어떤 상태에 있는지 추적합니다.  또한 `NumericUpDown` 컨트롤은 <xref:System.Windows.UIElement.IsFocused%2A> 속성을 추적하는 `Focused` 및 `UnFocused` 상태를 정의합니다.  컨트롤의 속성에 자연스럽게 대응되지 않는 상태를 사용하는 경우 private 속성을 정의하여 상태를 추적할 수 있습니다.  
  
 모든 상태를 업데이트하는 단일 메서드는 <xref:System.Windows.VisualStateManager>에 대한 호출을 중앙 집중화하고 코드를 관리 가능한 상태로 유지합니다.  다음 예제에서는 `NumericUpDown` 컨트롤의 도우미 메서드인 `UpdateStates`를 보여 줍니다.  `Value`가 0보다 크거나 같은 경우 <xref:System.Windows.Controls.Control>은 `Positive` 상태에 있고  `Value`가 0보다 작으면 `Negative` 상태에 있습니다.  <xref:System.Windows.UIElement.IsFocused%2A>가 `true`이면 컨트롤이 `Focused` 상태이고, 그렇지 않으면 `Unfocused` 상태입니다.  이 컨트롤은 변경하려는 상태에 상관 없이 상태를 변경해야 할 때마다 `UpdateStates`를 호출할 수 있습니다.  
  
 [!code-csharp[VSMCustomControl#UpdateStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
 [!code-vb[VSMCustomControl#UpdateStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]  
  
 컨트롤이 이미 특정 상태에 있을 때 해당 상태 이름을 <xref:System.Windows.VisualStateManager.GoToState%2A>에 전달하면 <xref:System.Windows.VisualStateManager.GoToState%2A>는 아무런 동작도 하지 않으므로 컨트롤의 현재 상태를 확인할 필요가 없습니다.  예를 들어 `Value`가 음수에서 다른 음수로 변경되면 `Negative` 상태에 대한 스토리보드는 중단되지 않으며 사용자는 컨트롤의 변경 내용을 보지 못합니다.  
  
 <xref:System.Windows.VisualStateManager.GoToState%2A>를 호출하면 <xref:System.Windows.VisualStateManager>는 <xref:System.Windows.VisualStateGroup> 개체를 사용하여 어떤 상태를 종료할지 결정합니다.  컨트롤은 언제나 해당 <xref:System.Windows.Controls.ControlTemplate>에 정의된 각 <xref:System.Windows.VisualStateGroup>별로 하나의 상태에 있으며 동일한 <xref:System.Windows.VisualStateGroup> 내에서 다른 상태로 이동할 때만 상태를 벗어납니다.  예를 들어 `NumericUpDown` 컨트롤의 <xref:System.Windows.Controls.ControlTemplate>은 한 <xref:System.Windows.VisualStateGroup>에서 `Positive` 및 `Negative` <xref:System.Windows.VisualState> 개체를 정의하고 다른 그룹에서 `Focused` 및 `Unfocused` <xref:System.Windows.VisualState> 개체를 정의합니다.  이 항목의 [완성된 예제](#complete_example) 단원에 정의된 `Focused` 및 `Unfocused` <xref:System.Windows.VisualState>를 참조할 수 있습니다. 컨트롤이 `Positive` 상태에서 `Negative` 상태로 변경되거나 그 반대로 변경될 때 컨트롤은 `Focused` 또는 `Unfocused` 상태로 유지됩니다.  
  
 컨트롤 상태가 변경될 수 있는 다음과 같은 세 가지 일반적인 경우가 있습니다.  
  
-   <xref:System.Windows.Controls.ControlTemplate>이 <xref:System.Windows.Controls.Control>에 적용되는 경우  
  
-   속성이 변경되는 경우  
  
-   이벤트가 발생하는 경우  
  
 다음 예제에서는 이러한 경우에 `NumericUpDown` 컨트롤의 상태를 업데이트합니다.  
  
 <xref:System.Windows.Controls.ControlTemplate>이 적용될 때 컨트롤이 올바른 상태로 표시되도록 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> 메서드에서 컨트롤의 상태를 업데이트해야 합니다.  다음 예제에서는 컨트롤이 적절한 상태에 있도록 하기 위해 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>에서 `UpdateStates`를 호출합니다.  예를 들어 `NumericUpDown` 컨트롤을 만든 다음 해당 <xref:System.Windows.Controls.Control.Foreground%2A>를 녹색으로, `Value`를 \-5로 설정한다고 가정합니다.  <xref:System.Windows.Controls.ControlTemplate>이 `NumericUpDown` 컨트롤에 적용될 때 `UpdateStates`를 호출하지 않으면 컨트롤이 `Negative` 상태에 있지 않고 값이 빨강이 아닌 녹색입니다.  `UpdateStates`를 호출하여 컨트롤을 `Negative` 상태로 만들어야 합니다.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 속성이 변경될 때 컨트롤 상태를 업데이트해야 하는 경우도 있습니다.  다음 예제에서는 전체 `ValueChangedCallback` 메서드를 보여 줍니다.  `Value`가 변경되면 `ValueChangedCallback`이 호출되므로 이 메서드는 `Value`가 양수에서 음수로 변경되거나 그 반대인 경우 `UpdateStates`를 호출합니다.  `Value`가 변경되지만 양수 또는 음수가 바뀌지 않는 경우에도 `UpdateStates`를 호출할 수 있는데 그 이유는 이 경우 컨트롤이 상태를 변경하지 않기 때문입니다.  
  
 [!code-csharp[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
 [!code-vb[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]  
  
 이벤트가 발생할 때도 상태를 업데이트해야 하는 경우가 있습니다.  다음 예제에서는 `NumericUpDown`이 <xref:System.Windows.Controls.Control>의 `UpdateStates`를 호출하여 <xref:System.Windows.UIElement.GotFocus> 이벤트를 처리합니다.  
  
 [!code-csharp[VSMCustomControl#OnGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
 [!code-vb[VSMCustomControl#OnGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]  
  
 <xref:System.Windows.VisualStateManager>는 컨트롤 상태를 관리하는 데 도움을 줍니다.  <xref:System.Windows.VisualStateManager>를 사용하면 컨트롤의 상태 간 올바른 전환을 보장할 수 있습니다.  이 단원에 설명된 <xref:System.Windows.VisualStateManager> 사용 관련 권장 사항을 따르면 컨트롤의 코드를 읽기 쉽고 유지 관리하기 쉽게 작성할 수 있습니다.  
  
<a name="providing_the_control_contract"></a>   
## 컨트롤 계약 제공  
 <xref:System.Windows.Controls.ControlTemplate> 작성자가 템플릿에 무엇을 배치할지 알 수 있도록 컨트롤 계약을 제공합니다.  컨트롤 계약에는 다음 세 가지 요소가 있습니다.  
  
-   컨트롤 논리가 사용하는 시각적 요소  
  
-   컨트롤의 상태 및 각 상태가 속해 있는 그룹  
  
-   컨트롤에 시각적으로 영향을 미치는 public 속성  
  
 새 <xref:System.Windows.Controls.ControlTemplate>을 만드는 사람은 컨트롤의 논리가 사용하는 <xref:System.Windows.FrameworkElement> 개체, 각 개체의 형식 및 이름에 대해 알고 있어야 합니다.  또한 <xref:System.Windows.Controls.ControlTemplate> 작성자는 컨트롤이 속할 수 있는 가능한 각 상태의 이름 및 해당 상태가 속한 <xref:System.Windows.VisualStateGroup>에 대해 알고 있어야 합니다.  
  
 `NumericUpDown` 예제로 돌아가면 이 컨트롤은 <xref:System.Windows.Controls.ControlTemplate>에 다음 <xref:System.Windows.FrameworkElement> 개체가 있을 것으로 예상합니다.  
  
-   `UpButton`이라는 이름의 <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
-   `DownButton`이라는 이름의 <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
 컨트롤은 다음 상태에 있을 수 있습니다.  
  
-   `ValueStates` <xref:System.Windows.VisualStateGroup>의 경우  
  
    -   `Positive`  
  
    -   `Negative`  
  
-   `FocusStates` <xref:System.Windows.VisualStateGroup>의 경우  
  
    -   `Focused`  
  
    -   `Unfocused`  
  
 컨트롤이 예상하는 <xref:System.Windows.FrameworkElement> 개체를 지정하려면 예상되는 요소의 이름과 형식을 지정하는 <xref:System.Windows.TemplatePartAttribute>를 사용합니다.  가능한 컨트롤 상태를 지정하려면 상태의 이름 및 상태가 속해 있는 <xref:System.Windows.VisualStateGroup>을 지정하는 <xref:System.Windows.TemplateVisualStateAttribute>를 사용합니다.  컨트롤의 클래스 정의에 <xref:System.Windows.TemplatePartAttribute> 및 <xref:System.Windows.TemplateVisualStateAttribute>를 배치합니다.  
  
 컨트롤의 모양에 영향을 미치는 모든 공용 속성도 컨트롤 계약의 일부입니다.  
  
 다음 예제에서는 `NumericUpDown` 컨트롤에 대한 상태 및 <xref:System.Windows.FrameworkElement> 개체를 지정합니다.  
  
 [!code-csharp[VSMCustomControl#ControlContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
 [!code-vb[VSMCustomControl#ControlContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]  
  
<a name="complete_example"></a>   
## 완성된 예제  
 다음 예제에서는 `NumericUpDown` 컨트롤에 대한 전체 <xref:System.Windows.Controls.ControlTemplate>을 보여 줍니다.  
  
 [!code-xml[VSMCustomControl#NUDTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]  
  
 다음 예제에서는 `NumericUpDown`에 대한 논리를 보여 줍니다.  
  
 [!code-csharp[VSMCustomControl#ControlLogic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
 [!code-vb[VSMCustomControl#ControlLogic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]  
  
## 참고 항목  
 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)   
 [컨트롤 사용자 지정](../../../../docs/framework/wpf/controls/control-customization.md)