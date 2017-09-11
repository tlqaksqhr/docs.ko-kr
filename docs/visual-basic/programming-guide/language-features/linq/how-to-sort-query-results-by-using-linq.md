---
title: "방법: LINQ (Visual Basic)를 사용 하 여 쿼리 결과 정렬 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- sorting query results, multiple columns
- sorting data [Visual Basic]
- sorting data [LINQ in Visual Basic]
- sorting query results [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], sorting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 07a4584d-9fd8-4a1d-b7d9-ccf2efa5c84e
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 0c728d9e52add00c9d3241a9f598c15eb2db17a5
ms.contentlocale: ko-kr
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="05a42-102">방법: LINQ를 사용하여 쿼리 결과 정렬(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05a42-102">How to: Sort Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="05a42-103">언어 통합 쿼리 (LINQ)를 사용 하면 쉽게 데이터베이스 정보에 액세스 하 고 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="05a42-104">다음 예제에는 SQL Server 데이터베이스에 대 한 쿼리를 수행 하 고 사용 하 여 여러 필드 별로 결과 정렬 하는 새 응용 프로그램을 만드는 방법을 보여 줍니다는 `Order By` 절.</span><span class="sxs-lookup"><span data-stu-id="05a42-104">The following example shows how to create a new application that performs queries against a SQL Server database and sorts the results by multiple fields by using the `Order By` clause.</span></span> <span data-ttu-id="05a42-105">각 필드에 대 한 정렬 순서는 오름차순 또는 내림차순 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-105">The sort order for each field can be ascending order or descending order.</span></span> <span data-ttu-id="05a42-106">자세한 내용은 참조 [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-106">For more information, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="05a42-107">이 항목의 예제는 Northwind 샘플 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="05a42-108">개발 컴퓨터에 Northwind 샘플 데이터베이스가 없는 경우 있습니다에서 다운로드할 수는 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkID=98088) 웹 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-108">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="05a42-109">자세한 내용은 [샘플 데이터베이스 다운로드](https://msdn.microsoft.com/library/bb399411)합니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-109">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="05a42-110">데이터베이스에 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="05a42-110">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="05a42-111">Visual Studio에서 열고 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 여 **서버 탐색기**/**데이터베이스 탐색기** 에 **보기** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="05a42-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="05a42-112">마우스 오른쪽 단추로 클릭 **데이터 연결** 에서 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 고 **연결 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="05a42-113">Northwind 샘플 데이터베이스에 올바른 연결을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="05a42-114">LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="05a42-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="05a42-115">Visual Studio에서에 **파일** 메뉴에서 **새로** 클릭 하 고 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="05a42-116">Visual basic **Windows Forms 응용 프로그램** 프로젝트 유형으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="05a42-117">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="05a42-118">선택 된 **LINQ to SQL 클래스** 항목 템플릿.</span><span class="sxs-lookup"><span data-stu-id="05a42-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="05a42-119">파일 이름을 `northwind.dbml`합니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="05a42-120">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-120">Click **Add**.</span></span> <span data-ttu-id="05a42-121">개체 관계형 디자이너 (O/R 디자이너) northwind.dbml 파일이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="05a42-122">O/R 디자이너를 쿼리 하는 테이블을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="05a42-122">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="05a42-123">**서버 탐색기**/**데이터베이스 탐색기**, Northwind 데이터베이스에 연결을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="05a42-124">확장 된 **테이블** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="05a42-125">O/R 디자이너를 닫은 경우 앞에 추가 되는 northwind.dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="05a42-126">Customers 테이블을 클릭 하 고 디자이너의 왼쪽된 창에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="05a42-127">Orders 테이블을 클릭 하 고 디자이너의 왼쪽된 창으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="05a42-128">디자이너 새 만들어 `Customer` 및 `Order` 프로젝트에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="05a42-129">눈에 띌 디자이너가 자동으로 테이블 간의 관계를 검색 자식 관련된 개체에 대 한 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="05a42-130">예를 들어, IntelliSense는 표시 됩니다는 `Customer` 개체에는 `Orders` 해당 고객에 게 관련 된 모든 주문에 대 한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="05a42-131">변경 내용을 저장 하 고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-131">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="05a42-132">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="05a42-133">데이터베이스를 쿼리하고 결과 표시 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="05a42-133">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="05a42-134">**도구 상자**를 끌어 한 <xref:System.Windows.Forms.DataGridView>Form1 프로젝트에 대 한 기본 Windows Form 컨트롤을.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="05a42-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="05a42-135">Form1 코드를 추가 하려면 두 번 클릭 하 여 `Load` 폼의 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="05a42-136">O/R 디자이너에 테이블을 추가한 경우 디자이너 추가 <xref:System.Data.Linq.DataContext>프로젝트에는 개체입니다.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="05a42-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="05a42-137">이 개체는 해당 테이블에 액세스 하 고 개별 개체 및 각 테이블에 대 한 컬렉션에 액세스할 수 있어야 하는 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="05a42-138"><xref:System.Data.Linq.DataContext>.dbml 파일의 이름에 따라 프로젝트에 대 한 개체입니다.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="05a42-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="05a42-139">이 프로젝트는 <xref:System.Data.Linq.DataContext>개체의 이름은 `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="05a42-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="05a42-140">인스턴스를 만들 수는 <xref:System.Data.Linq.DataContext>O/R 디자이너에서 지정 된 테이블에 프로그램 코드를 쿼리 합니다.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="05a42-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="05a42-141">다음 코드를 추가 하는 `Load` 데이터 컨텍스트의 속성으로 노출 되 고 결과 정렬 하는 테이블을 쿼리 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context and sort the results.</span></span> <span data-ttu-id="05a42-142">쿼리는 내림차순에서 고객 주문 수로 결과 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-142">The query sorts the results by the number of customer orders, in descending order.</span></span> <span data-ttu-id="05a42-143">고객의 주문 번호가 동일한에 회사 이름 오름차순 (기본값)으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-143">Customers that have the same number of orders are ordered by company name in ascending order (the default).</span></span>  
  
     <span data-ttu-id="05a42-144">[!code-vb[VbLINQToSQLHowTos #&10;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-sort-query-results-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="05a42-144">[!code-vb[VbLINQToSQLHowTos#10](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-sort-query-results-by-using-linq_1.vb)]</span></span>  
  
4.  <span data-ttu-id="05a42-145">F5 키를 눌러 프로젝트를 실행 하 고 결과 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a42-145">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05a42-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05a42-146">See Also</span></span>  
 <span data-ttu-id="05a42-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="05a42-147">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="05a42-148"> [쿼리](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="05a42-148"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="05a42-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="05a42-149"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="05a42-150"> [DataContext 메서드 (O/R 디자이너)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="05a42-150"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>

