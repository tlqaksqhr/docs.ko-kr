---
title: "방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 그룹화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 537aff8a49e42fe521ca6e0b2b698a461d4f5eaf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="6a061-102">방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 항목 그룹화</span><span class="sxs-lookup"><span data-stu-id="6a061-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="6a061-103">그룹화 기능은 <xref:System.Windows.Forms.ListView> 컨트롤 관련된 항목 집합을 그룹으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="6a061-104">이러한 그룹은 화면에서 그룹 제목을 포함 하는 가로 그룹 머리글에 의해 분리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="6a061-105">사용할 수 있습니다 <xref:System.Windows.Forms.ListView> 날짜, 또는 다른 논리적 그룹화 하 여 항목을 사전순으로 그룹화 하 여 큰 목록 보다 쉽게 탐색 하기 위해 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="6a061-106">다음 그림에서는 일부 그룹화 된 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-106">The following image shows some grouped items.</span></span>  
  
 <span data-ttu-id="6a061-107">![ListView 그룹](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span><span class="sxs-lookup"><span data-stu-id="6a061-107">![ListView Groups](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span></span>  
  
 <span data-ttu-id="6a061-108">다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="6a061-109">이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-109">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
 <span data-ttu-id="6a061-110">그룹화를 사용 하려면 먼저 만들어야 합니다 하나 이상의 <xref:System.Windows.Forms.ListViewGroup> 디자이너에서 또는 프로그래밍 방식으로 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="6a061-111">그룹을 정의한 후에 항목을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-111">Once a group has been defined, you can assign items to it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a061-112"><xref:System.Windows.Forms.ListView>그룹에 대해서만 사용할 수 있는 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] 응용 프로그램 호출 하는 경우는 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="6a061-112"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6a061-113">이전 버전의 운영 체제 그룹과 관련 된 코드가 아무 효과도 없습니다 및 그룹이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="6a061-114">자세한 내용은 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a061-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
>   
>  <span data-ttu-id="6a061-115">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-115">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6a061-116">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-116">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6a061-117">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a061-117">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="6a061-118">추가 하거나 디자이너에서 그룹을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="6a061-118">To add or remove groups in the designer</span></span>  
  
1.  <span data-ttu-id="6a061-119">에 **속성** 창 클릭는 **줄임표** (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 단추 옆에 <xref:System.Windows.Forms.ListView.Groups%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-119">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>  
  
     <span data-ttu-id="6a061-120">**ListViewGroup 컬렉션 편집기** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-120">The **ListViewGroup Collection Editor** appears.</span></span>  
  
2.  <span data-ttu-id="6a061-121">그룹을 추가 하려면 클릭는 **추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-121">To add a group, click the **Add** button.</span></span> <span data-ttu-id="6a061-122">설정할 수 있습니다는 새 그룹의 속성이 같은 <xref:System.Windows.Forms.ListViewGroup.Header%2A> 및 <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-122">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="6a061-123">그룹을 제거 하려면 선택 하 고 클릭 하 고 **제거** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-123">To remove a group, select it and click the **Remove** button.</span></span>  
  
### <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="6a061-124">디자이너에서 그룹에 항목을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="6a061-124">To assign items to groups in the designer</span></span>  
  
1.  <span data-ttu-id="6a061-125">에 **속성** 창 클릭는 **줄임표** (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 단추 옆에 <xref:System.Windows.Forms.ListView.Items%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-125">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     <span data-ttu-id="6a061-126">**ListViewItem 컬렉션 편집기** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-126">The **ListViewItem Collection Editor** appears.</span></span>  
  
2.  <span data-ttu-id="6a061-127">새 항목을 추가 하려면 클릭는 **추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-127">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="6a061-128">설정할 수 있습니다 다음 새 항목의 속성을 같은 <xref:System.Windows.Forms.ListViewItem.Text%2A> 및 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-128">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>  
  
3.  <span data-ttu-id="6a061-129">선택 된 <xref:System.Windows.Forms.ListViewItem.Group%2A> 속성 드롭 다운 목록에서 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a061-129">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a061-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a061-130">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [<span data-ttu-id="6a061-131">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6a061-131">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="6a061-132">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="6a061-132">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="6a061-133">Windows XP 기능 및 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6a061-133">Windows XP Features and Windows Forms Controls</span></span>](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [<span data-ttu-id="6a061-134">방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="6a061-134">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
