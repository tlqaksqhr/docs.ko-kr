---
title: "방법: 디자이너를 사용하여 ToolStripMenuItems 숨기기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9549fa11b3f019dce3cc77d5f6d1d08a8485f0cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a>방법: 디자이너를 사용하여 ToolStripMenuItems 숨기기
메뉴 항목 숨기기는 응용 프로그램의 사용자 인터페이스 (UI)를 제어 하 고 사용자 명령을 제한 하는 방법입니다. 종종 전체 메뉴에 메뉴 항목을 모두 사용할 수 없는 경우 숨길 합니다. 사용자에 대해 더 적은 방해 요소를 표시합니다. 또한 수 숨기고 메뉴 또는 메뉴 항목을 사용 하지 않도록 설정 대로 하려는 숨기는 것 만으로도 사용자 바로 가기 키를 사용 하 여 메뉴 명령에 액세스 하는 것을 금지 하지 않습니다. 메뉴 항목을 사용 하지 않도록 설정에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 디자이너를 사용 하 여 ToolStripMenuItems 사용 안 함](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a>최상위 메뉴와 해당 하위 메뉴 항목을 숨기려면  
  
1.  최상위 메뉴 항목을 선택 하 고 설정의 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 또는 <xref:System.Windows.Forms.ToolStripItem.Available%2A> 속성을 `false`합니다.  
  
     최상위 메뉴 항목을 숨길 때 해당 메뉴 내의 모든 메뉴 항목 숨겨집니다. 아닌 다른 위치를 클릭 하면는 <xref:System.Windows.Forms.MenuStrip> 설정한 후 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 를 `false`, 전체 최상위 메뉴 항목 및 해당 하위 메뉴 항목 따라서 액션의 실행 시간 효과 표시 폼에서 사라집니다. 디자인 타임에 최상위 메뉴 숨겨진된 항목을 표시 하려면 클릭는 <xref:System.Windows.Forms.MenuStrip> 에 **구성 요소 트레이**에 **문서 개요**, 또는 속성 표의 맨 위에 있는 합니다.  
  
> [!NOTE]
>  전체 메뉴 병합 시나리오에서 여러 문서 MDI (인터페이스) 자식 메뉴를 제외한 거의 숨겨집니다.  
  
### <a name="to-hide-a-submenu-item"></a>하위 메뉴 항목을 숨기려면  
  
1.  하위 메뉴 항목을 선택 하 고 설정의 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 속성을 `false`합니다.  
  
     하위 메뉴 항목을 숨길 때 쉽게 추가 작업을 위해 선택할 수 있도록 디자인 타임에 폼에 표시 되 게 합니다. 런타임 시 실제로 표시지 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [방법: 디자이너를 사용하여 ToolStripMenuItems를 사용하지 않도록 설정](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)
