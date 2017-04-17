---
title: "ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정 | Microsoft Docs"
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
  - "컨트롤 계약[WPF]"
  - "컨트롤[WPF], 상태별로 지정된 모양"
  - "컨트롤[WPF], 표시 구조 변경 사항"
  - "ControlTemplate[WPF], 기존 컨트롤에 대해 사용자 지정"
  - "컨트롤 스킨 지정[WPF]"
  - "템플릿[WPF], 기존 컨트롤에 대해 사용자 지정"
ms.assetid: 678dd116-43a2-4b8c-82b5-6b826f126e31
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정
<a name="introduction"></a> <xref:System.Windows.Controls.ControlTemplate>은 컨트롤의 시각적 구조와 시각적 동작을 지정합니다.  새 <xref:System.Windows.Controls.ControlTemplate>을 제공하여 컨트롤의 모양을 사용자 지정할 수 있습니다.  <xref:System.Windows.Controls.ControlTemplate>을 만드는 경우 기능을 변경하지 않고 기존 컨트롤의 모양을 바꿉니다.  예를 들어 응용 프로그램의 단추를 기본 사각형 모양 대신 둥근 모양으로 만들 수 있지만 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 발생시키는 단추의 기능은 유지됩니다.  
  
 이 항목에서는 <xref:System.Windows.Controls.ControlTemplate>의 다양한 부분에 대해 설명하고, <xref:System.Windows.Controls.Button>에 대한 간단한 <xref:System.Windows.Controls.ControlTemplate>을 만드는 방법을 보여 주며, 컨트롤의 컨트롤 계약을 이해하여 모양을 사용자 지정하는 방법을 설명합니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 <xref:System.Windows.Controls.ControlTemplate>을 만들기 때문에 코드를 작성하지 않고도 컨트롤의 모양을 변경할 수 있습니다.  Microsoft Expression Blend와 같은 디자이너를 사용자 정의 컨트롤 템플릿을 만들 수도 있습니다.  이 항목에서는 <xref:System.Windows.Controls.Button>의 모양을 사용자 지정하는 데 사용되는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 예제를 보여 줍니다. 전체 예제는 항목의 끝에 있습니다.  Expression Blend 사용에 대한 자세한 내용은 [템플릿을 지원하는 컨트롤의 스타일 지정](http://go.microsoft.com/fwlink/?LinkId=161153)을 참조하십시오.  
  
 다음 그림에서는 이 항목에서 만든 <xref:System.Windows.Controls.ControlTemplate>을 사용하는 <xref:System.Windows.Controls.Button>을 보여 줍니다.  
  
 ![사용자 지정 컨트롤 템플릿이 있는 단추](../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP\_ButtonNormal")  
사용자 지정 컨트롤 템플릿을 사용하는 단추  
  
 ![빨간색 테두리가 있는 단추](../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP\_ButtonMouseOver")  
사용자 지정 컨트롤 템플릿을 사용하고 마우스 포인터가 놓여 있는 단추  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목에서는 [컨트롤](../../../../docs/framework/wpf/controls/index.md)에 설명된 대로 컨트롤과 스타일을 만들고 사용하는 방법을 알고 있다고 가정합니다.  이 항목에서 설명하는 개념은 <xref:System.Windows.Controls.Control> 클래스에서 상속된 요소\(<xref:System.Windows.Controls.UserControl> 제외\)에 적용됩니다.  <xref:System.Windows.Controls.UserControl>에는 <xref:System.Windows.Controls.ControlTemplate>을 적용할 수 없습니다.  
  
<a name="when_you_should_create_a_controltemplate"></a>   
## ControlTemplate을 만들어야 하는 경우  
 컨트롤에는 컨트롤 모양의 여러 측면을 지정하기 위해 설정할 수 있는 많은 속성\(예: <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A> 및 <xref:System.Windows.Controls.Control.FontFamily%2A>\)이 있지만 이러한 속성을 설정하여 변경할 수 있는 사항은 제한됩니다.  예를 들어, <xref:System.Windows.Controls.CheckBox>에서 <xref:System.Windows.Controls.Control.Foreground%2A> 속성을 파랑으로, <xref:System.Windows.Controls.Control.FontStyle%2A>을 기울임꼴로 설정할 수 있습니다.  
  
 컨트롤에 대한 새로운 <xref:System.Windows.Controls.ControlTemplate>을 만드는 기능이 없다면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기반 응용 프로그램에 있는 모든 컨트롤의 일반 모양이 같아서 사용자 지정 모양과 느낌을 가진 응용 프로그램을 만드는 기능이 제한될 것입니다.  기본적으로 모든 <xref:System.Windows.Controls.CheckBox>에는 유사한 특성이 있습니다.  예를 들어 <xref:System.Windows.Controls.CheckBox>의 내용은 항상 선택 표시기의 오른쪽에 있고 확인 표시는 항상 <xref:System.Windows.Controls.CheckBox>가 선택되었음을 나타내는 데 사용됩니다.  
  
 컨트롤의 다른 속성이 수행하는 설정을 초과하여 컨트롤의 모양을 사용자 지정하려는 경우 <xref:System.Windows.Controls.ControlTemplate>을 만듭니다.  <xref:System.Windows.Controls.CheckBox>의 예제에서는 확인란의 내용을 선택 표시기 위에 배치하고 X를 사용하여 <xref:System.Windows.Controls.CheckBox>가 선택되었음을 나타낸다고 가정합니다.  <xref:System.Windows.Controls.CheckBox>의 <xref:System.Windows.Controls.ControlTemplate>에서 이러한 변경 내용을 지정합니다.  
  
 다음 그림에서는 기본 <xref:System.Windows.Controls.ControlTemplate>을 사용하는 <xref:System.Windows.Controls.CheckBox>를 보여 줍니다.  
  
 ![기본 컨트롤 템플릿이 있는 확인란](../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP\_CheckBoxDefault")  
기본 컨트롤 템플릿을 사용하는 확인란  
  
 다음 그림에서는 <xref:System.Windows.Controls.ControlTemplate>을 사용하여 <xref:System.Windows.Controls.CheckBox>의 내용을 선택 표시기 위에 배치하고 <xref:System.Windows.Controls.CheckBox>가 선택될 때 X를 표시하는 <xref:System.Windows.Controls.CheckBox>를 보여 줍니다.  
  
 ![사용자 지정 컨트롤 템플릿이 있는 확인란](../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP\_CheckBoxCustom")  
사용자 지정 컨트롤 템플릿을 사용하는 확인란  
  
 이 샘플의 <xref:System.Windows.Controls.CheckBox>에 대한 <xref:System.Windows.Controls.ControlTemplate>은 비교적 복잡하므로 이 항목에서는 <xref:System.Windows.Controls.Button>에 대한 <xref:System.Windows.Controls.ControlTemplate>을 만드는 간단한 예제를 사용합니다.  
  
<a name="changing_the_visual_structure_of_a_control"></a>   
## 컨트롤의 시각적 구조 변경  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 컨트롤은 복합 <xref:System.Windows.FrameworkElement> 개체인 경우가 많습니다.  <xref:System.Windows.Controls.ControlTemplate>을 만드는 경우 <xref:System.Windows.FrameworkElement> 개체를 결합하여 단일 컨트롤을 빌드합니다.  <xref:System.Windows.Controls.ControlTemplate>은 한 개의 <xref:System.Windows.FrameworkElement>만 해당 루트 요소로 사용해야 합니다.  일반적으로 루트 요소에는 다른 <xref:System.Windows.FrameworkElement> 개체가 포함됩니다.  개체가 조합되어 컨트롤의 시각적 구조를 생성합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Button>에 대한 사용자 지정 <xref:System.Windows.Controls.ControlTemplate>을 만듭니다.  <xref:System.Windows.Controls.ControlTemplate>은 <xref:System.Windows.Controls.Button>의 시각적 구조를 만듭니다.  이 예제에서는 마우스 포인트를 단추 위로 이동하거나 단추를 클릭할 때 단추의 모양이 변경되지 않습니다.  단추가 다른 상태에 있을 때 단추의 모양을 변경하는 방법에 대해서는 이 항목의 뒷부분에서 설명합니다.  
  
 이 예제에서 시각적 구조는 다음 부분으로 구성되어 있습니다.  
  
-   템플릿의 루트 <xref:System.Windows.FrameworkElement> 역할을 하는 `RootElement`라는 <xref:System.Windows.Controls.Border>  
  
-   `RootElement`의 자식인 <xref:System.Windows.Controls.Grid>  
  
-   단추의 내용을 표시하는 <xref:System.Windows.Controls.ContentPresenter>.  <xref:System.Windows.Controls.ContentPresenter>를 사용하여 모든 개체 형식을 표시할 수 있습니다.  
  
 [!code-xml[VSMButtonTemplate#BasicTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]  
  
### TemplateBinding을 사용하여 컨트롤의 속성 기능 유지  
 새로운 <xref:System.Windows.Controls.ControlTemplate>을 만드는 경우에도 public 속성을 사용하여 컨트롤의 모양을 변경할 수 있습니다.  [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) 태그 확장은 <xref:System.Windows.Controls.ControlTemplate>에 있는 요소의 속성을 컨트롤이 정의하는 public 속성에 바인딩합니다.  [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)을 사용하면 컨트롤의 속성이 템플릿의 매개 변수로 사용됩니다.  즉, 컨트롤의 속성을 설정하면 해당 값은 [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)이 사용되는 요소로 전달됩니다.  
  
 다음 예제에서는 [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) 태그 확장을 사용하여 <xref:System.Windows.Controls.ControlTemplate>에 있는 요소의 속성을 단추가 정의하는 public 속성에 바인딩하는 이전 예제 부분을 반복합니다.  
  
 [!code-xml[VSMButtonTemplate#TemplateBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]  
  
 이 예제에서는 <xref:System.Windows.Controls.Grid>의 <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=fullName> 속성 템플릿이 <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName>에 바인딩됩니다.  <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=fullName>가 템플릿 바인딩되어 있으므로 동일한 <xref:System.Windows.Controls.ControlTemplate>을 사용하는 단추를 여러 개 만들고 각 단추의 <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName>를 서로 다른 값으로 설정할 수 있습니다.  <xref:System.Windows.Controls.ControlTemplate>에서 <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName>가 요소 속성에 템플릿 바인딩되어 있지 않으면 단추의 <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName>를 설정해도 단추의 모양에 영향을 주지 않습니다.  
  
 두 속성의 이름이 같지 않아도 됩니다.  위의 예제에서 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=fullName> 속성은 <xref:System.Windows.Controls.ContentPresenter>의 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=fullName> 속성에 바인딩되는 템플릿입니다.  따라서 단추 콘텐츠의 가로 위치를 지정할 수 있습니다.  <xref:System.Windows.Controls.ContentPresenter>에는 `HorizontalContentAlignment` 속성이 없지만 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=fullName>를 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=fullName>에 바인딩할 수 있습니다.  템플릿을 사용하여 속성을 바인딩할 경우 대상 속성과 소스 속성의 형식이 동일해야 합니다.  
  
 <xref:System.Windows.Controls.Control> 클래스는 설정 시 컨트롤 템플릿에서 사용하여 컨트롤에 영향을 줄 수 있는 일부 속성을 정의합니다.  <xref:System.Windows.Controls.ControlTemplate>에서 속성을 사용하는 방법은 속성에 따라 다릅니다.  <xref:System.Windows.Controls.ControlTemplate>은 다음 중 하나의 방법으로 이 속성을 사용해야 합니다.  
  
-   <xref:System.Windows.Controls.ControlTemplate> 템플릿의 요소가 속성에 바인딩됩니다.  
  
-   <xref:System.Windows.Controls.ControlTemplate>의 요소는 부모 <xref:System.Windows.FrameworkElement>에서 속성을 상속 받습니다.  
  
 다음 표에서는 <xref:System.Windows.Controls.Control> 클래스로부터 컨트롤이 상속하는 표시 속성을 나열합니다.  또한 컨트롤의 기본 컨트롤 템플릿에서 상속 받은 속성 값을 사용하는지 또는 템플릿 바인딩되어야 하는지를 표시합니다.  
  
|Property|사용 방법|  
|--------------|-----------|  
|<xref:System.Windows.Controls.Control.Background%2A>|템플릿 바인딩|  
|<xref:System.Windows.Controls.Control.BorderThickness%2A>|템플릿 바인딩|  
|<xref:System.Windows.Controls.Control.BorderBrush%2A>|템플릿 바인딩|  
|<xref:System.Windows.Controls.Control.FontFamily%2A>|속성 상속 또는 템플릿 바인딩|  
|<xref:System.Windows.Controls.Control.FontSize%2A>|속성 상속 또는 템플릿 바인딩|  
|<xref:System.Windows.Controls.Control.FontStretch%2A>|속성 상속 또는 템플릿 바인딩|  
|<xref:System.Windows.Controls.Control.FontWeight%2A>|속성 상속 또는 템플릿 바인딩|  
|<xref:System.Windows.Controls.Control.Foreground%2A>|속성 상속 또는 템플릿 바인딩|  
|<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>|템플릿 바인딩|  
|<xref:System.Windows.Controls.Control.Padding%2A>|템플릿 바인딩|  
|<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>|템플릿 바인딩|  
  
 이 표에서는 <xref:System.Windows.Controls.Control> 클래스로부터 상속되는 표시 속성만 나열합니다.  표에 나열된 속성 외에도 컨트롤은 부모 프레임워크 요소로부터 <xref:System.Windows.FrameworkElement.DataContext%2A>, <xref:System.Windows.FrameworkElement.Language%2A> 및 <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> 속성을 상속할 수 있습니다.  
  
 또한 <xref:System.Windows.Controls.ContentPresenter>가 <xref:System.Windows.Controls.ContentControl>의 <xref:System.Windows.Controls.ControlTemplate>에 있으면 <xref:System.Windows.Controls.ContentPresenter>가 자동으로 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 및 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성에 바인딩됩니다.  마찬가지로 <xref:System.Windows.Controls.ItemsControl>의 <xref:System.Windows.Controls.ControlTemplate>에 있는 <xref:System.Windows.Controls.ItemsPresenter>는 자동으로 <xref:System.Windows.Controls.ItemsControl.Items%2A> 및 <xref:System.Windows.Controls.ItemsPresenter> 속성에 바인딩됩니다.  
  
 다음 예제에서는 앞의 예제에서 정의된 <xref:System.Windows.Controls.ControlTemplate>을 사용하는 두 개의 단추를 만듭니다.  이 예제에서는 각 단추의 <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A> 및 <xref:System.Windows.Controls.Control.FontSize%2A> 속성을 설정합니다.  <xref:System.Windows.Controls.Control.Background%2A> 속성은 <xref:System.Windows.Controls.ControlTemplate>에서 템플릿 바인딩되어 있으므로 이 속성을 설정하면 효과가 있습니다.  <xref:System.Windows.Controls.Control.Foreground%2A> 및 <xref:System.Windows.Controls.Control.FontSize%2A> 속성은 템플릿 바인딩되어 있지 않지만 해당 값을 상속받기 때문에 속성을 설정하면 효과가 있습니다.  
  
 [!code-xml[VSMButtonTemplate#ButtonDeclaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]  
  
 앞의 예제에서는 다음 그림과 유사한 출력을 생성합니다.  
  
 ![단추 두 개: 파란색 단추 하나와 자주색 단추 하나](../../../../docs/framework/wpf/controls/media/ndp-buttontwo.png "NDP\_ButtonTwo")  
배경색이 서로 다른 두 개의 단추  
  
<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>   
## 상태에 따라 컨트롤의 모양 변경  
 기본 모양을 가진 단추와 앞의 예제에서 사용된 단추의 차이점은 기본 단추가 다른 상태에 있을 때 약간 변경된다는 것입니다.  예를 들어 단추를 누르거나 마우스 포인터가 단추 위에 있으면 기본 단추의 모양이 변경됩니다.  <xref:System.Windows.Controls.ControlTemplate>은 컨트롤의 기능을 변경하지 않고 컨트롤의 시각적 동작을 변경합니다.  시각적 동작은 컨트롤이 특정 상태에 있을 때의 컨트롤 모양을 설명합니다.  컨트롤의 기능과 시각적 동작의 차이점을 파악하려면 단추 예제를 고려해 보십시오.  단추의 기능은 단추를 클릭할 때 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 발생시키는 것이지만 단추의 시각적 동작은 단추를 가리키거나 누를 때 단추 모양을 변경하는 것입니다.  
  
 <xref:System.Windows.VisualState> 개체를 사용하여 컨트롤이 특정 상태에 있을 때 컨트롤의 모양을 지정합니다.  <xref:System.Windows.VisualState>에는 <xref:System.Windows.Controls.ControlTemplate>에 있는 요소의 모양을 변경하는 <xref:System.Windows.Media.Animation.Storyboard>가 들어 있습니다.  컨트롤의 논리에서 <xref:System.Windows.VisualStateManager>를 사용하여 상태를 변경하기 때문에 이러한 동작이 발생하도록 코드를 작성할 필요는 없습니다.  컨트롤이 <xref:System.Windows.VisualState.Name%2A?displayProperty=fullName> 속성에 지정된 상태가 되면 <xref:System.Windows.Media.Animation.Storyboard>가 시작됩니다.  컨트롤이 더 이상 해당 상태가 아니면 <xref:System.Windows.Media.Animation.Storyboard>가 중지됩니다.  
  
 다음 예제에서는 마우스 포인터가 단추 위에 있을 때 <xref:System.Windows.Controls.Button>의 모양을 변경하는 <xref:System.Windows.VisualState>를 보여 줍니다.  <xref:System.Windows.Media.Animation.Storyboard>는 `BorderBrush`의 색을 변경하여 단추의 테두리 색을 변경합니다.  이 항목의 시작 부분에 있는 <xref:System.Windows.Controls.ControlTemplate> 예제를 참조하면 `BorderBrush`가 <xref:System.Windows.Controls.Border>의 <xref:System.Windows.Controls.Border.Background%2A>에 할당된 <xref:System.Windows.Media.SolidColorBrush>의 이름이라는 것을 확인할 수 있습니다.  
  
 [!code-xml[VSMButtonTemplate#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]  
  
 이 컨트롤은 해당 컨트롤 계약의 일부로 상태를 정의합니다. 컨트롤 계약에 대해서는 이 항목의 뒷부분에 있는 [컨트롤 계약을 이해하여 다른 컨트롤 사용자 지정](#customizing_other_controls_by_understanding_the_control_contract)에서 자세히 설명합니다.  다음 표에서는 <xref:System.Windows.Controls.Button>에 대해 지정된 상태를 보여 줍니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|--------------------|-------------------------|--------|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 컨트롤 위에 있습니다.|  
|Pressed|CommonStates|컨트롤을 눌렀습니다.|  
|Disabled|CommonStates|컨트롤이 사용하지 않도록 설정되어 있습니다.|  
|Focused|FocusStates|컨트롤에 포커스가 있습니다.|  
|Unfocused|FocusStates|컨트롤에 포커스가 없습니다.|  
  
 <xref:System.Windows.Controls.Button>은 두 개의 상태 그룹을 정의합니다. `CommonStates` 그룹에는 `Normal`, `MouseOver`, `Pressed` 및 `Disabled` 상태가 포함됩니다.  `FocusStates` 그룹에는 `Focused` 및 `Unfocused` 상태가 포함됩니다.  같은 상태 그룹에 있는 상태는 함께 사용할 수 없습니다.  컨트롤은 항상 그룹당 한 개의 상태에 있습니다.  예를 들어 <xref:System.Windows.Controls.Button>은 마우스 포인터가 단추 위에 없는 경우에도 포커스가 설정될 수 있습니다. 따라서 `Focused` 상태의 <xref:System.Windows.Controls.Button>은 `MouseOver`, `Pressed`, `Normal` 상태일 수 있습니다.  
  
 <xref:System.Windows.VisualState> 개체를 <xref:System.Windows.VisualStateGroup> 개체에 추가합니다.  <xref:System.Windows.VisualStateGroup> 개체를 연결된 속성 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=fullName>에 추가합니다.  다음 예제에서는 `Normal`, `MouseOver` 및 `Pressed` 상태에 대한 <xref:System.Windows.VisualState> 개체를 정의합니다. 세 상태는 모두 `CommonStates` 그룹에 있습니다.  각 <xref:System.Windows.VisualState>의 <xref:System.Windows.VisualState.Name%2A>은 이전 표에 나오는 이름과 일치합니다.  간단한 예제를 제공하기 위해 `Disabled` 상태와 `FocusStates` 그룹의 상태는 생략되었지만 이 항목의 끝에 있는 전체 예제에는 포함되어 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Controls.ControlTemplate>의 루트 <xref:System.Windows.FrameworkElement>에는 연결된 속성 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=fullName>를 설정해야 합니다.  
  
 [!code-xml[VSMButtonTemplate#VisualStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]  
  
 앞의 예제에서는 다음 그림과 유사한 출력을 생성합니다.  
  
 ![사용자 지정 컨트롤 템플릿이 있는 단추](../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP\_ButtonNormal")  
표준 상태에서 사용자 지정 컨트롤 템플릿을 사용하는 단추  
  
 ![빨간색 테두리가 있는 단추](../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP\_ButtonMouseOver")  
마우스가 위에 있는 상태에서 사용자 지정 컨트롤 템플릿을 사용하는 단추  
  
 ![단추를 누르면 테두리가 투명해집니다.](../../../../docs/framework/wpf/controls/media/ndp-buttonpressed.png "NDP\_ButtonPressed")  
누름 상태에서 사용자 지정 컨트롤 템플릿을 사용하는 단추  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 제공되는 컨트롤의 시각적 상태를 찾으려면 [Control 스타일 및 템플릿](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)을 참조하십시오.  
  
<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>   
## 상태 전환 시 컨트롤의 동작 지정  
 위의 예제에서, 단추를 클릭하면 단추의 모양도 변경되지만 단추를 1초 동안 누르고 있지 않으면 효과가 표시되지 않습니다.  기본적으로 애니메이션이 수행되려면 1초가 걸립니다.  대체로 사용자는 이보다 짧은 시간 내에 단추를 클릭했다가 놓기 때문에 <xref:System.Windows.Controls.ControlTemplate>을 기본 상태로 유지하면 시각적 피드백이 표시되지 않습니다.  
  
 <xref:System.Windows.VisualTransition> 개체를 <xref:System.Windows.Controls.ControlTemplate>에 추가하면 컨트롤이 한 상태에서 다른 상태로 부드럽게 전환되도록 애니메이션을 수행하는 데 소요되는 시간을 지정할 수 있습니다.  <xref:System.Windows.VisualTransition>을 만드는 경우 다음 중 하나 이상을 지정합니다.  
  
-   상태가 전환되는 데 소요되는 시간  
  
-   상태 전환 시 컨트롤의 모양에 발생하는 추가 변경 내용  
  
-   <xref:System.Windows.VisualTransition>이 적용되는 상태  
  
### 전환 기간 지정  
 <xref:System.Windows.VisualTransition.GeneratedDuration%2A> 속성을 설정하여 변환에 소요되는 시간을 지정할 수 있습니다.  앞의 예제에는 단추를 누를 때 단추의 테두리가 투명하게 되도록 지정하는 <xref:System.Windows.VisualState>가 있지만 단추를 빨리 눌렀다가 놓는 경우 애니메이션이 너무 오래 걸려 표시되지 않습니다.  <xref:System.Windows.VisualTransition>을 사용하여 컨트롤이 pressed 상태로 전환되는 데 걸리는 시간을 지정할 수 있습니다.  다음 예제에서는 컨트롤이 pressed 상태로 전환되는 데 1\/100초가 걸리도록 지정합니다.  
  
 [!code-xml[VSMButtonTemplate#PressedTransition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]  
  
### 전환 중 컨트롤의 모양 변경 지정  
 <xref:System.Windows.VisualTransition>에는 컨트롤의 상태가 전환될 때 시작되는 <xref:System.Windows.Media.Animation.Storyboard>가 들어 있습니다.  예를 들어, 컨트롤이 `MouseOver` 상태에서 `Normal` 상태로 전환될 때 특정 애니메이션이 발생하도록 지정할 수 있습니다.  다음 예제에서는 사용자가 마우스 포인터를 단추에서 멀리 이동할 때 단추의 테두리가 1.5초 내에 파랑, 노랑, 검정으로 차례로 변경되도록 지정하는 <xref:System.Windows.VisualTransition>을 만듭니다.  
  
 [!code-xml[VSMButtonTemplate#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]  
  
### VisualTransition 적용 시기 지정  
 <xref:System.Windows.VisualTransition>은 특정 상태에만 적용되도록 제한될 수도 있고 컨트롤의 상태가 전환될 때마다 적용될 수도 있습니다.  앞의 예제에서 <xref:System.Windows.VisualTransition>은 컨트롤이 `MouseOver` 상태에서 `Normal` 상태로 전환될 때 적용됩니다. 그 앞의 예제에서는 컨트롤이 `Pressed` 상태가 될 때 <xref:System.Windows.VisualTransition>이 적용됩니다.  <xref:System.Windows.VisualTransition.To%2A> 및 <xref:System.Windows.VisualTransition.From%2A> 속성을 설정하여 <xref:System.Windows.VisualTransition>이 적용되는 시기를 제한합니다.  다음 표에서는 가장 제한적인 수준에서 가장 덜 제한적인 수준까지 제한 수준에 대해 설명합니다.  
  
|제한 유형|From 값|To 값|  
|-----------|------------|----------|  
|지정된 상태에서 지정된 다른 상태로 전환|<xref:System.Windows.VisualState> 이름|<xref:System.Windows.VisualState> 이름|  
|임의의 상태에서 지정된 상태로 전환|설정 안 함|<xref:System.Windows.VisualState> 이름|  
|지정된 상태에서 임의의 상태로 변환|<xref:System.Windows.VisualState> 이름|설정 안 함|  
|임의의 상태에서 임의의 다른 상태로 전환|설정 안 함|설정 안 함|  
  
 동일한 상태를 참조하는 여러 <xref:System.Windows.VisualTransition> 개체가 <xref:System.Windows.VisualStateGroup>에 있을 수 있으며, 이러한 개체는 이전 표에 나오는 순서대로 사용됩니다.  다음 예제에는 두 개의 <xref:System.Windows.VisualTransition> 개체가 있습니다.  컨트롤이 `Pressed` 상태에서 `MouseOver` 상태로 전환될 때는 <xref:System.Windows.VisualTransition.From%2A>과 <xref:System.Windows.VisualTransition.To%2A>가 모두 설정된 <xref:System.Windows.VisualTransition>이 사용됩니다.  컨트롤이 `Pressed`가 아닌 상태에서 `MouseOver` 상태로 전환될 때는 다른 상태가 사용됩니다.  
  
 [!code-xml[VSMButtonTemplate#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]  
  
 <xref:System.Windows.VisualStateGroup>에는 <xref:System.Windows.VisualStateGroup>의 <xref:System.Windows.VisualState> 개체에 적용되는 <xref:System.Windows.VisualTransition> 개체가 포함된 <xref:System.Windows.VisualStateGroup.Transitions%2A> 속성이 있습니다.  <xref:System.Windows.Controls.ControlTemplate> 작성자는 원하는 <xref:System.Windows.VisualTransition>을 모두 포함할 수 있습니다.  그러나 <xref:System.Windows.VisualTransition.To%2A> 및 <xref:System.Windows.VisualTransition.From%2A> 속성이 <xref:System.Windows.VisualStateGroup>에 없는 상태 이름으로 설정된 경우에는 <xref:System.Windows.VisualTransition>이 무시됩니다.  
  
 다음 예제에서는 `CommonStates`에 대한 <xref:System.Windows.VisualStateGroup>을 보여 줍니다.  이 예제에서는 다음과 같은 단추의 각 전환에 대해 <xref:System.Windows.VisualTransition>을 정의합니다.  
  
-   `Pressed` 상태로 전환  
  
-   `MouseOver` 상태로 전환  
  
-   `Pressed` 상태에서 `MouseOver` 상태로 전환  
  
-   `MouseOver` 상태에서 `Normal` 상태로 전환  
  
 [!code-xml[VSMButtonTemplate#VisualTransitions](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]  
  
<a name="customizing_other_controls_by_understanding_the_control_contract"></a>   
## 컨트롤 계약을 이해하여 다른 컨트롤 사용자 지정  
 <xref:System.Windows.Controls.ControlTemplate>을 사용하여 시각적 구조\(<xref:System.Windows.FrameworkElement> 개체 사용\) 및 시각적 동작\(<xref:System.Windows.VisualState> 개체 사용\)을 지정하는 컨트롤은 부분 컨트롤 모델을 사용합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4와 함께 제공되는 컨트롤은 대부분 이 모델을 사용합니다.  <xref:System.Windows.Controls.ControlTemplate> 작성자가 주의해야 하는 부분은 컨트롤 계약을 통해 통신됩니다.  컨트롤 계약의 각 부분을 이해하면 부분 컨트롤 모델을 사용하는 모든 컨트롤의 모양을 사용자 지정할 수 있습니다.  
  
 컨트롤 계약에는 다음 세 가지 요소가 있습니다.  
  
-   컨트롤 논리가 사용하는 시각적 요소  
  
-   컨트롤의 상태 및 각 상태가 속해 있는 그룹  
  
-   컨트롤에 시각적으로 영향을 미치는 public 속성  
  
### 컨트롤 계약의 시각적 요소  
 경우에 따라 컨트롤의 논리는 <xref:System.Windows.Controls.ControlTemplate>에 있는 <xref:System.Windows.FrameworkElement>와 상호 작용합니다.  예를 들어, 컨트롤에서 해당 요소 중 하나의 이벤트를 처리할 수 있습니다.  컨트롤이 <xref:System.Windows.Controls.ControlTemplate>에서 특정 <xref:System.Windows.FrameworkElement>를 찾는 경우 해당 정보를 <xref:System.Windows.Controls.ControlTemplate> 작성자에게 전달해야 합니다.  이 컨트롤은 <xref:System.Windows.TemplatePartAttribute>를 사용하여 필요한 요소의 형식과 이름을 전달합니다.  <xref:System.Windows.Controls.Button>의 컨트롤 계약에는 <xref:System.Windows.FrameworkElement> 부분이 없지만 <xref:System.Windows.Controls.ComboBox> 등의 다른 컨트롤에는 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.ComboBox> 클래스에 지정된 <xref:System.Windows.TemplatePartAttribute> 개체를 보여 줍니다.  <xref:System.Windows.Controls.ComboBox>의 논리에서는 <xref:System.Windows.Controls.ControlTemplate>에서 `PART_EditableTextBox`라는 이름의 <xref:System.Windows.Controls.TextBox>와 `PART_Popup`이라는 이름의 <xref:System.Windows.Controls.Primitives.Popup>을 찾습니다.  
  
 [!code-csharp[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.ComboBox>에 대한 단순화된 <xref:System.Windows.Controls.ControlTemplate>을 보여 줍니다. 여기에는 <xref:System.Windows.Controls.ComboBox> 클래스의 <xref:System.Windows.TemplatePartAttribute> 개체에 지정된 요소가 포함되어 있습니다.  
  
 [!code-xml[VSMButtonTemplate#ComboBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]  
  
### 컨트롤 계약의 상태  
 컨트롤의 상태도 컨트롤 계약의 일부입니다.  <xref:System.Windows.Controls.Button>에 대한 <xref:System.Windows.Controls.ControlTemplate>을 만드는 예제에서는 해당 상태에 따라 <xref:System.Windows.Controls.Button>의 모양을 지정하는 방법을 보여 줍니다.  이 항목의 앞부분에 있는 [상태에 따라 컨트롤의 모양 변경](#changing_the_appearance_of_a_control_depending_on_its_state)에서 설명된 대로 각 지정된 상태에 대해 <xref:System.Windows.VisualState>를 만들고 <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A>을 공유하는 모든 <xref:System.Windows.VisualState> 개체를 <xref:System.Windows.VisualStateGroup>에 배치합니다.  타사 컨트롤 해야 지정한 상태를 사용 하 여 해당 <xref:System.Windows.TemplateVisualStateAttribute>, Expression Blend 컨트롤 템플릿 제작에 대 한 컨트롤의 상태를 노출 시키는 것과 같은 디자이너 도구를 사용 하는.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 제공되는 컨트롤의 컨트롤 계약을 찾으려면 [Control 스타일 및 템플릿](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)을 참조하십시오.  
  
### 컨트롤 계약의 속성  
 시각적으로 컨트롤에 영향을 주는 public 속성도 컨트롤 계약에 포함됩니다.  새로운 <xref:System.Windows.Controls.ControlTemplate>을 만들지 않고 이러한 속성을 설정하여 컨트롤의 모양을 변경할 수 있습니다.  [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) 태그 확장을 사용하여 <xref:System.Windows.Controls.ControlTemplate>에 있는 요소의 속성을 <xref:System.Windows.Controls.Button>이 정의하는 public 속성에 바인딩할 수도 있습니다.  
  
 다음 예제에서는 단추의 컨트롤 계약을 보여 줍니다.  
  
 [!code-csharp[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]  
  
 <xref:System.Windows.Controls.ControlTemplate>을 만드는 경우 기존 <xref:System.Windows.Controls.ControlTemplate>에서 시작한 다음 변경하는 것이 가장 쉬운 경우가 많습니다.  다음 중 하나를 수행하여 기존 <xref:System.Windows.Controls.ControlTemplate>을 변경할 수 있습니다.  
  
-   컨트롤 템플릿을 만들기 위한 그래픽 사용자 인터페이스를 제공하는 Expression Blend 등의 디자이너를 사용합니다.  자세한 내용은 [템플릿을 지원하는 컨트롤의 스타일 지정](http://go.microsoft.com/fwlink/?LinkId=161153)을 참조하십시오.  
  
-   기본 <xref:System.Windows.Controls.ControlTemplate>을 가져와서 편집합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 제공되는 기본 컨트롤 템플릿을 찾으려면 [Default WPF Themes](http://go.microsoft.com/fwlink/?LinkID=158252)를 참조하십시오.  
  
<a name="complete_example"></a>   
## 완성된 예제  
 다음 예제에서는 이 항목에서 설명한 전체 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.ControlTemplate>을 보여 줍니다.  
  
 [!code-xml[VSMButtonTemplate#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]  
  
## 참고 항목  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)