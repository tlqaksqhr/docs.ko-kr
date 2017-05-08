---
title: "방법: Storyboard를 사용하여 애니메이션 효과를 적용한 후 속성 설정 | Microsoft Docs"
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
  - "애니메이션, 이후에 속성 값 변경"
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: Storyboard를 사용하여 애니메이션 효과를 적용한 후 속성 설정
경우에 따라서는 애니메이션 효과를 적용한 후에는 속성 값을 변경할 수 없는 것처럼 보일 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard>를 사용하여 <xref:System.Windows.Media.SolidColorBrush>의 색에 애니메이션 효과를 적용합니다.  Storyboard는 단추를 클릭할 때 트리거됩니다.  <xref:System.Windows.Media.Animation.Timeline.Completed> 이벤트는 <xref:System.Windows.Media.Animation.ColorAnimation>이 완료되었을 때 프로그램이 알림을 받을 수 있도록 처리됩니다.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton1Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## 예제  
 <xref:System.Windows.Media.Animation.ColorAnimation>이 완료된 뒤 프로그램은 브러시의 색을 파란색으로 변경하려고 시도합니다.  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 앞의 코드는 아무 작업도 하지 않는 것처럼 보입니다. 브러시는 브러시에 애니메이션 효과를 적용하는 <xref:System.Windows.Media.Animation.ColorAnimation>에서 제공된 값인 노란색으로 유지됩니다.  기본 속성 값\(기준 값\)은 실제로 파란색으로 변경됩니다.  하지만 <xref:System.Windows.Media.Animation.ColorAnimation>이 여전히 기준 값을 재정의하므로 유효 또는 현재 값은 노란색으로 남아 있습니다.  기준 값이 다시 유효 값이 되도록 하려면 애니메이션이 속성에 영향을 주지 않도록 해야 합니다.  Storyboard 애니메이션에서 이렇게 하는 방법에는 세 가지가 있습니다.  
  
-   애니메이션의 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성을 <xref:System.Windows.Media.Animation.FillBehavior>으로 설정합니다.  
  
-   전체 Storyboard를 제거합니다.  
  
-   개별 속성에서 애니메이션을 제거합니다.  
  
## 애니메이션의 FillBehavior 속성을 Stop으로 설정합니다.  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>가 <xref:System.Windows.Media.Animation.FillBehavior>으로 설정된 애니메이션은 활성 기간의 끝에 도달한 후부터는 대상 속성에 영향을 주지 않게 됩니다.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton2Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## 전체 Storyboard 제거  
 <xref:System.Windows.Media.Animation.RemoveStoryboard> 트리거 또는 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=fullName> 메서드를 사용하면 Storyboard 애니메이션이 대상 속성에 영향을 주는 것이 중지됩니다.  이 방법과 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성을 설정하는 방법의 차이는 이 방법의 경우 Storyboard를 언제라도 제거할 수 있지만 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성은 애니메이션이 활성 기간의 끝에 도달했을 때만 영향을 준다는 점입니다.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton3Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## 개별 속성에서 애니메이션 제거  
 애니메이션이 속성을 영향을 주는 것을 중지하는 또 다른 방법은 애니메이션 효과가 적용되는 개체의 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 메서드를 사용하는 방법입니다.  첫 번째 매개 변수로는 애니메이션을 적용할 속성을 지정하고 두 번째 매개 변수로는 `null`을 지정합니다.  
  
 [!code-xml[timingbehaviors_snip#GraphicsMMButton4Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 이 방법은 비 Storyboard 애니메이션에서도 작동합니다.  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>   
 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=fullName>   
 <xref:System.Windows.Media.Animation.RemoveStoryboard>   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)