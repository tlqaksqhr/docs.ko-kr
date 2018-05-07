---
title: '방법: 그라데이션 중지점의 위치 또는 색에 애니메이션 효과 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
ms.openlocfilehash: 2eb528127c8aa66976788ec1f4e5362ca3a1ef26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a>방법: 그라데이션 중지점의 위치 또는 색에 애니메이션 효과 적용
애니메이션 효과 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.GradientStop.Color%2A> 및 <xref:System.Windows.Media.GradientStop.Offset%2A> 의 <xref:System.Windows.Media.GradientStop> 개체입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 세 개의 그라데이션 중지점 내 애니메이션 효과 적용 한 <xref:System.Windows.Media.LinearGradientBrush>합니다. 이 예제에서는 서로 다른 그라데이션 중지점 애니메이션 효과 적용 하며 각 세 애니메이션을 사용 합니다.  
  
-   첫 번째 애니메이션은 <xref:System.Windows.Media.Animation.DoubleAnimation>, 첫 번째 그라데이션 중지점의 애니메이션 효과 적용 <xref:System.Windows.Media.GradientStop.Offset%2A> 0.0에서 1.0 변환한 다음 다시 0.0으로 합니다. 결과적으로, 첫 번째 사각형의 왼쪽에서 오른쪽으로 왼쪽에서 그라데이션 shifts에서 색을 왼쪽으로 다시 합니다.  
  
-   두 번째 애니메이션은 <xref:System.Windows.Media.Animation.ColorAnimation>, 두 번째 그라데이션 중지점의 애니메이션 효과 적용 <xref:System.Windows.Media.GradientStop.Color%2A> 에서 <xref:System.Windows.Media.Colors.Purple%2A> 를 <xref:System.Windows.Media.Colors.Yellow%2A> 다시 <xref:System.Windows.Media.Colors.Purple%2A>합니다. 결과적으로, 노란색, 보라색 다시로 자주색에서 그라데이션의 중간 색을 변경합니다.  
  
-   세 번째 애니메이션 다른 <xref:System.Windows.Media.Animation.ColorAnimation>, 세 번째 그라데이션 중지점의 불투명도 애니메이션 효과 적용 <xref:System.Windows.Media.GradientStop.Color%2A> -1로 변환한 다음 다시 합니다. 결과적으로, 세 번째 그라데이션 색 희미해 고 나면 불투명 다시 합니다.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 이 예제에서는 한 <xref:System.Windows.Media.LinearGradientBrush>는 과정은 동일 하에 애니메이션 효과를 <xref:System.Windows.Media.GradientStop> 개체는 <xref:System.Windows.Media.RadialGradientBrush>합니다.  
  
 추가 예제에 대 한 참조는 [브러시 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.GradientStop>  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
