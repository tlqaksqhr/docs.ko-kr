---
title: '방법: Windows Forms TreeView 컨트롤의 아이콘 설정'
ms.date: 03/30/2017
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
ms.openlocfilehash: b732aa510be22f3cbdc5197574f1e2a825c35df4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536487"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a><span data-ttu-id="48a69-102">방법: Windows Forms TreeView 컨트롤의 아이콘 설정</span><span class="sxs-lookup"><span data-stu-id="48a69-102">How to: Set Icons for the Windows Forms TreeView Control</span></span>
<span data-ttu-id="48a69-103">Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤 각 노드 옆에 아이콘을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48a69-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control can display icons next to each node.</span></span> <span data-ttu-id="48a69-104">노드 텍스트의 바로 왼쪽에 있는 아이콘에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48a69-104">The icons are positioned to the immediate left of the node text.</span></span> <span data-ttu-id="48a69-105">이러한 아이콘을 표시 하려면 있는 트리 뷰를 연결 해야는 <xref:System.Windows.Forms.ImageList> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="48a69-105">To display these icons, you must associate the tree view with an <xref:System.Windows.Forms.ImageList> control.</span></span> <span data-ttu-id="48a69-106">이미지 목록에 대 한 자세한 내용은 참조 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) 및 [하는 방법: Windows Forms ImageList 구성 요소와 이미지 추가 또는 제거](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48a69-106">For more information about image lists, see [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48a69-107">Microsoft.NET Framework 버전 1.1의에서 버그는 이미지에 표시 되지 않도록 방지 <xref:System.Windows.Forms.TreeView> 노드 응용 프로그램 호출 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="48a69-107">A bug in Microsoft .NET Framework version 1.1 prevents images from appearing on <xref:System.Windows.Forms.TreeView> nodes when your application calls <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="48a69-108">이 버그를 해결 하려면 호출 <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> 에 프로그램 `Main` 메서드를 호출한 후 즉시 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="48a69-108">To work around this bug, call <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in your `Main` method immediately after calling <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span></span> <span data-ttu-id="48a69-109">이 버그는에서 수정 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="48a69-109">This bug is fixed in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
### <a name="to-display-images-in-a-tree-view"></a><span data-ttu-id="48a69-110">트리 보기에서 이미지를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="48a69-110">To display images in a tree view</span></span>  
  
1.  <span data-ttu-id="48a69-111">설정의 <xref:System.Windows.Forms.TreeView> 컨트롤의 <xref:System.Windows.Forms.TreeView.ImageList%2A> 속성을 기존 <xref:System.Windows.Forms.ImageList> 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48a69-111">Set the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.ImageList%2A> property to the existing <xref:System.Windows.Forms.ImageList> control you wish to use.</span></span>  
  
     <span data-ttu-id="48a69-112">속성 창에 디자이너에서 나 코드에서 이러한 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48a69-112">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2.  <span data-ttu-id="48a69-113">노드의 설정 <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> 및 <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="48a69-113">Set the node's <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> and <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> properties.</span></span> <span data-ttu-id="48a69-114"><xref:System.Windows.Forms.TreeNode.ImageIndex%2A> 속성 노드의 일반 및 확장 된 상태에 대해 표시 되는 이미지를 결정 및 <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> 속성 노드의 선택 된 상태에 대 한 표시 되는 이미지를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="48a69-114">The <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> property determines the image displayed for the node's normal and expanded states, and the <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> property determines the image displayed for the node's selected state.</span></span>  
  
     <span data-ttu-id="48a69-115">코드에서 또는 TreeNode 편집기 내에서 이러한 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48a69-115">These properties can be set in code, or within the TreeNode Editor.</span></span> <span data-ttu-id="48a69-116">TreeNode 편집기를 열려면 줄임표 단추를 클릭 합니다. ( ![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.TreeView.Nodes%2A> 속성 창에서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="48a69-116">To open the TreeNode Editor, click the ellipsis button ( ![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property on the Properties window.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="48a69-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48a69-117">See Also</span></span>  
 [<span data-ttu-id="48a69-118">TreeView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="48a69-118">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [<span data-ttu-id="48a69-119">방법: Windows Forms TreeView 컨트롤을 사용하여 노드 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="48a69-119">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [<span data-ttu-id="48a69-120">방법: Windows Forms TreeView 컨트롤의 노드 전체 반복</span><span class="sxs-lookup"><span data-stu-id="48a69-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [<span data-ttu-id="48a69-121">방법: 클릭한 TreeView 노드 확인</span><span class="sxs-lookup"><span data-stu-id="48a69-121">How to: Determine Which TreeView Node Was Clicked</span></span>](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [<span data-ttu-id="48a69-122">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="48a69-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
