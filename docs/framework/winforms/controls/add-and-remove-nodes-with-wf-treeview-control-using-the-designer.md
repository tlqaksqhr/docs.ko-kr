---
title: "방법: 디자이너를 사용하여 Windows Forms TreeView 컨트롤에서 노드 추가 및 제거 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "예제[Windows Forms], TreeView 컨트롤"
  - "TreeView 컨트롤의 트리 노드"
  - "TreeView 컨트롤[Windows Forms], 노드 추가"
  - "TreeView 컨트롤[Windows Forms], 노드 제거"
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 디자이너를 사용하여 Windows Forms TreeView 컨트롤에서 노드 추가 및 제거
Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤에서는 노드를 계층 구조 방식으로 표시하기 때문에 노드를 추가할 때는 해당 부모 노드를 확인해야 합니다.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.TreeView> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자이너에서 노드를 추가하거나 제거하려면  
  
1.  <xref:System.Windows.Forms.TreeView> 컨트롤을 선택합니다.  
  
2.  **속성** 창에서 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성 옆의 **줄임표**\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) 단추를 클릭합니다.  
  
     **TreeNode 편집기**가 나타납니다.  
  
3.  노드를 추가하려면 루트 노드가 있어야 합니다. 루트 노드가 없으면 먼저 **루트 추가**단추를 클릭하여 루트를 추가해야 합니다.  그런 다음 루트나 다른 노드를 선택하고 **자식 추가** 단추를 클릭하여 자식 노드를 추가할 수 있습니다.  
  
4.  노드를 삭제하려면 삭제할 노드를 선택한 다음 **삭제** 단추를 클릭합니다.  
  
## 참고 항목  
 [TreeView 컨트롤](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [TreeView 컨트롤 개요](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)   
 [방법: Windows Forms TreeView 컨트롤의 아이콘 설정](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)   
 [방법: Windows Forms TreeView 컨트롤의 노드 전체 반복](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)   
 [방법: 클릭한 TreeView 노드 확인](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)   
 [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가\(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)