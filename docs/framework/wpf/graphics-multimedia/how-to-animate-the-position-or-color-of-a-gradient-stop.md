---
title: "방법: 그라데이션 중지점의 위치 또는 색에 애니메이션 효과 적용 | Microsoft Docs"
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
  - "애니메이션, GradientStop 개체의 색"
  - "애니메이션, GradientStop 개체의 위치"
  - "색, 애니메이션 적용"
  - "GradientStop 개체, 색에 애니메이션 적용"
  - "GradientStop 개체, 위치에 애니메이션 적용"
  - "위치, 애니메이션 적용"
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 그라데이션 중지점의 위치 또는 색에 애니메이션 효과 적용
이 예제에서는 <xref:System.Windows.Media.GradientStop> 개체의 <xref:System.Windows.Media.GradientStop.Color%2A> 및 <xref:System.Windows.Media.GradientStop.Offset%2A>에 애니메이션 효과를 적용하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.LinearGradientBrush> 내에 있는 세 개의 그라데이션 중지점에 애니메이션 효과를 적용합니다.  이 예제에서 사용되는 세 개의 애니메이션은 각각 서로 다른 그라데이션 중지점에 애니메이션 효과를 적용합니다.  
  
-   첫 번째 애니메이션 <xref:System.Windows.Media.Animation.DoubleAnimation>은 첫 번째 그라데이션 중지점의 <xref:System.Windows.Media.GradientStop.Offset%2A>이 0.0에서 1.0으로 이동했다 다시 0.0으로 이동하는 애니메이션 효과를 적용합니다.  그러면 그라데이션의 첫 번째 색이 사각형의 왼쪽에서 오른쪽으로 전환되었다 다시 왼쪽으로 전환됩니다.  
  
-   두 번째 애니메이션 <xref:System.Windows.Media.Animation.ColorAnimation>은 두 번째 그라데이션 중지점의 <xref:System.Windows.Media.GradientStop.Color%2A>가 <xref:System.Windows.Media.Colors.Purple%2A>에서 <xref:System.Windows.Media.Colors.Yellow%2A>로 전환되었다가 다시 <xref:System.Windows.Media.Colors.Purple%2A>로 전환되는 애니메이션 효과를 적용합니다.  그러면 그라데이션의 중간 색이 자주색에서 노란색으로 변했다 다시 자주색으로 변합니다.  
  
-   세 번째 애니메이션인 다른 <xref:System.Windows.Media.Animation.ColorAnimation>은 세 번째 그라데이션 중지점의 <xref:System.Windows.Media.GradientStop.Color%2A> 불투명도가 \-1로 변했다가 다시 원상태로 돌아오는 애니메이션 효과를 적용합니다.  그러면 그라데이션의 세 번째 색이 흐려졌다가 다시 불투명해집니다.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 이 예제에서는 <xref:System.Windows.Media.LinearGradientBrush>를 사용하지만 프로세스는 <xref:System.Windows.Media.RadialGradientBrush> 안에서 <xref:System.Windows.Media.GradientStop> 개체에 애니메이션을 적용할 때와 같습니다.  
  
 다른 예제를 보려면 [Brushes 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.GradientStop>   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)