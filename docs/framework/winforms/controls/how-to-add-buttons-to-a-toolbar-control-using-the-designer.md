---
title: "방법: 디자이너를 사용하여 ToolBar 컨트롤에 단추 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ccd63cb88661db7601b87eec6bdf3a959afb8bbf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a><span data-ttu-id="a2162-102">방법: 디자이너를 사용하여 ToolBar 컨트롤에 단추 추가</span><span class="sxs-lookup"><span data-stu-id="a2162-102">How to: Add Buttons to a ToolBar Control Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="a2162-103"><xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ToolBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="a2162-104">핵심은 <xref:System.Windows.Forms.ToolBar> 컨트롤은 단추를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-104">An integral part of the <xref:System.Windows.Forms.ToolBar> control is the buttons you add to it.</span></span> <span data-ttu-id="a2162-105">또는 메뉴 명령에 쉽게 액세스할을 사용할 수 있습니다 이러한 또는 명령을 메뉴 구조에서 사용할 수 없는 사용자에 게 노출 하는 응용 프로그램의 사용자 인터페이스의 다른 영역에 배치 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-105">These can be used to provide easy access to menu commands or, alternately, they can be placed in another area of the user interface of your application to expose commands to your users that are not available in the menu structure.</span></span>  
  
 <span data-ttu-id="a2162-106">다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.ToolBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control.</span></span> <span data-ttu-id="a2162-107">이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-107">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2162-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a2162-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a2162-110">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2162-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-buttons-at-design-time"></a><span data-ttu-id="a2162-111">디자인 타임에 단추를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="a2162-111">To add buttons at design time</span></span>  
  
1.  <span data-ttu-id="a2162-112"><xref:System.Windows.Forms.ToolBar> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-112">Select the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
2.  <span data-ttu-id="a2162-113">에 **속성** 창 클릭는 <xref:System.Windows.Forms.ToolBar.Buttons%2A> 속성을 선택 하 고 클릭는 **줄임표** (![VisualStudioEllipsesButton 스크린 샷] (../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) 버튼을 클릭은 **ToolBarButton 컬렉션 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-113">In the **Properties** window, click the <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it and click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **ToolBarButton Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="a2162-114">사용 하 여는 **추가** 및 **제거** 단추에서 추가 하거나 제거 하는 단추는 <xref:System.Windows.Forms.ToolBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-114">Use the **Add** and **Remove** buttons to add and remove buttons from the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
4.  <span data-ttu-id="a2162-115">에 있는 개별 단추의 속성을 구성에서 **속성** 편집기의 오른쪽에 있는 창에 나타나는 창입니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-115">Configure the properties of the individual buttons in the **Properties** window that appears in the pane on the right side of the editor.</span></span> <span data-ttu-id="a2162-116">다음 표에서 고려해 야 할 몇 가지 중요 한 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-116">The following table shows some important properties to consider.</span></span>  
  
    |<span data-ttu-id="a2162-117">속성</span><span class="sxs-lookup"><span data-stu-id="a2162-117">Property</span></span>|<span data-ttu-id="a2162-118">설명</span><span class="sxs-lookup"><span data-stu-id="a2162-118">Description</span></span>|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|<span data-ttu-id="a2162-119">드롭다운 목록 도구 모음 단추에 표시할 메뉴를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-119">Sets the menu to be displayed in the drop-down toolbar button.</span></span> <span data-ttu-id="a2162-120">도구 모음 단추 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 속성으로 설정 되어 있어야 <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>합니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-120">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>.</span></span> <span data-ttu-id="a2162-121">이 속성의 인스턴스를 사용 하는 <xref:System.Windows.Forms.ContextMenu> 클래스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-121">This property takes an instance of the <xref:System.Windows.Forms.ContextMenu> class as a reference.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|<span data-ttu-id="a2162-122">토글 스타일 도구 모음 단추 부분적으로 눌린 있는지 여부를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-122">Sets whether a toggle-style toolbar button is partially pushed.</span></span> <span data-ttu-id="a2162-123">도구 모음 단추 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 속성으로 설정 되어 있어야 <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>합니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-123">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|<span data-ttu-id="a2162-124">토글 스타일 도구 모음 단추 현재 푸시된 상태에 있는지 여부를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-124">Sets whether a toggle-style toolbar button is currently in the pushed state.</span></span> <span data-ttu-id="a2162-125">도구 모음 단추 <xref:System.Windows.Forms.ToolBarButton.Style%2A> 속성으로 설정 되어 있어야 <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> 또는 <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>합니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-125">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> or <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|<span data-ttu-id="a2162-126">도구 모음 단추 스타일을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-126">Sets the style of the toolbar button.</span></span> <span data-ttu-id="a2162-127">값 중 하나 여야 합니다는 <xref:System.Windows.Forms.ToolBarButtonStyle> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-127">Must be one of the values in the <xref:System.Windows.Forms.ToolBarButtonStyle> enumeration.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|<span data-ttu-id="a2162-128">단추에 표시 되는 텍스트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-128">The text string displayed by the button.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|<span data-ttu-id="a2162-129">단추의 도구 설명으로 표시 되는 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-129">The text that appears as a ToolTip for the button.</span></span>|  
  
5.  <span data-ttu-id="a2162-130">클릭 **확인** 을 대화 상자를 닫고을 지정한 패널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a2162-130">Click **OK** to close the dialog box and create the panels you specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2162-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2162-131">See Also</span></span>  
 <xref:System.Windows.Forms.ToolBar>  
 [<span data-ttu-id="a2162-132">방법: ToolBar 단추의 아이콘 정의</span><span class="sxs-lookup"><span data-stu-id="a2162-132">How to: Define an Icon for a ToolBar Button</span></span>](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 [<span data-ttu-id="a2162-133">방법: Toolbar 단추의 메뉴 이벤트 트리거</span><span class="sxs-lookup"><span data-stu-id="a2162-133">How to: Trigger Menu Events for Toolbar Buttons</span></span>](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [<span data-ttu-id="a2162-134">ToolBar 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="a2162-134">ToolBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 [<span data-ttu-id="a2162-135">ToolBar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a2162-135">ToolBar Control</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)
