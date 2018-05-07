---
title: '방법: 이벤트가 발생할 때 요소에 변환 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
ms.openlocfilehash: bd50b369666a1b65226b2b7eb6f3d866ec670bde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a>방법: 이벤트가 발생할 때 요소에 변환 적용
적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.ScaleTransform> 이벤트가 발생 합니다. 여기에 표시된 개념은 다른 유형의 변환을 적용할 때 사용하는 것과 같습니다. 변환의 사용 가능한 형식에 대 한 자세한 내용은 참조는 <xref:System.Windows.Media.Transform> 클래스 또는 [변환 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)합니다.  
  
 다음 두 가지 방법으로 요소에 변환을 적용할 수 있습니다.  
  
-   이렇게 하면 *하지* 레이아웃에 영향을 줄을 사용 하 여 변환을 <xref:System.Windows.UIElement.RenderTransform%2A> 요소의 속성입니다.  
  
-   사용 하 여 변환을 레이아웃을 적용 하려면 않도록 하려는 경우는 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 요소의 속성입니다.  
  
 다음 예제에서는 적용는 <xref:System.Windows.Media.ScaleTransform> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 단추의 속성입니다. 며 단추 위로 마우스를 이동할 때는 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 및 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 의 속성은 <xref:System.Windows.Media.ScaleTransform> 로 설정 `2`, 단추가 더 커집니다. 마우스 포인터를 단추 밖 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 및 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 로 설정 `1`,이 경우 원래 크기로 되돌리려면 단추입니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[ButtonTransform#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
