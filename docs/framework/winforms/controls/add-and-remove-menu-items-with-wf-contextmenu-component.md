---
title: "방법: Windows Forms ContextMenu 구성 요소를 사용하여 메뉴 항목 추가 및 제거"
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
- context menus [Windows Forms], removing items
- ContextMenu component [Windows Forms], adding items
- shortcut menus [Windows Forms], removing items
- shortcut menus [Windows Forms], examples
- context menus [Windows Forms], adding items
- shortcut menus [Windows Forms], adding items
- ContextMenu component [Windows Forms], removing items
- context menus [Windows Forms], examples
- examples [Windows Forms], context menus
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2f3ca6f97049e0519243915856702654b924243
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a><span data-ttu-id="b6c6b-102">방법: Windows Forms ContextMenu 구성 요소를 사용하여 메뉴 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="b6c6b-102">How to: Add and Remove Menu Items with the Windows Forms ContextMenu Component</span></span>
<span data-ttu-id="b6c6b-103">추가 Windows Forms의 바로 가기 메뉴 항목을 제거 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6c6b-103">Explains how to add and remove shortcut menu items in Windows Forms.</span></span>  
  
 <span data-ttu-id="b6c6b-104">Windows Forms <xref:System.Windows.Forms.ContextMenu> 구성 요소는 선택한 개체에 관련 된 자주 사용 되는 명령 메뉴를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6c6b-104">The Windows Forms <xref:System.Windows.Forms.ContextMenu> component provides a menu of frequently used commands that are relevant to the selected object.</span></span> <span data-ttu-id="b6c6b-105">바로 가기 메뉴에 추가 하 여 항목을 추가할 수 있습니다 <xref:System.Windows.Forms.MenuItem> 개체는 <xref:System.Windows.Forms.Menu.MenuItems%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b6c6b-105">You can add items to the shortcut menu by adding <xref:System.Windows.Forms.MenuItem> objects to the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection.</span></span>  
  
 <span data-ttu-id="b6c6b-106">영구적으로; 바로 가기 메뉴에서 항목을 제거할 수 있습니다. 그러나 런타임 시 수 있습니다 더 적절 한을 숨기 거 나 항목을 대신 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6c6b-106">You can remove items from a shortcut menu permanently; however, at run time it may be more appropriate to hide or disable the items instead.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b6c6b-107">하지만 <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip> 대체 기능을 추가 하 고는 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 이전 버전의 컨트롤 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 선택 하는 경우 이전 버전과 호환성 및 이후 사용을 모두 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6c6b-107">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a><span data-ttu-id="b6c6b-108">바로 가기 메뉴에서 항목을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="b6c6b-108">To remove items from a shortcut menu</span></span>  
  
1.  <span data-ttu-id="b6c6b-109">사용 하 여는 <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> 또는 <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> 의 메서드는 <xref:System.Windows.Forms.Menu.MenuItems%2A> 의 컬렉션은 <xref:System.Windows.Forms.ContextMenu> 특정 메뉴 항목을 제거 하려면 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b6c6b-109">Use the <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> or <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection of the <xref:System.Windows.Forms.ContextMenu> component to remove a particular menu item.</span></span>  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     <span data-ttu-id="b6c6b-110">또는</span><span class="sxs-lookup"><span data-stu-id="b6c6b-110">-or-</span></span>  
  
2.  <span data-ttu-id="b6c6b-111">사용 하 여는 `Clear` 의 메서드는 `MenuItems` 의 컬렉션은 <xref:System.Windows.Forms.ContextMenu> 메뉴에서 모든 항목을 제거 하려면 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b6c6b-111">Use the `Clear` method of the `MenuItems` collection of the <xref:System.Windows.Forms.ContextMenu> component to remove all items from the menu.</span></span>  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b6c6b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6c6b-112">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenu>  
 [<span data-ttu-id="b6c6b-113">ContextMenu 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b6c6b-113">ContextMenu Component</span></span>](../../../../docs/framework/winforms/controls/contextmenu-component-windows-forms.md)  
 [<span data-ttu-id="b6c6b-114">ContextMenu 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="b6c6b-114">ContextMenu Component Overview</span></span>](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)
