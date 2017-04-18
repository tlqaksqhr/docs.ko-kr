---
title: "방법: 클릭한 TreeView 노드 확인(Windows Forms) | Microsoft Docs"
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
  - "TreeNode"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "예제[Windows Forms], TreeView 컨트롤"
  - "TreeView 컨트롤의 트리 노드, 클릭한 노드 확인"
  - "TreeView 컨트롤[Windows Forms], 클릭한 노드 확인"
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 클릭한 TreeView 노드 확인(Windows Forms)
Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤을 사용할 경우에는 일반적으로 클릭한 노드를 확인하여 적절하게 응답하는 작업을 수행해야 합니다.  
  
### 클릭한 TreeView 노드를 확인하려면  
  
1.  <xref:System.EventArgs> 개체를 사용하여 클릭한 노드 개체에 대한 참조를 반환합니다.  
  
2.  해당 이벤트와 관련된 데이터를 포함하는 <xref:System.Windows.Forms.TreeViewEventArgs> 클래스를 검사하여 클릭된 노드를 확인합니다.  
  
    ```vb  
    Private Sub TreeView1_AfterSelect(ByVal sender As System.Object, _  
    ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       ' Determine by checking the Node property of the TreeViewEventArgs.  
       MessageBox.Show(e.Node.Text)  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,   
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       // Determine by checking the Text property.  
       MessageBox.Show(e.Node.Text);  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          // Determine by checking the Text property.  
          MessageBox::Show(e->Node->Text);  
       }  
    ```  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.Control.MouseDown> 또는 <xref:System.Windows.Forms.Control.MouseUp> 이벤트의 <xref:System.Windows.Forms.MouseEventArgs>를 사용하여 클릭 동작이 발생한 <xref:System.Drawing.Point>의 <xref:System.Drawing.Point.X%2A> 및 <xref:System.Drawing.Point.Y%2A> 좌표 값을 가져올 수도 있습니다.  그런 다음 <xref:System.Windows.Forms.TreeView> 컨트롤의 <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> 메서드를 사용하여 클릭된 노드를 확인합니다.  
  
## 참고 항목  
 [TreeView 컨트롤](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)