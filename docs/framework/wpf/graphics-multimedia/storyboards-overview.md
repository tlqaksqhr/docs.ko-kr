---
title: Storyboard 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboard syntax [WPF]
- syntax [WPF], Storyboard
- timelines [WPF]
ms.assetid: 1a698c3c-30f1-4b30-ae56-57e8a39811bd
ms.openlocfilehash: a7f9539cd3ac571977a91cd4e7dce07d641af3b6
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932323"
---
# <a name="storyboards-overview"></a>Storyboard 개요
이 항목에서는 사용 하는 방법을 보여 줍니다. <xref:System.Windows.Media.Animation.Storyboard> 개체를 구성 하 고 애니메이션을 적용 합니다. 대화형으로 조작 하는 방법에 설명 합니다 <xref:System.Windows.Media.Animation.Storyboard> 개체 및 간접 속성 대상 지정 구문에 설명 합니다.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>전제 조건  
 이 항목을 이해하려면 다양한 애니메이션 형식과 해당 기본 기능에 대해 잘 알고 있어야 합니다. 애니메이션 소개를 보려면 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하세요. 또한 연결된 속성을 사용하는 방법을 알아야 합니다. 연결된 속성에 대한 자세한 내용은 [연결된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)를 참조하세요.  
  
<a name="whatisatimeline"></a>   
## <a name="what-is-a-storyboard"></a>Storyboard란?  
 애니메이션만이 타임라인의 유용한 형식은 아닙니다. 타임라인의 집합을 구성하고 속성에 타임라인을 적용하는 데 도움이 되는 다른 타임라인 클래스도 제공됩니다. 컨테이너 타임 라인에서 파생 된 <xref:System.Windows.Media.Animation.TimelineGroup> 클래스를 포함 <xref:System.Windows.Media.Animation.ParallelTimeline> 및 <xref:System.Windows.Media.Animation.Storyboard>합니다.  
  
 <xref:System.Windows.Media.Animation.Storyboard> 있기 타임 라인에 대 한 대상 지정 정보를 제공 하는 컨테이너 타임 라인의 형식입니다. 스토리 보드에는 모든 유형의 포함 될 수 있습니다 <xref:System.Windows.Media.Animation.Timeline>, 다른 컨테이너 타임 라인 및 애니메이션을 포함 합니다. <xref:System.Windows.Media.Animation.Storyboard> 개체를 사용 하 여 다양 한 개체 및 속성을 단일 타임 라인 트리로 쉽게 구성 하 고 복잡 한 타이밍 동작을 제어 하에 영향을 주는 타임 라인을 결합할 수 있습니다. 예를 들어 다음 세 가지 작업을 수행하는 단추가 필요하다고 가정해 봅니다.  
  
-   단추를 선택하면 단추가 커지고 색이 변경됩니다.  
  
-   클릭할 때 축소되었다가 다시 원래 크기로 커집니다.  
  
-   사용되지 않도록 설정되면 축소되었다가 50% 불투명도로 페이드됩니다.  
  
 이 경우 동일한 개체에 적용되는 여러 애니메이션 집합이 있고 단추 상태에 따라 다른 시간에 재생하려고 합니다. <xref:System.Windows.Media.Animation.Storyboard> 개체를 사용 하 여 애니메이션을 구성 하 고 하나 이상의 개체 그룹에 적용할 수 있습니다.  
  
<a name="wherecanyouuseastoryboard"></a>   
## <a name="where-can-you-use-a-storyboard"></a>Storyboard를 사용할 수 있는 위치  
 A <xref:System.Windows.Media.Animation.Storyboard> 애니메이션 효과 줄 클래스의 종속성 속성에 애니메이션 효과를 사용할 수 있습니다 (점에서 클래스 애니메이션을 적용 하는 방법에 대 한 자세한 내용은 참조는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)). 그러나 스토리 보 딩은 프레임 워크 수준 기능 이므로 개체에 속해야 합니다 <xref:System.Windows.NameScope> 의 한 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>합니다.  
  
 예를 들어 사용할 수 있습니다는 <xref:System.Windows.Media.Animation.Storyboard> 다음을 수행 합니다.  
  
-   애니메이션 효과 <xref:System.Windows.Media.SolidColorBrush> 단추의 배경색을 칠하는 (비 워크 프레임 요소) (형식의 <xref:System.Windows.FrameworkElement>),  
  
-   에 애니메이션 효과 주기를 <xref:System.Windows.Media.SolidColorBrush> 의 채우기를 칠하는 (비 워크 프레임 요소)를 <xref:System.Windows.Media.GeometryDrawing> (비 워크 프레임 요소)를 사용 하 여 표시 되는 <xref:System.Windows.Controls.Image> (<xref:System.Windows.FrameworkElement>).  
  
-   코드에 애니메이션 효과 주기를 <xref:System.Windows.Media.SolidColorBrush> 포함 하는 클래스에서 선언 된를 <xref:System.Windows.FrameworkElement>이면 합니다 <xref:System.Windows.Media.SolidColorBrush> 는 사용 하 여 해당 이름을 등록 <xref:System.Windows.FrameworkElement>합니다.  
  
 그러나 사용할 수 없는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션 효과를 주는 <xref:System.Windows.Media.SolidColorBrush> 사용 하 여 이름을 등록 하지 않았거나를 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>의 속성 설정에 사용 되지 않은 또는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>.  
  
<a name="applyanimationswithastoryboard"></a>   
## <a name="how-to-apply-animations-with-a-storyboard"></a>Storyboard를 사용하여 애니메이션을 적용하는 방법  
 사용 하는 <xref:System.Windows.Media.Animation.Storyboard> 구성 하 고 애니메이션 적용을 추가한 애니메이션의 자식 타임 라인으로는 <xref:System.Windows.Media.Animation.Storyboard>합니다. 합니다 <xref:System.Windows.Media.Animation.Storyboard> 클래스를 제공 합니다 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType> 연결 된 속성입니다. 애니메이션에 이러한 속성을 설정하여 해당 대상 개체 및 속성을 지정합니다.  
  
 먼저 해당 대상에 애니메이션을 적용 하는 <xref:System.Windows.Media.Animation.Storyboard> 트리거 작업 또는 메서드를 사용 하 여 합니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 사용을 <xref:System.Windows.Media.Animation.BeginStoryboard> 개체를 <xref:System.Windows.EventTrigger>를 <xref:System.Windows.Trigger>, 또는 <xref:System.Windows.DataTrigger>합니다. 코드에서 사용할 수도 있습니다는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드.  
  
 다음 표에서 다양 한 위치를 보여 줍니다. 여기서 각 <xref:System.Windows.Media.Animation.Storyboard> 시작 기술이 지원 되: 인스턴스별, 스타일, 컨트롤 템플릿 및 데이터 템플릿. "인스턴스별"은 스타일, 컨트롤 템플릿 또는 데이터 템플릿이 아닌 개체의 인스턴스에 직접 애니메이션 또는 storyboard를 적용하는 기술을 나타냅니다.  
  
|storyboard 시작 방법...|인스턴스별|스타일|컨트롤 템플릿|데이터 템플릿|예|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 및 <xref:System.Windows.EventTrigger>|예|예|예|예|[Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 속성 <xref:System.Windows.Trigger>|아니요|예|예|예|[속성 값이 변경될 때 애니메이션 트리거](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 및 <xref:System.Windows.DataTrigger>|아니요|예|예|예|[방법: 데이터가 변경될 때 애니메이션 트리거Changes](http://msdn.microsoft.com/library/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드|예|아니요|아니요|아니요|[Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션 효과를 주는 합니다 <xref:System.Windows.FrameworkElement.Width%2A> 의 <xref:System.Windows.Shapes.Rectangle> 요소 및 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 의 <xref:System.Windows.Media.SolidColorBrush> 를 그리는 데 <xref:System.Windows.Shapes.Rectangle>.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]  
  
 [!code-csharp[storyboards_ovw_snip#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]  
  
 다음 섹션에서는 합니다 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 자세히 속성을 연결 합니다.  
  
<a name="targetingelementsandfreezables"></a>   
## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>프레임워크 요소, 프레임워크 콘텐츠 요소 및 Freezable을 대상으로 지정  
 이전 섹션에서는 애니메이션이 대상을 찾기 위해서는 대상의 이름 및 애니메이션 효과를 주려는 속성을 알고 있어야 한다는 사실을 언급했습니다. 속성에 애니메이션 효과를 지정 하는 간단 합니다: 설정 하기만 하면 됩니다 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType> 애니메이션 효과를 줄 속성의 이름입니다.  해당 속성을 설정 하 여 애니메이션 효과 주려는 개체의 이름을 지정 하는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> 애니메이션 속성입니다.  
  
 에 대 한는 <xref:System.Windows.Setter.TargetName%2A> 하려면 속성 대상된 개체에는 이름이 있어야 합니다. 에 이름을 할당 한 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 에 이름을 할당 다릅니다를 <xref:System.Windows.Freezable> 개체.  
  
 프레임 워크 요소는 해당 클래스에서 상속 되는 <xref:System.Windows.FrameworkElement> 클래스입니다. 프레임 워크 요소의 예로 <xref:System.Windows.Window>, <xref:System.Windows.Controls.DockPanel>를 <xref:System.Windows.Controls.Button>, 및 <xref:System.Windows.Shapes.Rectangle>합니다. 기본적으로 모든 창, 패널 및 컨트롤은 요소입니다. 프레임 워크 콘텐츠 요소는 해당 클래스에서 상속 되는 <xref:System.Windows.FrameworkContentElement> 클래스입니다. 프레임 워크 콘텐츠 요소의 예로 <xref:System.Windows.Documents.FlowDocument> 고 <xref:System.Windows.Documents.Paragraph>입니다. 형식이 프레임워크 요소인지 또는 프레임워크 콘텐츠 요소인지 확실하지 않은 경우 Name 속성을 가지는지 여부를 확인합니다. 이 속성을 가질 경우 프레임워크 요소이거나 프레임워크 콘텐츠 요소일 것입니다. 확실히 하려면 해당 형식 페이지의 상속 계층 구조 섹션을 확인합니다.  
  
 프레임 워크 요소 또는 프레임 워크 콘텐츠 요소에서 대상으로 사용할 수 있도록 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 설정한 해당 <xref:System.Windows.FrameworkElement.Name%2A> 속성입니다. 코드에도 사용 해야 합니다 <xref:System.Windows.NameScope.RegisterName%2A> 를 만든 요소를 사용 하 여 요소 이름을 등록 하는 메서드를 <xref:System.Windows.NameScope>입니다.  
  
 다음 예제에서는 앞의 예제에서 가져온 이름을 할당 `MyRectangle` 는 <xref:System.Windows.Shapes.Rectangle>, 형식의 <xref:System.Windows.FrameworkElement>합니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]  
  
 [!code-csharp[storyboards_ovw_snip#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]  
  
 이름이 지정되면 해당 요소의 속성에 애니메이션 효과를 줄 수 있습니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]  
  
 [!code-csharp[storyboards_ovw_snip#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]  
  
 <xref:System.Windows.Freezable> 형식은 해당 클래스에서 상속 되는 <xref:System.Windows.Freezable> 클래스입니다. 예가 <xref:System.Windows.Freezable> 포함할 <xref:System.Windows.Media.SolidColorBrush>를 <xref:System.Windows.Media.RotateTransform>, 및 <xref:System.Windows.Media.GradientStop>합니다.  
  
 대상으로 지정할 수 있도록를 <xref:System.Windows.Freezable> 에서 애니메이션에 의해 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 사용할 합니다 [X:name 지시문](../../../../docs/framework/xaml-services/x-name-directive.md) 이름을 할당할 합니다. 코드를 사용 하 여는 <xref:System.Windows.NameScope.RegisterName%2A> 메서드를 만든 요소를 사용 하 여 해당 이름을 등록 하는 <xref:System.Windows.NameScope>합니다.  
  
 다음 예제에 이름을 할당 한 <xref:System.Windows.Freezable> 개체입니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]  
  
 [!code-csharp[storyboards_ovw_snip#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]  
  
 그런 후 개체를 애니메이션 대상으로 지정할 수 있습니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]  
  
 [!code-csharp[storyboards_ovw_snip#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]  
  
 <xref:System.Windows.Media.Animation.Storyboard> 개체 이름 범위를 사용 하 여 해결 하는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 속성입니다. WPF 이름 범위에 대한 자세한 내용은 [WPF XAML 이름 범위](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)를 참조하세요. 경우는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 속성을 생략 하면, 애니메이션 정의 된 또는 스타일의 요소 스타일의 경우 요소를 대상으로 합니다.  
  
 경우에 따라 이름을 할당할 수 없습니다는 <xref:System.Windows.Freezable> 개체입니다. 예를 들어 경우는 <xref:System.Windows.Freezable> 리소스로 선언 되거나 스타일에서 속성 값을 설정 하는 데 사용 되 이름을 부여할 수 없습니다. 이름이 없기 때문에 직접적으로 대상으로 지정할 수 없지만 간접적으로 지정할 수는 있습니다. 다음 섹션에서는 간접 대상 지정을 사용하는 방법을 설명합니다.  
  
<a name="pathsyntaxforchangeable"></a>   
## <a name="indirect-targeting"></a>간접 대상 지정  
 경우가 <xref:System.Windows.Freezable> 때와 같이 애니메이션으로 직접 대상으로 지정할 수는 <xref:System.Windows.Freezable> 리소스로 선언 되거나 스타일에서 속성 값을 설정 하는 데 사용 되 합니다. 이러한 경우를 직접 대상으로 하는 경우에 여전히 애니메이션을 적용할 수는 <xref:System.Windows.Freezable> 개체입니다. 설정 하는 대신 합니다 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 속성의 이름으로는 <xref:System.Windows.Freezable>, 게 요소의 이름입니다는 <xref:System.Windows.Freezable> "속해 있습니다." 예를 들어, 한 <xref:System.Windows.Media.SolidColorBrush> 설정 하는 데는 <xref:System.Windows.Shapes.Shape.Fill%2A> 사각형의 요소는 사각형에 속합니다. 애니메이션의 브러시에 애니메이션 효과를 설정 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 프레임 워크 요소 또는 프레임 워크 콘텐츠 요소 속성에서 시작 하는 속성의 체인을 사용 하 여는 <xref:System.Windows.Freezable> 설정 하는 데 사용 된 및로 끝나는 <xref:System.Windows.Freezable> 애니메이션 속성입니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]  
  
 [!code-csharp[storyboards_ovw_snip#134](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]  
  
 이면는 <xref:System.Windows.Freezable> 는 고정 클론 만들어질 및 해당 복제본 애니메이션 효과가 적용 됩니다. 이 경우 원래 개체의 <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> 반환할 속성 계속 `false`이므로 원래 개체가 실제로 애니메이션이 적용 되지는 않습니다. 복제 하는 방법에 대 한 자세한 내용은 참조는 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)합니다.  
  
 또한 간접 속성 대상 지정을 사용할 경우에는 존재하지 않는 개체를 대상으로 지정할 수 있습니다. 예를 들어는 생각할 수 있습니다는 <xref:System.Windows.Controls.Control.Background%2A> 특정 단추를 사용 하 여 설정 된를 <xref:System.Windows.Media.SolidColorBrush> 때 실제로 해당 색에 애니메이션 효과를 시도 <xref:System.Windows.Media.LinearGradientBrush> 단추의 배경을 설정 하는 데 사용 되었습니다. 이러한 경우 예외가 throw 되지 않습니다. 애니메이션 때문에 시각적 효과를 나타내지 못합니다 <xref:System.Windows.Media.LinearGradientBrush> 변경에 반응 하지 않습니다는 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 속성입니다.  
  
 다음 섹션에서는 간접 속성 대상 지정 구문을 좀 더 자세히 설명합니다.  
  
<a name="xamlsyntaxchangeableproperty"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>XAML에서 Freezable 속성을 간접적으로 대상으로 지정  
 Freezable의 속성을 대상으로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 다음 구문을 사용 합니다.  
  
| |  
|-|  
|*ElementPropertyName* `.` *FreezablePropertyName*|  
  
 Where  
  
-   *ElementPropertyName* 의 속성을 <xref:System.Windows.FrameworkElement> 는 <xref:System.Windows.Freezable> 을 설정 하는 데 사용 됩니다 및  
  
-   *FreezablePropertyName* 의 속성을 <xref:System.Windows.Freezable> 애니메이션 효과를 합니다.  
  
 다음 코드는 애니메이션을 적용 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 의 <xref:System.Windows.Media.SolidColorBrush> 설정 하는 데는  
  
 <xref:System.Windows.Shapes.Shape.Fill%2A> 사각형 요소입니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]  
  
 컬렉션 또는 배열에 포함된 Freezable을 대상으로 지정해야 하는 경우도 있습니다.  
  
 컬렉션에 포함된 Freezable을 대상으로 지정하려면 다음 경로 구문을 사용합니다.  
  
| |  
|-|  
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|  
  
 여기서 *CollectionIndex* 해당 배열 또는 컬렉션에 있는 개체의 인덱스입니다.  
  
 예를 들어 사각형에는 <xref:System.Windows.Media.TransformGroup> 리소스에 적용 된 해당 <xref:System.Windows.UIElement.RenderTransform%2A> 속성 애니메이션 효과 주려는 포함 된 변환 중 하나입니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]  
  
 다음 코드는 애니메이션을 적용 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.RotateTransform.Angle%2A> 의 속성을 <xref:System.Windows.Media.RotateTransform> 이전 예에서 같이 합니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#35](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]  
  
<a name="targetingpropertyofchangeableincode"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>코드에서 Freezable 속성을 간접적으로 대상으로 지정  
 만든 코드를 <xref:System.Windows.PropertyPath> 개체입니다. 만들 때 합니다 <xref:System.Windows.PropertyPath>를 지정할를 <xref:System.Windows.PropertyPath.Path%2A> 및 <xref:System.Windows.PropertyPath.PathParameters%2A>합니다.  
  
 만들려는 <xref:System.Windows.PropertyPath.PathParameters%2A>, 한 형식의 배열을 만들고 <xref:System.Windows.DependencyProperty> 종속성 속성 식별자 필드의 목록을 포함 하는 합니다. 첫 번째 식별자 필드의 속성은 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 는 <xref:System.Windows.Freezable> 설정 하는 데 사용 됩니다. 다음 식별자 필드의 속성을 나타내는 <xref:System.Windows.Freezable> 대상으로 합니다. 연결 하는 속성 체인으로 생각해 합니다 <xref:System.Windows.Freezable> 에 <xref:System.Windows.FrameworkElement> 개체입니다.  
  
 다음은 대상으로 하는 종속성 속성 체인의 예는 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 의 <xref:System.Windows.Media.SolidColorBrush> 설정 하는 데는 <xref:System.Windows.Shapes.Shape.Fill%2A> 사각형 요소의 합니다.  
  
 [!code-csharp[storyboards_ovw_snip#135](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]  
  
 지정 해야는 <xref:System.Windows.PropertyPath.Path%2A>합니다. <xref:System.Windows.PropertyPath.Path%2A> 는 <xref:System.String> 되었음을 알리는 합니다 <xref:System.Windows.PropertyPath.Path%2A> 해석 하는 방법을 해당 <xref:System.Windows.PropertyPath.PathParameters%2A>. 여기서는 다음 구문을 사용합니다.  
  
| |  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *FreezablePropertyArrayIndex* `)`|  
  
 Where  
  
-   *OwnerPropertyArrayIndex* 의 인덱스를 <xref:System.Windows.DependencyProperty> 의 식별자를 포함 하는 배열 합니다 <xref:System.Windows.FrameworkElement> 개체의 속성은는 <xref:System.Windows.Freezable> 을 설정 하는 데 사용 됩니다 및  
  
-   *FreezablePropertyArrayIndex* 의 인덱스를 <xref:System.Windows.DependencyProperty> 대상 속성의 식별자를 포함 하는 배열입니다.  
  
 다음 예제와 <xref:System.Windows.PropertyPath.Path%2A> 와 함께 <xref:System.Windows.PropertyPath.PathParameters%2A> 앞의 예제에서 정의 합니다.
  
 [!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]  
  
 애니메이션 효과를 주는 이전 예제에서 코드를 결합 하는 다음 예제에서는 합니다 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 의 <xref:System.Windows.Media.SolidColorBrush> 설정 하는 데는 <xref:System.Windows.Shapes.Shape.Fill%2A> 사각형 요소의 합니다.  
  
 [!code-csharp[storyboards_ovw_snip#137](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]  
  
 컬렉션 또는 배열에 포함된 Freezable을 대상으로 지정해야 하는 경우도 있습니다. 예를 들어 사각형에는 <xref:System.Windows.Media.TransformGroup> 리소스에 적용 된 해당 <xref:System.Windows.UIElement.RenderTransform%2A> 속성 애니메이션 효과 주려는 포함 된 변환 중 하나입니다.  
  
 [!code-xaml[storyboards_ovw_snip#142](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]  
  
 대상에는 <xref:System.Windows.Freezable> 다음 경로 구문을 사용 하면 컬렉션에 포함 합니다.  
  
| |  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *CollectionChildrenPropertyArrayIndex* `)` `[` *CollectionIndex* `].(` *FreezablePropertyArrayIndex* `)`|  
  
 여기서 *CollectionIndex* 해당 배열 또는 컬렉션에 있는 개체의 인덱스입니다.  
  
 대상에는 <xref:System.Windows.Media.RotateTransform.Angle%2A> 의 속성을 <xref:System.Windows.Media.RotateTransform>에서 두 번째 변환에는 <xref:System.Windows.Media.TransformGroup>, 다음을 사용 하 <xref:System.Windows.PropertyPath.Path%2A> 및 <xref:System.Windows.PropertyPath.PathParameters%2A>.  
  
 [!code-csharp[storyboards_ovw_snip#139](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]  
  
 다음 예제에서는 애니메이션에 대 한 전체 코드는 <xref:System.Windows.Media.RotateTransform.Angle%2A> 의 <xref:System.Windows.Media.RotateTransform> 내에 포함 된를 <xref:System.Windows.Media.TransformGroup>입니다.  
  
 [!code-csharp[storyboards_ovw_snip#138](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]  
  
### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>Freezable을 시작 지점으로 사용해서 간접적으로 대상 지정  
 이전 섹션에는 간접적으로 대상 하는 방법을 설명를 <xref:System.Windows.Freezable> 부터 시작 하 여는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 속성 체인을 만들고는 <xref:System.Windows.Freezable> 하위 속성입니다. 사용할 수도 있습니다는 <xref:System.Windows.Freezable> 시작 지점를 간접적으로 대상 중 하나는 <xref:System.Windows.Freezable> 하위 속성입니다. 사용할 때 추가적인 제한이 적용을 <xref:System.Windows.Freezable> 간접 대상 지정에 대 한 시작 점으로: 시작 <xref:System.Windows.Freezable> 매 <xref:System.Windows.Freezable> 간접적으로 대상된 하위 속성 간의 없습니다를 고정 해야 합니다.  
  
<a name="controllable_storyboards"></a>   
## <a name="interactively-controlling-a-storyboard-in-xaml"></a>XAML에서 Storyboard를 대화형으로 제어  
 Storyboard를 시작 하려면 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 사용을 <xref:System.Windows.Media.Animation.BeginStoryboard> 동작을 트리거합니다. <xref:System.Windows.Media.Animation.BeginStoryboard> 개체 및 이러한, 애니메이션 및 storyboard를 시작 하는 속성에 애니메이션을 배포 합니다. (이 프로세스에 대 한 자세한 내용은 참조는 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).) 제공 하는 경우는 <xref:System.Windows.Media.Animation.BeginStoryboard> 이름을 지정 하 여 해당 <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> 속성을 만들면 제어 가능한 storyboard입니다. 그러면 Storyboard를 시작한 후에 대화형으로 제어할 수 있습니다. 다음은 Storyboard를 제어하기 위해 이벤트 트리거와 함께 사용하는 제어 가능한 Storyboard 작업 목록입니다.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Storyboard를 일시 중지 합니다.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: 일시 중지 된 storyboard를 다시 시작합니다.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Storyboard 속도 변경합니다.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: 있는 경우 채우기 기간이의 끝에 스토리 보드를 이동 합니다.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Storyboard를 중지 합니다.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Storyboard를 제거합니다.  
  
 다음 예제에서는 제어 가능한 Storyboard 작업이 Storyboard를 대화형으로 제어하는 데 사용됩니다.  
  
 [!code-xaml[animation_ovws_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]  
  
<a name="controllable_storyboards_procedural"></a>   
## <a name="interactively-controlling-a-storyboard-by-using-code"></a>코드를 사용하여 Storyboard를 대화형으로 제어  
 앞의 예제에서는 트리거 작업을 사용해서 애니메이션 효과를 적용하는 방법을 살펴보았습니다. 코드를 제어할 수도 있습니다의 대화형 메서드를 사용 하 여 스토리 보드를 <xref:System.Windows.Media.Animation.Storyboard> 클래스입니다. 에 대 한는 <xref:System.Windows.Media.Animation.Storyboard> 되도록 코드에서 대화형으로, 해당 스토리 보드의 오버 로드를 사용 해야 합니다 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 지정 하 고 `true` 제어할 수 있도록 합니다. 참조 된 <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29> 자세한 페이지입니다.  
  
 다음은 조작에 사용할 수 있는 메서드를 보여 줍니다.는 <xref:System.Windows.Media.Animation.Storyboard> 시작 된 후:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>  
  
 이러한 메서드를 사용 하는 이점은 만들 필요가 없습니다 <xref:System.Windows.Trigger> 또는 <xref:System.Windows.TriggerAction> 개체;를 제어할 수에 대 한 참조 하기만 하면 <xref:System.Windows.Media.Animation.Storyboard> 조작 하려고 합니다.  
  
 **참고:** 에서 수행 되는 모든 대화형 작업을 <xref:System.Windows.Media.Animation.Clock>, 및 또는 <xref:System.Windows.Media.Animation.Storyboard> 다음 렌더링 직전 발생 하는 타이밍 엔진의 다음 틱에서 발생 합니다. 예를 들어, 사용 하는 경우는 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 타이밍 엔진의 다음 틱에서 값을 변경 하는 대신, 속성 값을 애니메이션의 다른 지점으로 이동 하는 방법 즉시 변경 되지 않습니다.  
  
 다음 예제에서는 적용의 대화형 메서드를 사용 하 여 애니메이션 제어 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.Storyboard> 클래스입니다.  
  
 [!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
 [!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]  
  
<a name="usingstoryboardsinstyles"></a>   
## <a name="animate-in-a-style"></a>스타일에서 애니메이션 효과 주기  
 사용할 수 있습니다 <xref:System.Windows.Media.Animation.Storyboard> 개체에 애니메이션을 정의 하는 <xref:System.Windows.Style>합니다. 사용 하 여 애니메이션 효과 적용을 <xref:System.Windows.Media.Animation.Storyboard> 에 <xref:System.Windows.Style> 사용 하는 것과 비슷합니다는 <xref:System.Windows.Media.Animation.Storyboard> 다음 세 가지 예외를 사용 하 여 다른 곳에서:  
  
-   지정 하지 않으면를 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>; <xref:System.Windows.Media.Animation.Storyboard> 항상 요소를 대상으로 하는 <xref:System.Windows.Style> 적용 됩니다. 대상 <xref:System.Windows.Freezable> 개체 간접 대상 지정을 사용 해야 합니다. 간접 대상 지정 하는 방법에 대 한 자세한 내용은 참조는 [간접 대상 지정](#pathsyntaxforchangeable) 섹션입니다.  
  
-   지정할 수 없습니다는 <xref:System.Windows.EventTrigger.SourceName%2A> 에 대 한는 <xref:System.Windows.EventTrigger> 또는 <xref:System.Windows.Trigger>합니다.  
  
-   설정 하려면 동적 리소스 참조 또는 데이터 바인딩 식을 사용할 수 없습니다 <xref:System.Windows.Media.Animation.Storyboard> 또는 애니메이션 속성 값입니다. 있기 때문입니다 내의 모든 항목을 <xref:System.Windows.Style> 스레드로부터 안전 해야 하며 타이밍 시스템 <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> 개체를 스레드로부터 안전 합니다. <xref:System.Windows.Media.Animation.Storyboard> 또는 해당 자식 타임 라인이 동적 리소스 참조 또는 데이터 바인딩 식을 포함 하는 경우 고정 될 수 없습니다. 고정 및 기타에 대 한 자세한 내용은 <xref:System.Windows.Freezable> 기능을 참조 합니다 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)합니다.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 대 한 이벤트 처리기를 선언할 수 없습니다 <xref:System.Windows.Media.Animation.Storyboard> 또는 애니메이션 이벤트입니다.  
  
 스타일의 storyboard를 정의 하는 방법을 보여 주는 예제를 참조 합니다 [스타일에서 애니메이션 효과 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-style.md) 예제입니다.  
  
<a name="defineAStoryboardInAControlTemplateSection"></a>   
## <a name="animate-in-a-controltemplate"></a>ControlTemplate에서 애니메이션 효과 적용  
 사용할 수 있습니다 <xref:System.Windows.Media.Animation.Storyboard> 개체에 애니메이션을 정의 하는 <xref:System.Windows.Controls.ControlTemplate>합니다. 사용 하 여 애니메이션 효과 적용을 <xref:System.Windows.Media.Animation.Storyboard> 에 <xref:System.Windows.Controls.ControlTemplate> 사용 하는 것과 비슷합니다는 <xref:System.Windows.Media.Animation.Storyboard> 다음 두 가지 예외를 사용 하 여 다른 곳에서:  
  
-   합니다 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 의 자식 개체만 참조할 수는 <xref:System.Windows.Controls.ControlTemplate>합니다. 하는 경우 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 지정 하지 않으면 애니메이션 대상으로 지정 하는 요소는 <xref:System.Windows.Controls.ControlTemplate> 적용 됩니다.  
  
-   합니다 <xref:System.Windows.EventTrigger.SourceName%2A> 에 대 한는 <xref:System.Windows.EventTrigger> 또는 <xref:System.Windows.Trigger> 의 자식 개체만 참조할 수는 <xref:System.Windows.Controls.ControlTemplate>합니다.  
  
-   설정 하려면 동적 리소스 참조 또는 데이터 바인딩 식을 사용할 수 없습니다 <xref:System.Windows.Media.Animation.Storyboard> 또는 애니메이션 속성 값입니다. 있기 때문입니다 내의 모든 항목을 <xref:System.Windows.Controls.ControlTemplate> 스레드로부터 안전 해야 하며 타이밍 시스템 <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> 개체를 스레드로부터 안전 합니다. <xref:System.Windows.Media.Animation.Storyboard> 또는 해당 자식 타임 라인이 동적 리소스 참조 또는 데이터 바인딩 식을 포함 하는 경우 고정 될 수 없습니다. 고정 및 기타에 대 한 자세한 내용은 <xref:System.Windows.Freezable> 기능을 참조 합니다 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)합니다.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 대 한 이벤트 처리기를 선언할 수 없습니다 <xref:System.Windows.Media.Animation.Storyboard> 또는 애니메이션 이벤트입니다.  
  
 스토리 보드를 정의 하는 방법을 보여 주는 예제는 <xref:System.Windows.Controls.ControlTemplate>를 참조 합니다 [ControlTemplate에서 애니메이션 효과 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md) 예제.  
  
<a name="animateWhenAPropertyValueChanges"></a>   
## <a name="animate-when-a-property-value-changes"></a>속성 값이 변경될 때 애니메이션 효과 주기  
 스타일 및 컨트롤 템플릿에서 트리거 개체를 사용하여 속성이 변경될 때 Storyboard를 시작할 수 있습니다. 예제를 보려면 [는 애니메이션 변경 될 때 속성 값을 트리거할](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md) 하 고 [ControlTemplate에서 애니메이션 효과 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md).  
  
 속성에 의해 적용 된 애니메이션 <xref:System.Windows.Trigger> 개체 보다 더 복잡 한 방식으로 동작 <xref:System.Windows.EventTrigger> 애니메이션이 나 애니메이션 사용을 시작 <xref:System.Windows.Media.Animation.Storyboard> 메서드.  이러한 "전달" 애니메이션을 사용 하 여 다른 정의한 <xref:System.Windows.Trigger> 개체를 사용 하 여 하지만 구성 <xref:System.Windows.EventTrigger> 및 메서드 트리거 애니메이션 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
