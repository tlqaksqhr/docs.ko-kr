---
title: "방법: Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "애니메이션, Storyboard 아님(로컬)"
  - "로컬 애니메이션"
  - "Storyboard가 아닌 애니메이션"
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기
이 예제에서는 <xref:System.Windows.Media.Animation.Storyboard>를 사용하지 않고 속성에 애니메이션 효과를 적용하는 한 가지 방법을 보여 줍니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서는 이 기능을 사용할 수 없습니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 속성에 애니메이션 효과를 주는 방법에 대한 자세한 내용은 [Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)를 참조하십시오.  
  
 속성에 로컬 애니메이션을 적용하려면 <xref:System.Windows.UIElement.BeginAnimation%2A> 메서드를 사용합니다.  이 메서드에는 애니메이션 효과를 줄 속성과 해당 속성에 적용할 애니메이션을 지정하는 두 개의 매개 변수 <xref:System.Windows.DependencyProperty>를 사용합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.Button>의 너비와 배경색에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 <xref:System.Windows.Media.Animation> 네임스페이스에는 여러 형식의 속성에 애니메이션 효과를 주기 위한 다양한 애니메이션 클래스가 있습니다.  속성에 애니메이션 효과를 주는 방법에 대한 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  [종속성 속성](GTMT)\(이 예제에 사용되는 속성의 형식\) 및 그 기능에 대한 자세한 내용은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Media.Animation.Storyboard> 개체를 사용하지 않고 애니메이션 효과를 주는 다른 방법도 있습니다. 이에 대한 자세한 내용은 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.AnimationTimeline>   
 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>   
 <xref:System.Windows.Media.Animation>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)