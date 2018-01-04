---
title: "연습: 두 개의 Windows Forms DataGridView 컨트롤을 사용 하 여 마스터-세부 폼 만들기"
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
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: af6f1bcb172543b372cbca52f54b675b6baf87d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a><span data-ttu-id="9d7c2-102">연습: 두 개의 Windows Forms DataGridView 컨트롤을 사용하여 마스터/세부 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="9d7c2-102">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="9d7c2-103">사용 하기 위한 가장 일반적인 시나리오 중 하나는 <xref:System.Windows.Forms.DataGridView> 컨트롤은는 *마스터/세부* 폼을 두 개의 데이터베이스 테이블 간의 부모/자식 관계 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-103">One of the most common scenarios for using the <xref:System.Windows.Forms.DataGridView> control is the *master/detail* form, in which a parent/child relationship between two database tables is displayed.</span></span> <span data-ttu-id="9d7c2-104">마스터 테이블에서 행을 선택 하면 해당 자식 데이터로 업데이트할 세부 테이블 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-104">Selecting rows in the master table causes the detail table to update with the corresponding child data.</span></span>  
  
 <span data-ttu-id="9d7c2-105">마스터/세부 폼을 구현 하는 것은 간의 상호 작용을 사용 하 여 쉽게는 <xref:System.Windows.Forms.DataGridView> 제어 및 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-105">Implementing a master/detail form is easy using the interaction between the <xref:System.Windows.Forms.DataGridView> control and the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="9d7c2-106">이 연습에서는 두 개를 사용 하 여 폼 빌드됩니다 <xref:System.Windows.Forms.DataGridView> 컨트롤과 두 개의 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-106">In this walkthrough, you will build the form using two <xref:System.Windows.Forms.DataGridView> controls and two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="9d7c2-107">Northwind SQL Server 예제 데이터베이스의 테이블을 관련 된 두 양식에 표시 됩니다: `Customers` 및 `Orders`합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-107">The form will show two related tables in the Northwind SQL Server sample database: `Customers` and `Orders`.</span></span> <span data-ttu-id="9d7c2-108">완료 되 면 master에서 데이터베이스의 모든 고객을 표시 하는 폼 갖습니다 <xref:System.Windows.Forms.DataGridView> 및 세부 정보에 선택한 고객에 대 한 모든 주문 <xref:System.Windows.Forms.DataGridView>합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-108">When you are finished, you will have a form that shows all the customers in the database in the master <xref:System.Windows.Forms.DataGridView> and all the orders for the selected customer in the detail <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
 <span data-ttu-id="9d7c2-109">단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법:는 마스터/세부 폼을 사용 하 여 두 개의 Windows Forms DataGridView 컨트롤 만들기](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-109">To copy the code in this topic as a single listing, see [How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9d7c2-110">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9d7c2-110">Prerequisites</span></span>  
 <span data-ttu-id="9d7c2-111">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-111">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="9d7c2-112">Northwind SQL Server 예제 데이터베이스에 있는 서버에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-112">Access to a server that has the Northwind SQL Server sample database.</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="9d7c2-113">폼 만들기</span><span class="sxs-lookup"><span data-stu-id="9d7c2-113">Creating the form</span></span>  
  
#### <a name="to-create-a-masterdetail-form"></a><span data-ttu-id="9d7c2-114">마스터/세부 폼을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9d7c2-114">To create a master/detail form</span></span>  
  
1.  <span data-ttu-id="9d7c2-115">파생 되는 클래스를 만듭니다 <xref:System.Windows.Forms.Form> 두 개가 포함 및 <xref:System.Windows.Forms.DataGridView> 컨트롤과 두 개의 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-115">Create a class that derives from <xref:System.Windows.Forms.Form> and contains two <xref:System.Windows.Forms.DataGridView> controls and two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="9d7c2-116">기본 폼 초기화를 제공 하 고 포함 하는 다음 코드는 `Main` 메서드.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-116">The following code provides basic form initialization and includes a `Main` method.</span></span> <span data-ttu-id="9d7c2-117">사용 하는 경우는 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 폼을 만드는 데 디자이너 수 디자이너 생성된 코드를 사용 하 여이 코드 대신 있지만 변수 선언에 여기에 나열 된 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-117">If you use the [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] designer to create your form, you can use the designer generated code instead of this code, but be sure to use the names shown in the variable declarations here.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2.  <span data-ttu-id="9d7c2-118">데이터베이스에 연결 하는 정보를 처리 하기 위한 폼의 클래스 정의에 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-118">Implement a method in your form's class definition for handling the detail of connecting to the database.</span></span> <span data-ttu-id="9d7c2-119">사용 하 여이 예제는 `GetData` 정보를 표시 하는 메서드는 <xref:System.Data.DataSet> 개체를 추가 하는 <xref:System.Data.DataRelation> 데이터 집합 및 바인딩 개체를는 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-119">This example uses a `GetData` method that populates a <xref:System.Data.DataSet> object, adds a <xref:System.Data.DataRelation> object to the data set, and binds the <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="9d7c2-120">`connectionString` 변수를 사용자의 데이터베이스에 적합한 값으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-120">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9d7c2-121">암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-121">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="9d7c2-122">데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-122">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="9d7c2-123">자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-123">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3.  <span data-ttu-id="9d7c2-124">폼의에 대 한 처리기를 구현 <xref:System.Windows.Forms.Form.Load> 바인딩하는 이벤트는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 <xref:System.Windows.Forms.BindingSource> 구성 요소와 호출 된 `GetData` 메서드.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-124">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that binds the <xref:System.Windows.Forms.DataGridView> controls to the <xref:System.Windows.Forms.BindingSource> components and calls the `GetData` method.</span></span> <span data-ttu-id="9d7c2-125">다음 예제에서는 크기를 조정 하는 코드를 포함 <xref:System.Windows.Forms.DataGridView> 에 표시 된 데이터에 맞게 열 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-125">The following example includes code that resizes <xref:System.Windows.Forms.DataGridView> columns to fit the displayed data.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="9d7c2-126">응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="9d7c2-126">Testing the Application</span></span>  
 <span data-ttu-id="9d7c2-127">이제 예상 대로 동작 되도록 폼을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-127">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="9d7c2-128">양식을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="9d7c2-128">To test the form</span></span>  
  
-   <span data-ttu-id="9d7c2-129">응용 프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-129">Compile and run the application.</span></span>  
  
     <span data-ttu-id="9d7c2-130">두 개의 나타납니다 <xref:System.Windows.Forms.DataGridView> 상하로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-130">You will see two <xref:System.Windows.Forms.DataGridView> controls, one above the other.</span></span> <span data-ttu-id="9d7c2-131">위에 표시 되는 northwind customers `Customers` 테이블을 마우스는 맨 아래에 `Orders` 선택한 고객에 해당 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-131">On top are the customers from the Northwind `Customers` table, and at the bottom are the `Orders` corresponding to the selected customer.</span></span> <span data-ttu-id="9d7c2-132">위에 있는 다른 행을 선택 하는 대로 <xref:System.Windows.Forms.DataGridView>, 더 작은 값의 내용을 <xref:System.Windows.Forms.DataGridView> 적절 하 게 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-132">As you select different rows in the upper <xref:System.Windows.Forms.DataGridView>, the contents of the lower <xref:System.Windows.Forms.DataGridView> change accordingly.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9d7c2-133">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9d7c2-133">Next Steps</span></span>  
 <span data-ttu-id="9d7c2-134">이 응용 프로그램에서는 기본적으로 이해는 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-134">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="9d7c2-135">모양 및 동작을 사용자 지정할 수 있습니다는 <xref:System.Windows.Forms.DataGridView> 여러 가지 방법으로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-135">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
-   <span data-ttu-id="9d7c2-136">테두리 및 머리글 스타일을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-136">Change border and header styles.</span></span> <span data-ttu-id="9d7c2-137">자세한 내용은 참조 [하는 방법: 테두리 및 눈금선 스타일 Windows Forms DataGridView 컨트롤에서 변경](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-137">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="9d7c2-138">사용 하거나 사용자 입력을 제한 된 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-138">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="9d7c2-139">자세한 내용은 참조 [하는 방법: 행 추가 및 삭제 금지 Windows Forms DataGridView 컨트롤에서](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), 및 [하는 방법: 열을 읽기 전용 Windows Forms DataGridView 컨트롤에서](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-139">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="9d7c2-140">에 대 한 사용자 입력 유효성 검사는 <xref:System.Windows.Forms.DataGridView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-140">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="9d7c2-141">자세한 내용은 참조 [연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-141">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="9d7c2-142">가상 모드를 사용 하 여 매우 큰 데이터 집합을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-142">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="9d7c2-143">자세한 내용은 참조 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-143">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="9d7c2-144">셀의 모양을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-144">Customize the appearance of cells.</span></span> <span data-ttu-id="9d7c2-145">자세한 내용은 참조 [하는 방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) 및 [하는 방법: Windows Forms DataGridView 컨트롤에 대 한 기본 셀 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9d7c2-145">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d7c2-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d7c2-146">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="9d7c2-147">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="9d7c2-147">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="9d7c2-148">방법: 두 개의 Windows Forms DataGridView 컨트롤을 사용하여 마스터/세부 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="9d7c2-148">How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md)  
 [<span data-ttu-id="9d7c2-149">연결 정보 보호</span><span class="sxs-lookup"><span data-stu-id="9d7c2-149">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)
