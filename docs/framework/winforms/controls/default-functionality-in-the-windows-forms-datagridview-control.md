---
title: "Windows Forms DataGridView 컨트롤의 기본 기능"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d6b15085c301f074ef6fcf9e60a75299c4b245b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="9f98a-102">Windows Forms DataGridView 컨트롤의 기본 기능</span><span class="sxs-lookup"><span data-stu-id="9f98a-102">Default Functionality in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="9f98a-103">Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤은 상당한 양의 기본 기능으로 사용자가 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f98a-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control provides users with a significant amount of default functionality.</span></span>  
  
## <a name="default-functionality"></a><span data-ttu-id="9f98a-104">기본 기능</span><span class="sxs-lookup"><span data-stu-id="9f98a-104">Default Functionality</span></span>  
 <span data-ttu-id="9f98a-105">기본적으로는 <xref:System.Windows.Forms.DataGridView> 제어:</span><span class="sxs-lookup"><span data-stu-id="9f98a-105">By default, a <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <span data-ttu-id="9f98a-106">열 머리글 및 행 머리글 계속 표시 되는 테이블을 세로로 스크롤할 때는 자동으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f98a-106">Automatically displays column headers and row headers that remain visible as the table scrolls vertically.</span></span>  
  
-   <span data-ttu-id="9f98a-107">현재 행에 대 한 선택 표시기를 포함 하는 행 헤더를 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f98a-107">Has a row header that contains a selection indicator for the current row.</span></span>  
  
-   <span data-ttu-id="9f98a-108">선택 영역 직사각형 첫 번째 셀에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f98a-108">Has a selection rectangle in the first cell.</span></span>  
  
-   <span data-ttu-id="9f98a-109">열 구분선을 두 번 클릭할 때 자동으로 조정할 수 있는 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f98a-109">Has columns that can be automatically resized when the user double-clicks the column dividers.</span></span>  
  
-   <span data-ttu-id="9f98a-110">Windows XP 및 Windows Server 2003 제품군에서 비주얼 스타일을 자동으로 지원 때는 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 에서 응용 프로그램의 메서드는 `Main` 메서드.</span><span class="sxs-lookup"><span data-stu-id="9f98a-110">Automatically supports visual styles on Windows XP and the Windows Server 2003 family when the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method is called from the application's `Main` method.</span></span>  
  
 <span data-ttu-id="9f98a-111">또한의 콘텐츠는 <xref:System.Windows.Forms.DataGridView> 기본적으로 컨트롤을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f98a-111">Additionally, the contents of a <xref:System.Windows.Forms.DataGridView> control can be edited by default:</span></span>  
  
-   <span data-ttu-id="9f98a-112">사용자가 두 번 클릭 또는 셀에서 f2 키를 누를 경우 컨트롤 자동으로 셀을 편집 모드로 전환 하 고 사용자가 셀의 내용을 업데이트.</span><span class="sxs-lookup"><span data-stu-id="9f98a-112">If the user double-clicks or presses F2 in a cell, the control automatically puts the cell into edit mode and updates the contents of the cell as the user types.</span></span>  
  
-   <span data-ttu-id="9f98a-113">사용자가 눈금의 끝에 스크롤할 사용자는 새 레코드를 추가 하는 한 개의 행이 있는지 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f98a-113">If the user scrolls to the end of the grid, the user will see that a row for adding new records is present.</span></span> <span data-ttu-id="9f98a-114">이 행을 클릭 하면 새 행에 추가 됩니다는 <xref:System.Windows.Forms.DataGridView> 기본 값으로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f98a-114">When the user clicks this row, a new row is added to the <xref:System.Windows.Forms.DataGridView> control, with default values.</span></span> <span data-ttu-id="9f98a-115">사용자가 esc 키를 누르면이 새 행이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="9f98a-115">When the user presses ESC, this new row disappears.</span></span>  
  
-   <span data-ttu-id="9f98a-116">사용자가 행 머리글을 클릭 하면 전체 행이 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f98a-116">If the user clicks a row header, the whole row is selected.</span></span>  
  
 <span data-ttu-id="9f98a-117">바인딩하는 경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터 소스를 설정 하 여 해당 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성, 컨트롤:</span><span class="sxs-lookup"><span data-stu-id="9f98a-117">When you bind a <xref:System.Windows.Forms.DataGridView> control to a data source by setting its <xref:System.Windows.Forms.DataGridView.DataSource%2A> property, the control:</span></span>  
  
-   <span data-ttu-id="9f98a-118">열 머리글 텍스트 데이터 원본 열의 이름을 자동으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f98a-118">Automatically uses the names of the data source's columns as the column header text.</span></span>  
  
-   <span data-ttu-id="9f98a-119">데이터 원본의 내용으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9f98a-119">Is populated with the contents of the data source.</span></span> <span data-ttu-id="9f98a-120"><xref:System.Windows.Forms.DataGridView>열은 데이터 원본의 각 열에 대해 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9f98a-120"><xref:System.Windows.Forms.DataGridView> columns are automatically created for each column in the data source.</span></span>  
  
-   <span data-ttu-id="9f98a-121">테이블에 표시 되는 각 행에 대 한 행을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9f98a-121">Creates a row for each visible row in the table.</span></span>  
  
-   <span data-ttu-id="9f98a-122">열 머리글을 마우스 오른쪽 단추로 클릭할 때 기본 데이터에 따라 행을 자동으로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f98a-122">Automatically sorts the rows based on the underlying data when the user clicks a column header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f98a-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f98a-123">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="9f98a-124">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9f98a-124">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
