---
title: Visual Basic에서 쿼리 작성
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: beb192f6b136455cb1adcb6cf2616578b63fcebf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655878"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a><span data-ttu-id="7ac11-102">연습: Visual Basic에서 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="7ac11-102">Walkthrough: Writing Queries in Visual Basic</span></span>
<span data-ttu-id="7ac11-103">이 연습에서는 Visual Basic 언어 기능을 사용 하 여 작성 하는 방법을 보여 줍니다. [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-103">This walkthrough demonstrates how you can use Visual Basic language features to write [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query expressions.</span></span> <span data-ttu-id="7ac11-104">이 연습에는 쿼리를 만드는 방법을 학생 개체의 목록에서 다음 쿼리를 실행 하는 방법 및 수정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-104">The walkthrough demonstrates how to create queries on a list of Student objects, how to run the queries, and how to modify them.</span></span> <span data-ttu-id="7ac11-105">이 쿼리는 개체 이니셜라이저, 지역 형식 유추, 익명 형식을 비롯 한 몇 가지 기능을 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-105">The queries incorporate several features including object initializers, local type inference, and anonymous types.</span></span>  
  
 <span data-ttu-id="7ac11-106">이 연습을 완료 한 후 샘플 및 특정에 대 한 설명서로 이동할 준비가 됩니다 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자에 관심이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-106">After completing this walkthrough, you will be ready to move on to the samples and documentation for the specific [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider you are interested in.</span></span> [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]<span data-ttu-id="7ac11-107"> 공급자에 포함 되어 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], 및 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-107"> providers include [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
## <a name="create-a-project"></a><span data-ttu-id="7ac11-108">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="7ac11-108">Create a Project</span></span>  
  
#### <a name="to-create-a-console-application-project"></a><span data-ttu-id="7ac11-109">콘솔 응용 프로그램 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="7ac11-109">To create a console application project</span></span>  
  
1.  <span data-ttu-id="7ac11-110">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-110">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="7ac11-111">**파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="7ac11-112">에 **설치 된 템플릿** 목록에서 클릭 **Visual Basic**합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-112">In the **Installed Templates** list, click **Visual Basic**.</span></span>  
  
4.  <span data-ttu-id="7ac11-113">프로젝트 형식 목록에서 클릭 **콘솔 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-113">In the list of project types, click **Console Application**.</span></span> <span data-ttu-id="7ac11-114">에 **이름** 상자, 프로젝트에 대 한 이름을 입력 한 다음 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-114">In the **Name** box, type a name for the project, and then click **OK**.</span></span>  
  
     <span data-ttu-id="7ac11-115">프로젝트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-115">A project is created.</span></span> <span data-ttu-id="7ac11-116">기본적으로 System.Core.dll에 대 한 참조를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-116">By default, it contains a reference to System.Core.dll.</span></span> <span data-ttu-id="7ac11-117">또한는 **가져온 네임 스페이스** 목록에 [참조 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) 포함는 <xref:System.Linq?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-117">Also, the **Imported namespaces** list on the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) includes the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
5.  <span data-ttu-id="7ac11-118">에 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), 되도록 **Option infer** 로 설정 된 **에**합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-118">On the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), ensure that **Option infer** is set to **On**.</span></span>  
  
## <a name="add-an-in-memory-data-source"></a><span data-ttu-id="7ac11-119">메모리 내 데이터 원본 추가</span><span class="sxs-lookup"><span data-stu-id="7ac11-119">Add an In-Memory Data Source</span></span>  
 <span data-ttu-id="7ac11-120">이 연습에서 쿼리의 데이터 원본이 목록이 `Student` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-120">The data source for the queries in this walkthrough is a list of `Student` objects.</span></span> <span data-ttu-id="7ac11-121">각 `Student` 개체 이름, 성, 학년 및 생 학생 본문에는 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-121">Each `Student` object contains a first name, a last name, a class year, and an academic rank in the student body.</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="7ac11-122">데이터 소스를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="7ac11-122">To add the data source</span></span>  
  
-   <span data-ttu-id="7ac11-123">정의 `Student` 클래스와 클래스의 인스턴스 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-123">Define a `Student` class, and create a list of instances of the class.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7ac11-124">정의 하는 데 필요한 코드는 `Student` 클래스를 만들고 사용 하는 목록을 연습 예제에 제공 됩니다 [하는 방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-124">The code needed to define the `Student` class and create the list used in the walkthrough examples is provided in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="7ac11-125">여기에서 복사 하 고 프로젝트에 붙여 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-125">You can copy it from there and paste it into your project.</span></span> <span data-ttu-id="7ac11-126">새 코드를 프로젝트를 만들 때 표시 하는 코드를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-126">The new code replaces the code that appeared when you created the project.</span></span>  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="7ac11-127">새 학생 학생 목록에 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="7ac11-127">To add a new student to the students list</span></span>  
  
-   <span data-ttu-id="7ac11-128">패턴에 따라는 `getStudents` 의 다른 인스턴스를 추가 하는 메서드는 `Student` 목록에는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-128">Follow the pattern in the `getStudents` method to add another instance of the `Student` class to the list.</span></span> <span data-ttu-id="7ac11-129">학생을 추가 개체 이니셜라이저를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-129">Adding the student will introduce you to object initializers.</span></span> <span data-ttu-id="7ac11-130">자세한 내용은 참조 [개체 이니셜라이저: 명명 된 형식과 익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-130">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>  
  
## <a name="create-a-query"></a><span data-ttu-id="7ac11-131">쿼리 만들기</span><span class="sxs-lookup"><span data-stu-id="7ac11-131">Create a Query</span></span>  
 <span data-ttu-id="7ac11-132">를 실행 하면이 섹션에 추가 된 쿼리 상위 10 개의 추가한 등 수가 학생의 목록을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-132">When executed, the query added in this section produces a list of the students whose academic rank puts them in the top ten.</span></span> <span data-ttu-id="7ac11-133">쿼리 전체를 선택 하기 때문에 `Student` 개체 때마다 쿼리 결과의 종류는 `IEnumerable(Of Student)`합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-133">Because the query selects the complete `Student` object each time, the type of the query result is `IEnumerable(Of Student)`.</span></span> <span data-ttu-id="7ac11-134">그러나 쿼리 형식이 일반적으로 지정 하지 않았습니다 쿼리 정의에.</span><span class="sxs-lookup"><span data-stu-id="7ac11-134">However, the type of the query typically is not specified in query definitions.</span></span> <span data-ttu-id="7ac11-135">대신, 컴파일러는 형식을 확인 하려면 지역 형식 유추를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-135">Instead, the compiler uses local type inference to determine the type.</span></span> <span data-ttu-id="7ac11-136">자세한 내용은 참조 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span> <span data-ttu-id="7ac11-137">쿼리의 범위 변수 `currentStudent`, 각각에 대 한 참조로 사용 `Student` 는 소스인 `students`에 있는 각 개체의 속성에 대 한 액세스를 제공 하 `students`합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-137">The query's range variable, `currentStudent`, serves as a reference to each `Student` instance in the source, `students`, providing access to the properties of each object in `students`.</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="7ac11-138">단순 쿼리를 작성하려면</span><span class="sxs-lookup"><span data-stu-id="7ac11-138">To create a simple query</span></span>  
  
1.  <span data-ttu-id="7ac11-139">위치를 찾습니다는 `Main` 다음과 같이 표시 하는 프로젝트의 메서드:</span><span class="sxs-lookup"><span data-stu-id="7ac11-139">Find the place in the `Main` method of the project that is marked as follows:</span></span>  
  
     [!code-vb[VbLINQWalkthrough#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_1.vb)]  
  
     <span data-ttu-id="7ac11-140">다음 코드를 복사 하 고 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-140">Copy the following code and paste it in.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_2.vb)]  
  
2.  <span data-ttu-id="7ac11-141">마우스 포인터로 가리켜 `studentQuery` 컴파일러에서 할당 유형이 인지 확인 하기 위해 코드에 `IEnumerable(Of Student)`합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-141">Rest the mouse pointer over `studentQuery` in your code to verify that the compiler-assigned type is `IEnumerable(Of Student)`.</span></span>  
  
## <a name="run-the-query"></a><span data-ttu-id="7ac11-142">쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="7ac11-142">Run the Query</span></span>  
 <span data-ttu-id="7ac11-143">변수 `studentQuery` 쿼리를 실행 결과가 아니라 쿼리의 정의 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-143">The variable `studentQuery` contains the definition of the query, not the results of running the query.</span></span> <span data-ttu-id="7ac11-144">쿼리를 실행 하기 위한 일반적인 메커니즘은는 `For Each` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-144">A typical mechanism for running a query is a `For Each` loop.</span></span> <span data-ttu-id="7ac11-145">반환된 된 시퀀스의 각 요소는 루프 반복 변수를 통해 액세스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-145">Each element in the returned sequence is accessed through the loop iteration variable.</span></span> <span data-ttu-id="7ac11-146">쿼리 실행에 대 한 자세한 내용은 참조 [쓰기 Your LINQ 쿼리 처음](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-146">For more information about query execution, see [Writing Your First LINQ Query](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
#### <a name="to-run-the-query"></a><span data-ttu-id="7ac11-147">쿼리를 실행 하려면</span><span class="sxs-lookup"><span data-stu-id="7ac11-147">To run the query</span></span>  
  
1.  <span data-ttu-id="7ac11-148">다음 추가 `For Each` 루프 아래 프로젝트에 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-148">Add the following `For Each` loop below the query in your project.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_3.vb)]  
  
2.  <span data-ttu-id="7ac11-149">루프 제어 변수 위에 마우스 포인터를 놓고 `studentRecord` 해당 데이터 형식을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-149">Rest the mouse pointer over the loop control variable `studentRecord` to see its data type.</span></span> <span data-ttu-id="7ac11-150">유형의 `studentRecord` 것으로 유추 `Student`때문에, `studentQuery` 의 컬렉션을 반환 `Student` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="7ac11-150">The type of `studentRecord` is inferred to be `Student`, because `studentQuery` returns a collection of `Student` instances.</span></span>  
  
3.  <span data-ttu-id="7ac11-151">빌드하고 CTRL + f 5를 눌러 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-151">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="7ac11-152">콘솔 창에서 결과 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-152">Note the results in the console window.</span></span>  
  
## <a name="modify-the-query"></a><span data-ttu-id="7ac11-153">쿼리 수정</span><span class="sxs-lookup"><span data-stu-id="7ac11-153">Modify the Query</span></span>  
 <span data-ttu-id="7ac11-154">지정된 된 순서에 있는 경우 쿼리 결과 검색 하는 것이 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-154">It is easier to scan query results if they are in a specified order.</span></span> <span data-ttu-id="7ac11-155">사용 가능한 모든 필드에 따라 반환된 된 시퀀스를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-155">You can sort the returned sequence based on any available field.</span></span>  
  
#### <a name="to-order-the-results"></a><span data-ttu-id="7ac11-156">결과를 정렬하려면</span><span class="sxs-lookup"><span data-stu-id="7ac11-156">To order the results</span></span>  
  
1.  <span data-ttu-id="7ac11-157">다음 추가 `Order By` 절 간의 `Where` 문 및 `Select` 쿼리 문입니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-157">Add the following `Order By` clause between the `Where` statement and the `Select` statement of the query.</span></span> <span data-ttu-id="7ac11-158">`Order By` 절은 결과 순서 사전순으로 a에서-Z, 성의 성에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-158">The `Order By` clause will order the results alphabetically from A to Z, according to the last name of each student.</span></span>  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2.  <span data-ttu-id="7ac11-159">요청 된 성 및 이름, 쿼리에 두 필드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-159">To order by last name and then first name, add both fields to the query:</span></span>  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     <span data-ttu-id="7ac11-160">표시할 `Descending` a z에서 순서</span><span class="sxs-lookup"><span data-stu-id="7ac11-160">You can also specify `Descending` to order from Z to A.</span></span>  
  
3.  <span data-ttu-id="7ac11-161">빌드하고 CTRL + f 5를 눌러 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-161">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="7ac11-162">콘솔 창에서 결과 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-162">Note the results in the console window.</span></span>  
  
#### <a name="to-introduce-a-local-identifier"></a><span data-ttu-id="7ac11-163">로컬 식별자를 제공 하려면</span><span class="sxs-lookup"><span data-stu-id="7ac11-163">To introduce a local identifier</span></span>  
  
1.  <span data-ttu-id="7ac11-164">쿼리 식의 로컬 식별자를 제공 하려면이 섹션의 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-164">Add the code in this section to introduce a local identifier in the query expression.</span></span> <span data-ttu-id="7ac11-165">로컬 식별자는 중간 결과 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-165">The local identifier will hold an intermediate result.</span></span> <span data-ttu-id="7ac11-166">다음 예에서 `name` 학생의 연결을 보유 하는 식별자의 첫 번째 이름과 성이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-166">In the following example, `name` is an identifier that holds a concatenation of the student's first and last names.</span></span> <span data-ttu-id="7ac11-167">여러 번 계산 해야 하는 식의 결과 저장 하 여 성능이 향상 될 수 또는 편의 위해 로컬 식별자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-167">A local identifier can be used for convenience, or it can enhance performance by storing the results of an expression that would otherwise be calculated multiple times.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_4.vb)]  
  
2.  <span data-ttu-id="7ac11-168">빌드하고 CTRL + f 5를 눌러 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-168">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="7ac11-169">콘솔 창에서 결과 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-169">Note the results in the console window.</span></span>  
  
#### <a name="to-project-one-field-in-the-select-clause"></a><span data-ttu-id="7ac11-170">Select 절에 필드를 하나에 프로젝트</span><span class="sxs-lookup"><span data-stu-id="7ac11-170">To project one field in the Select clause</span></span>  
  
1.  <span data-ttu-id="7ac11-171">쿼리를 추가 하 고 `For Each` 해당 요소가 원본의 요소와 다른 시퀀스를 생성 하는 쿼리를 만들려면이 섹션에서 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-171">Add the query and `For Each` loop from this section to create a query that produces a sequence whose elements differ from the elements in the source.</span></span> <span data-ttu-id="7ac11-172">다음 예제에서는 소스 컬렉션을는 `Student` 개체가 아니라는 각 개체의 멤버를 하나만 반환 됩니다: 성이 Garcia 인 학생의 성입니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-172">In the following example, the source is a collection of `Student` objects, but only one member of each object is returned: the first name of students whose last name is Garcia.</span></span> <span data-ttu-id="7ac11-173">때문에 `currentStudent.First` 는 문자열에서 반환 된 시퀀스의 데이터 형식을 `studentQuery3` 은 `IEnumerable(Of String)`, 문자열의 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-173">Because `currentStudent.First` is a string, the data type of the sequence returned by `studentQuery3` is `IEnumerable(Of String)`, a sequence of strings.</span></span> <span data-ttu-id="7ac11-174">이전 예제에서와 같이 데이터의 할당에 대 한 형식 `studentQuery3` 컴파일러 지역 형식 유추를 사용 하 여 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-174">As in earlier examples, the assignment of a data type for `studentQuery3` is left for the compiler to determine by using local type inference.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_5.vb)]  
  
2.  <span data-ttu-id="7ac11-175">마우스 포인터로 가리켜 `studentQuery3` 할당 된 형식이 확인 하기 위해 코드에 `IEnumerable(Of String)`합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-175">Rest the mouse pointer over `studentQuery3` in your code to verify that the assigned type is `IEnumerable(Of String)`.</span></span>  
  
3.  <span data-ttu-id="7ac11-176">빌드하고 CTRL + f 5를 눌러 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-176">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="7ac11-177">콘솔 창에서 결과 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-177">Note the results in the console window.</span></span>  
  
#### <a name="to-create-an-anonymous-type-in-the-select-clause"></a><span data-ttu-id="7ac11-178">Select 절에 익명 형식을 만들려면</span><span class="sxs-lookup"><span data-stu-id="7ac11-178">To create an anonymous type in the Select clause</span></span>  
  
1.  <span data-ttu-id="7ac11-179">쿼리에서 사용할 방법을 익명 유형을 확인 하려면이 섹션에서 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-179">Add the code from this section to see how anonymous types are used in queries.</span></span> <span data-ttu-id="7ac11-180">완전 한 레코드 아닌 데이터 원본에서 여러 필드를 반환 하려면 쿼리에서 사용으로 (`currentStudent` 이전 예제에서 레코드) 또는 단일 필드 (`First` 이전 섹션에).</span><span class="sxs-lookup"><span data-stu-id="7ac11-180">You use them in queries when you want to return several fields from the data source rather than complete records (`currentStudent` records in previous examples) or single fields (`First` in the preceding section).</span></span> <span data-ttu-id="7ac11-181">결과에 포함할 필드를 포함 하는 새 명명 된 형식을 정의 하는 대신에 필드를 지정 된 `Select` 절과 컴파일러 속성으로 해당 필드가 있는 익명 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-181">Instead of defining a new named type that contains the fields you want to include in the result, you specify the fields in the `Select` clause and the compiler creates an anonymous type with those fields as its properties.</span></span> <span data-ttu-id="7ac11-182">자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ac11-182">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="7ac11-183">다음 예에서는 이름 및 등 수가 1 ~ 10 생 순서로 상급의 순위를 반환 하는 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-183">The following example creates a query that returns the name and rank of seniors whose academic rank is between 1 and 10, in order of academic rank.</span></span> <span data-ttu-id="7ac11-184">이 예제에서는 유형의 `studentQuery4` 유추 되어야 합니다는 `Select` 절 익명 형식의 인스턴스를 반환 하 고 익명 형식에 사용할 수 있는 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-184">In this example, the type of `studentQuery4` must be inferred because the `Select` clause returns an instance of an anonymous type, and an anonymous type has no usable name.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_6.vb)]  
  
2.  <span data-ttu-id="7ac11-185">빌드하고 CTRL + f 5를 눌러 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-185">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="7ac11-186">콘솔 창에서 결과 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-186">Note the results in the console window.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="7ac11-187">추가 예</span><span class="sxs-lookup"><span data-stu-id="7ac11-187">Additional Examples</span></span>  
 <span data-ttu-id="7ac11-188">다음은 유연성을 설명 하기 위해 추가 예제를 보려면 목록 및의 기본 사항을 살펴보았으므로 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-188">Now that you understand the basics, the following is a list of additional examples to illustrate the flexibility and power of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="7ac11-189">각 예에서는 역할에 대 한 간략 한 설명을 뒤에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-189">Each example is preceded by a brief description of what it does.</span></span> <span data-ttu-id="7ac11-190">유추 된 유형 참조를 각 쿼리에 대 한 쿼리 결과 변수 위에 마우스 포인터를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-190">Rest the mouse pointer over the query result variable for each query to see the inferred type.</span></span> <span data-ttu-id="7ac11-191">사용 하 여 한 `For Each` 루프는 결과를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ac11-191">Use a `For Each` loop to produce the results.</span></span>  
  
 [!code-vb[VbLINQWalkthrough#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/walkthrough-writing-queries_7.vb)]  
  
## <a name="additional-information"></a><span data-ttu-id="7ac11-192">추가 정보</span><span class="sxs-lookup"><span data-stu-id="7ac11-192">Additional Information</span></span>  
 <span data-ttu-id="7ac11-193">특정 형식에 대 한 설명서와 샘플을 읽을 준비가 쿼리 작업의 기본 개념에 익숙한 후 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 에 관심이 있는 공급자:</span><span class="sxs-lookup"><span data-stu-id="7ac11-193">After you are familiar with the basic concepts of working with queries, you are ready to read the documentation and samples for the specific type of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider that you are interested in:</span></span>  
  
 [<span data-ttu-id="7ac11-194">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="7ac11-194">LINQ to Objects</span></span>](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)  
  
 [<span data-ttu-id="7ac11-195">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7ac11-195">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [<span data-ttu-id="7ac11-196">LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="7ac11-196">LINQ to XML</span></span>](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)  
  
 [<span data-ttu-id="7ac11-197">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="7ac11-197">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)  
  
## <a name="see-also"></a><span data-ttu-id="7ac11-198">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ac11-198">See Also</span></span>  
 [<span data-ttu-id="7ac11-199">LINQ(Language-Integrated Query)(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ac11-199">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 [<span data-ttu-id="7ac11-200">Visual Basic에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="7ac11-200">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="7ac11-201">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="7ac11-201">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="7ac11-202">개체 이니셜라이저: 명명된 형식과 익명 형식</span><span class="sxs-lookup"><span data-stu-id="7ac11-202">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="7ac11-203">익명 형식</span><span class="sxs-lookup"><span data-stu-id="7ac11-203">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="7ac11-204">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="7ac11-204">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="7ac11-205">LINQ</span><span class="sxs-lookup"><span data-stu-id="7ac11-205">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="7ac11-206">쿼리</span><span class="sxs-lookup"><span data-stu-id="7ac11-206">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)
