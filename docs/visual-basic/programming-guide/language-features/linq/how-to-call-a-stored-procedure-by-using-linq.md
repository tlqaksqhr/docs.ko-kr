---
title: "방법: LINQ (Visual Basic)를 사용 하 여 저장된 프로시저를 호출 합니다. | Microsoft 문서"
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
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
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
ms.openlocfilehash: 40e72ece8399b1ffbe8c5457c63113d563c9f7f8
ms.contentlocale: ko-kr
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="522db-102">방법: LINQ를 사용하여 저장 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="522db-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="522db-103">언어 통합 쿼리 (LINQ) 쉽게 데이터베이스 개체와 같은 저장 프로시저를 포함 하 여 데이터베이스 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522db-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="522db-104">다음 예제에는 SQL Server 데이터베이스의 저장된 프로시저를 호출 하는 응용 프로그램을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="522db-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="522db-105">데이터베이스에 두 개의 다른 저장된 프로시저를 호출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="522db-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="522db-106">각 프로시저는 쿼리 결과 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="522db-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="522db-107">입력된 매개 변수를 사용 하는 하나의 절차 및 다른 프로시저 매개 변수를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="522db-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="522db-108">이 항목의 예제는 Northwind 샘플 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="522db-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="522db-109">개발 컴퓨터에 Northwind 샘플 데이터베이스가 없는 경우 있습니다에서 다운로드할 수는 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkID=98088) 웹 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="522db-109">If you do not have the Northwind sample database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) Web site.</span></span> <span data-ttu-id="522db-110">자세한 내용은 [샘플 데이터베이스 다운로드](https://msdn.microsoft.com/library/bb399411)합니다.</span><span class="sxs-lookup"><span data-stu-id="522db-110">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="522db-111">데이터베이스에 연결을 만들려면</span><span class="sxs-lookup"><span data-stu-id="522db-111">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="522db-112">Visual Studio에서 열고 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 여 **서버 탐색기**/**데이터베이스 탐색기** 에 **보기** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="522db-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="522db-113">마우스 오른쪽 단추로 클릭 **데이터 연결** 에서 **서버 탐색기**/**데이터베이스 탐색기** 클릭 하 고 **연결 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="522db-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="522db-114">Northwind 샘플 데이터베이스에 올바른 연결을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="522db-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="522db-115">LINQ to SQL 파일을 포함 하는 프로젝트를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="522db-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="522db-116">Visual Studio에서에 **파일** 메뉴에서 **새로** 클릭 하 고 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="522db-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="522db-117">Visual basic **Windows Forms 응용 프로그램** 프로젝트 유형으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="522db-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="522db-118">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="522db-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="522db-119">선택 된 **LINQ to SQL 클래스** 항목 템플릿.</span><span class="sxs-lookup"><span data-stu-id="522db-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="522db-120">파일 이름을 `northwind.dbml`합니다.</span><span class="sxs-lookup"><span data-stu-id="522db-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="522db-121">**추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="522db-121">Click **Add**.</span></span> <span data-ttu-id="522db-122">개체 관계형 디자이너 (O/R 디자이너) northwind.dbml 파일이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="522db-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="522db-123">저장된 프로시저를 O/R 디자이너에 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="522db-123">To add stored procedures to the O/R Designer</span></span>  
  
1.  <span data-ttu-id="522db-124">**서버 탐색기**/**데이터베이스 탐색기**, Northwind 데이터베이스에 연결을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="522db-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="522db-125">확장 된 **저장 프로시저** 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="522db-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="522db-126">O/R 디자이너를 닫은 경우 앞에 추가 되는 northwind.dbml 파일을 두 번 클릭 하 여 다시 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="522db-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="522db-127">클릭 된 **연도별 매출** 저장 프로시저 및 디자이너의 오른쪽 창으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="522db-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="522db-128">클릭 하 고 **Ten Most Expensive Products** 저장된 프로시저는 디자이너의 오른쪽 창으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="522db-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3.  <span data-ttu-id="522db-129">변경 내용을 저장 하 고 디자이너를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="522db-129">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="522db-130">프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="522db-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="522db-131">저장된 프로시저의 결과 표시 하는 코드를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="522db-131">To add code to display the results of the stored procedures</span></span>  
  
1.  <span data-ttu-id="522db-132">**도구 상자**, 끌어는 <xref:System.Windows.Forms.DataGridView>Form1 프로젝트에 대 한 기본 Windows Form 컨트롤을.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="522db-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="522db-133">Form1 코드를 추가 하려면 두 번 클릭 하 여 `Load` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="522db-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3.  <span data-ttu-id="522db-134">디자이너에 추가 된 저장된 프로시저를 O/R 디자이너를 추가한 경우는 <xref:System.Data.Linq.DataContext>프로젝트에 대 한 개체입니다.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="522db-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="522db-135">이 개체는 해당 프로시저에 액세스 해야 하는 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="522db-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="522db-136"><xref:System.Data.Linq.DataContext>.dbml 파일의 이름에 따라 프로젝트에 대해 개체.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="522db-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="522db-137">이 프로젝트는 <xref:System.Data.Linq.DataContext>개체의 이름은 `northwindDataContext`.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="522db-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="522db-138">인스턴스를 만들 수는 <xref:System.Data.Linq.DataContext>O/R 디자이너에서 지정 된 저장된 프로시저 메서드에서 코드를 호출 합니다.</xref:System.Data.Linq.DataContext></span><span class="sxs-lookup"><span data-stu-id="522db-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="522db-139">에 바인딩하는 <xref:System.Windows.Forms.DataGridView>개체를 호출 하 여 즉시 실행 하도록 할 수는 <xref:System.Linq.Enumerable.ToList%2A>메서드는 저장된 프로시저의 결과를.</xref:System.Linq.Enumerable.ToList%2A> </xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="522db-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="522db-140">다음 코드를 추가 하는 `Load` 데이터 컨텍스트에 대 한 메서드로 노출 하는 저장된 프로시저 중 하나를 호출 하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="522db-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     <span data-ttu-id="522db-141">[!code-vb[VbLINQtoSQLHowTos #&1;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="522db-141">[!code-vb[VbLINQtoSQLHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]</span></span>  
    <span data-ttu-id="522db-142">[!code-vb[VbLINQtoSQLHowTos #&2;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="522db-142">[!code-vb[VbLINQtoSQLHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]</span></span>  
  
4.  <span data-ttu-id="522db-143">F5 키를 눌러 프로젝트를 실행 하 고 결과 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="522db-143">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="522db-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="522db-144">See Also</span></span>  
 <span data-ttu-id="522db-145">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="522db-145">[LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="522db-146"> [쿼리](../../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="522db-146"> [Queries](../../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="522db-147"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span><span class="sxs-lookup"><span data-stu-id="522db-147"> [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) </span></span>  
<span data-ttu-id="522db-148"> [DataContext 메서드 (O/R 디자이너)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer) </span><span class="sxs-lookup"><span data-stu-id="522db-148"> [DataContext Methods (O/R Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer) </span></span>  
<span data-ttu-id="522db-149"> [방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 합니다.](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)</span><span class="sxs-lookup"><span data-stu-id="522db-149"> [How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)</span></span>

