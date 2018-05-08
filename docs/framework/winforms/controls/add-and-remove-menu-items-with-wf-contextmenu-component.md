---
title: '방법: Windows Forms ContextMenu 구성 요소를 사용하여 메뉴 항목 추가 및 제거'
ms.date: 03/30/2017
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
ms.openlocfilehash: 7cc11eaf4a671c76933c2705b41a4df6c35c0536
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a>방법: Windows Forms ContextMenu 구성 요소를 사용하여 메뉴 항목 추가 및 제거
추가 Windows Forms의 바로 가기 메뉴 항목을 제거 하는 방법에 설명 합니다.  
  
 Windows Forms <xref:System.Windows.Forms.ContextMenu> 구성 요소는 선택한 개체에 관련 된 자주 사용 되는 명령 메뉴를 제공 합니다. 바로 가기 메뉴에 추가 하 여 항목을 추가할 수 있습니다 <xref:System.Windows.Forms.MenuItem> 개체는 <xref:System.Windows.Forms.Menu.MenuItems%2A> 컬렉션입니다.  
  
 영구적으로; 바로 가기 메뉴에서 항목을 제거할 수 있습니다. 그러나 런타임 시 수 있습니다 더 적절 한을 숨기 거 나 항목을 대신 사용 하지 않도록 설정 합니다.  
  
> [!IMPORTANT]
>  하지만 <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip> 대체 기능을 추가 하 고는 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 이전 버전의 컨트롤 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 선택 하는 경우 이전 버전과 호환성 및 이후 사용을 모두 유지 됩니다.  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a>바로 가기 메뉴에서 항목을 제거 하려면  
  
1.  사용 하 여는 <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> 또는 <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> 의 메서드는 <xref:System.Windows.Forms.Menu.MenuItems%2A> 의 컬렉션은 <xref:System.Windows.Forms.ContextMenu> 특정 메뉴 항목을 제거 하려면 구성 요소입니다.  
  
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
  
     또는  
  
2.  사용 하 여는 `Clear` 의 메서드는 `MenuItems` 의 컬렉션은 <xref:System.Windows.Forms.ContextMenu> 메뉴에서 모든 항목을 제거 하려면 구성 요소입니다.  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ContextMenu>  
 [ContextMenu 구성 요소](../../../../docs/framework/winforms/controls/contextmenu-component-windows-forms.md)  
 [ContextMenu 구성 요소 개요](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)
