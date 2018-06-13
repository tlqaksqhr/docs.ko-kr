---
title: '방법: 디자이너를 사용하여 ToolStripMenuItems를 사용하지 않도록 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: 3ce18d40910145a076cc7084e2fba8ee0229c21f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531556"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="f474b-102">방법: 디자이너를 사용하여 ToolStripMenuItems를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="f474b-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="f474b-103">제한 하거나 사용자의 동작에 대 한 응답으로 메뉴 항목을 설정 하거나 해제 하 여 사용자가 수행 하는 명령을 넓힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f474b-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="f474b-104">메뉴 항목은 기본적으로 활성화 만들어질 때 통해 조정할 수 있습니다는 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f474b-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="f474b-105">디자인 타임에이 속성을 조작할 수 있습니다는 **속성** 창 또는 코드에서 설정 하 여 프로그래밍 방식으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f474b-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="f474b-106">자세한 내용은 참조 [하는 방법: ToolStripMenuItems 사용 안 함](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f474b-106">For more information, see [How to: Disable ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f474b-107">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f474b-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f474b-108">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f474b-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f474b-109">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f474b-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="f474b-110">디자인 타임에 메뉴 항목을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="f474b-110">To disable a menu item at design time</span></span>  
  
1.  <span data-ttu-id="f474b-111">폼에서 선택한 메뉴 항목을 사용 하 여 설정할는 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="f474b-111">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="f474b-112">메뉴에 포함 된 모든 메뉴 항목을 해제 메뉴의 첫 번째 또는 최상위 메뉴 항목을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f474b-112">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="f474b-113">마찬가지로, 하위 메뉴 항목이 해제 하위 메뉴 항목이 포함 된 메뉴 항목을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f474b-113">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="f474b-114">메뉴의 모든 명령을 사용자에 게 사용할 수 없을 경우이 인해 사용자 인터페이스를 명확 하는 대로 숨기고 전체 메뉴를 사용 하지 않도록 설정 하는 바람직한 프로그래밍 관행을 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f474b-114">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="f474b-115">숨기기와 숨기는 것 만으로도 바로 가기 키를 통해 메뉴 명령에 액세스 하지 않는 메뉴를 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f474b-115">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="f474b-116">설정의 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 에 최상위 메뉴 항목의 `false` 전체 메뉴를 숨기 합니다.</span><span class="sxs-lookup"><span data-stu-id="f474b-116">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f474b-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f474b-117">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="f474b-118">방법: ToolStripMenuItems 숨기기</span><span class="sxs-lookup"><span data-stu-id="f474b-118">How to: Hide ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [<span data-ttu-id="f474b-119">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="f474b-119">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
