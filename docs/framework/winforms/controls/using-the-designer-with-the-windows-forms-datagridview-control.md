---
title: "Windows Forms DataGridView 컨트롤에 디자이너 사용"
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
- DataGridView control [Windows Forms], designer support
- formatting [Windows Forms]
ms.assetid: b66057a6-5983-4864-b4e7-8cbc88a7010c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9df10ecabc8f61c3ef984adb6466f195395fd181
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-designer-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="c741a-102">Windows Forms DataGridView 컨트롤에 디자이너 사용</span><span class="sxs-lookup"><span data-stu-id="c741a-102">Using the Designer with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="c741a-103">Visual Studio에 대 한 디자이너 지원을 제공는 `DataGridView` 제어 코드를 작성 하지 않고도 여러 설정 작업을 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c741a-103">Visual Studio provides designer support for the `DataGridView` control that enables you to perform many setup tasks without writing code.</span></span> <span data-ttu-id="c741a-104">이러한 작업에는 열을 수정 하는 데이터 소스에 컨트롤 데이터를 표시 하는 데 사용 되는 바인딩 및 모양 및 컨트롤의 기본 동작을 조정 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c741a-104">These tasks include binding the control to a data source, modifying the columns used to display data, and adjusting the appearance and basic behavior of the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c741a-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c741a-105">In This Section</span></span>  
 [<span data-ttu-id="c741a-106">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="c741a-106">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c741a-107">사용 하는 방법에 설명 된 **열 추가** 및 **열 편집** 을 채우고 columns 컬렉션 수정 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="c741a-107">Describes how to use the **Add Columns** and **Edit Columns** dialog boxes to populate and modify the columns collection.</span></span>  
  
 [<span data-ttu-id="c741a-108">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="c741a-108">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/bind-data-to-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c741a-109">사용 하는 방법에 설명 된 **데이터 소스 선택** 데이터에 연결 하는 컨트롤의 스마트 태그 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c741a-109">Describes how to use the **Choose Data Source** option on the control's smart tag to connect to data.</span></span>  
  
 [<span data-ttu-id="c741a-110">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 순서 변경</span><span class="sxs-lookup"><span data-stu-id="c741a-110">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c741a-111">사용 하는 방법에 설명 된 **열 편집** 대화 상자를 열 다시 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="c741a-111">Describes how to use the **Edit Columns** dialog box to rearrange columns.</span></span>  
  
 [<span data-ttu-id="c741a-112">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤의 형식 변경</span><span class="sxs-lookup"><span data-stu-id="c741a-112">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 <span data-ttu-id="c741a-113">사용 하는 방법에 설명 된 **열 편집** 열 유형을 변경 하려면 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="c741a-113">Describes how to use the **Edit Columns** dialog box to change column types.</span></span>  
  
 [<span data-ttu-id="c741a-114">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용</span><span class="sxs-lookup"><span data-stu-id="c741a-114">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c741a-115">사용자가 열을 다시 정렬할 수 있도록 컨트롤의 스마트 태그를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c741a-115">Describes how to use the control's smart tag to enable users to rearrange columns.</span></span>  
  
 [<span data-ttu-id="c741a-116">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 고정</span><span class="sxs-lookup"><span data-stu-id="c741a-116">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c741a-117">사용 하는 방법에 설명 된 **열 편집** 스크롤에서 특정 열을 방지 하기 위해 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="c741a-117">Describes how to use the **Edit Columns** dialog box to prevent specific columns from scrolling.</span></span>  
  
 [<span data-ttu-id="c741a-118">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 고정</span><span class="sxs-lookup"><span data-stu-id="c741a-118">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c741a-119">사용 하는 방법에 설명 된 **열 편집** 특정 열을 숨기는 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="c741a-119">Describes how to use the **Edit Columns** dialog box to hide specific columns.</span></span>  
  
 [<span data-ttu-id="c741a-120">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열을 읽기 전용으로 설정</span><span class="sxs-lookup"><span data-stu-id="c741a-120">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c741a-121">사용 하는 방법에 설명 된 **열 편집** 특정 열에 값을 편집 하지 못하게 하려면 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="c741a-121">Describes how to use the **Edit Columns** dialog box to prevent users from editing values in specific columns.</span></span>  
  
 [<span data-ttu-id="c741a-122">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제 금지</span><span class="sxs-lookup"><span data-stu-id="c741a-122">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c741a-123">사용자가 추가 하거나 행 삭제를 방지 하기 위해 컨트롤의 스마트 태그를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c741a-123">Describes how to use the control's smart tag to prevent users from adding or deleting rows.</span></span>  
  
 [<span data-ttu-id="c741a-124">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="c741a-124">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="c741a-125">사용 하는 방법에 설명 된 **CellStyle 작성기** 대화 상자 컨트롤에는 장부를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c741a-125">Describes how to use the **CellStyle Builder** dialog box to create a ledger-like appearance in the control.</span></span>  
  
 [<span data-ttu-id="c741a-126">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 기본 셀 스타일 및 데이터 형식 설정</span><span class="sxs-lookup"><span data-stu-id="c741a-126">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/default-cell-styles-datagridview.md)  
 <span data-ttu-id="c741a-127">사용 하는 방법에 설명 된 **CellStyle 작성기** 기본 모양과 데이터 표시를 설정 하려면 대화 상자 컨트롤에 대 한 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c741a-127">Describes how to use the **CellStyle Builder** dialog box to set up the basic appearance and data-display formats for the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c741a-128">참조</span><span class="sxs-lookup"><span data-stu-id="c741a-128">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="c741a-129"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c741a-129">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c741a-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c741a-130">See Also</span></span>  
 [<span data-ttu-id="c741a-131">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c741a-131">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
