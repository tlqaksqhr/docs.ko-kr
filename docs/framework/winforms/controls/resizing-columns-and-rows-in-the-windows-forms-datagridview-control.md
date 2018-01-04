---
title: "Windows Forms DataGridView 컨트롤의 열 및 행 크기 조정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c1c11ca487003e57a499b3ff46178350e6aad404
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="c0729-102">Windows Forms DataGridView 컨트롤의 열 및 행 크기 조정</span><span class="sxs-lookup"><span data-stu-id="c0729-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c0729-103">`DataGridView` 컨트롤의 열 및 행의 크기 조정 동작을 사용자 지정 하기 위한 다양 한 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="c0729-104">일반적으로 `DataGridView` 셀 크기를 조정 하지 않으면 해당 내용에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="c0729-105">대신, 표시 된 값을 셀 보다 큰 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="c0729-106">콘텐츠를 문자열로 표시 될 수를 셀 도구 설명에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="c0729-107">기본적으로 사용자가 행, 열 및 자세한 정보를 표시할 마우스로 머리글 구분선을 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="c0729-108">사용자가 자동으로 조정 하는 내용에 따라 관련된 행, 열 또는 헤더 대역 외에 구분선 두 번 클릭 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="c0729-109">`DataGridView` 컨트롤은 속성, 메서드 및 사용자 지정 하거나 모든 이러한 사용자 조정 동작을 비활성화할 수 있도록 하는 이벤트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="c0729-110">또한 프로그래밍 방식으로 크기를 조정할 수 행, 열 및 해당 내용에 맞게 머리글 또는 내용이 변경 될 때마다 스스로 자동으로 조정 하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="c0729-111">열을 자동으로 지정 하는 비율로 제어의 사용 가능한 너비를 분배할를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0729-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c0729-112">In This Section</span></span>  
 [<span data-ttu-id="c0729-113">Windows Forms DataGridView 컨트롤의 크기 조정 옵션</span><span class="sxs-lookup"><span data-stu-id="c0729-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c0729-114">크기 조정 행, 열 및 헤더에 대 한 옵션을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="c0729-115">또한 크기 조정 관련 속성 및 메서드의에 대해 자세히 설명 하 고 일반적인 사용 시나리오에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="c0729-116">Windows Forms DataGridView 컨트롤의 열 채우기 모드</span><span class="sxs-lookup"><span data-stu-id="c0729-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c0729-117">열 채우기 모드를 자세히 설명 하 고 열 채우기 모드 및 다른 모드 실험 하는 데 사용할 수 있는 데모 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="c0729-118">방법: Windows Forms DataGridView 컨트롤의 크기 조정 모드 설정</span><span class="sxs-lookup"><span data-stu-id="c0729-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="c0729-119">일반적인 목적에 대 한 크기 조정 모드를 구성 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="c0729-120">방법: Windows Forms DataGridView 컨트롤에서 내용에 맞게 프로그래밍 방식으로 셀 크기 조정</span><span class="sxs-lookup"><span data-stu-id="c0729-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="c0729-121">프로그래밍 방식으로 크기 실험 하는 데 사용할 수 있는 예제 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="c0729-122">방법: Windows Forms DataGridView 컨트롤에서 내용이 변경되는 경우 자동으로 셀 크기 조정</span><span class="sxs-lookup"><span data-stu-id="c0729-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="c0729-123">자동 크기 조정 모드를 시험 하는 데 사용할 수 있는 예제 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c0729-124">참조</span><span class="sxs-lookup"><span data-stu-id="c0729-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="c0729-125"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c0729-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0729-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0729-126">See Also</span></span>  
 [<span data-ttu-id="c0729-127">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c0729-127">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
