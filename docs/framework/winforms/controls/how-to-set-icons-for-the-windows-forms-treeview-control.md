---
title: "방법: Windows Forms TreeView 컨트롤의 아이콘 설정"
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
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6d6133a378c4939a20cef6bab8f3ee5f36b9c3cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>방법: Windows Forms TreeView 컨트롤의 아이콘 설정
Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤 각 노드 옆에 아이콘을 표시할 수 있습니다. 노드 텍스트의 바로 왼쪽에 있는 아이콘에 배치 됩니다. 이러한 아이콘을 표시 하려면 있는 트리 뷰를 연결 해야는 <xref:System.Windows.Forms.ImageList> 제어 합니다. 이미지 목록에 대 한 자세한 내용은 참조 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) 및 [하는 방법: Windows Forms ImageList 구성 요소와 이미지 추가 또는 제거](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)합니다.  
  
> [!NOTE]
>  Microsoft.NET Framework 버전 1.1의에서 버그는 이미지에 표시 되지 않도록 방지 <xref:System.Windows.Forms.TreeView> 노드 응용 프로그램 호출 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>합니다. 이 버그를 해결 하려면 호출 <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> 에 프로그램 `Main` 메서드를 호출한 후 즉시 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>합니다. 이 버그는에서 수정 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]합니다.  
  
### <a name="to-display-images-in-a-tree-view"></a>트리 보기에서 이미지를 표시 하려면  
  
1.  설정의 <xref:System.Windows.Forms.TreeView> 컨트롤의 <xref:System.Windows.Forms.TreeView.ImageList%2A> 속성을 기존 <xref:System.Windows.Forms.ImageList> 컨트롤을 사용 합니다.  
  
     속성 창에 디자이너에서 나 코드에서 이러한 속성을 설정할 수 있습니다.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2.  노드의 설정 <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> 및 <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> 속성입니다. <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> 속성 노드의 일반 및 확장 된 상태에 대해 표시 되는 이미지를 결정 및 <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> 속성 노드의 선택 된 상태에 대 한 표시 되는 이미지를 결정 합니다.  
  
     코드에서 또는 TreeNode 편집기 내에서 이러한 속성을 설정할 수 있습니다. TreeNode 편집기를 열려면 줄임표 단추를 클릭 합니다. ( ![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성 창에서 속성입니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [TreeView 컨트롤 개요](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [방법: Windows Forms TreeView 컨트롤의 노드 전체 반복](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [방법: 클릭한 TreeView 노드 확인](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
