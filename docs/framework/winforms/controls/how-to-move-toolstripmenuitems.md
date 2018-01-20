---
title: "방법: ToolStripMenuItems 이동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ffef860118ba20508bba037910d85866055c898
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-move-toolstripmenuitems"></a>방법: ToolStripMenuItems 이동
디자인 타임에 이동할 수 있습니다 최상위 메뉴 전체와 해당 메뉴 항목을 다른 위치로 <xref:System.Windows.Forms.MenuStrip>합니다. 최상위 메뉴 간에 개별 메뉴 항목을 이동 하거나 메뉴 내에서 메뉴 항목의 위치를 변경할 수도 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a>최상위 메뉴와 해당 메뉴 항목을 다른 최상위 위치로 이동 하려면  
  
1.  클릭 하 고 이동 하려는 메뉴에서 마우스 왼쪽된 단추를 누른 채 합니다.  
  
2.  원하는 새 위치 앞에 있는 최상위 메뉴에 삽입 포인터를 끌어서 마우스 왼쪽된 단추를 놓습니다.  
  
     선택한 메뉴 삽입 지점의 오른쪽으로 이동 합니다.  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a>드롭다운 위치에 최상위 메뉴와 해당 메뉴 항목을 이동 하려면  
  
1.  이동 하 고 CTRL + x 또는 메뉴를 마우스 오른쪽 단추로 클릭 하 고 선택 하려는 메뉴를 마우스 왼쪽 단추로 클릭 **잘라내기** 바로 가기 메뉴에서.  
  
2.  대상 최상위 메뉴에서 원하는 새 위치 위에 있는 메뉴 항목을 마우스 왼쪽 단추로 클릭 하 고 CTRL + V를 또는 원하는 새 위치 위에 있는 메뉴 항목을 마우스 오른쪽 단추로 클릭 하 고 선택 **붙여넣기** 바로 가기 메뉴에서.  
  
     잘라낸 메뉴는 선택한 메뉴 항목 뒤에 삽입 됩니다.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a>항목 컬렉션 편집기를 사용 하 여 메뉴 내에서 메뉴 항목을 이동 하려면  
  
1.  이동 하려는 메뉴 항목을 포함 하는 메뉴를 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  바로 가기 메뉴에서 선택 **편집 DropDownItems**합니다.  
  
3.  에 **항목 컬렉션 편집기**를 이동 하려는 메뉴 항목을 마우스 왼쪽 단추로 클릭 합니다.  
  
4.  메뉴 내의 메뉴 항목을 이동 하려면 위쪽 및 아래쪽 화살표 키를 클릭 합니다.  
  
5.  **확인**을 클릭합니다.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a>키보드를 사용 하 여 메뉴 내에서 메뉴 항목을 이동 하려면  
  
1.  키를 누른 ALT 키를 합니다.  
  
2.  이동 하려는 메뉴 항목에 마우스 왼쪽된 단추를 클릭 하 여.  
  
3.  메뉴 항목을 새 위치로 끌어서 마우스 왼쪽된 단추를 놓습니다.  
  
### <a name="to-move-a-menu-item-to-another-menu"></a>다른 메뉴에 메뉴 항목을 이동 하려면  
  
1.  메뉴 항목을 이동 하 고 CTRL + x 또는 메뉴 항목을 마우스 오른쪽 단추로 클릭 하 고 선택 하려면 마우스 왼쪽 단추로 클릭 **잘라내기** 바로 가기 메뉴에서.  
  
2.  잘라낸 메뉴 항목이 포함 된 메뉴를 클릭 합니다.  
  
3.  원하는 새 위치 앞에 있는 메뉴 항목을 마우스 왼쪽 단추로 클릭 하 고 CTRL + V를 누르거나 선택한 원하는 새 위치 앞에 있는 메뉴 항목을 마우스 오른쪽 단추로 클릭 **붙여넣기** 바로 가기 메뉴에서.  
  
     잘라낸 메뉴 항목이 선택된 된 메뉴 항목 뒤에 삽입 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
