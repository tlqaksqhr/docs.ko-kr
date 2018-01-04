---
title: "Windows Forms DataGridView 컨트롤의 데이터 입력"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], data entry
- data entry [Windows Forms], dataGridView control
- data grids [Windows Forms], data entry
ms.assetid: 4a6d4676-d4e7-4b0e-9c22-50ce65ffe0d6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 399520738c53e149e7a5539a62a5d4599e26a8da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2495c-102">Windows Forms DataGridView 컨트롤의 데이터 입력</span><span class="sxs-lookup"><span data-stu-id="2495c-102">Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2495c-103">`DataGridView` 컨트롤 사용자가 추가 또는 컨트롤의 데이터를 수정할 방식을 변경할 수 있는 여러 가지 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-103">The `DataGridView` control provides several features that let you change how users add or modify data in the control.</span></span> <span data-ttu-id="2495c-104">예를 들어 가능 데이터 입력 보다 효율적인 새 행에 대 한 기본 값을 제공 하 고 오류 발생 시 사용자가 경고 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-104">For example, you can make data entry more efficient by providing default values for new rows and by alerting users when errors occur.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2495c-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2495c-105">In This Section</span></span>  
 [<span data-ttu-id="2495c-106">방법: Windows Forms DataGridView 컨트롤에 편집 모드 지정</span><span class="sxs-lookup"><span data-stu-id="2495c-106">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2495c-107">사용자가 셀 편집 시작 방식을 변경 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-107">Describes how to change the way users start editing cells.</span></span>  
  
 [<span data-ttu-id="2495c-108">방법: Windows Forms DataGridView 컨트롤에서 새 행에 기본값 지정</span><span class="sxs-lookup"><span data-stu-id="2495c-108">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)  
 <span data-ttu-id="2495c-109">데이터 입력 시간 절약을 위해 새 레코드에 대 한 행을 채우는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-109">Describes how to prepopulate the row for new records to save data-entry time.</span></span>  
  
 [<span data-ttu-id="2495c-110">Windows Forms DataGridView 컨트롤에서 새 레코드에 행 사용</span><span class="sxs-lookup"><span data-stu-id="2495c-110">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2495c-111">자세한 정보를 숨길 수의 모양을 사용자 지정 및에 연결 하는 방법 정보를 포함 하 여 새 레코드에 대 한 행에 설명 된 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-111">Describes the row for new records in detail, including information on hiding it, on customizing its appearance, and on how it relates to the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span>  
  
 [<span data-ttu-id="2495c-112">연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="2495c-112">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2495c-113">데이터 입력 형식 지정 오류를 방지 하기 위해 사용자 입력의 유효성을 검사 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-113">Describes how to validate user input to prevent data-entry formatting errors.</span></span>  
  
 [<span data-ttu-id="2495c-114">연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리</span><span class="sxs-lookup"><span data-stu-id="2495c-114">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 <span data-ttu-id="2495c-115">사용자가 새 값을 적용할 때 데이터 원본에서 발생 하는 데이터 입력 오류를 처리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-115">Describes how to handle data-entry errors that originate from the data source when the user attempts to commit a new value.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2495c-116">참조</span><span class="sxs-lookup"><span data-stu-id="2495c-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="2495c-117"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="2495c-118">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.EditMode%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.EditMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 <span data-ttu-id="2495c-119">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataError?displayProperty=nameWithType>  
 <span data-ttu-id="2495c-120">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.DataError> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataError> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellValidating?displayProperty=nameWithType>  
 <span data-ttu-id="2495c-121">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.CellValidating> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellValidating> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2495c-122">관련 단원</span><span class="sxs-lookup"><span data-stu-id="2495c-122">Related Sections</span></span>  
 [<span data-ttu-id="2495c-123">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="2495c-123">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2495c-124">수동으로 또는 외부 데이터 원본에서 컨트롤을 데이터로 채우는 방법을 설명 하는 항목을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2495c-124">Provides topics that describe how to populate the control with data either manually or from an external data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2495c-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2495c-125">See Also</span></span>  
 [<span data-ttu-id="2495c-126">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2495c-126">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="2495c-127">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="2495c-127">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
