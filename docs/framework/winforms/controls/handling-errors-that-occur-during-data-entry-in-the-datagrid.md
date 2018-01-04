---
title: "연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 016a30e4b578ead199124d70cc12f240c74bf370
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="26f85-102">연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리</span><span class="sxs-lookup"><span data-stu-id="26f85-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="26f85-103">내부 데이터 저장소에서 오류를 처리 하는 것은 데이터 입력 응용 프로그램에 대 한 필수 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="26f85-104">Windows Forms <xref:System.Windows.Forms.DataGridView> 제어 작업을 편리 노출 하 여는 <xref:System.Windows.Forms.DataGridView.DataError> 데이터 저장소는 비즈니스 규칙 또는 제약 조건 위반을 감지할 때 발생 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>  
  
 <span data-ttu-id="26f85-105">이 연습에서는 행을 검색 합니다는 `Customers` Northwind 샘플 데이터베이스의 테이블을 표시 한 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="26f85-106">에 중복 된 `CustomerID` 새 행 이나는 편집된 된 기존 행에 값이 검색 되는 <xref:System.Windows.Forms.DataGridView.DataError> 표시 하 여 처리 되는 이벤트가 발생 합니다는 <xref:System.Windows.Forms.MessageBox> 예외를 설명 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>  
  
 <span data-ttu-id="26f85-107">단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법: 처리 오류는 발생 하는 동안 데이터 입력 Windows Forms DataGridView 컨트롤에서](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="26f85-108">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="26f85-108">Prerequisites</span></span>  
 <span data-ttu-id="26f85-109">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-109">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="26f85-110">Northwind SQL Server 예제 데이터베이스에 있는 서버에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-110">Access to a server that has the Northwind SQL Server sample database.</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="26f85-111">폼 만들기</span><span class="sxs-lookup"><span data-stu-id="26f85-111">Creating the Form</span></span>  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="26f85-112">DataGridView 컨트롤에서 데이터 입력 오류를 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="26f85-112">To handle data-entry errors in the DataGridView control</span></span>  
  
1.  <span data-ttu-id="26f85-113">파생 되는 클래스를 만듭니다 <xref:System.Windows.Forms.Form> 포함 한 <xref:System.Windows.Forms.DataGridView> 제어 및 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     <span data-ttu-id="26f85-114">다음 코드 예제에서는 기본 초기화를 제공 하 고 포함 된 `Main` 메서드.</span><span class="sxs-lookup"><span data-stu-id="26f85-114">The following code example provides basic initialization and includes a `Main` method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  <span data-ttu-id="26f85-115">폼의 클래스 정의 처리 하는 데이터베이스에 대 한 연결 정보에는 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>  
  
     <span data-ttu-id="26f85-116">사용 하 여이 코드 예제는 `GetData` 채워진 반환 하는 메서드 <xref:System.Data.DataTable> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="26f85-117">설정 하는 `connectionString` 변수를 사용 중인 데이터베이스에 대 한 적합 한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="26f85-118">암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="26f85-119">데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="26f85-120">자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26f85-120">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  <span data-ttu-id="26f85-121">폼의에 대 한 처리기를 구현 <xref:System.Windows.Forms.Form.Load> 초기화 하는 이벤트는 <xref:System.Windows.Forms.DataGridView> 및 <xref:System.Windows.Forms.BindingSource> 데이터 바인딩을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  <span data-ttu-id="26f85-122">처리는 <xref:System.Windows.Forms.DataGridView.DataError> 이벤트에는 <xref:System.Windows.Forms.DataGridView>합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     <span data-ttu-id="26f85-123">오류에 대 한 컨텍스트가 커밋 작업에 오류를 표시 한 <xref:System.Windows.Forms.MessageBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="26f85-124">응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="26f85-124">Testing the Application</span></span>  
 <span data-ttu-id="26f85-125">이제 예상 대로 동작 되도록 폼을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-125">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="26f85-126">양식을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="26f85-126">To test the form</span></span>  
  
-   <span data-ttu-id="26f85-127">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-127">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="26f85-128">표시 됩니다는 <xref:System.Windows.Forms.DataGridView> Customers 테이블의 데이터로 채워진 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="26f85-129">에 대 한 중복 값을 입력 하면 `CustomerID` 및 편집, 셀 값을 자동으로 되돌아갑니다 커밋하고 표시 됩니다는 <xref:System.Windows.Forms.MessageBox> 데이터 입력 오류를 표시 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="26f85-130">다음 단계</span><span class="sxs-lookup"><span data-stu-id="26f85-130">Next Steps</span></span>  
 <span data-ttu-id="26f85-131">이 응용 프로그램에서는 기본적으로 이해는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="26f85-132">모양 및 동작을 사용자 지정할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 여러 가지 방법으로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
-   <span data-ttu-id="26f85-133">테두리 및 머리글 스타일을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-133">Change border and header styles.</span></span> <span data-ttu-id="26f85-134">자세한 내용은 참조 [하는 방법: 테두리 및 눈금선 스타일 Windows Forms DataGridView 컨트롤에서 변경](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="26f85-135">사용 하거나 사용자 입력을 제한 된 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="26f85-136">자세한 내용은 참조 [하는 방법: 행 추가 및 삭제 금지 Windows Forms DataGridView 컨트롤에서](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), 및 [하는 방법: 열을 읽기 전용 Windows Forms DataGridView 컨트롤에서](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="26f85-137">에 대 한 사용자 입력 유효성 검사는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="26f85-138">자세한 내용은 참조 [연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="26f85-139">가상 모드를 사용 하 여 매우 큰 데이터 집합을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="26f85-140">자세한 내용은 참조 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="26f85-141">셀의 모양을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-141">Customize the appearance of cells.</span></span> <span data-ttu-id="26f85-142">자세한 내용은 참조 [하는 방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) 및 [하는 방법: Windows Forms DataGridView 컨트롤에 대 한 기본 셀 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="26f85-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26f85-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26f85-143">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="26f85-144">Windows Forms DataGridView 컨트롤의 데이터 입력</span><span class="sxs-lookup"><span data-stu-id="26f85-144">Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="26f85-145">방법: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리</span><span class="sxs-lookup"><span data-stu-id="26f85-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [<span data-ttu-id="26f85-146">연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="26f85-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="26f85-147">연결 정보 보호</span><span class="sxs-lookup"><span data-stu-id="26f85-147">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)
