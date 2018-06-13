---
title: '방법: SolidColorBrush의 색 또는 불투명도에 애니메이션 효과 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 2457bdb794d81e7c482f735cad4ade34564328e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559326"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>방법: SolidColorBrush의 색 또는 불투명도에 애니메이션 효과 적용
애니메이션 효과 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 및 <xref:System.Windows.Media.Brush.Opacity%2A> 의 <xref:System.Windows.Media.SolidColorBrush>합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 세 애니메이션을 사용 하 여 애니메이션 효과를 줄의 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 및 <xref:System.Windows.Media.Brush.Opacity%2A> 의 <xref:System.Windows.Media.SolidColorBrush>합니다.  
  
-   첫 번째 애니메이션은 <xref:System.Windows.Media.Animation.ColorAnimation>, 브러시의 색을 변경 <xref:System.Windows.Media.Colors.Gray%2A> 마우스 사각형 안으로 이동할 때.  
  
-   다음 애니메이션 다른 <xref:System.Windows.Media.Animation.ColorAnimation>, 브러시의 색을 변경 <xref:System.Windows.Media.Colors.Orange%2A> 마우스가 사각형을 벗어날 때.  
  
-   마지막 애니메이션은 <xref:System.Windows.Media.Animation.DoubleAnimation>를 마우스 왼쪽된 단추를 누를 때 브러시의 불투명도 0.0으로 변경 합니다.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 를 다른 종류의 브러시에 애니메이션을 적용 하는 방법을 보여 주는 전체 샘플에 대 한 참조는 [브러시 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)합니다. 애니메이션에 대 한 자세한 내용은 참조는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)합니다.  
  
 이 예제의 코드 버전 다른 애니메이션 예제와 일관성을 위해 사용 하 여는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션을 적용 하는 개체입니다. 그러나 코드에서 단일 애니메이션을 적용할 때 더 간단 하 게 사용 하 여는 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 사용 하는 대신 메서드를 <xref:System.Windows.Media.Animation.Storyboard>합니다. 예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [브러시 샘플](http://go.microsoft.com/fwlink/?LinkID=159973)
