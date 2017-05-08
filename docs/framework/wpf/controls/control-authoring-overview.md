---
title: "컨트롤 제작 개요 | Microsoft Docs"
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
  - "컨트롤 제작 개요"
  - "컨트롤, 제작 개요"
ms.assetid: 3d864748-cff0-4e63-9b23-d8e5a635b28f
caps.latest.revision: 32
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# 컨트롤 제작 개요
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 컨트롤 모델은 확장성이 뛰어나기 때문에 새로운 컨트롤을 만들 필요가 거의 없습니다.  하지만 그래도 사용자 지정 컨트롤을 만들어야 하는 경우가 있습니다.  이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 다양한 컨트롤 제작 모델과 사용자 지정 컨트롤을 만들어야 하는 필요성을 최소화하는 기능에 대해 설명합니다.  또한 새 컨트롤을 만드는 방법을 보여 줍니다.  
  
   
  
<a name="when_to_write_a_new_control"></a>   
## 새 컨트롤 작성에 대한 대안  
 과거에는 컨트롤을 사용자 지정하려는 경우 컨트롤의 배경색, 테두리 굵기, 글꼴 크기 등의 표준 속성을 변경하는 것만 가능했습니다.  컨트롤의 모양이나 동작을 미리 정의된 이 매개 변수 이상으로 확장하려면 일반적으로 컨트롤 그리기를 담당하는 메서드를 기존 컨트롤에서 상속하여 재정의하는 방법으로 새 컨트롤을 만들어야 했습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 이 방법도 가능하지만 풍부한 콘텐츠 모델, 스타일, 템플릿 및 트리거를 사용하여 기존 컨트롤을 사용자 지정할 수 있습니다.  다음에는 새 컨트롤을 만들지 않고도 이러한 기능을 통해 요구 사항에 맞으면서 일관성 있는 환경을 만드는 방법에 대한 예가 나와 있습니다.  
  
-   **풍부한 콘텐츠.** 대부분의 표준 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤은 풍부한 콘텐츠를 지원합니다.  예를 들어 <xref:System.Windows.Controls.Button>의 콘텐츠 속성은 <xref:System.Object> 형식이므로 이론적으로는 <xref:System.Windows.Controls.Button>에 무엇이든지 표시할 수 있습니다.  단추에 이미지와 텍스트를 표시하려면 이미지와 <xref:System.Windows.Controls.TextBlock>을 <xref:System.Windows.Controls.StackPanel>에 추가하고 <xref:System.Windows.Controls.StackPanel>을 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성에 할당합니다.  이러한 컨트롤은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시각적 요소와 임의의 데이터를 표시할 수 있으므로 복잡한 시각화를 지원하기 위해 새 컨트롤을 만들거나 기존 컨트롤을 수정할 필요가 적어집니다.  <xref:System.Windows.Controls.Button>용 콘텐츠 모델 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 기타 콘텐츠 모델에 대한 자세한 내용은 [WPF 콘텐츠 모델](../../../../docs/framework/wpf/controls/wpf-content-model.md)을 참조하십시오.  
  
-   **스타일.** <xref:System.Windows.Style>은 컨트롤 속성을 나타내는 값 컬렉션입니다.  스타일을 사용하면 새 컨트롤을 작성하지 않고도 원하는 모양과 동작의 재사용 가능한 표현을 만들 수 있습니다.  예를 들어 모든 <xref:System.Windows.Controls.TextBlock> 컨트롤에 글꼴 크기가 14인 빨간색 Arial 글꼴을 사용한다고 가정합니다.  스타일을 리소스로 만들고 이에 맞는 적절한 속성을 설정할 수 있습니다.  그러면 응용 프로그램에 추가하는 모든 <xref:System.Windows.Controls.TextBlock>에 동일한 모양이 적용됩니다.  
  
-   **데이터 템플릿.** <xref:System.Windows.DataTemplate>을 사용하면 데이터가 컨트롤에 표시되는 방식을 사용자 지정할 수 있습니다.  예를 들어 <xref:System.Windows.DataTemplate>을 사용하여 데이터가 <xref:System.Windows.Controls.ListBox>에 표시되는 방식을 지정할 수 있습니다.  이에 대한 예제를 보려면 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)를 참조하십시오.  데이터 모양을 사용자 지정하는 것 외에도 <xref:System.Windows.DataTemplate>에는 사용자 지정 UI의 유연성을 크게 높이는 UI 요소도 포함할 수 있습니다.  예를 들어 <xref:System.Windows.DataTemplate>을 사용하여 각 항목에 확인란이 포함된 <xref:System.Windows.Controls.ComboBox>를 만들 수 있습니다.  
  
-   **컨트롤 템플릿.** [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 컨트롤 대부분은 <xref:System.Windows.Controls.ControlTemplate>을 사용하여 컨트롤의 구조와 모양을 정의하며 이를 통해 컨트롤의 모양과 컨트롤의 기능이 분리됩니다. 컨트롤의 <xref:System.Windows.Controls.ControlTemplate>을 다시 정의하여 컨트롤 모양을 다양하게 변경할 수 있습니다.  예를 들어 신호등 모양의 컨트롤이 필요한 경우를 가정해 봅니다.  이 컨트롤에는 간단한 사용자 인터페이스와 기능이 있습니다.  컨트롤은 한 번에 하나만 켜질 수 있는 세 개의 원으로 구성됩니다.  조금 생각해 보면 <xref:System.Windows.Controls.RadioButton>은 한 번에 하나만 선택되는 기능을 제공하기는 하지만 <xref:System.Windows.Controls.RadioButton>의 기본 모양은 신호등의 등과 다르다는 것을 알 수 있습니다.  <xref:System.Windows.Controls.RadioButton>의 모양은 컨트롤 템플릿을 사용하여 정의되므로 컨트롤의 요구 사항에 맞게 <xref:System.Windows.Controls.ControlTemplate>을 간단하게 재정의하여 라디오 단추로 신호등을 만들 수 있습니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Controls.RadioButton>은 <xref:System.Windows.DataTemplate>을 사용할 수 있지만 이 예제에서는 <xref:System.Windows.DataTemplate>으로는 부족합니다.  <xref:System.Windows.DataTemplate>은 컨트롤의 콘텐츠 모양을 정의합니다.  <xref:System.Windows.Controls.RadioButton>의 경우 콘텐츠는 <xref:System.Windows.Controls.RadioButton>의 선택 여부를 표시하는 원 오른쪽에 나타납니다.  신호등 예제에서 라디오 단추는 "점등"될 수 있는 원만 있으면 됩니다. 신호등에 필요한 모양이 <xref:System.Windows.Controls.RadioButton>의 기본 모양과 다르기 때문에 <xref:System.Windows.Controls.ControlTemplate>을 재정의해야 합니다.  일반적으로 <xref:System.Windows.DataTemplate>을 사용하여 컨트롤의 콘텐츠\(또는 데이터\)를 정의하며 <xref:System.Windows.Controls.ControlTemplate>을 사용하여 컨트롤의 구조를 정의합니다.  
  
-   **트리거.** <xref:System.Windows.Trigger>를 사용하면 새 컨트롤을 만들지 않고도 컨트롤의 모양과 동작을 동적으로 변경할 수 있습니다.  예를 들어 응용 프로그램에 여러 개의 <xref:System.Windows.Controls.ListBox> 컨트롤이 있으며 각 <xref:System.Windows.Controls.ListBox>의 항목을 선택하면 해당 항목이 굵은 빨간색 글꼴로 표시되도록 하려는 경우를 가정해 봅니다.  직감적으로 <xref:System.Windows.Controls.ListBox>에서 상속되는 클래스를 만들고 <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> 메서드를 재정의하여 선택되는 항목의 모양을 변경하려고 하겠지만, 선택되는 항목의 모양을 변경하는 트리거를 <xref:System.Windows.Controls.ListBoxItem>의 스타일에 추가하는 것이 더 좋은 방법입니다.  트리거를 사용하면 속성 값을 변경하거나 속성 값에 기반하여 작업을 수행할 수 있습니다.  <xref:System.Windows.EventTrigger>를 사용하면 이벤트 발생 시 작업을 수행할 수 있습니다.  
  
 스타일, 템플릿 및 트리거에 대한 자세한 내용은 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)을 참조하십시오.  
  
 일반적으로 사용하는 컨트롤이 기존 컨트롤의 기능을 미러링하지만 컨트롤의 모양을 변경해야 하는 경우 이 단원의 방법을 사용하여 기존 컨트롤의 모양을 변경할 수 있는지 여부를 먼저 고려해야 합니다.  
  
<a name="models_for_control_authoring"></a>   
## 컨트롤 제작 모델  
 풍부한 콘텐츠 모델, 스타일, 템플릿 및 트리거를 사용하면 새 컨트롤을 만들 필요가 거의 없습니다.  하지만 새 컨트롤을 만들어야 하는 경우에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 다양한 컨트롤 제작 모델을 잘 알고 있어야 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 컨트롤 작성을 위한 세 가지 일반 모델을 제공하며 각 모델마다 서로 다른 기능과 유연성 수준을 제공합니다.  세 모델의 기본 클래스는 <xref:System.Windows.Controls.UserControl>, <xref:System.Windows.Controls.Control> 및 <xref:System.Windows.FrameworkElement>입니다.  
  
### UserControl에서 파생  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 컨트롤을 만드는 가장 간단한 방법은 <xref:System.Windows.Controls.UserControl>에서 파생시키는 방법입니다.  <xref:System.Windows.Controls.UserControl>에서 상속되는 컨트롤을 빌드할 때는 <xref:System.Windows.Controls.UserControl>에 기존 구성 요소를 추가하고, 구성 요소에 이름을 지정한 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 이벤트 처리기를 참조합니다.  그런 다음 코드에서 명명된 요소를 참조하고 이벤트 처리기를 정의합니다.  이 개발 모델은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 응용 프로그램을 개발할 때 사용되는 모델과 매우 비슷합니다.  
  
 올바르게 구성한 경우 <xref:System.Windows.Controls.UserControl>에서 풍부한 콘텐츠, 스타일 및 트리거를 이용할 수 있습니다.  하지만 컨트롤이 <xref:System.Windows.Controls.UserControl>에서 상속된 경우에는 해당 컨트롤을 사용하는 사용자가 <xref:System.Windows.DataTemplate> 또는 <xref:System.Windows.Controls.ControlTemplate>을 사용하여 모양을 사용자 지정할 수 없습니다.  템플릿을 지원하는 사용자 지정 컨트롤을 만들려면 <xref:System.Windows.Controls.Control> 클래스 또는 해당 클래스의 파생 클래스\(<xref:System.Windows.Controls.UserControl> 제외\) 중 하나에서 파생시켜야 합니다.  
  
#### UserControl에서 파생시킬 경우의 이점  
 다음과 같은 경우에 모두 해당할 때는 <xref:System.Windows.Controls.UserControl>에서 파생시키는 것이 좋습니다.  
  
-   응용 프로그램을 빌드하는 방식과 유사한 방식으로 컨트롤을 빌드하려는 경우  
  
-   컨트롤이 기존 구성 요소로만 구성되는 경우  
  
-   복잡한 사용자 지정을 지원할 필요가 없는 경우  
  
### Control에서 파생  
 <xref:System.Windows.Controls.Control> 클래스에서 파생시키는 것은 대부분의 기존 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에서 사용되는 모델입니다.  <xref:System.Windows.Controls.Control> 클래스에서 상속되는 컨트롤을 만들 때는 템플릿을 사용하여 모양을 정의합니다.  이렇게 하여 운영 논리를 시각적 표현과 분리합니다.  또한 이벤트 대신 명령과 바인딩을 사용하고 가능하면 <xref:System.Windows.Controls.ControlTemplate>의 요소를 참조하지 않는 방법으로 UI와 논리를 분리할 수도 있습니다. 컨트롤의 UI와 논리가 적절하게 분리되면 컨트롤의 사용자는 컨트롤의 <xref:System.Windows.Controls.ControlTemplate>을 다시 정의하여 모양을 사용자 지정할 수 있습니다. 사용자 지정 <xref:System.Windows.Controls.Control>을 빌드하는 것이 <xref:System.Windows.Controls.UserControl>을 빌드하는 것처럼 간단하지는 않지만 사용자 지정 <xref:System.Windows.Controls.Control>의 유연성이 가장 큽니다.  
  
#### Control에서 파생시킬 경우의 이점  
 다음과 같은 경우 중 하나 이상에 해당할 때는 <xref:System.Windows.Controls.UserControl> 클래스를 사용하는 대신 <xref:System.Windows.Controls.Control>에서 파생시키는 것이 좋습니다.  
  
-   <xref:System.Windows.Controls.ControlTemplate>을 통해 컨트롤의 모양을 사용자 지정할 수 있어야 하는 경우  
  
-   컨트롤에서 다양한 테마를 지원해야 하는 경우  
  
### FrameworkElement에서 파생  
 <xref:System.Windows.Controls.UserControl> 또는 <xref:System.Windows.Controls.Control>에서 파생된 컨트롤은 모두 기존 요소 구성에 의존합니다.  <xref:System.Windows.FrameworkElement>에서 상속되는 모든 개체는 <xref:System.Windows.Controls.ControlTemplate>에 포함되어 있을 수 있기 때문에 이는 대부분의 상황에서 문제가 되지 않습니다.  하지만 컨트롤의 모양을 간단한 요소 컴퍼지션의 기능만으로 구현할 수 없는 경우가 있습니다.  이런 경우에는 <xref:System.Windows.FrameworkElement>를 기반으로 구성 요소를 구성하는 것이 올바른 방법입니다.  
  
 <xref:System.Windows.FrameworkElement> 기반 구성 요소를 빌드하는 표준 방법은 직접 렌더링과 사용자 지정 요소 컴퍼지션의 두 가지입니다.  직접 렌더링에서는 <xref:System.Windows.FrameworkElement>의 <xref:System.Windows.UIElement.OnRender%2A> 메서드를 재정의하고 구성 요소 시각적 표시를 명시적으로 정의하는 <xref:System.Windows.Media.DrawingContext> 작업을 제공해야 합니다.  이것은 <xref:System.Windows.Controls.Image> 및 <xref:System.Windows.Controls.Border>에서 사용되는 메서드입니다.  사용자 지정 요소 컴퍼지션에서는 <xref:System.Windows.Media.Visual> 형식의 개체를 사용하여 구성 요소의 모양을 구성해야 합니다.  예제를 보려면 [DrawingVisual 개체 사용](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)을 참조하십시오.  <xref:System.Windows.Controls.Primitives.Track>은 사용자 지정 요소 컴퍼지션을 사용하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤의 한 예입니다.  한 컨트롤에서 직접 렌더링과 사용자 지정 요소 컴퍼지션을 혼합하여 사용하는 것도 가능합니다.  
  
#### FrameworkElement에서 파생시킬 경우의 이점  
 다음과 같은 경우 중 하나 이상에 해당할 때는 <xref:System.Windows.FrameworkElement>에서 파생시키는 것이 좋습니다.  
  
-   간단한 요소 컴퍼지션으로 제공되는 것 이상으로 컨트롤의 모양을 세밀하게 제어하려는 경우  
  
-   고유한 렌더링 논리를 정의하여 컨트롤 모양을 정의하려는 경우  
  
-   <xref:System.Windows.Controls.UserControl> 및 <xref:System.Windows.Controls.Control>로 가능한 수준을 뛰어넘는 방법으로 기존 요소를 구성하려는 경우  
  
<a name="control_authoring_basics"></a>   
## 컨트롤 제작 기본  
 앞에서 설명했듯이, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 가장 강력한 기능 중 하나는 사용자 지정 컨트롤을 만들 필요 없이 컨트롤의 기본 속성 설정 이외의 다양한 방법으로 컨트롤 모양과 동작을 변경할 수 있는 것입니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템과 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트 시스템을 통해 스타일 지정, 데이터 바인딩 및 트리거 기능을 사용할 수 있습니다. 다음 단원에서는 사용자 지정 컨트롤을 만들 때 사용한 모델에 관계없이 사용자 지정 컨트롤의 사용자가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 포함된 컨트롤의 경우와 마찬가지로 이러한 기능을 사용할 수 있도록 수행해야 할 사항에 대해 설명합니다.  
  
### 종속성 속성 사용  
 속성이 종속성 속성이면 다음을 수행할 수 있습니다.  
  
-   스타일에서 속성을 설정합니다.  
  
-   속성을 데이터 소스에 바인딩합니다.  
  
-   동적 리소스를 속성의 값으로 사용합니다.  
  
-   속성에 애니메이션 효과를 줍니다.  
  
 컨트롤의 속성이 이러한 기능을 지원하도록 하려면 종속성 속성으로 구현해야 합니다.  다음 예제에서는 다음을 수행하여 `Value`라는 종속성 속성을 정의합니다.  
  
-   `ValueProperty`라는 <xref:System.Windows.DependencyProperty> 식별자를 `public` `static` `readonly` 필드로 정의합니다.  
  
-   <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=fullName>를 호출하여 속성 이름을 속성 시스템에 등록하고 다음을 지정합니다.  
  
    -   속성 이름  
  
    -   속성의 형식입니다.  
  
    -   속성 소유 형식  
  
    -   속성의 메타데이터.  메타데이터에는 속성의 기본값, <xref:System.Windows.CoerceValueCallback> 및 <xref:System.Windows.PropertyChangedCallback>이 포함됩니다.  
  
-   속성의 `get` 및 `set` 접근자를 구현하여 종속성 속성 등록에 사용한 것과 이름이 동일한 `Value`라는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 래퍼 속성을 정의합니다.  `get` 및 `set` 접근자는 각각 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A>를 호출만 합니다.  클라이언트와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 접근자를 무시하고 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A>를 직접 호출할 수 있기 때문에 종속성 속성의 접근자에는 추가적인 논리를 포함하지 않는 것이 좋습니다.  예를 들어 속성이 데이터 소스에 바인딩될 때는 속성의 `set` 접근자가 호출되지 않습니다.  get 및 set 접근자에 논리를 추가하는 대신 <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.CoerceValueCallback> 및 <xref:System.Windows.PropertyChangedCallback> 대리자를 사용하여 응답하거나 값 변경을 검사하십시오.  이러한 콜백에 대한 자세한 내용은 [종속성 속성 콜백 및 유효성 검사](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)를 참조하십시오.  
  
-   <xref:System.Windows.CoerceValueCallback>에 대해 `CoerceValue`라는 메서드를 정의합니다.  `CoerceValue`는 `Value`가 `MinValue`보다 크거나 같고 `MaxValue`보다 작거나 같은지 확인합니다.  
  
-   <xref:System.Windows.PropertyChangedCallback>에 대해 `OnValueChanged`라는 메서드를 정의합니다.  `OnValueChanged`는 <xref:System.Windows.RoutedPropertyChangedEventArgs%601> 개체를 만들고 라우트된 이벤트 `ValueChanged`를 발생시킬 준비를 합니다.  라우트된 이벤트에 대해서는 다음 단원에서 설명합니다.  
  
 [!code-csharp[UserControlNumericUpDown#DependencyProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
 [!code-vb[UserControlNumericUpDown#DependencyProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]  
  
 자세한 내용은 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)을 참조하십시오.  
  
### 라우트된 이벤트 사용  
 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 속성의 개념을 추가 기능으로 확장하는 [종속성 속성](GTMT)과 마찬가지로 [라우트된 이벤트](GTMT)는 표준 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 이벤트 개념을 확장합니다.  라우트된 이벤트는 다음 동작을 지원하므로 새 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤을 만들 때 이벤트를 라우트된 이벤트로 구현하는 것도 좋은 방법입니다.  
  
-   이벤트는 여러 컨트롤의 부모에서 처리될 수 있습니다.  이벤트가 버블링 이벤트인 경우에는 요소 트리의 단일 부모가 이벤트를 구독할 수 있습니다.  그러면 응용 프로그램 작성자는 하나의 처리기를 사용하여 여러 컨트롤의 이벤트에 응답할 수 있습니다.  예를 들어 컨트롤이 <xref:System.Windows.DataTemplate>에 포함되어 <xref:System.Windows.Controls.ListBox>의 각 항목에 속하는 경우 응용 프로그램 개발자는 <xref:System.Windows.Controls.ListBox>에서 컨트롤의 이벤트에 대한 이벤트 처리기를 정의할 수 있습니다.  컨트롤에서 이벤트가 발생할 때마다 이벤트 처리기가 호출됩니다.  
  
-   라우트된 이벤트는 <xref:System.Windows.EventSetter>에 사용할 수 있기 때문에 응용 프로그램 개발자는 스타일 안에서 이벤트의 처리기를 지정할 수 있습니다.  
  
-   라우트된 이벤트는 <xref:System.Windows.EventTrigger>에 사용할 수 있으므로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하여 속성에 애니메이션 효과를 적용할 때 유용합니다.  자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
 다음 예제에서는 다음을 수행하여 라우트된 이벤트를 정의합니다.  
  
-   `ValueChangedEvent`라는 <xref:System.Windows.RoutedEvent> 식별자를 `public` `static` `readonly` 필드로 정의합니다.  
  
-   <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=fullName> 메서드를 호출하여 라우트된 이벤트를 등록합니다.  이 예제에서는 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>를 호출할 때 다음 정보를 지정합니다.  
  
    -   이벤트의 이름은 `ValueChanged`입니다.  
  
    -   라우팅 전략은 <xref:System.Windows.RoutingStrategy>입니다. 즉, 소스\(이벤트를 발생시키는 개체\)에서 이벤트 처리기가 먼저 호출된 다음 가장 가까운 부모 요소의 이벤트 처리기부터 시작하여 소스의 부모 요소의 이벤트 처리기가 연이어 호출됩니다.  
  
    -   이벤트 처리기의 형식은 <xref:System.Decimal> 형식으로 구성되는 <xref:System.Windows.RoutedPropertyChangedEventHandler%601>입니다.  
  
    -   이벤트를 소유하는 형식은 `NumericUpDown`입니다.  
  
-   `ValueChanged`라는 공용 이벤트를 선언하고 이벤트 접근자 선언을 포함합니다.  이 예제에서는 `add` 접근자 선언에서 <xref:System.Windows.UIElement.AddHandler%2A>를 호출하고 `remove` 접근자 선언에서 <xref:System.Windows.UIElement.RemoveHandler%2A>를 호출하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트 서비스를 사용합니다.  
  
-   `ValueChanged` 이벤트를 발생시키는 `OnValueChanged`라는 보호된 가상 메서드를 만듭니다.  
  
 [!code-csharp[UserControlNumericUpDown#RoutedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
 [!code-vb[UserControlNumericUpDown#RoutedEvent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]  
  
 자세한 내용은 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md) 및 [사용자 지정 라우트된 이벤트 만들기](../../../../docs/framework/wpf/advanced/how-to-create-a-custom-routed-event.md)를 참조하십시오.  
  
### 바인딩 사용  
 컨트롤의 UI를 논리와 분리하려면 데이터 바인딩을 사용하는 것이 좋습니다.  특히 <xref:System.Windows.Controls.ControlTemplate>을 사용하여 컨트롤 모양을 정의할 때는 컨트롤의 UI와 논리를 분리하는 것이 좋습니다.  데이터 바인딩을 사용하면 코드에서 UI의 특정 부분을 참조할 필요가 없어질 수 있습니다.  코드에서 <xref:System.Windows.Controls.ControlTemplate> 내의 요소를 참조할 경우 <xref:System.Windows.Controls.ControlTemplate>이 변경되면 참조된 요소를 새 <xref:System.Windows.Controls.ControlTemplate>에 포함해야 하기 때문에 <xref:System.Windows.Controls.ControlTemplate> 내의 요소는 참조하지 않는 것이 좋습니다.  
  
 다음 예제에서는 `NumericUpDown` 컨트롤의 <xref:System.Windows.Controls.TextBlock>을 업데이트하여 여기에 이름을 할당하고 코드에서 이름을 사용하여 텍스트 상자를 참조합니다.  
  
 [!code-xml[UserControlNumericUpDownSimple#UIRefMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]  
  
 [!code-csharp[UserControlNumericUpDownSimple#UIRefCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
 [!code-vb[UserControlNumericUpDownSimple#UIRefCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]  
  
 다음 예제에서는 바인딩을 사용하여 동일한 작업을 수행합니다.  
  
 [!code-xml[UserControlNumericUpDown#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]  
  
 데이터 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  
  
### 디자이너용 디자인  
 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]에서 사용자 지정 WPF 컨트롤에 대한 지원을 받으려면\(예를 들어 속성 창으로 속성 편집\) 다음 지침을 따르십시오.  [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]에 사용할 컨트롤을 개발하는 방법에 대한 자세한 내용은 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)를 참조하십시오.  
  
#### 종속성 속성  
 앞의 "종속성 속성 사용"에서 설명한 것처럼 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] `get` 및 `set` 접근자를 구현해야 합니다. 디자이너는 래퍼를 사용하여 종속성 속성의 존재 여부를 탐지할 수 있지만 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 컨트롤의 클라이언트와 마찬가지로 속성을 가져오거나 설정할 때 반드시 접근자를 호출할 필요는 없습니다.  
  
#### 연결된 속성  
 다음 지침에 따라 사용자 지정 컨트롤에 연결된 속성을 구현해야 합니다.  
  
-   <xref:System.Windows.DependencyProperty.RegisterAttached%2A> 메서드를 사용하여 생성한 *PropertyName*`Property` 형태의 `public` `static` `readonly` <xref:System.Windows.DependencyProperty>가 있어야 합니다.  <xref:System.Windows.DependencyProperty.RegisterAttached%2A>로 전달되는 속성 이름은 *PropertyName*과 일치해야 합니다.  
  
-   `Set` *PropertyName*과 `Get`*PropertyName*이라는 `public` `static` CLR 메서드 쌍을 구현합니다.  두 메서드 모두 <xref:System.Windows.DependencyProperty>에서 파생된 클래스를 첫 번째 인수로 받아야 합니다.  `Set`*PropertyName* 메서드 또한 속성의 등록된 데이터 형식과 일치하는 형식의 인수를 받습니다.  `Get`*PropertyName* 메서드는 동일한 형식의 값을 반환해야 합니다.  `Set`*PropertyName* 메서드가 없으면 해당 속성은 읽기 전용으로 표시됩니다.  
  
-   `Set` *PropertyName* 및 `Get`*PropertyName*은 각각 대상 종속성 개체에 있는 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A> 메서드에 직접 라우트되어야 합니다.  디자이너는 메서드 래퍼를 통해 호출하거나 대상 종속성 개체를 직접 호출하여 연결된 속성에 액세스할 수 있습니다.  
  
 연결된 속성에 대한 자세한 내용은 [연결된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)를 참조하십시오.  
  
### 공유 리소스 정의 및 사용  
 컨트롤을 응용 프로그램과 같은 어셈블리에 포함할 수도 있고 별도의 어셈블리에 패키지하여 여러 응용 프로그램에서 사용할 수도 있습니다.  이 항목에서 설명하는 대부분의 정보는 사용하는 모델에 관계없이 적용됩니다.  그러나 한 가지 주목해야 할 차이점이 있습니다.  컨트롤을 응용 프로그램과 같은 어셈블리에 배치할 경우 App.xaml 파일에 전역 리소스를 추가할 수 있지만,  컨트롤만 포함된 어셈블리의 경우 어셈블리에 <xref:System.Windows.Application> 개체가 연결되어 있지 않으므로 App.xaml 파일을 사용할 수 없습니다.  
  
 응용 프로그램에서는 리소스를 찾을 때 다음의 순서대로 세 가지 수준에서 리소스를 찾습니다.  
  
1.  요소 수준입니다.  
  
     시스템이 리소스를 참조하는 요소와 함께 시작된 후 리소스의 논리적 부모에서 루트 요소에 도달할 때까지 리소스를 검색합니다.  
  
2.  응용 프로그램 수준입니다.  
  
     <xref:System.Windows.Application> 개체가 정의하는 리소스입니다.  
  
3.  테마 수준입니다.  
  
     테마 수준 사전은 Themes라는 하위 폴더에 저장됩니다.  Themes 폴더에 있는 파일은 각각의 테마에 해당합니다.  예를 들어 이 폴더에는 Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml 등의 파일이 있습니다.  generic.xaml이라는 파일도 포함되어 있을 수 있습니다.  테마 수준에서 리소스를 찾을 때 시스템에서는 리소스를 먼저 테마별 파일에서 찾은 다음 generic.xaml에서 찾습니다.  
  
 컨트롤이 응용 프로그램과는 별도의 어셈블리에 있는 경우 전역 리소스를 요소 수준이나 테마 수준에 배치해야 하며,  두 방법 중 어느 것을 사용하든 나름의 장점이 있습니다.  
  
#### 요소 수준에서 리소스 정의  
 요소 수준에서 공유 리소스를 정의하려면 사용자 지정 리소스 사전을 만들어 컨트롤의 리소스 사전과 병합하면 됩니다.  이 방법을 사용할 경우 원하는 리소스 파일을 지정할 수 있으며 컨트롤과 같은 폴더에 리소스 파일을 배치할 수 있습니다.  또한 요소 수준의 리소스는 단순한 문자열을 키로 사용할 수 있습니다.  다음 예제에서는 Dictionary1.xaml이라는 <xref:System.Windows.Media.LinearGradientBrush> 리소스 파일을 만듭니다.  
  
 [!code-xml[SharedResources#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]  
  
 사용자 지정 리소스 사전을 정의했으면 사전을 컨트롤의 리소스 사전과 병합해야 합니다.  이 작업은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]이나 코드를 사용하여 수행할 수 있습니다.  
  
 다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하여 리소스 사전을 병합합니다.  
  
 [!code-xml[SharedResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]  
  
 이 방법을 사용할 경우 <xref:System.Windows.ResourceDictionary> 개체를 참조할 때마다 이 개체가 생성되는 단점이 있습니다.  예를 들어 라이브러리에 10개의 사용자 지정 컨트롤이 있는데 XAML을 사용하여 각 컨트롤에 대해 공유 리소스 사전을 병합하면 10개의 동일한 <xref:System.Windows.ResourceDictionary> 개체가 생성됩니다.  이를 방지하려면 코드에서 리소스를 병합하여 결과 <xref:System.Windows.ResourceDictionary>를 반환하는 정적 클래스를 만듭니다.  
  
 다음 예제에서는 공유 <xref:System.Windows.ResourceDictionary>를 반환하는 클래스를 만듭니다.  
  
 [!code-csharp[SharedResources#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]  
  
 다음 예제에서는 `InitilizeComponent`를 호출하기 전에 공유 리소스를 컨트롤의 생성자에 있는 사용자 지정 컨트롤의 리소스와 병합합니다.  `SharedDictionaryManager.SharedDictionary`는 정적 속성이므로 <xref:System.Windows.ResourceDictionary>가 한 번만 생성됩니다.  `InitializeComponent`가 호출되기 전에 리소스 사전이 병합되었으므로 해당 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일의 컨트롤에 리소스를 사용할 수 있습니다.  
  
 [!code-csharp[SharedResources#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]  
  
#### 테마 수준에서 리소스 정의  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하면 다양한 Windows 테마에 사용할 리소스를 만들 수 있습니다.  컨트롤 작성자는 사용 중인 테마에 따라 특정 테마의 리소스를 정의하여 컨트롤의 모양을 변경할 수 있습니다.  예를 들어, Windows 고전 테마\(Windows 2000의 기본 테마\)의 <xref:System.Windows.Controls.Button> 모양은 Windows Luna 테마\(Windows XP의 기본 테마\)의 <xref:System.Windows.Controls.Button> 모양과 다릅니다. 이는 <xref:System.Windows.Controls.Button>이 각 테마에 대해 서로 다른 <xref:System.Windows.Controls.ControlTemplate>을 사용하기 때문입니다.  
  
 테마별 리소스는 특정 파일 이름이 지정되어 리소스 사전에 보관됩니다.  이러한 파일은 컨트롤이 포함된 폴더의 하위 폴더인 `Themes` 폴더에 있어야 합니다.  다음 표에서는 리소스 사전 파일 및 각 파일과 연결된 테마를 보여 줍니다.  
  
|리소스 사전 파일 이름|Windows 테마|  
|------------------|----------------|  
|`Classic.xaml`|Windows XP의 기본 Windows 9x\/2000 테마|  
|`Luna.NormalColor.xaml`|Windows XP의 기본 파랑 테마|  
|`Luna.Homestead.xaml`|Windows XP의 올리브 테마|  
|`Luna.Metallic.xaml`|Windows XP의 은색 테마|  
|`Royale.NormalColor.xaml`|Windows XP Media Center Edition의 기본 테마|  
|`Aero.NormalColor.xaml`|Windows Vista의 기본 테마|  
  
 모든 테마에 대해 리소스를 정의할 필요가 없습니다.  특정 테마에 대해 리소스가 정의되어 있지 않으면 컨트롤은 `Classic.xaml`에서 리소스를 확인합니다.  리소스가 현재 테마에 해당하는 파일이나 `Classic.xaml`에 정의되어 있지 않으면 컨트롤은 `generic.xaml`이라는 리소스 사전 파일에 있는 일반 리소스를 사용합니다.  `generic.xaml` 파일은 테마별 리소스 사전 파일과 동일한 폴더에 있습니다.  `generic.xaml`은 특정 Windows 테마와 일치하지는 않지만 그렇다 해도 테마 수준 사전입니다.  
  
 [NumericUpDown Custom Control with Theme and UI Automation Support 샘플](http://go.microsoft.com/fwlink/?LinkID=160025)에는 `NumericUpDown` 컨트롤에 대한 두 개의 리소스 사전이 포함되어 있습니다. 하나는 generic.xaml에 있고 다른 하나는 Luna.NormalColor.xaml에 있습니다.  응용 프로그램을 실행한 후 Windows XP의 은색 테마와 다른 테마 간을 전환하여 두 컨트롤 템플릿의 차이를 확인할 수 있습니다.  Windows Vista를 실행하는 경우 Luna.NormalColor.xaml의 이름을 Aero.NormalColor.xaml로 바꾼 다음 Windows 고전과 Windows Vista의 기본 테마 같은 두 테마 간을 전환할 수 있습니다.  
  
 <xref:System.Windows.Controls.ControlTemplate>을 테마별 리소스 사전 파일에 배치할 때 다음 예제와 같이 컨트롤의 정적 생성자를 만든 다음 <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>에서 <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29>를 호출해야 합니다.  
  
 [!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
 [!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]  
  
##### 테마 리소스의 키 정의 및 참조  
 요소 수준에서 리소스를 정의하는 경우 문자열을 리소스의 키로 지정하고 이 문자열을 통해 리소스에 액세스할 수 있습니다.  테마 수준에서 리소스를 정의하는 경우에는 <xref:System.Windows.ComponentResourceKey>를 리소스의 키로 사용해야 합니다.  다음 예제에서는 generic.xaml에 리소스를 정의합니다.  
  
  
  
 다음 예제에서는 <xref:System.Windows.ComponentResourceKey>를 키로 지정하여 리소스를 참조합니다.  
  
  
  
##### 테마 리소스의 위치 지정  
 컨트롤의 리소스를 찾으려면 어셈블리에 컨트롤 관련 리소스가 들어 있다는 것을 호스팅 응용 프로그램이 알고 있어야 합니다.  이 작업은 <xref:System.Windows.ThemeInfoAttribute>를 컨트롤이 포함된 어셈블리에 추가하여 수행할 수 있습니다.  <xref:System.Windows.ThemeInfoAttribute>에는 일반 리소스의 위치를 지정하는 <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> 속성과 테마별 리소스의 위치를 지정하는 <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> 속성이 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> 및 <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> 속성을 <xref:System.Windows.ResourceDictionaryLocation>로 설정하여 일반 리소스와 테마별 리소스가 컨트롤과 같은 어셈블리에 있도록 지정합니다.  
  
 [!code-csharp[CustomControlNumericUpDown#ThemesSection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
 [!code-vb[CustomControlNumericUpDown#ThemesSection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]  
  
## 참고 항목  
 [WPF Designer](http://msdn.microsoft.com/ko-kr/c6c65214-8411-4e16-b254-163ed4099c26)   
 [WPF의 Pack URI](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [컨트롤 사용자 지정](../../../../docs/framework/wpf/controls/control-customization.md)