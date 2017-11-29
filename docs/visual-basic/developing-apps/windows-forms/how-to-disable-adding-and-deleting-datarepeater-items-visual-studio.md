---
title: "방법: DataRepeater 항목 추가 및 삭제 사용 안 함(Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, disabling delete
- DataRepeater, disabling add
ms.assetid: 298d8f60-ddfe-4361-ab66-cf76d0df5220
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1b15fe6fb5190855126ffa60ac488aaa74ad9b5a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-disable-adding-and-deleting-datarepeater-items-visual-studio"></a><span data-ttu-id="1d35a-102">방법: DataRepeater 항목 추가 및 삭제 사용 안 함(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="1d35a-102">How to: Disable Adding and Deleting DataRepeater Items (Visual Studio)</span></span>
<span data-ttu-id="1d35a-103">기본적으로 사용자가 추가 하 고 수의 항목을 삭제 한 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-103">By default, users can add and delete items in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="1d35a-104">사용자가 CTRL + N을 눌러 새 항목을 추가할 수 있습니다 때는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> 포커스 했거나이 클릭 하 여는 **AddNewItem** 단추는 <xref:System.Windows.Forms.BindingNavigator> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-104">Users can add a new item by pressing CTRL+N when a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> has focus or by clicking the **AddNewItem** button on the <xref:System.Windows.Forms.BindingNavigator> control.</span></span> <span data-ttu-id="1d35a-105">사용자 키를 눌러 항목을 삭제할 수 있습니다 때 삭제 될는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> 포커스 했거나이 클릭 하 여는 **DeleteItem** 단추는 <xref:System.Windows.Forms.BindingNavigator> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-105">Users can delete an item by pressing DELETE when a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> has focus or by clicking the **DeleteItem** button on the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
 <span data-ttu-id="1d35a-106">추가 및/또는 디자인 타임 또는 런타임 시 삭제를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-106">You can disable adding and/or deleting at design time or at run time.</span></span>  
  
### <a name="to-disable-adding-and-deleting-at-design-time"></a><span data-ttu-id="1d35a-107">디자인 타임에 추가 및 삭제를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1d35a-107">To disable adding and deleting at design time</span></span>  
  
1.  <span data-ttu-id="1d35a-108">Windows Forms 디자이너에서 선택 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-108">In the Windows Forms Designer, select the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1d35a-109">컨트롤의 아래쪽 섹션을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-109">You must select the lower section of the control.</span></span> <span data-ttu-id="1d35a-110">항목 템플릿 섹션을 선택 하면 다른 속성 집합이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-110">If you select the item template section, a different set of properties will be displayed.</span></span>  
  
2.  <span data-ttu-id="1d35a-111">속성 창에서 설정 된 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> 속성을 **False**합니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-111">In the Properties window, set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> property to **False**.</span></span>  
  
3.  <span data-ttu-id="1d35a-112">설정의 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> 속성을 **False**합니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-112">Set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> property to **False**.</span></span>  
  
4.  <span data-ttu-id="1d35a-113">Windows Forms 디자이너에서 선택 된 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 클릭 한 다음는 **AddNewItem** 단추 (에 더하기 기호가 있는 단추).</span><span class="sxs-lookup"><span data-stu-id="1d35a-113">In the Windows Forms Designer, select the <xref:System.Windows.Forms.BindingNavigator> control, and then click the **AddNewItem** button (the button with a plus sign on it).</span></span>  
  
5.  <span data-ttu-id="1d35a-114">속성 창에서 설정 된 <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> 속성을 **False**합니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-114">In the Properties window, set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property to **False**.</span></span>  
  
6.  <span data-ttu-id="1d35a-115">Windows Forms 디자이너에서 선택 된 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 클릭 한 다음는 **DeleteItem** 단추 (에 빨간색 X가 있는 단추).</span><span class="sxs-lookup"><span data-stu-id="1d35a-115">In the Windows Forms Designer, select the <xref:System.Windows.Forms.BindingNavigator> control, and then click the **DeleteItem** button (the button with a red X on it).</span></span>  
  
7.  <span data-ttu-id="1d35a-116">속성 창에서 설정 된 <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> 속성을 **False**합니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-116">In the Properties window, set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property to **False**.</span></span>  
  
8.  <span data-ttu-id="1d35a-117">구성 요소 트레이에 선택는 <xref:System.Windows.Forms.BindingSource> 입니다는 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 바인딩되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-117">In the Component Tray, select the <xref:System.Windows.Forms.BindingSource> to which the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> is bound.</span></span>  
  
9. <span data-ttu-id="1d35a-118">속성 창에서 설정 된 <xref:System.Windows.Forms.BindingSource.AllowNew%2A> 속성을 **False**합니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-118">In the Properties window, set the <xref:System.Windows.Forms.BindingSource.AllowNew%2A> property to **False**.</span></span>  
  
10. <span data-ttu-id="1d35a-119">Windows Forms 디자이너에서 두 번 클릭은 **DeleteItem** 단추 코드 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-119">In the Windows Forms Designer, double-click the **DeleteItem** button to open the Code Editor.</span></span>  
  
11. <span data-ttu-id="1d35a-120">이벤트 드롭 다운 목록에서 선택 된 `BindingNavigatorDeleteItem_EnabledChanged` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-120">In the Events drop-down list, select the `BindingNavigatorDeleteItem_EnabledChanged` event.</span></span>  
  
12. <span data-ttu-id="1d35a-121">다음 코드를 `BindingNavigatorDeleteItem_EnabledChanged` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-121">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="1d35a-122"><xref:System.Windows.Forms.BindingSource> 로 인해 현재 레코드가 변경될 때마다 **DeleteItem** 단추가 활성화되므로 이 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-122">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
### <a name="to-disable-adding-and-deleting-at-run-time"></a><span data-ttu-id="1d35a-123">실행된 시간에 추가 및 삭제를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1d35a-123">To disable adding and deleting at run time</span></span>  
  
1.  <span data-ttu-id="1d35a-124">Windows Forms 디자이너에서 폼을 두 번 클릭하여 코드 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-124">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="1d35a-125">`Form_Load` 이벤트에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-125">Add the following code to the `Form_Load` event:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.vb)]  
  
3.  <span data-ttu-id="1d35a-126">다음 코드를 `BindingNavigatorDeleteItem_EnabledChanged` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-126">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="1d35a-127"><xref:System.Windows.Forms.BindingSource> 로 인해 현재 레코드가 변경될 때마다 **DeleteItem** 단추가 활성화되므로 이 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d35a-127">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d35a-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d35a-128">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="1d35a-129">DataRepeater 컨트롤 소개</span><span class="sxs-lookup"><span data-stu-id="1d35a-129">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="1d35a-130">DataRepeater 컨트롤 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1d35a-130">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
