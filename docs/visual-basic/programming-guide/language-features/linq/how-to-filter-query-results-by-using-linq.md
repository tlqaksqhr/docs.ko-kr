---
title: "방법: LINQ를 사용하여 쿼리 결과 필터링(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0d2e93d9b4518482b22c78d10d31c4035bdf587e
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="0cf67-102">방법: LINQ를 사용하여 쿼리 결과 필터링(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cf67-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="0cf67-103">통합 언어 쿼리 (LINQ)을 사용 하면 쉽게 데이터베이스 정보에 액세스 하 고 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="0cf67-104">SQL Server 데이터베이스에 대 한 쿼리를 수행 하 고 특정 값으로 사용 하 여 결과 필터링 하는 새 응용 프로그램을 만드는 방법을 보여 주는 다음 예제는 `Where` 절.</span><span class="sxs-lookup"><span data-stu-id="0cf67-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="0cf67-105">자세한 내용은 참조 [Where 절](../../../../visual-basic/language-reference/queries/where-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
 <span data-ttu-id="0cf67-106">이 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="0cf67-107">개발 컴퓨터에 Northwind 샘플 데이터베이스가 없는 경우에서 다운로드할 수 있습니다는 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkID=98088) 웹 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-107">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="0cf67-108">자세한 내용은 [샘플 데이터베이스 다운로드](../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-108">For instructions, see [Downloading Sample Databases](../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="0cf67-109">데이터베이스에 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="0cf67-109">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="0cf67-110">Visual Studio에서 열고 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 여 **서버 탐색기**/**데이터베이스 탐색기** 에 **보기** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="0cf67-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="0cf67-111">마우스 오른쪽 단추로 클릭 **데이터 연결** 에 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 고 **연결 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="0cf67-112">Northwind 샘플 데이터베이스에 올바른 연결을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-112">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="0cf67-113">LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="0cf67-113">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="0cf67-114">Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="0cf67-115">Visual basic **Windows Forms 응용 프로그램** 프로젝트 형식으로.</span><span class="sxs-lookup"><span data-stu-id="0cf67-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="0cf67-116">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="0cf67-117">선택 된 **LINQ to SQL 클래스** 항목 템플릿을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-117">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="0cf67-118">파일 이름을 `northwind.dbml`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="0cf67-119">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-119">Click **Add**.</span></span> <span data-ttu-id="0cf67-120">개체 관계형 디자이너 (O/R 디자이너) northwind.dbml 파일이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="0cf67-121">O/R 디자이너를 쿼리 하는 테이블을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="0cf67-121">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="0cf67-122">**서버 탐색기**/**데이터베이스 탐색기**, Northwind 데이터베이스에 연결을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="0cf67-123">확장 된 **테이블** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-123">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="0cf67-124">O/R 디자이너를 닫은 경우 이전에 추가한 northwind.dbml 파일이 두 번 클릭 하 여 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="0cf67-125">Customers 테이블을 클릭 하 고 디자이너의 왼쪽된 창에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="0cf67-126">Orders 테이블을 클릭 하 고 디자이너의 왼쪽된 창으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-126">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="0cf67-127">디자이너가 새 만들어 `Customer` 및 `Order` 프로젝트에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="0cf67-128">고 해당 데이터베이스 디자이너 자동으로 테이블 간의 관계를 검색 자식 관련된 개체에 대 한 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="0cf67-129">예를 들어, IntelliSense는 표시 됩니다는 `Customer` 개체에는 `Orders` 해당 고객에 게 관련 된 모든 주문에 대 한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="0cf67-130">변경 내용을 저장 하 고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-130">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="0cf67-131">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-131">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="0cf67-132">데이터베이스를 쿼리하고 결과 표시 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="0cf67-132">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="0cf67-133">**도구 상자**를 끌어는 <xref:System.Windows.Forms.DataGridView> Form1 프로젝트에 대 한 기본 Windows Form 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="0cf67-134">Form1 코드를 추가 하려면 두 번 클릭 하 고 `Load` 폼의 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="0cf67-135">O/R 디자이너에 테이블을 추가 하는 경우에 디자이너 추가 <xref:System.Data.Linq.DataContext> 프로젝트에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="0cf67-136">이 개체는 개별 개체와 각 테이블에 대 한 컬렉션 외에도 해당 테이블에 액세스 해야 하는 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="0cf67-137"><xref:System.Data.Linq.DataContext> .dbml 파일의 이름에 따라 프로젝트에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="0cf67-138">이 프로젝트는 <xref:System.Data.Linq.DataContext> 개체의 이름은 `northwindDataContext`합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="0cf67-139">인스턴스를 만들 수는 <xref:System.Data.Linq.DataContext> 코드와 쿼리에서 O/R 디자이너에서 지정 된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="0cf67-140">다음 코드를 추가 하 고 `Load` 데이터 컨텍스트 클래스의 속성으로 노출 되는 테이블을 쿼리 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="0cf67-141">쿼리 결과 필터링 하 고에 있는 고객만 반환 `London`합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-141">The query filters the results and returns only customers that are located in `London`.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_1.vb)]  
  
4.  <span data-ttu-id="0cf67-142">F5 키를 눌러 프로젝트를 실행 하 고 결과 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-142">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="0cf67-143">다음은 몇 가지 다른 필터를 테스트해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf67-143">Following are some other filters that you can try.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-filter-query-results-by-using-linq_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0cf67-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0cf67-144">See Also</span></span>  
 [<span data-ttu-id="0cf67-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="0cf67-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="0cf67-146">쿼리</span><span class="sxs-lookup"><span data-stu-id="0cf67-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="0cf67-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="0cf67-147">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="0cf67-148">DataContext 메서드 (O/R 디자이너)</span><span class="sxs-lookup"><span data-stu-id="0cf67-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
