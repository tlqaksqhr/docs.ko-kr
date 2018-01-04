---
title: "방법: 디자이너를 사용하여 TreeNode에 바로 가기 메뉴 연결"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3acc1a731fa584a17c8a96f8a02986a504cd302d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a><span data-ttu-id="1331a-102">방법: 디자이너를 사용하여 TreeNode에 바로 가기 메뉴 연결</span><span class="sxs-lookup"><span data-stu-id="1331a-102">How to: Attach a Shortcut Menu to a TreeNode Using the Designer</span></span>
<span data-ttu-id="1331a-103">Windows Forms <xref:System.Windows.Forms.TreeView> 제어 파일 및 Windows 운영 체제에서 Windows 탐색기 기능의 왼쪽된 창에 표시 되는 폴더에 비슷한 노드 계층 구조를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1331a-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of the Windows Explorer feature in Windows operating systems.</span></span> <span data-ttu-id="1331a-104">설정 하 여는 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 제공할 수 있습니다 상황에 맞는 작업 사용자에 게 마우스 오른쪽 단추로 클릭 하 고 <xref:System.Windows.Forms.TreeView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1331a-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="1331a-105">연결 하 여 한 <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 개별 <xref:System.Windows.Forms.TreeNode> 항목, 사용자 지정 된 수준의 바로 가기 메뉴 기능을 추가할 수 있습니다 프로그램 <xref:System.Windows.Forms.TreeView> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="1331a-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1331a-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1331a-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1331a-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1331a-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1331a-108">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1331a-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a><span data-ttu-id="1331a-109">디자인 타임에 TreeNode에 바로 가기 메뉴를 연결할</span><span class="sxs-lookup"><span data-stu-id="1331a-109">To associate a shortcut menu with a TreeNode at design time</span></span>  
  
1.  <span data-ttu-id="1331a-110">추가 <xref:System.Windows.Forms.TreeView> 양식에 컨트롤을 다음에 노드 추가 <xref:System.Windows.Forms.TreeView> 필요에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="1331a-110">Add a <xref:System.Windows.Forms.TreeView> control to your form, and then add nodes to the <xref:System.Windows.Forms.TreeView> as needed.</span></span> <span data-ttu-id="1331a-111">자세한 내용은 참조 [하는 방법: Windows Forms TreeView 컨트롤에서 노드 추가 및 제거](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1331a-111">For more information, see [How to: Add and Remove Nodes with the Windows Forms TreeView Control](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span></span>  
  
2.  <span data-ttu-id="1331a-112">추가 <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 폼에 다음 실행 시 사용할 수 있도록 하려는 노드 수준의 작업을 나타내는 바로 가기 메뉴에 메뉴 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1331a-112">Add a <xref:System.Windows.Forms.ContextMenuStrip> component to your form, and then add menu items to the shortcut menu that represent node-level operations you wish to make available at run time.</span></span> <span data-ttu-id="1331a-113">자세한 내용은 참조 [하는 방법: ContextMenuStrip에 메뉴 항목 추가](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1331a-113">For more information, see [How to: Add Menu Items to a ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).</span></span>  
  
3.  <span data-ttu-id="1331a-114">다시 여세요는 **TreeNodeEditor** 에 대 한 대화 상자는 <xref:System.Windows.Forms.TreeView> 컨트롤을 편집 하 고 설정 노드를 선택 해당 <xref:System.Windows.Forms.ContextMenuStrip> 추가한 바로 가기 메뉴에는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1331a-114">Reopen the **TreeNodeEditor** dialog box for the <xref:System.Windows.Forms.TreeView> control, select the node to edit, and set its <xref:System.Windows.Forms.ContextMenuStrip> property to the shortcut menu that you added.</span></span>  
  
4.  <span data-ttu-id="1331a-115">이 속성이 설정 된 경우 바로 가기 메뉴에서 노드를 마우스 오른쪽 단추로 클릭할 때 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1331a-115">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
     <span data-ttu-id="1331a-116">또한 처리 하는 코드를 작성 하려면 됩니다는 <xref:System.Windows.Forms.ToolStripItem.Click> 이러한 새 메뉴 항목에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="1331a-116">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1331a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1331a-117">See Also</span></span>  
 [<span data-ttu-id="1331a-118">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1331a-118">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [<span data-ttu-id="1331a-119">TreeView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="1331a-119">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [<span data-ttu-id="1331a-120">ContextMenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1331a-120">ContextMenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
