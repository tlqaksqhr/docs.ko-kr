---
title: LINQ(Language-Integrated Query)(C#)
ms.custom: 
ms.date: 02/02/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 19dd1782-905b-4a9d-a3e9-618453037fa2
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0a721bba36eb1ed4ae94b99e25a1dcce33faef6e
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2018
---
# <a name="language-integrated-query-linq"></a><span data-ttu-id="c6841-102">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="c6841-102">Language Integrated Query (LINQ)</span></span>

<span data-ttu-id="c6841-103">LINQ(Language-Integrated Query)는 C# 언어에 직접 쿼리 기능을 통합하는 방식을 기반으로 하는 기술 집합 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-103">Language-Integrated Query (LINQ) is the name for a set of technologies based on the integration of query capabilities directly into the C# language.</span></span> <span data-ttu-id="c6841-104">일반적으로 데이터에 대한 쿼리는 컴파일 시간의 형식 검사나 IntelliSense 지원 없이 간단한 문자열로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="c6841-105">또한 SQL 데이터베이스, XML 문서, 다양한 웹 서비스 등의 각 데이터 소스 형식에 대해 서로 다른 쿼리 언어를 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="c6841-106">LINQ를 사용할 경우 쿼리는 클래스, 메서드, 이벤트와 같은 고급 언어 구문이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-106">With LINQ, a query is a first-class language construct, just like classes, methods, events.</span></span>

<span data-ttu-id="c6841-107">쿼리를 작성하는 개발자의 경우 LINQ에서 가장 눈에 잘 띄는 "언어 통합" 부분은 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-107">For a developer who writes queries, the most visible "language-integrated" part of LINQ is the query expression.</span></span> <span data-ttu-id="c6841-108">쿼리 식은 선언적 *쿼리 구문*으로 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-108">Query expressions are written in a declarative *query syntax*.</span></span> <span data-ttu-id="c6841-109">쿼리 구문을 사용하면 최소한의 코드로 데이터 소스에 대해 필터링, 정렬 및 그룹화 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-109">By using query syntax, you can perform filtering, ordering, and grouping operations on data sources with a minimum of code.</span></span> <span data-ttu-id="c6841-110">동일한 기본 쿼리 식 패턴을 사용하여 SQL 데이터베이스, ADO .NET 데이터 집합, XML 문서 및 스트림, .NET 컬렉션에서 데이터를 쿼리하고 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-110">You use the same basic query expression patterns to query and transform data in SQL databases, ADO .NET Datasets, XML documents and streams, and .NET collections.</span></span>

<span data-ttu-id="c6841-111">다음 예제에서는 전체 쿼리 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-111">The following example shows the complete query operation.</span></span> <span data-ttu-id="c6841-112">전체 작업에는 데이터 소스 만들기, 쿼리 식 정의 및 `foreach` 문의 쿼리 실행이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-112">The complete operation includes creating a data source, defining the query expression, and executing the query in a `foreach` statement.</span></span>

[!code-csharp[csProgGuideLINQ#11](../../../../../samples/snippets/csharp/concepts/linq/index_1.cs)]

## <a name="query-expression-overview"></a><span data-ttu-id="c6841-113">쿼리 식 개요</span><span class="sxs-lookup"><span data-stu-id="c6841-113">Query expression overview</span></span>

-   <span data-ttu-id="c6841-114">쿼리 식은 LINQ 사용 데이터 소스에서 데이터를 쿼리하고 변환하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-114">Query expressions can be used to query and to transform data from any LINQ-enabled data source.</span></span> <span data-ttu-id="c6841-115">예를 들어 단일 쿼리로 SQL 데이터베이스에서 데이터를 검색하고 XML 스트림을 출력으로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-115">For example, a single query can retrieve data from a SQL database, and produce an XML stream as output.</span></span>  
  
-   <span data-ttu-id="c6841-116">쿼리 식은 익숙한 C# 언어 구문을 많이 사용하기 때문에 쉽게 마스터할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-116">Query expressions are easy to master because they use many familiar C# language constructs.</span></span>  
  
-   <span data-ttu-id="c6841-117">대부분의 경우 컴파일러가 형식을 유추할 수 있기 때문에 명시적으로 형식을 제공할 필요는 없지만 쿼리 식의 변수는 모두 강력한 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-117">The variables in a query expression are all strongly typed, although in many cases you do not have to provide the type explicitly because the compiler can infer it.</span></span> <span data-ttu-id="c6841-118">자세한 내용은 [LINQ 쿼리 작업의 형식 관계](type-relationships-in-linq-query-operations.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6841-118">For more information, see [Type relationships in LINQ query operations](type-relationships-in-linq-query-operations.md).</span></span>  
  
-   <span data-ttu-id="c6841-119">쿼리는 쿼리 변수를 반복할 때까지(예: `foreach` 문) 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-119">A query is not executed until you iterate over the query variable, for example, in a `foreach` statement.</span></span> <span data-ttu-id="c6841-120">자세한 내용은 [LINQ 쿼리 소개](introduction-to-linq-queries.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6841-120">For more information, see [Introduction to LINQ queries](introduction-to-linq-queries.md).</span></span>  
  
-   <span data-ttu-id="c6841-121">컴파일 타임에 쿼리 식은 C# 사양에 명시된 규칙에 따라 표준 쿼리 연산자 메서드 호출으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-121">At compile time, query expressions are converted to Standard Query Operator method calls according to the rules set forth in the C# specification.</span></span> <span data-ttu-id="c6841-122">쿼리 구문을 사용하여 표현할 수 있는 모든 쿼리는 메서드 구문으로도 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-122">Any query that can be expressed by using query syntax can also be expressed by using method syntax.</span></span> <span data-ttu-id="c6841-123">그러나 대부분의 경우 쿼리 구문이 더 읽기 쉽고 간결합니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-123">However, in most cases query syntax is more readable and concise.</span></span> <span data-ttu-id="c6841-124">자세한 내용은 [C# 언어 사양](../../../language-reference/language-specification/index.md) 및 [표준 쿼리 연산자 개요](standard-query-operators-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6841-124">For more information, see [C# language specification](../../../language-reference/language-specification/index.md) and [Standard query operators overview](standard-query-operators-overview.md).</span></span>  
  
-   <span data-ttu-id="c6841-125">일반적으로 LINQ 쿼리를 작성하는 경우 가능하면 쿼리 구문을 사용하고 필요한 경우 메서드 구문을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-125">As a rule when you write LINQ queries, we recommend that you use query syntax whenever possible and method syntax whenever necessary.</span></span> <span data-ttu-id="c6841-126">두 개의 다른 폼 간에 의미 체계 또는 성능상의 차이는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-126">There is no semantic or performance difference between the two different forms.</span></span> <span data-ttu-id="c6841-127">쿼리 식이 메서드 구문으로 작성된 동급의 식보다 읽기 쉬운 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-127">Query expressions are often more readable than equivalent expressions written in method syntax.</span></span>  
  
-   <span data-ttu-id="c6841-128"><xref:System.Linq.Enumerable.Count%2A> 또는 <xref:System.Linq.Enumerable.Max%2A>와 같은 일부 쿼리 작업은 해당하는 쿼리 식 절이 없으므로 메서드 호출로 표현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-128">Some query operations, such as <xref:System.Linq.Enumerable.Count%2A> or <xref:System.Linq.Enumerable.Max%2A>, have no equivalent query expression clause and must therefore be expressed as a method call.</span></span> <span data-ttu-id="c6841-129">메서드 구문을 다양한 방법으로 쿼리 구문에 조합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-129">Method syntax can be combined with query syntax in various ways.</span></span> <span data-ttu-id="c6841-130">자세한 내용은 [쿼리 구문과 메서드 구문 비교](query-syntax-and-method-syntax-in-linq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6841-130">For more information, see [Query syntax and method syntax in LINQ](query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
-   <span data-ttu-id="c6841-131">쿼리 식은 쿼리가 적용되는 형식에 따라 식 트리 또는 대리자로 컴파일될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-131">Query expressions can be compiled to expression trees or to delegates, depending on the type that the query is applied to.</span></span> <span data-ttu-id="c6841-132"><xref:System.Collections.Generic.IEnumerable%601> 쿼리는 대리자로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-132"><xref:System.Collections.Generic.IEnumerable%601> queries are compiled to delegates.</span></span> <span data-ttu-id="c6841-133"><xref:System.Linq.IQueryable> 및 <xref:System.Linq.IQueryable%601> 쿼리는 식 트리로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6841-133"><xref:System.Linq.IQueryable> and <xref:System.Linq.IQueryable%601> queries are compiled to expression trees.</span></span> <span data-ttu-id="c6841-134">자세한 내용은 [식 트리](../../../expression-trees.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6841-134">For more information, see [Expression trees](../../../expression-trees.md).</span></span>  

## <a name="next-steps"></a><span data-ttu-id="c6841-135">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c6841-135">Next steps</span></span>

<span data-ttu-id="c6841-136">LINQ에 대한 자세한 내용을 알아보려면 [쿼리 식 기본 사항](../../../linq/query-expression-basics.md)에서 몇 가지 기본 개념을 익힌 후 관심 있는 LINQ 기술에 대한 설명서를 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="c6841-136">To learn more details about LINQ, start by becoming familiar with some basic concepts in [Query expression basics](../../../linq/query-expression-basics.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>   
-   <span data-ttu-id="c6841-137">XML 문서: [LINQ to XML](linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="c6841-137">XML documents: [LINQ to XML](linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="c6841-138">ADO.NET Entity Framework: [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md)</span><span class="sxs-lookup"><span data-stu-id="c6841-138">ADO.NET Entity Framework: [LINQ to entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md)</span></span>  
  
-   <span data-ttu-id="c6841-139">.NET 컬렉션, 파일, 문자열 등: [LINQ to Objects](linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="c6841-139">.NET collections, files, strings and so on: [LINQ to objects](linq-to-objects.md)</span></span>

<span data-ttu-id="c6841-140">LINQ를 보다 깊이 있게 이해하려면 [C#의 LINQ](../../../linq/linq-in-csharp.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6841-140">To gain a deeper understanding of LINQ in general, see [LINQ in C#](../../../linq/linq-in-csharp.md).</span></span>

<span data-ttu-id="c6841-141">C#에서 LINQ를 사용하려면 자습서 [LINQ 작업](../../../tutorials/working-with-linq.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6841-141">To start working with LINQ in C#, see the tutorial [Working with LINQ](../../../tutorials/working-with-linq.md).</span></span>



