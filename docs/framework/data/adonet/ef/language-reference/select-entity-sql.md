---
title: SELECT(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a33bd0d-ded1-41e7-ba3c-305502755e3b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3123d76d5999d9f7201e1415d6bc4313f9767098
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="select-entity-sql"></a><span data-ttu-id="38b43-102">SELECT(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="38b43-102">SELECT (Entity SQL)</span></span>
<span data-ttu-id="38b43-103">쿼리 결과로 반환될 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-103">Specifies the elements returned by a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38b43-104">구문</span><span class="sxs-lookup"><span data-stu-id="38b43-104">Syntax</span></span>  
  
```  
SELECT [ ALL | DISTINCT ] [ topSubclause ] aliasedExpr   
      [{ , aliasedExpr }] FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause ]  
or  
SELECT VALUE [ ALL | DISTINCT ] [ topSubclause ] expr FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause  
```  
  
## <a name="arguments"></a><span data-ttu-id="38b43-105">인수</span><span class="sxs-lookup"><span data-stu-id="38b43-105">Arguments</span></span>  
 <span data-ttu-id="38b43-106">ALL</span><span class="sxs-lookup"><span data-stu-id="38b43-106">ALL</span></span>  
 <span data-ttu-id="38b43-107">결과 집합에 중복 항목이 나타날 수 있음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-107">Specifies that duplicates can appear in the result set.</span></span> <span data-ttu-id="38b43-108">ALL이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-108">ALL is the default.</span></span>  
  
 <span data-ttu-id="38b43-109">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="38b43-109">DISTINCT</span></span>  
 <span data-ttu-id="38b43-110">결과 집합에 고유한 결과만 나타날 수 있음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-110">Specifies that only unique results can appear in the result set.</span></span>  
  
 <span data-ttu-id="38b43-111">VALUE</span><span class="sxs-lookup"><span data-stu-id="38b43-111">VALUE</span></span>  
 <span data-ttu-id="38b43-112">항목 하나만 지정할 수 있으며 행 래퍼를 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-112">Allows only one item to be specified, and does not add on a row wrapper.</span></span>  
  
 `topSubclause`  
 <span data-ttu-id="38b43-113">쿼리에서 첫 번째로 반환되는 결과의 개수를 나타내며 `top (``expr``)`형태로 표시되는 모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-113">Any valid expression that indicates the number of first results to return from the query, of the form `top (``expr``)`.</span></span>  
  
 <span data-ttu-id="38b43-114">LIMIT 매개 변수는 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) 연산자 또한 결과 집합의 처음 n 개의 항목을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-114">The LIMIT parameter of the [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) operator also lets you select the first n items in the result set.</span></span>  
  
 `aliasedExpr`  
 <span data-ttu-id="38b43-115">다음 형태의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-115">An expression of the form:</span></span>  
  
 <span data-ttu-id="38b43-116">`expr`으로 `identifier` &#124;`expr`</span><span class="sxs-lookup"><span data-stu-id="38b43-116">`expr` as `identifier` &#124; `expr`</span></span>  
  
 `expr`  
 <span data-ttu-id="38b43-117">리터럴 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-117">A literal or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38b43-118">설명</span><span class="sxs-lookup"><span data-stu-id="38b43-118">Remarks</span></span>  
 <span data-ttu-id="38b43-119">SELECT 절에 평가 됩니다는 [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), 및 [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md) 절이 계산 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-119">The SELECT clause is evaluated after the [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), and [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md) clauses have been evaluated.</span></span> <span data-ttu-id="38b43-120">SELECT 절은 현재 범위 내에 있는 항목만 참조할 수 있으며, FROM 절 또는 외부 범위에서 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-120">The SELECT clause can only refer to items currently in-scope (from the FROM clause, or from outer scopes).</span></span> <span data-ttu-id="38b43-121">GROUP BY 절이 지정된 경우, SELECT 절에서는 GROUP BY 키의 별칭만 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-121">If a GROUP BY clause has been specified, the SELECT clause is only allowed to reference the aliases for the GROUP BY keys.</span></span> <span data-ttu-id="38b43-122">FROM 절 항목에 대한 참조는 집계 함수에서만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-122">Referring to the FROM clause items is only permitted in aggregate functions.</span></span>  
  
 <span data-ttu-id="38b43-123">SELECT 키워드 다음에 나오는 하나 이상의 쿼리 식을 나열한 목록은 선택 목록이라고 하고 공식적으로는 프로젝션이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-123">The list of one or more query expressions following the SELECT keyword is known as the select list, or more formally as the projection.</span></span> <span data-ttu-id="38b43-124">가장 일반적인 형태의 프로젝션은 단일 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-124">The most general form of projection is a single query expression.</span></span> <span data-ttu-id="38b43-125">`member1` 컬렉션에서 `collection1`멤버를 선택하면 다음 예제와 같이 `member1` 의 각 개체에 대한 모든 `collection1`값이 포함된 새로운 컬렉션이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-125">If you select a member `member1` from a collection `collection1`, you will produce a new collection of all the `member1` values for each object in `collection1`, as illustrated in the following example.</span></span>  
  
```  
SELECT collection1.member1 FROM collection1  
```  
  
 <span data-ttu-id="38b43-126">예를 들어 `customers` 가 `Customer` 형식의 `Name` 속성이 포함된 `string`형식의 컬렉션인 경우, `Name` 에서 `customers` 을 선택하면 다음 예제와 같이 문자열 컬렉션이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-126">For example, if `customers` is a collection of type `Customer` that has a property `Name` that is of type `string`, selecting `Name` from `customers` will yield a collection of strings, as illustrated in the following example.</span></span>  
  
```  
SELECT customers.Name FROM customers AS c  
```  
  
 <span data-ttu-id="38b43-127">FULL, INNER, LEFT, OUTER, ON, RIGHT 등의 JOIN 구문을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-127">It is also possible to use JOIN syntax (FULL, INNER, LEFT, OUTER, ON, and RIGHT).</span></span> <span data-ttu-id="38b43-128">ON은 내부 조인에 필수적이지만 크로스 조인에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-128">ON is required for inner joins and is nto allowed for cross joins.</span></span>  
  
## <a name="row-and-value-select-clauses"></a><span data-ttu-id="38b43-129">ROW 및 VALUE SELECT 절</span><span class="sxs-lookup"><span data-stu-id="38b43-129">Row and Value Select Clauses</span></span>  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="38b43-130"> 에서는 두 가지 변형의 SELECT 절을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-130"> supports two variants of the SELECT clause.</span></span> <span data-ttu-id="38b43-131">하나는 행 선택으로서, SELECT 키워드로 식별됩니다. 이 절은 프로젝션될 값을 하나 이상 지정하는 데 사용됩니다. 반환되는 값 주위에 행 래퍼가 암시적으로 추가되므로, 쿼리 식의 결과는 항상 행의 multiset입니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-131">The first variant, row select, is identified by the SELECT keyword, and can be used to specify one or more values that should be projected out. Because a row wrapper is implicitly added around the values returned, the result of the query expression is always a multiset of rows.</span></span>  
  
 <span data-ttu-id="38b43-132">행의 각 쿼리 식에서는 별칭이 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-132">Each query expression in a row select must specify an alias.</span></span> <span data-ttu-id="38b43-133">별칭이 지정되지 않은 경우[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 에서는 별칭 생성 규칙에 따라 별칭을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-133">If no alias is specified,[!INCLUDE[esql](../../../../../../includes/esql-md.md)] attempts to generate an alias by using the alias generation rules.</span></span>  
  
 <span data-ttu-id="38b43-134">SELECT 절의 다른 변형은 값 선택으로서, SELECT VALUE 키워드로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-134">The other variant of the SELECT clause, value select, is identified by the SELECT VALUE keyword.</span></span> <span data-ttu-id="38b43-135">이 절은 항목 하나만 지정할 수 있으며 행 래퍼를 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-135">It allows only one value to be specified, and does not add a row wrapper.</span></span>  
  
 <span data-ttu-id="38b43-136">행 선택은 다음 예제에서 보여 주는 것처럼 항상 VALUE SELECT로 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-136">A row select is always expressible in terms of VALUE SELECT, as illustrated in the following example.</span></span>  
  
```  
SELECT 1 AS a, "abc" AS b FROM C  
SELECT VALUE ROW(1 AS a, "abc" AS b) FROM C   
```  
  
## <a name="all-and-distinct-modifiers"></a><span data-ttu-id="38b43-137">ALL 및 DISTINCT 한정자</span><span class="sxs-lookup"><span data-stu-id="38b43-137">All and Distinct Modifiers</span></span>  
 <span data-ttu-id="38b43-138">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 에서 지원되는 두 가지 SELECT 절 모두 ALL 한정자나 DISTINCT 한정자의 사양을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-138">Both variants of SELECT in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allow the specification of an ALL or DISTINCT modifier.</span></span> <span data-ttu-id="38b43-139">DISTINCT 한정자가 지정된 경우, 쿼리 식에서 생성되는 컬렉션에서 중복 항목이 제거됩니다(SELECT 절까지 포함).</span><span class="sxs-lookup"><span data-stu-id="38b43-139">If the DISTINCT modifier is specified, duplicates are eliminated from the collection produced by the query expression (up to and including the SELECT clause).</span></span> <span data-ttu-id="38b43-140">ALL 한정자가 지정된 경우에는 중복 항목이 제거되지 않으며, ALL이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-140">If the ALL modifier is specified, no duplicate elimination is performed; ALL is the default.</span></span>  
  
## <a name="differences-from-transact-sql"></a><span data-ttu-id="38b43-141">Transact-SQL과의 차이점</span><span class="sxs-lookup"><span data-stu-id="38b43-141">Differences from Transact-SQL</span></span>  
 <span data-ttu-id="38b43-142">Transact-SQL과는 달리, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 에서는 SELECT 절에 * 인수의 사용을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-142">Unlike Transact-SQL, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not support use of the * argument in the SELECT clause.</span></span>  <span data-ttu-id="38b43-143">대신 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 에서는 다음 예제에서 보여 주는 것처럼 쿼리를 통해 FROM 절에서 컬렉션 별칭을 참조하여 전체 레코드를 프로젝션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-143">Instead, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] allows queries to project out entire records by referencing the collection aliases from the FROM clause, as illustrated in the following example.</span></span>  
  
```  
SELECT * FROM T1, T2  
```  
  
 <span data-ttu-id="38b43-144">위의 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 쿼리 식은 다음과 같이 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-144">The previous [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] query expression is expressed in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in the following way.</span></span>  
  
```  
SELECT a1, a2 FROM T1 AS a1, T2 AS a2  
```  
  
## <a name="example"></a><span data-ttu-id="38b43-145">예제</span><span class="sxs-lookup"><span data-stu-id="38b43-145">Example</span></span>  
 <span data-ttu-id="38b43-146">다음 Entity SQL 쿼리에서는 SELECT 연산자를 사용하여 쿼리에서 반환될 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-146">The following Entity SQL query uses the SELECT operator to specify the elements to be returned by a query.</span></span> <span data-ttu-id="38b43-147">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-147">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="38b43-148">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="38b43-148">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="38b43-149">[How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-149">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="38b43-150">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="38b43-150">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less)]  
  
## <a name="see-also"></a><span data-ttu-id="38b43-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38b43-151">See Also</span></span>  
 [<span data-ttu-id="38b43-152">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="38b43-152">Query Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
 [<span data-ttu-id="38b43-153">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="38b43-153">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="38b43-154">맨 위로</span><span class="sxs-lookup"><span data-stu-id="38b43-154">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
