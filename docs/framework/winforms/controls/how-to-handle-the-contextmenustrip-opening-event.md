---
title: '방법: ContextMenuStrip Opening 이벤트 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
ms.openlocfilehash: c5af03f4726063754f81ec9226b4b161599b4121
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531864"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a>방법: ContextMenuStrip Opening 이벤트 처리
동작을 사용자 지정할 수 있습니다 프로그램 <xref:System.Windows.Forms.ContextMenuStrip> 처리 하 여 컨트롤의 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 이벤트입니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 처리 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.ToolStripDropDown.Opening> 이벤트입니다. 이벤트 처리기에 동적으로 항목에 추가 <xref:System.Windows.Forms.ContextMenuStrip> 제어 합니다. 전체 코드 예제를 보려면 [하는 방법: ToolStrip 추가 동적](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md)합니다.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 설정의 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> 속성을 `true` 메뉴 열리지 않도록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>  
 <xref:System.Windows.Forms.ToolStripDropDown>  
 [ToolStrip 컨트롤](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
