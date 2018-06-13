---
title: 기본 쿼리 작업(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
ms.openlocfilehash: 5587a60e97464324659b325e38a18ac25488d30d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644123"
---
# <a name="basic-query-operations-visual-basic"></a><span data-ttu-id="7eafa-102">기본 쿼리 작업(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7eafa-102">Basic Query Operations (Visual Basic)</span></span>
<span data-ttu-id="7eafa-103">이 항목에서는에 대 한 간략 한 소개 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Visual Basic을 쿼리에서 수행 하는 작업의 일반적인 종류의 일부에 대 한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-103">This topic provides a brief introduction to [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] expressions in Visual Basic, and to some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="7eafa-104">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7eafa-104">For more information, see the following topics:</span></span>  
  
 [<span data-ttu-id="7eafa-105">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="7eafa-105">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [<span data-ttu-id="7eafa-106">쿼리</span><span class="sxs-lookup"><span data-stu-id="7eafa-106">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [<span data-ttu-id="7eafa-107">연습: Visual Basic에서 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="7eafa-107">Walkthrough: Writing Queries in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a><span data-ttu-id="7eafa-108">데이터 원본 (원본)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-108">Specifying the Data Source (From)</span></span>  
 <span data-ttu-id="7eafa-109">에 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리는 첫 번째 단계는 쿼리 하려는 데이터 원본을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-109">In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, the first step is to specify the data source that you want to query.</span></span> <span data-ttu-id="7eafa-110">따라서는 `From` 쿼리의 절에에서는 항상 먼저 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-110">Therefore, the `From` clause in a query always comes first.</span></span> <span data-ttu-id="7eafa-111">쿼리 연산자는 선택 하 고 소스의 형식에 따라 결과 모양을 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-111">Query operators select and shape the result based on the type of the source.</span></span>  
  
 [!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]  
  
 <span data-ttu-id="7eafa-112">`From` 절에는 데이터 원본을 지정 합니다. `customers`, 및 *범위 변수*, `cust`합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-112">The `From` clause specifies the data source, `customers`, and a *range variable*, `cust`.</span></span> <span data-ttu-id="7eafa-113">쿼리 식에서 실제 반복이 발생 하지 한다는 점을 제외 하 고 범위 변수는 루프 반복 변수는 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-113">The range variable is like a loop iteration variable, except that in a query expression, no actual iteration occurs.</span></span> <span data-ttu-id="7eafa-114">쿼리가 실행 될 때, 자주 사용 하 여 한 `For Each` 루프의 각 연속 요소에 대 한 참조로 사용 범위 변수 `customers`합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-114">When the query is executed, often by using a `For Each` loop, the range variable serves as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="7eafa-115">컴파일러에서 `cust` 형식을 유추할 수 있으므로 명시적으로 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-115">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="7eafa-116">가 있거나 없는 명시적인 입력을 작성 하는 쿼리의 예 참조 [쿼리 작업 (Visual Basic)의 형식 관계](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-116">For examples of queries written with and without explicit typing, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
 <span data-ttu-id="7eafa-117">사용 하는 방법에 대 한 자세한 내용은 `From` 절 Visual basic에서 참조 [From 절이](../../../../visual-basic/language-reference/queries/from-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-117">For more information about how to use the `From` clause in Visual Basic, see [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md).</span></span>  
  
## <a name="filtering-data-where"></a><span data-ttu-id="7eafa-118">데이터 필터링 (위치)</span><span class="sxs-lookup"><span data-stu-id="7eafa-118">Filtering Data (Where)</span></span>  
 <span data-ttu-id="7eafa-119">아마도 가장 일반적인 쿼리 작업 하는 부울 식 형태로 필터를 적용 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-119">Probably the most common query operation is applying a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="7eafa-120">다음 쿼리 식이 true 인 요소에만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-120">The query then returns only those elements for which the expression is true.</span></span> <span data-ttu-id="7eafa-121">A `Where` 절을 사용 하 여 필터링을 수행 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-121">A `Where` clause is used to perform the filtering.</span></span> <span data-ttu-id="7eafa-122">필터 결과 시퀀스에 포함할 데이터 원본에 있는 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-122">The filter specifies which elements in the data source to include in the resulting sequence.</span></span> <span data-ttu-id="7eafa-123">다음 예제에서는 주소 런던에 살고 있는 고객만 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-123">In the following example, only those customers who have an address in London are included.</span></span>  
  
 [!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]  
  
 <span data-ttu-id="7eafa-124">와 같은 논리 연산자를 사용할 수 `And` 및 `Or` 에서 필터 식을 결합 하는 `Where` 절.</span><span class="sxs-lookup"><span data-stu-id="7eafa-124">You can use logical operators such as `And` and `Or` to combine filter expressions in a `Where` clause.</span></span> <span data-ttu-id="7eafa-125">예를 들어 고객에 대해서만 Devon 이름이 고 런던에서는 반환 하려면 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-125">For example, to return only those customers who are from London and whose name is Devon, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 <span data-ttu-id="7eafa-126">런던 또는 파리에서 고객을 반환 하려면 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-126">To return customers from London or Paris, use the following code:</span></span>  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 <span data-ttu-id="7eafa-127">사용 하는 방법에 대 한 자세한 내용은 `Where` 절 Visual basic에서 참조 [Where 절](../../../../visual-basic/language-reference/queries/where-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-127">For more information about how to use the `Where` clause in Visual Basic, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>  
  
## <a name="ordering-data-order-by"></a><span data-ttu-id="7eafa-128">(Order By) 데이터 정렬</span><span class="sxs-lookup"><span data-stu-id="7eafa-128">Ordering Data (Order By)</span></span>  
 <span data-ttu-id="7eafa-129">자주 하는 것을 특정 순서로 반환 되는 데이터 정렬입니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-129">It often is convenient to sort returned data into a particular order.</span></span> <span data-ttu-id="7eafa-130">`Order By` 절에서 지정된 된 필드 또는 필드 정렬할 반환된 된 시퀀스의 요소를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-130">The `Order By` clause will cause the elements in the returned sequence to be sorted on a specified field or fields.</span></span> <span data-ttu-id="7eafa-131">예를 들어 다음 쿼리는 정렬 기준으로 결과 `Name` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-131">For example, the following query sorts the results based on the `Name` property.</span></span> <span data-ttu-id="7eafa-132">때문에 `Name` 문자열인 경우 A에서 Z까지 반환된 된 데이터를 사전순으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-132">Because `Name` is a string, the returned data will be sorted alphabetically, from A to Z.</span></span>  
  
 [!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]  
  
 <span data-ttu-id="7eafa-133">결과를 역순으로 정렬하려면 `Order By...Descending` 절을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-133">To order the results in reverse order, from Z to A, use the `Order By...Descending` clause.</span></span> <span data-ttu-id="7eafa-134">기본값은 `Ascending` 하지 않은 경우 `Ascending` 나 `Descending` 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-134">The default is `Ascending` when neither `Ascending` nor `Descending` is specified.</span></span>  
  
 <span data-ttu-id="7eafa-135">사용 하는 방법에 대 한 자세한 내용은 `Order By` 절 Visual basic에서 참조 [Order By 절](../../../../visual-basic/language-reference/queries/order-by-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-135">For more information about how to use the `Order By` clause in Visual Basic, see [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
## <a name="selecting-data-select"></a><span data-ttu-id="7eafa-136">(선택) 데이터 선택</span><span class="sxs-lookup"><span data-stu-id="7eafa-136">Selecting Data (Select)</span></span>  
 <span data-ttu-id="7eafa-137">`Select` 절 형식과 반환 된 요소의 콘텐츠를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-137">The `Select` clause specifies the form and content of returned elements.</span></span> <span data-ttu-id="7eafa-138">결과의 전체으로 구성할 것인지를 지정할 수는 예를 들어 `Customer` 개체를 하나만 `Customer` 계산에 따라 속성, 속성 하위 집합, 다양 한 데이터 원본 또는 몇 가지 새로운 결과 형식에서 속성을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-138">For example, you can specify whether your results will consist of complete `Customer` objects, just one `Customer` property, a subset of properties, a combination of properties from various data sources, or some new result type based on a computation.</span></span> <span data-ttu-id="7eafa-139">`Select` 절이 소스 요소의 복사본이 아닌 다른 항목을 생성하는 경우 이 작업을 *프로젝션*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-139">When the `Select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span>  
  
 <span data-ttu-id="7eafa-140">전체로 구성 된 컬렉션을 검색 하려면 `Customer` 개체 자체 범위 변수를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-140">To retrieve a collection that consists of complete `Customer` objects, select the range variable itself:</span></span>  
  
 [!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]  
  
 <span data-ttu-id="7eafa-141">경우는 `Customer` 인스턴스는 많은 필드를 가진 대형 개체 하 고 검색 하려는 모든 이름이 고, 선택할 수 있습니다 `cust.Name`다음 예제에 나온 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-141">If a `Customer` instance is a large object that has many fields, and all that you want to retrieve is the name, you can select `cust.Name`, as shown in the following example.</span></span> <span data-ttu-id="7eafa-142">지역 형식 유추의 컬렉션에서이 결과 유형을 변경 인식 `Customer` 개체를 문자열 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-142">Local type inference recognizes that this changes the result type from a collection of `Customer` objects to a collection of strings.</span></span>  
  
 [!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]  
  
 <span data-ttu-id="7eafa-143">데이터 원본에서 여러 필드를 선택 하는 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-143">To select multiple fields from the data source, you have two choices:</span></span>  
  
-   <span data-ttu-id="7eafa-144">에 `Select` 절의 결과에 포함할 필드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-144">In the `Select` clause, specify the fields you want to include in the result.</span></span> <span data-ttu-id="7eafa-145">컴파일러에 해당 필드가 속성으로 익명 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-145">The compiler will define an anonymous type that has those fields as its properties.</span></span> <span data-ttu-id="7eafa-146">자세한 내용은 [무명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7eafa-146">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="7eafa-147">다음 예에서 반환 되는 요소는 익명 형식의 인스턴스 이기 때문에 참조할 수 없습니다 형식 이름으로 다른 곳에서 사용자 코드에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-147">Because the returned elements in the following example are instances of an anonymous type, you cannot refer to the type by name elsewhere in your code.</span></span> <span data-ttu-id="7eafa-148">컴파일러에서 지정 된 이름 형식에 대 한 일반 Visual Basic 코드에서 유효 하지 않은 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-148">The compiler-designated name for the type contains characters that are not valid in normal Visual Basic code.</span></span> <span data-ttu-id="7eafa-149">다음 예제에서는의 쿼리에 의해 반환 되는 컬렉션의 요소에서에서 `londonCusts4` 익명 형식의 인스턴스인</span><span class="sxs-lookup"><span data-stu-id="7eafa-149">In the following example, the elements in the collection that is returned by the query in `londonCusts4` are instances of an anonymous type</span></span>  
  
     [!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     <span data-ttu-id="7eafa-150">-또는-</span><span class="sxs-lookup"><span data-stu-id="7eafa-150">-or-</span></span>  
  
-   <span data-ttu-id="7eafa-151">명명 된 유형을 정의 하는 결과에 포함 하 고 만들고에서 형식의 인스턴스를 초기화 하 고 원하는 특정 필드가 `Select` 절.</span><span class="sxs-lookup"><span data-stu-id="7eafa-151">Define a named type that contains the particular fields that you want to include in the result, and create and initialize instances of the type in the `Select` clause.</span></span> <span data-ttu-id="7eafa-152">반환 되는 컬렉션 외부 개별 결과 사용 해야 하는 경우에 또는 메서드 호출에 매개 변수로 전달 해야 할 경우이 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-152">Use this option only if you have to use individual results outside the collection in which they are returned, or if you have to pass them as parameters in method calls.</span></span> <span data-ttu-id="7eafa-153">유형의 `londonCusts5` 다음 예제는 IEnumerable (Of NamePhone).</span><span class="sxs-lookup"><span data-stu-id="7eafa-153">The type of `londonCusts5` in the following example is IEnumerable(Of NamePhone).</span></span>  
  
     [!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]  
  
 <span data-ttu-id="7eafa-154">사용 하는 방법에 대 한 자세한 내용은 `Select` 절 Visual basic에서 참조 [Select 절](../../../../visual-basic/language-reference/queries/select-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-154">For more information about how to use the `Select` clause in Visual Basic, see [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
## <a name="joining-data-join-and-group-join"></a><span data-ttu-id="7eafa-155">조인 데이터 (조인 및 그룹 조인)</span><span class="sxs-lookup"><span data-stu-id="7eafa-155">Joining Data (Join and Group Join)</span></span>  
 <span data-ttu-id="7eafa-156">둘 이상의 데이터 원본에 결합할 수는 `From` 여러 가지 방법으로 절.</span><span class="sxs-lookup"><span data-stu-id="7eafa-156">You can combine more than one data source in the `From` clause in several ways.</span></span> <span data-ttu-id="7eafa-157">예를 들어 다음 코드는 두 개의 데이터 원본이 사용 하 고 암시적으로 결과에서 둘 모두에서 속성을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-157">For example, the following code uses two data sources and implicitly combines properties from both of them in the result.</span></span> <span data-ttu-id="7eafa-158">쿼리는 마지막 이름이 함께 시작 하는 학생은 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-158">The query selects students whose last names start with a vowel.</span></span>  
  
 [!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  <span data-ttu-id="7eafa-159">만든 학생의 목록으로이 코드를 실행할 수 [하는 방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-159">You can run this code with the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span>  
  
 <span data-ttu-id="7eafa-160">`Join` 키워드는 해당 하는 `INNER JOIN` sql에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-160">The `Join` keyword is equivalent to an `INNER JOIN` in SQL.</span></span> <span data-ttu-id="7eafa-161">두 컬렉션의 요소 간에 일치 하는 키 값을 기반으로 하는 두 컬렉션을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-161">It combines two collections based on matching key values between elements in the two collections.</span></span> <span data-ttu-id="7eafa-162">쿼리 키 값이 일치 하는 컬렉션 요소를의 전체 또는 일부를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-162">The query returns all or part of the collection elements that have matching key values.</span></span> <span data-ttu-id="7eafa-163">예를 들어 다음 코드는 이전 암시적 조인과의 동작을 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-163">For example, the following code duplicates the action of the previous implicit join.</span></span>  
  
 [!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]  
  
 <span data-ttu-id="7eafa-164">`Group Join` 마찬가지로 컬렉션을 단일 계층 구조 컬렉션으로 결합 한 `LEFT JOIN` sql에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-164">`Group Join` combines collections into a single hierarchical collection, just like a `LEFT JOIN` in SQL.</span></span> <span data-ttu-id="7eafa-165">자세한 내용은 참조 [Join 절](../../../../visual-basic/language-reference/queries/join-clause.md) 및 [Group Join 절](../../../../visual-basic/language-reference/queries/group-join-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-165">For more information, see [Join Clause](../../../../visual-basic/language-reference/queries/join-clause.md) and [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md).</span></span>  
  
## <a name="grouping-data-group-by"></a><span data-ttu-id="7eafa-166">데이터 그룹화 (Group By)</span><span class="sxs-lookup"><span data-stu-id="7eafa-166">Grouping Data (Group By)</span></span>  
 <span data-ttu-id="7eafa-167">추가할 수는 `Group By` 요소 중 하나 이상의 필드에 따라 쿼리 결과의 요소를 그룹화 하는 절.</span><span class="sxs-lookup"><span data-stu-id="7eafa-167">You can add a `Group By` clause to group the elements in a query result according to one or more fields of the elements.</span></span> <span data-ttu-id="7eafa-168">예를 들어 다음 코드는 클래스 연도별 학생 들을 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-168">For example, the following code groups students by class year.</span></span>  
  
 [!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]  
  
 <span data-ttu-id="7eafa-169">만든 학생의 목록을 사용 하 여이 코드를 실행 하는 경우 [하는 방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)의 출력은 `For Each` 문이:</span><span class="sxs-lookup"><span data-stu-id="7eafa-169">If you run this code using the list of students created in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), the output from the `For Each` statement is:</span></span>  
  
 <span data-ttu-id="7eafa-170">연도: Junior</span><span class="sxs-lookup"><span data-stu-id="7eafa-170">Year: Junior</span></span>  
  
 <span data-ttu-id="7eafa-171">Tucker, Michael</span><span class="sxs-lookup"><span data-stu-id="7eafa-171">Tucker, Michael</span></span>  
  
 <span data-ttu-id="7eafa-172">Garcia, Hugo</span><span class="sxs-lookup"><span data-stu-id="7eafa-172">Garcia, Hugo</span></span>  
  
 <span data-ttu-id="7eafa-173">Garcia, Debra</span><span class="sxs-lookup"><span data-stu-id="7eafa-173">Garcia, Debra</span></span>  
  
 <span data-ttu-id="7eafa-174">Tucker, 창</span><span class="sxs-lookup"><span data-stu-id="7eafa-174">Tucker, Lance</span></span>  
  
 <span data-ttu-id="7eafa-175">연도: 수석</span><span class="sxs-lookup"><span data-stu-id="7eafa-175">Year: Senior</span></span>  
  
 <span data-ttu-id="7eafa-176">Omelchenko, Svetlana</span><span class="sxs-lookup"><span data-stu-id="7eafa-176">Omelchenko, Svetlana</span></span>  
  
 <span data-ttu-id="7eafa-177">홍현아라, Michiko</span><span class="sxs-lookup"><span data-stu-id="7eafa-177">Osada, Michiko</span></span>  
  
 <span data-ttu-id="7eafa-178">Fakhouri, Fadi</span><span class="sxs-lookup"><span data-stu-id="7eafa-178">Fakhouri, Fadi</span></span>  
  
 <span data-ttu-id="7eafa-179">Hanying Feng,</span><span class="sxs-lookup"><span data-stu-id="7eafa-179">Feng, Hanying</span></span>  
  
 <span data-ttu-id="7eafa-180">Terry Adams,</span><span class="sxs-lookup"><span data-stu-id="7eafa-180">Adams, Terry</span></span>  
  
 <span data-ttu-id="7eafa-181">연도: 대학 1 학년</span><span class="sxs-lookup"><span data-stu-id="7eafa-181">Year: Freshman</span></span>  
  
 <span data-ttu-id="7eafa-182">Mortensen, Sven</span><span class="sxs-lookup"><span data-stu-id="7eafa-182">Mortensen, Sven</span></span>  
  
 <span data-ttu-id="7eafa-183">Garcia을 경우</span><span class="sxs-lookup"><span data-stu-id="7eafa-183">Garcia, Cesar</span></span>  
  
 <span data-ttu-id="7eafa-184">다음 코드에 표시 된 변형 클래스 년을 정렬 한 다음 성을 기준으로 각 연도 내에서 학습자를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-184">The variation shown in the following code orders the class years, and then orders the students within each year by last name.</span></span>  
  
 [!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]  
  
 <span data-ttu-id="7eafa-185">에 대 한 자세한 내용은 `Group By`, 참조 [그룹 By 절](../../../../visual-basic/language-reference/queries/group-by-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7eafa-185">For more information about `Group By`, see [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eafa-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7eafa-186">See Also</span></span>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [<span data-ttu-id="7eafa-187">Visual Basic에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="7eafa-187">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="7eafa-188">쿼리</span><span class="sxs-lookup"><span data-stu-id="7eafa-188">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="7eafa-189">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7eafa-189">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="7eafa-190">LINQ</span><span class="sxs-lookup"><span data-stu-id="7eafa-190">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
