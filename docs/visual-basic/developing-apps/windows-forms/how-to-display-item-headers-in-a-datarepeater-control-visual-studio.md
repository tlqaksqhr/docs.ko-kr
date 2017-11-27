---
title: "방법: DataRepeater 컨트롤의 항목 머리글 표시(Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DataRepeater, item headers
- DataRepeater, selection indicators
ms.assetid: 37321447-0ffa-43e1-bdc9-0480e392b90f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: da02f9374471a581a58131e26d618f91d7cbb7af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-item-headers-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="87b9e-102">방법: DataRepeater 컨트롤의 항목 머리글 표시(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="87b9e-102">How to: Display Item Headers in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="87b9e-103">항목 헤더에는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 시각적 표시기를 제공 하는 컨트롤 때는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-103">The item header in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control provides a visual indicator when a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> is selected.</span></span> <span data-ttu-id="87b9e-104">경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> (기본값) 이면 항목 머리글이 각 항목의 왼쪽에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-104">When the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> (the default), the item header is displayed to the left of each item.</span></span> <span data-ttu-id="87b9e-105">경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>, 항목 머리글이 각 항목의 위쪽에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-105">When the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>, the item header is displayed at the top of each item.</span></span>  
  
 <span data-ttu-id="87b9e-106">처음 선택 항목 헤더에 지정 된 색으로 표시 됩니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 속성과 흰색 화살표가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-106">When it is first selected, the item header is displayed in the color that is specified by the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> property, and a white arrow icon is displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87b9e-107">설정 하는 경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 를 <xref:System.Drawing.Color.White%2A>, 항목을 먼저 선택 선택 기호가 표시 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-107">If you set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> to <xref:System.Drawing.Color.White%2A>, the selection symbol will not be visible when the item is first selected.</span></span>  
  
 <span data-ttu-id="87b9e-108">필드에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 에 포커스가 항목 헤더 변경 내용에 색은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> 배경 색 및 화살표 아이콘 검정색으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-108">When a field in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> has focus, the color of the item header changes to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> background color and the arrow icon changes to black.</span></span> <span data-ttu-id="87b9e-109">데이터가 변경 되 면 연필 기호 항목 헤더에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-109">If data is changed, a pencil symbol is displayed in the item header.</span></span>  
  
 <span data-ttu-id="87b9e-110">기본 너비 (또는 높이 때는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> 속성이 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>) 항목의 머리글은 15 픽셀입니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-110">The default width (or height when the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>) of the item header is 15 pixels.</span></span> <span data-ttu-id="87b9e-111">설정 하 여 너비를 변경할 수는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-111">You can change the width by setting the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87b9e-112">경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 속성이 11 보다 작은 값으로 설정 되 면 표시기 기호 항목 머리글에서 표시 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-112">If the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> property is set to a value that is less than 11, the indicator symbols in the item header will not be displayed.</span></span>  
  
 <span data-ttu-id="87b9e-113">항목 헤더를 설정 하 여 숨길 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> 속성을 **False**합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-113">You can hide the item headers by setting the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> property to **False**.</span></span> <span data-ttu-id="87b9e-114">때 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> 로 설정 된 **False**, 항목을 선택 하는 유일한 표시는 주위에 점선은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-114">When <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> is set to **False**, the only indication that an item is selected is a dotted line around the perimeter of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="87b9e-115">모니터링 하 여 사용자 고유의 선택 표시기를 제공할 수도 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> 속성은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> 에 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 의 이벤트는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-115">You can also provide your own selection indicator by monitoring the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> property of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="87b9e-116">자세한 내용은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="87b9e-116">For more information, see <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.</span></span>  
  
### <a name="to-change-the-appearance-of-item-headers"></a><span data-ttu-id="87b9e-117">항목 헤더의 모양을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="87b9e-117">To change the appearance of item headers</span></span>  
  
1.  <span data-ttu-id="87b9e-118">Windows Forms 디자이너에서의 낮은 영역을 선택는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-118">In the Windows Forms Designer, select the lower region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="87b9e-119">컨트롤의 아래쪽 영역을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-119">You must select the lower region of the control.</span></span> <span data-ttu-id="87b9e-120">항목 템플릿 섹션을 선택 하면 속성 창에서 다른 속성 집합이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-120">If you select the item template section, a different set of properties will appear in the Properties window.</span></span>  
  
2.  <span data-ttu-id="87b9e-121">속성 창에서 사용 하 여는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 속성 항목 헤더의 색을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-121">In the Properties window, use the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> property to change the color of the item headers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="87b9e-122">설정 하는 경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> 를 <xref:System.Drawing.Color.White%2A>, 항목을 먼저 선택 선택 기호가 표시 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-122">If you set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> to <xref:System.Drawing.Color.White%2A>, the selection symbol will not be visible when the item is first selected.</span></span>  
  
3.  <span data-ttu-id="87b9e-123">사용 하 여는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 항목 머리글의 너비 (또는 높이)을 변경할 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-123">Use the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> property to change the width (or height) of the item headers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="87b9e-124">경우는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> 속성이 11 보다 작은 값으로 설정 되 면 표시기 기호 항목 머리글에서 표시 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-124">If the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> property is set to a value that is less than 11, the indicator symbols in the item header will not be displayed.</span></span>  
  
### <a name="to-hide-item-headers"></a><span data-ttu-id="87b9e-125">항목 머리글을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="87b9e-125">To hide item headers</span></span>  
  
1.  <span data-ttu-id="87b9e-126">Windows Forms 디자이너에서의 낮은 영역을 선택는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-126">In the Windows Forms Designer, select the lower region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="87b9e-127">컨트롤의 아래쪽 영역을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-127">You must select the lower region of the control.</span></span> <span data-ttu-id="87b9e-128">항목 템플릿 섹션을 선택 하면 속성 창에서 다른 속성 집합이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-128">If you select the item template section, a different set of properties will appear in the Properties window.</span></span>  
  
2.  <span data-ttu-id="87b9e-129">속성 창에서 설정 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> 속성을 **False**합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-129">In the Properties window, set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> property to **False**.</span></span>  
  
     <span data-ttu-id="87b9e-130">항목이 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 은 선택 하면 유일한 표시 될 주위에 점선은 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="87b9e-130">When an item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> is selected, the only indication will be a dotted line around the perimeter of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b9e-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87b9e-131">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="87b9e-132">DataRepeater 컨트롤 소개</span><span class="sxs-lookup"><span data-stu-id="87b9e-132">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="87b9e-133">방법: DataRepeater 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="87b9e-133">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="87b9e-134">방법: DataRepeater 컨트롤의 레이아웃 변경</span><span class="sxs-lookup"><span data-stu-id="87b9e-134">How to: Change the Layout of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="87b9e-135">DataRepeater 컨트롤 문제 해결</span><span class="sxs-lookup"><span data-stu-id="87b9e-135">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
