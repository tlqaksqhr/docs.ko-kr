---
title: "방법: 속성 값이 변경될 때 애니메이션 트리거 | Microsoft Docs"
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
  - "애니메이션, 속성 값이 변경될 때 시작"
  - "스토리보드, 속성 값이 변경될 때 시작"
  - "애니메이션 트리거"
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 속성 값이 변경될 때 애니메이션 트리거
이 예제에서는 속성 값이 변경될 때 <xref:System.Windows.Trigger>를 사용하여 <xref:System.Windows.Media.Animation.Storyboard>를 시작하는 방법을 보여 줍니다.  <xref:System.Windows.Trigger>는 <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate> 또는 <xref:System.Windows.DataTemplate> 내에서 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Trigger>를 사용하여 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.UIElement.IsMouseOver%2A> 속성이 `true`가 될 때 해당 <xref:System.Windows.UIElement.Opacity%2A>에 애니메이션 효과를 적용합니다.  
  
 [!code-xml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 속성 <xref:System.Windows.Trigger> 개체에 의해 적용된 애니메이션은 <xref:System.Windows.EventTrigger> 애니메이션 또는 <xref:System.Windows.Media.Animation.Storyboard> 메서드를 사용하여 시작된 애니메이션보다 복잡한 방식으로 작동합니다.  이러한 애니메이션은 다른 <xref:System.Windows.Trigger> 개체에 의해 정의된 애니메이션과 "핸드오프"하지만 <xref:System.Windows.EventTrigger> 및 메서드에서 트리거한 애니메이션으로 구성됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Trigger>   
 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)