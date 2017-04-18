---
title: "ListView 컨트롤 개요(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ListView"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "목록 보기"
  - "목록"
  - "ListView 컨트롤[Windows Forms], ListView 컨트롤 정보"
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# ListView 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤은 아이콘과 함께 항목 목록을 표시합니다.  목록 뷰를 사용하면 Windows 탐색기의 오른쪽 창과 같은 사용자 인터페이스를 만들 수 있습니다.  ListView 컨트롤에는 LargeIcon, SmallIcon, List 및 Details의 네 가지 보기 모드가 있습니다.  
  
## ListView 컨트롤로 할 수 있는 작업  
  
> [!NOTE]
>  또 다른 보기 모드인 Tile은 Windows XP 및 Windows Server 2003 운영 체제에서만 사용할 수 있습니다.  자세한 내용은 [방법: Windows Forms ListView 컨트롤의 Tile 보기 사용](../../../../docs/framework/winforms/controls/how-to-enable-tile-view-in-a-windows-forms-listview-control.md)을 참조하십시오.  
  
 LargeIcon 모드에서는 항목 텍스트 옆에 큰 아이콘을 표시합니다. 이 때 컨트롤이 충분히 크면 항목이 여러 열에 나타납니다.  SmallIcon 모드에서는 작은 아이콘이 표시된다는 것을 제외하면 같습니다.  List 모드에서는 항상 하나의 열에 작은 아이콘을 표시합니다.  Details 모드에서는 항목이 여러 열에 표시됩니다.  자세한 내용은 [방법: Windows Forms ListView 컨트롤에 열 추가](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)를 참조하십시오.  보기 모드는 <xref:System.Windows.Forms.ListView.View%2A> 속성에 의해 결정됩니다.  모든 보기 모드에서 이미지 목록의 이미지를 표시할 수 있습니다.  자세한 내용은 [방법: Windows Forms ListView 컨트롤의 아이콘 표시](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)를 참조하십시오.  
  
 다음 표에서는 사용할 수 있는 일부 <xref:System.Windows.Forms.ListView> 멤버와 보기를 보여 줍니다.  
  
|ListView 멤버|보기|  
|-----------------|--------|  
|<xref:System.Windows.Forms.ListView.Alignment%2A> 속성|<xref:System.Windows.Forms.View> 또는 <xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.AutoArrange%2A> 속성|<xref:System.Windows.Forms.View> 또는 <xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.AutoResizeColumn%2A> 메서드|<xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.Columns%2A> 속성|<xref:System.Windows.Forms.View> 또는 <xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.DrawSubItem> 이벤트|<xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.FindItemWithText%2A> 메서드|<xref:System.Windows.Forms.View>, <xref:System.Windows.Forms.View> 또는 <xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.FindNearestItem%2A> 메서드|<xref:System.Windows.Forms.View> 또는 <xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.GetItemAt%2A> 메서드|<xref:System.Windows.Forms.View> 또는 <xref:System.Windows.Forms.View>|  
|<xref:System.Windows.Forms.ListView.Groups%2A> 속성|<xref:System.Windows.Forms.View>를 제외한 모든 보기|  
|<xref:System.Windows.Forms.ListView.HeaderStyle%2A> 속성|<xref:System.Windows.Forms.View>.|  
|<xref:System.Windows.Forms.ListView.InsertionMark%2A> 속성|<xref:System.Windows.Forms.View>, <xref:System.Windows.Forms.View> 또는 <xref:System.Windows.Forms.View>|  
  
 <xref:System.Windows.Forms.ListView> 컨트롤의 가장 중요한 속성은 컨트롤에 의해 표시되는 항목이 포함된 <xref:System.Windows.Forms.ListView.Items%2A>입니다.  컨트롤에서 현재 선택된 항목의 컬렉션은 <xref:System.Windows.Forms.ListView.SelectedItems%2A> 속성에 포함됩니다.  <xref:System.Windows.Forms.ListView.MultiSelect%2A> 속성을 `true`로 설정하면 사용자가 여러 항목을 선택할 수 있습니다. 예를 들어, 여러 항목을 한꺼번에 다른 컨트롤에 끌어서 놓을 수 있습니다.  <xref:System.Windows.Forms.ListView.CheckBoxes%2A> 속성을 `true`로 설정하면 <xref:System.Windows.Forms.ListView> 컨트롤에서 항목 옆에 확인란을 표시할 수 있습니다.  
  
 <xref:System.Windows.Forms.ListView.Activation%2A> 속성은 사용자가 목록에 있는 항목을 활성화하기 위해 수행해야 하는 작업의 유형을 결정합니다. 옵션에는 <xref:System.Windows.Forms.ItemActivation>, <xref:System.Windows.Forms.ItemActivation> 및 <xref:System.Windows.Forms.ItemActivation>이 있습니다.  <xref:System.Windows.Forms.ItemActivation> 활성화 옵션을 사용하는 경우 항목을 한 번 클릭하면 항목이 활성화되며,  <xref:System.Windows.Forms.ItemActivation> 활성화 옵션을 사용하는 경우에는 사용자가 항목을 두 번 클릭하면 항목이 활성화되고 한 번 클릭하면 항목 텍스트의 색이 변경됩니다.  또한 <xref:System.Windows.Forms.ItemActivation> 활성화 옵션을 사용하는 경우에는 사용자가 항목을 두 번 클릭하면 항목이 활성화되지만 항목의 모양은 변경되지 않습니다.  
  
 또한 <xref:System.Windows.Forms.ListView> 컨트롤에서는 그룹화, Tile 보기, 삽입 표시 등 Windows XP 플랫폼에서 사용할 수 있는 비주얼 스타일과 기타 기능이 지원됩니다.  자세한 내용은 [Windows XP Features and Windows Forms Controls](http://msdn.microsoft.com/ko-kr/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)를 참조하십시오.  
  
## 참고 항목  
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
 [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가\(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)   
 [방법: Windows Forms으로 다중 창 사용자 인터페이스 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)