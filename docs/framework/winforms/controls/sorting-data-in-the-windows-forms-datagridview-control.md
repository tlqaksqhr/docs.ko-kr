---
title: "Windows Forms DataGridView 컨트롤의 데이터 정렬"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2327c6d9696bc5fb54943eb8bbce9d4795a378b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2eaa4-102">Windows Forms DataGridView 컨트롤의 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="2eaa4-102">Sorting Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2eaa4-103">기본적으로 사용자의 데이터를 정렬할 수는 `DataGridView` 텍스트 상자 열 머리글을 클릭 하 여 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-103">By default, users can sort the data in a `DataGridView` control by clicking the header of a text box column.</span></span> <span data-ttu-id="2eaa4-104">수정할 수 있습니다는 `SortMode` 사용자가 작업을 수행 하는 경우 다른 형식의 열을 정렬할 수 있도록 특정 열 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-104">You can modify the `SortMode` property of specific columns to allow users to sort by other column types when it makes sense to do so.</span></span> <span data-ttu-id="2eaa4-105">임의의 열 또는 여러 열으로 프로그래밍 방식으로 데이터를 정렬할 수 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-105">You can also sort the data programmatically by any column, or by multiple columns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2eaa4-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2eaa4-106">In This Section</span></span>  
 [<span data-ttu-id="2eaa4-107">Windows Forms DataGridView 컨트롤의 열 정렬 모드</span><span class="sxs-lookup"><span data-stu-id="2eaa4-107">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2eaa4-108">컨트롤의 데이터 정렬에 대 한 옵션에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-108">Describes the options for sorting data in the control.</span></span>  
  
 [<span data-ttu-id="2eaa4-109">방법: Windows Forms DataGridView 컨트롤의 열 정렬 모드 설정</span><span class="sxs-lookup"><span data-stu-id="2eaa4-109">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)  
 <span data-ttu-id="2eaa4-110">사용자가 기본적으로 정렬 가능 하지 않은 열을 정렬할 수 있도록 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-110">Describes how to enable users to sort by columns that are not sortable by default.</span></span>  
  
 [<span data-ttu-id="2eaa4-111">방법: Windows Forms DataGridView 컨트롤에서 정렬 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="2eaa4-111">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2eaa4-112">프로그래밍 방식으로 데이터를 정렬 하는 방법 및 정렬을 사용 하 여 사용자 지정 하는 방법에 설명 된 <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> 이벤트 또는 구현 하 여는 <xref:System.Collections.IComparer> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-112">Describes how to sort data programmatically and how to customize sorting by using the <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> event or by implementing the <xref:System.Collections.IComparer> interface.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2eaa4-113">참조</span><span class="sxs-lookup"><span data-stu-id="2eaa4-113">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="2eaa4-114"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-114">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
 <span data-ttu-id="2eaa4-115">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.Sort%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-115">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.Sort%2A> method.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="2eaa4-116">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-116">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumnSortMode>  
 <span data-ttu-id="2eaa4-117">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewColumnSortMode> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumeration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eaa4-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2eaa4-118">See Also</span></span>  
 [<span data-ttu-id="2eaa4-119">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2eaa4-119">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="2eaa4-120">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="2eaa4-120">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
