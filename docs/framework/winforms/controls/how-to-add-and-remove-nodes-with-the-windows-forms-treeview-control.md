---
title: "방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거 | Microsoft Docs"
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
  - "예제[Windows Forms], TreeView 컨트롤"
  - "TreeView 컨트롤의 트리 노드"
  - "TreeView 컨트롤[Windows Forms], 노드 추가"
  - "TreeView 컨트롤[Windows Forms], 노드 제거"
ms.assetid: de1b82db-4905-449a-9f59-af271a6b6673
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거
Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤은 해당 <xref:System.Windows.Forms.TreeView.Nodes%2A> 컬렉션에 최상위 노드를 저장합니다.  또한 각 <xref:System.Windows.Forms.TreeNode>에는 자식 노드를 저장하기 위한 고유한 <xref:System.Windows.Forms.TreeNode.Nodes%2A> 컬렉션이 있습니다.  이 두 컬렉션 속성은 모두 <xref:System.Windows.Forms.TreeNodeCollection> 형식입니다. 이 형식은 노드 계층 구조의 단일 수준에서 노드를 추가, 제거 및 다시 정렬할 수 있도록 하는 표준 컬렉션 멤버를 제공합니다.  
  
### 프로그래밍 방식으로 노드를 추가하려면  
  
1.  트리 뷰에 있는 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성의 <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> 메서드를 사용합니다.  
  
    ```vb  
    ' Adds new node as a child node of the currently selected node.  
    Dim newNode As TreeNode = New TreeNode("Text for new node")  
    TreeView1.SelectedNode.Nodes.Add(newNode)  
  
    ```  
  
    ```csharp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode newNode = new TreeNode("Text for new node");  
    treeView1.SelectedNode.Nodes.Add(newNode);  
  
    ```  
  
    ```cpp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode ^ newNode = new TreeNode("Text for new node");  
    treeView1->SelectedNode->Nodes->Add(newNode);  
    ```  
  
### 프로그래밍 방식으로 노드를 제거하려면  
  
1.  하나의 노드를 제거하려면 트리 뷰에 있는 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성의 <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> 메서드를 사용하고 모든 노드를 지우려면 <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> 메서드를 사용합니다.  
  
    ```vb  
    ' Removes currently selected node, or root if nothing is selected.  
    TreeView1.Nodes.Remove(TreeView1.SelectedNode)  
    ' Clears all nodes.  
    TreeView1.Nodes.Clear()  
  
    ```  
  
    ```csharp  
    // Removes currently selected node, or root if nothing   
    // is selected.  
    treeView1.Nodes.Remove(treeView1.SelectedNode);  
    // Clears all nodes.  
    TreeView1.Nodes.Clear();  
  
    ```  
  
    ```cpp  
    // Removes currently selected node, or root if nothing  
    // is selected.  
    treeView1->Nodes->Remove(treeView1->SelectedNode);  
    // Clears all nodes.  
    treeView1->Nodes->Clear();  
    ```  
  
## 참고 항목  
 [TreeView 컨트롤](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [TreeView 컨트롤 개요](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)   
 [방법: Windows Forms TreeView 컨트롤의 아이콘 설정](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)   
 [방법: Windows Forms TreeView 컨트롤의 노드 전체 반복](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)   
 [방법: 클릭한 TreeView 노드 확인](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)   
 [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가\(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)