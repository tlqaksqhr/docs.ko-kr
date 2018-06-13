---
title: '방법: Storyboard를 사용하여 속성에 애니메이션 효과 주기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: 7e67fb07a05d474999515a678fd72ac6b96953c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561074"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>방법: Storyboard를 사용하여 속성에 애니메이션 효과 주기
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Storyboard> 속성 애니메이션 효과를 합니다. 속성을 사용 하 여 애니메이션 효과를 줄는 <xref:System.Windows.Media.Animation.Storyboard>, 애니메이션 효과 적용 하 고 만들 수도 하려는 각 속성에 대 한 애니메이션을 만들는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션을 포함 하도록 합니다.  
  
 속성 형식에 따라 사용할 애니메이션 형식이 결정됩니다. 예를 들어, 사용 하는 속성에 애니메이션 효과를 주는 <xref:System.Double> 값을 사용 하 여 한 <xref:System.Windows.Media.Animation.DoubleAnimation>합니다. <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> 연결 된 속성 개체 및 애니메이션이 적용 되는 속성을 지정 합니다.  
  
 스토리 보드를 시작 하려면 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 사용 하 여 한 <xref:System.Windows.Media.Animation.BeginStoryboard> 동작 및 <xref:System.Windows.EventTrigger>합니다. <xref:System.Windows.EventTrigger> 시작 되는 <xref:System.Windows.Media.Animation.BeginStoryboard> 이벤트가 하 되 작업으로 지정 된 해당 <xref:System.Windows.EventTrigger.RoutedEvent%2A> 속성이 발생 합니다. <xref:System.Windows.Media.Animation.BeginStoryboard> 동작이 시작 되는 <xref:System.Windows.Media.Animation.Storyboard>합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard> 두 애니메이션 효과를 줄 개체 <xref:System.Windows.Controls.Button> 컨트롤입니다. 첫 번째 단추의 크기를 변경 하기 위해 해당 <xref:System.Windows.FrameworkElement.Width%2A> 애니메이션 효과가 적용 됩니다. 두 번째 단추의 색을 변경 하기 위해는 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 의 속성에서 <xref:System.Windows.Media.SolidColorBrush> 설정 하는 데 사용 되는 <xref:System.Windows.Controls.Control.Background%2A> 단추에 애니메이션 효과 적용 합니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[AnimatePropertyStoryboards#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
>  애니메이션 모두 대상 수 있지만 <xref:System.Windows.FrameworkElement> 와 같은 개체는 <xref:System.Windows.Controls.Control> 또는 <xref:System.Windows.Controls.Panel>, 및 <xref:System.Windows.Freezable> 와 같은 개체는 <xref:System.Windows.Media.Brush> 또는 <xref:System.Windows.Media.Transform>, 프레임 워크 요소에만 사용할는 <xref:System.Windows.FrameworkElement.Name%2A> 속성입니다. 애니메이션의 대상으로 지정될 수 있게 freezable에 이름을 할당하려면 이전 예제와 같이 [x:Name 지시문](../../../../docs/framework/xaml-services/x-name-directive.md)을 사용합니다.  
  
 코드를 사용 하는 경우 만들어야 합니다는 <xref:System.Windows.NameScope> 에 대 한는 <xref:System.Windows.FrameworkElement> 에 애니메이션 효과를 줄 개체의 이름을 등록 하 고 <xref:System.Windows.FrameworkElement>합니다. 코드에서 애니메이션을 시작 하려면 사용 하 여 한 <xref:System.Windows.Media.Animation.BeginStoryboard> 동작과 <xref:System.Windows.EventTrigger>합니다. 필요에 따라 이벤트 처리기를 사용할 수 있습니다 및 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 방식의 <xref:System.Windows.Media.Animation.Storyboard>합니다. 다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 애니메이션 및 Storyboard에 대한 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하세요.  
  
 사용 하도록 제한 없는 코드를 사용 하는 경우 <xref:System.Windows.Media.Animation.Storyboard> 속성에 애니메이션을 적용 하기 위해 개체입니다. 자세한 내용 및 예제에 대해서는 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md) 및 [AnimationClock을 사용하여 속성에 애니메이션 효과 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md)을 참조하세요.
