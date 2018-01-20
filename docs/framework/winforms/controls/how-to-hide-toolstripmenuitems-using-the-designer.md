---
title: "방법: 디자이너를 사용하여 ToolStripMenuItems 숨기기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 06a95581e156a7027c8fa0bda6e5fbc4babdb85b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="bfb74-102">방법: 디자이너를 사용하여 ToolStripMenuItems 숨기기</span><span class="sxs-lookup"><span data-stu-id="bfb74-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="bfb74-103">메뉴 항목 숨기기는 응용 프로그램의 사용자 인터페이스 (UI)를 제어 하 고 사용자 명령을 제한 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb74-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="bfb74-104">종종 전체 메뉴에 메뉴 항목을 모두 사용할 수 없는 경우 숨길 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb74-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="bfb74-105">사용자에 대해 더 적은 방해 요소를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb74-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="bfb74-106">또한 수 숨기고 메뉴 또는 메뉴 항목을 사용 하지 않도록 설정 대로 하려는 숨기는 것 만으로도 사용자 바로 가기 키를 사용 하 여 메뉴 명령에 액세스 하는 것을 금지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb74-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="bfb74-107">메뉴 항목을 사용 하지 않도록 설정에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 디자이너를 사용 하 여 ToolStripMenuItems 사용 안 함](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb74-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfb74-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb74-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bfb74-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb74-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bfb74-110">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bfb74-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="bfb74-111">최상위 메뉴와 해당 하위 메뉴 항목을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="bfb74-111">To hide a top-level menu and its submenu items</span></span>  
  
1.  <span data-ttu-id="bfb74-112">최상위 메뉴 항목을 선택 하 고 설정의 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 또는 <xref:System.Windows.Forms.ToolStripItem.Available%2A> 속성을 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb74-112">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="bfb74-113">최상위 메뉴 항목을 숨길 때 해당 메뉴 내의 모든 메뉴 항목 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="bfb74-113">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="bfb74-114">아닌 다른 위치를 클릭 하면는 <xref:System.Windows.Forms.MenuStrip> 설정한 후 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 를 `false`, 전체 최상위 메뉴 항목 및 해당 하위 메뉴 항목 따라서 액션의 실행 시간 효과 표시 폼에서 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="bfb74-114">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="bfb74-115">디자인 타임에 최상위 메뉴 숨겨진된 항목을 표시 하려면 클릭는 <xref:System.Windows.Forms.MenuStrip> 에 **구성 요소 트레이**에 **문서 개요**, 또는 속성 표의 맨 위에 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb74-115">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfb74-116">전체 메뉴 병합 시나리오에서 여러 문서 MDI (인터페이스) 자식 메뉴를 제외한 거의 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="bfb74-116">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>  
  
### <a name="to-hide-a-submenu-item"></a><span data-ttu-id="bfb74-117">하위 메뉴 항목을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="bfb74-117">To hide a submenu item</span></span>  
  
1.  <span data-ttu-id="bfb74-118">하위 메뉴 항목을 선택 하 고 설정의 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 속성을 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb74-118">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="bfb74-119">하위 메뉴 항목을 숨길 때 쉽게 추가 작업을 위해 선택할 수 있도록 디자인 타임에 폼에 표시 되 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfb74-119">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="bfb74-120">런타임 시 실제로 표시지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb74-120">It will actually be hidden at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfb74-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfb74-121">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [<span data-ttu-id="bfb74-122">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="bfb74-122">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="bfb74-123">방법: 디자이너를 사용하여 ToolStripMenuItems를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="bfb74-123">How to: Disable ToolStripMenuItems Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)
