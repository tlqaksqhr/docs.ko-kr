---
title: "Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 888fb1cbd960c006dc2705a2b0bd66c038a926f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="4828c-102">Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용</span><span class="sxs-lookup"><span data-stu-id="4828c-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4828c-103">`DataGridView` 컨트롤에서는 다양 한 셀, 행 및 열 사용자가 방법을 선택할 수 구성 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4828c-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="4828c-104">예를 들어 가능 단일 또는 여러 선택 영역, 전체 행 또는 사용자가 셀을 클릭할 때 열을 선택 또는 전체 행 또는 열을 선택할 사용자가 머리글을 클릭할 경우에 셀 선택도를 매핑함으로써 합니다.</span><span class="sxs-lookup"><span data-stu-id="4828c-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="4828c-105">선택에 대 한 고유의 사용자 인터페이스를 제공 하려는 경우에 일반적인 선택을 사용 하지 않도록 설정할 수 있으며 모든 선택 항목을 프로그래밍 방식으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4828c-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="4828c-106">또한 사용자가 선택한 값을 클립보드에 복사할 수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4828c-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4828c-107">단원 내용</span><span class="sxs-lookup"><span data-stu-id="4828c-107">In This Section</span></span>  
 [<span data-ttu-id="4828c-108">Windows Forms DataGridView 컨트롤의 선택 모드</span><span class="sxs-lookup"><span data-stu-id="4828c-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4828c-109">사용자 및 컨트롤의 프로그래밍 방식으로 선택에 대 한 옵션을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4828c-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="4828c-110">방법: Windows Forms DataGridView 컨트롤의 선택 모드 설정</span><span class="sxs-lookup"><span data-stu-id="4828c-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="4828c-111">사용자가 셀을 클릭 하면 단일 행 선택에 대 한 제어를 구성 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4828c-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="4828c-112">방법: Windows Forms DataGridView 컨트롤에서 선택한 셀, 행 및 열 가져오기</span><span class="sxs-lookup"><span data-stu-id="4828c-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="4828c-113">선택한 셀, 행 및 열 컬렉션을 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4828c-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="4828c-114">방법: Windows Forms DataGridView 컨트롤에서 사용자가 여러 셀을 클립보드에 복사할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="4828c-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="4828c-115">컨트롤의 클립보드 지원을 사용 하도록 설정 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4828c-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4828c-116">참조</span><span class="sxs-lookup"><span data-stu-id="4828c-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="4828c-117"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4828c-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="4828c-118">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4828c-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="4828c-119">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4828c-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="4828c-120">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4828c-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="4828c-121">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4828c-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="4828c-122">에 대 한 참조 설명서를 제공는 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4828c-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4828c-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4828c-123">See Also</span></span>  
 [<span data-ttu-id="4828c-124">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="4828c-124">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="4828c-125">Windows Forms DataGridView 컨트롤에서의 기본 키보드 및 마우스 처리</span><span class="sxs-lookup"><span data-stu-id="4828c-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
