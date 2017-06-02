---
title: "애니메이션 개요 | Microsoft Docs"
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
  - "애니메이션 storyboard [WPF]"
  - "애니메이션 [WPF], 개요"
ms.assetid: bd9ce563-725d-4385-87c9-d7ee38cf79ea
caps.latest.revision: 73
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 73
---
# 애니메이션 개요
<a name="introduction"></a>[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 강력한 매력적인 사용자 인터페이스와 멋진 문서를 만들 수 있도록 하는 그래픽 및 레이아웃 기능 집합을 제공 합니다. 애니메이션을 훨씬 더 화려하 하 고 유용한 멋진 사용자 인터페이스를 가능 합니다. 방금 배경 색에 애니메이션을 적용 하거나 애니메이션 적용 하 여 <xref:System.Windows.Media.Transform>, 유용한 시각적 효과 제공 하거나 화면을 멋지게 전환을 만들 수 있습니다.  
  
 이 개요에서는에 대 한 소개는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션, 타이밍 시스템입니다. 애니메이션에 중점을 둡니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스토리 보드를 사용 하 여 개체입니다.  

<a name="introducinganimations"></a>   
## <a name="introducing-animations"></a>애니메이션 소개  
 애니메이션은 일련의 마지막 약간씩 다르게 이미지를 빠르게 순환 하 여 만든 감을. 이미지 그룹을 하나의 장면에 게 뇌입니다. 이 영화의이 가정은 초당 많은 사진이 나 프레임을 기록 하는 카메라를 사용 하 여 만들어집니다. 프레임은 재생 프로젝터로 움직이는 그림 청중에 게 표시 됩니다.  
  
 컴퓨터의 애니메이션은 유사 합니다. 예를 들어, 보기에서 사각형 페이드 그리기를 수행 하는 프로그램 다음과 같이 작동 합니다.  
  
-   프로그램에는 타이머를 만듭니다.  
  
-   프로그램 설정 간격으로 얼마나 많은 시간이 경과 타이머를 확인 합니다.  
  
-   타이머를 검사 될 때마다 시간 경과에 따라 사각형에 대 한 현재 불투명도 값을 계산 합니다.  
  
-   그런 다음 프로그램 사각형을 새 값으로 업데이트 하 고 그립니다.  
  
 이전에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] 개발자가 만들고 타이밍 시스템을 관리할 하거나 특별 한 사용자 지정 라이브러리를 사용 해야 했습니다.                  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]관리 되는 코드를 통해 노출 되는 효율적인 타이밍 시스템이 포함 하 고 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 깊이에 통합 된 및는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프레임 워크입니다.                  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]애니메이션을 사용 하면 쉽게 컨트롤 및 기타 그래픽 개체에 애니메이션 효과 주기 수입니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]타이밍 시스템을 관리 하 고 효율적으로 화면을 다시 그리기의 모든 백그라운드 작업을 처리 합니다. 이러한 효과 내는 방법 대신 만들려는 효과에 집중할 수 있도록 하는 타이밍 클래스를 제공 합니다.                  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]또한 손쉽게 애니메이션 클래스가 상속할 수는 기본 클래스를 노출 하 여 사용자 고유의 애니메이션 만들기, 사용자 지정된 애니메이션을 생성 합니다. 이러한 사용자 지정 애니메이션의 많은 표준 애니메이션 클래스의 성능 이점을 얻습니다.  
  
<a name="thewpftimingsystem"></a>   
## <a name="wpf-property-animation-system"></a>WPF 속성 애니메이션 시스템  
 타이밍 시스템에 대 한 몇 가지 중요 한 개념을 이해 하는 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션을 더 쉽게 사용할 수 있습니다. 가장 중요 한은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 개별 속성에 애니메이션을 적용 하 여 개체에 애니메이션 적용 합니다. 예를 들어, 프레임 워크 요소 확장을 위해 애니메이션을 적용 하면 해당 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성입니다. 뷰에서 사라지게 하는 개체를 위해 애니메이션을 적용 하면 해당 <xref:System.Windows.UIElement.Opacity%2A> 속성입니다.  
  
 애니메이션 기능을 속성에 대 한 것은 다음 세 가지 요구 사항을 충족 해야 합니다.  
  
-   종속성 속성 이어야 합니다.  
  
-   상속 하는 클래스에 속해 있어야 <xref:System.Windows.DependencyObject> 구현 하는 <xref:System.Windows.Media.Animation.IAnimatable> 인터페이스입니다.  
  
-   있어야 호환 가능한 애니메이션 형식을 사용할 수 있습니다. (경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 제공 하지 않으면, 직접 만들 수 있습니다. 참조는 [사용자 지정 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md).)  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]많은 개체가 포함 된 <xref:System.Windows.Media.Animation.IAnimatable> 속성입니다. 와 같은 컨트롤 <xref:System.Windows.Controls.Button> 및 <xref:System.Windows.Controls.TabControl>, 고도 <xref:System.Windows.Controls.Panel> 및 <xref:System.Windows.Shapes.Shape> 개체에서 상속 <xref:System.Windows.DependencyObject>합니다. 해당 속성의 대부분은 종속성 속성입니다.  
  
 사용할 수 있습니다 애니메이션 거의 어디서 나 스타일 및 템플릿 컨트롤에 포함 하는. 애니메이션 시각적인; 필요가 없습니다. 개체에 속하지 않는 사용자 인터페이스의이 섹션에 설명 된 조건을 충족 하는 경우 애니메이션을 적용할 수 있습니다.  
  
<a name="storyboardwalkthrough"></a>   
## <a name="example-make-an-element-fade-in-and-out-of-view"></a>예: 한 요소 페이드 아웃 확인  
 사용 하는 방법을 보여 주는이 예제는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션을 종속성 속성의 값에 애니메이션을 적용 합니다. 사용 하 여는 <xref:System.Windows.Media.Animation.DoubleAnimation>, 생성 하는 애니메이션의 형식인 <xref:System.Double> 애니메이션 효과를 주는 값을는 <xref:System.Windows.UIElement.Opacity%2A> 속성은 <xref:System.Windows.Shapes.Rectangle>. 결과적으로 <xref:System.Windows.Shapes.Rectangle> 서서히 뷰에 나타나거나 사라집니다.  
  
 예제의 첫 번째 부분은 만듭니다는 <xref:System.Windows.Shapes.Rectangle> 요소입니다. 다음 단계는 애니메이션을 만들고 사각형의에 적용 하는 방법을 보여 줍니다 <xref:System.Windows.UIElement.Opacity%2A> 속성입니다.  
  
 다음에 만드는 방법을 보여 줍니다는 <xref:System.Windows.Shapes.Rectangle> 요소에는 <xref:System.Windows.Controls.StackPanel> xaml에서입니다.  
  
 [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_1)]  
  
 다음에 만드는 방법을 보여 줍니다는 <xref:System.Windows.Shapes.Rectangle> 요소에는 <xref:System.Windows.Controls.StackPanel> 코드에서입니다.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_1)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_1)]  
  
<a name="opacity_animation_step1"></a>   
### <a name="part-1-create-a-doubleanimation"></a>1 부:는 DoubleAnimation 만들기  
 페이드 아웃 하기 위해 방법은 애니메이션을 적용 하는 것은 <xref:System.Windows.UIElement.Opacity%2A> 속성입니다. 때문에 <xref:System.Windows.UIElement.Opacity%2A> 형식의 속성은 <xref:System.Double>, double 값을 생성 하는 애니메이션을 사용 해야 합니다. A <xref:System.Windows.Media.Animation.DoubleAnimation> 는 그러한 애니메이션 중 하나입니다. A <xref:System.Windows.Media.Animation.DoubleAnimation> 두 double 값 사이의 변환을 생성 합니다. 설정 시작 값을 지정 하려면 해당 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성입니다. 설정한 끝 값을 지정 하려면 해당 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성입니다.  
  
1.  불투명도 값 `1.0` 완전히 불투명 개체와의 불투명도 값을 사용 하면 `0.0` 사용 하면 완전히 표시 되지 않습니다. To make the animation transition from                                  `1.0` to                                  `0.0` you set its                                  <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to                                  `1.0` and its                                  <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property to                                  `0.0`. 다음에 만드는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.DoubleAnimation> xaml에서입니다.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_2)]  
  
     다음에 만드는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.DoubleAnimation> 코드에서입니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_2)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_2)]  
  
2.  다음으로 지정 해야는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>합니다. <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 애니메이션 시작 값에서 해당 대상 값으로 이동 하는 데 걸리는 시간을 지정 합니다. 다음을 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> XAML에서&5; 초입니다.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_3)]  
  
     다음을 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 코드에서&5; 초입니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_3)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_3)]  
  
3.  앞의 코드에서 전환 되는 애니메이션을 보여 주었습니다 `1.0` 를 `0.0`, 완전히 표시 되지 않도록 하려면 완전히 불투명에서 사라지는 데 대상 요소에 이르게 됩니다. 완전히 사라진 후 보기로 다시 페이드 요소를 설정의 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성에 애니메이션을 `true`합니다. 애니메이션 반복 무기한 설정를 해당 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>합니다. 다음을 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 및 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> XAML의 속성입니다.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_4)]  
  
     다음을 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 및 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 코드에서 속성입니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Class1.cs#rectangleopacityfadeexamplecode_4)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/Class1.vb#rectangleopacityfadeexamplecode_4)]  
  
<a name="opacity_animation_step2"></a>   
### <a name="part-2-create-a-storyboard"></a>2 부: 스토리 보드 만들기  
 만들 개체에 애니메이션을 적용할는 <xref:System.Windows.Media.Animation.Storyboard> 사용 하 여는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 연결 된 개체를 지정 하는 속성 및 속성에 애니메이션을 적용 합니다.  
  
1.  만들기는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션을 자식으로 추가 합니다. 다음에 만드는 방법을 보여 줍니다는 <xref:System.Windows.Media.Animation.Storyboard> xaml에서입니다.  
  
     <!-- TODO: review snippet reference [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_5)]  -->  
  
     만드는 <xref:System.Windows.Media.Animation.Storyboard> 코드에서 선언 된 <xref:System.Windows.Media.Animation.Storyboard> 클래스 수준에서 변수입니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_100)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_100)]  
  
     다음 초기화는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션을 자식으로 추가 합니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_101)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_101)]  
  
2.  <xref:System.Windows.Media.Animation.Storyboard> 는 애니메이션을 적용할 위치를 알아야 합니다. 사용 된 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=fullName> 연결 된 속성을 개체에 애니메이션 효과 주기를 지정 합니다. 다음에서는의 대상 이름을 설정 하는 방법을 보여 줍니다.는 <xref:System.Windows.Media.Animation.DoubleAnimation> 를 `MyRectangle` xaml에서입니다.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_6)]  
  
     다음에서는의 대상 이름을 설정 하는 방법을 보여 줍니다.는 <xref:System.Windows.Media.Animation.DoubleAnimation> 를 `MyRectangle` 코드에서입니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_102)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_102)]  
  
3.  사용 된 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 연결 된 속성을 속성에 애니메이션 효과 적용을 지정 합니다. 다음 애니메이션은 구성 하는 방법을 보여 줍니다. 대상에는 <xref:System.Windows.UIElement.Opacity%2A> 의 속성은 <xref:System.Windows.Shapes.Rectangle> XAML에서.  
  
     [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml_7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/Window1.xaml#rectangleopacityfadeexamplexaml_7)]  
  
     다음 애니메이션은 구성 하는 방법을 보여 줍니다. 대상에는 <xref:System.Windows.UIElement.Opacity%2A> 의 속성은 <xref:System.Windows.Shapes.Rectangle> 코드에서.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_103)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_103)]  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 구문 예를 보려면 다음을 참조 하 고는 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)합니다.  
  
<a name="opacity_animation_step3"></a>   
### <a name="part-3-xaml-associate-the-storyboard-with-a-trigger"></a>스토리 보드를 트리거와 (XAML) 3 부: 연결  
 적용 하 고 시작 하는 가장 쉬운 방법은 <xref:System.Windows.Media.Animation.Storyboard> 에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 이벤트 트리거를 사용 하는 것입니다.                          이 섹션에서는 연결 하는 방법을 보여 줍니다.는 <xref:System.Windows.Media.Animation.Storyboard> XAML에서 트리거를 사용 합니다.  
  
1.  만들기는 <xref:System.Windows.Media.Animation.BeginStoryboard> 개체를 스토리 보드를 연결 합니다. A <xref:System.Windows.Media.Animation.BeginStoryboard> 의 형식인 <xref:System.Windows.TriggerAction> 적용 하 고 시작 하는 <xref:System.Windows.Media.Animation.Storyboard>합니다.  
  
     [!code-xml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_3)]  
  
2.  만들기는 <xref:System.Windows.EventTrigger> 추가 <xref:System.Windows.Media.Animation.BeginStoryboard> 를 해당 <xref:System.Windows.EventTrigger.Actions%2A> 컬렉션입니다. 설정의 <xref:System.Windows.EventTrigger.RoutedEvent%2A> 의 속성은 <xref:System.Windows.EventTrigger> 시작 하려는 라우트된 이벤트에는 <xref:System.Windows.Media.Animation.Storyboard>합니다. (라우트된 이벤트에 대 한 자세한 내용은 참조는 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md).)  
  
     [!code-xml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_2)]  
  
3.  추가 된 <xref:System.Windows.EventTrigger> 에 <xref:System.Windows.FrameworkElement.Triggers%2A> 사각형의 컬렉션입니다.  
  
     [!code-xml[animation_ovws_snippet#RectangleOpacityFadeExampleInline_1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/RectangleOpacityFadeExample.xaml#rectangleopacityfadeexampleinline_1)]  
  
<a name="opacity_animation_step3code"></a>   
### <a name="part-3-code-associate-the-storyboard-with-an-event-handler"></a>스토리 보드를 이벤트 처리기 (코드) 3 부: 연결  
 적용 하 고 시작 하는 가장 쉬운 방법은 <xref:System.Windows.Media.Animation.Storyboard> 이벤트 처리기를 사용 하는 코드에서입니다. 이 섹션에서는 연결 하는 방법을 보여 줍니다.는 <xref:System.Windows.Media.Animation.Storyboard> 코드에서를 이벤트 처리기입니다.  
  
1.  에 대 한 등록의 <xref:System.Windows.FrameworkElement.Loaded> 사각형의 이벤트입니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_104)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_104)]  
  
2.  이벤트 처리기를 선언 합니다. 이벤트 처리기에서 사용 하 여는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 스토리 보드를 적용 하는 방법입니다.  
  
     [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode_105)]
     [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode_105](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode_105)]  
  
### <a name="complete-example"></a>전체 예제  
 다음 XAML에서 뷰 페이드 인 되는 사각형을 만드는 방법을 보여줍니다.  
  
 [!code-xml[animation_ovws2#RectangleOpacityFadeExampleXaml](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml#rectangleopacityfadeexamplexaml)]  
  
 다음 코드에서 페이드 인 되는 사각형을 만드는 방법을 보여줍니다.  
  
 [!code-csharp[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws2/CSharp/MainWindow.xaml.cs#rectangleopacityfadeexamplecode)]
 [!code-vb[animation_ovws2#RectangleOpacityFadeExampleCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws2/VisualBasic/MainWindow.xaml.vb#rectangleopacityfadeexamplecode)]  
  
<a name="animationtypes"></a>   
## <a name="animation-types"></a>애니메이션 형식  
 애니메이션 속성 값을 생성 하므로 다양 한 애니메이션 유형에 속성 형식에 존재 합니다. 사용 하는 속성에 애니메이션 효과 주기는 <xref:System.Double>와 같은 <xref:System.Windows.FrameworkElement.Width%2A> 있는 요소의 속성을 생성 하는 애니메이션을 사용 <xref:System.Double> 값입니다. 사용 하는 속성에 애니메이션 효과 주기는 <xref:System.Windows.Point>를 생성 하는 애니메이션을 사용 하 여 <xref:System.Windows.Point> 값 및 기타 등등 합니다. 다른 속성 유형의 수를 되어의 몇 가지 애니메이션 클래스는 <xref:System.Windows.Media.Animation> 네임 스페이스입니다. 다행 스럽게도 쉽게 구분할 수 있도록 엄격한 명명 규칙을 따릅니다.  
  
-   \<                         *형식*> 애니메이션  
  
     시작 및 대상 값 사이 또는 오프셋된 값을 해당 시작 값에 추가 하 여 애니메이션 "From/To/By" 또는 "기본" 애니메이션 이라고 이러한 합니다.  
  
    -   시작 값을 지정 하려면 애니메이션의 From 속성을 설정 합니다.  
  
    -   끝 값을 지정 하려면 애니메이션의 To 속성을 설정 합니다.  
  
    -   오프셋된 값을 지정 하려면 애니메이션의 By 속성을 설정 합니다.  
  
     이 개요의 예제에서는 가장 사용 하기 쉬운 있기 때문에 이러한 애니메이션을 사용 합니다. From/To/By 애니메이션 From/To/By 애니메이션 개요에서 자세히 설명 되어 있습니다.  
  
-   \<                         *형식*> 뿐임  
  
     키 프레임 애니메이션은 원하는 수의 대상 값을 지정 하 고도 보간 방법을 제어할 수 있으므로 From/To/By 애니메이션 보다 훨씬 강력 합니다. 일부 형식은 키 프레임 애니메이션을 애니메이션만 있습니다. 키 프레임 애니메이션에 자세히 설명 된 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)합니다.  
  
-   \<                         *형식*> AnimationUsingPath  
  
     경로 애니메이션을 사용 하 여 애니메이션된 값을 생성 하기 위해 기하학적 경로 사용할 수 있습니다.  
  
-   \<                         *형식*> AnimationBase  
  
     구현 하는 경우 애니메이션을 적용 하는 추상 클래스는 <> \</> *형식*> 값입니다. 이 클래스에 대 한 기본 클래스로 사용 <> \</> *형식*> 애니메이션 및 <> \</> *형식*> 뿐임 클래스입니다. 사용자 고유의 사용자 지정 애니메이션을 만드는 경우에 이러한 클래스를 직접 처리 해야 합니다. 그렇지 않은 경우 사용 하 여 한 <> \</> *형식*> 애니메이션 또는 키 프레임<>*형식*> 애니메이션 합니다.  
  
 사용 해야 할 대부분의 경우에는 <> \</> *형식*>와 같은 애니메이션 클래스 <xref:System.Windows.Media.Animation.DoubleAnimation> 및 <xref:System.Windows.Media.Animation.ColorAnimation>합니다.  
  
 다음 표에서 몇 가지 일반적인 애니메이션 형식 및 사용 되는 일부 속성을 보여 줍니다.  
  
|속성 형식|해당 (From/To/By) basic 애니메이션|해당 키 프레임 애니메이션|해당 경로 애니메이션|사용 예|  
|-------------------|----------------------------------------------------|---------------------------------------|----------------------------------|-------------------|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|없음|Animate the                                  <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a                                  <xref:System.Windows.Media.SolidColorBrush> or a                                  <xref:System.Windows.Media.GradientStop>.|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|Animate the                                  <xref:System.Windows.FrameworkElement.Width%2A> of a                                  <xref:System.Windows.Controls.DockPanel> or the                                  <xref:System.Windows.FrameworkElement.Height%2A> of a                                  <xref:System.Windows.Controls.Button>.|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|애니메이션 효과 주기는 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 항목의 위치는 <xref:System.Windows.Media.EllipseGeometry>합니다.|  
|<xref:System.String>|없음|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|없음|Animate the                                  <xref:System.Windows.Controls.TextBlock.Text%2A> of a                                  <xref:System.Windows.Controls.TextBlock> or the                                  <xref:System.Windows.Controls.ContentControl.Content%2A> of a                                  <xref:System.Windows.Controls.Button>.|  
  
<a name="animationsaretimelines"></a>   
### <a name="animations-are-timelines"></a>애니메이션은 타임 라인  
 모든 애니메이션 형식에서 상속 된 <xref:System.Windows.Media.Animation.Timeline> 클래스, 따라서 모든 애니메이션은 타임 라인의 특수 형식입니다. A <xref:System.Windows.Media.Animation.Timeline> 시간 세그먼트를 정의 합니다. 지정할 수는 *타이밍 동작* 는 타임 라인의: 해당 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, 반복 및 진행 속도 제어할 것에 대 한 것이 얼마나 많은 시간입니다.  
  
 애니메이션은는 <xref:System.Windows.Media.Animation.Timeline>, 시간 세그먼트를 나타냅니다. 지정 된 시간 세그먼트의 하지만 닫힘으로 애니메이션 출력 값 계산 (또는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>). 애니메이션을 진행 또는 "재생" 경우 연결 된 속성을 업데이트 합니다.  
  
 세 가지 자주 사용 되는 타이밍 속성이 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, 및 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>합니다.  
  
#### <a name="the-duration-property"></a>Duration 속성  
 앞서 설명한 것 처럼 일정 시간 세그먼트를 나타냅니다. 해당 세그먼트의 길이에 의해 결정 됩니다는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 타임 라인은 일반적으로 사용 하 여 지정 된 <xref:System.Windows.Duration.TimeSpan%2A> 값입니다. 일정 기간이의 끝에 도달 하면 반복을 완료 되었습니다.  
  
 애니메이션에 사용 하 여 해당 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 속성을 현재 값을 결정 합니다. 지정 하지 않은 경우는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 값에 대 한 애니메이션을 사용 하 여 기본값 1 초입니다.  
  
 다음 구문을의 단순화 된 버전을 보여 줍니다.는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 특성에 대 한 구문에서 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 속성.  
  
||  
|-|  
|*hours* `:` *minutes* `:` *seconds*|  
  
 다음 표에 몇 가지 나와 <xref:System.Windows.Duration> 설정 및 결과 값입니다.  
  
|설정|결과 값|  
|-------------|---------------------|  
|0:0:5.5|5.5 초입니다.|  
|0:30:5.5|30 분 5.5 초입니다.|  
|1:30:5.5|1 시간 30 분, 및 5.5 초입니다.|  
  
 지정 하는 한 가지 방법은 <xref:System.Windows.Duration> 코드에서 사용 하는 <xref:System.TimeSpan.FromSeconds%2A> 만드는 메서드를 한 <xref:System.TimeSpan>, 새을 선언 <xref:System.Windows.Duration> 를 사용 하 여 <xref:System.TimeSpan>합니다.  
  
 에 대 한 자세한 내용은 <xref:System.Windows.Duration> 값과 전체 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 구문 참조는 <xref:System.Windows.Duration> 구조입니다.  
  
#### <a name="autoreverse"></a>AutoReverse  
 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성의 끝에 도달한 후 타임 라인 뒤로 재생 되는지 여부를 지정 합니다. 해당 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>합니다. 이 애니메이션 속성을 설정 하는 경우 `true`의 끝에 도달한 후 해당 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, 끝 값에서 시작 값으로 다시 재생 합니다. 이 속성은 기본적으로 `false`합니다.  
  
#### <a name="repeatbehavior"></a>RepeatBehavior  
 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성 타임 라인을 재생 하는 횟수를 지정 합니다. 기본적으로 타임 라인의 반복 횟수를가지고 `1.0`, 재생 되 고 전혀 반복 되지 않습니다.  
  
 이러한 속성 및 다른 사용자에 대 한 자세한 내용은 참조는 [타이밍 동작 개요](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)합니다.  
  
<a name="applyanimationstoproperty"></a>   
## <a name="applying-an-animation-to-a-property"></a>속성에 애니메이션 적용  
 이전 섹션에서는 다양 한 유형의 애니메이션 및 타이밍 속성에 설명 합니다. 이 섹션에 애니메이션 효과를 원하는 속성에 애니메이션을 적용 하는 방법을 보여 줍니다.                  <xref:System.Windows.Media.Animation.Storyboard> 개체 속성에 애니메이션을 적용 하는 방법을 제공 합니다. A <xref:System.Windows.Media.Animation.Storyboard> 는 *컨테이너 타임 라인* 포함 된 애니메이션에 대 한 대상 정보를 제공 하는 합니다.  
  
### <a name="targeting-objects-and-properties"></a>개체 및 속성을 대상으로 지정  
 <xref:System.Windows.Media.Animation.Storyboard> 클래스를 제공 된 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 연결 된 속성입니다. 애니메이션에 이러한 속성을 설정 하 여 하면 애니메이션을 지시 애니메이션을 적용 합니다. 그러나 애니메이션 대상 개체를 하기 전에 개체가 일반적으로 이름을 지정 합니다.  
  
 에 이름을 할당 한 <xref:System.Windows.FrameworkElement> 에 이름을 할당에서 다른 한 <xref:System.Windows.Freezable> 개체입니다. 대부분의 컨트롤 및 패널은 프레임 워크 요소입니다. 그러나 브러시, 변환, 기 하 도형 등 대부분의 순수 하 게 그래픽 개체는 freezable 개체. 형식 인지 확실 하지 않은 경우는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.Freezable>, 참조는 **상속 계층 구조** 섹션의 참조 설명서입니다.  
  
-   확인 하는 <xref:System.Windows.FrameworkElement> 애니메이션 대상으로 사용자 이름을 설정 하 여 해당 <xref:System.Windows.FrameworkElement.Name%2A> 속성입니다. 코드에서 사용 해야는 <xref:System.Windows.FrameworkElement.RegisterName%2A> 속해 있는 페이지와 요소 이름을 등록 합니다.  
  
-   있도록는 <xref:System.Windows.Freezable> 개체에 애니메이션 대상 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용 하면는 [X:name 지시문](../../../../docs/framework/xaml-services/x-name-directive.md) 이름을 할당 하 합니다. 코드에서 방금 사용은 <xref:System.Windows.FrameworkElement.RegisterName%2A> 속해 있는 페이지와 개체를 등록 합니다.  
  
 다음 섹션의 요소 이름 지정의 예제를 제공 합니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 코드입니다. 이름 및 대상 지정 하는 방법에 대 한 자세한 정보에 대 한 참조는 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)합니다.  
  
### <a name="applying-and-starting-storyboards"></a>적용 하 고 스토리 보드를 시작 합니다.  
 스토리 보드를 시작 하려면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]와 연결 된 <xref:System.Windows.EventTrigger>합니다. <xref:System.Windows.EventTrigger> 는 지정된 된 이벤트가 발생할 때 수행할 작업을 설명 하는 개체입니다. 이러한 작업 중 하나가 될 수 있습니다는 <xref:System.Windows.Media.Animation.BeginStoryboard> 작업을 사용 하 여 스토리 보드를 시작 합니다. 이벤트 트리거는 응용 프로그램이 특정 이벤트에 응답 하는 방법을 지정할 수 있도록 때문에 이벤트 처리기에 비슷한 개념입니다. 이벤트 처리기와 달리 이벤트 트리거에서 완벽 하 게 설명할 수 있는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; 없는 다른 코드를 사용 해야 합니다.  
  
 시작 하려면는 <xref:System.Windows.Media.Animation.Storyboard> 코드에서 사용할 수는 <xref:System.Windows.EventTrigger> 하거나 사용 하 여는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 의 메서드는 <xref:System.Windows.Media.Animation.Storyboard> 클래스.  
  
<a name="controllingstoryboards"></a>   
## <a name="interactively-control-a-storyboard"></a>스토리 보드를 대화형으로 제어  
 앞의 예제에는 시작 하는 방법을 보여 주었습니다는 <xref:System.Windows.Media.Animation.Storyboard> 이벤트가 발생 합니다. 또한 대화형으로 제어할 수는 <xref:System.Windows.Media.Animation.Storyboard> 시작 된 후: 일시 중지, 다시 시작, 중지, 채우기 기간으로 이동, 검색 및 제거할 수 있습니다는 <xref:System.Windows.Media.Animation.Storyboard>합니다. 자세한 내용 및 대화형으로 제어 하는 방법을 보여 주는 예제는 <xref:System.Windows.Media.Animation.Storyboard>, 참조는 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)합니다.  
  
<a name="fillbehaviorsection"></a>   
## <a name="what-happens-after-an-animation-ends"></a>애니메이션이 끝난 후 어떻게 될까요?  
 <xref:System.Windows.Media.Animation.FillBehavior> 속성 끝날 때 타임 라인의 동작을 지정 합니다. 기본적으로 타임 라인 시작 <xref:System.Windows.Media.Animation.ClockState> 종료 될 때입니다. 애니메이션을 <xref:System.Windows.Media.Animation.ClockState> 최종 출력 값을 유지 합니다.  
  
 <xref:System.Windows.Media.Animation.DoubleAnimation> 이전 예제에서 끝나지 때문에 해당 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성이 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>합니다. 다음 예제에서는 유사한 애니메이션을 사용 하 여 사각형에 애니메이션 효과 적용 합니다. 위의 예와 달리는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 및 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 이 애니메이션의 속성을 기본값으로 유지 됩니다. 따라서 애니메이션 진행 되는 1에서 0으로 5 초 동안 한 후 중지 합니다.  
  
 [!code-xml[animation_ovws_snippet#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/FillBehaviorExample.xaml#fillbehaviorexamplerectangleinline)]  
  
 [!code-csharp[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/FillBehaviorExample.cs#fillbehaviorexamplerectangleinline)]
 [!code-vb[animation_ovws_procedural_snip#FillBehaviorExampleRectangleInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/fillbehaviorexample.vb#fillbehaviorexamplerectangleinline)]  
  
 때문에 해당 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 는 해당 기본값에서 변경 되지 않았습니다 <xref:System.Windows.Media.Animation.FillBehavior>, 애니메이션 보유 한 최종 값이 0 끝날 때. 따라서는 <xref:System.Windows.UIElement.Opacity%2A> 종료 후 애니메이션 0으로 사각형 그대로 유지 됩니다. 설정 하는 경우는 <xref:System.Windows.UIElement.Opacity%2A> 사각형을 다른 값의 사용자 코드는 아무런 영향을 주지 애니메이션 여전히 영향을 받는 때문에 <xref:System.Windows.UIElement.Opacity%2A> 속성입니다.  
  
 다시 코드에서 애니메이션된 속성을 제어 하는 방법을 사용 하는 것은 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드에 null을 지정 하는 <xref:System.Windows.Media.Animation.AnimationTimeline> 매개 변수입니다. 자세한 내용 및 예제에 대 한 참조 [설정 된 속성 후 애니메이션 스토리 보드를](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md)합니다.  
  
 가 속성 값을 설정 하지만 <xref:System.Windows.Media.Animation.ClockState> 또는 <xref:System.Windows.Media.Animation.ClockState> 속성 값은 변경, 애니메이션 표시에 영향을 주지 않습니다. 자세한 내용은 참조는 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)합니다.  
  
<a name="databindingAndAnimatingAnimationsSection"></a>   
## <a name="data-binding-and-animating-animations"></a>데이터 바인딩 및 애니메이션을 애니메이션 적용  
 대부분의 애니메이션 속성에 바인딩하거나 애니메이션; 데이터 일 수 있습니다. 예를 들어 애니메이션을 적용할 수는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 의 속성을 <xref:System.Windows.Media.Animation.DoubleAnimation>합니다. 그러나 타이밍 시스템이 작동 하는 방식 때문에 데이터 바인딩 또는 애니메이션 애니메이션 다른 데이터 처럼 작동 하지 않기 바인딩된 또는 애니메이션이 적용 된 개체입니다. 해당 동작을 이해 하려면 속성에 애니메이션을 적용 하는 의미를 이해할 수 있습니다.  
  
 애니메이션을 적용 하는 방법을 보여 주는 이전 단원의 예제를 참조 하십시오는 <xref:System.Windows.UIElement.Opacity%2A> 사각형입니다. 해당 이벤트 트리거를 적용 하는 이전 예제에서 사각형 로드 되 면는 <xref:System.Windows.Media.Animation.Storyboard>합니다. 타이밍 시스템의 복사본을 만듭니다는 <xref:System.Windows.Media.Animation.Storyboard> 및 애니메이션 합니다. 이러한 복사본은 고정 (읽기 전용으로 설정 됨) 및 <xref:System.Windows.Media.Animation.Clock> 프로토타입은 개체가 만들어집니다. 이러한 clock 대상된 속성에 애니메이션 적용의 실제 작업을 수행 합니다.  
  
 타이밍 시스템에 대 한 클록 만듭니다는 <xref:System.Windows.Media.Animation.DoubleAnimation> 개체와 지정 된 속성에 적용 하 고는 <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 의 <xref:System.Windows.Media.Animation.DoubleAnimation>. 타이밍 시스템 시계를 적용 하는 경우에 <xref:System.Windows.UIElement.Opacity%2A> "MyRectangle." 라고 하는 개체의 속성  
  
 에 대 한 클록도 만들어지면는 <xref:System.Windows.Media.Animation.Storyboard>, 시계 모든 속성에 적용 되지 않습니다. 용도 대해 만들어진 클록 해당 자식 클록을 제어 하는 것은 <xref:System.Windows.Media.Animation.DoubleAnimation>합니다.  
  
 데이터 바인딩이나 애니메이션 변경 내용을 반영 하도록 애니메이션에 대 한 해당 시계를 다시 생성 해야 합니다. 시계를 자동으로 생성 되지 않습니다. 변경 내용을 반영 하는 애니메이션을 하려면 해당 스토리 보드를 사용 하 여 다시 적용 한 <xref:System.Windows.Media.Animation.BeginStoryboard> 또는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드. 이러한 방법 중 하나를 사용 하면 애니메이션 다시 시작 합니다. 코드에서 사용할 수는 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 스토리 보드를 이동 하려면 메서드의 이전 위치로 다시 합니다.  
  
 데이터의 예로 바인딩된 애니메이션을 보려면 [키 스플라인 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160011)합니다.                  애니메이션 및 타이밍 시스템 작동 방식에 대 한 자세한 내용은 참조 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)합니다.  
  
<a name="otherWaysToAnimateSection"></a>   
## <a name="other-ways-to-animate"></a>애니메이션을 적용 하는 다른 방법  
 이 개요의 예제에는 스토리 보드를 사용 하 여 애니메이션을 적용 하는 방법을 보여 줍니다. 코드를 사용 하면 여러 가지 방법으로 애니메이션을 적용할 수 있습니다. 자세한 내용은 참조는 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)합니다.  
  
<a name="animation_samples"></a>   
## <a name="animation-samples"></a>애니메이션 샘플  
 다음 샘플 응용 프로그램에 애니메이션 추가 시작할 수 있습니다.  
  
-   [From, To 및 애니메이션 대상 값 샘플](http://go.microsoft.com/fwlink/?LinkID=159988)  
  
     다른 From/To/By 설정이 나와 있습니다.  
  
-   [애니메이션 타이밍 동작 샘플](http://go.microsoft.com/fwlink/?LinkID=159970)  
  
     애니메이션의 타이밍 동작을 제어할 수는 여러 가지 방법을 보여 줍니다. 이 샘플도 보여 줍니다 데이터에 바인딩하는 방법을 애니메이션 대상 값입니다.  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)|타이밍 시스템 사용 하는 방법에 대해 설명는 <xref:System.Windows.Media.Animation.Timeline> 및 <xref:System.Windows.Media.Animation.Clock> 애니메이션을 만들 수 있게 하는 클래스입니다.|  
|[애니메이션 팁과 트릭](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)|성능 같은 애니메이션 문제 해결에 대 한 유용한 팁을 나열 합니다.|  
|[사용자 지정 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)|키 프레임, 애니메이션 클래스 또는 프레임당 콜백을 사용 하 여 애니메이션 시스템을 확장 하는 방법에 설명 합니다.|  
|From/To/By 애니메이션 개요|두 값 사이 전환 하는 애니메이션을 만드는 방법에 설명 합니다.|  
|[키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)|애니메이션 보간 방법을 제어 하는 기능을 포함 한 여러 대상 값을 만드는 방법을 설명 합니다.|  
|[감속/가속 함수](../../../../docs/framework/wpf/graphics-multimedia/easing-functions.md)|반송 같은 실제 결과를 얻으려면 애니메이션에 수학 수식을 적용 하는 방법에 설명 합니다.|  
|[경로 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)|이동 하거나 복잡 한 경로 따라 개체를 회전 하는 방법에 설명 합니다.|  
|[속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)|속성 애니메이션 스토리 보드를 사용 하 여, 로컬 애니메이션, 시계 및 프레임당 애니메이션에 설명 합니다.|  
|[Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)|여러 개의 일정으로 스토리 보드를 사용 하 여 복잡 한 애니메이션을 만드는 방법을 설명 합니다.|  
|[타이밍 동작 개요](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)|설명의 <xref:System.Windows.Media.Animation.Timeline> 유형 및 애니메이션에 사용 되는 속성입니다.|  
|[타이밍 이벤트 개요](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)|사용할 수 있는 이벤트에 설명 된 <xref:System.Windows.Media.Animation.Timeline> 및 <xref:System.Windows.Media.Animation.Clock> 개체와 같은 타임 라인의 지점에서 코드를 실행 하기 위한 시작, 일시 중지, 다시 시작, 건너뛰기, 또는 중지 합니다.|  
|[방법 도움말 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)|응용 프로그램에서 애니메이션 및 타임 라인을 사용 하기 위한 코드 예제가 포함 되어 있습니다.|  
|[Clock 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/clocks-how-to-topics.md)|사용 하기 위한 코드 예제가 <xref:System.Windows.Media.Animation.Clock> 응용 프로그램의 개체입니다.|  
|[키 프레임 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)|응용 프로그램에 키 프레임 애니메이션을 사용 하기 위한 코드 예제가 포함 되어 있습니다.|  
|[경로 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)|경로 애니메이션 응용 프로그램에서 사용 하기 위한 코드 예제가 포함 되어 있습니다.|  
  
<a name="reference"></a>   
## <a name="reference"></a>참조  
 <xref:System.Windows.Media.Animation.Timeline>  
  
 <xref:System.Windows.Media.Animation.Storyboard>  
  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
  
 <xref:System.Windows.Media.Animation.Clock>