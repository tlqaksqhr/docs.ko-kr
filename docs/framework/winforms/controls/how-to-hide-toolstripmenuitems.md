---
title: "방법: ToolStripMenuItems 숨기기"
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
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6f5491cfbfc312b2ce3e35170ddc4edc8ee39a61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="43fde-102">방법: ToolStripMenuItems 숨기기</span><span class="sxs-lookup"><span data-stu-id="43fde-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="43fde-103">메뉴 항목 숨기기는 응용 프로그램의 사용자 인터페이스를 제어 하 고 사용자 명령을 제한 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="43fde-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="43fde-104">종종 전체 메뉴에 메뉴 항목을 모두 사용할 수 없는 경우 숨길 합니다.</span><span class="sxs-lookup"><span data-stu-id="43fde-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="43fde-105">사용자에 대해 더 적은 방해 요소를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="43fde-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="43fde-106">또한 수 숨기고 메뉴 또는 메뉴 항목을 사용 하지 않도록 설정 대로 하려는 숨기는 것 만으로도 사용자 바로 가기 키를 사용 하 여 메뉴 명령에 액세스 하는 것을 금지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43fde-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="43fde-107">프로그래밍 방식으로 모든 메뉴 항목을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="43fde-107">To hide any menu item programmatically</span></span>  
  
-   <span data-ttu-id="43fde-108">메뉴 항목의 속성을 설정 하는 메서드를 추가 설정 하는 코드는 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 속성을 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="43fde-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="43fde-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43fde-109">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 [<span data-ttu-id="43fde-110">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="43fde-110">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="43fde-111">방법: ToolStripMenuItems 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="43fde-111">How to: Disable ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)
