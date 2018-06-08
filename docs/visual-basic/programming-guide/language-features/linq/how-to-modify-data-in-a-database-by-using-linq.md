---
title: '방법: LINQ를 사용하여 데이터베이스의 데이터 수정(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inserting rows [LINQ to SQL]
- deleting rows [LINQ to SQL]
- updating rows [LINQ to SQL]
- inserting data [Visual Basic]
- deleting data
- data [Visual Basic], updating
- updating data [LINQ]
- queries [LINQ in Visual Basic], data changes in database
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
ms.openlocfilehash: 617bb62f9009c507658b5d1262657cb4dfa860e9
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827113"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="9e5f5-102">방법: LINQ를 사용하여 데이터베이스의 데이터 수정(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e5f5-102">How to: Modify Data in a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="9e5f5-103">통합 언어 쿼리 (LINQ) 쿼리 쉽게 데이터베이스 정보를 액세스 및 데이터베이스의 값을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-103">Language-Integrated Query (LINQ) queries make it easy to access database information and modify values in the database.</span></span>  
  
 <span data-ttu-id="9e5f5-104">다음 예제에서는 SQL Server 데이터베이스에서를 검색 하는 새 응용 프로그램을 만드는 방법과 업데이트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-104">The following example shows how to create a new application that retrieves and updates information in a SQL Server database.</span></span>  
  
 <span data-ttu-id="9e5f5-105">이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="9e5f5-106">개발 컴퓨터에이 데이터베이스가 없는 경우에 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="9e5f5-107">자세한 내용은 [샘플 데이터베이스 다운로드](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="9e5f5-108">데이터베이스에 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9e5f5-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="9e5f5-109">Visual Studio에서 열고 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 여는 **보기** 메뉴를 선택한 후 **서버탐색기** / **데이터베이스 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking the **View** menu, and then select **Server Explorer**/**Database Explorer**.</span></span>  
  
2.  <span data-ttu-id="9e5f5-110">마우스 오른쪽 단추로 클릭 **데이터 연결** 에 **서버 탐색기**/**데이터베이스 탐색기**를 클릭 하 고 **연결 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer**, and click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="9e5f5-111">Northwind 샘플 데이터베이스에 올바른 연결을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a><span data-ttu-id="9e5f5-112">SQL 파일에는 LINQ 사용 하 여 프로젝트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="9e5f5-112">To add a Project with a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="9e5f5-113">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="9e5f5-114">Visual basic **Windows Forms 응용 프로그램** 프로젝트 형식으로.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="9e5f5-115">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="9e5f5-116">선택 된 **LINQ to SQL 클래스** 항목 템플릿을 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="9e5f5-117">파일 이름을 `northwind.dbml`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="9e5f5-118">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-118">Click **Add**.</span></span> <span data-ttu-id="9e5f5-119">개체 관계형 디자이너 (O/R 디자이너)으로 열릴는 `northwind.dbml` 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-119">The Object Relational Designer (O/R Designer) is opened for the `northwind.dbml` file.</span></span>  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a><span data-ttu-id="9e5f5-120">쿼리 디자이너를 수정 하는 테이블을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="9e5f5-120">To add tables to query and modify to the designer</span></span>  
  
1.  <span data-ttu-id="9e5f5-121">**서버 탐색기**/**데이터베이스 탐색기**, Northwind 데이터베이스에 연결을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="9e5f5-122">확장 된 **테이블** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="9e5f5-123">O/R 디자이너를 닫은 경우 다시 열 수 있습니다이 두 번 클릭 하 여 `northwind.dbml` 이전에 추가한 파일.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-123">If you have closed the O/R Designer, you can reopen it by double-clicking the `northwind.dbml` file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="9e5f5-124">Customers 테이블을 클릭 하 고 디자이너의 왼쪽된 창에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-124">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="9e5f5-125">디자이너는 프로젝트에 대 한 새 Customer 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-125">The designer creates a new Customer object for your project.</span></span>  
  
3.  <span data-ttu-id="9e5f5-126">변경 내용을 저장 하 고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-126">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="9e5f5-127">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-127">Save your project.</span></span>  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a><span data-ttu-id="9e5f5-128">데이터베이스를 수정 하 고 결과 표시 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="9e5f5-128">To add code to modify the database and display the results</span></span>  
  
1.  <span data-ttu-id="9e5f5-129">**도구 상자**를 끌어는 <xref:System.Windows.Forms.DataGridView> Form1 프로젝트에 대 한 기본 Windows Form 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="9e5f5-130">O/R 디자이너에 테이블을 추가 하는 경우에 디자이너 추가 <xref:System.Data.Linq.DataContext> 프로젝트에는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-130">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="9e5f5-131">이 개체에는 Customers 테이블에 액세스 하는 데 사용할 수 있는 코드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-131">This object contains code that you can use to access the Customers table.</span></span> <span data-ttu-id="9e5f5-132">또한 테이블에 고객 컬렉션과 로컬 Customer 개체를 정의 하는 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-132">It also contains code that defines  a local Customer object and a Customers collection for the table.</span></span> <span data-ttu-id="9e5f5-133"><xref:System.Data.Linq.DataContext> .dbml 파일의 이름에 따라 프로젝트에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-133">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="9e5f5-134">이 프로젝트는 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-134">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="9e5f5-135">인스턴스를 만들 수는 <xref:System.Data.Linq.DataContext> 코드 및 쿼리 개체를 O/R 디자이너에서 지정 된 고객 컬렉션을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-135">You can create an instance of the <xref:System.Data.Linq.DataContext> object in your code and query and modify the Customers collection specified by the O/R Designer.</span></span> <span data-ttu-id="9e5f5-136">호출 하 여 제출 하기 전에 고객 컬렉션에 수행한 변경 내용을 데이터베이스에 반영 되지 않습니다는 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 의 메서드는 <xref:System.Data.Linq.DataContext> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-136">Changes that you make to the Customers collection are not reflected in the database until you submit them by calling the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> method of the <xref:System.Data.Linq.DataContext> object.</span></span>  
  
     <span data-ttu-id="9e5f5-137">Windows Form Form1 코드를 추가 하려면 두 번 클릭 하 여 <xref:System.Windows.Forms.Form.Load> 이벤트를 쿼리 하는 경우 Customers 테이블의 속성으로 노출 되 프로그램 <xref:System.Data.Linq.DataContext>합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-137">Double-click the Windows Form, Form1, to add code to the <xref:System.Windows.Forms.Form.Load> event to query the Customers table that is exposed as a property of your <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="9e5f5-138">다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-138">Add the following code:</span></span>  
  
    ```vb  
    Private db As northwindDataContext  
  
    Private Sub Form1_Load(ByVal sender As System.Object,   
                           ByVal e As System.EventArgs  
                          ) Handles MyBase.Load  
      db = New northwindDataContext()  
  
      RefreshData()  
    End Sub  
  
    Private Sub RefreshData()  
      Dim customers = From cust In db.Customers   
                      Where cust.City(0) = "W"   
                      Select cust  
  
      DataGridView1.DataSource = customers  
    End Sub  
    ```  
  
3.  <span data-ttu-id="9e5f5-139">**도구 상자**, 세 개의 끌어 <xref:System.Windows.Forms.Button> 폼에 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-139">From the **Toolbox**, drag three <xref:System.Windows.Forms.Button> controls onto the form.</span></span> <span data-ttu-id="9e5f5-140">첫 번째 선택 `Button` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-140">Select the first `Button` control.</span></span> <span data-ttu-id="9e5f5-141">에 **속성** 창의 설정는 `Name` 의 `Button` 컨트롤을 `AddButton` 및 `Text` 를 `Add`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-141">In the **Properties** window, set the `Name` of the `Button` control to `AddButton` and the `Text` to `Add`.</span></span> <span data-ttu-id="9e5f5-142">두 번째 단추를 선택 하 고 설정 된 `Name` 속성을 `UpdateButton` 및 `Text` 속성을 `Update`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-142">Select the second button and set the `Name` property to `UpdateButton` and the `Text` property to `Update`.</span></span> <span data-ttu-id="9e5f5-143">세 번째 단추를 선택 하 고 설정 된 `Name` 속성을 `DeleteButton` 및 `Text` 속성을 `Delete`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-143">Select the third button and set the `Name` property to `DeleteButton` and the `Text` property to `Delete`.</span></span>  
  
4.  <span data-ttu-id="9e5f5-144">두 번 클릭 하 고 **추가** 코드를 추가 하는 단추 해당 `Click` 이벤트.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-144">Double-click the **Add** button to add code to its `Click` event.</span></span> <span data-ttu-id="9e5f5-145">다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-145">Add the following code:</span></span>  
  
    ```vb  
    Private Sub AddButton_Click(ByVal sender As System.Object,   
                                ByVal e As System.EventArgs  
                               ) Handles AddButton.Click  
      Dim cust As New Customer With {   
        .City = "Wellington",   
        .CompanyName = "Blue Yonder Airlines",   
        .ContactName = "Jill Frank",   
        .Country = "New Zealand",   
        .CustomerID = "JILLF"}  
  
      db.Customers.InsertOnSubmit(cust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
5.  <span data-ttu-id="9e5f5-146">두 번 클릭 하 고 **업데이트** 코드를 추가 하는 단추 해당 `Click` 이벤트.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-146">Double-click the **Update** button to add code to its `Click` event.</span></span> <span data-ttu-id="9e5f5-147">다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-147">Add the following code:</span></span>  
  
    ```vb  
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles UpdateButton.Click  
      Dim updateCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      updateCust.ContactName = "Jill Shrader"  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
6.  <span data-ttu-id="9e5f5-148">두 번 클릭은 **삭제** 코드를 추가 하는 단추 해당 `Click` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-148">Double-click the **Delete** button to add code to its `Click` event.</span></span> <span data-ttu-id="9e5f5-149">다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-149">Add the following code:</span></span>  
  
    ```vb  
    Private Sub DeleteButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles DeleteButton.Click  
      Dim deleteCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      db.Customers.DeleteOnSubmit(deleteCust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
7.  <span data-ttu-id="9e5f5-150">F5 키를 눌러 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-150">Press F5 to run your project.</span></span> <span data-ttu-id="9e5f5-151">클릭 **추가** 새 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-151">Click **Add** to add a new record.</span></span> <span data-ttu-id="9e5f5-152">클릭 **업데이트** 새 레코드를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-152">Click **Update** to modify the new record.</span></span> <span data-ttu-id="9e5f5-153">클릭 **삭제** 새 레코드를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-153">Click **Delete** to delete the new record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e5f5-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e5f5-154">See Also</span></span>  
 [<span data-ttu-id="9e5f5-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="9e5f5-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="9e5f5-156">쿼리</span><span class="sxs-lookup"><span data-stu-id="9e5f5-156">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="9e5f5-157">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9e5f5-157">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="9e5f5-158">DataContext 메서드 (O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="9e5f5-158">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="9e5f5-159">방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e5f5-159">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
