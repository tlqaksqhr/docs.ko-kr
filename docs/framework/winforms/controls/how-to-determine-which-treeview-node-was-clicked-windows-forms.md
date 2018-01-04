---
title: "방법: 클릭한 TreeView 노드 확인(Windows Forms)"
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
f1_keywords: TreeNode
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- tree nodes in TreeView control [Windows Forms], determining node clicked
- TreeView control [Windows Forms], determining node clicked
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2671d2790b3c5e476513cd5932d4684838aeceb6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="10ed9-102">방법: 클릭한 TreeView 노드 확인(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="10ed9-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="10ed9-103">Windows Forms 작업할 때 <xref:System.Windows.Forms.TreeView> 컨트롤은 일반적인 작업 결정 하는 것 노드 클릭 되었는지와 적절 하 게 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="10ed9-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="10ed9-104">클릭 한 TreeView 노드 확인</span><span class="sxs-lookup"><span data-stu-id="10ed9-104">To determine which TreeView node was clicked</span></span>  
  
1.  <span data-ttu-id="10ed9-105">사용 하 여는 <xref:System.EventArgs> 클릭 한 노드 개체에 대 한 참조를 반환 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="10ed9-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2.  <span data-ttu-id="10ed9-106">노드를 선택 하 여 클릭 했는지 확인는 <xref:System.Windows.Forms.TreeViewEventArgs> 이벤트와 관련 된 데이터를 포함 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="10ed9-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
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
    >  <span data-ttu-id="10ed9-107">사용할 수 있습니다는 <xref:System.Windows.Forms.MouseEventArgs> 의 <xref:System.Windows.Forms.Control.MouseDown> 또는 <xref:System.Windows.Forms.Control.MouseUp> 가져올 이벤트는 <xref:System.Drawing.Point.X%2A> 및 <xref:System.Drawing.Point.Y%2A> 좌표 값은 <xref:System.Drawing.Point> 클릭이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="10ed9-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="10ed9-108">다음을 사용 하 여는 <xref:System.Windows.Forms.TreeView> 컨트롤의 <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> 클릭 된 노드를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10ed9-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ed9-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10ed9-109">See Also</span></span>  
 [<span data-ttu-id="10ed9-110">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="10ed9-110">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
