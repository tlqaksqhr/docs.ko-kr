---
title: "Storyboard 개요"
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
- Storyboard syntax [WPF]
- syntax [WPF], Storyboard
- timelines [WPF]
ms.assetid: 1a698c3c-30f1-4b30-ae56-57e8a39811bd
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 614b5cc4843dbb886fa9cb02c56b28452e9fae8a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="storyboards-overview"></a>Storyboard 개요
이 항목에서는 사용 하는 방법을 보여 줍니다. <xref:System.Windows.Media.Animation.Storyboard> 개체를 구성 하 고 애니메이션을 적용 합니다. 대화형으로 조작 하는 방법을 설명 <xref:System.Windows.Media.Animation.Storyboard> 개체 및 대상 지정 구문 간접 속성에 설명 합니다.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>필수 구성 요소  
 이 항목을 이해하려면 다양한 애니메이션 형식과 해당 기본 기능에 대해 잘 알고 있어야 합니다. 애니메이션 소개를 보려면 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하세요. 또한 연결된 속성을 사용하는 방법을 알아야 합니다. 연결된 속성에 대한 자세한 내용은 [연결된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)를 참조하세요.  
  
<a name="whatisatimeline"></a>   
## <a name="what-is-a-storyboard"></a>Storyboard란?  
 애니메이션만이 타임라인의 유용한 형식은 아닙니다. 타임라인의 집합을 구성하고 속성에 타임라인을 적용하는 데 도움이 되는 다른 타임라인 클래스도 제공됩니다. 파생 되는 컨테이너 타임 라인의 <xref:System.Windows.Media.Animation.TimelineGroup> 클래스와 포함 <xref:System.Windows.Media.Animation.ParallelTimeline> 및 <xref:System.Windows.Media.Animation.Storyboard>합니다.  
  
 A <xref:System.Windows.Media.Animation.Storyboard> 포함 된 타임 라인에 대 한 대상 정보를 제공 하는 컨테이너 타임 라인의 형식입니다. 스토리 보드에는 모든 종류의 포함 될 수 있습니다 <xref:System.Windows.Media.Animation.Timeline>, 다른 컨테이너 타임 라인 및 애니메이션을 포함 합니다. <xref:System.Windows.Media.Animation.Storyboard>개체를 사용 하 여 다양 한 개체 및 속성을 쉽게 구성 하 고 복잡 한 타이밍 동작을 제어 하는 단일 시간 표시 막대 트리에 영향을 주는 타임 라인을 결합할 수 있습니다. 예를 들어 다음 세 가지 작업을 수행하는 단추가 필요하다고 가정해 봅니다.  
  
-   단추를 선택하면 단추가 커지고 색이 변경됩니다.  
  
-   클릭할 때 축소되었다가 다시 원래 크기로 커집니다.  
  
-   사용되지 않도록 설정되면 축소되었다가 50% 불투명도로 페이드됩니다.  
  
 이 경우 동일한 개체에 적용되는 여러 애니메이션 집합이 있고 단추 상태에 따라 다른 시간에 재생하려고 합니다. <xref:System.Windows.Media.Animation.Storyboard>개체를 사용 하 여 애니메이션을 구성 하 고 하나 이상의 개체 그룹으로 적용할 수 있습니다.  
  
<a name="wherecanyouuseastoryboard"></a>   
## <a name="where-can-you-use-a-storyboard"></a>Storyboard를 사용할 수 있는 위치  
 A <xref:System.Windows.Media.Animation.Storyboard> 애니메이션 가능한 클래스의 종속성 속성이 애니메이션 효과 주는 데 사용할 수 있습니다 (어떤 원리에 의해 클래스 애니메이션을 적용 하는 방법에 대 한 자세한 내용은 참조는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)). 그러나, 스토리 보 딩 프레임 워크 수준 기능 이므로 개체에 속해 있어야는 <xref:System.Windows.NameScope> 의 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>합니다.  
  
 예를 들어, 사용할 수는 <xref:System.Windows.Media.Animation.Storyboard> 다음을 수행 합니다.  
  
-   애니메이션 효과 적용 한 <xref:System.Windows.Media.SolidColorBrush> 단추의 배경을 그리는 (워크 요소) (형식의 <xref:System.Windows.FrameworkElement>),  
  
-   애니메이션 효과 적용 한 <xref:System.Windows.Media.SolidColorBrush> (워크 요소)의 채우기 그리는 <xref:System.Windows.Media.GeometryDrawing> (워크 요소)를 사용 하 여 표시 되는 <xref:System.Windows.Controls.Image> (<xref:System.Windows.FrameworkElement>).  
  
-   코드에서 애니메이션을 적용 한 <xref:System.Windows.Media.SolidColorBrush> 도 포함 되어 있는 클래스에 의해 선언 된는 <xref:System.Windows.FrameworkElement>경우는 <xref:System.Windows.Media.SolidColorBrush> 이름을 등록 하는 <xref:System.Windows.FrameworkElement>합니다.  
  
 그러나 있습니다 사용할 수 없습니다는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션 효과를 주는 <xref:System.Windows.Media.SolidColorBrush> 사용 하 여 이름을 등록 하지 않았거나는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>의 속성을 설정 하는 사용 되지 않은 또는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>합니다.  
  
<a name="applyanimationswithastoryboard"></a>   
## <a name="how-to-apply-animations-with-a-storyboard"></a>Storyboard를 사용하여 애니메이션을 적용하는 방법  
 사용 하는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션의 자식 타임 라인으로 추가 하면 구성 하 고 애니메이션을 적용 하는 <xref:System.Windows.Media.Animation.Storyboard>합니다. <xref:System.Windows.Media.Animation.Storyboard> 클래스를 제공는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType> 연결 된 속성입니다. 애니메이션에 이러한 속성을 설정하여 해당 대상 개체 및 속성을 지정합니다.  
  
 시작을 대상 애니메이션을 적용 하는 <xref:System.Windows.Media.Animation.Storyboard> 트리거 동작 또는 메서드를 사용 하 여 합니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용 하면는 <xref:System.Windows.Media.Animation.BeginStoryboard> 개체는 <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger>, 또는 <xref:System.Windows.DataTrigger>합니다. 코드에서 사용할 수도 있습니다는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드.  
  
 다음 표에서 다양 한 위치를 보여 줍니다. 여기서 각 <xref:System.Windows.Media.Animation.Storyboard> 시작 기술을 사용할 수 있습니다: 인스턴스당, 스타일, 컨트롤 템플릿 및 데이터 서식 파일입니다. "인스턴스별"은 스타일, 컨트롤 템플릿 또는 데이터 템플릿이 아닌 개체의 인스턴스에 직접 애니메이션 또는 storyboard를 적용하는 기술을 나타냅니다.  
  
|storyboard 시작 방법...|인스턴스별|스타일|컨트롤 템플릿|데이터 템플릿|예|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>및<xref:System.Windows.EventTrigger>|예|예|예|예|[Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>속성<xref:System.Windows.Trigger>|아니요|예|예|예|[속성 값이 변경될 때 애니메이션 트리거](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard>및<xref:System.Windows.DataTrigger>|아니요|예|예|예|[방법: 데이터가 변경될 때 애니메이션 트리거Changes](http://msdn.microsoft.com/library/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드|예|아니요|아니요|아니요|[Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션 효과를 주는 <xref:System.Windows.FrameworkElement.Width%2A> 의 <xref:System.Windows.Shapes.Rectangle> 요소 및 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 의 <xref:System.Windows.Media.SolidColorBrush> 를 그리는 데 사용 되는 <xref:System.Windows.Shapes.Rectangle>합니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]  
  
 [!code-csharp[storyboards_ovw_snip#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]  
  
 다음 섹션에 설명 된 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 연결 된 속성에서 자세히 합니다.  
  
<a name="targetingelementsandfreezables"></a>   
## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>프레임워크 요소, 프레임워크 콘텐츠 요소 및 Freezable을 대상으로 지정  
 이전 섹션에서는 애니메이션이 대상을 찾기 위해서는 대상의 이름 및 애니메이션 효과를 주려는 속성을 알고 있어야 한다는 사실을 언급했습니다. 애니메이션 효과를 주는 속성을 지정 하는 단순 합니다: 설정 하기만 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType> 애니메이션 효과를 줄 속성의 이름으로 합니다.  속성을 설정 하 여 애니메이션 효과 줄 개체의 이름을 지정 하는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> 애니메이션 속성입니다.  
  
 에 대 한는 <xref:System.Windows.Setter.TargetName%2A> 속성 작동 하도록 하는 대상된 개체에는 이름이 있어야 합니다. 에 이름을 할당 한 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 에 이름을 할당 다르면는 <xref:System.Windows.Freezable> 개체입니다.  
  
 프레임 워크 요소는 해당 클래스에서 상속 되는 <xref:System.Windows.FrameworkElement> 클래스입니다. 프레임 워크 요소의 예로 <xref:System.Windows.Window>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Button>, 및 <xref:System.Windows.Shapes.Rectangle>합니다. 기본적으로 모든 창, 패널 및 컨트롤은 요소입니다. 프레임 워크 콘텐츠 요소는 해당 클래스에서 상속 되는 <xref:System.Windows.FrameworkContentElement> 클래스입니다. 콘텐츠 요소와 프레임 워크의 예로 <xref:System.Windows.Documents.FlowDocument> 및 <xref:System.Windows.Documents.Paragraph>합니다. 형식이 프레임워크 요소인지 또는 프레임워크 콘텐츠 요소인지 확실하지 않은 경우 Name 속성을 가지는지 여부를 확인합니다. 이 속성을 가질 경우 프레임워크 요소이거나 프레임워크 콘텐츠 요소일 것입니다. 확실히 하려면 해당 형식 페이지의 상속 계층 구조 섹션을 확인합니다.  
  
 프레임 워크 요소 또는 콘텐츠 프레임 워크 요소에서 대상으로 사용할 수 있도록 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 설정 하면 해당 <xref:System.Windows.FrameworkElement.Name%2A> 속성입니다. 코드에도 사용 해야는 <xref:System.Windows.NameScope.RegisterName%2A> 요소의 이름을를 만든 요소에 등록 하는 메서드는 <xref:System.Windows.NameScope>합니다.  
  
 다음 예제에서는 앞의 예제에서 가져온 이름을 할당 `MyRectangle` 는 <xref:System.Windows.Shapes.Rectangle>는 유형의 <xref:System.Windows.FrameworkElement>합니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]  
  
 [!code-csharp[storyboards_ovw_snip#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]  
  
 이름이 지정되면 해당 요소의 속성에 애니메이션 효과를 줄 수 있습니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]  
  
 [!code-csharp[storyboards_ovw_snip#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]  
  
 <xref:System.Windows.Freezable>유형은 해당 클래스에서 상속 되는 <xref:System.Windows.Freezable> 클래스입니다. 몇 가지 <xref:System.Windows.Freezable> 포함 <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.RotateTransform>, 및 <xref:System.Windows.Media.GradientStop>합니다.  
  
 대상으로 사용할 수 있도록는 <xref:System.Windows.Freezable> 에서 애니메이션에 따라 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 사용 하면는 [X:name 지시문](../../../../docs/framework/xaml-services/x-name-directive.md) 에 이름을 할당할 수 있습니다. 코드를 사용 하 여는 <xref:System.Windows.NameScope.RegisterName%2A> 를 만든 요소에 해당 이름을 등록 하는 메서드는 <xref:System.Windows.NameScope>합니다.  
  
 다음 예제에서는 할당 하는 이름을 <xref:System.Windows.Freezable> 개체입니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]  
  
 [!code-csharp[storyboards_ovw_snip#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]  
  
 그런 후 개체를 애니메이션 대상으로 지정할 수 있습니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]  
  
 [!code-csharp[storyboards_ovw_snip#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]  
  
 <xref:System.Windows.Media.Animation.Storyboard>개체 이름 범위를 사용 하 여 해결 하는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 속성입니다. WPF 이름 범위에 대한 자세한 내용은 [WPF XAML 이름 범위](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)를 참조하세요. 경우는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 속성을 생략 하면, 애니메이션 정의 된 또는 스타일이 적용 된 요소 스타일의 경우 요소를 대상으로 합니다.  
  
 에 이름을 할당할 수 없는 경우에 따라는 <xref:System.Windows.Freezable> 개체입니다. 예를 들어 경우는 <xref:System.Windows.Freezable> 자원으로 선언 되거나 된 스타일에서 속성 값을 설정 하는 데 사용 되는 이름을 지정할 수 없습니다. 이름이 없기 때문에 직접적으로 대상으로 지정할 수 없지만 간접적으로 지정할 수는 있습니다. 다음 섹션에서는 간접 대상 지정을 사용하는 방법을 설명합니다.  
  
<a name="pathsyntaxforchangeable"></a>   
## <a name="indirect-targeting"></a>간접 대상 지정  
 시기가 <xref:System.Windows.Freezable> 직접적으로 애니메이션, 예를 들어 대상으로 지정할 수는 <xref:System.Windows.Freezable> 자원으로 선언 되거나 스타일의 속성 값을 설정 하는 데 사용 합니다. 이러한 경우를 직접 대상으로 하는 경우에 여전히 애니메이션을 적용할 수는 <xref:System.Windows.Freezable> 개체입니다. 설정 하는 대신는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 속성의 이름으로는 <xref:System.Windows.Freezable>, 게 요소의 이름을 있는 <xref:System.Windows.Freezable> "속해 있습니다." 예를 들어 한 <xref:System.Windows.Media.SolidColorBrush> 설정 하는 데는 <xref:System.Windows.Shapes.Shape.Fill%2A> 요소는 사각형의 해당 사각형에 속합니다. 브러시, 애니메이션을 애니메이션의 설정 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 요소 프레임 워크 또는 프레임 워크 콘텐츠 요소 속성에서 시작 하는 속성의 체인으로는 <xref:System.Windows.Freezable> 설정 하는 데 사용 된 및로 끝나는 <xref:System.Windows.Freezable> 애니메이션 속성입니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]  
  
 [!code-csharp[storyboards_ovw_snip#134](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]  
  
 경우는 <xref:System.Windows.Freezable> 은 고정 클론 걸 수, 하 고 해당 복제 애니메이션 효과가 적용 합니다. 이 경우 원래 개체의 <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> 속성 계속 해 서 반환 `false`원래 개체는 실제로 애니메이션 때문에 있습니다. 복제에 대 한 자세한 내용은 참조는 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)합니다.  
  
 또한 간접 속성 대상 지정을 사용할 경우에는 존재하지 않는 개체를 대상으로 지정할 수 있습니다. 예를 들어 있는 생각할 수 있습니다는 <xref:System.Windows.Controls.Control.Background%2A> 으로 설정 된 특정 단추의 <xref:System.Windows.Media.SolidColorBrush> 때 실제로 해당 색에 애니메이션을 적용 하려고 하 고는 <xref:System.Windows.Media.LinearGradientBrush> 단추의 배경을 설정 하는 데 사용 되었습니다. 이러한 경우 예외가 발생 하지 않습니다. 애니메이션 실패 하기 때문에 표시에 영향을 미칠 <xref:System.Windows.Media.LinearGradientBrush> 에 대 한 변경에 응답 하지 않습니다는 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 속성입니다.  
  
 다음 섹션에서는 간접 속성 대상 지정 구문을 좀 더 자세히 설명합니다.  
  
<a name="xamlsyntaxchangeableproperty"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>XAML에서 Freezable 속성을 간접적으로 대상으로 지정  
 freezable의 속성을 대상으로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 다음 구문을 사용 합니다.  
  
||  
|-|  
|*ElementPropertyName* `.` *FreezablePropertyName*|  
  
 Where  
  
-   *ElementPropertyName* 의 속성는 <xref:System.Windows.FrameworkElement> 는 <xref:System.Windows.Freezable> 을 설정 하는 데 사용 되 고  
  
-   *FreezablePropertyName* 의 속성은 <xref:System.Windows.Freezable> 애니메이션 효과를 주는 합니다.  
  
 다음 코드에 애니메이션 효과 적용 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 의 <xref:System.Windows.Media.SolidColorBrush> 설정 하는 데는  
  
 <xref:System.Windows.Shapes.Shape.Fill%2A>사각형 요소입니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]  
  
 컬렉션 또는 배열에 포함된 Freezable을 대상으로 지정해야 하는 경우도 있습니다.  
  
 컬렉션에 포함된 Freezable을 대상으로 지정하려면 다음 경로 구문을 사용합니다.  
  
||  
|-|  
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|  
  
 여기서 *CollectionIndex* 개체의 배열 또는 컬렉션의 인덱스입니다.  
  
 예를 들어, 사각형에는 <xref:System.Windows.Media.TransformGroup> 리소스에 적용 된 해당 <xref:System.Windows.UIElement.RenderTransform%2A> 속성을 포함 하는 변환 중 하나를 애니메이션 효과를 줄.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]  
  
 다음 코드에 애니메이션 효과 적용 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.RotateTransform.Angle%2A> 의 속성은 <xref:System.Windows.Media.RotateTransform> 앞의 예제에 표시 된 것입니다.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#35](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]  
  
<a name="targetingpropertyofchangeableincode"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>코드에서 Freezable 속성을 간접적으로 대상으로 지정  
 코드에서 만듭니다는 <xref:System.Windows.PropertyPath> 개체입니다. 만들 때의 <xref:System.Windows.PropertyPath>, 지정는 <xref:System.Windows.PropertyPath.Path%2A> 및 <xref:System.Windows.PropertyPath.PathParameters%2A>합니다.  
  
 만들려는 <xref:System.Windows.PropertyPath.PathParameters%2A>, 형식의 배열을 만들 <xref:System.Windows.DependencyProperty> 종속성 속성 식별자 필드 목록을 포함 하 합니다. 속성에 대 한 첫 번째 식별자 필드는는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 하는 <xref:System.Windows.Freezable> 설정 하는 데 사용 됩니다. 다음 식별자 필드의 속성을 나타내는 <xref:System.Windows.Freezable> 대상으로 합니다. 에 연결 하는 속성의 체인으로 참여는 <xref:System.Windows.Freezable> 에 <xref:System.Windows.FrameworkElement> 개체입니다.  
  
 다음 대상으로 하는 종속성 속성 체인의 한 예로 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 의 <xref:System.Windows.Media.SolidColorBrush> 설정 하는 데는 <xref:System.Windows.Shapes.Shape.Fill%2A> 사각형입니다.  
  
 [!code-csharp[storyboards_ovw_snip#135](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]  
  
 지정 해야는 <xref:System.Windows.PropertyPath.Path%2A>합니다. A <xref:System.Windows.PropertyPath.Path%2A> 는 <xref:System.String> 되었음을 알리는 <xref:System.Windows.PropertyPath.Path%2A> 해석 하는 방법의 <xref:System.Windows.PropertyPath.PathParameters%2A>합니다. 여기서는 다음 구문을 사용합니다.  
  
||  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *FreezablePropertyArrayIndex* `)`|  
  
 Where  
  
-   *OwnerPropertyArrayIndex* 의 인덱스는 <xref:System.Windows.DependencyProperty> 의 식별자를 포함 하는 배열은 <xref:System.Windows.FrameworkElement> 개체의 속성 하는 <xref:System.Windows.Freezable> 을 설정 하는 데 사용 되 고  
  
-   *FreezablePropertyArrayIndex* 의 인덱스는 <xref:System.Windows.DependencyProperty> 대상 속성의 식별자가 포함 된 배열입니다.  
  
 다음 예제와 <xref:System.Windows.PropertyPath.Path%2A> 를 수 반하는 <xref:System.Windows.PropertyPath.PathParameters%2A> 앞의 예제에 정의 되어 있습니다.
  
 [!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]  
  
 다음 예제에서는 결합 애니메이션 효과를 주는 이전 예제에서 코드는 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 의 <xref:System.Windows.Media.SolidColorBrush> 설정 하는 데는 <xref:System.Windows.Shapes.Shape.Fill%2A> 사각형입니다.  
  
 [!code-csharp[storyboards_ovw_snip#137](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]  
  
 컬렉션 또는 배열에 포함된 Freezable을 대상으로 지정해야 하는 경우도 있습니다. 예를 들어, 사각형에는 <xref:System.Windows.Media.TransformGroup> 리소스에 적용 된 해당 <xref:System.Windows.UIElement.RenderTransform%2A> 속성을 포함 하는 변환 중 하나를 애니메이션 효과를 줄.  
  
 [!code-xaml[storyboards_ovw_snip#142](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]  
  
 대상에는 <xref:System.Windows.Freezable> 다음 경로 구문을 사용 하는 컬렉션에 포함 합니다.  
  
||  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *CollectionChildrenPropertyArrayIndex* `)` `[` *CollectionIndex* `].(` *FreezablePropertyArrayIndex* `)`|  
  
 여기서 *CollectionIndex* 개체의 배열 또는 컬렉션의 인덱스입니다.  
  
 대상에는 <xref:System.Windows.Media.RotateTransform.Angle%2A> 의 속성은 <xref:System.Windows.Media.RotateTransform>의 두 번째 변환이 <xref:System.Windows.Media.TransformGroup>, 다음을 사용 합니다 <xref:System.Windows.PropertyPath.Path%2A> 및 <xref:System.Windows.PropertyPath.PathParameters%2A>합니다.  
  
 [!code-csharp[storyboards_ovw_snip#139](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]  
  
 다음 예제에서는 애니메이션에 대 한 전체 코드는 <xref:System.Windows.Media.RotateTransform.Angle%2A> 의 <xref:System.Windows.Media.RotateTransform> 내에 포함 된 한 <xref:System.Windows.Media.TransformGroup>합니다.  
  
 [!code-csharp[storyboards_ovw_snip#138](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]  
  
### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>Freezable을 시작 지점으로 사용해서 간접적으로 대상 지정  
 이전 섹션에 간접적으로 대상 하는 방법을 설명는 <xref:System.Windows.Freezable> 부터 시작 하 여 한 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 속성 체인을 만들어는 <xref:System.Windows.Freezable> 하위 속성입니다. 사용할 수도 있습니다는 <xref:System.Windows.Freezable> 시작 지점를 간접적으로 대상 중 하나는 <xref:System.Windows.Freezable> 하위 속성입니다. 사용할 때 하나의 추가 제한 사항을 적용 됩니다는 <xref:System.Windows.Freezable> 간접 대상에 대 한 시작 점으로: 시작 <xref:System.Windows.Freezable> 매 <xref:System.Windows.Freezable> 지점과 대상된 간접적으로든 하위 속성 간의 하지를 고정 해야 합니다.  
  
<a name="controllable_storyboards"></a>   
## <a name="interactively-controlling-a-storyboard-in-xaml"></a>XAML에서 Storyboard를 대화형으로 제어  
 스토리 보드를 시작 하려면 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 사용 하면는 <xref:System.Windows.Media.Animation.BeginStoryboard> 동작 합니다. <xref:System.Windows.Media.Animation.BeginStoryboard>개체와, 애니메이션 및 스토리 보드를 시작 하는 속성에 애니메이션을 배포 합니다. (이 프로세스에 대 한 세부 정보를 참조 하십시오.는 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).) 제공 하는 경우는 <xref:System.Windows.Media.Animation.BeginStoryboard> 이름을 지정 하 여 해당 <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> 속성 되도록 하 여 제어할 수 있는 스토리 보드 합니다. 그러면 Storyboard를 시작한 후에 대화형으로 제어할 수 있습니다. 다음은 Storyboard를 제어하기 위해 이벤트 트리거와 함께 사용하는 제어 가능한 Storyboard 작업 목록입니다.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: 스토리 보드를 일시 중지 됩니다.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: 일시 중지 된 스토리 보드를 다시 시작합니다.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: 스토리 보드의 속도 변경합니다.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: 있는 경우 채우기 기간의 끝에 스토리 보드를 진행 합니다.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: 스토리 보드를 중지합니다.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: 스토리 보드를 제거합니다.  
  
 다음 예제에서는 제어 가능한 Storyboard 작업이 Storyboard를 대화형으로 제어하는 데 사용됩니다.  
  
 [!code-xaml[animation_ovws_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]  
  
<a name="controllable_storyboards_procedural"></a>   
## <a name="interactively-controlling-a-storyboard-by-using-code"></a>코드를 사용하여 Storyboard를 대화형으로 제어  
 앞의 예제에서는 트리거 작업을 사용해서 애니메이션 효과를 적용하는 방법을 살펴보았습니다. 코드에서 제어할 수도 있습니다의 대화형 메서드를 사용 하 여 스토리 보드는 <xref:System.Windows.Media.Animation.Storyboard> 클래스입니다. 에 대 한는 <xref:System.Windows.Media.Animation.Storyboard> 코드에서 대화형으로 만들 수의 스토리 보드의 적합 한 오버 로드를 사용 해야 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 지정 하 고 `true` 제어할 수 있도록 합니다. 참조는 <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29> 자세한 내용을 보려면 페이지입니다.  
  
 다음 목록에는 조작 하는 데 사용할 수 있는 메서드를 보여 줍니다.는 <xref:System.Windows.Media.Animation.Storyboard> 시작 된 후:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>  
  
 이러한 메서드를 사용 하는 장점이 만들 필요가 없습니다 <xref:System.Windows.Trigger> 또는 <xref:System.Windows.TriggerAction> 는 제어할 수에 대 한 참조 하기만 하는 개체가 <xref:System.Windows.Media.Animation.Storyboard> 조작 하려는 합니다.  
  
 **참고:** 에서 수행 되는 모든 대화형 작업은 <xref:System.Windows.Media.Animation.Clock>, 즉도 <xref:System.Windows.Media.Animation.Storyboard> 다음 틱은 다음 렌더링 되기 바로 전에 발생 하는 타이밍 엔진에서 발생 합니다. 예를 들어, 사용 하는 경우는 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 타이밍 엔진의 다음 틱에 값을 변경 하는 대신, 애니메이션, 속성 값의에서 다른 지점으로 이동 하려면 메서드 즉시 변경 되지 않습니다.  
  
 적용 및의 대화형 메서드를 사용 하 여 애니메이션을 제어 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Media.Animation.Storyboard> 클래스입니다.  
  
 [!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
 [!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]  
  
<a name="usingstoryboardsinstyles"></a>   
## <a name="animate-in-a-style"></a>스타일에서 애니메이션 효과 주기  
 사용할 수 있습니다 <xref:System.Windows.Media.Animation.Storyboard> 에서 애니메이션을 정의 하는 개체는 <xref:System.Windows.Style>합니다. 사용한 애니메이션는 <xref:System.Windows.Media.Animation.Storyboard> 에 <xref:System.Windows.Style> 사용 하는 <xref:System.Windows.Media.Animation.Storyboard> 와 같은 세 가지 예외가 있지만, 다른 위치에서:  
  
-   지정 하지 않으면는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>; <xref:System.Windows.Media.Animation.Storyboard> 항상 요소를 대상으로 하는 <xref:System.Windows.Style> 적용 됩니다. 대상에 <xref:System.Windows.Freezable> 개체 간접 대상으로 사용 해야 합니다. 간접 대상 지정 하는 방법에 대 한 자세한 내용은 참조는 [간접 대상](#pathsyntaxforchangeable) 섹션.  
  
-   지정할 수 없습니다는 <xref:System.Windows.EventTrigger.SourceName%2A> 에 대 한 프로그램 <xref:System.Windows.EventTrigger> 또는 <xref:System.Windows.Trigger>합니다.  
  
-   동적 리소스 참조 또는 데이터 바인딩 식을 설정 하려면 사용할 수 없습니다 <xref:System.Windows.Media.Animation.Storyboard> 또는 애니메이션 속성 값입니다. 하기 때문 내의 모든 항목는 <xref:System.Windows.Style> 스레드로부터 안전 해야 하 고 타이밍 시스템 해야 <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> 스레드로부터 안전 하면 개체입니다. A <xref:System.Windows.Media.Animation.Storyboard> 또는 해당 자식 타임 라인 동적 리소스 참조 또는 데이터 바인딩 식을 포함 하는 경우에 고정할 수 없습니다. 고정 오류 코드 및 기타에 대 한 자세한 내용은 <xref:System.Windows.Freezable> 기능 참조는 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)합니다.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 대 한 이벤트 처리기를 선언할 수 없습니다 <xref:System.Windows.Media.Animation.Storyboard> 또는 애니메이션 이벤트입니다.  
  
 스타일에서 스토리 보드를 정의 하는 방법을 보여 주는 예제를 참조 하십시오.는 [스타일의 애니메이션](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-style.md) 예제입니다.  
  
<a name="defineAStoryboardInAControlTemplateSection"></a>   
## <a name="animate-in-a-controltemplate"></a>ControlTemplate에서 애니메이션 효과 적용  
 사용할 수 있습니다 <xref:System.Windows.Media.Animation.Storyboard> 에서 애니메이션을 정의 하는 개체는 <xref:System.Windows.Controls.ControlTemplate>합니다. 사용한 애니메이션는 <xref:System.Windows.Media.Animation.Storyboard> 에 <xref:System.Windows.Controls.ControlTemplate> 사용 하는 <xref:System.Windows.Media.Animation.Storyboard> 와 같은 두 가지 예외가 있지만, 다른 위치에서:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 의 자식 개체를 참조할 수 있습니다는 <xref:System.Windows.Controls.ControlTemplate>합니다. 경우 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 를 지정 하지 않으면 애니메이션 요소를 대상으로 하는 <xref:System.Windows.Controls.ControlTemplate> 적용 됩니다.  
  
-   <xref:System.Windows.EventTrigger.SourceName%2A> 에 대 한 프로그램 <xref:System.Windows.EventTrigger> 또는 <xref:System.Windows.Trigger> 의 자식 개체를 참조할 수 있습니다는 <xref:System.Windows.Controls.ControlTemplate>합니다.  
  
-   동적 리소스 참조 또는 데이터 바인딩 식을 설정 하려면 사용할 수 없습니다 <xref:System.Windows.Media.Animation.Storyboard> 또는 애니메이션 속성 값입니다. 하기 때문 내의 모든 항목는 <xref:System.Windows.Controls.ControlTemplate> 스레드로부터 안전 해야 하 고 타이밍 시스템 해야 <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> 스레드로부터 안전 하면 개체입니다. A <xref:System.Windows.Media.Animation.Storyboard> 또는 해당 자식 타임 라인 동적 리소스 참조 또는 데이터 바인딩 식을 포함 하는 경우에 고정할 수 없습니다. 고정 오류 코드 및 기타에 대 한 자세한 내용은 <xref:System.Windows.Freezable> 기능 참조는 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)합니다.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 대 한 이벤트 처리기를 선언할 수 없습니다 <xref:System.Windows.Media.Animation.Storyboard> 또는 애니메이션 이벤트입니다.  
  
 스토리 보드를 정의 하는 방법을 보여 주는 예제는 <xref:System.Windows.Controls.ControlTemplate>, 참조는 [는 ControlTemplate의 애니메이션](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md) 예제입니다.  
  
<a name="animateWhenAPropertyValueChanges"></a>   
## <a name="animate-when-a-property-value-changes"></a>속성 값이 변경될 때 애니메이션 효과 주기  
 스타일 및 컨트롤 템플릿에서 트리거 개체를 사용하여 속성이 변경될 때 Storyboard를 시작할 수 있습니다. 예제를 보려면 [트리거하는 애니메이션 때 정도 속성 값이 변경](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md) 및 [는 ControlTemplate의 애니메이션](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md)합니다.  
  
 속성에 의해 적용 된 애니메이션이 <xref:System.Windows.Trigger> 개체 보다 더 복잡 한 방식으로 작동 <xref:System.Windows.EventTrigger> 애니메이션이 나 애니메이션 사용 하 여 시작 <xref:System.Windows.Media.Animation.Storyboard> 메서드.  "핸드 오프" 애니메이션이 있는 다른 정의 <xref:System.Windows.Trigger> 개체 하지만로 작성 <xref:System.Windows.EventTrigger> 및 애니메이션 메서드 트리거됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
