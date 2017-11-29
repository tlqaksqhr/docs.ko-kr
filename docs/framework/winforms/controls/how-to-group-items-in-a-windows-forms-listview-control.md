---
title: "방법: Windows Forms ListView 컨트롤에서 항목 그룹화"
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
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c22134513c2c6a3ff2bc621e68f546b7bcc93ba9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="ca89f-102">방법: Windows Forms ListView 컨트롤에서 항목 그룹화</span><span class="sxs-lookup"><span data-stu-id="ca89f-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="ca89f-103">그룹화 기능을 통해는 <xref:System.Windows.Forms.ListView> 컨트롤을 그룹에 관련된 항목 집합을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca89f-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="ca89f-104">이러한 그룹은 화면에서 그룹 제목을 포함 하는 가로 그룹 머리글에 의해 분리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca89f-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="ca89f-105">사용할 수 있습니다 <xref:System.Windows.Forms.ListView> 날짜, 또는 다른 논리적 그룹화 하 여 항목을 사전순으로 그룹화 하 여 큰 목록 보다 쉽게 탐색 하기 위해 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="ca89f-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="ca89f-106">다음 그림에서는 일부 그룹화 된 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca89f-106">The following image shows some grouped items.</span></span>  
  
 <span data-ttu-id="ca89f-107">![ListView 그룹](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span><span class="sxs-lookup"><span data-stu-id="ca89f-107">![ListView Groups](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span></span>  
<span data-ttu-id="ca89f-108">ListView 그룹화 된 항목</span><span class="sxs-lookup"><span data-stu-id="ca89f-108">ListView grouped items</span></span>  
  
 <span data-ttu-id="ca89f-109">그룹화를 사용 하려면 먼저 디자이너에서 또는 프로그래밍 방식으로 그룹 하나 이상 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca89f-109">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="ca89f-110">그룹을 정의한 후 할당할 수 있습니다 <xref:System.Windows.Forms.ListView> 항목 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="ca89f-110">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="ca89f-111">이동할 수도 있습니다 항목 그룹에서 다른 프로그래밍 방식으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca89f-111">You can also move items from one group to another programmatically.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca89f-112"><xref:System.Windows.Forms.ListView>그룹에 대해서만 사용할 수 있는 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] 응용 프로그램 호출 하는 경우는 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="ca89f-112"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ca89f-113">이전 버전의 운영 체제 그룹과 관련 된 코드가 아무 효과도 없습니다 및 그룹이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca89f-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="ca89f-114">자세한 내용은 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca89f-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="ca89f-115">그룹을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="ca89f-115">To add groups</span></span>  
  
1.  <span data-ttu-id="ca89f-116"><xref:System.Windows.Forms.ListView.Groups%2A> 컬렉션의 <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca89f-116">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="ca89f-117">그룹을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="ca89f-117">To remove groups</span></span>  
  
1.  <span data-ttu-id="ca89f-118">사용 하 여는 <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 또는 <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 의 메서드는 <xref:System.Windows.Forms.ListView.Groups%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ca89f-118">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="ca89f-119"><xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> 단일 그룹을 제거 하는 메서드, <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> 메서드 목록에서 모든 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca89f-119">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca89f-120">그룹을 제거 해도 해당 그룹 내의 항목은 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca89f-120">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="ca89f-121">항목 그룹을 할당 하거나 그룹 간에 항목을 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="ca89f-121">To assign items to groups or move items between groups</span></span>  
  
1.  <span data-ttu-id="ca89f-122">설정의 <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> 개별 항목의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ca89f-122">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="ca89f-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca89f-123">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [<span data-ttu-id="ca89f-124">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ca89f-124">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [<span data-ttu-id="ca89f-125">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="ca89f-125">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="ca89f-126">Windows XP 기능 및 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ca89f-126">Windows XP Features and Windows Forms Controls</span></span>](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [<span data-ttu-id="ca89f-127">방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="ca89f-127">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
