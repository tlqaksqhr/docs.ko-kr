---
title: '방법: 패널의 자식 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 4babbf1df57f340a3f6be218f213ad1c868ec9f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550221"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a>방법: 패널의 자식 표시
프로그래밍 방식으로 지정된 된 자식에 표시기를 바인딩하는 방법을 보여 주는이 예제 <xref:System.Windows.Controls.Panel>합니다.  
  
## <a name="example"></a>예제  
 표시기의 자식 항목에 바인딩하는 <xref:System.Windows.Controls.Panel>, 다음이 단계를 수행 합니다.  
  
1.  선언 <xref:System.Windows.Documents.AdornerLayer> 개체와 호출은 `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> 메서드 표시 수의 자식 요소에 대 한 표시기 계층을 찾으려고 합니다.  
  
2.  부모 요소와 호출의 자식을 열거는 <xref:System.Windows.Documents.AdornerLayer.Add%2A> 표시기 각 자식 요소를 바인딩하는 메서드.  
  
 다음 예에서는 바인딩합니다 (위에 표시 된)의 자식에 SimpleCircleAdorner는 <xref:System.Windows.Controls.StackPanel> 라는 *myStackPanel*합니다.  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 사용하여 표시기를 다른 요소에 바인딩하는 것은 현재 지원되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [표시기 개요](../../../../docs/framework/wpf/controls/adorners-overview.md)
