---
title: "방법: 디자이너를 사용하여 ToolStripMenuItems를 사용하지 않도록 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4958f315ff0415c3964d22dffff2553c0901eb91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a>방법: 디자이너를 사용하여 ToolStripMenuItems를 사용하지 않도록 설정
제한 하거나 사용자의 동작에 대 한 응답으로 메뉴 항목을 설정 하거나 해제 하 여 사용자가 수행 하는 명령을 넓힐 수 있습니다. 메뉴 항목은 기본적으로 활성화 만들어질 때 통해 조정할 수 있습니다는 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성입니다. 디자인 타임에이 속성을 조작할 수 있습니다는 **속성** 창 또는 코드에서 설정 하 여 프로그래밍 방식으로 합니다. 자세한 내용은 참조 [하는 방법: ToolStripMenuItems 사용 안 함](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-disable-a-menu-item-at-design-time"></a>디자인 타임에 메뉴 항목을 사용 하지 않도록 설정 하려면  
  
1.  폼에서 선택한 메뉴 항목을 사용 하 여 설정할는 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 `false`합니다.  
  
    > [!TIP]
    >  메뉴에 포함 된 모든 메뉴 항목을 해제 메뉴의 첫 번째 또는 최상위 메뉴 항목을 사용 하지 않도록 설정 합니다. 마찬가지로, 하위 메뉴 항목이 해제 하위 메뉴 항목이 포함 된 메뉴 항목을 사용 하지 않도록 설정 합니다. 메뉴의 모든 명령을 사용자에 게 사용할 수 없을 경우이 인해 사용자 인터페이스를 명확 하는 대로 숨기고 전체 메뉴를 사용 하지 않도록 설정 하는 바람직한 프로그래밍 관행을 간주 됩니다. 숨기기와 숨기는 것 만으로도 바로 가기 키를 통해 메뉴 명령에 액세스 하지 않는 메뉴를 사용 하지 않도록 설정 해야 합니다. 설정의 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 에 최상위 메뉴 항목의 `false` 전체 메뉴를 숨기 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [방법: ToolStripMenuItems 숨기기](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
