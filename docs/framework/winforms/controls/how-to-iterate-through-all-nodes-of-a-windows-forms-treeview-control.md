---
title: "방법: Windows Forms TreeView 컨트롤의 노드 전체 반복"
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
- TreeView control [Windows Forms], iterating through nodes
- tree nodes in TreeView control [Windows Forms], iterating through
ms.assetid: 427f8928-ebcf-4beb-887f-695b905d5134
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 057612bfb28333df0aebaa5ca19555f4c4951687
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control"></a>방법: Windows Forms TreeView 컨트롤의 노드 전체 반복
Windows Forms의 모든 노드를 검사 하는 경우에 따라 <xref:System.Windows.Forms.TreeView> 노드 값에 몇 가지 계산을 수행 하기 위해 컨트롤입니다. 트리의 각 컬렉션의 각 노드를 반복하는 재귀 프로시저(C# 및 C++의 재귀 메서드)를 사용하여 이 작업을 수행할 수 있습니다.  
  
 각 <xref:System.Windows.Forms.TreeNode> 트리 보기에서 개체의 트리 뷰를 탐색 하는 데 사용할 수 있는 속성: <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A>, 및 <xref:System.Windows.Forms.TreeNode.Parent%2A>합니다. 값은 <xref:System.Windows.Forms.TreeNode.Parent%2A> 속성은 현재 노드의 부모 노드입니다. 에 나열 되어 있는 경우, 현재 노드의 자식 노드는 <xref:System.Windows.Forms.TreeNode.Nodes%2A> 속성입니다. <xref:System.Windows.Forms.TreeView> 컨트롤 자체에 <xref:System.Windows.Forms.TreeView.TopNode%2A> 속성이 속한 전체 형식 트리 뷰의 루트 노드에 설정 되어 만들어져야 합니다.  
  
### <a name="to-iterate-through-all-nodes-of-the-treeview-control"></a>TreeView 컨트롤의 노드 전체를 반복하려면  
  
1.  각 노드를 테스트하는 재귀 프로시저(C# 및 C++의 재귀 메서드)를 만듭니다.  
  
2.  프로시저를 호출합니다.  
  
     다음 예제에서는 각 인쇄 하는 방법을 보여 줍니다 <xref:System.Windows.Forms.TreeNode> 개체의 <xref:System.Windows.Forms.TreeNode.Text%2A> 속성:  
  
    ```vb  
    Private Sub PrintRecursive(ByVal n As TreeNode)  
       System.Diagnostics.Debug.WriteLine(n.Text)  
       MessageBox.Show(n.Text)  
       Dim aNode As TreeNode  
       For Each aNode In n.Nodes  
          PrintRecursive(aNode)  
       Next  
    End Sub  
  
    ' Call the procedure using the top nodes of the treeview.  
    Private Sub CallRecursive(ByVal aTreeView As TreeView)  
       Dim n As TreeNode  
       For Each n In aTreeView.Nodes  
          PrintRecursive(n)  
       Next  
    End Sub  
    ```  
  
    ```csharp  
    private void PrintRecursive(TreeNode treeNode)  
    {  
       // Print the node.  
       System.Diagnostics.Debug.WriteLine(treeNode.Text);  
       MessageBox.Show(treeNode.Text);  
       // Print each node recursively.  
       foreach (TreeNode tn in treeNode.Nodes)  
       {  
          PrintRecursive(tn);  
       }  
    }  
  
    // Call the procedure using the TreeView.  
    private void CallRecursive(TreeView treeView)  
    {  
       // Print each node recursively.  
       TreeNodeCollection nodes = treeView.Nodes;  
       foreach (TreeNode n in nodes)  
       {  
          PrintRecursive(n);  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void PrintRecursive( TreeNode^ treeNode )  
       {  
          // Print the node.  
          System::Diagnostics::Debug::WriteLine( treeNode->Text );  
          MessageBox::Show( treeNode->Text );  
  
          // Print each node recursively.  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(treeNode->Nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ tn = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( tn );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
  
       // Call the procedure using the TreeView.  
       void CallRecursive( TreeView^ treeView )  
       {  
          // Print each node recursively.  
          TreeNodeCollection^ nodes = treeView->Nodes;  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ n = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( n );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [TreeView 컨트롤](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [재귀 프로시저](~/docs/visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)
