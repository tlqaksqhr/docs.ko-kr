---
title: '방법: 요소에 표시기 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: fb419ee5a57e81e7e3bc72ae04fd200703b80cd3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552554"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a>방법: 요소에 표시기 바인딩
지정 된 표시기를 프로그래밍 방식으로 바인딩하는 방법을 보여 주는이 예제 <xref:System.Windows.UIElement>합니다.  
  
## <a name="example"></a>예제  
 표시기를 특정 바인딩할 <xref:System.Windows.UIElement>, 다음이 단계를 수행 합니다.  
  
1.  호출 된 `static` 메서드 <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 가져오려는 <xref:System.Windows.Documents.AdornerLayer> 개체에 대 한는 <xref:System.Windows.UIElement> 표시 될 합니다. <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 지정 된 위치에서 시작 되는 시각적 트리를 이동 **UIElement**를 찾으면 첫 번째 표시기 계층을 반환 합니다. (표시기 계층이 없으면 메서드가 null을 반환합니다.)  
  
2.  호출 된 <xref:System.Windows.Documents.AdornerLayer.Add%2A> 대상에 표시기를 바인딩할 메서드를 **UIElement**합니다.  
  
 다음 예에서는 바인딩합니다 (위에 표시 된)를 SimpleCircleAdorner는 <xref:System.Windows.Controls.TextBox> 라는 *myTextBox*합니다.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 사용하여 표시기를 다른 요소에 바인딩하는 것은 현재 지원되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [표시기 개요](../../../../docs/framework/wpf/controls/adorners-overview.md)
