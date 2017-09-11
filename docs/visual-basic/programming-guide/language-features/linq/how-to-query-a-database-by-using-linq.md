---
title: "방법: LINQ (Visual Basic)를 사용 하 여 데이터베이스 쿼리 | Microsoft 문서"
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
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
caps.latest.revision: 12
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
ms.openlocfilehash: a645a71dd0489d6bf2cc0cd4fe5898eb7293f13c
ms.contentlocale: ko-kr
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="e9d6e-102">방법: LINQ를 사용하여 데이터베이스 쿼리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9d6e-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="e9d6e-103">언어 통합 쿼리 (LINQ)를 사용 하면 쉽게 데이터베이스 정보에 액세스 하 고 쿼리를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="e9d6e-104">다음 예제에는 SQL Server 데이터베이스에 대 한 쿼리를 수행 하는 새 응용 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="e9d6e-105">이 항목의 예제는 Northwind 샘플 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="e9d6e-106">개발 컴퓨터에 Northwind 샘플 데이터베이스가 없는 경우 있습니다에서 다운로드할 수는 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkID=98088) 웹 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-106">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="e9d6e-107">자세한 내용은 [샘플 데이터베이스 다운로드](https://msdn.microsoft.com/library/bb399411)합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="e9d6e-108">데이터베이스에 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="e9d6e-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="e9d6e-109">Visual Studio에서 열고 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 여 **서버 탐색기**/**데이터베이스 탐색기** 에 **보기** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="e9d6e-110">마우스 오른쪽 단추로 클릭 **데이터 연결** 에서 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 고 **연결 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="e9d6e-111">Northwind 샘플 데이터베이스에 올바른 연결을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="e9d6e-112">LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="e9d6e-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="e9d6e-113">Visual Studio에서에 **파일** 메뉴에서 **새로** 클릭 하 고 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="e9d6e-114">Visual basic **Windows Forms 응용 프로그램** 프로젝트 유형으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="e9d6e-115">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="e9d6e-116">선택 된 **LINQ to SQL 클래스** 항목 템플릿.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="e9d6e-117">파일 이름을 `northwind.dbml`합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="e9d6e-118">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-118">Click **Add**.</span></span> <span data-ttu-id="e9d6e-119">개체 관계형 디자이너 (O/R 디자이너) northwind.dbml 파일이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="e9d6e-120">O/R 디자이너를 쿼리 하는 테이블을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="e9d6e-120">To add tables to query to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="e9d6e-121">**서버 탐색기**/**데이터베이스 탐색기**, Northwind 데이터베이스에 연결을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="e9d6e-122">확장 된 **테이블** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="e9d6e-123">O/R 디자이너를 닫은 경우 앞에 추가 되는 northwind.dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="e9d6e-124">Customers 테이블을 클릭 하 고 디자이너의 왼쪽된 창에 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="e9d6e-125">Orders 테이블을 클릭 하 고 디자이너의 왼쪽된 창으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="e9d6e-126">디자이너 새 만들어 `Customer` 및 `Order` 프로젝트에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="e9d6e-127">눈에 띌 디자이너가 자동으로 테이블 간의 관계를 검색 자식 관련된 개체에 대 한 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="e9d6e-128">예를 들어, IntelliSense는 표시 됩니다는 `Customer` 개체에는 `Orders` 해당 고객에 게 관련 된 모든 주문에 대 한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3.  <span data-ttu-id="e9d6e-129">변경 내용을 저장 하 고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="e9d6e-130">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="e9d6e-131">데이터베이스를 쿼리하고 결과 표시 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="e9d6e-131">To add code to query the database and display the results</span></span>  
  
1.  <span data-ttu-id="e9d6e-132">**도구 상자**를 끌어 한 <xref:System.Windows.Forms.DataGridView>Form1 프로젝트에 대 한 기본 Windows Form 컨트롤을.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="e9d6e-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="e9d6e-133">Form1 코드를 추가 하려면 두 번 클릭 하 여 `Load` 폼의 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3.  <span data-ttu-id="e9d6e-134">O/R 디자이너에 테이블을 추가한 경우 디자이너가 추가 <xref:System.Data.Linq.DataContext>프로젝트에 대 한 개체입니다.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e9d6e-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="e9d6e-135">이 개체에 개별 개체와 각 테이블에 대 한 컬렉션 외에도 해당 테이블에 액세스 해야 하는 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="e9d6e-136"><xref:System.Data.Linq.DataContext>.dbml 파일의 이름에 따라 프로젝트에 대 한 개체입니다.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e9d6e-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="e9d6e-137">이 프로젝트는 <xref:System.Data.Linq.DataContext>개체의 이름은 `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e9d6e-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="e9d6e-138">인스턴스를 만들 수는 <xref:System.Data.Linq.DataContext>O/R 디자이너에서 지정 된 테이블에 프로그램 코드를 쿼리 합니다.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="e9d6e-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="e9d6e-139">다음 코드를 추가 하는 `Load` 데이터 컨텍스트의 속성으로 노출 되는 테이블을 쿼리 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     <span data-ttu-id="e9d6e-140">[!code-vb[VbLINQToSQLHowTos #&3;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e9d6e-140">[!code-vb[VbLINQToSQLHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]</span></span>  
  
4.  <span data-ttu-id="e9d6e-141">F5 키를 눌러 프로젝트를 실행 하 고 결과 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-141">Press F5 to run your project and view the results.</span></span>  
  
5.  <span data-ttu-id="e9d6e-142">다음은 사용할 수 있는 몇 가지 추가 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-142">Following are some additional queries that you can try:</span></span>  
  
     <span data-ttu-id="e9d6e-143">[!code-vb[VbLINQToSQLHowTos #&4;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e9d6e-143">[!code-vb[VbLINQToSQLHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]</span></span>  
    <span data-ttu-id="e9d6e-144">[!code-vb[VbLINQToSQLHowTos #&5;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="e9d6e-144">[!code-vb[VbLINQToSQLHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d6e-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9d6e-145">See Also</span></span>  
 <span data-ttu-id="e9d6e-146">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="e9d6e-146">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="e9d6e-147"> [쿼리](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="e9d6e-147"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="e9d6e-148"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="e9d6e-148"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="e9d6e-149"> [DataContext 메서드 (O/R 디자이너)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span><span class="sxs-lookup"><span data-stu-id="e9d6e-149"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)</span></span>

