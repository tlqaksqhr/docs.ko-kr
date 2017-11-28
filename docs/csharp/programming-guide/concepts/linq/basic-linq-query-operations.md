---
title: "기본 LINQ 쿼리 작업(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- orderby clause [LINQ in C#]
- ordering data [LINQ in C#]
- selecting data [LINQ in C#]
- queries [LINQ in C#], basic operations
- grouping data [LINQ in C#]
- data sources [LINQ in C#]
- sorting data [LINQ in C#]
- projections [LINQ in C#]
- filtering data [LINQ in C#]
- joining data [LINQ in C#]
- select clause [LINQ in C#]
- LINQ [C#], basic query operations
- join clause [LINQ in C#]
- group clause [LINQ in C#]
ms.assetid: a7ea3421-1cf4-4df7-832a-aa22fe6379e9
caps.latest.revision: "39"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c7a258ae8d85425abb6d1474d2cb01b02f6deb2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="basic-linq-query-operations-c"></a><span data-ttu-id="78c18-102">기본 LINQ 쿼리 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="78c18-102">Basic LINQ Query Operations (C#)</span></span>
<span data-ttu-id="78c18-103">이 항목에서는 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식 및 쿼리에서 수행하는 일부 일반적인 작업을 간단히 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-103">This topic gives a brief introduction to [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions and some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="78c18-104">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78c18-104">More detailed information is in the following topics:</span></span>  
  
 [<span data-ttu-id="78c18-105">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="78c18-105">LINQ Query Expressions</span></span>](../../../../csharp/programming-guide/linq-query-expressions/index.md)  
  
 [<span data-ttu-id="78c18-106">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="78c18-106">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
  
 [<span data-ttu-id="78c18-107">연습: C#에서 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="78c18-107">Walkthrough: Writing Queries in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)  
  
> [!NOTE]
>  <span data-ttu-id="78c18-108">SQL 또는 XQuery와 같은 쿼리 언어를 이미 잘 알고 있으면 이 항목의 대부분을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-108">If you already are familiar with a query language such as SQL or XQuery, you can skip most of this topic.</span></span> <span data-ttu-id="78c18-109">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식에서 절의 순서를 알아보려면 "`from` 절"을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="78c18-109">Read about the "`from` clause" in the next section to learn about the order of clauses in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span>  
  
## <a name="obtaining-a-data-source"></a><span data-ttu-id="78c18-110">데이터 소스 가져오기</span><span class="sxs-lookup"><span data-stu-id="78c18-110">Obtaining a Data Source</span></span>  
 <span data-ttu-id="78c18-111">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리에서 첫 번째 단계는 데이터 소스를 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-111">In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, the first step is to specify the data source.</span></span> <span data-ttu-id="78c18-112">대부분의 프로그래밍 언어에서처럼 C#에서 변수는 선언된 후 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-112">In C# as in most programming languages a variable must be declared before it can be used.</span></span> <span data-ttu-id="78c18-113">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리에서는 데이터 소스(`customers`) 및 *범위 변수*(`cust`)를 소개하기 위해 `from` 절이 먼저 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-113">In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, the `from` clause comes first in order to introduce the data source (`customers`) and the *range variable* (`cust`).</span></span>  
  
 [!code-csharp[csLINQGettingStarted#23](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_1.cs)]  
  
 <span data-ttu-id="78c18-114">쿼리 식에서는 실제 반복이 발생하지 않는다는 점을 제외하고 범위 변수는 `foreach` 루프의 반복 변수와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-114">The range variable is like the iteration variable in a `foreach` loop except that no actual iteration occurs in a query expression.</span></span> <span data-ttu-id="78c18-115">쿼리가 실행될 때 범위 변수는 `customers`에서 각 연속 요소에 대한 참조로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-115">When the query is executed, the range variable will serve as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="78c18-116">컴파일러에서 `cust` 형식을 유추할 수 있으므로 명시적으로 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-116">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="78c18-117">추가 범위 변수는 `let` 절에 의해 소개될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-117">Additional range variables can be introduced by a `let` clause.</span></span> <span data-ttu-id="78c18-118">자세한 내용은 [let 절](../../../../csharp/language-reference/keywords/let-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78c18-118">For more information, see [let clause](../../../../csharp/language-reference/keywords/let-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78c18-119"><xref:System.Collections.ArrayList>와 같은 제네릭이 아닌 데이터 소스의 경우 범위 변수를 명시적으로 형식화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-119">For non-generic data sources such as <xref:System.Collections.ArrayList>, the range variable must be explicitly typed.</span></span> <span data-ttu-id="78c18-120">자세한 내용은 [방법: LINQ를 사용하여 ArrayList 쿼리(C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md) 및 [from 절](../../../../csharp/language-reference/keywords/from-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78c18-120">For more information, see [How to: Query an ArrayList with LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md) and [from clause](../../../../csharp/language-reference/keywords/from-clause.md).</span></span>  
  
## <a name="filtering"></a><span data-ttu-id="78c18-121">필터링</span><span class="sxs-lookup"><span data-stu-id="78c18-121">Filtering</span></span>  
 <span data-ttu-id="78c18-122">대부분의 일반적인 쿼리 작업에서는 부울 식 형태로 필터를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-122">Probably the most common query operation is to apply a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="78c18-123">필터를 사용하면 쿼리에서는 식이 true인 요소만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-123">The filter causes the query to return only those elements for which the expression is true.</span></span> <span data-ttu-id="78c18-124">결과는 `where` 절에 따라 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-124">The result is produced by using the `where` clause.</span></span> <span data-ttu-id="78c18-125">적용되는 필터는 소스 시퀀스에서 제외할 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-125">The filter in effect specifies which elements to exclude from the source sequence.</span></span> <span data-ttu-id="78c18-126">다음 예제에서는 London에 주소가 있는 `customers`만 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-126">In the following example, only those `customers` who have an address in London are returned.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#24](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_2.cs)]  
  
 <span data-ttu-id="78c18-127">친숙한 C# 논리 `AND` 및 `OR` 연산자를 사용하여 `where` 절에서 필요한 만큼 필터 식을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-127">You can use the familiar C# logical `AND` and `OR` operators to apply as many filter expressions as necessary in the `where` clause.</span></span> <span data-ttu-id="78c18-128">예를 들어 "London"에 있고(`AND`) 이름이 "Devon"인 고객만 반환하려면 다음 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-128">For example, to return only customers from "London" `AND` whose name is "Devon" you would write the following code:</span></span>  
  
 [!code-csharp[csLINQGettingStarted#25](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_3.cs)]  
  
 <span data-ttu-id="78c18-129">London 또는 Paris에 있는 고객을 반환하려면 다음 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-129">To return customers from London or Paris, you would write the following code:</span></span>  
  
 [!code-csharp[csLINQGettingStarted#26](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_4.cs)]  
  
 <span data-ttu-id="78c18-130">자세한 내용은 [where 절](../../../../csharp/language-reference/keywords/where-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78c18-130">For more information, see [where clause](../../../../csharp/language-reference/keywords/where-clause.md).</span></span>  
  
## <a name="ordering"></a><span data-ttu-id="78c18-131">순서 지정</span><span class="sxs-lookup"><span data-stu-id="78c18-131">Ordering</span></span>  
 <span data-ttu-id="78c18-132">보통 반환된 데이터를 정렬하는 것이 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-132">Often it is convenient to sort the returned data.</span></span> <span data-ttu-id="78c18-133">`orderby` 절을 사용하면 반환된 시퀀스의 요소가 정렬되는 형식의 기본 비교자에 따라 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-133">The `orderby` clause will cause the elements in the returned sequence to be sorted according to the default comparer for the type being sorted.</span></span> <span data-ttu-id="78c18-134">예를 들어 `Name` 속성에 따라 결과를 정렬하도록 다음 쿼리를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-134">For example, the following query can be extended to sort the results based on the `Name` property.</span></span> <span data-ttu-id="78c18-135">`Name`이 문자열이면 기본 비교자는 A에서 Z까지 사전순 정렬을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-135">Because `Name` is a string, the default comparer performs an alphabetical sort from A to Z.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#27](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_5.cs)]  
  
 <span data-ttu-id="78c18-136">결과를 역순으로 정렬하려면 `orderby…descending` 절을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-136">To order the results in reverse order, from Z to A, use the `orderby…descending` clause.</span></span>  
  
 <span data-ttu-id="78c18-137">자세한 내용은 [orderby 절](../../../../csharp/language-reference/keywords/orderby-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78c18-137">For more information, see [orderby clause](../../../../csharp/language-reference/keywords/orderby-clause.md).</span></span>  
  
## <a name="grouping"></a><span data-ttu-id="78c18-138">그룹화</span><span class="sxs-lookup"><span data-stu-id="78c18-138">Grouping</span></span>  
 <span data-ttu-id="78c18-139">`group` 절을 사용하면 지정한 키를 기준으로 결과를 그룹화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-139">The `group` clause enables you to group your results based on a key that you specify.</span></span> <span data-ttu-id="78c18-140">예를 들어 결과가 `City`별로 그룹화되어 London 또는 Paris의 모든 고객이 개별 그룹에 포함되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-140">For example you could specify that the results should be grouped by the `City` so that all customers from London or Paris are in individual groups.</span></span> <span data-ttu-id="78c18-141">이 경우 `cust.City`가 키입니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-141">In this case, `cust.City` is the key.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#28](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_6.cs)]  
  
 <span data-ttu-id="78c18-142">쿼리를 `group` 절로 종료하면 결과에 여러 목록으로 구성된 목록 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-142">When you end a query with a `group` clause, your results take the form of a list of lists.</span></span> <span data-ttu-id="78c18-143">목록의 각 요소는 `Key` 멤버 및 해당 키로 그룹화된 요소 목록이 포함된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-143">Each element in the list is an object that has a `Key` member and a list of elements that are grouped under that key.</span></span> <span data-ttu-id="78c18-144">그룹 시퀀스를 생성하는 쿼리를 반복할 경우 중첩된 `foreach` 루프를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-144">When you iterate over a query that produces a sequence of groups, you must use a nested `foreach` loop.</span></span> <span data-ttu-id="78c18-145">외부 루프는 각 그룹을 반복하고 내부 루프는 각 그룹의 멤버를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-145">The outer loop iterates over each group, and the inner loop iterates over each group's members.</span></span>  
  
 <span data-ttu-id="78c18-146">그룹 작업의 결과를 참조해야 할 경우 `into` 키워드를 사용하여 추가로 쿼리될 수 있는 식별자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-146">If you must refer to the results of a group operation, you can use the `into` keyword to create an identifier that can be queried further.</span></span> <span data-ttu-id="78c18-147">다음 쿼리는 세 명 이상의 고객이 포함된 그룹만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-147">The following query returns only those groups that contain more than two customers:</span></span>  
  
 [!code-csharp[csLINQGettingStarted#29](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_7.cs)]  
  
 <span data-ttu-id="78c18-148">자세한 내용은 [group 절](../../../../csharp/language-reference/keywords/group-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78c18-148">For more information, see [group clause](../../../../csharp/language-reference/keywords/group-clause.md).</span></span>  
  
## <a name="joining"></a><span data-ttu-id="78c18-149">조인</span><span class="sxs-lookup"><span data-stu-id="78c18-149">Joining</span></span>  
 <span data-ttu-id="78c18-150">조인 작업은 데이터 소스에서 명시적으로 모델링되지 않은 시퀀스 간 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-150">Join operations create associations between sequences that are not explicitly modeled in the data sources.</span></span> <span data-ttu-id="78c18-151">예를 들어 같은 위치를 가진 모든 고객 및 배포자를 찾는 조인을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-151">For example you can perform a join to find all the customers and distributors who have the same location.</span></span> <span data-ttu-id="78c18-152">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]에서 `join` 절은 항상 직접 데이터베이스 테이블이 아닌 개체 컬렉션에 대해 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-152">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] the `join` clause always works against object collections instead of database tables directly.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#36](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/basic-linq-query-operations_8.cs)]  
  
 <span data-ttu-id="78c18-153">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]의 외래 키는 개체 모델에서 항목 컬렉션을 포함하는 속성으로 표현되므로 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]에서는 SQL에서처럼 자주 `join`을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-153">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] you do not have to use `join` as often as you do in SQL because foreign keys in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] are represented in the object model as properties that hold a collection of items.</span></span> <span data-ttu-id="78c18-154">예를 들어 `Customer` 개체에는 `Order` 개체의 컬렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-154">For example, a `Customer` object contains a collection of `Order` objects.</span></span> <span data-ttu-id="78c18-155">조인을 수행하지 않고 점 표기법을 사용하여 주문에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-155">Rather than performing a join, you access the orders by using dot notation:</span></span>  
  
```  
from order in Customer.Orders...  
```  
  
 <span data-ttu-id="78c18-156">자세한 내용은 [join 절](../../../../csharp/language-reference/keywords/join-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78c18-156">For more information, see [join clause](../../../../csharp/language-reference/keywords/join-clause.md).</span></span>  
  
## <a name="selecting-projections"></a><span data-ttu-id="78c18-157">선택(프로젝션)</span><span class="sxs-lookup"><span data-stu-id="78c18-157">Selecting (Projections)</span></span>  
 <span data-ttu-id="78c18-158">`select` 절은 쿼리 결과를 생성하고 각 반환된 요소의 “모양" 또는 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-158">The `select` clause produces the results of the query and specifies the "shape" or type of each returned element.</span></span> <span data-ttu-id="78c18-159">예를 들어 결과가 계산 또는 새 개체 만들기에 따라 전체 `Customer` 개체, 하나의 멤버만, 멤버 하위 집합 또는 일부 완전히 다른 결과 형식으로 구성될지 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-159">For example, you can specify whether your results will consist of complete `Customer` objects, just one member, a subset of members, or some completely different result type based on a computation or new object creation.</span></span> <span data-ttu-id="78c18-160">`select` 절이 소스 요소의 복사본이 아닌 다른 항목을 생성하는 경우 이 작업을 *프로젝션*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-160">When the `select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span> <span data-ttu-id="78c18-161">프로젝션을 사용하여 데이터를 변환하는 것은 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식의 강력한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="78c18-161">The use of projections to transform data is a powerful capability of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="78c18-162">자세한 내용은 [LINQ를 통한 데이터 변환(C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md) 및 [select 절](../../../../csharp/language-reference/keywords/select-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78c18-162">For more information, see [Data Transformations with LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md) and [select clause](../../../../csharp/language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78c18-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78c18-163">See Also</span></span>  
 [<span data-ttu-id="78c18-164">C#에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="78c18-164">Getting Started with LINQ in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="78c18-165">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="78c18-165">LINQ Query Expressions</span></span>](../../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="78c18-166">연습: C#에서 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="78c18-166">Walkthrough: Writing Queries in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)  
 [<span data-ttu-id="78c18-167">쿼리 키워드(LINQ)</span><span class="sxs-lookup"><span data-stu-id="78c18-167">Query Keywords (LINQ)</span></span>](../../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="78c18-168">익명 형식</span><span class="sxs-lookup"><span data-stu-id="78c18-168">Anonymous Types</span></span>](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
