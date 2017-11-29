---
title: "방법: ToolStripMenuItems에 향상된 기능 추가"
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
helpviewer_keywords:
- commands [Windows Forms], grouping on menus
- check marks [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], displaying access keys
- menus [Windows Forms], grouping commands
- menu items [Windows Forms], displaying shortcut keys
- ToolStripMenuItems
- separators [Windows Forms], displaying on menus
- menu items [Windows Forms], showing separators
- menu items [Windows Forms], adding check marks
- ToolStripMenuItems [Windows Forms], adding check marks
- menu items [Windows Forms], adding images
- ToolStripSeparators [Windows Forms], displaying on MenuStrips
- menu items [Windows Forms], displaying access keys
- ToolStripMenuItems [Windows Forms], displaying shortcut keys
- ToolStripMenuItems [Windows Forms], adding images
- keyboard shortcuts [Windows Forms], displaying on menus
- images [Windows Forms], adding to menus
- ToolStripMenuItems [Windows Forms], showing separator bars
ms.assetid: aa5f19bb-b545-4378-bfa6-36ba592f0d7c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2701094ffcbcf7eeb14444163b995816398876fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-enhancements-to-toolstripmenuitems"></a><span data-ttu-id="01965-102">방법: ToolStripMenuItems에 향상된 기능 추가</span><span class="sxs-lookup"><span data-stu-id="01965-102">How to: Add Enhancements to ToolStripMenuItems</span></span>
<span data-ttu-id="01965-103">유용성을 향상 시킬 수 있습니다 <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip> 다음과 같은 방법으로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="01965-103">You can enhance the usability of <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> controls in the following ways:</span></span>  
  
-   <span data-ttu-id="01965-104">확인 표시는 눈금자 워드 프로세서의 여백 표시 되는지 여부와 같은 설정 / 해제는 기능이 설정 되어 있는지 여부를 지정 하거나 되는 파일의 파일 목록에 표시 되는 등에서 다음으로 나타내려면 추가 **창** 메뉴입니다.</span><span class="sxs-lookup"><span data-stu-id="01965-104">Add check marks to designate whether a feature is turned on or off, such as whether a ruler is displayed along the margin of a word-processing application, or to indicate which file in a list of files is being displayed, such as on a **Window** menu.</span></span>  
  
-   <span data-ttu-id="01965-105">메뉴 명령에 시각적으로 나타내는 이미지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="01965-105">Add images that visually represent menu commands.</span></span>  
  
-   <span data-ttu-id="01965-106">명령을 수행 하기 위한 마우스에 키보드 대신 사용할 수 있도록 바로 가기 키를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="01965-106">Display shortcut keys to provide a keyboard alternative to the mouse for performing commands.</span></span> <span data-ttu-id="01965-107">CTRL + C를 수행 하는 예를 들어는 **복사** 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="01965-107">For example, pressing CTRL+C performs the **Copy** command.</span></span>  
  
-   <span data-ttu-id="01965-108">탐색 메뉴에 대 한 마우스에 키보드 대신 사용할 수 있도록 선택 키를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="01965-108">Display access keys to provide a keyboard alternative to the mouse for menu navigation.</span></span> <span data-ttu-id="01965-109">예를 들어 ALT + F를 누르면 선택은 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="01965-109">For example, pressing ALT+F chooses the **File** menu.</span></span>  
  
-   <span data-ttu-id="01965-110">관련된 명령을 그룹화 하 고 메뉴를 더 쉽게 읽을 수 있도록 하려면 구분선을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="01965-110">Show separator bars to group related commands and make menus more readable.</span></span>  
  
### <a name="to-display-a-check-mark-on-a-menu-command"></a><span data-ttu-id="01965-111">메뉴 명령에 확인 표시를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="01965-111">To display a check mark on a menu command</span></span>  
  
-   <span data-ttu-id="01965-112">설정의 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="01965-112">Set its <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="01965-113">설정의 <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="01965-113">This also sets the <xref:System.Windows.Forms.ToolStripMenuItem.CheckState%2A> property to `true`.</span></span> <span data-ttu-id="01965-114">메뉴 명령에서 선택 되었는지 여부에 관계 없이 기본적으로 선택 된 상태로 표시 하려는 경우에이 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="01965-114">Use this procedure only if you want the menu command to appear as checked by default, regardless of whether it is selected.</span></span>  
  
### <a name="to-display-a-check-mark-that-changes-state-with-each-click"></a><span data-ttu-id="01965-115">클릭할 때마다 상태를 변경 하는 확인 표시가 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="01965-115">To display a check mark that changes state with each click</span></span>  
  
-   <span data-ttu-id="01965-116">설정 메뉴 명령 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="01965-116">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true`.</span></span>  
  
### <a name="to-add-an-image-to-a-menu-command"></a><span data-ttu-id="01965-117">메뉴 명령에 이미지를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="01965-117">To add an image to a menu command</span></span>  
  
-   <span data-ttu-id="01965-118">설정 메뉴 명령 <xref:System.Windows.Forms.ToolStripItem.Image%2A> 속성을 이미지의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="01965-118">Set the menu command's <xref:System.Windows.Forms.ToolStripItem.Image%2A> property to the name of the image.</span></span> <span data-ttu-id="01965-119">경우는 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 이 메뉴 명령의 속성이로 설정 되어 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> 또는 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, 이미지를 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01965-119">If the <xref:System.Windows.Forms.ToolStripItemDisplayStyle> property of this menu command is set to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>, the image cannot be displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01965-120">이미지 여백을 표시할 수도 확인 표시가 필요한 경우.</span><span class="sxs-lookup"><span data-stu-id="01965-120">The image margin can also show a check mark if you so choose.</span></span> <span data-ttu-id="01965-121">또한, 설정할 수 있습니다는 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 이미지의 속성 `true`, 실행 시으로 해치 테두리가 이미지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01965-121">Also, you can set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property of the image to `true`, and the image will appear with a hatched border around it at run time.</span></span>  
  
### <a name="to-display-a-shortcut-key-for-a-menu-command"></a><span data-ttu-id="01965-122">메뉴 명령에 대 한 바로 가기 키를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="01965-122">To display a shortcut key for a menu command</span></span>  
  
-   <span data-ttu-id="01965-123">설정 메뉴 명령 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> 속성에서 원하는 키보드 조합 CTRL + O 같은 **열려** 메뉴 명령 및 집합의 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="01965-123">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A> property to the desired keyboard combination, such as CTRL+O for the **Open** menu command, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-custom-shortcut-keys-for-a-menu-command"></a><span data-ttu-id="01965-124">메뉴 명령에 대 한 사용자 지정 바로 가기 키를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="01965-124">To display custom shortcut keys for a menu command</span></span>  
  
-   <span data-ttu-id="01965-125">설정 메뉴 명령 <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> 속성에서 원하는 키보드 조합 CTRL + SHIFT + O 보다는 SHIFT + CTRL + O, 집합 등의 <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="01965-125">Set the menu command's <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> property to the desired keyboard combination, such as CTRL+SHIFT+O rather than SHIFT+CTRL+O, and set the <xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A> property to `true`.</span></span>  
  
### <a name="to-display-an-access-key-for-a-menu-command"></a><span data-ttu-id="01965-126">메뉴 명령에 대 한 선택 키를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="01965-126">To display an access key for a menu command</span></span>  
  
-   <span data-ttu-id="01965-127">설정 하는 경우는 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 메뉴 명령에 대 한 속성 입력 앰퍼샌드 (&) 선택 키 밑줄을 표시 하려면 문자 앞입니다.</span><span class="sxs-lookup"><span data-stu-id="01965-127">When you set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property for the menu command, enter an ampersand (&) before the letter you want to be underlined as the access key.</span></span> <span data-ttu-id="01965-128">예를 들어 입력 `&Open` 로 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 메뉴 항목의 속성으로 표시 되는 메뉴 명령에서 발생 합니다 **O**펜입니다.</span><span class="sxs-lookup"><span data-stu-id="01965-128">For example, typing `&Open` as the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of a menu item will result in a menu command that appears as **O**pen.</span></span>  
  
     <span data-ttu-id="01965-129">이 메뉴 명령이 이동 하려면 ALT 키를 눌러 포커스는 <xref:System.Windows.Forms.MenuStrip>, 메뉴 이름의 선택 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="01965-129">To navigate to this menu command, press ALT to give focus to the <xref:System.Windows.Forms.MenuStrip>, and press the access key of the menu name.</span></span> <span data-ttu-id="01965-130">메뉴 선택 키를 가진 항목이 표시을 열고, 액세스 키를 눌러 메뉴 명령이 선택 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01965-130">When the menu opens and shows items with access keys, you only need to press the access key to select the menu command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01965-131">ALT + F를 동일한 메뉴 시스템에서 두 번 정의 하는 등의 중복 된 선택 키를 정의 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="01965-131">Avoid defining duplicate access keys, such as defining ALT+F twice in the same menu system.</span></span> <span data-ttu-id="01965-132">중복 된 선택 키의 선택 순서를 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01965-132">The selection order of duplicate access keys cannot be guaranteed.</span></span>  
  
### <a name="to-display-a-separator-bar-between-menu-commands"></a><span data-ttu-id="01965-133">메뉴 명령 사이 구분 기호 막대를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="01965-133">To display a separator bar between menu commands</span></span>  
  
-   <span data-ttu-id="01965-134">정의 하 고 나면 사용자 <xref:System.Windows.Forms.MenuStrip> 및 여기에 포함 될 항목 사용의 <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> 또는 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 메뉴 명령을 추가 하는 메서드 및 <xref:System.Windows.Forms.ToolStripSeparator> 컨트롤을 <xref:System.Windows.Forms.MenuStrip> 원하는 순서로 합니다.</span><span class="sxs-lookup"><span data-stu-id="01965-134">After you define your <xref:System.Windows.Forms.MenuStrip> and the items it will contain, use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> or <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add the menu commands and <xref:System.Windows.Forms.ToolStripSeparator> controls to the <xref:System.Windows.Forms.MenuStrip> in the order you want.</span></span>  
  
    ```vb  
    ' This code adds a top-level File menu to the MenuStrip.  
    Me.menuStrip1.Items.Add(New ToolStripMenuItem() _  
    {Me.fileToolStripMenuItem})  
  
    ' This code adds the New and Open menu commands, a separator bar,   
    ' and the Save and Exit menu commands to the top-level File menu,   
    ' in that order.  
    Me.fileToolStripMenuItem.DropDownItems.AddRange(New _  
    ToolStripMenuItem() {Me.newToolStripMenuItem, _  
    Me.openToolStripMenuItem, Me.toolStripSeparator1, _  
    Me.saveToolStripMenuItem, Me.exitToolStripMenuItem})  
    ```  
  
    ```csharp  
    // This code adds a top-level File menu to the MenuStrip.  
    this.menuStrip1.Items.Add(new ToolStripItem[]_  
    {this.fileToolStripMenuItem});  
  
    // This code adds the New and Open menu commands, a separator bar,   
    // and the Save and Exit menu commands to the top-level File menu,   
    // in that order.  
    this.fileToolStripMenuItem.DropDownItems.AddRange(new _  
    ToolStripItem[] {  
    this.newToolStripMenuItem,  
    this.openToolStripMenuItem,  
    this.toolStripSeparator1,  
    this.saveToolStripMenuItem,  
    this.exitToolStripMenuItem});  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="01965-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01965-135">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="01965-136">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="01965-136">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
