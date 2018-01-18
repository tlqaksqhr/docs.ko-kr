---
title: "null 비교"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9168051a87b1cd2c0cccaa54f1d688aca018b731
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="null-comparisons"></a><span data-ttu-id="6669a-102">null 비교</span><span class="sxs-lookup"><span data-stu-id="6669a-102">Null Comparisons</span></span>
<span data-ttu-id="6669a-103">데이터 소스의 `null` 값은 값을 알 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-103">A `null` value in the data source indicates that the value is unknown.</span></span> <span data-ttu-id="6669a-104">[!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리에서는 특정 계산이나 비교가 유효한 데이터 또는 Null이 아닌 데이터를 가진 행에서만 수행되도록 Null 값을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-104">In [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries, you can check for null values so that certain calculations or comparisons are only performed on rows that have valid, or non-null, data.</span></span> <span data-ttu-id="6669a-105">그러나 CLR Null 의미 체계는 데이터 소스의 Null 의미 체계와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-105">CLR null semantics, however, may differ from the null semantics of the data source.</span></span> <span data-ttu-id="6669a-106">대부분의 데이터베이스는 세 개의 값으로 구성된 논리 버전을 사용하여 Null 비교를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-106">Most databases use a version of three-valued logic to handle null comparisons.</span></span> <span data-ttu-id="6669a-107">즉, Null 값에 대한 비교는 `true` 또는 `false`가 되지 않고 `unknown`이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-107">That is, a comparison against a null value does not evaluate to `true` or `false`, it evaluates to `unknown`.</span></span> <span data-ttu-id="6669a-108">ANSI Null은 이렇게 구현되는 경우가 많지만 항상 그런 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-108">Often this is an implementation of ANSI nulls, but this is not always the case.</span></span>  
  
 <span data-ttu-id="6669a-109">기본적으로 SQL Server에서 Null은 Null과 같음 비교는 Null 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-109">By default in SQL Server, the null-equals-null comparison returns a null value.</span></span> <span data-ttu-id="6669a-110">다음 예제에서는 `ShipDate`가 Null인 행은 결과 집합에서 제외되고 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 문에서 0개 행을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-110">In the following example, the rows where `ShipDate` is null are excluded from the result set, and the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] statement would return 0 rows.</span></span>  
  
```  
-- Find order details and orders with no ship date.  
SELECT h.SalesOrderID  
FROM Sales.SalesOrderHeader h  
JOIN Sales.SalesOrderDetail o ON o.SalesOrderID = h.SalesOrderID  
WHERE h.ShipDate IS Null  
```  
  
 <span data-ttu-id="6669a-111">Null은 Null과 같음 비교에서 true를 반환하는 CLR Null 의미 체계와 이 동작은 전혀 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-111">This is very different from the CLR null semantics, where the null-equals-null comparison returns true.</span></span>  
  
 <span data-ttu-id="6669a-112">다음 LINQ 쿼리는 CLR로 표현되지만 데이터 소스에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-112">The following LINQ query is expressed in the CLR, but it is executed in the data source.</span></span> <span data-ttu-id="6669a-113">CLR 의미 체계가 데이터 소스에서 반영될 것이라는 보장이 없으므로 예상 동작을 결정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-113">Because there is no guarantee that CLR semantics will be honored at the data source, the expected behavior is indeterminate.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#joinonnull)]
 [!code-vb[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#joinonnull)]  
  
## <a name="key-selectors"></a><span data-ttu-id="6669a-114">키 선택기</span><span class="sxs-lookup"><span data-stu-id="6669a-114">Key Selectors</span></span>  
 <span data-ttu-id="6669a-115">A *키 선택기* 요소에서 키를 추출 하는 표준 쿼리 연산자에 사용 되는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-115">A *key selector* is a function used in the standard query operators to extract a key from an element.</span></span> <span data-ttu-id="6669a-116">키 선택기 함수에서 식을 상수와 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-116">In the key selector function, an expression can be compared with a constant.</span></span> <span data-ttu-id="6669a-117">식을 Null 상수와 비교하거나 두 개의 Null 상수를 비교하면 CLR Null 의미 체계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-117">CLR null semantics are exhibited if an expression is compared to a null constant or if two null constants are compared.</span></span> <span data-ttu-id="6669a-118">데이터 소스에서 Null 값을 가진 두 개의 열을 비교하면 저장소 Null 의미 체계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-118">Store null semantics are exhibited if two columns with null values in the data source are compared.</span></span> <span data-ttu-id="6669a-119">키 선택기는 <xref:System.Linq.Queryable.GroupBy%2A>과 같은 대부분의 그룹화 및 정렬 표준 쿼리 연산자에서 발견되며, 쿼리 결과를 정렬하거나 그룹화하는 기준 키를 선택하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-119">Key selectors are found in many of the grouping and ordering standard query operators, such as <xref:System.Linq.Queryable.GroupBy%2A>, and are used to select keys by which to order or group the query results.</span></span>  
  
## <a name="null-property-on-a-null-object"></a><span data-ttu-id="6669a-120">Null 개체의 Null 속성</span><span class="sxs-lookup"><span data-stu-id="6669a-120">Null Property on a Null Object</span></span>  
 <span data-ttu-id="6669a-121">[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]에서 Null 개체의 속성은 Null입니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-121">In the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)], the properties of a null object are null.</span></span> <span data-ttu-id="6669a-122">CLR에서 Null 개체의 속성을 참조하려고 하면 <xref:System.NullReferenceException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-122">When you attempt to reference a property of a null object in the CLR, you will receive a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="6669a-123">LINQ 쿼리에 Null 개체의 속성이 필요한 경우 일관성 없는 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-123">When a LINQ query involves a property of a null object, this can result in inconsistent behavior.</span></span>  
  
 <span data-ttu-id="6669a-124">예를 들어, 다음 쿼리에서 `NewProduct`로의 캐스팅은 명령 트리 계층에서 수행되며, 이로 인해 `Introduced` 속성이 Null이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-124">For example, in the following query, the cast to `NewProduct` is done in the command tree layer, which might result in the `Introduced` property being null.</span></span> <span data-ttu-id="6669a-125"><xref:System.DateTime> 비교가 true가 되도록 데이터베이스에서 Null 비교를 정의한 경우 해당 행이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-125">If the database defined null comparisons such that the <xref:System.DateTime> comparison evaluates to true, the row will be included.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## <a name="passing-null-collections-to-aggregate-functions"></a><span data-ttu-id="6669a-126">Null 컬렉션을 집계 함수에 전달</span><span class="sxs-lookup"><span data-stu-id="6669a-126">Passing Null Collections to Aggregate Functions</span></span>  
 <span data-ttu-id="6669a-127">[!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]지 원하는 컬렉션을 전달 하면 `IQueryable` 데이터베이스에서 집계 함수에 집계 작업이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-127">In [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)], when you pass a collection that supports `IQueryable` to an aggregate function, aggregate operations are performed at the database.</span></span> <span data-ttu-id="6669a-128">메모리에 수행된 된 쿼리의와 데이터베이스에서 수행 된 쿼리의 결과에 차이점이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-128">There might be differences in the results of a query that was performed in-memory and a query that was performed at the database.</span></span> <span data-ttu-id="6669a-129">메모리 내 쿼리의 경우와 일치 하지 않는 경우 쿼리가 0을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-129">With an in-memory query, if there are no matches, the query returns zero.</span></span> <span data-ttu-id="6669a-130">데이터베이스에서 동일한 쿼리가 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-130">At the database, the same query returns `null`.</span></span> <span data-ttu-id="6669a-131">경우는 `null` 값이 LINQ 집계 함수로 전달 되는, 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-131">If a `null` value is passed to a LINQ aggregate function, an exception will be thrown.</span></span> <span data-ttu-id="6669a-132">허용 가능한 하도록 `null` 유형과 null 허용 형식으로 쿼리 결과 수신 하는 형식의 속성 값을 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="6669a-132">To accept possible `null` values, cast the types and the properties of the types that receive query results to nullable types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6669a-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6669a-133">See Also</span></span>  
 [<span data-ttu-id="6669a-134">LINQ to Entities 쿼리의 식</span><span class="sxs-lookup"><span data-stu-id="6669a-134">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
