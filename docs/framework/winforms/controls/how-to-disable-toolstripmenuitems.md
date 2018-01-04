---
title: "방법: ToolStripMenuItems 사용 안 함"
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
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0432c59979f8f595b481154f5b339e448ee66b06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="f0c75-102">방법: ToolStripMenuItems 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="f0c75-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="f0c75-103">제한 하거나 사용자의 동작에 대 한 응답으로 메뉴 항목을 설정 하거나 해제 하 여 사용자가 수행 하는 명령을 넓힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c75-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="f0c75-104">메뉴 항목은 기본적으로 활성화 만들어질 때 통해 조정할 수 있습니다는 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c75-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="f0c75-105">디자인 타임에이 속성을 조작할 수 있습니다는 **속성** 창 또는 코드에서 설정 하 여 프로그래밍 방식으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c75-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="f0c75-106">메뉴 항목을 프로그래밍 방식으로 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="f0c75-106">To disable a menu item programmatically</span></span>  
  
-   <span data-ttu-id="f0c75-107">메뉴 항목의 속성을 설정 하는 메서드를 추가 설정 하는 코드는 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> 속성을 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c75-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="f0c75-108">메뉴의 첫 번째 또는 최상위 메뉴 항목을 사용 하지 않도록 설정 메뉴에서 내에 포함 된 모든 메뉴 항목 숨겨지지만 비활성화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c75-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="f0c75-109">마찬가지로, 하위 메뉴 항목이 포함 된 메뉴 항목을 비활성화 하면 하위 메뉴 항목을 숨깁니다 하지만 비활성화 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c75-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="f0c75-110">메뉴의 모든 명령을 사용자에 게 사용할 수 없을 경우이 인해 사용자 인터페이스를 명확 하는 대로 숨기고 전체 메뉴를 사용 하지 않도록 설정 하는 바람직한 프로그래밍 관행을 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c75-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="f0c75-111">숨기기 및 메뉴를 사용 하지 않도록 설정 하 고 숨기기만 하더라도 사용자는 바로 가기 키를 통해 메뉴 명령에 액세스 하기 때문에 모든 항목과 하위 메뉴 항목 메뉴를 사용 하지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c75-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="f0c75-112">설정의 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 에 최상위 메뉴 항목의 `false` 전체 메뉴를 숨기 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c75-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c75-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0c75-113">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="f0c75-114">방법: ToolStripMenuItems 숨기기</span><span class="sxs-lookup"><span data-stu-id="f0c75-114">How to: Hide ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [<span data-ttu-id="f0c75-115">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="f0c75-115">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
