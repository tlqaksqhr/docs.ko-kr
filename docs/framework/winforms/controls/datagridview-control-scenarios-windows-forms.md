---
title: "DataGridView 컨트롤 시나리오(Windows Forms)"
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
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 919197d8fdb40f0e0fb7b91fecae38f4e0e061bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="datagridview-control-scenarios-windows-forms"></a><span data-ttu-id="48f18-102">DataGridView 컨트롤 시나리오(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="48f18-102">DataGridView Control Scenarios (Windows Forms)</span></span>
<span data-ttu-id="48f18-103">와 <xref:System.Windows.Forms.DataGridView> 컨트롤을 다양 한 데이터 원본에서에서 테이블 형식 데이터를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-103">With the <xref:System.Windows.Forms.DataGridView> control, you can display tabular data from a variety of data sources.</span></span> <span data-ttu-id="48f18-104">간단한 용도로 수동으로 차원을 채울 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 제어를 통해 직접 데이터를 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-104">For simple uses, you can manually populate a <xref:System.Windows.Forms.DataGridView> and manipulate the data directly through the control.</span></span> <span data-ttu-id="48f18-105">그러나 일반적으로는 외부 데이터 원본에 데이터를 저장 한 키를 통해에 컨트롤 바인딩는 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-105">Typically, however, you will store your data in an external data source and bind the control to it through a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="48f18-106">이 항목에서는 몇 가지 일반적인 시나리오와 관련 된 설명는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-106">This topic describes some of the common scenarios that involve the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a><span data-ttu-id="48f18-107">시나리오 1: 적은 양의 데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-107">Scenario 1: Displaying Small Amounts of Data</span></span>  
 <span data-ttu-id="48f18-108">에 표시 하기 위해 외부 데이터 원본에 데이터를 저장할 필요가 없습니다는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-108">You do not have to store your data in an external data source to display it in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="48f18-109">적은 양의 데이터를 사용 하는 경우에 사용자가 직접 컨트롤을 채울 수 있으며 제어를 통해 데이터를 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-109">If you are working with a small amount of data, you can populate the control yourself and manipulate the data through the control.</span></span> <span data-ttu-id="48f18-110">이 라고 *바인딩되지 않은 모드*합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-110">This is called *unbound mode*.</span></span> <span data-ttu-id="48f18-111">자세한 내용은 참조 [하는 방법: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-111">For more information, see [How to: Create an Unbound Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="48f18-112">시나리오 주요 사항</span><span class="sxs-lookup"><span data-stu-id="48f18-112">Scenario Key Points</span></span>  
  
-   <span data-ttu-id="48f18-113">바인딩되지 않은 모드에서 하면 컨트롤을 수동으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-113">In unbound mode, you populate the control manually.</span></span>  
  
-   <span data-ttu-id="48f18-114">바인딩되지 않은 모드는 적은 양의 데이터에 특히 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-114">Unbound mode is particularly suited for small amounts of read-only data.</span></span>  
  
-   <span data-ttu-id="48f18-115">바인딩되지 않은 모드는 스프레드시트 모양의 또는 근거가 테이블도 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-115">Unbound mode is also suited for spreadsheet-like or sparsely populated tables.</span></span>  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a><span data-ttu-id="48f18-116">시나리오 2: 보기 및 외부 데이터 원본에 저장 된 데이터를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-116">Scenario 2: Viewing and Updating Data Stored in an External Data Source</span></span>  
 <span data-ttu-id="48f18-117">사용할 수는 <xref:System.Windows.Forms.DataGridView> 데이터베이스 테이블 또는 비즈니스 개체의 컬렉션에 같은 데이터 원본에 유지 하는 데이터에 액세스할 수 있는 사용자를 통해 사용자 인터페이스 (UI)으로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-117">You can use the <xref:System.Windows.Forms.DataGridView> control as a user interface (UI) through which users can access data kept in a data source such as a database table or a collection of business objects.</span></span> <span data-ttu-id="48f18-118">자세한 내용은 참조 [하는 방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-118">For more information, see [How to: Bind Data to the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="48f18-119">시나리오 주요 사항</span><span class="sxs-lookup"><span data-stu-id="48f18-119">Scenario Key Points</span></span>  
  
-   <span data-ttu-id="48f18-120">바인딩된 모드를 사용 하 여 데이터 원본에 연결, 데이터 원본 속성 또는 데이터베이스 열을 기준으로 열을 자동으로 생성 하 고 컨트롤을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-120">Bound mode lets you connect to a data source, automatically generate columns based on the data source properties or database columns, and automatically populate the control.</span></span>  
  
-   <span data-ttu-id="48f18-121">바인딩된 모드는 많은 사용자 데이터와 상호 작용에 대 한 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-121">Bound mode is suited for heavy user interaction with data.</span></span> <span data-ttu-id="48f18-122">표시 되는 데이터 형식을 지정할 수 및 사용자 지정 데이터를 데이터 원본에서 예상 되는 형식으로 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-122">Data can be formatted for display, and user-specified data can be parsed into the format expected by the data source.</span></span> <span data-ttu-id="48f18-123">사용자가 경고를 보낼 수 및 오류가 있는 셀을 해결할 수 있도록 서식 오류 및 데이터베이스 제약 조건 오류는 데이터 입력을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-123">Data entry formatting errors and database constraint errors can be detected so that users can be warned and erroneous cells can be corrected.</span></span>  
  
-   <span data-ttu-id="48f18-124">열 정렬 등의 추가 기능, 고정 및 다시 사용자가을 자신의 워크플로에 대 한 가장 편리한 방식으로 데이터를 볼 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-124">Additional functionality such as column sorting, freezing, and reordering enable users to view data in the way most convenient for their workflow.</span></span>  
  
-   <span data-ttu-id="48f18-125">클립보드 지원을 통해 사용자가 다른 응용 프로그램으로 응용 프로그램에서 데이터를 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-125">Clipboard support enables users to copy data from your application into other applications.</span></span>  
  
## <a name="scenario-3-advanced-data"></a><span data-ttu-id="48f18-126">시나리오 3: 고급 데이터</span><span class="sxs-lookup"><span data-stu-id="48f18-126">Scenario 3: Advanced Data</span></span>  
 <span data-ttu-id="48f18-127">표준 데이터 바인딩 모델 해결 되지 않는 경우 컨트롤과 데이터 간의 상호 작용을 구현 하 여 관리할 수 있습니다 *가상 모드*합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-127">If you have special needs that the standard data binding model does not address, you can manage the interaction between the control and your data by implementing *virtual mode*.</span></span> <span data-ttu-id="48f18-128">구현 정보로 셀에 대 한 제어 요청 정보 수 있는 하나 이상의 이벤트 처리기를 구현 하는 가상 모드 의미 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-128">Implementing virtual mode means implementing one or more event handlers that let the control request information about cells as the information is needed.</span></span>  
  
 <span data-ttu-id="48f18-129">예를 들어 많은 양의 데이터를 사용 하는 경우 최적의 효율성을 위해 가상 모드 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-129">For example, if you work with large amounts of data, you may want to implement virtual mode to ensure optimal efficiency.</span></span> <span data-ttu-id="48f18-130">가상 모드는 다른 데이터 원본에서 검색 하는 열과 함께 표시 하는 바인딩되지 않은 열의 값을 유지 관리 하기 위한 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-130">Virtual mode is also useful for maintaining the values of unbound columns that you display along with columns retrieved from another data source.</span></span>  
  
 <span data-ttu-id="48f18-131">가상 모드에 대 한 자세한 내용은 참조 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-131">For more information about virtual mode, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="48f18-132">시나리오 주요 사항</span><span class="sxs-lookup"><span data-stu-id="48f18-132">Scenario Key Points</span></span>  
  
-   <span data-ttu-id="48f18-133">가상 모드는 성능을 미세 조정 해야 할 때 매우 많은 양의 데이터를 표시 하기 위한 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-133">Virtual mode is suited for displaying very large amounts of data when you need to fine-tune performance.</span></span>  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a><span data-ttu-id="48f18-134">시나리오 4: 자동으로 크기 조정 행 및 열</span><span class="sxs-lookup"><span data-stu-id="48f18-134">Scenario 4: Automatically Resizing Rows and Columns</span></span>  
 <span data-ttu-id="48f18-135">정기적으로 업데이트 하는 데이터를 표시 하면 행과 열 모든 콘텐츠 표시 되는지 확인을 자동으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-135">When you display data that is regularly updated, you can automatically resize rows and columns to ensure that all content is visible.</span></span> <span data-ttu-id="48f18-136"><xref:System.Windows.Forms.DataGridView> 크기 조정 자동으로 콘텐츠가 변경 될 때마다 또는 컨트롤 사용 또는 사용 안 함 수동 크기 조정, 특정 시간에 프로그래밍 방식으로 크기를 조정할 수 있는 몇 가지 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-136">The <xref:System.Windows.Forms.DataGridView> control provides several options that let you enable or disable manual resizing, resize programmatically at specific times, or resize automatically whenever content changes.</span></span> <span data-ttu-id="48f18-137">자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 크기 조정 옵션](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-137">For more information, see [Sizing Options in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="48f18-138">시나리오 주요 사항</span><span class="sxs-lookup"><span data-stu-id="48f18-138">Scenario Key Points</span></span>  
  
-   <span data-ttu-id="48f18-139">수동 크기 조정을 통해 셀 높이 너비를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-139">Manual resizing enables users to adjust cell heights and widths.</span></span>  
  
-   <span data-ttu-id="48f18-140">자동 크기 조정 셀 내용이 잘리지 않도록 셀 크기를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-140">Automatic resizing enables you to maintain cell sizes so that cell content is never clipped.</span></span>  
  
-   <span data-ttu-id="48f18-141">프로그래밍 방식의 크기 연속 자동 크기 조정의 성능 저하를 방지 하기 위해 특정 시간에 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-141">Programmatic resizing enables you to resize cells at specific times to avoid the performance penalty of continuous automatic resizing.</span></span>  
  
## <a name="scenario-5-simple-customization"></a><span data-ttu-id="48f18-142">시나리오 5: 단순 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="48f18-142">Scenario 5: Simple Customization</span></span>  
 <span data-ttu-id="48f18-143"><xref:System.Windows.Forms.DataGridView> 컨트롤의 기본 모양과 동작을 변경할 수 있는 여러 가지 방법이 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-143">The <xref:System.Windows.Forms.DataGridView> control provides many ways for you to alter its basic appearance and behavior.</span></span> <span data-ttu-id="48f18-144">자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-144">For more information, see [Cell Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="48f18-145">시나리오 주요 사항</span><span class="sxs-lookup"><span data-stu-id="48f18-145">Scenario Key Points</span></span>  
  
-   <span data-ttu-id="48f18-146"><xref:System.Windows.Forms.DataGridViewCellStyle>개체를 사용 하면 색, 글꼴, 서식 및 여러 수준에서 및 컨트롤의 개별 요소에 대 한 위치 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-146"><xref:System.Windows.Forms.DataGridViewCellStyle> objects let you provide color, font, formatting, and positioning information at multiple levels and for individual elements of the control.</span></span>  
  
-   <span data-ttu-id="48f18-147">셀 스타일 및 계층 코드를 재사용할 수 있으므로 여러 요소를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-147">Cell styles can be layered and shared by multiple elements, letting you reuse code.</span></span>  
  
## <a name="scenario-6-advanced-customization"></a><span data-ttu-id="48f18-148">시나리오 6: 고급 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="48f18-148">Scenario 6: Advanced Customization</span></span>  
 <span data-ttu-id="48f18-149"><xref:System.Windows.Forms.DataGridView> 컨트롤은 모양과 동작을 사용자 지정할 수 있는 여러 가지 방법이 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-149">The <xref:System.Windows.Forms.DataGridView> control provides many ways for you to customize its appearance and behavior.</span></span>  
  
### <a name="scenario-key-points"></a><span data-ttu-id="48f18-150">시나리오 주요 사항</span><span class="sxs-lookup"><span data-stu-id="48f18-150">Scenario Key Points</span></span>  
  
-   <span data-ttu-id="48f18-151">셀 그리기 코드를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-151">You can provide your own cell painting code.</span></span> <span data-ttu-id="48f18-152">자세한 내용은 참조 [하는 방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-152">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="48f18-153">고유한 행 그리기를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-153">You can provide your own row painting.</span></span> <span data-ttu-id="48f18-154">이 값은 유용 예를 들어 여러 열에 걸쳐 있는 내용이 있는 행을 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-154">This is useful, for example, to create rows with content that spans multiple columns.</span></span> <span data-ttu-id="48f18-155">자세한 내용은 참조 [하는 방법: Windows Forms DataGridView 컨트롤에서 행 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-155">For more information, see [How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="48f18-156">셀 모양 사용자 지정 하려면 사용자 고유의 셀과 열 클래스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-156">You can implement your own cell and column classes to customize cell appearance.</span></span> <span data-ttu-id="48f18-157">자세한 내용은 참조 [하는 방법: 확장 해당 동작과 모양은 하 여 Windows Forms DataGridView 컨트롤에서 사용자 지정 셀 및 열](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-157">For more information, see [How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md).</span></span>  
  
-   <span data-ttu-id="48f18-158">기본 제공 열 형식으로 제공 되지 않는 호스트 컨트롤에 사용자 고유의 셀과 열 클래스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-158">You can implement your own cell and column classes to host controls other than the ones provided by the built-in column types.</span></span> <span data-ttu-id="48f18-159">자세한 내용은 참조 [하는 방법: Windows Forms DataGridView 셀에서 호스트 컨트롤](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="48f18-159">For more information, see [How to: Host Controls in Windows Forms DataGridView Cells](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f18-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48f18-160">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="48f18-161">DataGridView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="48f18-161">DataGridView Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)
