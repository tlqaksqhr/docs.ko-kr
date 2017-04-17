---
title: "Storyboard 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Storyboard 구문"
  - "구문, 스토리보드"
  - "Timeline"
ms.assetid: 1a698c3c-30f1-4b30-ae56-57e8a39811bd
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# Storyboard 개요
이 항목에서는 <xref:System.Windows.Media.Animation.Storyboard> 개체를 사용하여 애니메이션을 구성 및 적용하는 방법을 보여 줍니다.  <xref:System.Windows.Media.Animation.Storyboard> 개체를 대화형으로 조작하는 방법을 설명하고 간접 속성 대상 지정 구문에 대해 설명합니다.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목을 이해하려면 여러 다른 애니메이션 형식 및 해당 기본 기능에 익숙해야 합니다.  애니메이션에 대한 소개는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  또한 연결된 속성을 사용하는 방법을 알아야 합니다.  연결된 속성에 대한 자세한 내용은 [연결된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)를 참조하십시오.  
  
<a name="whatisatimeline"></a>   
## Storyboard란?  
 애니메이션이 사용 가능한 유일한 Timeline의 형식은 아닙니다.  Timeline 집합을 구성하고 Timeline을 속성에 적용하는 데 도움이 되도록 다른 Timeline 클래스가 제공됩니다.  컨테이너 Timeline은 <xref:System.Windows.Media.Animation.TimelineGroup> 클래스에서 파생되고 <xref:System.Windows.Media.Animation.ParallelTimeline> 및 <xref:System.Windows.Media.Animation.Storyboard>를 포함합니다.  
  
 <xref:System.Windows.Media.Animation.Storyboard>는 포함된 Timeline에 대한 대상 정보를 제공하는 컨테이너 Timeline 형식입니다.  Storyboard는 다른 컨테이너 Timeline 및 애니메이션을 비롯한 모든 형식의 <xref:System.Windows.Media.Animation.Timeline>을 포함할 수 있습니다.  <xref:System.Windows.Media.Animation.Storyboard> 개체를 사용하면 다양한 개체 및 속성에 영향을 주는 Timeline을 단일 Timeline 트리에 결합할 수 있으며 이를 통해 복잡한 타이밍 동작을 쉽게 구성 및 제어할 수 있습니다.  예를 들어 다음 세 가지 작업을 수행하는 단추가 필요하다고 가정해 봅니다.  
  
-   사용자가 단추를 선택하면 커지고 색이 변경됩니다.  
  
-   클릭하면 축소되어 원래 크기로 돌아갑니다.  
  
-   사용하지 않도록 설정하면 축소되고 50% 불투명하게 흐려집니다.  
  
 이 경우 동일한 개체에 적용되는 여러 애니메이션 집합이 있으며 단추의 상태에 따라 이러한 애니메이션 집합을 다른 시점에 재생해야 합니다.  <xref:System.Windows.Media.Animation.Storyboard> 개체를 사용하면 애니메이션을 구성하여 하나 이상의 개체에 그룹으로 적용할 수 있습니다.  
  
<a name="wherecanyouuseastoryboard"></a>   
## Storyboard를 사용할 수 있는 위치  
 <xref:System.Windows.Media.Animation.Storyboard>를 사용하여 애니메이션 가능한 클래스의 [종속성 속성](GTMT)에 애니메이션 효과를 줄 수 있습니다. 클래스를 애니메이션 가능하게 만드는 방법에 대한 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  그러나 스토리보드 작성이 프레임워크 수준 기능이므로 개체는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>의 <xref:System.Windows.NameScope>에 속해야 합니다.  
  
 예를 들어 <xref:System.Windows.Media.Animation.Storyboard>를 사용하여 다음을 수행할 수 있습니다.  
  
-   단추\(<xref:System.Windows.FrameworkElement> 형식\)의 배경을 그리는 <xref:System.Windows.Media.SolidColorBrush>\(비프레임워크 요소\)에 애니메이션 효과를 줍니다.  
  
-   <xref:System.Windows.Controls.Image>\(<xref:System.Windows.FrameworkElement>\)를 사용하여 표시되는 <xref:System.Windows.Media.GeometryDrawing>\(비프레임워크 요소\)의 채우기를 그리는 <xref:System.Windows.Media.SolidColorBrush>\(비프레임워크 요소\)에 애니메이션 효과를 줍니다.  
  
-   코드에서 <xref:System.Windows.Media.SolidColorBrush>가 이름을 <xref:System.Windows.FrameworkElement>에 등록한 경우 또한 해당 <xref:System.Windows.FrameworkElement>를 포함하는 클래스에 의해 선언된 <xref:System.Windows.Media.SolidColorBrush>에 애니메이션 효과를 줍니다.  
  
 그러나 해당 이름을 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>에 등록하지 않았거나 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>의 속성을 설정하는 데 사용되지 않은 <xref:System.Windows.Media.SolidColorBrush>에는 <xref:System.Windows.Media.Animation.Storyboard>를 사용하여 애니메이션 효과를 줄 수 없습니다.  
  
<a name="applyanimationswithastoryboard"></a>   
## Storyboard와 함께 애니메이션을 적용하는 방법  
 <xref:System.Windows.Media.Animation.Storyboard>를 사용하여 애니메이션을 구성 및 적용하려면 애니메이션을 <xref:System.Windows.Media.Animation.Storyboard>의 자식 Timeline으로 추가합니다.  <xref:System.Windows.Media.Animation.Storyboard> 클래스에서는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=fullName> 및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=fullName> 연결 속성을 제공합니다.  애니메이션에서 이러한 속성을 설정하여 대상 개체 및 속성을 지정합니다.  
  
 애니메이션을 대상에 적용하려면 트리거 동작 또는 메서드를 사용하여 <xref:System.Windows.Media.Animation.Storyboard>를 시작합니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 <xref:System.Windows.Media.Animation.BeginStoryboard> 개체를 <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger> 또는 <xref:System.Windows.DataTrigger>와 함께 사용합니다.  코드에서는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 사용할 수도 있습니다.  
  
 다음 표에서는 각 <xref:System.Windows.Media.Animation.Storyboard> 시작 기술이 지원되는 다양한 위치\(인스턴스별, 스타일, 컨트롤 템플릿 및 데이터 템플릿\)를 보여 줍니다. 이때   인스턴스별"은 애니메이션이나 Storyboard를 스타일, 컨트롤 템플릿 또는 데이터 템플릿에 적용하지 않고 개체의 인스턴스에 직접 적용하는 기술을 말합니다.  
  
|다음을 사용하여 Storyboard 시작|인스턴스별|스타일|컨트롤 템플릿|데이터 템플릿|예제|  
|----------------------------|-----------|---------|-------------|-------------|--------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 및 <xref:System.Windows.EventTrigger>|예|예|예|예|[Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 및 속성 <xref:System.Windows.Trigger>|아니요|예|예|예|[속성 값이 변경될 때 애니메이션 트리거](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 및 <xref:System.Windows.DataTrigger>|아니요|예|예|예|[How to: Trigger an Animation When Data Changes](http://msdn.microsoft.com/ko-kr/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드|예|아니요|아니요|아니요|[Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard>를 사용하여 <xref:System.Windows.Shapes.Rectangle> 요소의 <xref:System.Windows.FrameworkElement.Width%2A> 및 해당 <xref:System.Windows.Shapes.Rectangle>을 그리는 데 사용되는 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.SolidColorBrush.Color%2A>에 애니메이션 효과를 줍니다.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]  
  
 다음 단원에서는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 연결 속성에 대해 자세히 설명합니다.  
  
<a name="targetingelementsandfreezables"></a>   
## 프레임워크 요소, 프레임워크 콘텐츠 요소 및 Freezable을 대상으로 지정  
 이전 단원에서는 애니메이션이 해당 대상을 찾으려면 대상 이름과 애니메이션 효과를 줄 속성을 알아야 한다는 것을 언급했습니다.  애니메이션 효과를 줄 속성을 지정하는 것은 간단합니다. 단순히 애니메이션 효과를 줄 속성의 이름과 함께 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=fullName>를 설정하면 됩니다.  애니메이션에서 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=fullName> 속성을 설정하여 해당 속성에 애니메이션 효과를 주려는 개체의 이름을 지정합니다.  
  
 <xref:System.Windows.Setter.TargetName%2A> 속성이 작동하려면 대상으로 지정된 개체에 이름이 있어야 합니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>에 이름을 할당하는 것은 <xref:System.Windows.Freezable> 개체에 이름을 할당하는 것과 다릅니다.  
  
 프레임워크 요소는 <xref:System.Windows.FrameworkElement> 클래스에서 상속되는 클래스입니다.  프레임워크 요소의 예로는 <xref:System.Windows.Window>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Button> 및 <xref:System.Windows.Shapes.Rectangle>이 있습니다.  기본적으로 모든 창, 패널 및 컨트롤은 요소입니다.  프레임워크 콘텐츠 요소는 <xref:System.Windows.FrameworkContentElement> 클래스에서 상속되는 클래스입니다.  프레임워크 콘텐츠 요소의 예로는 <xref:System.Windows.Documents.FlowDocument> 및 <xref:System.Windows.Documents.Paragraph>가 있습니다.  형식이 프레임워크 요소 또는 프레임워크 콘텐츠 요소인지 확실하지 않은 경우 Name 속성이 있는지 확인합니다.  이 속성이 있는 경우 형식은 프레임워크 요소 또는 프레임워크 콘텐츠 요소일 것입니다.  확실하게 하려면 해당 형식 페이지의 InheritanceHierarchy 섹션을 확인합니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 프레임워크 요소 또는 프레임워크 콘텐츠 요소의 대상 지정을 사용하도록 설정하려면 해당 <xref:System.Windows.FrameworkElement.Name%2A> 속성을 설정합니다.  코드에서는 또한 <xref:System.Windows.NameScope.RegisterName%2A> 메서드를 사용하여 <xref:System.Windows.NameScope>를 만든 요소에 요소 이름을 등록해야 합니다.  
  
 이전 예제에서 가져온 다음 예제에서는 <xref:System.Windows.FrameworkElement> 형식인 <xref:System.Windows.Shapes.Rectangle>에 `MyRectangle`이라는 이름을 할당합니다.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]  
  
 이름을 갖게 된 후에는 해당 요소의 속성에 애니메이션 효과를 줄 수 있습니다.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]  
  
 <xref:System.Windows.Freezable> 형식은 <xref:System.Windows.Freezable> 클래스에서 상속되는 클래스입니다.  <xref:System.Windows.Freezable>의 예로는 <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.RotateTransform> 및 <xref:System.Windows.Media.GradientStop>이 있습니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 <xref:System.Windows.Freezable>을 애니메이션 대상으로 지정할 수 있게 하려면 [x:Name 지시문](../../../../docs/framework/xaml-services/x-name-directive.md)를 사용하여 이름을 할당합니다.  코드에서는 <xref:System.Windows.NameScope.RegisterName%2A> 메서드를 사용하여 <xref:System.Windows.NameScope>를 만든 요소에 해당 이름을 등록합니다.  
  
 다음 예제에서는 이름을 <xref:System.Windows.Freezable> 개체에 할당합니다.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]  
  
 그런 다음 개체를 애니메니션의 대상으로 할 수 있습니다.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]  
  
 <xref:System.Windows.Media.Animation.Storyboard> 개체는 이름 범위를 사용하여 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 속성을 확인합니다.  WPF 이름 범위에 대한 자세한 내용은 [WPF XAML 이름 범위](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)를 참조하십시오.  <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 속성이 생략된 경우 애니메이션은 애니메이션이 정의된 요소나 스타일이 지정된 요소\(스타일의 경우\)를 대상으로 합니다.  
  
 <xref:System.Windows.Freezable> 개체에 이름을 할당할 수 없는 경우도 있습니다.  예를 들어 <xref:System.Windows.Freezable>이 리소스로 선언되거나 스타일에서 속성 값을 설정하는 데 사용될 경우 이름을 제공할 수 없습니다.  이름이 없기 때문에 대상으로 직접 지정할 수는 없지만 간접적으로 대상이 될 수 있습니다.  다음 단원에서는 간접 대상 지정을 사용하는 방법에 대해 설명합니다.  
  
<a name="pathsyntaxforchangeable"></a>   
## 간접 대상 지정  
 <xref:System.Windows.Freezable>이 리소스로 선언되거나 스타일의 속성 값을 설정하는 데 사용되는 경우처럼 <xref:System.Windows.Freezable>이 직접적으로 애니메이션의 대상이 될 수 없는 경우가 있습니다.  이러한 경우 대상으로 직접 지정할 수 없더라도 <xref:System.Windows.Freezable> 개체에 계속해서 애니메이션 효과를 줄 수 있습니다.  <xref:System.Windows.Freezable>의 이름을 사용하여  <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 속성을 설정하는 대신에 <xref:System.Windows.Freezable>이 "속하는" 요소의 이름을 제공합니다. 예를 들어 사각형 요소의 <xref:System.Windows.Shapes.Shape.Fill%2A>을 설정하는 데 사용되는 <xref:System.Windows.Media.SolidColorBrush>는 해당 사각형에 속합니다.  브러시에 애니메이션 효과를 주려면 <xref:System.Windows.Freezable>이 설정하는 데 사용된 프레임워크 요소 또는 프레임워크 콘텐츠 요소의 속성에서 시작하여 애니메이션 효과를 줄 <xref:System.Windows.Freezable> 속성으로 끝나는 속성 체인을 사용하여 애니메이션의 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A>를 설정합니다.  
  
  
  
 [!code-csharp[storyboards_ovw_snip#134](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]  
  
 <xref:System.Windows.Freezable>이 고정된 경우 복제본이 작성되고 해당 복제본에 애니메이션 효과가 주어집니다.  이 경우 원래 개체에 실제로 애니메이션 효과가 주어지지 않으므로 원래 개체의 <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> 속성은 계속해서 `false`를 반환합니다.  복제에 대한 자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
 또한 간접 속성 대상 지정을 사용할 경우 존재하지 않는 개체를 대상으로 할 수 있습니다.  예를 들어 실제로는 특정 단추의 배경을 설정하기 위해 <xref:System.Windows.Media.LinearGradientBrush>가 사용되었지만 해당 단추의 <xref:System.Windows.Controls.Control.Background%2A>가 <xref:System.Windows.Media.SolidColorBrush>를 사용하여 설정되었다고 가정하고 해당 색에 애니메이션 효과를 줄 수 있습니다.  이러한 경우 예외가 throw되지 않습니다. <xref:System.Windows.Media.LinearGradientBrush>가 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 속성의 변경 내용에 반응하지 않으므로 애니메이션은 시각적인 효과를 가지는 데 실패합니다.  
  
 다음 단원에서는 간접 속성 대상 지정 구문에 대해 자세히 설명합니다.  
  
<a name="xamlsyntaxchangeableproperty"></a>   
### XAML에서 Freezable의 속성을 간접적으로 대상 지정  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 Freezable의 속성을 대상으로 하려면 다음 구문을 사용합니다.  
  
||  
|-|  
|*ElementPropertyName*`.`*FreezablePropertyName*|  
  
 Where  
  
-   *ElementPropertyName*은 <xref:System.Windows.Freezable>이 설정하는 데 사용되는 <xref:System.Windows.FrameworkElement>의 속성입니다.  
  
-   *FreezablePropertyName*은 애니메이션 효과를 주려는 <xref:System.Windows.Freezable>의 속성입니다.  
  
 다음 코드 예제에서는 사각형 요소에서 다음 항목을 설정하는 데 사용되는 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.SolidColorBrush.Color%2A>에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
 <xref:System.Windows.Shapes.Shape.Fill%2A>  
  
  
  
 컬렉션 또는 배열에 포함된 Freezable을 대상으로 해야 하는 경우가 있습니다.  
  
 컬렉션에 포함된 Freezable을 대상으로 하려면 다음 경로 구문을 사용합니다.  
  
||  
|-|  
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|  
  
 여기서 *CollectionIndex*는 해당 배열 또는 컬렉션에 있는 개체의 인덱스입니다.  
  
 예를 들어 사각형에서 해당 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 적용되는 <xref:System.Windows.Media.TransformGroup> 리소스가 있으며 포함된 변환 중 하나에 애니메이션 효과를 주려고 한다고 가정해 봅니다.  
  
  
  
 다음 코드는 이전 예제에 있는 <xref:System.Windows.Media.RotateTransform>의 <xref:System.Windows.Media.RotateTransform.Angle%2A> 속성에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
  
  
<a name="targetingpropertyofchangeableincode"></a>   
### 코드에서 Freezable의 속성을 간접적으로 대상 지정  
 코드에서는 <xref:System.Windows.PropertyPath> 개체를 만듭니다.  <xref:System.Windows.PropertyPath>를 만들 경우 <xref:System.Windows.PropertyPath.Path%2A> 및 <xref:System.Windows.PropertyPath.PathParameters%2A>를 지정합니다.  
  
 <xref:System.Windows.PropertyPath.PathParameters%2A>를 만들려면 종속성 속성 식별자 필드의 목록을 포함하는 <xref:System.Windows.DependencyProperty> 형식의 배열을 만듭니다.  첫 번째 식별자 필드는 <xref:System.Windows.Freezable>이 설정하는 데 사용되는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>의 속성용입니다.  다음 식별자 필드는 대상으로 할 <xref:System.Windows.Freezable>의 속성을 나타냅니다.  이것은 <xref:System.Windows.FrameworkElement> 개체에 <xref:System.Windows.Freezable>을 연결하는 속성 체인으로 간주할 수 있습니다.  
  
 다음은 사각형 요소의 <xref:System.Windows.Shapes.Shape.Fill%2A>을 설정하는 데 사용된 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.SolidColorBrush.Color%2A>를 대상으로 하는 종속성 속성 체인의 예제입니다.  
  
 [!code-csharp[storyboards_ovw_snip#135](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]  
  
 또한 <xref:System.Windows.PropertyPath.Path%2A>를 지정해야 합니다.  <xref:System.Windows.PropertyPath.Path%2A>는 해당 <xref:System.Windows.PropertyPath.PathParameters%2A>를 해석하는 방법을 <xref:System.Windows.PropertyPath.Path%2A>에 알려주는 <xref:System.String>입니다.  다음 구문이 사용됩니다.  
  
||  
|-|  
|`(`*OwnerPropertyArrayIndex*`).(`*FreezablePropertyArrayIndex*`)`|  
  
 Where  
  
-   *OwnerPropertyArrayIndex*는 <xref:System.Windows.Freezable>이 설정하는 데 사용되는 <xref:System.Windows.FrameworkElement> 개체 속성의 식별자를 포함하는 <xref:System.Windows.DependencyProperty> 배열의 인덱스입니다.  
  
-   *FreezablePropertyArrayIndex*는 대상으로 할 속성의 식별자를 포함하는 <xref:System.Windows.DependencyProperty> 배열의 인덱스입니다.  
  
 다음 예제에서는 이전 예제에 정의된 <xref:System.Windows.PropertyPath.PathParameters%2A>를 수반하는 <xref:System.Windows.PropertyPath.Path%2A>를 보여 줍니다.  
  
 [!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]  
  
 다음 예제에서는 사각형 요소의 <xref:System.Windows.Shapes.Shape.Fill%2A>을 설정하는 데 사용되는 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.SolidColorBrush.Color%2A>에 애니메이션 효과를 주기 위해 이전 예제의 코드를 결합합니다.  
  
 [!code-csharp[storyboards_ovw_snip#137](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]  
  
 컬렉션 또는 배열에 포함된 Freezable을 대상으로 해야 하는 경우가 있습니다.  예를 들어 사각형에서 해당 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 적용되는 <xref:System.Windows.Media.TransformGroup> 리소스가 있으며 포함된 변환 중 하나에 애니메이션 효과를 주려고 한다고 가정해 봅니다.  
  
 [!code-xml[storyboards_ovw_snip#142](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]  
  
 컬렉션에 포함된 <xref:System.Windows.Freezable>을 대상으로 하려면 다음 경로 구문을 사용합니다.  
  
||  
|-|  
|`(`*OwnerPropertyArrayIndex*`).(` *CollectionChildrenPropertyArrayIndex*`)` `[`*CollectionIndex* `].(`*FreezablePropertyArrayIndex*`)`|  
  
 여기서 *CollectionIndex*는 해당 배열 또는 컬렉션에 있는 개체의 인덱스입니다.  
  
 <xref:System.Windows.Media.TransformGroup>의 두 번째 변환인 <xref:System.Windows.Media.RotateTransform>의 <xref:System.Windows.Media.RotateTransform.Angle%2A> 속성을 대상으로 하려면 다음 <xref:System.Windows.PropertyPath.Path%2A> 및 <xref:System.Windows.PropertyPath.PathParameters%2A>를 사용합니다.  
  
 [!code-csharp[storyboards_ovw_snip#139](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]  
  
 다음 예제에서는 <xref:System.Windows.Media.TransformGroup> 내에 포함된 <xref:System.Windows.Media.RotateTransform>의 <xref:System.Windows.Media.RotateTransform.Angle%2A>에 애니메이션 효과를 주기 위한 완전한 코드를 보여 줍니다.  
  
 [!code-csharp[storyboards_ovw_snip#138](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]  
  
### Freezable을 시작점으로 사용하여 간접적으로 대상 지정  
 이전 단원에서는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>에서 시작하고 <xref:System.Windows.Freezable> 하위 속성에 대한 속성 체인을 만들어서 간접적으로 <xref:System.Windows.Freezable>을 대상으로 하는 방법에 대해 설명했습니다.  <xref:System.Windows.Freezable>을 시작점으로 사용하여 해당 <xref:System.Windows.Freezable> 하위 속성 중 하나를 간접적으로 대상으로 할 수도 있습니다.  <xref:System.Windows.Freezable>을 간접 대상 지정을 위한 시작점으로 사용할 때 추가로 적용되는 한 가지 제한 사항은 간접적으로 대상으로 지정된 하위 속성과의 사이에서 시작 <xref:System.Windows.Freezable> 및 모든 <xref:System.Windows.Freezable>이 고정되지 않아야 한다는 것입니다.  
  
<a name="controllable_storyboards"></a>   
## XAML에서 대화형으로 Storyboard 제어  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 Storyboard를 시작하려면 <xref:System.Windows.Media.Animation.BeginStoryboard> 트리거 동작을 사용합니다.  <xref:System.Windows.Media.Animation.BeginStoryboard>는 애니메이션 효과를 줄 개체와 속성에 애니메이션을 배포한 다음 Storyboard를 시작합니다.  \(이 프로세스에 대한 자세한 내용은 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)를 참조하십시오.\) <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> 속성을 지정하여 <xref:System.Windows.Media.Animation.BeginStoryboard>에 이름을 제공하면 제어 가능한 Storyboard로 만들 수 있습니다.  그러면 Storyboard를 시작한 후 대화형으로 제어할 수 있습니다.  다음은 Storyboard를 제어하기 위해 이벤트 트리거와 함께 사용하는 제어 가능한 Storyboard 작업 목록입니다.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Storyboard를 일시 중지합니다.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: 일시 중지한 Storyboard를 다시 시작합니다.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Storyboard의 속도를 변경합니다.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Storyboard를 해당 전체 기간\(있는 경우\)의 끝으로 진행합니다.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Storyboard를 중지합니다.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Storyboard를 제거합니다.  
  
 다음 예제에서는 제어 가능한 Storyboard 작업을 사용하여 대화형으로 Storyboard를 제어합니다.  
  
 [!code-xml[animation_ovws_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]  
  
<a name="controllable_storyboards_procedural"></a>   
## 코드를 사용하여 대화형으로 Storyboard 제어  
 이전 예제에서는 트리거 동작을 사용하여 애니메이션 효과를 주는 방법을 설명했습니다.  코드에서는 <xref:System.Windows.Media.Animation.Storyboard> 클래스의 대화형 메서드를 사용하여 Storyboard를 제어할 수도 있습니다.  <xref:System.Windows.Media.Animation.Storyboard>를 코드에서 대화형으로 만들려면 Storyboard의 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드에 대한 적절한 오버로드를 사용하고 제어 가능하도록 `true`로 지정해야 합니다.  자세한 내용은 <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29> 페이지를 참조하십시오.  
  
 다음 목록에서는 <xref:System.Windows.Media.Animation.Storyboard>를 시작된 후 조작하는 데 사용할 수 있는 메서드를 보여 줍니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>  
  
 이러한 메서드를 사용하면 <xref:System.Windows.Trigger> 또는 <xref:System.Windows.TriggerAction> 개체를 만들 필요가 없다는 이점이 있습니다. 조작할 제어 가능한 <xref:System.Windows.Media.Animation.Storyboard>에 대한 참조만 필요합니다.  
  
 **참고:**  <xref:System.Windows.Media.Animation.Clock>에 대해 수행했으며 그에 따라 <xref:System.Windows.Media.Animation.Storyboard>에 대해서도 수행된 모든 대화형 작업은 다음 렌더링 직전에 발생하는 타이밍 엔진의 다음 Tick 시 발생합니다.  예를 들어 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 메서드를 사용하여 애네니메이션의 다른 지점으로 이동할 경우 속성 값은 즉시 변경되지 않으며 타이밍 엔진의 다음 Tick에서 값이 변경됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard> 클래스의 대화형 메서드를 사용하여 애니메이션을 적용 및 제어하는 방법을 보여 줍니다.  
  
 [!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
 [!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]  
  
<a name="usingstoryboardsinstyles"></a>   
## 스타일에서 애니메이션 효과 주기  
 <xref:System.Windows.Media.Animation.Storyboard> 개체를 사용하여 <xref:System.Windows.Style>에서 애니메이션을 정의할 수 있습니다.  <xref:System.Windows.Style>에서 <xref:System.Windows.Media.Animation.Storyboard>를 사용하여 애니메이션 효과를 주는 것은 다음과 같은 세 가지 예외를 제외하고는 다른 곳에서 <xref:System.Windows.Media.Animation.Storyboard>를 사용하는 것과 비슷합니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>을 지정하지 않습니다. <xref:System.Windows.Media.Animation.Storyboard>는 <xref:System.Windows.Style>이 적용되는 요소를 항상 대상으로 합니다.  <xref:System.Windows.Freezable> 개체를 대상으로 하려면 간접 대상 지정을 사용해야 합니다.  간접 대상 지정에 대한 자세한 내용은 [간접 대상 지정](#pathsyntaxforchangeable) 단원을 참조하십시오.  
  
-   <xref:System.Windows.EventTrigger> 또는 <xref:System.Windows.Trigger>에 대한 <xref:System.Windows.EventTrigger.SourceName%2A>을 지정할 수 없습니다.  
  
-   동적 리소스 참조나 데이터 바인딩 표현식을 사용하여 <xref:System.Windows.Media.Animation.Storyboard> 또는 애니메니션 속성 값을 설정할 수 없습니다.  이는 <xref:System.Windows.Style> 안의 모든 항목이 스레드로부터 안전하며 타이밍 시스템은 이러한 항목을 스레드로부터 안전하게 만들기 위해 <xref:System.Windows.Media.Animation.Storyboard> 개체에 <xref:System.Windows.Freezable.Freeze%2A>을 수행해야 하기 때문입니다.  <xref:System.Windows.Media.Animation.Storyboard>는 동적 리소스 참조 또는 데이터 바인딩 표현식이 자신이나 자식 Timeline에 포함된 경우 고정할 수 없습니다.  고정과 기타 <xref:System.Windows.Freezable> 기능에 대한 자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서는 <xref:System.Windows.Media.Animation.Storyboard> 또는 애니메이션 이벤트에 대한 이벤트 처리기를 선언할 수 없습니다.  
  
 스타일에서 Storyboard를 정의하는 방법을 보여 주는 예제를 보려면 [스타일에서 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-style.md) 예제를 참조하십시오.  
  
<a name="defineAStoryboardInAControlTemplateSection"></a>   
## ControlTemplate에서 애니메이션 효과 주기  
 <xref:System.Windows.Media.Animation.Storyboard> 개체를 사용하여 <xref:System.Windows.Controls.ControlTemplate>에서 애니메이션을 정의할 수 있습니다.  <xref:System.Windows.Controls.ControlTemplate>에서 <xref:System.Windows.Media.Animation.Storyboard>를 사용하여 애니메이션 효과를 주는 것은 다음과 같은 두 가지 예외를 제외하고는 다른 곳에서 <xref:System.Windows.Media.Animation.Storyboard>를 사용하는 것과 비슷합니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>은 <xref:System.Windows.Controls.ControlTemplate>의 자식 개체만 참조할 수 있습니다.  <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>이 지정되지 않은 경우 애니메이션은 <xref:System.Windows.Controls.ControlTemplate>이 적용되는 요소를 대상으로 합니다.  
  
-   <xref:System.Windows.EventTrigger> 또는 <xref:System.Windows.Trigger>에 대한 <xref:System.Windows.EventTrigger.SourceName%2A>은 <xref:System.Windows.Controls.ControlTemplate>의 자식 개체만 참조할 수 있습니다.  
  
-   동적 리소스 참조나 데이터 바인딩 표현식을 사용하여 <xref:System.Windows.Media.Animation.Storyboard> 또는 애니메니션 속성 값을 설정할 수 없습니다.  이는 <xref:System.Windows.Controls.ControlTemplate> 안의 모든 항목이 스레드로부터 안전하며 타이밍 시스템은 이러한 항목을 스레드로부터 안전하게 만들기 위해 <xref:System.Windows.Media.Animation.Storyboard> 개체에 <xref:System.Windows.Freezable.Freeze%2A>을 수행해야 하기 때문입니다.  <xref:System.Windows.Media.Animation.Storyboard>는 동적 리소스 참조 또는 데이터 바인딩 표현식이 자신이나 자식 Timeline에 포함된 경우 고정할 수 없습니다.  고정과 기타 <xref:System.Windows.Freezable> 기능에 대한 자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서는 <xref:System.Windows.Media.Animation.Storyboard> 또는 애니메이션 이벤트에 대한 이벤트 처리기를 선언할 수 없습니다.  
  
 <xref:System.Windows.Controls.ControlTemplate>에서 Storyboard를 정의하는 방법에 대한 예제를 보려면 [ControlTemplate에서 애니메이션 효과 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md) 예제를 참조하십시오.  
  
<a name="animateWhenAPropertyValueChanges"></a>   
## 속성 값 변경 시에 애니메니션 효과 주기  
 스타일 및 컨트롤 템플릿에서 Trigger 개체를 사용하여 속성 변경 시에 Storyboard를 시작할 수 있습니다.  예제를 보려면 [속성 값이 변경될 때 애니메이션 트리거](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md) 및 [ControlTemplate에서 애니메이션 효과 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md)를 참조하십시오.  
  
 속성 <xref:System.Windows.Trigger> 개체에 의해 적용된 애니메이션은 <xref:System.Windows.EventTrigger> 애니메이션 또는 <xref:System.Windows.Media.Animation.Storyboard> 메서드를 사용하여 시작된 애니메이션보다 복잡한 방식으로 작동합니다.  이러한 애니메이션은 다른 <xref:System.Windows.Trigger> 개체에 의해 정의된 애니메이션과 "핸드오프"하지만 <xref:System.Windows.EventTrigger> 및 메서드에서 트리거한 애니메이션으로 구성됩니다.  
  
## 참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)