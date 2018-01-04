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
ms.workload: dotnet
ms.openlocfilehash: 02dfe1cb494df91a2a3ef3a6bba533306d61edef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control"></a><span data-ttu-id="98f5a-102">방법: Windows Forms TreeView 컨트롤의 노드 전체 반복</span><span class="sxs-lookup"><span data-stu-id="98f5a-102">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>
<span data-ttu-id="98f5a-103">Windows Forms의 모든 노드를 검사 하는 경우에 따라 <xref:System.Windows.Forms.TreeView> 노드 값에 몇 가지 계산을 수행 하기 위해 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="98f5a-103">It is sometimes useful to examine every node in a Windows Forms <xref:System.Windows.Forms.TreeView> control in order to perform some calculation on the node values.</span></span> <span data-ttu-id="98f5a-104">트리의 각 컬렉션의 각 노드를 반복하는 재귀 프로시저(C# 및 C++의 재귀 메서드)를 사용하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98f5a-104">This operation can be done using a recursive procedure (recursive method in C# and C++) that iterates through each node in each collection of the tree.</span></span>  
  
 <span data-ttu-id="98f5a-105">각 <xref:System.Windows.Forms.TreeNode> 트리 보기에서 개체의 트리 뷰를 탐색 하는 데 사용할 수 있는 속성: <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A>, 및 <xref:System.Windows.Forms.TreeNode.Parent%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="98f5a-105">Each <xref:System.Windows.Forms.TreeNode> object in a tree view has properties that you can use to navigate the tree view: <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A>, and <xref:System.Windows.Forms.TreeNode.Parent%2A>.</span></span> <span data-ttu-id="98f5a-106">값은 <xref:System.Windows.Forms.TreeNode.Parent%2A> 속성은 현재 노드의 부모 노드입니다.</span><span class="sxs-lookup"><span data-stu-id="98f5a-106">The value of the <xref:System.Windows.Forms.TreeNode.Parent%2A> property is the parent node of the current node.</span></span> <span data-ttu-id="98f5a-107">에 나열 되어 있는 경우, 현재 노드의 자식 노드는 <xref:System.Windows.Forms.TreeNode.Nodes%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="98f5a-107">The child nodes of the current node, if there are any, are listed in its <xref:System.Windows.Forms.TreeNode.Nodes%2A> property.</span></span> <span data-ttu-id="98f5a-108"><xref:System.Windows.Forms.TreeView> 컨트롤 자체에 <xref:System.Windows.Forms.TreeView.TopNode%2A> 속성이 속한 전체 형식 트리 뷰의 루트 노드에 설정 되어 만들어져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98f5a-108">The <xref:System.Windows.Forms.TreeView> control itself has the <xref:System.Windows.Forms.TreeView.TopNode%2A> property, which is the root node of the entire tree view.</span></span>  
  
### <a name="to-iterate-through-all-nodes-of-the-treeview-control"></a><span data-ttu-id="98f5a-109">TreeView 컨트롤의 노드 전체를 반복하려면</span><span class="sxs-lookup"><span data-stu-id="98f5a-109">To iterate through all nodes of the TreeView control</span></span>  
  
1.  <span data-ttu-id="98f5a-110">각 노드를 테스트하는 재귀 프로시저(C# 및 C++의 재귀 메서드)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98f5a-110">Create a recursive procedure (recursive method in C# and C++) that tests each node.</span></span>  
  
2.  <span data-ttu-id="98f5a-111">프로시저를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="98f5a-111">Call the procedure.</span></span>  
  
     <span data-ttu-id="98f5a-112">다음 예제에서는 각 인쇄 하는 방법을 보여 줍니다 <xref:System.Windows.Forms.TreeNode> 개체의 <xref:System.Windows.Forms.TreeNode.Text%2A> 속성:</span><span class="sxs-lookup"><span data-stu-id="98f5a-112">The following example shows how to print each <xref:System.Windows.Forms.TreeNode> object's <xref:System.Windows.Forms.TreeNode.Text%2A> property:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="98f5a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98f5a-113">See Also</span></span>  
 [<span data-ttu-id="98f5a-114">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="98f5a-114">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [<span data-ttu-id="98f5a-115">재귀 프로시저</span><span class="sxs-lookup"><span data-stu-id="98f5a-115">Recursive Procedures</span></span>](~/docs/visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)
