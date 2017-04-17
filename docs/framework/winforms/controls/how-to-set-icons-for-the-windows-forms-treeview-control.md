---
title: "방법: Windows Forms TreeView 컨트롤의 아이콘 설정 | Microsoft Docs"
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
  - "아이콘, TreeView 컨트롤에 대해 설정"
  - "ImageList 구성 요소[Windows Forms], 이미지 추가"
  - "TreeView 컨트롤의 트리 노드, 아이콘"
  - "TreeView 컨트롤[Windows Forms], 노드 아이콘"
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: Windows Forms TreeView 컨트롤의 아이콘 설정
Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤을 사용하여 각 노드 옆에 아이콘을 표시할 수 있습니다.  아이콘은 노드 텍스트의 바로 왼쪽에 배치됩니다.  이러한 아이콘을 표시하려면 트리 뷰를 <xref:System.Windows.Forms.ImageList> 컨트롤과 연결해야 합니다.  이미지 목록에 대한 자세한 내용은 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) 및 [방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)를 참조하십시오.  
  
> [!NOTE]
>  Microsoft .NET Framework 버전 1.1의 버그로 인해 응용 프로그램에서 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>을 호출할 때 이미지가 <xref:System.Windows.Forms.TreeView> 노드에 나타나지 않습니다.  이 버그를 해결하려면 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>를 호출한 후 바로 `Main` 메서드에서 <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>를 호출합니다.  이 버그는 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]에서 수정되었습니다.  
  
### 트리 뷰에 이미지를 표시하려면  
  
1.  사용할 기존 <xref:System.Windows.Forms.ImageList> 컨트롤을 <xref:System.Windows.Forms.TreeView> 컨트롤의 <xref:System.Windows.Forms.TreeView.ImageList%2A> 속성에 설정합니다.  
  
     이러한 속성은 디자이너의 속성 창을 사용하거나 코드를 통해 설정할 수 있습니다.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2.  노드의 <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> 및 <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> 속성을 설정합니다.  <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> 속성은 보통 및 확장 상태의 노드에 대해 표시되는 이미지를 결정하고 <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> 속성은 선택된 상태의 노드에 대해 표시되는 이미지를 결정합니다.  
  
     이러한 속성은 트리 노드 편집기를 사용하거나 코드를 통해 설정할 수 있습니다.  트리 노드 편집기를 열려면 속성 창에서 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성 옆에 있는 줄임표 단추\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\)를 클릭하십시오.  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## 참고 항목  
 [TreeView 컨트롤 개요](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)   
 [방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)   
 [방법: Windows Forms TreeView 컨트롤의 노드 전체 반복](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)   
 [방법: 클릭한 TreeView 노드 확인](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)   
 [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가\(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)