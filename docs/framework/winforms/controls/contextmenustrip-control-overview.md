---
title: "ContextMenuStrip 컨트롤 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ContextMenuStrip
helpviewer_keywords:
- context menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- shortcut menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- ContextMenuStrip control [Windows Forms], about ContextMenuStrip control
ms.assetid: 9787cdb3-88f1-4198-972f-eefd9524ce39
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 11d5de760b8a03d7bc35adabb631048a70e20264
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="contextmenustrip-control-overview"></a><span data-ttu-id="3d076-102">ContextMenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="3d076-102">ContextMenuStrip Control Overview</span></span>
> [!NOTE]
>  <span data-ttu-id="3d076-103">그러나 <xref:System.Windows.Forms.ContextMenuStrip> 대체 하 고 여기에 새로운 기능이 추가 된 <xref:System.Windows.Forms.ContextMenu> 컨트롤는 <xref:System.Windows.Forms.ContextMenu> 컨트롤을 선택 하는 경우 이전 버전과 호환성 및 이후 사용에 대 한 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d076-103">The <xref:System.Windows.Forms.ContextMenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> control; however, the <xref:System.Windows.Forms.ContextMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="3d076-104">상황에 맞는 메뉴 라고도 하는 바로 가기 메뉴를 마우스 오른쪽 단추를 클릭할 때 마우스 위치에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3d076-104">Shortcut menus, also called context menus, appear at the mouse position when the user clicks the right mouse button.</span></span> <span data-ttu-id="3d076-105">바로 가기 *메뉴* 클라이언트 영역 또는 마우스 포인터 위치에 있는 컨트롤에 대 한 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d076-105">Shortcut *menus* provide options for the client area or the control at the mouse pointer location.</span></span>  
  
 <span data-ttu-id="3d076-106"><xref:System.Windows.Forms.ContextMenuStrip> 컨트롤은 새 매끄럽게 작동 하도록 설계 되었습니다 <xref:System.Windows.Forms.ToolStrip> 있지만 관련 된 컨트롤에 연결할 수는 <xref:System.Windows.Forms.ContextMenuStrip> 쉽게 다른 제어 기능과 함께 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d076-106">The <xref:System.Windows.Forms.ContextMenuStrip> control is designed to work seamlessly with the new <xref:System.Windows.Forms.ToolStrip> and related controls, but you can associate a <xref:System.Windows.Forms.ContextMenuStrip> with other controls just as easily.</span></span>  
  
 <span data-ttu-id="3d076-107">다음 표에서 중요 한 <xref:System.Windows.Forms.ContextMenuStrip> 도우미 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3d076-107">The following table shows the important <xref:System.Windows.Forms.ContextMenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="3d076-108">클래스</span><span class="sxs-lookup"><span data-stu-id="3d076-108">Class</span></span>|<span data-ttu-id="3d076-109">설명</span><span class="sxs-lookup"><span data-stu-id="3d076-109">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="3d076-110">에 표시 된 선택 가능한 옵션을 나타냅니다는 <xref:System.Windows.Forms.MenuStrip> 또는 <xref:System.Windows.Forms.ContextMenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="3d076-110">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="3d076-111">사용자는 사용자가 클릭할 때 표시 되는 목록에서 단일 항목을 선택할 수 있도록 하는 컨트롤을 나타냅니다는 <xref:System.Windows.Forms.ToolStripDropDownButton> 또는 더 높은 수준의 메뉴 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="3d076-111">Represents a control that enables the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="3d076-112">파생 된 컨트롤에 대 한 기본 기능을 제공 <xref:System.Windows.Forms.ToolStripItem> 클릭 하면 드롭다운 항목을 표시 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d076-112">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d076-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d076-113">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
