---
title: "방법: TextBox에 사용자 지정 컨텍스트 메뉴 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [WPF], custom
- menus [WPF], custom
- custom context menus [WPF]
- TextBox control [WPF], custom content menus
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4552031a08680af2f4d41702d2f76ed0c44af21b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a>방법: TextBox에 사용자 지정 컨텍스트 메뉴 사용
정의 대 한 간단한 사용자 지정 컨텍스트 메뉴를 구현 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TextBox>합니다.  
  
## <a name="example"></a>예  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 정의 하는 예제는 <xref:System.Windows.Controls.TextBox> 사용자 지정 상황에 맞는 메뉴를 포함 하는 컨트롤입니다.  
  
 상황에 맞는 메뉴를 사용 하 여 정의 되는 <xref:System.Windows.Controls.ContextMenu> 요소입니다.  상황에 맞는 메뉴 자체 구성 된 일련의 <xref:System.Windows.Controls.MenuItem> 요소 및 <xref:System.Windows.Controls.Separator> 요소입니다.  각 <xref:System.Windows.Controls.MenuItem> 요소; 상황에 맞는 메뉴에서 명령을 정의 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 메뉴 명령에 대 한 표시 텍스트를 정의 하는 특성 및 <xref:System.Windows.Controls.MenuItem.Click> 특성 각 메뉴 항목에 대 한 처리기 메서드를 지정 합니다.  <xref:System.Windows.Controls.Separator> 요소 분리 하면 줄 이전 및 이후의 메뉴 항목 간의 렌더링을 수행 하면 됩니다.  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a>예  
 다음 예제에서는 위의 상황에 맞는 메뉴 정의 대 한 구현 코드 뿐 아니라 있으며 특정 상황에 맞는 메뉴를 사용 하지 않도록 설정 하는 코드를 보여 줍니다.  <xref:System.Windows.Controls.ContextMenu.Opened> 이벤트는 동적으로 사용 되거나의 현재 상태에 따라 특정 명령을 사용 하지 않도록 설정 하는 데 사용 된 <xref:System.Windows.Controls.TextBox>합니다.  
  
 사용 하 여 복원 기본 상황에 맞는 메뉴는 <xref:System.Windows.DependencyObject.ClearValue%2A> 의 값을 지울 메서드는 <xref:System.Windows.FrameworkElement.ContextMenu%2A> 속성입니다.  상황에 맞는 메뉴를 모두 해제 하려면 설정는 <xref:System.Windows.FrameworkElement.ContextMenu%2A> 속성을 null 참조 (`Nothing` Visual basic에서).  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a>참고 항목  
 [상황에 맞는 메뉴로 맞춤법 검사 사용](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)  
 [TextBox 개요](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
