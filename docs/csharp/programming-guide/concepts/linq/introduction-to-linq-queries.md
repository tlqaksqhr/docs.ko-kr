---
title: "LINQ 쿼리 소개(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- deferred execution [LINQ]
- LINQ, queries
- LINQ, deferred execution
- queries [LINQ], about LINQ queries
ms.assetid: 37895c02-268c-41d5-be39-f7d936fa88a8
caps.latest.revision: 47
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8427a0f439516cbba0b38db25f48b0083a337b1b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="introduction-to-linq-queries-c"></a><span data-ttu-id="f04bd-102">LINQ 쿼리 소개(C#)</span><span class="sxs-lookup"><span data-stu-id="f04bd-102">Introduction to LINQ Queries (C#)</span></span>
<span data-ttu-id="f04bd-103">*쿼리*는 데이터 소스에서 데이터를 검색하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-103">A *query* is an expression that retrieves data from a data source.</span></span> <span data-ttu-id="f04bd-104">쿼리는 일반적으로 특수화된 쿼리 언어로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-104">Queries are usually expressed in a specialized query language.</span></span> <span data-ttu-id="f04bd-105">관계형 데이터베이스에는 SQL이 사용되고 XML에는 XQuery가 사용되는 것처럼 시간에 따라 다양한 형식의 데이터 소스에 대해 서로 다른 언어가 개발되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-105">Different languages have been developed over time for the various types of data sources, for example SQL for relational databases and XQuery for XML.</span></span> <span data-ttu-id="f04bd-106">따라서 개발자는 지원해야 하는 데이터 소스의 형식이나 데이터 형식에 따라 새로운 쿼리 언어를 배워야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-106">Therefore, developers have had to learn a new query language for each type of data source or data format that they must support.</span></span> [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]<span data-ttu-id="f04bd-107">는 다양한 데이터 소스 및 형식에 사용할 수 있는 일관된 모델을 제공함으로써 이러한 상황을 간단하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-107"> simplifies this situation by offering a consistent model for working with data across various kinds of data sources and formats.</span></span> <span data-ttu-id="f04bd-108">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리에서는 항상 개체를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-108">In a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, you are always working with objects.</span></span> <span data-ttu-id="f04bd-109">XML 문서, SQL 데이터베이스, [!INCLUDE[vstecado](~/includes/vstecado-md.md)] 데이터 집합, .NET 컬렉션 및 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자를 사용할 수 있는 다른 모든 형식에서 데이터를 쿼리하고 변환하는 데 동일한 기본 코딩 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-109">You use the same basic coding patterns to query and transform data in XML documents, SQL databases, [!INCLUDE[vstecado](~/includes/vstecado-md.md)] Datasets, .NET collections, and any other format for which a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider is available.</span></span>  
  
## <a name="three-parts-of-a-query-operation"></a><span data-ttu-id="f04bd-110">쿼리 작업의 세 부분</span><span class="sxs-lookup"><span data-stu-id="f04bd-110">Three Parts of a Query Operation</span></span>  
 <span data-ttu-id="f04bd-111">모든 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 작업은 다음과 같은 세 가지 고유한 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-111">All [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query operations consist of three distinct actions:</span></span>  
  
1.  <span data-ttu-id="f04bd-112">데이터 소스 가져오기.</span><span class="sxs-lookup"><span data-stu-id="f04bd-112">Obtain the data source.</span></span>  
  
2.  <span data-ttu-id="f04bd-113">쿼리 만들기.</span><span class="sxs-lookup"><span data-stu-id="f04bd-113">Create the query.</span></span>  
  
3.  <span data-ttu-id="f04bd-114">쿼리 실행.</span><span class="sxs-lookup"><span data-stu-id="f04bd-114">Execute the query.</span></span>  
  
 <span data-ttu-id="f04bd-115">다음 예제에서는 쿼리 작업의 세 부분이 소스 코드로 표현되는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-115">The following example shows how the three parts of a query operation are expressed in source code.</span></span> <span data-ttu-id="f04bd-116">예제에서는 편의상 정수 배열을 데이터 소스로 사용하지만 다른 데이터 소스에도 동일한 개념이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-116">The example uses an integer array as a data source for convenience; however, the same concepts apply to other data sources also.</span></span> <span data-ttu-id="f04bd-117">이 예제는 이 항목의 나머지 부분 전체에서 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-117">This example is referred to throughout the rest of this topic.</span></span>  
  
 <span data-ttu-id="f04bd-118">[!code-cs[CsLINQGettingStarted#1](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f04bd-118">[!code-cs[CsLINQGettingStarted#1](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_1.cs)]</span></span>  
  
 <span data-ttu-id="f04bd-119">다음 그림에서는 전체 쿼리 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-119">The following illustration shows the complete query operation.</span></span> <span data-ttu-id="f04bd-120">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]에서는 쿼리 실행이 쿼리 자체와 구분됩니다. 즉, 쿼리 변수를 만드는 것만으로 데이터가 검색되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-120">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] the execution of the query is distinct from the query itself; in other words you have not retrieved any data just by creating a query variable.</span></span>  
  
 <span data-ttu-id="f04bd-121">![완전한 LINQ 쿼리 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_query.png "LINQ_Query")</span><span class="sxs-lookup"><span data-stu-id="f04bd-121">![Complete LINQ Query Operation](../../../../csharp/programming-guide/concepts/linq/media/linq_query.png "LINQ_Query")</span></span>  
  
## <a name="the-data-source"></a><span data-ttu-id="f04bd-122">데이터 소스</span><span class="sxs-lookup"><span data-stu-id="f04bd-122">The Data Source</span></span>  
 <span data-ttu-id="f04bd-123">이전 예제에서는 데이터 소스가 배열이기 때문에 제네릭 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 암시적으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-123">In the previous example, because the data source is an array, it implicitly supports the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="f04bd-124">즉, [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]로 쿼리할 수 있다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-124">This fact means it can be queried with [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span></span> <span data-ttu-id="f04bd-125">쿼리가 `foreach` 문에서 실행되고, `foreach`는 <xref:System.Collections.IEnumerable> 또는 <xref:System.Collections.Generic.IEnumerable%601>이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-125">A query is executed in a `foreach` statement, and `foreach` requires <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="f04bd-126"><xref:System.Collections.Generic.IEnumerable%601> 또는 제네릭 <xref:System.Linq.IQueryable%601> 같은 파생된 인터페이스를 지원하는 형식을 *쿼리 가능 형식*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-126">Types that support <xref:System.Collections.Generic.IEnumerable%601> or a derived interface such as the generic <xref:System.Linq.IQueryable%601> are called *queryable types*.</span></span>  
  
 <span data-ttu-id="f04bd-127">쿼리 가능 형식은 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 데이터 소스로 사용하기 위해 수정하거나 특별하게 처리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-127">A queryable type requires no modification or special treatment to serve as a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] data source.</span></span> <span data-ttu-id="f04bd-128">소스 데이터가 쿼리 가능 형식으로 메모리에 나타나지 않을 경우 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자는 그렇게 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-128">If the source data is not already in memory as a queryable type, the [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider must represent it as such.</span></span> <span data-ttu-id="f04bd-129">예를 들어 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]는 XML 문서를 쿼리 가능 <xref:System.Xml.Linq.XElement> 형식으로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-129">For example, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] loads an XML document into a queryable <xref:System.Xml.Linq.XElement> type:</span></span>  
  
 <span data-ttu-id="f04bd-130">[!code-cs[CsLINQGettingStarted#2](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f04bd-130">[!code-cs[CsLINQGettingStarted#2](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_2.cs)]</span></span>  
  
 <span data-ttu-id="f04bd-131">먼저 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]을 사용하여 디자인 타임에 수동으로 또는 Visual Studio에서 [Visual Studio의 LINQ to SQL 도구](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)를 사용하여 개체 관계형 매핑을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-131">With [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], you first create an object-relational mapping at design time either manually or by using the [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) in Visual Studio.</span></span> <span data-ttu-id="f04bd-132">개체에 대해 쿼리를 작성하면 런타임에 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]에서 데이터베이스와의 통신을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-132">You write your queries against the objects, and at run-time [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] handles the communication with the database.</span></span> <span data-ttu-id="f04bd-133">다음 예에서 `Customers`는 데이터베이스의 특정 테이블을 나타내며, <xref:System.Linq.IQueryable%601> 쿼리 결과 형식은 <xref:System.Collections.Generic.IEnumerable%601>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-133">In the following example, `Customers` represents a specific table in the database, and the type of the query result, <xref:System.Linq.IQueryable%601>, derives from <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
```csharp  
Northwnd db = new Northwnd(@"c:\northwnd.mdf");  
  
// Query for customers in London.  
IQueryable<Customer> custQuery =  
    from cust in db.Customers  
    where cust.City == "London"  
    select cust;  
```  
  
 <span data-ttu-id="f04bd-134">특정 형식의 데이터 소스를 만드는 방법에 대한 자세한 내용은 다양한 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 공급자에 대한 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f04bd-134">For more information about how to create specific types of data sources, see the documentation for the various [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] providers.</span></span> <span data-ttu-id="f04bd-135">그러나 기본 규칙은 아주 간단합니다. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 데이터 소스는 제네릭 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스 또는 이 인터페이스에서 상속된 인터페이스를 지원하는 모든 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-135">However, the basic rule is very simple: a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] data source is any object that supports the generic <xref:System.Collections.Generic.IEnumerable%601> interface, or an interface that inherits from it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f04bd-136">제네릭이 아닌 <xref:System.Collections.IEnumerable> 인터페이스를 지원하는 <xref:System.Collections.ArrayList> 같은 형식은 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 데이터 소스로도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-136">Types such as <xref:System.Collections.ArrayList> that support the non-generic <xref:System.Collections.IEnumerable> interface can also be used as a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] data source.</span></span> <span data-ttu-id="f04bd-137">자세한 내용은 [방법: LINQ를 사용하여 ArrayList 쿼리(C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f04bd-137">For more information, see [How to: Query an ArrayList with LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md).</span></span>  
  
##  <span data-ttu-id="f04bd-138"><a name="query"></a> 쿼리</span><span class="sxs-lookup"><span data-stu-id="f04bd-138"><a name="query"></a> The Query</span></span>  
 <span data-ttu-id="f04bd-139">쿼리는 데이터 소스 또는 소스에서 검색할 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-139">The query specifies what information to retrieve from the data source or sources.</span></span> <span data-ttu-id="f04bd-140">필요한 경우 쿼리는 정보를 반환하기 전에 해당 정보를 정렬, 그룹화 및 구체화하는 방법도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-140">Optionally, a query also specifies how that information should be sorted, grouped, and shaped before it is returned.</span></span> <span data-ttu-id="f04bd-141">쿼리는 쿼리 변수에 저장되고 쿼리 식으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-141">A query is stored in a query variable and initialized with a query expression.</span></span> <span data-ttu-id="f04bd-142">쿼리를 쉽게 작성할 수 있도록 C#에서는 새로운 쿼리 구문이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-142">To make it easier to write queries, C# has introduced new query syntax.</span></span>  
  
 <span data-ttu-id="f04bd-143">이전 예제의 쿼리는 정수 배열에서 모든 짝수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-143">The query in the previous example returns all the even numbers from the integer array.</span></span> <span data-ttu-id="f04bd-144">쿼리 식에는 `from`, `where` 및 `select`의 세 가지 절이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-144">The query expression contains three clauses: `from`, `where` and `select`.</span></span> <span data-ttu-id="f04bd-145">SQL에 익숙한 경우 절의 순서가 SQL의 순서와 반대임을 알고 있을 것입니다. `from` 절은 데이터 소스를 지정하고 `where` 절은 필터를 적용하며 `select` 절은 반환되는 요소의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-145">(If you are familiar with SQL, you will have noticed that the ordering of the clauses is reversed from the order in SQL.) The `from` clause specifies the data source, the `where` clause applies the filter, and the `select` clause specifies the type of the returned elements.</span></span> <span data-ttu-id="f04bd-146">이러한 쿼리 절 및 다른 쿼리 절은 [LINQ 쿼리 식](../../../../csharp/programming-guide/linq-query-expressions/index.md) 섹션에서 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-146">These and the other query clauses are discussed in detail in the [LINQ Query Expressions](../../../../csharp/programming-guide/linq-query-expressions/index.md) section.</span></span> <span data-ttu-id="f04bd-147">여기에서 중요한 점은 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]에서 쿼리 변수 자체는 아무 작업도 수행하지 않고 데이터를 반환하지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-147">For now, the important point is that in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], the query variable itself takes no action and returns no data.</span></span> <span data-ttu-id="f04bd-148">나중에 쿼리가 실행될 때 결과를 생성하는 데 필요한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-148">It just stores the information that is required to produce the results when the query is executed at some later point.</span></span> <span data-ttu-id="f04bd-149">백그라운드에서 쿼리를 생성하는 방법에 대한 자세한 내용은 [표준 쿼리 연산자 개요(C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f04bd-149">For more information about how queries are constructed behind the scenes, see [Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f04bd-150">쿼리는 메서드 구문을 사용하여 표현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-150">Queries can also be expressed by using method syntax.</span></span> <span data-ttu-id="f04bd-151">자세한 내용은 [LINQ의 쿼리 구문 및 메서드 구문](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f04bd-151">For more information, see [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
## <a name="query-execution"></a><span data-ttu-id="f04bd-152">쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="f04bd-152">Query Execution</span></span>  
  
### <a name="deferred-execution"></a><span data-ttu-id="f04bd-153">지연된 실행</span><span class="sxs-lookup"><span data-stu-id="f04bd-153">Deferred Execution</span></span>  
 <span data-ttu-id="f04bd-154">앞에서 설명한 대로 쿼리 변수 자체는 쿼리 명령을 저장할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-154">As stated previously, the query variable itself only stores the query commands.</span></span> <span data-ttu-id="f04bd-155">실제 쿼리 실행은 `foreach` 문에서 쿼리 변수가 반복될 때까지 지연됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-155">The actual execution of the query is deferred until you iterate over the query variable in a `foreach` statement.</span></span> <span data-ttu-id="f04bd-156">이 개념을 *지연된 실행*이라고 하며 다음 예제에서 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-156">This concept is referred to as *deferred execution* and is demonstrated in the following example:</span></span>  
  
 <span data-ttu-id="f04bd-157">[!code-cs[csLinqGettingStarted#4](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f04bd-157">[!code-cs[csLinqGettingStarted#4](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_3.cs)]</span></span>  
  
 <span data-ttu-id="f04bd-158">`foreach` 문은 쿼리 결과가 검색되는 위치이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-158">The `foreach` statement is also where the query results are retrieved.</span></span> <span data-ttu-id="f04bd-159">예를 들어 이전 쿼리에서 반복 변수 `num`은 반환된 시퀀스에서 각 값을 한 번에 하나씩 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-159">For example, in the previous query, the iteration variable `num` holds each value (one at a time) in the returned sequence.</span></span>  
  
 <span data-ttu-id="f04bd-160">쿼리 변수 자체는 쿼리 결과를 저장하지 않으므로 원하는 만큼 자주 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-160">Because the query variable itself never holds the query results, you can execute it as often as you like.</span></span> <span data-ttu-id="f04bd-161">예를 들어 별도의 응용 프로그램에서 지속적으로 업데이트되는 데이터베이스가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-161">For example, you may have a database that is being updated continually by a separate application.</span></span> <span data-ttu-id="f04bd-162">이 응용 프로그램에서 최근 데이터를 검색하는 쿼리를 작성하고 이를 일정 간격을 두고 반복적으로 실행하여 매번 다른 결과를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-162">In your application, you could create one query that retrieves the latest data, and you could execute it repeatedly at some interval to retrieve different results every time.</span></span>  
  
### <a name="forcing-immediate-execution"></a><span data-ttu-id="f04bd-163">즉시 실행 강제 적용</span><span class="sxs-lookup"><span data-stu-id="f04bd-163">Forcing Immediate Execution</span></span>  
 <span data-ttu-id="f04bd-164">소스 요소 범위에 대해 집계 함수를 수행하는 쿼리는 먼저 해당 요소를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-164">Queries that perform aggregation functions over a range of source elements must first iterate over those elements.</span></span> <span data-ttu-id="f04bd-165">이러한 쿼리의 예로 `Count`, `Max`, `Average` 및 `First`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-165">Examples of such queries are `Count`, `Max`, `Average`, and `First`.</span></span> <span data-ttu-id="f04bd-166">이러한 쿼리는 쿼리 자체에서 결과를 반환하려면 `foreach`를 사용해야 하기 때문에 명시적 `foreach` 문 없이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-166">These execute without an explicit `foreach` statement because the query itself must use `foreach` in order to return a result.</span></span> <span data-ttu-id="f04bd-167">또한 이러한 유형의 쿼리는 `IEnumerable` 컬렉션이 아니라 단일 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-167">Note also that these types of queries return a single value, not an `IEnumerable` collection.</span></span> <span data-ttu-id="f04bd-168">다음 쿼리는 소스 배열에서 짝수의 개수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-168">The following query returns a count of the even numbers in the source array:</span></span>  
  
 <span data-ttu-id="f04bd-169">[!code-cs[csLinqGettingStarted#5](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="f04bd-169">[!code-cs[csLinqGettingStarted#5](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_4.cs)]</span></span>  
  
 <span data-ttu-id="f04bd-170">모든 쿼리를 즉시 실행하고 그 결과를 캐시하기 위해 <xref:System.Linq.Enumerable.ToList%2A> 또는 <xref:System.Linq.Enumerable.ToArray%2A> 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-170">To force immediate execution of any query and cache its results, you can call the <xref:System.Linq.Enumerable.ToList%2A> or <xref:System.Linq.Enumerable.ToArray%2A> methods.</span></span>  
  
 <span data-ttu-id="f04bd-171">[!code-cs[csLinqGettingStarted#6](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="f04bd-171">[!code-cs[csLinqGettingStarted#6](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/introduction-to-linq-queries_5.cs)]</span></span>  
  
 <span data-ttu-id="f04bd-172">또한 `foreach` 루프를 쿼리 식 바로 다음에 배치하여 강제로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-172">You can also force execution by putting the `foreach` loop immediately after the query expression.</span></span> <span data-ttu-id="f04bd-173">그러나 `ToList` 또는 `ToArray`를 호출하여 단일 컬렉션 개체에서 모든 데이터를 캐시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04bd-173">However, by calling `ToList` or `ToArray` you also cache all the data in a single collection object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f04bd-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f04bd-174">See Also</span></span>  
 <span data-ttu-id="f04bd-175">[C#에서 LINQ 시작](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="f04bd-175">[Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
 <span data-ttu-id="f04bd-176">[연습: C#에서 쿼리 작성](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span><span class="sxs-lookup"><span data-stu-id="f04bd-176">[Walkthrough: Writing Queries in C#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span></span>  
 <span data-ttu-id="f04bd-177">[연습: C#에서 쿼리 작성](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span><span class="sxs-lookup"><span data-stu-id="f04bd-177">[Walkthrough: Writing Queries in C#](../../../../csharp/programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span></span>  
 <span data-ttu-id="f04bd-178">[LINQ 쿼리 식](../../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="f04bd-178">[LINQ Query Expressions](../../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 <span data-ttu-id="f04bd-179">[foreach, in](../../../../csharp/language-reference/keywords/foreach-in.md) </span><span class="sxs-lookup"><span data-stu-id="f04bd-179">[foreach, in](../../../../csharp/language-reference/keywords/foreach-in.md) </span></span>  
 [<span data-ttu-id="f04bd-180">쿼리 키워드(LINQ)</span><span class="sxs-lookup"><span data-stu-id="f04bd-180">Query Keywords (LINQ)</span></span>](../../../../csharp/language-reference/keywords/query-keywords.md)

