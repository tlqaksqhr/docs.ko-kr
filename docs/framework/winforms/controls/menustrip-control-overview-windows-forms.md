---
title: MenuStrip 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: b09d653210c72a38bbc4dc0858ae2553ad9cbeef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="menustrip-control-overview-windows-forms"></a>MenuStrip 컨트롤 개요(Windows Forms)
메뉴는 상황도 별로 그룹화 되어 있는 명령을 포함 하 여 사용자에 게 기능을 노출 합니다.  
  
 <xref:System.Windows.Forms.MenuStrip> 컨트롤이이 버전의 Visual Studio 및.NET Framework의 새로운 기능입니다. 컨트롤을 예: Microsoft Office에서 메뉴를 쉽게 만들 수 있습니다.  
  
 <xref:System.Windows.Forms.MenuStrip> 다중 문서 인터페이스 (MDI)와 메뉴 병합, 도구 설명 및 오버플로 컨트롤을 지원 합니다. 선택 키, 바로 가기 키, 확인 표시, 이미지 및 구분선을 추가 하 여 유용성 및 메뉴의 가독성을 향상 시킬 수 있습니다.  
  
 그러나 <xref:System.Windows.Forms.MenuStrip> 대체 하 고 여기에 새로운 기능이 추가 된 <xref:System.Windows.Forms.MainMenu> 컨트롤는 <xref:System.Windows.Forms.MainMenu> 컨트롤을 선택 하는 경우 이전 버전과 호환성 및 이후 사용에 대 한 유지 합니다.  
  
## <a name="ways-to-use-the-menustrip-control"></a>MenuStrip 컨트롤을 사용 하는 방법  
 사용 하 여는 <xref:System.Windows.Forms.MenuStrip> 를 제어 합니다.  
  
-   지 원하는 일반적인된 메뉴가 등의 고급 사용자 인터페이스 및 레이아웃 기능 텍스트 및 이미지 정렬 및 정렬, 끌어서 놓기 작업, MDI, 오버플로 및 메뉴 명령에 액세스 하기 위한 대체 모드, 쉽게 사용자 지정을 만듭니다.  
  
-   일반적인 모양 및 동작의 운영 체제를 지원 합니다.  
  
-   다른 컨트롤에 대 한 이벤트를 처리 하는 동일한 방식으로, 모든 컨테이너 및 포함 된 항목에는 일관성 있게 이벤트를 처리 합니다.  
  
 다음 표에서 몇 가지 특히 중요 한 속성을 <xref:System.Windows.Forms.MenuStrip> 및 연결 된 클래스입니다.  
  
|속성|설명|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|가져오거나는 <xref:System.Windows.Forms.ToolStripMenuItem> MDI 자식 폼의 목록을 표시 하는 데 사용 되는 합니다.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|자식 메뉴를 MDI 응용 프로그램의 부모 메뉴와 병합 하는 방법을 가져오거나 설정 합니다.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|MDI 응용 프로그램에서 메뉴 내에서 병합된 된 항목의 위치를 가져오거나 설정 합니다.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|폼이 MDI 자식 폼의 컨테이너 인지를 나타내는 값을 가져오거나 설정 합니다.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|에 대 한 도구 설명에 표시 되는지 여부를 나타내는 값을 가져오거나 설정 합니다.는 <xref:System.Windows.Forms.MenuStrip>합니다.|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<xref:System.Windows.Forms.MenuStrip>에서 오버플로 기능을 지원하는지를 나타내는 값을 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|와 연결 된 바로 가기 키를 가져오거나 설정 합니다.는 <xref:System.Windows.Forms.ToolStripMenuItem>합니다.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|연결 된 바로 가기 키는 있는 여부를 나타내는 값을 가져오거나는 <xref:System.Windows.Forms.ToolStripMenuItem> 옆에 표시 되는 <xref:System.Windows.Forms.ToolStripMenuItem>합니다.|  
  
 다음 표에서 중요 한 <xref:System.Windows.Forms.MenuStrip> 도우미 클래스입니다.  
  
|클래스|설명|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|에 표시 된 선택 가능한 옵션을 나타냅니다는 <xref:System.Windows.Forms.MenuStrip> 또는 <xref:System.Windows.Forms.ContextMenuStrip>합니다.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|바로 가기 메뉴를 나타냅니다.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|사용자는 사용자가 클릭할 때 표시 되는 목록에서 단일 항목을 선택할 수 있게 하는 컨트롤을 나타냅니다는 <xref:System.Windows.Forms.ToolStripDropDownButton> 또는 더 높은 수준의 메뉴 항목입니다.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|파생 된 컨트롤에 대 한 기본 기능을 제공 <xref:System.Windows.Forms.ToolStripItem> 클릭 하면 드롭다운 항목을 표시 하는 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
