---
title: '방법: 이벤트를 사용하여 롤오버 효과 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: d458d87586614093b35fcd73969dea04fe620351
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543012"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a>방법: 이벤트를 사용하여 롤오버 효과 만들기
이 예제에는 마우스 포인터가 요소에서 사용 하는 영역을 들어가고을 요소의 색을 변경 하는 방법을 보여 줍니다.  
  
 이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일 및 코드 숨김 파일입니다.  
  
> [!NOTE]
>  이벤트를 사용 하는 방법을 보여 주는이 예제 이지만이 동일한 효과를 만드는 권장된 방법을 사용 하는 <xref:System.Windows.Trigger> 스타일에서입니다. 자세한 내용은 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] 구성 된 사용자 인터페이스를 만들고 <xref:System.Windows.Controls.Border> 주위는 <xref:System.Windows.Controls.TextBlock>, 연결는 <xref:System.Windows.Input.Mouse.MouseEnter> 및 <xref:System.Windows.UIElement.MouseLeave> 에 이벤트 처리기는 <xref:System.Windows.Controls.Border>합니다.  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 다음 코드 숨김 만듭니다는 <xref:System.Windows.UIElement.MouseEnter> 및 <xref:System.Windows.UIElement.MouseLeave> 이벤트 처리기입니다.  마우스 포인터가 들어갈 때는 <xref:System.Windows.Controls.Border>, 배경의 <xref:System.Windows.Controls.Border> 빨강으로 변경 합니다.  마우스 포인터가 벗어날 때는 <xref:System.Windows.Controls.Border>, 배경의 <xref:System.Windows.Controls.Border> 다시 흰색으로 변경 합니다.  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
