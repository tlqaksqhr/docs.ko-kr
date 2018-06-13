---
title: MainMenu 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: a7ea9fcf25942f21d2d549ea998161398fbc608f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534214"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="95735-102">MainMenu 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="95735-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="95735-103">하지만 <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip> 대체 기능을 추가 하 고는 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 이전 버전의 컨트롤 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 선택 하는 경우 이전 버전과 호환성 및 이후 사용을 모두 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95735-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="95735-104">Windows Forms <xref:System.Windows.Forms.MainMenu> 런타임 시 구성 요소에 메뉴가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95735-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="95735-105">주 메뉴 및 개별 항목의 모든 하위 메뉴는 <xref:System.Windows.Forms.MenuItem> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="95735-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="95735-106">키 속성</span><span class="sxs-lookup"><span data-stu-id="95735-106">Key Properties</span></span>  
 <span data-ttu-id="95735-107">메뉴 항목을 설정 하 여 기본 항목으로 지정 될 수 있습니다는 <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="95735-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="95735-108">메뉴를 클릭 하면 기본 항목이 굵은 텍스트로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="95735-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="95735-109">메뉴 항목의 <xref:System.Windows.Forms.MenuItem.Checked%2A> 속성이 `true` 또는 `false`, 메뉴 항목이 선택 되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="95735-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="95735-110">메뉴 항목의 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 속성에서 선택한 항목의 모양을 사용자 지정: 경우 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 로 설정 되어 `true`, 경우 항목; 옆에 표시 되는 라디오 단추 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 로 설정 된 `false`, 항목 옆에 확인 표시가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="95735-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95735-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95735-111">See Also</span></span>  
 <xref:System.Windows.Forms.MainMenu>  
 <xref:System.Windows.Forms.Menu>  
 <xref:System.Windows.Forms.MenuItem>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [<span data-ttu-id="95735-112">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="95735-112">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
