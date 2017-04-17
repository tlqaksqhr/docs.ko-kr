---
title: "방법: FrameworkElement의 크기에 애니메이션 효과 적용 | Microsoft Docs"
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
  - "애니메이션, FrameworkElement 크기"
  - "FrameworkElement, 크기에 애니메이션 적용"
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: FrameworkElement의 크기에 애니메이션 효과 적용
<xref:System.Windows.FrameworkElement>의 크기에 애니메이션 효과를 적용하려면 해당 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성에 애니메이션 효과를 적용하거나 애니메이션이 적용된 <xref:System.Windows.Media.ScaleTransform>을 사용합니다.  
  
 다음 예제에서는 이와 같은 두 가지 방법을 사용하여 두 단추의 크기에 애니메이션 효과를 적용합니다.  첫 번째 단추는 해당 <xref:System.Windows.FrameworkElement.Width%2A> 속성에 애니메이션 효과를 적용하여 단추 크기를 조정하고, 두 번째 단추는 해당 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 적용된 <xref:System.Windows.Media.ScaleTransform>에 애니메이션 효과를 적용하여 단추 크기를 조정합니다.  각 단추에는 텍스트가 포함되어 있습니다.  처음에는 두 단추의 텍스트가 똑같이 나타나지만 단추 크기를 조정한 후에는 두 번째 단추의 텍스트가 왜곡되어 나타납니다.  
  
## 예제  
 [!code-xml[transformanimations_snip#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 요소를 변환하면 요소와 요소의 내용이 모두 변환됩니다.  첫 번째 단추와 같이 요소 크기를 직접 변경하는 경우 요소 내용의 크기 및 위치가 부모 요소의 크기에 종속되는 경우가 아니면 요소 내용은 크기가 조정되지 않습니다.  
  
 애니메이션이 적용된 변환을 요소의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 적용하여 요소 크기에 애니메이션 효과를 적용하는 경우 <xref:System.Windows.UIElement.RenderTransform%2A> 속성이 레이아웃 과정을 트리거하지 않으므로 요소의 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A>에 직접 애니메이션 효과를 적용할 때보다 성능이 향상됩니다.  
  
 속성에 애니메이션 효과를 적용하는 방법에 대한 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  변환에 대한 자세한 내용은 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)를 참조하십시오.