---
title: "방법: Windows Forms TreeView 컨트롤의 노드 전체 반복 | Microsoft Docs"
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
  - "TreeView 컨트롤의 트리 노드, 반복"
  - "TreeView 컨트롤[Windows Forms], TreeView 컨트롤"
ms.assetid: 427f8928-ebcf-4beb-887f-695b905d5134
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Forms TreeView 컨트롤의 노드 전체 반복
노드 값으로 계산하기 위해 Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤의 모든 노드를 검사해야 할 경우가 있습니다.  이 작업은 트리의 각 컬렉션에 있는 모든 노드를 반복하는 재귀 프로시저\(C\# 및 C\+\+에서는 재귀 메서드\)를 사용하여 수행할 수 있습니다.  
  
 트리 뷰의 각 <xref:System.Windows.Forms.TreeNode> 개체에는 트리 뷰를 탐색하는 데 사용할 수 있는 <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A>, <xref:System.Windows.Forms.TreeNode.Parent%2A> 등의 속성이 있습니다.  <xref:System.Windows.Forms.TreeNode.Parent%2A> 속성 값은 현재 노드의 부모 노드입니다.  현재 노드의 자식 노드가 있는 경우 <xref:System.Windows.Forms.TreeNode.Nodes%2A> 속성에 이러한 자식 노드가 나열됩니다.  <xref:System.Windows.Forms.TreeView> 컨트롤에는 전체 트리 뷰의 루트 노드인 <xref:System.Windows.Forms.TreeView.TopNode%2A> 속성이 있습니다.  
  
### TreeView 컨트롤의 모든 노드를 반복하려면  
  
1.  각 노드를 테스트하는 재귀 프로시저\(C\# 및 C\+\+에서는 재귀 메서드\)를 만듭니다.  
  
2.  프로시저를 호출합니다.  
  
     다음 예제에서는 각 <xref:System.Windows.Forms.TreeNode> 개체의 <xref:System.Windows.Forms.TreeNode.Text%2A> 속성을 인쇄하는 방법을 보여 줍니다.  
  
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
  
## 참고 항목  
 [TreeView 컨트롤](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [Recursive Procedures](../Topic/Recursive%20Procedures%20\(Visual%20Basic\).md)