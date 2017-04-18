---
title: "방법: Storyboard를 사용하여 속성에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "애니메이션, 스토리보드"
  - "스토리보드, 애니메이션"
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Storyboard를 사용하여 속성에 애니메이션 효과 주기
이 예제에서는 <xref:System.Windows.Media.Animation.Storyboard>를 사용하여 속성에 애니메이션 효과를 주는 방법을 보여 줍니다.  <xref:System.Windows.Media.Animation.Storyboard>를 사용하여 속성에 애니메이션 효과를 주려면 애니메이션 효과를 줄 각 속성에 대해 애니메이션을 만들고 애니메이션이 포함될 <xref:System.Windows.Media.Animation.Storyboard>도 만듭니다.  
  
 사용할 애니메이션의 형식은 속성의 형식에 따라 결정됩니다.  예를 들어 <xref:System.Double> 값을 사용하는 속성에 애니메이션 효과를 주려면 <xref:System.Windows.Media.Animation.DoubleAnimation>을 사용합니다.  <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> [연결된 속성](GTMT)을 사용하여 애니메이션이 적용되는 개체와 속성을 지정합니다.  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 스토리보드를 시작하려면 <xref:System.Windows.Media.Animation.BeginStoryboard> 동작과 <xref:System.Windows.EventTrigger>를 사용합니다.  <xref:System.Windows.EventTrigger>는 <xref:System.Windows.EventTrigger.RoutedEvent%2A> 속성으로 지정된 이벤트가 발생하면 <xref:System.Windows.Media.Animation.BeginStoryboard> 동작을 시작합니다.  <xref:System.Windows.Media.Animation.BeginStoryboard> 동작은 <xref:System.Windows.Media.Animation.Storyboard>를 시작합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard> 개체를 사용하여 두 개의 <xref:System.Windows.Controls.Button> 컨트롤에 애니메이션 효과를 줍니다.  첫 번째 단추의 크기를 변경하기 위해 <xref:System.Windows.FrameworkElement.Width%2A>에 애니메이션이 적용됩니다.  두 번째 단추의 색을 변경하기 위해 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 속성을 사용하여 애니메이션 효과가 적용되는 단추의 <xref:System.Windows.Controls.Control.Background%2A>를 설정합니다.  
  
## 예제  
 [!code-xml[AnimatePropertyStoryboards#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
>  <xref:System.Windows.Controls.Control> 또는 <xref:System.Windows.Controls.Panel>과 같은 <xref:System.Windows.FrameworkElement> 개체와 <xref:System.Windows.Media.Brush> 또는 <xref:System.Windows.Media.Transform>과 같은 <xref:System.Windows.Freezable> 개체가 모두 애니메이션의 대상이 될 수 있지만 프레임워크 요소만 <xref:System.Windows.FrameworkElement.Name%2A> 속성을 가집니다.  Freezable에 이름을 할당하여 애니메이션 대상이 될 수 있도록 하려면 이전 예제에서처럼 [x:Name 지시문](../../../../docs/framework/xaml-services/x-name-directive.md)을 사용합니다.  
  
 코드를 사용하는 경우에는 <xref:System.Windows.FrameworkElement>에 대한 <xref:System.Windows.NameScope>를 만들고 애니메이션 효과를 줄 개체의 이름을 이 <xref:System.Windows.FrameworkElement>에 등록합니다.  코드에서 애니메이션을 시작하려면 <xref:System.Windows.Media.Animation.BeginStoryboard> 동작을 <xref:System.Windows.EventTrigger>와 함께 사용합니다.  필요하다면 이벤트 처리기와 <xref:System.Windows.Media.Animation.Storyboard>의 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 사용할 수 있습니다.  다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 애니메이션 및 Storyboard에 대한 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
 코드를 사용하는 경우 속성에 애니메이션 효과를 주기 위해 <xref:System.Windows.Media.Animation.Storyboard> 개체 외에도 다른 방법을 사용할 수 있습니다.  자세한 내용 및 예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md) 및 [AnimationClock을 사용하여 속성에 애니메이션 효과 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md)을 참조하십시오.