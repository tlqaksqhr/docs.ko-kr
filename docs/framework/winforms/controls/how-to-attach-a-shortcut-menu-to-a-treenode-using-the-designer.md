---
title: "방법: 디자이너를 사용하여 TreeNode에 바로 가기 메뉴 연결"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ab73f6e4dc6a4e348853183046db564e748360b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a>방법: 디자이너를 사용하여 TreeNode에 바로 가기 메뉴 연결
Windows Forms <xref:System.Windows.Forms.TreeView> 제어 파일 및 Windows 운영 체제에서 Windows 탐색기 기능의 왼쪽된 창에 표시 되는 폴더에 비슷한 노드 계층 구조를 표시 합니다. 설정 하 여는 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 제공할 수 있습니다 상황에 맞는 작업 사용자에 게 마우스 오른쪽 단추로 클릭 하 고 <xref:System.Windows.Forms.TreeView> 제어 합니다. 연결 하 여 한 <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 개별 <xref:System.Windows.Forms.TreeNode> 항목, 사용자 지정 된 수준의 바로 가기 메뉴 기능을 추가할 수 있습니다 프로그램 <xref:System.Windows.Forms.TreeView> 컨트롤입니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a>디자인 타임에 TreeNode에 바로 가기 메뉴를 연결할  
  
1.  추가 <xref:System.Windows.Forms.TreeView> 양식에 컨트롤을 다음에 노드 추가 <xref:System.Windows.Forms.TreeView> 필요에 따라 합니다. 자세한 내용은 참조 [하는 방법: Windows Forms TreeView 컨트롤에서 노드 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)합니다.  
  
2.  추가 <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 폼에 다음 실행 시 사용할 수 있도록 하려는 노드 수준의 작업을 나타내는 바로 가기 메뉴에 메뉴 항목을 추가 합니다. 자세한 내용은 참조 [하는 방법: ContextMenuStrip에 메뉴 항목 추가](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md)합니다.  
  
3.  다시 여세요는 **TreeNodeEditor** 에 대 한 대화 상자는 <xref:System.Windows.Forms.TreeView> 컨트롤을 편집 하 고 설정 노드를 선택 해당 <xref:System.Windows.Forms.ContextMenuStrip> 추가한 바로 가기 메뉴에는 속성입니다.  
  
4.  이 속성이 설정 된 경우 바로 가기 메뉴에서 노드를 마우스 오른쪽 단추로 클릭할 때 표시 됩니다.  
  
     또한 처리 하는 코드를 작성 하려면 됩니다는 <xref:System.Windows.Forms.ToolStripItem.Click> 이러한 새 메뉴 항목에 대 한 이벤트입니다.  
  
## <a name="see-also"></a>참고 항목  
 [TreeView 컨트롤](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [TreeView 컨트롤 개요](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [ContextMenuStrip 컨트롤](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
