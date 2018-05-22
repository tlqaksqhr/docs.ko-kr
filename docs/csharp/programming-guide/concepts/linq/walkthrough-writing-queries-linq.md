---
title: '연습: C#에서 쿼리 작성(LINQ)'
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], walkthroughs
- LINQ [C#], writing queries
- queries [LINQ in C#], writing
- writing LINQ queries
ms.assetid: 2962a610-419a-4276-9ec8-4b7f2af0c081
ms.openlocfilehash: 10ffdbd6430c0ad55b0a5d71f217a7cb18163741
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-writing-queries-in-c-linq"></a><span data-ttu-id="685a6-102">연습: C#에서 쿼리 작성(LINQ)</span><span class="sxs-lookup"><span data-stu-id="685a6-102">Walkthrough: Writing Queries in C# (LINQ)</span></span>
<span data-ttu-id="685a6-103">이 연습에서는 LINQ 쿼리 식을 작성하는 데 사용되는 C # 언어 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-103">This walkthrough demonstrates the C# language features that are used to write LINQ query expressions.</span></span>  
  
## <a name="create-a-c-project"></a><span data-ttu-id="685a6-104">C# 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="685a6-104">Create a C# Project</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="685a6-105">다음 지침은 Visual Studio용입니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-105">The following instructions are for Visual Studio.</span></span> <span data-ttu-id="685a6-106">다른 개발 환경을 사용하는 경우 System.Core.dll에 대한 참조와 <xref:System.Linq?displayProperty=nameWithType> 네임스페이스에 대한 `using` 지시문을 사용하여 콘솔 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-106">If you are using a different development environment, create a console project with a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
#### <a name="to-create-a-project-in-visual-studio"></a><span data-ttu-id="685a6-107">Visual Studio에서 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="685a6-107">To create a project in Visual Studio</span></span>  
  
1.  <span data-ttu-id="685a6-108">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-108">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="685a6-109">메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-109">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="685a6-110">**새 프로젝트** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-110">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="685a6-111">**설치됨**, **템플릿**, **Visual C#** 을 차례로 확장하고 **콘솔 응용 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-111">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>  
  
4.  <span data-ttu-id="685a6-112">**이름** 텍스트 상자에 다른 이름을 입력하거나 기본 이름을 선택한 다음 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-112">In the **Name** text box, enter a different name or accept the default name, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="685a6-113">**솔루션 탐색기**에 새 프로젝트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-113">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="685a6-114">프로젝트에 System.Core.dll에 대한 참조 및 <xref:System.Linq?displayProperty=nameWithType> 네임스페이스에 대한 `using` 지시문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-114">Notice that your project has a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="create-an-in-memory-data-source"></a><span data-ttu-id="685a6-115">메모리 내 데이터 소스 만들기</span><span class="sxs-lookup"><span data-stu-id="685a6-115">Create an in-Memory Data Source</span></span>  
 <span data-ttu-id="685a6-116">쿼리의 데이터 소스는 간단한 `Student` 개체 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-116">The data source for the queries is a simple list of `Student` objects.</span></span> <span data-ttu-id="685a6-117">각 `Student` 레코드에는 이름, 성 및 클래스의 테스트 점수를 나타내는 정수 배열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-117">Each `Student` record has a first name, last name, and an array of integers that represents their test scores in the class.</span></span> <span data-ttu-id="685a6-118">프로젝트에 이 코드를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-118">Copy this code into your project.</span></span> <span data-ttu-id="685a6-119">다음 특성에 주의합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-119">Note the following characteristics:</span></span>  
  
-   <span data-ttu-id="685a6-120">`Student` 클래스는 자동으로 구현된 속성으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-120">The `Student` class consists of auto-implemented properties.</span></span>  
  
-   <span data-ttu-id="685a6-121">목록의 각 학생은 개체 이니셜라이저로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-121">Each student in the list is initialized with an object initializer.</span></span>  
  
-   <span data-ttu-id="685a6-122">목록 자체는 컬렉션 이니셜라이저로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-122">The list itself is initialized with a collection initializer.</span></span>  
  
 <span data-ttu-id="685a6-123">이 전체 데이터 구조는 생성자 또는 명시적 멤버 액세스에 대한 명시적 호출 없이 초기화되고 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-123">This whole data structure will be initialized and instantiated without explicit calls to any constructor or explicit member access.</span></span> <span data-ttu-id="685a6-124">이러한 새로운 기능에 대한 자세한 내용은 [자동으로 구현된 속성](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) 및 [개체 및 컬렉션 이니셜라이저](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="685a6-124">For more information about these new features, see [Auto-Implemented Properties](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md) and [Object and Collection Initializers](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="685a6-125">데이터 소스를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="685a6-125">To add the data source</span></span>  
  
-   <span data-ttu-id="685a6-126">`Student` 클래스 및 초기화된 학생 목록을 프로젝트의 `Program` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-126">Add the `Student` class and the initialized list of students to the `Program` class in your project.</span></span>  
  
     [!code-csharp[CsLinqGettingStarted#11](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_1.cs)]  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="685a6-127">학생 목록에 새 학생을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="685a6-127">To add a new Student to the Students list</span></span>  
  
1.  <span data-ttu-id="685a6-128">새 `Student`를 `Students` 목록에 추가하고 원하는 이름 및 시험 점수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-128">Add a new `Student` to the `Students` list and use a name and test scores of your choice.</span></span> <span data-ttu-id="685a6-129">개체 이니셜라이저의 구문을 더 잘 알 수 있도록 새로운 학생 정보를 모두 입력해 보세요.</span><span class="sxs-lookup"><span data-stu-id="685a6-129">Try typing all the new student information in order to better learn the syntax for the object initializer.</span></span>  
  
## <a name="create-the-query"></a><span data-ttu-id="685a6-130">쿼리 만들기</span><span class="sxs-lookup"><span data-stu-id="685a6-130">Create the Query</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="685a6-131">단순 쿼리를 작성하려면</span><span class="sxs-lookup"><span data-stu-id="685a6-131">To create a simple query</span></span>  
  
-   <span data-ttu-id="685a6-132">응용 프로그램의 `Main` 메서드에서, 실행 시 첫 번째 테스트의 점수가 90보다 큰 모든 학생의 목록을 생성하는 간단한 쿼리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-132">In the application's `Main` method, create a simple query that, when it is executed, will produce a list of all students whose score on the first test was greater than 90.</span></span> <span data-ttu-id="685a6-133">전체 `Student` 개체가 선택되므로 쿼리의 형식은 `IEnumerable<Student>`입니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-133">Note that because the whole `Student` object is selected, the type of the query is `IEnumerable<Student>`.</span></span> <span data-ttu-id="685a6-134">[var](../../../../csharp/language-reference/keywords/var.md) 키워드를 사용하여 코드에서 암시적 형식을 사용할 수도 있지만, 결과를 명확하게 설명하기 위해 명시적 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-134">Although the code could also use implicit typing by using the [var](../../../../csharp/language-reference/keywords/var.md) keyword, explicit typing is used to clearly illustrate results.</span></span> <span data-ttu-id="685a6-135">`var`에 대한 자세한 내용은 [암시적으로 형식화된 지역 변수](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="685a6-135">(For more information about `var`, see [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).)</span></span>  
  
     <span data-ttu-id="685a6-136">또한 쿼리의 범위 변수 `student`는 소스의 각 `Student`에 대한 참조로 사용되며, 각 개체에 대한 멤버 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-136">Note also that the query's range variable, `student`, serves as a reference to each `Student` in the source, providing member access for each object.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#12](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_2.cs)]  
  
## <a name="execute-the-query"></a><span data-ttu-id="685a6-137">쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="685a6-137">Execute the Query</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="685a6-138">쿼리를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="685a6-138">To execute the query</span></span>  
  
1.  <span data-ttu-id="685a6-139">이제 쿼리를 실행하도록 할 `foreach` 루프를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-139">Now write the `foreach` loop that will cause the query to execute.</span></span> <span data-ttu-id="685a6-140">다음은 코드에 대한 유의 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-140">Note the following about the code:</span></span>  
  
    -   <span data-ttu-id="685a6-141">반환된 시퀀스의 각 요소는 `foreach` 루프의 반복 변수를 통해 액세스됩니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-141">Each element in the returned sequence is accessed through the iteration variable in the `foreach` loop.</span></span>  
  
    -   <span data-ttu-id="685a6-142">이 변수의 형식은 `Student`이며, 쿼리 변수 형식은 `IEnumerable<Student>`과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-142">The type of this variable is `Student`, and the type of the query variable is compatible, `IEnumerable<Student>`.</span></span>  
  
2.  <span data-ttu-id="685a6-143">이 코드를 추가한 후 응용 프로그램을 빌드하고 실행하고 **콘솔** 창에서 결과를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="685a6-143">After you have added this code, build and run the application to see the results in the **Console** window.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#13](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_3.cs)]  
  
#### <a name="to-add-another-filter-condition"></a><span data-ttu-id="685a6-144">다른 필터 조건을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="685a6-144">To add another filter condition</span></span>  
  
1.  <span data-ttu-id="685a6-145">쿼리를 구체화하기 위해 `where` 절에서 여러 부울 조건을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-145">You can combine multiple Boolean conditions in the `where` clause in order to further refine a query.</span></span> <span data-ttu-id="685a6-146">다음 코드는 쿼리를 실행하여 첫 번째 점수가 90을 초과하고 마지막 점수가 80 미만인 학생들을 반환하도록 하는 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-146">The following code adds a condition so that the query returns those students whose first score was over 90 and whose last score was less than 80.</span></span> <span data-ttu-id="685a6-147">`where` 절은 다음 코드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-147">The `where` clause should resemble the following code.</span></span>  
  
    ```  
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     <span data-ttu-id="685a6-148">자세한 내용은 [where 절](../../../../csharp/language-reference/keywords/where-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="685a6-148">For more information, see [where clause](../../../../csharp/language-reference/keywords/where-clause.md).</span></span>  
  
## <a name="modify-the-query"></a><span data-ttu-id="685a6-149">쿼리 수정</span><span class="sxs-lookup"><span data-stu-id="685a6-149">Modify the Query</span></span>  
  
#### <a name="to-order-the-results"></a><span data-ttu-id="685a6-150">결과를 정렬하려면</span><span class="sxs-lookup"><span data-stu-id="685a6-150">To order the results</span></span>  
  
1.  <span data-ttu-id="685a6-151">특정 순서로 되어 있는 경우 결과를 더 쉽게 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-151">It will be easier to scan the results if they are in some kind of order.</span></span> <span data-ttu-id="685a6-152">반환된 시퀀스를 소스 요소에서 액세스 가능한 필드 기준으로 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-152">You can order the returned sequence by any accessible field in the source elements.</span></span> <span data-ttu-id="685a6-153">예를 들어, 다음 `orderby` 절은 각 학생의 성에 따라 결과를 사전순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-153">For example, the following `orderby` clause orders the results in alphabetical order from A to Z according to the last name of each student.</span></span> <span data-ttu-id="685a6-154">`where` 문 바로 다음과 `select` 문 앞에서 다음 `orderby` 절을 쿼리에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-154">Add the following `orderby` clause to your query, right after the `where` statement and before the `select` statement:</span></span>  
  
    ```  
    orderby student.Last ascending  
    ```  
  
2.  <span data-ttu-id="685a6-155">이제 가장 높은 점수에서 가장 낮은 점수까지 첫 번째 테스트의 점수에 따라 역순으로 결과를 정렬하도록 `orderby` 절을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-155">Now change the `orderby` clause so that it orders the results in reverse order according to the score on the first test, from the highest score to the lowest score.</span></span>  
  
    ```  
    orderby student.Scores[0] descending  
    ```  
  
3.  <span data-ttu-id="685a6-156">점수를 볼 수 있도록 `WriteLine` 형식 문자열을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-156">Change the `WriteLine` format string so that you can see the scores:</span></span>  
  
    ```  
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     <span data-ttu-id="685a6-157">자세한 내용은 [orderby 절](../../../../csharp/language-reference/keywords/orderby-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="685a6-157">For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).</span></span>  
  
#### <a name="to-group-the-results"></a><span data-ttu-id="685a6-158">결과를 그룹화하려면</span><span class="sxs-lookup"><span data-stu-id="685a6-158">To group the results</span></span>  
  
1.  <span data-ttu-id="685a6-159">그룹화는 쿼리 식의 강력한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-159">Grouping is a powerful capability in query expressions.</span></span> <span data-ttu-id="685a6-160">그룹 절이 있는 쿼리는 그룹 시퀀스를 생성하며, 각 그룹 자체는 `Key` 및 해당 그룹의 모든 멤버로 구성된 시퀀스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-160">A query with a group clause produces a sequence of groups, and each group itself contains a `Key` and a sequence that consists of all the members of that group.</span></span> <span data-ttu-id="685a6-161">다음과 같은 새 쿼리는 학생 성의 첫 글자를 키로 사용하여 학생들을 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-161">The following new query groups the students by using the first letter of their last name as the key.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#14](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_4.cs)]  
  
2.  <span data-ttu-id="685a6-162">이제 쿼리 형식이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-162">Note that the type of the query has now changed.</span></span> <span data-ttu-id="685a6-163">이제 쿼리를 실행하면 `char` 형식을 키로 가지고 있고 `Student` 개체의 시퀀스를 가지고 있는 그룹의 시퀀스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-163">It now produces a sequence of groups that have a `char` type as a key, and a sequence of `Student` objects.</span></span> <span data-ttu-id="685a6-164">쿼리 형식이 변경되었으므로 다음 코드는 `foreach` 실행 루프도 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-164">Because the type of the query has changed, the following code changes the `foreach` execution loop also:</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#15](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_5.cs)]  
  
3.  <span data-ttu-id="685a6-165">응용 프로그램을 실행하고 **콘솔** 창에서 결과를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-165">Run the application and view the results in the **Console** window.</span></span>  
  
     <span data-ttu-id="685a6-166">자세한 내용은 [group 절](../../../../csharp/language-reference/keywords/group-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="685a6-166">For more information, see [group clause](../../../../csharp/language-reference/keywords/group-clause.md).</span></span>  
  
#### <a name="to-make-the-variables-implicitly-typed"></a><span data-ttu-id="685a6-167">변수를 암시적으로 형식화하려면</span><span class="sxs-lookup"><span data-stu-id="685a6-167">To make the variables implicitly typed</span></span>  
  
1.  <span data-ttu-id="685a6-168">`IGroupings`의 `IEnumerables`를 명시적으로 코딩하는 작업은 지루할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-168">Explicitly coding `IEnumerables` of `IGroupings` can quickly become tedious.</span></span> <span data-ttu-id="685a6-169">`var`을 사용하여 동일한 쿼리 및 `foreach` 루프를 훨씬 더 편리하게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-169">You can write the same query and `foreach` loop much more conveniently by using `var`.</span></span> <span data-ttu-id="685a6-170">`var` 키워드는 개체 형식을 변경하지 않고, 형식을 추론하도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-170">The `var` keyword does not change the types of your objects; it just instructs the compiler to infer the types.</span></span> <span data-ttu-id="685a6-171">`studentQuery`의 형식 및 `group` 반복 변수를 `var`로 변경하고 쿼리를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-171">Change the type of `studentQuery` and the iteration variable `group` to `var` and rerun the query.</span></span> <span data-ttu-id="685a6-172">내부 `foreach` 루프에서 반복 변수의 형식은 여전히 `Student`로 지정되며 쿼리는 이전과 마찬가지로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-172">Note that in the inner `foreach` loop, the iteration variable is still typed as `Student`, and the query works just as before.</span></span> <span data-ttu-id="685a6-173">`s` 반복 변수를 `var`로 변경하고 쿼리를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-173">Change the `s` iteration variable to `var` and run the query again.</span></span> <span data-ttu-id="685a6-174">정확히 동일한 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-174">You see that you get exactly the same results.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#16](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_6.cs)]  
  
     <span data-ttu-id="685a6-175">[var](../../../../csharp/language-reference/keywords/var.md)에 대한 자세한 내용은 [암시적으로 형식화된 지역 변수](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="685a6-175">For more information about [var](../../../../csharp/language-reference/keywords/var.md), see [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
#### <a name="to-order-the-groups-by-their-key-value"></a><span data-ttu-id="685a6-176">키 값을 기준으로 그룹을 정렬하려면</span><span class="sxs-lookup"><span data-stu-id="685a6-176">To order the groups by their key value</span></span>  
  
1.  <span data-ttu-id="685a6-177">이전 쿼리를 실행하면 그룹이 사전순으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-177">When you run the previous query, you notice that the groups are not in alphabetical order.</span></span> <span data-ttu-id="685a6-178">이를 변경하려면 `group` 절 뒤에 `orderby` 절을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-178">To change this, you must provide an `orderby` clause after the `group` clause.</span></span> <span data-ttu-id="685a6-179">그러나 `orderby` 절을 사용하려면 우선 `group` 절로 만든 그룹에 대한 참조 역할을 하는 식별자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-179">But to use an `orderby` clause, you first need an identifier that serves as a reference to the groups created by the `group` clause.</span></span> <span data-ttu-id="685a6-180">다음과 같이 `into` 키워드를 사용하여 식별자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-180">You provide the identifier by using the `into` keyword, as follows:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#17](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_7.cs)]  
  
     <span data-ttu-id="685a6-181">이 쿼리를 실행하면 이제 그룹이 사전순으로 정렬되는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-181">When you run this query, you will see the groups are now sorted in alphabetical order.</span></span>  
  
#### <a name="to-introduce-an-identifier-by-using-let"></a><span data-ttu-id="685a6-182">let을 사용하여 식별자를 소개하려면</span><span class="sxs-lookup"><span data-stu-id="685a6-182">To introduce an identifier by using let</span></span>  
  
1.  <span data-ttu-id="685a6-183">`let` 키워드를 사용하여 쿼리 식의 식 결과에 대한 식별자를 소개할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-183">You can use the `let` keyword to introduce an identifier for any expression result in the query expression.</span></span> <span data-ttu-id="685a6-184">이 식별자는 다음 예제에서처럼 편리하게 사용할 수도 있고, 여러 번 계산할 필요가 없도록 표현식의 결과를 저장하여 성능을 향상시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-184">This identifier can be a convenience, as in the following example, or it can enhance performance by storing the results of an expression so that it does not have to be calculated multiple times.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#18](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_8.cs)]  
  
     <span data-ttu-id="685a6-185">자세한 내용은 [let 절](../../../../csharp/language-reference/keywords/let-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="685a6-185">For more information, see [let clause](../../../../csharp/language-reference/keywords/let-clause.md).</span></span>  
  
#### <a name="to-use-method-syntax-in-a-query-expression"></a><span data-ttu-id="685a6-186">쿼리 식에서 메서드 구문을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="685a6-186">To use method syntax in a query expression</span></span>  
  
1.  <span data-ttu-id="685a6-187">[LINQ의 쿼리 구문 및 메서드 구문](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)에 설명된 대로 일부 쿼리 작업은 메서드 구문을 사용해야만 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-187">As described in [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md), some query operations can only be expressed by using method syntax.</span></span> <span data-ttu-id="685a6-188">다음 코드는 소스 시퀀스의 각 `Student`에 대한 총 점수를 계산한 다음, 해당 쿼리의 결과에 대해 `Average()` 메서드를 호출하여 클래스의 평균 점수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-188">The following code calculates the total score for each `Student` in the source sequence, and then calls the `Average()` method on the results of that query to calculate the average score of the class.</span></span> <span data-ttu-id="685a6-189">쿼리 식 전후에 괄호를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-189">Note the placement of parentheses around the query expression.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#19](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_9.cs)]  
  
#### <a name="to-transform-or-project-in-the-select-clause"></a><span data-ttu-id="685a6-190">select 절에서 변환 또는 프로젝션하려면</span><span class="sxs-lookup"><span data-stu-id="685a6-190">To transform or project in the select clause</span></span>  
  
1.  <span data-ttu-id="685a6-191">쿼리가 소스 시퀀스의 요소와 다른 요소를 갖는 시퀀스를 생성하는 것은 매우 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-191">It is very common for a query to produce a sequence whose elements differ from the elements in the source sequences.</span></span> <span data-ttu-id="685a6-192">이전 쿼리 및 실행 루프를 삭제하거나 주석으로 처리하고 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-192">Delete or comment out your previous query and execution loop, and replace it with the following code.</span></span> <span data-ttu-id="685a6-193">쿼리는 문자열 시퀀스(`Students` 아님)를 반환하며 이 사실은 `foreach` 루프에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-193">Note that the query returns a sequence of strings (not `Students`), and this fact is reflected in the `foreach` loop.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#20](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_10.cs)]  
  
2.  <span data-ttu-id="685a6-194">이 연습의 앞부분에 있는 코드는 평균 클래스 점수가 약 334임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-194">Code earlier in this walkthrough indicated that the average class score is approximately 334.</span></span> <span data-ttu-id="685a6-195">총점이 클래스 평균보다 큰 `Students`의 시퀀스를 `Student ID`와 함께 생성하려면 `select` 문에서 무명 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-195">To produce a sequence of `Students` whose total score is greater than the class average, together with their `Student ID`, you can use an anonymous type in the `select` statement:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#21](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/walkthrough-writing-queries-linq_11.cs)]  
  
## <a name="next-steps"></a><span data-ttu-id="685a6-196">다음 단계</span><span class="sxs-lookup"><span data-stu-id="685a6-196">Next Steps</span></span>  
 <span data-ttu-id="685a6-197">C#에서 쿼리 작업의 기본 사항에 익숙해지면 관심이 있는 특정 LINQ 공급자 형식에 대한 설명서와 샘플을 읽을 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="685a6-197">After you are familiar with the basic aspects of working with queries in C#, you are ready to read the documentation and samples for the specific type of LINQ provider you are interested in:</span></span>  
  
 [<span data-ttu-id="685a6-198">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="685a6-198">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
  
 [<span data-ttu-id="685a6-199">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="685a6-199">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)  
  
 [<span data-ttu-id="685a6-200">LINQ to XML(C#)</span><span class="sxs-lookup"><span data-stu-id="685a6-200">LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [<span data-ttu-id="685a6-201">LINQ to Objects(C#)</span><span class="sxs-lookup"><span data-stu-id="685a6-201">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="685a6-202">참고 항목</span><span class="sxs-lookup"><span data-stu-id="685a6-202">See Also</span></span>  
 [<span data-ttu-id="685a6-203">LINQ(Language-Integrated Query)(C#)</span><span class="sxs-lookup"><span data-stu-id="685a6-203">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)  
 [<span data-ttu-id="685a6-204">C#에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="685a6-204">Getting Started with LINQ in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="685a6-205">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="685a6-205">LINQ Query Expressions</span></span>](../../../../csharp/programming-guide/linq-query-expressions/index.md)
