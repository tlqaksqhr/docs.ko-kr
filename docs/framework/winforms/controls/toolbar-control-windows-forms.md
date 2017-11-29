---
title: "ToolBar 컨트롤(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolBar control [Windows Forms]
ms.assetid: 6b40e9ce-6a7a-4784-bfc9-7f1d36b7462e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18fc87d4ebccd101bec47abd39805746d0b9ef81
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="toolbar-control-windows-forms"></a><span data-ttu-id="66986-102">ToolBar 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="66986-102">ToolBar Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="66986-103"><xref:System.Windows.Forms.ToolStrip> 컨트롤은 `ToolBar` 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 `ToolBar` 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66986-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the `ToolBar` control; however, the `ToolBar` control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="66986-104">Windows Forms `ToolBar` 컨트롤은 폼에서 드롭다운 메뉴 및 명령을 활성화하는 비트맵 단추가 포함된 한 행을 표시하는 컨트롤 막대로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66986-104">The Windows Forms `ToolBar` control is used on forms as a control bar that displays a row of drop-down menus and bitmapped buttons that activate commands.</span></span> <span data-ttu-id="66986-105">따라서 도구 모음 단추 클릭은 메뉴 명령을 선택하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66986-105">Thus, clicking a toolbar button is equivalent to choosing a menu command.</span></span> <span data-ttu-id="66986-106">단추는 누름 단추, 드롭다운 메뉴 또는 구분 기호로 표시 및 동작하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66986-106">The buttons can be configured to appear and behave as push buttons, drop-down menus, or separators.</span></span> <span data-ttu-id="66986-107">일반적으로 도구 모음에는 응용 프로그램 메뉴 구조의 항목에 해당하는 단추 및 메뉴가 포함되며, 응용 프로그램에서 자주 사용되는 함수 및 명령에 대한 빠른 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="66986-107">Typically, a toolbar contains buttons and menus that correspond to items in an application's menu structure, providing quick access to an application's most frequently used functions and commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66986-108">`ToolBar` 컨트롤의 <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> 속성은 <xref:System.Windows.Forms.ContextMenu> 클래스의 인스턴스를 참조로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66986-108">The `ToolBar` control's <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> property takes an instance of the <xref:System.Windows.Forms.ContextMenu> class as a reference.</span></span> <span data-ttu-id="66986-109">이 속성은 <xref:System.Windows.Forms.Menu> 클래스에서 상속되는 모든 개체를 수락하므로 응용 프로그램의 도구 모음에 이러한 종류의 단추를 구현할 때는 전달하는 참조를 신중하게 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="66986-109">Carefully consider the reference you pass when implementing this sort of button on toolbars in your application, as the property will accept any object that inherits from the <xref:System.Windows.Forms.Menu> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66986-110">단원 내용</span><span class="sxs-lookup"><span data-stu-id="66986-110">In This Section</span></span>  
 [<span data-ttu-id="66986-111">ToolBar 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="66986-111">ToolBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 <span data-ttu-id="66986-112">사용자가 사용할 수 있는 사용자 지정 도구 모음을 디자인할 수 있게 해주는 `ToolBar` 컨트롤의 일반적인 개념을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="66986-112">Introduces the general concepts of the `ToolBar` control, which allows you to design custom toolbars that your users can work with.</span></span>  
  
 [<span data-ttu-id="66986-113">방법: ToolBar 컨트롤에 단추 추가</span><span class="sxs-lookup"><span data-stu-id="66986-113">How to: Add Buttons to a ToolBar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)  
 <span data-ttu-id="66986-114">`ToolBar` 컨트롤에 단추를 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="66986-114">Describes how to add buttons to a `ToolBar` control.</span></span>  
  
 [<span data-ttu-id="66986-115">방법: ToolBar 단추의 아이콘 정의</span><span class="sxs-lookup"><span data-stu-id="66986-115">How to: Define an Icon for a ToolBar Button</span></span>](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 <span data-ttu-id="66986-116">`ToolBar` 컨트롤의 단추 내에 아이콘을 표시하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="66986-116">Describes how to display icons within a `ToolBar` control's buttons.</span></span>  
  
 [<span data-ttu-id="66986-117">방법: Toolbar 단추의 메뉴 이벤트 트리거</span><span class="sxs-lookup"><span data-stu-id="66986-117">How to: Trigger Menu Events for Toolbar Buttons</span></span>](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 <span data-ttu-id="66986-118">사용자가 `ToolBar` 컨트롤에서 클릭하는 단추를 해석하는 코드를 작성하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="66986-118">Gives directions on writing code to interpret which button the user clicks in a `ToolBar` control.</span></span>  
  
 <span data-ttu-id="66986-119">또한 참조 [하는 방법:는 도구 모음 단추를 사용 하 여 디자이너에 대 한 아이콘을 정의](http://msdn.microsoft.com/library/ms233659\(v=vs.110\)), [하는 방법: 도구 모음 컨트롤 사용 하는 디자이너에 단추 추가](http://msdn.microsoft.com/library/ms233650\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="66986-119">Also see [How to: Define an Icon for a ToolBar Button Using the Designer](http://msdn.microsoft.com/library/ms233659\(v=vs.110\)), [How to: Add Buttons to a ToolBar Control Using the Designer](http://msdn.microsoft.com/library/ms233650\(v=vs.110\)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="66986-120">참조</span><span class="sxs-lookup"><span data-stu-id="66986-120">Reference</span></span>  
 <span data-ttu-id="66986-121"><xref:System.Windows.Forms.ToolBar> 클래스</span><span class="sxs-lookup"><span data-stu-id="66986-121"><xref:System.Windows.Forms.ToolBar> class</span></span>  
 <span data-ttu-id="66986-122">클래스 및 해당 멤버에 대한 참조 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="66986-122">Provides reference information on the class and its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="66986-123">관련 단원</span><span class="sxs-lookup"><span data-stu-id="66986-123">Related Sections</span></span>  
 [<span data-ttu-id="66986-124">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="66986-124">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="66986-125">사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="66986-125">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="66986-126">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="66986-126">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 <span data-ttu-id="66986-127">Windows Forms 응용 프로그램에서 메뉴, 컨트롤 및 사용자 정의 컨트롤을 호스트할 수 있는 도구 모음을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="66986-127">Describes toolbars that can host menus, controls, and user controls in Windows Forms applications.</span></span>
