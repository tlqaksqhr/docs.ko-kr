---
title: "BindingNavigator 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DataNavigator
helpviewer_keywords:
- BindingNavigator control [Windows Forms], about BindingNavigator control
- records [Windows Forms], navigating on a form
- data [Windows Forms], navigating
- data navigation
ms.assetid: 4423eede-f8d1-4d02-822f-5bf8432680d0
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 921f8c7791620d51107fa2ff31a637094fc0c633
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bindingnavigator-control-overview-windows-forms"></a><span data-ttu-id="31f49-102">BindingNavigator 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="31f49-102">BindingNavigator Control Overview (Windows Forms)</span></span>
<span data-ttu-id="31f49-103"><xref:System.Windows.Forms.BindingNavigator> 컨트롤을 사용하여 사용자가 Windows Form에서 데이터를 검색 및 변경할 수 있게 해주는 표준화된 방법을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-103">You can use the <xref:System.Windows.Forms.BindingNavigator> control to create a standardized means for users to search and change data on a Windows Form.</span></span> <span data-ttu-id="31f49-104">사용자가 폼의 데이터 레코드를 탐색하고 레코드와 상호 작용할 수 있도록 <xref:System.Windows.Forms.BindingSource> 구성 요소와 함께 <xref:System.Windows.Forms.BindingNavigator>를 사용하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-104">You frequently use <xref:System.Windows.Forms.BindingNavigator> with the <xref:System.Windows.Forms.BindingSource> component to enable users to move through data records on a form and interact with the records.</span></span>  
  
## <a name="how-the-bindingnavigator-works"></a><span data-ttu-id="31f49-105">BindingNavigator 작동 방식</span><span class="sxs-lookup"><span data-stu-id="31f49-105">How the BindingNavigator Works</span></span>  
 <span data-ttu-id="31f49-106"><xref:System.Windows.Forms.BindingNavigator> 컨트롤은 데이터 추가, 데이터 삭제 및 데이터 탐색과 같은 대부분의 일반적인 데이터 관련 작업을 위한 일련의 <xref:System.Windows.Forms.ToolStripItem> 개체를 포함하는 <xref:System.Windows.Forms.ToolStrip>으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-106">The <xref:System.Windows.Forms.BindingNavigator> control is composed of a <xref:System.Windows.Forms.ToolStrip> with a series of <xref:System.Windows.Forms.ToolStripItem> objects for most of the common data-related actions: adding data, deleting data, and navigating through data.</span></span> <span data-ttu-id="31f49-107">기본적으로 <xref:System.Windows.Forms.BindingNavigator> 컨트롤은 이러한 표준 단추를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-107">By default, the <xref:System.Windows.Forms.BindingNavigator> control contains these standard buttons.</span></span> <span data-ttu-id="31f49-108">다음 스크린샷은 폼의 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-108">The following screen shot shows the <xref:System.Windows.Forms.BindingNavigator> control on a form.</span></span>  
  
 <span data-ttu-id="31f49-109">![BindingNavigator 컨트롤](../../../../docs/framework/winforms/controls/media/cpdatacontainerctrl.gif "cpDataContainerCtrl")</span><span class="sxs-lookup"><span data-stu-id="31f49-109">![BindingNavigator Control](../../../../docs/framework/winforms/controls/media/cpdatacontainerctrl.gif "cpDataContainerCtrl")</span></span>  
  
 <span data-ttu-id="31f49-110">다음 표에서는 컨트롤을 나열하고 해당 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-110">The following table lists the controls and describes their functions.</span></span>  
  
|<span data-ttu-id="31f49-111">컨트롤</span><span class="sxs-lookup"><span data-stu-id="31f49-111">Control</span></span>|<span data-ttu-id="31f49-112">함수</span><span class="sxs-lookup"><span data-stu-id="31f49-112">Function</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="31f49-113"><xref:System.Windows.Forms.BindingNavigator.AddNewItem%2A> 단추</span><span class="sxs-lookup"><span data-stu-id="31f49-113"><xref:System.Windows.Forms.BindingNavigator.AddNewItem%2A> button</span></span>|<span data-ttu-id="31f49-114">내부 데이터 소스에 새 행을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-114">Inserts a new row into the underlying data source.</span></span>|  
|<span data-ttu-id="31f49-115"><xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> 단추</span><span class="sxs-lookup"><span data-stu-id="31f49-115"><xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button</span></span>|<span data-ttu-id="31f49-116">내부 데이터 소스에서 현재 행을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-116">Deletes the current row from the underlying data source.</span></span>|  
|<span data-ttu-id="31f49-117"><xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> 단추</span><span class="sxs-lookup"><span data-stu-id="31f49-117"><xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button</span></span>|<span data-ttu-id="31f49-118">내부 데이터 소스의 첫 번째 행으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-118">Moves to the first item in the underlying data source.</span></span>|  
|<span data-ttu-id="31f49-119"><xref:System.Windows.Forms.BindingNavigator.MoveLastItem%2A> 단추</span><span class="sxs-lookup"><span data-stu-id="31f49-119"><xref:System.Windows.Forms.BindingNavigator.MoveLastItem%2A> button</span></span>|<span data-ttu-id="31f49-120">내부 데이터 소스의 마지막 행으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-120">Moves to the last item in the underlying data source.</span></span>|  
|<span data-ttu-id="31f49-121"><xref:System.Windows.Forms.BindingNavigator.MoveNextItem%2A> 단추</span><span class="sxs-lookup"><span data-stu-id="31f49-121"><xref:System.Windows.Forms.BindingNavigator.MoveNextItem%2A> button</span></span>|<span data-ttu-id="31f49-122">내부 데이터 소스의 다음 행으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-122">Moves to the next item in the underlying data source.</span></span>|  
|<span data-ttu-id="31f49-123"><xref:System.Windows.Forms.BindingNavigator.MovePreviousItem%2A> 단추</span><span class="sxs-lookup"><span data-stu-id="31f49-123"><xref:System.Windows.Forms.BindingNavigator.MovePreviousItem%2A> button</span></span>|<span data-ttu-id="31f49-124">내부 데이터 소스의 이전 행으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-124">Moves to the previous item in the underlying data source.</span></span>|  
|<span data-ttu-id="31f49-125"><xref:System.Windows.Forms.BindingNavigator.PositionItem%2A> 텍스트 상자</span><span class="sxs-lookup"><span data-stu-id="31f49-125"><xref:System.Windows.Forms.BindingNavigator.PositionItem%2A> text box</span></span>|<span data-ttu-id="31f49-126">내부 데이터 소스 내의 현재 위치를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-126">Returns the current position within the underlying data source.</span></span>|  
|<span data-ttu-id="31f49-127"><xref:System.Windows.Forms.BindingNavigator.CountItem%2A> 텍스트 상자</span><span class="sxs-lookup"><span data-stu-id="31f49-127"><xref:System.Windows.Forms.BindingNavigator.CountItem%2A> text box</span></span>|<span data-ttu-id="31f49-128">내부 데이터 소스의 총 항목 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-128">Returns the total number of items in the underlying data source.</span></span>|  
  
 <span data-ttu-id="31f49-129">이 컬렉션의 각 컨트롤에 대해 프로그래밍 방식으로 동일한 기능을 제공하는 <xref:System.Windows.Forms.BindingSource> 구성 요소의 해당 멤버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-129">For each control in this collection, there is a corresponding member of the <xref:System.Windows.Forms.BindingSource> component that programmatically provides the same functionality.</span></span> <span data-ttu-id="31f49-130">예를 들어 <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> 단추는 <xref:System.Windows.Forms.BindingSource> 구성 요소의 <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> 메서드에 해당하고 <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> 단추는 <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> 메서드에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-130">For example, the <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> method of the <xref:System.Windows.Forms.BindingSource> component, the <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> method, and so on.</span></span>  
  
 <span data-ttu-id="31f49-131">기본 단추가 응용 프로그램에 적합하지 않은 경우 또는 다른 유형의 기능을 지원하기 위해 추가 단추가 필요한 경우 고유한 <xref:System.Windows.Forms.ToolStrip> 단추를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31f49-131">If the default buttons are not suited to your application, or if you require additional buttons to support other types of functionality, you can supply your own <xref:System.Windows.Forms.ToolStrip> buttons.</span></span> <span data-ttu-id="31f49-132">[방법: Windows Forms BindingNavigator 컨트롤에 로드, 저장 및 취소 단추 추가](../../../../docs/framework/winforms/controls/load-save-and-cancel-bindingnavigator.md)도 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31f49-132">Also see [How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control](../../../../docs/framework/winforms/controls/load-save-and-cancel-bindingnavigator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f49-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31f49-133">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="31f49-134">BindingNavigator 컨트롤</span><span class="sxs-lookup"><span data-stu-id="31f49-134">BindingNavigator Control</span></span>](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)
