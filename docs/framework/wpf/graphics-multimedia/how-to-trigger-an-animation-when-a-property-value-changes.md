---
title: '방법: 속성 값이 변경될 때 애니메이션 트리거'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: f127f00445a587ee097faa6bed28e124690de10e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a>방법: 속성 값이 변경될 때 애니메이션 트리거
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Trigger> 시작 하는 <xref:System.Windows.Media.Animation.Storyboard> 속성 값이 변경 합니다. 사용할 수는 <xref:System.Windows.Trigger> 내는 <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, 또는 <xref:System.Windows.DataTemplate>합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Trigger> 애니메이션 효과를 줄의 <xref:System.Windows.UIElement.Opacity%2A> 의 <xref:System.Windows.Controls.Button> 때 해당 <xref:System.Windows.UIElement.IsMouseOver%2A> 속성은 `true`합니다.  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 속성에 의해 적용 된 애니메이션이 <xref:System.Windows.Trigger> 개체 보다 더 복잡 한 방식으로 작동 <xref:System.Windows.EventTrigger> 애니메이션이 나 애니메이션 사용 하 여 시작 <xref:System.Windows.Media.Animation.Storyboard> 메서드.  "핸드 오프" 애니메이션이 있는 다른 정의 <xref:System.Windows.Trigger> 개체 하지만로 작성 <xref:System.Windows.EventTrigger> 및 애니메이션 메서드 트리거됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Trigger>  
 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
