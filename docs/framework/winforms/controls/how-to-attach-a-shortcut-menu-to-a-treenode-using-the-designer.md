---
title: "방법: 디자이너를 사용하여 TreeNode에 바로 가기 메뉴 연결 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "바로 가기 메뉴, TreeNodes에 연결"
  - "TreeNode, 디자이너를 사용하여 바로 가기 메뉴 연결"
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 디자이너를 사용하여 TreeNode에 바로 가기 메뉴 연결
Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤은 Windows 운영 체제에서 Windows 탐색기 기능의 왼쪽 창에 파일과 폴더가 표시되는 방식과 비슷한 방식으로 노드 계층 구조를 표시하는 데 사용됩니다.  <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 설정하면 사용자가 <xref:System.Windows.Forms.TreeView> 컨트롤을 마우스 오른쪽 단추로 클릭할 경우 상황에 맞는 작업을 제공할 수 있습니다.  <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 개별 <xref:System.Windows.Forms.TreeNode> 항목과 연결하면 <xref:System.Windows.Forms.TreeView> 컨트롤에 사용자 지정된 수준의 바로 가기 메뉴 기능을 추가할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자인 타임에서 바로 가기 메뉴를 TreeNode와 연결하려면  
  
1.  <xref:System.Windows.Forms.TreeView> 컨트롤을 폼에 추가한 다음 필요에 따라 <xref:System.Windows.Forms.TreeView>에 노드를 추가합니다.  자세한 내용은 [방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)를 참조하십시오.  
  
2.  <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 폼에 추가한 다음 런타임에서 사용 가능하게 할 노드 수준 작업을 나타내는 바로 가기 메뉴에 메뉴 항목을 추가합니다.  자세한 내용은 [방법: ContextMenuStrip에 메뉴 항목 추가](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md)를 참조하십시오.  
  
3.  <xref:System.Windows.Forms.TreeView> 컨트롤의 **TreeNodeEditor** 대화 상자를 다시 열고 편집할 노드를 선택한 다음 <xref:System.Windows.Forms.ContextMenuStrip> 속성을 사용자가 추가한 바로 가기 메뉴로 설정합니다.  
  
4.  이 속성이 설정되어 있을 때 노드를 마우스 오른쪽 단추로 클릭하면 바로 가기 메뉴가 표시됩니다.  
  
     또한 해당 메뉴 항목에 대한 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트를 처리하는 코드를 작성할 수 있습니다.  
  
## 참고 항목  
 [TreeView 컨트롤](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [TreeView 컨트롤 개요](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)   
 [ContextMenuStrip 컨트롤](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)