---
title: ListView 컨트롤 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
ms.openlocfilehash: f92b5f5ae40287c95da10ef96aad0fa764fa00e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540675"
---
# <a name="listview-control-overview-windows-forms"></a>ListView 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤은 아이콘이 포함된 항목 목록을 표시합니다. 목록 뷰를 사용하여 Windows 탐색기의 오른쪽 창과 같은 사용자 인터페이스를 만들 수 있습니다. 컨트롤에 4 개의 보기 모드: LargeIcon, SmallIcon, 목록 및 세부 정보입니다.  
  
## <a name="what-you-can-do-with-the-listview-control"></a>ListView 컨트롤으로 수행할 수 있습니다  
  
> [!NOTE]
>  추가 뷰 모드로, 타일, Windows XP 및 Windows Server 2003 운영 체제에서 사용할 수만 경우 자세한 내용은 참조 [하는 방법: Windows Forms ListView 컨트롤에서 Tile 보기 사용](../../../../docs/framework/winforms/controls/how-to-enable-tile-view-in-a-windows-forms-listview-control.md)합니다.  
  
 LargeIcon 모드 표시 된 항목 텍스트 옆에 있는 큰 아이콘 항목은 컨트롤이 충분히 큰 여러 열에 나타납니다. SmallIcon 모드는 작은 아이콘 표시 한다는 같습니다. 목록 모드 작은 아이콘을 표시 하지만 단일 열에는 항상 합니다. 자세히 보기 모드에는 여러 열에 항목이 표시 됩니다. 자세한 내용은 참조 [하는 방법: Windows Forms ListView 컨트롤에 열 추가](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)합니다. 보기 모드에 의해 결정 되는 <xref:System.Windows.Forms.ListView.View%2A> 속성입니다. 보기 모드의 모든 이미지 목록의 이미지를 표시할 수 있습니다. 자세한 내용은 참조 [하는 방법: Windows Forms ListView 컨트롤에 대 한 표시 아이콘이](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)합니다.  
  
 다음 표에서 몇 가지는 <xref:System.Windows.Forms.ListView> 멤버와는 사용할 수 있는 보기입니다.  
  
|ListView 멤버|보기|  
|---------------------|----------|  
|<xref:System.Windows.Forms.ListView.Alignment%2A> 속성|<xref:System.Windows.Forms.View.SmallIcon> 또는 <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.AutoArrange%2A> 속성|<xref:System.Windows.Forms.View.SmallIcon> 또는 <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.AutoResizeColumn%2A> 메서드|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.Columns%2A> 속성|<xref:System.Windows.Forms.View.Details> 또는 <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.DrawSubItem> 이벤트|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.FindItemWithText%2A> 메서드|<xref:System.Windows.Forms.View.Details>, <xref:System.Windows.Forms.View.List>또는 <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.FindNearestItem%2A> 메서드|<xref:System.Windows.Forms.View.SmallIcon> 또는 <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.GetItemAt%2A> 메서드|<xref:System.Windows.Forms.View.Details> 또는 <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.Groups%2A> 속성|제외한 모든 보기 <xref:System.Windows.Forms.View.List>|  
|<xref:System.Windows.Forms.ListView.HeaderStyle%2A> 속성|<xref:System.Windows.Forms.View.Details>.|  
|<xref:System.Windows.Forms.ListView.InsertionMark%2A> 속성|<xref:System.Windows.Forms.View.LargeIcon>, <xref:System.Windows.Forms.View.SmallIcon>또는 <xref:System.Windows.Forms.View.Tile>|  
  
 키 속성은 <xref:System.Windows.Forms.ListView> 컨트롤은 <xref:System.Windows.Forms.ListView.Items%2A>를 컨트롤에 의해 표시 되는 항목을 포함 하 합니다. <xref:System.Windows.Forms.ListView.SelectedItems%2A> 속성 컨트롤에서 현재 선택 된 항목의 컬렉션을 포함 합니다. 예를 들어 경우 다른 컨트롤에 한 번에 여러 항목이 끌어서를 여러 항목을 선택할 수는 <xref:System.Windows.Forms.ListView.MultiSelect%2A> 속성이 `true`합니다. <xref:System.Windows.Forms.ListView> 경우 컨트롤에서 항목 옆의 확인란을 표시할 수는 <xref:System.Windows.Forms.ListView.CheckBoxes%2A> 속성이 `true`합니다.  
  
 <xref:System.Windows.Forms.ListView.Activation%2A> 속성 동작 유형을 목록에서 항목을 활성화 하기 위해 사용자를 수행 해야 결정: 옵션은 <xref:System.Windows.Forms.ItemActivation.Standard>, <xref:System.Windows.Forms.ItemActivation.OneClick>, 및 <xref:System.Windows.Forms.ItemActivation.TwoClick>합니다. <xref:System.Windows.Forms.ItemActivation.OneClick> 활성화 된 항목을 활성화 하려면 한 번의 클릭이 필요 합니다. <xref:System.Windows.Forms.ItemActivation.TwoClick> 정품 인증을 사용 해야; 항목을 활성화 하려면 두 번 클릭 항목 텍스트의 색을 변경 하는 한 번의 클릭 합니다. <xref:System.Windows.Forms.ItemActivation.Standard> 활성화 사용자를 두 번 클릭 하면 항목이 활성화를 이어야 하는데 항목의 모양을 변경 되지 않습니다.  
  
 <xref:System.Windows.Forms.ListView> 그룹화, tile 보기 및 삽입 표시를 포함 하 여 Windows XP 플랫폼에서도 지 원하는 비주얼 스타일 및 기타 기능을 사용할 수 있는 컨트롤입니다. 자세한 내용은 참조 [Windows XP 기능 및 Windows Forms 컨트롤](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ListView>  
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [방법: Windows Forms ListView 컨트롤에 열 추가](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [방법: Windows Forms ListView 컨트롤의 아이콘 표시](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [방법: Windows Forms ListView 컨트롤을 사용하여 열에 하위 항목 표시](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 [방법: Windows Forms ListView 컨트롤에서 항목 선택](../../../../docs/framework/winforms/controls/how-to-select-an-item-in-the-windows-forms-listview-control.md)  
 [방법: Windows Forms ListView 컨트롤에서 항목 그룹화](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)  
 [방법: Windows Forms ListView 컨트롤에 삽입 표시 나타내기](../../../../docs/framework/winforms/controls/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)  
 [방법: ListView 컨트롤에 검색 기능 추가](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
 [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [방법: Windows Forms으로 다중 창 사용자 인터페이스 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)
