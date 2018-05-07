---
title: '방법: 요소 또는 브러시의 불투명도에 애니메이션 효과 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
ms.openlocfilehash: a45bf0344c10e1214aa5218e25e9bd9a87d5ea60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>방법: 요소 또는 브러시의 불투명도에 애니메이션 효과 적용
페이드 아웃 프레임 워크 요소를 하려면 애니메이션을 적용할 수 해당 <xref:System.Windows.UIElement.Opacity%2A> 속성 또는 있습니다 애니메이션을 적용할 수는 <xref:System.Windows.Media.Brush.Opacity%2A> 속성은 <xref:System.Windows.Media.Brush> (또는 브러시) 칠할 하는 데 사용 합니다. 하면 불투명도 요소에 애니메이션을 적용 하 고 자식 페이드 아웃, 하지만 페이드 요소의 부분에 대 한 좀 더 선택적 될 수 있습니다 요소를 그리는 데 사용 되는 브러시에 애니메이션을 적용 합니다. 예를 들어 단추의 배경을 그리는 데 사용 되는 브러시 불투명도 애니메이션을 적용할 수 있습니다. 이 단추의 배경을 완전히 불투명 한 텍스트를 그대로 유지 하면서 현재 뷰를 페이드 인 / 아웃 하 리라 예상 되었습니다.  
  
> [!NOTE]
>  애니메이션의 <xref:System.Windows.Media.Brush.Opacity%2A> 의 <xref:System.Windows.Media.Brush> 애니메이션 보다 성능상 이점이 <xref:System.Windows.UIElement.Opacity%2A> 요소의 속성입니다.  
  
 다음 예제에서는 두 개의 단추는 페이드 아웃 되도록 애니메이션이 적용 됩니다. 첫 번째의 불투명도 <xref:System.Windows.Controls.Button> 에서 애니메이션 효과가 적용 되어 `1.0` 를 `0.0` 위에 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 5 초입니다. 두 번째 단추는 또한 애니메이션 효과가 적용 되어, 하지만 SolidColorBrush의 불투명도 그리는 데 사용 되는 <xref:System.Windows.Controls.Control.Background%2A> 전체 단추의 불투명도 하지 않고 애니메이션 효과가 적용 됩니다. 예제를 실행 하는 경우 첫 번째 단추 완전히 페이드 인 보기를 두 번째 단추의 배경을 페이드 아웃 합니다. 텍스트와 테두리에 완전히 불투명 한이 유지 됩니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 이 예제에서 코드는 생략 되었습니다. 전체 샘플의 불투명도 애니메이션 효과 적용 하는 방법도 설명는 <xref:System.Windows.Media.Color> 내는 <xref:System.Windows.Media.LinearGradientBrush>합니다.  전체 샘플에 대 한 참조는 [불투명도 요소 예제에 애니메이션 적용](http://go.microsoft.com/fwlink/?LinkID=159968)합니다.
