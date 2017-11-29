---
title: "방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: de1b82db-4905-449a-9f59-af271a6b6673
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41834f0bdfe800019c1f641d5b20147b10774221
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a>방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거
Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤의 최상위 노드를 저장 합니다. 해당 <xref:System.Windows.Forms.TreeView.Nodes%2A> 컬렉션입니다. 각 <xref:System.Windows.Forms.TreeNode> 역시 자체 <xref:System.Windows.Forms.TreeNode.Nodes%2A> 해당 자식 노드를 저장 하는 컬렉션입니다. 두 컬렉션 속성은 형식의 <xref:System.Windows.Forms.TreeNodeCollection>, 추가, 사용할 수 있는 표준 컬렉션 멤버를 제거 및 노드 계층의 단일 수준에서 노드를 다시 정렬를 제공 합니다.  
  
### <a name="to-add-nodes-programmatically"></a>프로그래밍 방식으로 노드를 추가 하려면  
  
1.  사용 하 여는 <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> 트리 보기의 메서드 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성입니다.  
  
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
  
### <a name="to-remove-nodes-programmatically"></a>프로그래밍 방식으로 노드를 제거 하려면  
  
1.  사용 하 여는 <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> 메서드 트리 보기의 <xref:System.Windows.Forms.TreeView.Nodes%2A> 단일 노드를 제거 하려면 속성 또는 <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> 메서드 모든 노드를 선택 취소 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [TreeView 컨트롤](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [TreeView 컨트롤 개요](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [방법: Windows Forms TreeView 컨트롤의 아이콘 설정](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)  
 [방법: Windows Forms TreeView 컨트롤의 노드 전체 반복](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [방법: 클릭한 TreeView 노드 확인](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
