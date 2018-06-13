---
title: ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.assetid: 678dd116-43a2-4b8c-82b5-6b826f126e31
ms.openlocfilehash: bbdc79fabf8dbe344baae66d718d79ac6375db7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558059"
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정
<a name="introduction"></a> A <xref:System.Windows.Controls.ControlTemplate> 시각적 구조와 컨트롤의 시각적 동작을 지정 합니다. 새 제공 하 여 컨트롤의 모양을 사용자 지정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate>합니다. 만들 때 한 <xref:System.Windows.Controls.ControlTemplate>, 기능을 변경 하지 않고 기존 컨트롤의 모양을 바꿉니다. 예를 들어 만들 수 있는 단추 응용 프로그램에서 기본 정사각형 대신 라운드 있지만 단추에서 여전히 발생는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트입니다.  
  
 이 항목의 다양 한 부분에 설명는 <xref:System.Windows.Controls.ControlTemplate>을 만드는 간단한 방법을 보여 줍니다 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Button>, 모양을 사용자 지정할 수 있도록 컨트롤의 컨트롤 계약을 이해 하는 방법에 설명 합니다. 만들 수 있으므로 한 <xref:System.Windows.Controls.ControlTemplate> 에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 코드를 작성 하지 않고 컨트롤의 모양을 변경할 수 있습니다. Microsoft Expression Blend와 같은 디자이너를 사용하여 사용자 지정 컨트롤 템플릿을 만들 수도 있습니다. 이 항목의 예를 보여 줍니다.는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 의 모양을 사용자 지정 하는 <xref:System.Windows.Controls.Button> 하 고이 항목의 끝에 전체 예제를 나열 합니다. Expression Blend 사용에 대한 자세한 내용은 [템플릿을 지원하는 컨트롤의 스타일 지정](http://go.microsoft.com/fwlink/?LinkId=161153)을 참조하세요.  
  
 다음 그림에 나온은 <xref:System.Windows.Controls.Button> 를 사용 하는 <xref:System.Windows.Controls.ControlTemplate> 이 항목에서 만들어집니다.  
  
 ![사용자 지정 컨트롤 템플릿 사용 하 여는 단추입니다. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP_ButtonNormal")  
사용자 지정 컨트롤 템플릿을 사용하는 단추  
  
 ![빨간색 테두리가 있는 단추입니다. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
사용자 지정 컨트롤 템플릿을 사용하고 마우스 포인터가 위에 놓여 있는 단추  
  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>전제 조건  
 이 항목에서는 [컨트롤](../../../../docs/framework/wpf/controls/index.md)에 설명된 대로 컨트롤과 스타일을 만들고 사용하는 방법을 알고 있다고 가정합니다. 이 항목에 설명 된 개념에서 상속 하는 요소에 적용 된 <xref:System.Windows.Controls.Control> 클래스를 제외 하 고는 <xref:System.Windows.Controls.UserControl>합니다. 적용할 수 없습니다는 <xref:System.Windows.Controls.ControlTemplate> 에 <xref:System.Windows.Controls.UserControl>합니다.  
  
<a name="when_you_should_create_a_controltemplate"></a>   
## <a name="when-you-should-create-a-controltemplate"></a>ControlTemplate을 만들어야 하는 경우  
 와 같은 컨트롤의 속성은 <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, 및 <xref:System.Windows.Controls.Control.FontFamily%2A>, 컨트롤의 모양의 다양 한 측면을 지정 하도록 설정할 수 있지만 이러한 속성을 설정 하 여 만들 수 있는 변경 내용을 제한 됩니다. 예를 들어, 설정할 수는 <xref:System.Windows.Controls.Control.Foreground%2A> 속성을 파랑 및 <xref:System.Windows.Controls.Control.FontStyle%2A> 을 기울임꼴로에 <xref:System.Windows.Controls.CheckBox>합니다.  
  
 새 수 없다면 <xref:System.Windows.Controls.ControlTemplate> 컨트롤에 대 한 모든 컨트롤의 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반된 응용 프로그램은 모양이 동일한 일반, 사용자 지정 된 모양과 느낌을 사용 하 여 응용 프로그램을 만들려면 기능 제한 될 것입니다. 기본적으로 모든 <xref:System.Windows.Controls.CheckBox> 비슷한 특징이 있습니다. 예를 들어의 콘텐츠는 <xref:System.Windows.Controls.CheckBox> 선택 표시기의 오른쪽에는 항상 고 확인 표시를 나타내기 위해 항상 사용 됩니다는 <xref:System.Windows.Controls.CheckBox> 을 선택 합니다.  
  
 만들는 <xref:System.Windows.Controls.ControlTemplate> 어떤 속성을 설정 다른 컨트롤에 처리 해 초과 컨트롤의 모양을 사용자 지정 하려는 경우. 예제에서는 <xref:System.Windows.Controls.CheckBox>, 확인란 선택 표시기 보다 앞으로 콘텐츠는 설정할 수 및 해당 x는 <xref:System.Windows.Controls.CheckBox> 을 선택 합니다. 이러한 변경에 지정 된 <xref:System.Windows.Controls.ControlTemplate> 의 <xref:System.Windows.Controls.CheckBox>합니다.  
  
 다음 그림에서는 한 <xref:System.Windows.Controls.CheckBox> 하는 기본 <xref:System.Windows.Controls.ControlTemplate>합니다.  
  
 ![기본 컨트롤 템플릿이 있는 확인란을 선택 합니다. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
기본 컨트롤 템플릿을 사용하는 확인란  
  
 다음 그림에서는 <xref:System.Windows.Controls.CheckBox> 사용자 지정을 사용 하 여 <xref:System.Windows.Controls.ControlTemplate> 의 콘텐츠를 배치 하는 <xref:System.Windows.Controls.CheckBox> 위에서 X 표시 및 선택 표시기 때는 <xref:System.Windows.Controls.CheckBox> 을 선택 합니다.  
  
 ![사용자 지정 컨트롤 템플릿이 있는 확인란을 선택 합니다. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
사용자 지정 컨트롤 템플릿을 사용하는 확인란  
  
 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.CheckBox> 이 샘플은 상대적으로 복잡 한 이므로이 항목을 만드는 간단한 예제를 사용 하 여 한 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Button>합니다.  
  
<a name="changing_the_visual_structure_of_a_control"></a>   
## <a name="changing-the-visual-structure-of-a-control"></a>컨트롤의 시각적 구조 변경  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 컨트롤은 복합 종종 <xref:System.Windows.FrameworkElement> 개체입니다. 만들 때 한 <xref:System.Windows.Controls.ControlTemplate>를 결합 하면 <xref:System.Windows.FrameworkElement> 단일 컨트롤을 작성 하는 개체입니다. A <xref:System.Windows.Controls.ControlTemplate> 하나만 있어야 <xref:System.Windows.FrameworkElement> 루트 요소로 서입니다. 루트 요소는 일반적으로 다른 포함 <xref:System.Windows.FrameworkElement> 개체입니다. 개체가 조합되면 컨트롤의 시각적 구조가 만들어집니다.  
  
 다음 예제에서는 사용자 지정 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Button>합니다. <xref:System.Windows.Controls.ControlTemplate> 의 시각적 구조 만듭니다는 <xref:System.Windows.Controls.Button>합니다. 이 예제에서는 마우스 포인트를 단추 위로 이동하거나 단추를 클릭할 때 단추의 모양이 변경되지 않습니다. 단추가 다른 상태에 있을 때 단추의 모양을 변경하는 방법에 대해서는 이 항목의 뒷부분에서 설명합니다.  
  
 이 예제에서 시각적 구조는 다음 부분으로 구성되어 있습니다.  
  
-   A <xref:System.Windows.Controls.Border> 라는 `RootElement` 서식 파일의 루트 스페이스로 <xref:System.Windows.FrameworkElement>합니다.  
  
-   A <xref:System.Windows.Controls.Grid> 의 자식인 `RootElement`합니다.  
  
-   A <xref:System.Windows.Controls.ContentPresenter> 단추의 콘텐츠를 표시 하는입니다. <xref:System.Windows.Controls.ContentPresenter> 모든 종류의 개체 표시 될 수 있습니다.  
  
 [!code-xaml[VSMButtonTemplate#BasicTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]  
  
### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>TemplateBinding을 사용하여 컨트롤의 속성 기능 유지  
 만들 새 <xref:System.Windows.Controls.ControlTemplate>, 여전히 하려는 공용 속성을 사용 하 여 컨트롤의 모양을 변경 합니다. [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) 태그 확장에 있는 요소의 속성을 바인딩하는 <xref:System.Windows.Controls.ControlTemplate> 컨트롤에 의해 정의 된 public 속성을 합니다. [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)을 사용하면 컨트롤의 속성이 템플릿의 매개 변수로 작동됩니다. 즉, 컨트롤의 속성을 설정하면 해당 값은 [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)이 있는 요소로 전달됩니다.  
  
 사용 하 여 앞의 예제의 일부를 반복 하는 다음 예제는 [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) 태그 확장에 있는 요소의 속성을 바인딩하는 <xref:System.Windows.Controls.ControlTemplate> 단추에 정의 된 public 속성을 합니다.  
  
 [!code-xaml[VSMButtonTemplate#TemplateBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]  
  
 이 예제는 <xref:System.Windows.Controls.Grid> 가 해당 <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> 속성 서식 파일에 바인딩된 <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>합니다. 때문에 <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> 은 바인딩된 서식 파일을 동일한 것을 사용 하는 여러 단추를 만들 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 설정 하 고는 <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> 각 단추에 대해 서로 다른 값으로. 경우 <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> 하지 서식 파일에 있는 요소의 속성에 바인딩된는 <xref:System.Windows.Controls.ControlTemplate>설정는 <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> 단추의 모양에 영향을 미치지 것을 단추입니다.  
  
 두 속성의 이름이 같지 않아도 됩니다. 앞의 예제에는 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> 속성은 <xref:System.Windows.Controls.Button> 서식 파일에 바인딩된는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType> 속성의는 <xref:System.Windows.Controls.ContentPresenter>합니다. 이를 통해 단추 콘텐츠의 가로 위치를 지정할 수 있습니다. <xref:System.Windows.Controls.ContentPresenter> 명명 된 속성이 없는 `HorizontalContentAlignment`, 하지만 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> 에 바인딩될 수 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>합니다. 속성을 템플릿 바인딩할 경우 대상 속성과 소스 속성의 형식이 동일해야 합니다.  
  
 <xref:System.Windows.Controls.Control> 클래스 설정 하는 경우 컨트롤에 적용 하려면 컨트롤 템플릿을 사용 해야 하는 몇 가지 속성을 정의 합니다. 방법을 <xref:System.Windows.Controls.ControlTemplate> 사용 하 여가 속성은 속성에 따라 달라 집니다. <xref:System.Windows.Controls.ControlTemplate> 다음 방법 중 하나에서 속성을 사용 해야 합니다.  
  
-   요소는 <xref:System.Windows.Controls.ControlTemplate> 템플릿 속성에 바인딩됩니다.  
  
-   요소는 <xref:System.Windows.Controls.ControlTemplate> 부모 사이트에서 속성을 상속 <xref:System.Windows.FrameworkElement>합니다.  
  
 다음 표에서 시각적 속성에서 컨트롤에 상속 된 <xref:System.Windows.Controls.Control> 클래스입니다. 또한 컨트롤의 기본 컨트롤 템플릿이 상속받은 속성 값을 사용하는지 또는 템플릿 바인딩되어야 하는지를 나타냅니다.  
  
|속성|사용 방법|  
|--------------|------------------|  
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
  
 테이블에서 상속 되며, visual 속성만 나열 된 <xref:System.Windows.Controls.Control> 클래스입니다. 테이블에 나열 된 속성 외에도 컨트롤을 상속할 수 있습니다는 <xref:System.Windows.FrameworkElement.DataContext%2A>, <xref:System.Windows.FrameworkElement.Language%2A>, 및 <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> 부모 프레임 워크 요소의 속성입니다.  
  
 또한 경우는 <xref:System.Windows.Controls.ContentPresenter> 에 <xref:System.Windows.Controls.ControlTemplate> 의 <xref:System.Windows.Controls.ContentControl>, <xref:System.Windows.Controls.ContentPresenter> 를 자동으로 바인딩할는 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 및 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성입니다. 마찬가지로, 한 <xref:System.Windows.Controls.ItemsPresenter> 에 <xref:System.Windows.Controls.ControlTemplate> 의 <xref:System.Windows.Controls.ItemsControl> 를 자동으로 바인딩할는 <xref:System.Windows.Controls.ItemsControl.Items%2A> 및 <xref:System.Windows.Controls.ItemsPresenter> 속성입니다.  
  
 다음 예제에서는 사용 하는 두 개의 단추는 <xref:System.Windows.Controls.ControlTemplate> 앞의 예제에 정의 합니다. 예제에서는 <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, 및 <xref:System.Windows.Controls.Control.FontSize%2A> 각 단추에 대해 속성입니다. 설정의 <xref:System.Windows.Controls.Control.Background%2A> 속성은 템플릿에 바인딩되어 있기 때문에 적용 된 <xref:System.Windows.Controls.ControlTemplate>합니다. 경우에는 <xref:System.Windows.Controls.Control.Foreground%2A> 및 <xref:System.Windows.Controls.Control.FontSize%2A> 속성은 템플릿 바인딩되어 있지, 해당 값을 상속 하기 때문에 설정 해도 효과가 합니다.  
  
 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]  
  
 앞의 예제에서는 다음 그림과 유사한 출력을 생성합니다.  
  
 ![두 개의 단추, 하나의 파란색 단추 하 나와 자주색 합니다. ] (../../../../docs/framework/wpf/controls/media/ndp-buttontwo.png "NDP_ButtonTwo")  
배경색이 서로 다른 두 개의 단추  
  
<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>   
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>상태에 따라 컨트롤의 모양 변경  
 기본 모양을 가진 단추와 앞의 예제에서 사용된 단추의 차이점은 기본 단추가 다른 상태에 있을 때 약간 변경된다는 것입니다. 예를 들어 단추를 누르거나 마우스 포인터가 단추 위에 있으면 기본 단추의 모양이 변경됩니다. 하지만 <xref:System.Windows.Controls.ControlTemplate> 기능을 변경 하지 않는 컨트롤의 컨트롤의 시각적 동작 변경지 않습니다. 시각적 동작은 컨트롤이 특정 상태에 있을 때의 컨트롤 모양을 설명합니다. 컨트롤의 기능과 시각적 동작의 차이점을 파악하려면 단추 예제를 참조하세요. 단추의 기능은 시키려면는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 클릭할 이지만 단추의 시각적 동작 가리키는 또는 누를 때 모양을 변경 하는 이벤트입니다.  
  
 사용 하면 <xref:System.Windows.VisualState> 특정 상태에 있을 때 컨트롤의 모양을 지정 하는 개체입니다. A <xref:System.Windows.VisualState> 포함 한 <xref:System.Windows.Media.Animation.Storyboard> 에 있는 요소의 모양을 변경 하는 <xref:System.Windows.Controls.ControlTemplate>합니다. 컨트롤의 논리를 사용 하 여 상태 변경 되기 때문에 발생 합니다.이 코드를 작성할 필요가 없습니다는 <xref:System.Windows.VisualStateManager>합니다. 컨트롤에 지정 된 상태로 전환 하는 경우는 <xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType> 속성에는 <xref:System.Windows.Media.Animation.Storyboard> 시작 합니다. 컨트롤의 상태가 종료 하는 경우는 <xref:System.Windows.Media.Animation.Storyboard> 중지 합니다.  
  
 다음 예제와 <xref:System.Windows.VisualState> 의 모양을 변경 하는 <xref:System.Windows.Controls.Button> 위로 마우스 포인터의 경우. <xref:System.Windows.Media.Animation.Storyboard> 단추의 테두리 색 색을 변경 하 여 변경 된 `BorderBrush`합니다. 참조 하는 경우는 <xref:System.Windows.Controls.ControlTemplate> 예제에서는이 항목의 시작 부분에 있습니다 이라는 것을 `BorderBrush` 의 이름인는 <xref:System.Windows.Media.SolidColorBrush> 에 할당 된는 <xref:System.Windows.Controls.Border.Background%2A> 의 <xref:System.Windows.Controls.Border>합니다.  
  
 [!code-xaml[VSMButtonTemplate#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]  
  
 이 컨트롤을 통해 해당 컨트롤 계약의 일부로 상태를 정의합니다. 컨트롤 계약에 대해서는 이 항목의 뒷부분에 있는 [컨트롤 계약을 이해하여 다른 컨트롤 사용자 지정](#customizing_other_controls_by_understanding_the_control_contract)에서 자세히 설명합니다. 다음 표에서에 지정 된 상태를 나열는 <xref:System.Windows.Controls.Button>합니다.  
  
|VisualState 이름|VisualStateGroup 이름|설명|  
|----------------------|---------------------------|-----------------|  
|보통|CommonStates|기본 상태입니다.|  
|MouseOver|CommonStates|마우스 포인터가 컨트롤 위에 있습니다.|  
|누름|CommonStates|컨트롤을 눌렀습니다.|  
|사용 안 함|CommonStates|컨트롤이 비활성화되었습니다.|  
|포커스 있음|FocusStates|컨트롤에 포커스가 있습니다.|  
|포커스 없음|FocusStates|컨트롤에 포커스가 없습니다.|  
  
 <xref:System.Windows.Controls.Button> 두 상태 그룹을 정의:는 `CommonStates` 그룹에 포함 된 `Normal`, `MouseOver`, `Pressed`, 및 `Disabled` 상태입니다. `FocusStates` 그룹에는 `Focused` 및 `Unfocused` 상태가 포함됩니다. 같은 상태 그룹에 있는 상태는 함께 사용할 수 없습니다. 컨트롤은 항상 그룹마다 한 개의 상태에 있습니다. 예를 들어 한 <xref:System.Windows.Controls.Button> 마우스 포인터는 초과 아니며, 따라서 경우에 포커스를 가질 수는 <xref:System.Windows.Controls.Button> 에 `Focused` 상태가 될 수 있습니다는 `MouseOver`, `Pressed`, 또는 `Normal` 상태입니다.  
  
 추가한 <xref:System.Windows.VisualState> 개체를 <xref:System.Windows.VisualStateGroup> 개체입니다. 추가한 <xref:System.Windows.VisualStateGroup> 개체는 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> 연결 된 속성입니다. 다음 예제에서는 정의 <xref:System.Windows.VisualState> 에 대 한 개체는 `Normal`, `MouseOver`, 및 `Pressed` 모두에 있는 상태가 `CommonStates` 그룹입니다. <xref:System.Windows.VisualState.Name%2A> 각 <xref:System.Windows.VisualState> 이전 테이블의 이름과 일치 합니다. 간단한 예제를 제공하기 위해 `Disabled` 상태와 `FocusStates` 그룹의 상태는 생략되었지만 이 항목의 끝에 있는 전체 예제에는 포함되어 있습니다.  
  
> [!NOTE]
>  로 설정 된 <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> 루트에 연결 <xref:System.Windows.FrameworkElement> 의 <xref:System.Windows.Controls.ControlTemplate>합니다.  
  
 [!code-xaml[VSMButtonTemplate#VisualStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]  
  
 앞의 예제에서는 다음 그림과 유사한 출력을 생성합니다.  
  
 ![사용자 지정 컨트롤 템플릿 사용 하 여는 단추입니다. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP_ButtonNormal")  
정상 상태에서 사용자 지정 컨트롤 템플릿을 사용하는 단추  
  
 ![빨간색 테두리가 있는 단추입니다. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
마우스가 위에 있는 상태에서 사용자 지정 컨트롤 템플릿을 사용하는 단추  
  
 ![테두리는 눌린된 단추에 투명 합니다. ] (../../../../docs/framework/wpf/controls/media/ndp-buttonpressed.png "NDP_ButtonPressed")  
누름 상태에서 사용자 지정 컨트롤 템플릿을 사용하는 단추  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 제공된 컨트롤의 시각적 상태를 찾으려면 [Control 스타일 및 템플릿](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)을 참조하세요.  
  
<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>   
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>상태 간 전환 시 컨트롤의 동작 지정  
 위의 예제에서 단추를 클릭하면 모양도 변경되지만 단추를 1초 동안 누르고 있지 않으면 효과가 표시되지 않습니다. 기본적으로 애니메이션은 적용되려면 1초가 걸립니다. 시각적 피드백 유지 될 사용자가 클릭 하 고 훨씬 짧은 시간 내에 있는 단추를 놓을 가능성이 있으므로 <xref:System.Windows.Controls.ControlTemplate> 기본 상태에 있습니다.  
  
 애니메이션 추가 하 여 한 상태에서 다른 컨트롤을 부드럽게 전환 하는 데 걸리는 시간을 지정할 수 있습니다 <xref:System.Windows.VisualTransition> 개체는 <xref:System.Windows.Controls.ControlTemplate>합니다. 만들 때 한 <xref:System.Windows.VisualTransition>, 다음 중 하나 이상을 지정 합니다.  
  
-   적용할 상태 간에 전환되는 데 소요되는 시간  
  
-   컨트롤의 모양에 전환 시 적용되는 추가 변경 내용  
  
-   상태를 확인할는 <xref:System.Windows.VisualTransition> 에 적용 됩니다.  
  
### <a name="specifying-the-duration-of-a-transition"></a>전환 기간 지정  
 전환의 소요 시간을 설정 하 여 지정할 수는 <xref:System.Windows.VisualTransition.GeneratedDuration%2A> 속성입니다. 위의 예제에는 <xref:System.Windows.VisualState> 애니메이션 시간이 너무 길어진 경우 단추를 신속 하 게 눌렀다 두드러질 수 있지만 단추를 누를 때 단추의 테두리가 투명해 집니다를 지정 하는 합니다. 사용할 수는 <xref:System.Windows.VisualTransition> 시간을 지정 하는 컨트롤 하는 데 걸리는 눌린 상태로 전환 합니다. 다음 예제에서는 컨트롤이 누른 상태로 전환되는 데 1/100초가 걸리도록 지정합니다.  
  
 [!code-xaml[VSMButtonTemplate#PressedTransition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]  
  
### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>전환 중 컨트롤의 모양 변경 지정  
 <xref:System.Windows.VisualTransition> 포함 한 <xref:System.Windows.Media.Animation.Storyboard> 컨트롤 상태 간의 전환 될 때 시작 하 합니다. 예를 들어 컨트롤이 `MouseOver` 상태에서 `Normal` 상태로 전환될 때 특정 애니메이션이 적용되도록 지정할 수 있습니다. 다음 예제에서는 한 <xref:System.Windows.VisualTransition> 하는 변경 되도록 지정 하를 단추에서 마우스 포인터를 이동할 때 단추의 테두리에 파랑, 노랑,을 차례로 검정색으로 (1.5 초)입니다.  
  
 [!code-xaml[VSMButtonTemplate#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]  
  
### <a name="specifying-when-a-visualtransition-is-applied"></a>VisualTransition 적용 시기 지정  
 A <xref:System.Windows.VisualTransition> 특정 상태에 적용 하도록 제한할 수 또는 적용할 수 있습니다 언제 든 지 상태 간의 컨트롤 전환 합니다. 앞의 예제에서는 <xref:System.Windows.VisualTransition> 컨트롤에서 발생 하는 경우 적용 되는 `MouseOver` 상태는 `Normal` 상태 그 이전에 예제에서는 <xref:System.Windows.VisualTransition> 컨트롤에 바뀔 때 적용 되는 `Pressed` 상태입니다. 시간을 제한할는 <xref:System.Windows.VisualTransition> 설정 하 여 적용 되는 <xref:System.Windows.VisualTransition.To%2A> 및 <xref:System.Windows.VisualTransition.From%2A> 속성입니다. 다음 표에서는 최대한의 제한에서 최소한의 제한까지 제한 수준에 대해 설명합니다.  
  
|제한 유형|From 값|To 값|  
|-------------------------|-------------------|-----------------|  
|지정된 상태에서 지정된 다른 상태로 전환|이름을 <xref:System.Windows.VisualState>|이름을 <xref:System.Windows.VisualState>|  
|임의의 상태에서 지정된 상태로 전환|설정 안 함|이름을 <xref:System.Windows.VisualState>|  
|지정된 상태에서 임의의 상태로 전환|이름을 <xref:System.Windows.VisualState>|설정 안 함|  
|임의의 상태에서 임의의 다른 상태로 전환|설정 안 함|설정 안 함|  
  
 여러 개 있을 수 <xref:System.Windows.VisualTransition> 개체에 <xref:System.Windows.VisualStateGroup> 동일한 상태를 참조 하는 없지만 이전 표에서 지정 된 순서로 사용할 됩니다. 다음 예제에서는 두 개의 <xref:System.Windows.VisualTransition> 개체입니다. 컨트롤에서 전환 하는 경우는 `Pressed` 상태는 `MouseOver` 상태는 <xref:System.Windows.VisualTransition> 가 모두 <xref:System.Windows.VisualTransition.From%2A> 및 <xref:System.Windows.VisualTransition.To%2A> 집합이 사용 됩니다. 컨트롤이 `Pressed`가 아닌 상태에서 `MouseOver` 상태로 전환될 때는 다른 상태가 사용됩니다.  
  
 [!code-xaml[VSMButtonTemplate#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]  
  
 <xref:System.Windows.VisualStateGroup> 에 <xref:System.Windows.VisualStateGroup.Transitions%2A> 포함 된 속성의 <xref:System.Windows.VisualTransition> 개체에 적용 되는 <xref:System.Windows.VisualState> 개체에 <xref:System.Windows.VisualStateGroup>합니다. 로 <xref:System.Windows.Controls.ControlTemplate> 작성자는 모두 포함할 수 <xref:System.Windows.VisualTransition> 원하는 합니다. 그러나 경우는 <xref:System.Windows.VisualTransition.To%2A> 및 <xref:System.Windows.VisualTransition.From%2A> 속성에 포함 되지 않은 상태 이름으로 설정 됩니다는 <xref:System.Windows.VisualStateGroup>, <xref:System.Windows.VisualTransition> 는 무시 됩니다.  
  
 다음 예제와 <xref:System.Windows.VisualStateGroup> 에 대 한는 `CommonStates`합니다. 이 예제에서는 정의 <xref:System.Windows.VisualTransition> 단추의 다음의 각 전환에 대 한 합니다.  
  
-   `Pressed` 상태로 전환  
  
-   `MouseOver` 상태로 전환  
  
-   `Pressed` 상태에서 `MouseOver` 상태로 전환  
  
-   `MouseOver` 상태에서 `Normal` 상태로 전환  
  
 [!code-xaml[VSMButtonTemplate#VisualTransitions](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]  
  
<a name="customizing_other_controls_by_understanding_the_control_contract"></a>   
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>컨트롤 계약을 이해하여 다른 컨트롤 사용자 지정  
 사용 하는 컨트롤은 <xref:System.Windows.Controls.ControlTemplate> 시각적 구조를 지정 하려면 (사용 하 여 <xref:System.Windows.FrameworkElement> 개체) 및 시각적 동작 (사용 하 여 <xref:System.Windows.VisualState> 개체) 부분 컨트롤 모델을 사용 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4와 함께 제공되는 많은 컨트롤이 이 모델을 사용합니다. 부분 하는 <xref:System.Windows.Controls.ControlTemplate> 에 주의 해야 하는 작성자 컨트롤 계약을 통해 전달 됩니다. 컨트롤 계약의 파트를 이해하면 파트 컨트롤 모델을 사용하는 모든 컨트롤의 모양을 사용자 지정할 수 있습니다.  
  
 컨트롤 계약에는 세 가지 요소가 있습니다.  
  
-   컨트롤 논리가 사용하는 시각적 요소  
  
-   컨트롤의 상태 및 각 상태가 속해 있는 그룹  
  
-   컨트롤에 시각적으로 영향을 미치는 공용 속성  
  
### <a name="visual-elements-in-the-control-contract"></a>컨트롤 계약의 시각적 요소  
 컨트롤의 논리와 상호 작용 하는 경우에 따라 한 <xref:System.Windows.FrameworkElement> 에 <xref:System.Windows.Controls.ControlTemplate>합니다. 예를 들어 컨트롤에서 해당 요소 중 하나의 이벤트를 처리할 수 있습니다. 컨트롤이 특정을 찾으려고 시도 하는 경우 <xref:System.Windows.FrameworkElement> 에 <xref:System.Windows.Controls.ControlTemplate>, 게 해당 정보를 전달 해야는 <xref:System.Windows.Controls.ControlTemplate> 작성자입니다. 컨트롤이 사용 하는 <xref:System.Windows.TemplatePartAttribute> 유형 예상 되는 요소 및 해야 하는 요소의 이름을 전달 하는 데 있습니다. <xref:System.Windows.Controls.Button> 없는 <xref:System.Windows.FrameworkElement> 와 같은 파트의 제어 계약 하지만 다른 컨트롤에는 <xref:System.Windows.Controls.ComboBox>, 않습니다.  
  
 다음 예제와 <xref:System.Windows.TemplatePartAttribute> 에 지정 된 개체는 <xref:System.Windows.Controls.ComboBox> 클래스입니다. 논리 <xref:System.Windows.Controls.ComboBox> 를 찾으려고 시도 <xref:System.Windows.Controls.TextBox> 라는 `PART_EditableTextBox` 및 <xref:System.Windows.Controls.Primitives.Popup> 라는 `PART_Popup` 에 해당 <xref:System.Windows.Controls.ControlTemplate>합니다.  
  
 [!code-csharp[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]  
  
 다음 예제에서는 간단해 진 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ComboBox> 변수로 지정 된 요소를 포함 하는 <xref:System.Windows.TemplatePartAttribute> 에 있는 개체는 <xref:System.Windows.Controls.ComboBox> 클래스입니다.  
  
 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]  
  
### <a name="states-in-the-control-contract"></a>컨트롤 계약의 상태  
 컨트롤의 상태도 컨트롤 계약의 파트입니다. 만드는 예는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Button> 의 모양을 지정 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.Button> 해당 상태에 따라 합니다. 만들는 <xref:System.Windows.VisualState> 각 상태를 지정 하 고 모든 배치에 대 한 <xref:System.Windows.VisualState> 공유 하는 개체는 <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> 에 <xref:System.Windows.VisualStateGroup>에 설명 된 대로 [상태에 따라 컨트롤의 모양 변경](#changing_the_appearance_of_a_control_depending_on_its_state) 이 이전 항목입니다. 사용 하 여 타사 컨트롤 상태를 지정 해야는 <xref:System.Windows.TemplateVisualStateAttribute>, 컨트롤 템플릿을 작성 하는 것에 대 한 컨트롤의 상태를 노출 하려면 Expression Blend와 같은 디자이너 도구를 할 수 있게 합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 제공되는 컨트롤의 컨트롤 계약을 찾으려면 [Control 스타일 및 템플릿](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)을 참조하세요.  
  
### <a name="properties-in-the-control-contract"></a>컨트롤 계약의 속성  
 시각적으로 컨트롤에 영향을 주는 공용 속성도 컨트롤 계약에 포함됩니다. 새 만들지 않고 컨트롤의 모양을 변경 하려면 이러한 속성을 설정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate>합니다. 사용할 수도 있습니다는 [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) 태그 확장에 있는 요소의 속성을 바인딩하는 <xref:System.Windows.Controls.ControlTemplate> 에 정의 된 공용 속성에는 <xref:System.Windows.Controls.Button>합니다.  
  
 다음 예제에서는 단추의 컨트롤 계약을 보여 줍니다.  
  
 [!code-csharp[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]  
  
 만들 때 한 <xref:System.Windows.Controls.ControlTemplate>, 기존로 시작 하는 것이 더 편리 방식은 <xref:System.Windows.Controls.ControlTemplate> 변경 합니다. 기존 변경 하려면 다음 중 하나를 수행 <xref:System.Windows.Controls.ControlTemplate>:  
  
-   컨트롤 템플릿을 만들기 위한 그래픽 사용자 인터페이스를 제공하는 Expression Blend 등의 디자이너를 사용합니다. 자세한 내용은 [템플릿을 지원하는 컨트롤의 스타일 지정](http://go.microsoft.com/fwlink/?LinkId=161153)을 참조하세요.  
  
-   기본 가져오기 <xref:System.Windows.Controls.ControlTemplate> 하 고 편집 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 함께 제공되는 기본 컨트롤 템플릿을 찾으려면 [기본 WPF 테마](http://go.microsoft.com/fwlink/?LinkID=158252)를 참조하세요.  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>완성된 예제  
 다음 예에서는 전체 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.ControlTemplate> 이 항목에서 설명 하 합니다.  
  
 [!code-xaml[VSMButtonTemplate#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]  
  
## <a name="see-also"></a>참고 항목  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)
