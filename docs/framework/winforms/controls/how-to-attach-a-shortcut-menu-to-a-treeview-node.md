---
title: "방법: TreeView 노드에 바로 가기 메뉴 연결"
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
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca251c9dec87db0ecb4b565b522839ace7f44479
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a><span data-ttu-id="fbee0-102">방법: TreeView 노드에 바로 가기 메뉴 연결</span><span class="sxs-lookup"><span data-stu-id="fbee0-102">How to: Attach a ShortCut Menu to a TreeView Node</span></span>
<span data-ttu-id="fbee0-103">Windows Forms <xref:System.Windows.Forms.TreeView> 제어에서 파일을 Windows 탐색기의 왼쪽된 창에 표시 되는 폴더 비슷한 노드 계층 구조를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbee0-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of Windows Explorer.</span></span> <span data-ttu-id="fbee0-104">설정 하 여는 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 제공할 수 있습니다 상황에 맞는 작업 사용자에 게 마우스 오른쪽 단추로 클릭 하 고 <xref:System.Windows.Forms.TreeView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbee0-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="fbee0-105">연결 하 여 한 <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 개별 <xref:System.Windows.Forms.TreeNode> 항목, 사용자 지정 된 수준의 바로 가기 메뉴 기능을 추가할 수 있습니다 프로그램 <xref:System.Windows.Forms.TreeView> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="fbee0-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a><span data-ttu-id="fbee0-106">TreeNode를 바로 가기 메뉴를 프로그래밍 방식으로 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="fbee0-106">To associate a shortcut menu with a TreeNode programmatically</span></span>  
  
1.  <span data-ttu-id="fbee0-107">인스턴스화하는 <xref:System.Windows.Forms.TreeView> 적절 한 속성 설정을 사용 하 여 제어 하 고, 루트 만들기 <xref:System.Windows.Forms.TreeNode>, 다음 하위 노드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbee0-107">Instantiate a <xref:System.Windows.Forms.TreeView> control with the appropriate property settings, create a root <xref:System.Windows.Forms.TreeNode>, and then add subnodes.</span></span>  
  
2.  <span data-ttu-id="fbee0-108">인스턴스화하는 <xref:System.Windows.Forms.ContextMenuStrip> 구성 요소를 한 다음 추가 <xref:System.Windows.Forms.ToolStripMenuItem> 실행 시 사용할 수 있도록 설정할 각 작업에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbee0-108">Instantiate a <xref:System.Windows.Forms.ContextMenuStrip> component, and then add a <xref:System.Windows.Forms.ToolStripMenuItem> for each operation you want to make available at run time.</span></span>  
  
3.  <span data-ttu-id="fbee0-109">설정의 <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> 적절 한 속성 <xref:System.Windows.Forms.TreeNode> 만들면 바로 가기 메뉴에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbee0-109">Set the <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> property of the appropriate <xref:System.Windows.Forms.TreeNode> to the shortcut menu you create.</span></span>  
  
4.  <span data-ttu-id="fbee0-110">이 속성이 설정 된 경우 바로 가기 메뉴에서 노드를 마우스 오른쪽 단추로 클릭할 때 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbee0-110">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
 <span data-ttu-id="fbee0-111">다음 코드 예제에서는 기본 <xref:System.Windows.Forms.TreeView> 및 <xref:System.Windows.Forms.ContextMenuStrip> 루트와 연결 된 <xref:System.Windows.Forms.TreeNode> 의 <xref:System.Windows.Forms.TreeView>합니다.</span><span class="sxs-lookup"><span data-stu-id="fbee0-111">The following code example creates a basic <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ContextMenuStrip> associated with the root <xref:System.Windows.Forms.TreeNode> of the <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="fbee0-112">메뉴 선택 맞게 사용자 지정 해야 합니다는 <xref:System.Windows.Forms.TreeView> 개발 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbee0-112">You will need to customize the menu choices to those that fit the <xref:System.Windows.Forms.TreeView> you are developing.</span></span> <span data-ttu-id="fbee0-113">또한 처리 하는 코드를 작성 하려면 됩니다는 <xref:System.Windows.Forms.ToolStripItem.Click> 이러한 새 메뉴 항목에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="fbee0-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fbee0-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbee0-114">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [<span data-ttu-id="fbee0-115">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fbee0-115">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
