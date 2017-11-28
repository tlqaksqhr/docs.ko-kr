---
title: "Windows Forms DataGridView 컨트롤에서 데이터 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 839a4fd8052578e32e4d46d10e07aa52a1f23d90
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d4883-102">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="d4883-102">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d4883-103">`DataGridView` 컨트롤은 다양 한 외부 데이터 원본에서에서 데이터를 표시 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-103">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="d4883-104">또는 컨트롤에 행과 열을 추가 하 고 수동으로 데이터를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-104">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="d4883-105">데이터 소스에 컨트롤을 바인딩하는 경우에 데이터 원본의 스키마에 따라 자동으로 열을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-105">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="d4883-106">이러한 열을 원하는 대로 표시 되지 않으면를 숨길 수, 제거 또는 다시 정렬할 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-106">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="d4883-107">또한 데이터 원본에서 제공 되지 않는 추가 데이터를 표시 하려면 바인딩되지 않은 열을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-107">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="d4883-108">또한 표준 형식 (예: 통화 형식)를 사용 하 여 데이터를 표시 하거나 표시 (예: 음수 값에 대 한 배경색을 변경 하거나 바꿀 문자열 값이 필요한 데이터를 표시 해야 형식을 사용자 지정할 수 있습니다. 해당 이미지).</span><span class="sxs-lookup"><span data-stu-id="d4883-108">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4883-109">단원 내용</span><span class="sxs-lookup"><span data-stu-id="d4883-109">In This Section</span></span>  
 [<span data-ttu-id="d4883-110">Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드</span><span class="sxs-lookup"><span data-stu-id="d4883-110">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4883-111">컨트롤에 데이터를 채우기 위한 옵션에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-111">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="d4883-112">Windows Forms DataGridView 컨트롤의 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="d4883-112">Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4883-113">값을 표시 하는 셀의 서식을 지정 하기 위한 옵션에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-113">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="d4883-114">연습: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="d4883-114">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4883-115">수동으로 컨트롤을 데이터로 채우는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-115">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="d4883-116">방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="d4883-116">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4883-117">에 바인딩하여 컨트롤을 데이터로 채우는 방법에 설명 된 `BindingSource` 데이터베이스에서 가져온 정보를 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-117">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="d4883-118">방법: 데이터 바인딩된 Windows Forms DataGridView 컨트롤에서 열 자동 생성</span><span class="sxs-lookup"><span data-stu-id="d4883-118">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="d4883-119">바인딩된 데이터 소스에 따라 열을 자동으로 생성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-119">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="d4883-120">방법: 자동으로 생성된 열을 Windows Forms DataGridView 컨트롤에서 제거</span><span class="sxs-lookup"><span data-stu-id="d4883-120">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="d4883-121">숨기 거 나 바인딩된 데이터 소스에서 자동으로 생성 된 열을 삭제 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-121">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="d4883-122">방법: Windows Forms DataGridView 컨트롤에서 열 순서 변경</span><span class="sxs-lookup"><span data-stu-id="d4883-122">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4883-123">바인딩된 데이터 소스에서 자동으로 생성 하는 열 다시 정렬 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-123">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="d4883-124">방법: 데이터 바인딩된 Windows Forms DataGridView 컨트롤에 바인딩되지 않은 열 추가</span><span class="sxs-lookup"><span data-stu-id="d4883-124">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="d4883-125">추가적인 바인딩되지 않은 열을 표시 하 여 바인딩된 데이터 원본에서 데이터를 보완 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-125">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="d4883-126">방법: Windows Forms DataGridView 컨트롤에 개체 바인딩</span><span class="sxs-lookup"><span data-stu-id="d4883-126">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="d4883-127">각 개체가 개별 행에 표시 되도록 임의 개체의 컬렉션에 컨트롤을 바인딩하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-127">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="d4883-128">방법: Windows Forms DataGridView 행에 바인딩된 개체에 액세스</span><span class="sxs-lookup"><span data-stu-id="d4883-128">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](../../../../docs/framework/winforms/controls/how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="d4883-129">컨트롤의 특정 행에 바인딩된 개체를 검색 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-129">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="d4883-130">연습: 두 개의 Windows Forms DataGridView 컨트롤을 사용하여 마스터/세부 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="d4883-130">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="d4883-131">두 관련된 데이터베이스 테이블의에서 데이터를 표시 하는 방법에 설명 되도록 하나에 표시 된 값 `DataGridView` 컨트롤에서 현재 선택 된 행에 다른 컨트롤에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-131">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="d4883-132">방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d4883-132">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4883-133">처리 하는 방법에 설명 된 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 의 값에 따라 셀의 모양을 변경 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-133">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d4883-134">참조</span><span class="sxs-lookup"><span data-stu-id="d4883-134">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="d4883-135"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-135">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="d4883-136">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="d4883-137"><xref:System.Windows.Forms.BindingSource> 구성 요소에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d4883-138">관련 단원</span><span class="sxs-lookup"><span data-stu-id="d4883-138">Related Sections</span></span>  
 [<span data-ttu-id="d4883-139">Windows Forms DataGridView 컨트롤의 데이터 입력</span><span class="sxs-lookup"><span data-stu-id="d4883-139">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="d4883-140">사용자가 컨트롤에서 데이터를 추가 및 수정하는 방법을 변경하는 방법에 대해 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4883-140">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4883-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4883-141">See Also</span></span>  
 [<span data-ttu-id="d4883-142">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d4883-142">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="d4883-143">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="d4883-143">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
