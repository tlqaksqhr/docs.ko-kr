---
title: 애니메이션 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], animations
- animations [WPF], overview
ms.assetid: bd9ce563-725d-4385-87c9-d7ee38cf79ea
ms.openlocfilehash: 5fb9550ddce4ead900206c2ece2f976ab8b42c4b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558332"
---
# <a name="animation-overview"></a>애니메이션 개요
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 강력한 집합이 매력적인 사용자 인터페이스와 멋진 문서를 만들 수 있도록 하는 그래픽 및 레이아웃 기능을 제공 합니다. 애니메이션은 매력적인 사용자 인터페이스를 훨씬 더 화려하고 유용하게 만들어줄 수 있습니다. 방금 배경 색에 애니메이션을 적용 하거나 애니메이션을 적용 하 여 <xref:System.Windows.Media.Transform>, 유용한 시각적 표시를 제공 하거나 화면을 멋지게 전환을 만들 수 있습니다.  
  
 이 개요에서는에 대 한 소개는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션, 타이밍 시스템입니다. 애니메이션에 중점을 둡니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스토리 보드를 사용 하 여 개체입니다.  

<a name="introducinganimations"></a>   
## <a name="introducing-animations"></a>애니메이션 소개  
 애니메이션은 마지막까지 조금씩 달라지는 일련의 이미지를 빠르게 순환하면서 만들어지는 효과입니다. 뇌는 이미지 그룹을 변화하는 하나의 영상으로 인식합니다. 영화에서는 많은 사진 또는 프레임을 초별로 기록하는 카메라를 사용하여 이러한 효과를 만듭니다. 프로젝터에서 프레임이 재생되면 청중은 동영상을 보게 됩니다.  
  
 컴퓨터의 애니메이션도 유사합니다. 예를 들어 사각형 그림을 보기에서 페이드 아웃하는 프로그램은 다음과 같이 작동할 수 있습니다.  
  
-   프로그램이 타이머를 만듭니다.  
  
-   프로그램이 설정된 간격으로 타이머를 확인하여 경과된 시간을 파악합니다.  
  
-   프로그램이 타이머를 확인할 때마다 경과된 시간에 따라 사각형의 현재 불투명도 값을 계산합니다.  
  
-   그런 다음 새 값으로 사각형을 업데이트한 후 그립니다.  
  
 이전에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] 개발자가 만들고 타이밍 시스템을 관리할 하거나 특수 한 사용자 지정 라이브러리를 사용 해야 했습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 관리 되는 코드를 통해 노출 되는 효율적인 타이밍 시스템 포함 및 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 깊이에 통합 된 및의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프레임 워크입니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션을 사용하면 쉽게 컨트롤 및 기타 그래픽 개체에 애니메이션 효과를 줄 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 타이밍 시스템을 관리하고 화면을 효율적으로 다시 그리는 모든 백그라운드 작업을 처리합니다. 그뿐 아니라 이러한 효과를 달성하는 기법이 아닌, 만들려는 효과에 집중할 수 있도록 하는 타이밍 클래스를 제공합니다. 또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 클래스가 상속할 수 있는 애니메이션 기본 클래스를 노출하여 사용자 고유의 애니메이션을 쉽게 만들 수 있도록 하므로 애니메이션을 사용자 지정할 수 있습니다. 이러한 사용자 지정 애니메이션은 표준 애니메이션 클래스에 비해 성능상의 이점도 큽니다.  
  
<a name="thewpftimingsystem"></a>   
## <a name="wpf-property-animation-system"></a>WPF 속성 애니메이션 시스템  
 타이밍 시스템에 대 한 몇 가지 중요 한 개념을 이해 하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션을 사용 하 여 더 쉬워질 수 있습니다. 가장 중요 한 한다는 것입니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 개별 속성에 애니메이션을 적용 하 여 개체에 애니메이션을 적용 합니다. 예를 들어 증가 하는 프레임 워크 요소 있도록 애니메이션을 적용 하면 해당 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성입니다. 뷰에서 사라지게 하는 개체를 애니메이션을 적용 하면 해당 <xref:System.Windows.UIElement.Opacity%2A> 속성입니다.  
  
 속성에 애니메이션 기능을 부여하려면 다음 세 가지 요구 사항을 충족해야 합니다.  
  
-   종속성 속성이어야 합니다.  
  
-   상속 되는 클래스에 속해 있어야 <xref:System.Windows.DependencyObject> 구현 하는 <xref:System.Windows.Media.Animation.IAnimatable> 인터페이스입니다.  
  
-   사용 가능한 호환되는 애니메이션 형식이어야 합니다. (경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 제공 하지 않으면, 직접 만들 수 있습니다. 참조는 [사용자 지정 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md).)  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 많은 개체가 포함 된 <xref:System.Windows.Media.Animation.IAnimatable> 속성입니다. 와 같은 컨트롤 <xref:System.Windows.Controls.Button> 및 <xref:System.Windows.Controls.TabControl>, 그리고 <xref:System.Windows.Controls.Panel> 및 <xref:System.Windows.Shapes.Shape> 개체에서 상속 <xref:System.Windows.DependencyObject>합니다. 해당 속성 대부분은 종속성 속성입니다.  
  
 스타일 및 템플릿 컨트롤을 비롯한 거의 모든 위치에서 애니메이션을 사용할 수 있습니다. 애니메이션은 시각적일 필요가 없습니다. 이 섹션에 설명된 조건을 충족하지 않을 경우 사용자 인터페이스에 속하지 않는 개체에 애니메이션 효과를 줄 수 있습니다.  
  
<a name="storyboardwalkthrough"></a>   
## <a name="example-make-an-element-fade-in-and-out-of-view"></a>예제: 보기에서 요소 페이드 인 및 페이드 아웃  
 사용 하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 종속성 속성의 값에 애니메이션 효과를 애니메이션 합니다. 사용 하 여는 <xref:System.Windows.Media.Animation.DoubleAnimation>, 생성 하는 애니메이션의 형식인 <xref:System.Double> 애니메이션 효과를 줄 값의 <xref:System.Windows.UIElement.Opacity%2A> 속성은 <xref:System.Windows.Shapes.Rectangle>합니다. 결과적으로 <xref:System.Windows.Shapes.Rectangle> 페이드 인 되 보기.  
  
 예의 첫 번째 부분 만듭니다는 <xref:System.Windows.Shapes.Rectangle> 요소입니다. 다음 단계는 애니메이션을 만들고 사각형의에 적용 하는 방법을 보여 <xref:System.Windows.UIElement.Opacity%2A> 속성입니다.
  
 다음 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Shapes.Rectangle> 요소에는 <xref:System.Windows.Controls.StackPanel> XAML에서 합니다.  
  
 [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]  
  
 다음 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Shapes.Rectangle> 요소에는 <xref:System.Windows.Controls.StackPanel> 코드에서입니다.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]  
  
<a name="opacity_animation_step1"></a>   
### <a name="part-1-create-a-doubleanimation"></a>1부: DoubleAnimation 만들기  
 애니메이션 효과를 줄은 페이드 아웃 하기 위해 한 가지 방법은 해당 <xref:System.Windows.UIElement.Opacity%2A> 속성입니다. 때문에 <xref:System.Windows.UIElement.Opacity%2A> 속성은 형식이 <xref:System.Double>를 double 값을 생성 하는 애니메이션을 사용 해야 합니다. A <xref:System.Windows.Media.Animation.DoubleAnimation> 는 그러한 애니메이션 중 하나입니다. A <xref:System.Windows.Media.Animation.DoubleAnimation> 두 double 값 사이의 변환을 생성 합니다. 설정 시작 값을 지정 하려면 해당 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성입니다. 설정한 끝 값을 지정 하려면 해당 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성입니다.  
  
1.  불투명도 값 `1.0` 하면 완전히 불투명 개체와의 불투명도 값 `0.0` 하면 완전히 표시 되지 않습니다. 애니메이션 전환이 가능 하도록 `1.0` 를 `0.0` 설정한 해당 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성을 `1.0` 및 해당 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 `0.0`합니다. 다음 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Media.Animation.DoubleAnimation> XAML에서 합니다.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]  
  
     다음 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Media.Animation.DoubleAnimation> 코드에서입니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]  
  
2.  다음으로 지정 해야 합니다는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>합니다. <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 애니메이션의 시작 값에서 대상 값까지 이동 하는 기간을 지정 합니다. 다음을 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> XAML에서 5 초입니다.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]  
  
     다음을 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 코드에서 5 초입니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]  
  
3.  앞의 코드에서 전환 되는 애니메이션을 보인 `1.0` 를 `0.0`, 때문에 완전히 보이지 않는에 완전히 불투명에서 페이드 인 대상 요소입니다. 완전히 사라진 후 다시 페이드 요소를 설정의 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성에 애니메이션의 `true`합니다. 애니메이션 무기한 반복 만들려면 설정 해당 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>합니다. 다음을 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 및 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> XAML의 속성입니다.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]  
  
     다음을 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 및 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 코드의 속성입니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]  
  
<a name="opacity_animation_step2"></a>   
### <a name="part-2-create-a-storyboard"></a>2부: Storyboard 만들기  
 만들 개체에 애니메이션을 적용할는 <xref:System.Windows.Media.Animation.Storyboard> 사용 하 여는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 연결 된 개체를 지정 하는 속성 및 애니메이션 속성입니다.  
  
1.  만들기는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션을 자식으로 추가 합니다. 다음 만드는 방법을 보여 줍니다.는 <xref:System.Windows.Media.Animation.Storyboard> XAML에서 합니다.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]    
  
     만드는 <xref:System.Windows.Media.Animation.Storyboard> 코드에서 선언 된 <xref:System.Windows.Media.Animation.Storyboard> 클래스 수준 변수입니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]  
  
     다음 초기화는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션을 자식으로 추가 합니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]  
  
2.  <xref:System.Windows.Media.Animation.Storyboard> 애니메이션을 적용할 위치를 알아야 합니다. 사용 된 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> 연결 된 속성 개체에 애니메이션 효과를 지정 합니다. 다음의 대상 이름을 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.DoubleAnimation> 를 `MyRectangle` XAML에서 합니다.  
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]  
  
     다음의 대상 이름을 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.DoubleAnimation> 를 `MyRectangle` 코드에서입니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]  
  
3.  사용 된 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 연결 된 속성에 애니메이션 효과를 주는 속성을 지정 합니다. 다음 애니메이션 구성 방법을 보여 줍니다. 대상에는 <xref:System.Windows.UIElement.Opacity%2A> 의 속성은 <xref:System.Windows.Shapes.Rectangle> XAML에서 합니다.
  
     [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]  
  
     다음 애니메이션 구성 방법을 보여 줍니다. 대상에는 <xref:System.Windows.UIElement.Opacity%2A> 의 속성은 <xref:System.Windows.Shapes.Rectangle> 코드에서.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 구문 및 추가 예에 대 한 참조는 [적기](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)합니다.  
  
<a name="opacity_animation_step3"></a>   
### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>3부: Storyboard를 트리거에 연결  
 적용 하 고 시작 하는 가장 쉬운 방법은 한 <xref:System.Windows.Media.Animation.Storyboard> 에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 이벤트 트리거를 사용 하는 것입니다. 이 섹션에서는 연결 하는 방법을 보여 줍니다.는 <xref:System.Windows.Media.Animation.Storyboard> XAML에서 트리거를 사용 합니다.  
  
1.  만들기는 <xref:System.Windows.Media.Animation.BeginStoryboard> 개체 및 스토리 보드를 연결 합니다. A <xref:System.Windows.Media.Animation.BeginStoryboard> 의 형식인 <xref:System.Windows.TriggerAction> 적용 하 고 시작 하는 <xref:System.Windows.Media.Animation.Storyboard>합니다.  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]  
  
2.  만들기는 <xref:System.Windows.EventTrigger> 추가 <xref:System.Windows.Media.Animation.BeginStoryboard> 를 해당 <xref:System.Windows.EventTrigger.Actions%2A> 컬렉션입니다. 설정의 <xref:System.Windows.EventTrigger.RoutedEvent%2A> 속성의는 <xref:System.Windows.EventTrigger> 시작 하려는 라우트된 이벤트에는 <xref:System.Windows.Media.Animation.Storyboard>합니다. (라우트된 이벤트에 대 한 자세한 내용은 참조는 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md).)  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]  
  
3.  추가 <xref:System.Windows.EventTrigger> 에 <xref:System.Windows.FrameworkElement.Triggers%2A> 사각형의 컬렉션입니다.  
  
     [!code-xaml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]  
  
<a name="opacity_animation_step3code"></a>   
### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>3부(코드): Storyboard를 이벤트 처리기에 연결  
 적용 하 고 시작 하는 가장 쉬운 방법은 한 <xref:System.Windows.Media.Animation.Storyboard> 코드의 이벤트 처리기를 사용 하는 합니다. 이 섹션에서는 연결 하는 방법을 보여 줍니다.는 <xref:System.Windows.Media.Animation.Storyboard> 와 코드에서 이벤트 처리기입니다.  
  
1.  에 대 한 등록은 <xref:System.Windows.FrameworkElement.Loaded> 사각형의 이벤트입니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]  
  
2.  이벤트 처리기를 선언합니다. 이벤트 처리기에서 사용 하 여는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 스토리 보드를 적용할 방법을 합니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]  
  
### <a name="complete-example"></a>완성된 예제  
 다음은 XAML의 보기 페이드 인 되는 사각형을 만드는 방법.  
  
 [!code-xaml[animation_ovws2#RectangleOpacityFadeExampleXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]  
  
 다음에서는 코드에서 보기로부터 페이드 인 및 페이드 아웃되는 사각형을 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]  
  
<a name="animationtypes"></a>   
## <a name="animation-types"></a>애니메이션 형식  
 애니메이션은 속성 값을 생성하므로 속성 형식마다 다양한 애니메이션 형식이 존재합니다. 사용 하는 속성에 애니메이션 효과를 주는 <xref:System.Double>와 같은 <xref:System.Windows.FrameworkElement.Width%2A> 는 요소의 속성을 사용 하 여 생성 하는 애니메이션 <xref:System.Double> 값입니다. 사용 하는 속성에 애니메이션 효과를 주는 <xref:System.Windows.Point>를 생성 하는 애니메이션을 사용 하 여 <xref:System.Windows.Point> 값, 및 기타 등등. 속성 형식 수 있으므로 매우에 다양은 <xref:System.Windows.Media.Animation> 네임 스페이스입니다. 다행스럽게도 쉬운 구분을 위해 엄격한 명명 규칙을 따릅니다.  
  
-   \<*형식*> 애니메이션  
  
     "From/To/By" 또는 "basic" 애니메이션으로도 알려져 있는 이러한 클래스는 시작 값과 대상 값 사이에 애니메이션 효과를 주거나 시작 값에 오프셋 값을 추가하여 애니메이션 효과를 줍니다.  
  
    -   시작 값을 지정하려면 애니메이션의 From 속성을 설정합니다.  
  
    -   끝 값을 지정하려면 애니메이션의 To 속성을 설정합니다.  
  
    -   오프셋 값을 지정하려면 애니메이션의 By 속성을 설정합니다.  
  
     이러한 애니메이션이 가장 사용하기 쉬우므로 이 개요의 예제에서도 사용됩니다. From/하/By 애니메이션 From/To/By 애니메이션 개요에서 자세히 설명 되어 있습니다.  
  
-   \<*형식*> AnimationUsingKeyFrames  
  
     키 프레임 애니메이션은 원하는 수의 대상 값을 지정하고 보간 방법을 제어할 수 있으므로 From/To/By 애니메이션보다 훨씬 더 강력합니다. 일부 형식은 키 프레임 애니메이션으로만 애니메이션 효과를 줄 수 있습니다. 키 프레임 애니메이션에 자세히 설명 된 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)합니다.  
  
-   \<*형식*> AnimationUsingPath  
  
     경로 애니메이션에서는 기하학적 경로를 사용하여 애니메이션 사용 값을 생성할 수 있습니다.  
  
-   \<*형식*> AnimationBase  
  
     구현할 때 애니메이션 효과 적용 하는 추상 클래스는 \< *형식*> 값입니다. 이 클래스에 대 한 기본 클래스로 사용 \< *형식*> 애니메이션 및 \< *형식*> AnimationUsingKeyFrames 클래스입니다. 사용자 고유의 사용자 지정 애니메이션을 만들려는 경우에만 이러한 클래스를 직접 처리해야 합니다. 그렇지 않은 경우 사용 하 여는 \< *형식*> 애니메이션 또는 키프레임\<*형식*> 애니메이션 합니다.  
  
 대부분의 경우에서 사용 하려고 수는 \< *형식*>와 같은 애니메이션 클래스 <xref:System.Windows.Media.Animation.DoubleAnimation> 및 <xref:System.Windows.Media.Animation.ColorAnimation>합니다.  
  
 다음 표에서는 몇 가지 일반적인 애니메이션 형식 및 사용되는 일부 속성을 보여 줍니다.  
  
|속성 형식|해당 basic(From/To/By) 애니메이션|해당 키 프레임 애니메이션|해당 경로 애니메이션|사용 예제|  
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|없음|애니메이션 효과 줄의 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 의 <xref:System.Windows.Media.SolidColorBrush> 또는 <xref:System.Windows.Media.GradientStop>합니다.|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|애니메이션 효과 줄의 <xref:System.Windows.FrameworkElement.Width%2A> 의 <xref:System.Windows.Controls.DockPanel> 또는 <xref:System.Windows.FrameworkElement.Height%2A> 의 <xref:System.Windows.Controls.Button>합니다.|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|애니메이션 효과 줄의 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 항목의 위치는 <xref:System.Windows.Media.EllipseGeometry>합니다.|  
|<xref:System.String>|없음|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|없음|애니메이션 효과 줄의 <xref:System.Windows.Controls.TextBlock.Text%2A> 의 <xref:System.Windows.Controls.TextBlock> 또는 <xref:System.Windows.Controls.ContentControl.Content%2A> 의 <xref:System.Windows.Controls.Button>합니다.|  
  
<a name="animationsaretimelines"></a>   
### <a name="animations-are-timelines"></a>애니메이션은 타임라인임  
 모든 애니메이션 형식에서 상속 된 <xref:System.Windows.Media.Animation.Timeline> 클래스; 따라서 모든 애니메이션이 특수 한 유형의 타임 라인입니다. A <xref:System.Windows.Media.Animation.Timeline> 시간을 세그먼트를 정의 합니다. 지정할 수 있습니다는 *타이밍 동작* 일정의: 해당 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, 반복, 및에 얼마나 빨리 시간에 대 한 진행 되는 횟수입니다.  
  
 애니메이션은는 <xref:System.Windows.Media.Animation.Timeline>, 시간 세그먼트를 나타냅니다. 애니메이션 또한 출력 값을 계산 것 진행 되는 동안 해당 지정된 시간 세그먼트 (또는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>). 애니메이션은 진행되거나 "재생"되면서 연결된 속성을 업데이트합니다.  
  
 세 가지 자주 사용 하는 타이밍 속성이 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, 및 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>합니다.  
  
#### <a name="the-duration-property"></a>Duration 속성  
 앞서 설명한 것처럼 타임라인은 시간 세그먼트를 나타냅니다. 이 세그먼트의 길이에 의해 결정 됩니다는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 타임 라인은 일반적으로 사용 하 여 지정 된 <xref:System.Windows.Duration.TimeSpan%2A> 값입니다. 타임라인이 기간 끝에 도달하면 반복이 완료되는 것입니다.  
  
 애니메이션에 사용 하 여 해당 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 속성 현재 값을 결정 하도록 합니다. 지정 하지 않는 경우는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 값에 대 한 애니메이션을 사용 하 여 기본값 1 초입니다.  
  
 다음 구문을의 단순화 된 버전을 보여 줍니다.는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 특성에 대 한 구문에서 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 속성.  
  
*hours* `:` *minutes* `:` *seconds*
  
 다음 표에 몇 가지 나와 <xref:System.Windows.Duration> 설정 및 결과 값입니다.  
  
|설정|결과 값|  
|-------------|---------------------|  
|0:0:5.5|5.5초|  
|0:30:5.5|30분 5.5초|  
|1:30:5.5|1시간 30분 5.5초|  
  
 지정 하는 한 가지 방법은 <xref:System.Windows.Duration> 코드에서 사용 하는 <xref:System.TimeSpan.FromSeconds%2A> 만드는 메서드를 한 <xref:System.TimeSpan>, 새을 선언 <xref:System.Windows.Duration> 하를 사용 하 여 <xref:System.TimeSpan>합니다.  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Duration> 값과 전체 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 구문 참조는 <xref:System.Windows.Duration> 구조입니다.  
  
#### <a name="autoreverse"></a>AutoReverse  
 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성의 끝에 도달한 후 시간 표시 막대 뒤로 재생 되는지 여부를 지정 해당 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>합니다. 이 애니메이션 속성을 설정 하는 경우 `true`의 끝에 도달한 후 해당 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, 끝 값에서 시작 값으로 다시 재생 합니다. 기본적으로이 속성은 `false`합니다.  
  
#### <a name="repeatbehavior"></a>RepeatBehavior  
 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성 타임 라인을 수행 하는 횟수를 지정 합니다. 기본적으로 타임 라인의 반복 횟수를가지고 `1.0`, 재생 되 고 반복 전혀 실행 되지 않습니다.  
  
 이러한 속성 및 다른 사용자에 대 한 자세한 내용은 참조는 [타이밍 동작 개요](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)합니다.  
  
<a name="applyanimationstoproperty"></a>   
## <a name="applying-an-animation-to-a-property"></a>속성에 애니메이션 적용  
 이전 섹션에서는 다양한 애니메이션 유형 및 타이밍 속성에 대해 설명합니다. 이 섹션에서는 애니메이션 효과를 주려는 속성에 애니메이션을 적용하는 방법을 보여 줍니다. <xref:System.Windows.Media.Animation.Storyboard> 개체 속성에 애니메이션을 적용 하는 방법을 제공 합니다. A <xref:System.Windows.Media.Animation.Storyboard> 는 *컨테이너 타임 라인* 포함 된 애니메이션에 대 한 대상 정보를 제공 하는 합니다.  
  
### <a name="targeting-objects-and-properties"></a>개체 및 속성을 대상으로 지정  
 <xref:System.Windows.Media.Animation.Storyboard> 클래스를 제공는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 연결 된 속성입니다. 애니메이션에 이러한 속성을 설정하여 적용할 애니메이션을 지정합니다. 그러나 애니메이션이 개체를 대상으로 지정하려면 먼저 해당 개체에 이름을 지정해야 합니다.  
  
 에 이름을 할당 한 <xref:System.Windows.FrameworkElement> 에 이름을 할당에서 다른 한 <xref:System.Windows.Freezable> 개체입니다. 대부분의 컨트롤 및 패널은 프레임워크 요소입니다. 그러나 브러시, 변환, 기 하 도형 등의 순수한 그래픽 개체 대부분은 Freezable 개체입니다. 형식이 인지 확실 하지 않은 경우는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.Freezable>, 참조는 **상속 계층 구조** 해당 참조 설명서의 섹션입니다.  
  
-   확인 하는 <xref:System.Windows.FrameworkElement> 애니메이션 대상으로 사용자 이름을 설정 하 여 해당 <xref:System.Windows.FrameworkElement.Name%2A> 속성입니다. 코드에서 사용 해야는 <xref:System.Windows.FrameworkElement.RegisterName%2A> 속해 있는 페이지와 요소 이름을 등록 합니다.  
  
-   있도록는 <xref:System.Windows.Freezable> 개체를 애니메이션 대상에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 사용 하면는 [X:name 지시문](../../../../docs/framework/xaml-services/x-name-directive.md) 에 이름을 할당할 수 있습니다. 코드에서 바로 사용할는 <xref:System.Windows.FrameworkElement.RegisterName%2A> 속해 있는 페이지와 개체를 등록 합니다.  
  
 다음 섹션에서 요소 이름 지정의 예제를 제공 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 코드입니다. 이름 및 대상 지정 하는 방법에 대 한 자세한 내용은 참조는 [적기](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)합니다.  
  
### <a name="applying-and-starting-storyboards"></a>Storyboard 적용 및 시작  
 스토리 보드를 시작 하려면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]와 연결 된 <xref:System.Windows.EventTrigger>합니다. <xref:System.Windows.EventTrigger> 는 지정된 된 이벤트가 발생할 때 수행할 작업을 설명 하는 개체입니다. 이러한 작업 중 하나가 될 수 있습니다는 <xref:System.Windows.Media.Animation.BeginStoryboard> 동작을 사용 하 여 스토리 보드를 시작 합니다. 이벤트 트리거는 응용 프로그램이 특정 이벤트에 응답하는 방법을 지정할 수 있도록 하므로 개념적으로 이벤트 처리기와 비슷합니다. 이벤트 처리기와 달리 이벤트 트리거에서 완벽 하 게 설명할 수 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; 다른 코드는 필요 없습니다.  
  
 시작 하는 <xref:System.Windows.Media.Animation.Storyboard> 코드에서 사용할 수 있습니다는 <xref:System.Windows.EventTrigger> 하거나 사용 하 여는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 의 메서드는 <xref:System.Windows.Media.Animation.Storyboard> 클래스입니다.  
  
<a name="controllingstoryboards"></a>   
## <a name="interactively-control-a-storyboard"></a>대화식으로 Storyboard 제어  
 앞의 예제에는 시작 하는 방법을 보여 주었습니다는 <xref:System.Windows.Media.Animation.Storyboard> 이벤트가 발생 합니다. 대화형으로 제어할 수 있습니다는 <xref:System.Windows.Media.Animation.Storyboard> 시작 된 후: 일시 중지, 다시 시작, 중지, 기간 이동, seek 및 제거할 수 있습니다는 <xref:System.Windows.Media.Animation.Storyboard>합니다. 자세한 내용 및 대화형으로 제어 하는 방법을 보여 주는 예제는 <xref:System.Windows.Media.Animation.Storyboard>, 참조는 [적기](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)합니다.  
  
<a name="fillbehaviorsection"></a>   
## <a name="what-happens-after-an-animation-ends"></a>애니메이션이 끝난 후에 발생하는 결과  
 <xref:System.Windows.Media.Animation.FillBehavior> 속성 끝날 때 타임 라인의 동작을 지정 합니다. 기본적으로 타임 라인 시작 <xref:System.Windows.Media.Animation.ClockState.Filling> 종료 합니다. 애니메이션을 <xref:System.Windows.Media.Animation.ClockState.Filling> 최종 출력 값을 유지 합니다.  
  
 <xref:System.Windows.Media.Animation.DoubleAnimation> 이전 예에서 끝나지 때문에 해당 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성이 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>합니다. 다음 예제에서는 유사한 애니메이션을 사용하여 사각형에 애니메이션 효과를 줍니다. 위의 예와 달리는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 및 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 이 애니메이션의 속성을 기본값으로 유지 됩니다. 따라서 애니메이션은 5초 넘게 1에서 0으로 진행된 후 중지합니다.  
  
 [!code-xaml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]  
  
 [!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
 [!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]  
  
 때문에 해당 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 즉 해당 기본값에서 변경 되지 않았습니다 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, 애니메이션 보유 한 다음 마지막 값이 0 끝날 때. 따라서는 <xref:System.Windows.UIElement.Opacity%2A> 애니메이션 후 0으로 사각형은 유지의 종료 합니다. 설정 하는 경우는 <xref:System.Windows.UIElement.Opacity%2A> 사각형을 다른 값의 코드가 아무런 영향을 주지 애니메이션은 영향을 계속 하기 때문에 <xref:System.Windows.UIElement.Opacity%2A> 속성입니다.  
  
 다시 코드에서 애니메이션된 속성을 제어 하는 방법을 사용 하는 것은 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드 null을 지정 하는 <xref:System.Windows.Media.Animation.AnimationTimeline> 매개 변수입니다. 자세한 내용 및 예제에 대 한 참조 [설정는 속성 후 애니메이션에 스토리](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md)합니다.  
  
 가 속성 값을 설정 하는 없지만 <xref:System.Windows.Media.Animation.ClockState.Active> 또는 <xref:System.Windows.Media.Animation.ClockState.Filling> 애니메이션 효과가 없습니다 것 이므로, 속성 값은 변경 합니다. 자세한 내용은 참조는 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)합니다.  
  
<a name="databindingAndAnimatingAnimationsSection"></a>   
## <a name="data-binding-and-animating-animations"></a>데이터 바인딩 및 애니메이션 효과 적용  
 대부분의 애니메이션 속성 바인딩하거나 애니메이션; 데이터를 적용할 수 있습니다. 예를 들어 애니메이션을 적용할 수는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 속성은 <xref:System.Windows.Media.Animation.DoubleAnimation>합니다. 그러나 타이밍 시스템이 작동하는 방식 때문에 데이터 바인딩 또는 애니메이션 효과 주기가 다른 데이터 바인딩 또는 애니메이션 개체와 다르게 동작합니다. 해당 동작을 이해하기 위해 속성에 애니메이션을 적용하는 것이 어떤 의미를 갖는지 이해하면 도움이 됩니다.  
  
 애니메이션 효과 적용 하는 방법을 설명 하는 이전 섹션의 예제를 참조는 <xref:System.Windows.UIElement.Opacity%2A> 사각형의 합니다. 앞의 예제에는 사각형 로드 되 면 해당 이벤트 트리거가 적용 된 <xref:System.Windows.Media.Animation.Storyboard>합니다. 타이밍 시스템의 복사본을 만듭니다는 <xref:System.Windows.Media.Animation.Storyboard> 및 애니메이션 합니다. 이러한 복사본 고정 (읽기 전용으로 설정) 및 <xref:System.Windows.Media.Animation.Clock> 임원의 개체가 만들어집니다. 이러한 클록은 대상 속성에 애니메이션 효과를 주는 실제 작업을 수행합니다.  
  
 타이밍 시스템에 대 한 클록 만듭니다는 <xref:System.Windows.Media.Animation.DoubleAnimation> 개체 및 지정 된 속성에 적용 하는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 의 <xref:System.Windows.Media.Animation.DoubleAnimation>합니다. 타이밍 시스템 시계를 적용 하는 경우에 <xref:System.Windows.UIElement.Opacity%2A> "MyRectangle" 라고 하는 개체의 속성  
  
 에 대 한 클록도 만들어지면는 <xref:System.Windows.Media.Animation.Storyboard>, 클록 모든 속성에 적용 되지 않습니다. 용도 대해 만들어진 클록 해당 자식 클록을 제어 하는 것은 <xref:System.Windows.Media.Animation.DoubleAnimation>합니다.  
  
 애니메이션에 데이터 바인딩 또는 애니메이션 변경 내용을 반영하려면 해당 클록이 다시 생성되어야 합니다. 클록은 자동으로 다시 생성되지 않습니다. 변경 내용을 반영 하는 애니메이션을 하려면 해당 스토리 보드를 사용 하 여 다시 적용 한 <xref:System.Windows.Media.Animation.BeginStoryboard> 또는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드. 이러한 메서드 중 하나를 사용하면 애니메이션이 다시 시작됩니다. 코드에서 사용할 수는 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 의 이전 위치에 스토리 보드를 이동할 메서드의 다시 합니다.  
  
 참조 데이터의 예로 바인딩된 애니메이션을 [키 스플라인 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160011)합니다. 애니메이션 및 타이밍 시스템 작동 하는 방법에 대 한 자세한 내용은 참조 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)합니다.  
  
<a name="otherWaysToAnimateSection"></a>   
## <a name="other-ways-to-animate"></a>애니메이션 효과를 주는 다른 방법  
 이 개요의 예제에서는 Storyboard를 사용하여 애니메이션 효과를 주는 방법을 보여 줍니다. 코드를 사용하면 여러 가지 방법으로 애니메이션 효과를 줄 수 있습니다. 자세한 내용은 참조는 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)합니다.  
  
<a name="animation_samples"></a>   
## <a name="animation-samples"></a>애니메이션 샘플  
 다음 샘플은 응용 프로그램에 애니메이션을 추가하는 데 도움이 될 수 있습니다.  
  
-   [From, To 및 By 애니메이션 대상 값 샘플](http://go.microsoft.com/fwlink/?LinkID=159988)  
  
     다른 From/To/By 설정을 보여 줍니다.  
  
-   [애니메이션 타이밍 동작 샘플](http://go.microsoft.com/fwlink/?LinkID=159970)  
  
     애니메이션의 타이밍 동작을 제어할 수는 여러 가지 방법을 보여 줍니다. 또한 이 샘플은 애니메이션의 대상 값에 대해 데이터 바인딩을 수행하는 방법을 보여 줍니다.  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)|타이밍 시스템 사용 하는 방법에 대해 설명 된 <xref:System.Windows.Media.Animation.Timeline> 및 <xref:System.Windows.Media.Animation.Clock> 애니메이션을 만들 수 있는 클래스입니다.|  
|[애니메이션에 대한 유용한 정보](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)|성능 같은 애니메이션 문제 해결에 도움이 되는 유용한 정보를 나열합니다.|  
|[사용자 지정 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)|키 프레임, 애니메이션 클래스 또는 프레임당 콜백으로 애니메이션 시스템을 확장하는 방법을 설명합니다.|  
|From/To/By 애니메이션 개요|두 값 사이를 전환하는 애니메이션을 만드는 방법을 설명합니다.|  
|[키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)|보간 방법을 제어하는 기능을 포함하여 여러 대상 값을 사용하여 애니메이션을 만드는 방법을 설명합니다.|  
|[감속/가속 함수](../../../../docs/framework/wpf/graphics-multimedia/easing-functions.md)|반송 같은 실질적인 동작을 얻기 위해 애니메이션에 수학 수식을 적용하는 방법을 설명합니다.|  
|[경로 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)|복잡한 경로를 따라 개체를 이동하거나 회전하는 방법을 설명합니다.|  
|[속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)|Storyboard, 로컬 애니메이션, 시계 및 프레임당 애니메이션을 사용하는 속성 애니메이션에 대해 설명합니다.|  
|[Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)|여러 개의 타임라인을 갖는 Storyboard를 사용하여 복잡한 애니메이션을 만드는 방법을 설명 합니다.|  
|[타이밍 동작 개요](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)|설명의 <xref:System.Windows.Media.Animation.Timeline> 유형 및 애니메이션에 사용 되는 속성입니다.|  
|[타이밍 이벤트 개요](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)|사용할 수 있는 이벤트에 설명 된 <xref:System.Windows.Media.Animation.Timeline> 및 <xref:System.Windows.Media.Animation.Clock> 개체와 같은 타임 라인의 지점에서 코드를 실행 하기 위한 시작, 일시 중지, 재개, 건너뛸 또는 중지 합니다.|  
|[방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)|응용 프로그램에서 애니메이션 및 타임라인을 사용하기 위한 코드 예제가 포함되어 있습니다.|  
|[Clock 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/clocks-how-to-topics.md)|사용 하기 위한 코드 예제가 포함 되어는 <xref:System.Windows.Media.Animation.Clock> 응용 프로그램의 개체입니다.|  
|[키 프레임 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)|응용 프로그램에서 키 프레임 애니메이션을 사용하기 위한 코드 예제가 포함되어 있습니다.|  
|[경로 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)|응용 프로그램에서 경로 애니메이션을 사용하기 위한 코드 예제가 포함되어 있습니다.|  
  
<a name="reference"></a>   
## <a name="reference"></a>참조  
 <xref:System.Windows.Media.Animation.Timeline>  
  
 <xref:System.Windows.Media.Animation.Storyboard>  
  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
  
 <xref:System.Windows.Media.Animation.Clock>
