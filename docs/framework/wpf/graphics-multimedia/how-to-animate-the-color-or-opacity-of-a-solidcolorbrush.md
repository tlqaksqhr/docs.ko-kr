---
title: "방법: SolidColorBrush의 색 또는 불투명도에 애니메이션 효과 적용 | Microsoft Docs"
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
  - "애니메이션, SolidColorBrush의 색"
  - "애니메이션, SolidColorBrush의 불투명도"
  - "색, 애니메이션 적용"
  - "불투명도, 애니메이션 적용"
  - "SolidColorBrush, 색에 애니메이션 적용"
  - "SolidColorBrush, 불투명도에 애니메이션 적용"
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: SolidColorBrush의 색 또는 불투명도에 애니메이션 효과 적용
이 예제에서는 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 및 <xref:System.Windows.Media.Brush.Opacity%2A>에 애니메이션 효과를 적용하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 세 가지 애니메이션을 사용하여 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 및 <xref:System.Windows.Media.Brush.Opacity%2A>에 애니메이션 효과를 적용합니다.  
  
-   첫 번째 애니메이션인 <xref:System.Windows.Media.Animation.ColorAnimation>은 마우스가 사각형 안으로 이동할 때 브러시의 색을 <xref:System.Windows.Media.Colors.Gray%2A>로 변경합니다.  
  
-   다음 애니메이션에 해당하는 또 다른 <xref:System.Windows.Media.Animation.ColorAnimation>은 마우스가 사각형에서 벗어날 때 브러시의 색을 <xref:System.Windows.Media.Colors.Orange%2A>로 변경합니다.  
  
-   마지막 애니메이션인 <xref:System.Windows.Media.Animation.DoubleAnimation>은 마우스 왼쪽 단추를 누를 때 브러시의 불투명도를 0.0으로 변경합니다.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 다양한 종류의 브러시에 애니메이션 효과를 적용하는 방법을 보여 주는 전체 샘플을 보려면 [Brushes 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)을 참조하십시오.  애니메이션에 대한 자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
 다른 애니메이션 예제와의 일관성을 위해 이 예제의 코드 버전에서는 <xref:System.Windows.Media.Animation.Storyboard> 개체를 사용하여 애니메이션을 적용합니다.  하지만 코드에 단일 애니메이션을 적용하는 경우 <xref:System.Windows.Media.Animation.Storyboard>를 사용하는 대신 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 사용하면 더 간편합니다.  예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)을 참조하십시오.  
  
## 참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Brushes 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)