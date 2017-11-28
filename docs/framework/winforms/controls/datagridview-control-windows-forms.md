---
title: "DataGridView 컨트롤(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tables [Windows Forms]
- data grids [Windows Forms
- data [Windows Forms], displaying in tabular format
- grid controls [Windows Forms]
- datasets [Windows Forms], user interface
- Windows Forms, displaying data
- data presentation
- tabular data [Windows Forms], displaying on Windows Forms
- datasets [Windows Forms], displaying in DataGridView control
- DataGridView control [Windows Forms]
ms.assetid: dbee73f2-bba6-4874-9389-cd21d44309be
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08a0cc15cff39bb936a78db95c73568aa643d0b6
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="datagridview-control-windows-forms"></a><span data-ttu-id="dad4e-102">DataGridView 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="dad4e-102">DataGridView Control (Windows Forms)</span></span>
<span data-ttu-id="dad4e-103">`DataGridView` 컨트롤에서는 데이터를 표 형식으로 표시하는 강력하고 유연한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-103">The `DataGridView` control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="dad4e-104">`DataGridView` 컨트롤을 사용하여 적은 양의 데이터에 대한 읽기 전용 보기를 표시하거나, 컨트롤을 확장하여 매우 큰 데이터 집합에 대한 편집 가능한 보기를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-104">You can use the `DataGridView` control to show read-only views of a small amount of data, or you can scale it to show editable views of very large sets of data.</span></span>  
  
 <span data-ttu-id="dad4e-105">다양한 방법으로 `DataGridView` 컨트롤을 확장하여 사용자 지정 동작을 응용 프로그램에 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-105">You can extend the `DataGridView` control in a number of ways to build custom behaviors into your applications.</span></span> <span data-ttu-id="dad4e-106">예를 들어 프로그래밍 방식으로 고유한 정렬 알고리즘을 지정하고 고유한 셀 형식을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-106">For example, you can programmatically specify your own sorting algorithms, and you can create your own types of cells.</span></span> <span data-ttu-id="dad4e-107">여러 속성 중에서 선택하여 `DataGridView` 컨트롤의 모양을 쉽게 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-107">You can easily customize the appearance of the `DataGridView` control by choosing among several properties.</span></span> <span data-ttu-id="dad4e-108">대부분 데이터 저장소 형식을 데이터 소스로 사용하거나 `DataGridView` 컨트롤을 바인딩된 데이터 소스 없이 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-108">Many types of data stores can be used as a data source, or the `DataGridView` control can operate with no data source bound to it.</span></span>  
  
 <span data-ttu-id="dad4e-109">이 섹션의 항목에서는 `DataGridView` 기능을 응용 프로그램에 빌드하는 데 사용할 수 있는 개념 및 기술을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-109">The topics in this section describe the concepts and techniques that you can use to build `DataGridView` features into your applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dad4e-110">단원 내용</span><span class="sxs-lookup"><span data-stu-id="dad4e-110">In This Section</span></span>  
 [<span data-ttu-id="dad4e-111">DataGridView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="dad4e-111">DataGridView Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 <span data-ttu-id="dad4e-112">Windows Forms `DataGridView` 컨트롤의 아키텍처와 핵심 개념을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-112">Provides topics that describe the architecture and core concepts of the Windows Forms `DataGridView` control.</span></span>  
  
 [<span data-ttu-id="dad4e-113">Windows Forms DataGridView 컨트롤의 기본 기능</span><span class="sxs-lookup"><span data-stu-id="dad4e-113">Default Functionality in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dad4e-114">데이터 소스에 바인딩될 때 Windows Forms `DataGridView` 컨트롤의 기본 모양과 동작에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-114">Describes the default appearance and behavior of the Windows Forms `DataGridView` control when it is bound to a data source.</span></span>  
  
 [<span data-ttu-id="dad4e-115">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="dad4e-115">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dad4e-116">데이터를 표시하고 사용자가 데이터를 수정 또는 추가할 수 있도록 하는 데 사용되는 Windows Forms `DataGridView` 컨트롤의 열 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-116">Describes the column types in the Windows Forms `DataGridView` control used to display data and allow users to modify or add data.</span></span>  
  
 [<span data-ttu-id="dad4e-117">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="dad4e-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="dad4e-118">일반적으로 사용되는 셀, 행 및 열 속성을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-118">Provides topics that describe commonly-used cell, row, and column properties.</span></span>  
  
 [<span data-ttu-id="dad4e-119">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="dad4e-119">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dad4e-120">컨트롤의 기본 모양과 셀 데이터의 표시 형식을 수정하는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-120">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="dad4e-121">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="dad4e-121">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dad4e-122">수동으로 또는 외부 데이터 소스에서 컨트롤을 데이터로 채우는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-122">Provides topics that describe how to populate the control with data either manually, or from an external data source.</span></span>  
  
 [<span data-ttu-id="dad4e-123">Windows Forms DataGridView 컨트롤의 열 및 행 크기 조정</span><span class="sxs-lookup"><span data-stu-id="dad4e-123">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dad4e-124">셀 내용에 맞추거나 컨트롤의 사용 가능한 너비에 맞춰서 행 및 열 크기를 자동으로 조정할 수 있는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-124">Provides topics that describe how the size of rows and columns can be adjusted automatically to fit cell content or to fit the available width of the control.</span></span>  
  
 [<span data-ttu-id="dad4e-125">Windows Forms DataGridView 컨트롤의 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="dad4e-125">Sorting Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dad4e-126">컨트롤의 정렬 기능을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-126">Provides topics that describe the sorting features in the control.</span></span>  
  
 [<span data-ttu-id="dad4e-127">Windows Forms DataGridView 컨트롤의 데이터 입력</span><span class="sxs-lookup"><span data-stu-id="dad4e-127">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dad4e-128">사용자가 컨트롤에서 데이터를 추가 및 수정하는 방법을 변경하는 방법에 대해 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-128">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
 [<span data-ttu-id="dad4e-129">Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용</span><span class="sxs-lookup"><span data-stu-id="dad4e-129">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dad4e-130">컨트롤의 셀, 행 및 열 선택 기능을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-130">Provides topics that describe the cell, row, and column selection features in the control.</span></span>  
  
 [<span data-ttu-id="dad4e-131">Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="dad4e-131">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="dad4e-132">셀, 행 및 열 개체를 사용하여 프로그래밍하는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-132">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
 [<span data-ttu-id="dad4e-133">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="dad4e-133">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dad4e-134">`DataGridView` 셀 및 행의 사용자 지정 그리기를 수행하고 파생된 셀, 열 및 행 형식을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-134">Provides topics that describe custom painting `DataGridView` cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="dad4e-135">Windows Forms DataGridView 컨트롤의 성능 조정</span><span class="sxs-lookup"><span data-stu-id="dad4e-135">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dad4e-136">컨트롤을 효율적으로 사용하여 대용량 데이터를 사용할 때 성능 문제를 방지하는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-136">Provides topics that describe how to use the control efficiently to avoid performance problems when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="dad4e-137">Windows Forms DataGridView 컨트롤에서의 기본 키보드 및 마우스 처리</span><span class="sxs-lookup"><span data-stu-id="dad4e-137">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dad4e-138">사용자가 키보드와 마우스를 통해 `DataGridView` 컨트롤을 조작할 수 있는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-138">Describes how users can interact with the `DataGridView` control through a keyboard and a mouse.</span></span>  
  
 [<span data-ttu-id="dad4e-139">Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점</span><span class="sxs-lookup"><span data-stu-id="dad4e-139">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)  
 <span data-ttu-id="dad4e-140">`DataGridView` 컨트롤로 <xref:System.Windows.Forms.DataGrid> 컨트롤을 개선하고 대체하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-140">Describes how the `DataGridView` control improves upon and replaces the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
 <span data-ttu-id="dad4e-141">또한 참조 [디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤에서](http://msdn.microsoft.com/library/ms171593\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-141">Also see [Using the Designer with the Windows Forms DataGridView Control](http://msdn.microsoft.com/library/ms171593\(v=vs.110\)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dad4e-142">참조</span><span class="sxs-lookup"><span data-stu-id="dad4e-142">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="dad4e-143"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-143">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="dad4e-144"><xref:System.Windows.Forms.BindingSource> 구성 요소에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-144">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="dad4e-145"><xref:System.Windows.Forms.DataGridView> 컨트롤과 <xref:System.Windows.Forms.BindingSource> 구성 요소는 서로 긴밀하게 작동하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dad4e-145">The <xref:System.Windows.Forms.DataGridView> control and the <xref:System.Windows.Forms.BindingSource> component are designed to work closely together.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dad4e-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dad4e-146">See Also</span></span>  
 [<span data-ttu-id="dad4e-147">Windows Forms에서 사용할 컨트롤</span><span class="sxs-lookup"><span data-stu-id="dad4e-147">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
