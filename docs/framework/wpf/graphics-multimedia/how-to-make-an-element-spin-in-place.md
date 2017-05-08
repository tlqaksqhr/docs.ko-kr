---
title: "방법: 현재 위치에서 요소가 회전하도록 만들기 | Microsoft Docs"
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
  - "클래스, DoubleAnimation"
  - "클래스, RotateTransform"
  - "DoubleAnimation 클래스"
  - "그래픽, 요소 회전"
  - "RotateTransform 클래스"
  - "요소 회전"
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 현재 위치에서 요소가 회전하도록 만들기
이 예제에서는 <xref:System.Windows.Media.RotateTransform> 및 <xref:System.Windows.Media.Animation.DoubleAnimation>을 사용하여 요소를 회전하는 방법을 보여 줍니다.  
  
 다음 예제에서는 요소의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 <xref:System.Windows.Media.RotateTransform>을 적용합니다.  이 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>을 사용하여 <xref:System.Windows.Media.RotateTransform>의 <xref:System.Windows.Media.RotateTransform.Angle%2A>에 애니메이션 효과를 줍니다.  이 예제에서는 현재 위치에서 요소를 회전하기 위해 요소의 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성을 \(0.5, 0.5\) 지점으로 설정합니다.  
  
## 예제  
 [!code-xml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 추가 변환 예제를 비롯하여 전체 샘플을 보려면 [2\-D Transforms 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)을 참조하십시오.  
  
## 참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)