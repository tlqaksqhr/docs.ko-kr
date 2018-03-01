---
title: "ContextMenu 구성 요소 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b0db67e8da97f380c3bb2eb9aab951628c4b6487
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="62669-102">ContextMenu 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="62669-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="62669-103">하지만 <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip> 대체 기능을 추가 하 고는 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 이전 버전의 컨트롤 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 선택 하는 경우 이전 버전과 호환성 및 이후 사용을 모두 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62669-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="62669-104">Windows forms <xref:System.Windows.Forms.ContextMenu> 구성 요소를 선택된 된 개체와 연결 된 자주 사용 되는 명령의 쉽게 액세스할 수 있는 바로 가기 메뉴를 가진 사용자가 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62669-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="62669-105">바로 가기 메뉴 항목은 자주 응용 프로그램에서 다른 곳에 나타나는 기본 메뉴 항목의 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="62669-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="62669-106">일반적으로 사용자의 마우스 오른쪽 단추로 클릭 하 여 바로 가기 메뉴를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62669-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="62669-107">Windows Forms에서 바로 가기 메뉴 컨트롤에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62669-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="62669-108">키 속성</span><span class="sxs-lookup"><span data-stu-id="62669-108">Key Properties</span></span>  
 <span data-ttu-id="62669-109">컨트롤의 설정 하 여 바로 가기 메뉴 컨트롤과 연결할 수 있습니다 <xref:System.Windows.Forms.Control.ContextMenu%2A> 속성을는 <xref:System.Windows.Forms.ContextMenu> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="62669-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="62669-110">단일 바로 가기 메뉴는 여러 컨트롤에 연결할 수 있지만 각 컨트롤 바로 가기 메뉴를 하나만 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62669-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="62669-111">키 속성은 <xref:System.Windows.Forms.ContextMenu> 구성 요소는는 <xref:System.Windows.Forms.Menu.MenuItems%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="62669-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="62669-112">프로그래밍 방식으로 작성 하 여 메뉴 항목을 추가할 수 있습니다 <xref:System.Windows.Forms.MenuItem> 개체에 추가 하는 <xref:System.Windows.Forms.Menu.MenuItemCollection> 바로 가기 메뉴의 합니다.</span><span class="sxs-lookup"><span data-stu-id="62669-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="62669-113">바로 가기 메뉴 항목에에서 일반적으로 다른 메뉴에서 가져온 것을 하기 때문에 가장 많이 추가 합니다 항목 바로 가기 메뉴에 복사 하 여.</span><span class="sxs-lookup"><span data-stu-id="62669-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62669-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62669-114">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenu>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>
