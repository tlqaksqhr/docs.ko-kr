---
title: "명령 트리에서 SQL 생성 - 최선의 방법"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71ef6a24-4c4f-4254-af3a-ffc0d855b0a8
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 06d2711d9dac203645c127fa86581a9888db3cb1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="generating-sql-from-command-trees---best-practices"></a><span data-ttu-id="77f87-102">명령 트리에서 SQL 생성 - 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="77f87-102">Generating SQL from Command Trees - Best Practices</span></span>
<span data-ttu-id="77f87-103">출력 쿼리 명령 트리는 SQL로 표현 가능한 쿼리를 유사하게 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-103">Output query command trees closely model queries expressible in SQL.</span></span> <span data-ttu-id="77f87-104">그러나 출력 명령 트리에서 SQL을 생성할 때 공급자 작성기에 대한 특정한 공통적 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-104">However, there are certain common challenges for provider writers when generating SQL from an output command tree.</span></span> <span data-ttu-id="77f87-105">이 항목에서는 이러한 문제에 대해 설명하며,</span><span class="sxs-lookup"><span data-stu-id="77f87-105">This topic discusses these challenges.</span></span> <span data-ttu-id="77f87-106">그 다음 항목에서는 동일한 공급자가 이러한 문제를 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-106">In the next topic, the sample provider shows how to address these challenges.</span></span>  
  
## <a name="group-dbexpression-nodes-in-a-sql-select-statement"></a><span data-ttu-id="77f87-107">SQL SELECT 문에서 DbExpression 노드 그룹화</span><span class="sxs-lookup"><span data-stu-id="77f87-107">Group DbExpression Nodes in a SQL SELECT Statement</span></span>  
 <span data-ttu-id="77f87-108">일반적인 SQL 문에는 다음과 같은 모양의 중첩 구조가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-108">A typical SQL statement has a nested structure of the following shape:</span></span>  
  
```  
SELECT …  
FROM …  
WHERE …  
GROUP BY …  
ORDER BY …  
```  
  
 <span data-ttu-id="77f87-109">하나 이상의 절이 비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-109">One or more clauses may be empty.</span></span>  <span data-ttu-id="77f87-110">중첩된 SELECT 문은 어떤 줄에서든 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-110">A nested SELECT statement could occur in any of the lines.</span></span>  
  
 <span data-ttu-id="77f87-111">쿼리 명령 트리를 SQL SELECT 문으로 변환하는 경우 관계형 연산자마다 하위 쿼리가 하나씩 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-111">A possible translation of a query command tree into a SQL SELECT statement would produce one subquery for every relational operator.</span></span> <span data-ttu-id="77f87-112">그러나 이 경우 읽기 어려운 불필요한 중첩 하위 쿼리가 생성되며,</span><span class="sxs-lookup"><span data-stu-id="77f87-112">However, that would lead to unnecessary nested subqueries that would be difficult to read.</span></span>  <span data-ttu-id="77f87-113">일부 데이터 저장소에서는 쿼리 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-113">On some data stores, the query may perform poorly.</span></span>  
  
 <span data-ttu-id="77f87-114">예를 들어, 다음과 같은 쿼리 명령 트리를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-114">As an example, consider the following query command tree</span></span>  
  
```  
Project (  
a.x,  
   a = Filter(  
      b.y = 5,   
      b = Scan("TableA")  
   )  
)  
```  
  
 <span data-ttu-id="77f87-115">비효율적인 변환에서는 다음을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-115">An inefficient translation would produce:</span></span>  
  
```  
SELECT a.x  
FROM (   SELECT *  
         FROM TableA as b  
         WHERE b.y = 5) as a  
```  
  
 <span data-ttu-id="77f87-116">모든 관계식 노드가 새로운 SQL SELECT 문이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-116">Note that every relational expression node becomes a new SQL SELECT statement.</span></span>  
  
 <span data-ttu-id="77f87-117">따라서 정확성을 유지하면서 가능한 한 많은 식 노드를 단일 SQL SELECT 문에 집계해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-117">Therefore, it is important to aggregate as many expression nodes as possible into a single SQL SELECT statement while preserving correctness.</span></span>  
  
 <span data-ttu-id="77f87-118">위의 예제에 대한 이러한 집계의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-118">The result of such aggregation for the example presented above would be:</span></span>  
  
```  
SELECT b.x   
FROM TableA as b  
WHERE b.y = 5  
```  
  
## <a name="flatten-joins-in-a-sql-select-statement"></a><span data-ttu-id="77f87-119">SQL SELECT 문에서 조인 평면화</span><span class="sxs-lookup"><span data-stu-id="77f87-119">Flatten Joins in a SQL SELECT Statement</span></span>  
 <span data-ttu-id="77f87-120">여러 노드를 단일 SQL SELECT 문에 집계하는 예로 여러 조인 식을 단일 SQL SELECT 문에 집계하는 경우를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-120">One case of aggregating multiple nodes into a single SQL SELECT statement is aggregating multiple join expressions into a single SQL SELECT statement.</span></span> <span data-ttu-id="77f87-121">DbJoinExpression은 두 입력 간의 단일 조인을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-121">DbJoinExpression represents a single join between two inputs.</span></span> <span data-ttu-id="77f87-122">그러나 단일 SQL SELECT 문의 일부로 둘 이상의 조인을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-122">However, as part of a single SQL SELECT statement, more than one join can be specified.</span></span> <span data-ttu-id="77f87-123">이 경우 지정된 순서대로 조인이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-123">In that case the joins are performed in the order specified.</span></span>  
  
 <span data-ttu-id="77f87-124">왼쪽 편 조인(다른 조인의 왼쪽 자식으로 나타나는 조인)은 단일 SQL SELECT 문으로 보다 쉽게 평면화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-124">Left spine joins, (joins that appear as a left child of another join) can be more easily flattened into a single SQL SELECT statement.</span></span> <span data-ttu-id="77f87-125">예를 들어, 다음과 같은 쿼리 명령 트리를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-125">For example, consider the following query command tree:</span></span>  
  
```  
InnerJoin(  
   a = LeftOuterJoin(  
   b = Extent("TableA")  
   c = Extent("TableB")  
   ON b.y = c.x ),  
   d = Extent("TableC")   
   ON a.b.y = d.z  
)  
```  
  
 <span data-ttu-id="77f87-126">이 트리는 다음으로 올바르게 변환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-126">This can be correctly translated into:</span></span>  
  
```  
SELECT *  
FROM TableA as b  
LEFT OUTER JOIN TableB as c ON b.y = c.x  
INNER JOIN TableC as d ON b.y = d.z  
```  
  
 <span data-ttu-id="77f87-127">그러나 왼쪽 편 조인이 아닌 조인은 쉽게 평면화할 수 없으므로 평면화하려고 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-127">However, non-left spine joins cannot easily be flattened, and you should not try to flatten them.</span></span> <span data-ttu-id="77f87-128">다음 쿼리 명령 트리의 조인을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-128">For example, the joins in the following query command tree:</span></span>  
  
```  
InnerJoin(  
   a = Extent("TableA")   
   b = LeftOuterJoin(  
   c = Extent("TableB")  
   d = Extent("TableC")  
   ON c.y = d.x),  
   ON a.z = b.c.y  
)  
```  
  
 <span data-ttu-id="77f87-129">이 조인은 하위 쿼리가 포함된 SQL SELECT 문으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-129">Would be translated to a SQL SELECT statement with a sub-query.</span></span>  
  
```  
SELECT *  
FROM TableA as a  
INNER JOIN (SELECT *   
   FROM TableB as c   
   LEFT OUTER JOIN TableC as d  
   ON c.y = d.x) as b  
ON b.y = d.z  
```  
  
## <a name="input-alias-redirecting"></a><span data-ttu-id="77f87-130">입력 별칭 리디렉션</span><span class="sxs-lookup"><span data-stu-id="77f87-130">Input Alias Redirecting</span></span>  
 <span data-ttu-id="77f87-131">입력 별칭 리디렉션을 설명하기 위해 DbFilterExpression, DbProjectExpression, DbCrossJoinExpression, DbJoinExpression, DbSortExpression, DbGroupByExpression, DbApplyExpression 및 DbSkipExpression과 같은 관계식의 구조를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-131">To explain input alias redirecting, consider the structure of the relational expressions, such as DbFilterExpression, DbProjectExpression, DbCrossJoinExpression, DbJoinExpression, DbSortExpression, DbGroupByExpression, DbApplyExpression, and DbSkipExpression.</span></span>  
  
 <span data-ttu-id="77f87-132">이러한 각 형식에는 입력 컬렉션을 설명하는 하나 이상의 입력 속성이 있으며, 각 입력에 해당하는 바인딩 변수는 컬렉션 순회 중에 해당 입력의 각 요소를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-132">Each of these types has one or more Input properties that describe an input collection, and a binding variable corresponding to each input is used to represent each element of that input during a collection traversal.</span></span> <span data-ttu-id="77f87-133">바인딩 변수는 DbFilterExpression의 Predicate 속성이나 DbProjectExpression의 Projection 속성 등에서 입력 요소를 참조할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-133">The binding variable is used when referring to the input element, for example in the Predicate property of a DbFilterExpression or the Projection property of a DbProjectExpression.</span></span>  
  
 <span data-ttu-id="77f87-134">더 많은 관계식 노드를 단일 SQL SELECT 문에 집계하고 관계식의 일부(예: DbProjectExpression의 Projection 속성 일부)인 식을 계산하는 경우 여러 식 바인딩이 단일 익스텐트로 리디렉션되어야 하므로 사용하는 바인딩 변수는 입력의 별칭과 동일하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-134">When aggregating more relational expression nodes into a single SQL SELECT statement, and evaluating an expression that is part of a relational expression (for example part of the Projection property of a DbProjectExpression) the binding variable that it uses may not be the same as the alias of the input, as multiple expression bindings would have to be redirected to a single extent.</span></span>  <span data-ttu-id="77f87-135">이 문제를 별칭 이름 바꾸기라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-135">This problem is called alias renaming.</span></span>  
  
 <span data-ttu-id="77f87-136">이 항목의 첫 번째 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-136">Consider the first example in this topic.</span></span> <span data-ttu-id="77f87-137">기본 변환을 수행하고 Projection a.x (DbPropertyExpression(a, x))를 변환하는 경우 입력의 별칭을 바인딩 변수와 일치하도록 "a"로 지정했으므로 `a.x`로 변환하는 것이 올바릅니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-137">If doing the naïve translation and translating the Projection a.x (DbPropertyExpression(a, x)), it is correct to translate it into `a.x` because we have aliased the input as "a" to match the binding variable.</span></span>  <span data-ttu-id="77f87-138">그러나 두 노드를 단일 SQL SELECT 문에 집계하는 경우에는 입력의 별칭이 "b"로 지정되었으므로 동일한 DbPropertyExpression을 `b.x`로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-138">However, when aggregating both the nodes into a single SQL SELECT statement, you need to translate the same DbPropertyExpression into `b.x`, as the input has been aliased with "b".</span></span>  
  
## <a name="join-alias-flattening"></a><span data-ttu-id="77f87-139">조인 별칭 평면화</span><span class="sxs-lookup"><span data-stu-id="77f87-139">Join Alias Flattening</span></span>  
 <span data-ttu-id="77f87-140">출력 명령 트리의 다른 모든 관계식과 달리 DbJoinExpression은 각각 입력 중 하나에 해당하는 두 열로 구성된 행인 결과 형식을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-140">Unlike any other relational expression in an output command tree, the DbJoinExpression outputs a result type that is a row consisting of two columns, each of which corresponds to one of the inputs.</span></span> <span data-ttu-id="77f87-141">DbPropertyExpresssion이 조인에서 제공되는 스칼라 속성에 액세스하기 위해 작성되는 경우 또 다른 DbPropertyExpresssion 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-141">When a DbPropertyExpresssion is built to access a scalar property originating from a join, it is over another DbPropertyExpresssion.</span></span>  
  
 <span data-ttu-id="77f87-142">예로 예제 2의 "a.b.y"와 예제 3의 "b.c.y"를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-142">Examples include "a.b.y" in example 2 and "b.c.y" in example 3.</span></span> <span data-ttu-id="77f87-143">그러나 해당 SQL 문에서 이들은 "b.y"로 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-143">However in the corresponding SQL statements these are referred as "b.y".</span></span> <span data-ttu-id="77f87-144">이렇게 별칭이 다시 지정되는 것을 조인 별칭 평면화라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-144">This re-aliasing is called join alias flattening.</span></span>  
  
## <a name="column-name-and-extent-alias-renaming"></a><span data-ttu-id="77f87-145">열 이름 및 익스텐트 별칭 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="77f87-145">Column Name and Extent Alias Renaming</span></span>  
 <span data-ttu-id="77f87-146">조인이 있는 SQL SELECT 쿼리가 프로젝션을 사용하여 완료되어야 하는 경우 입력에서 참여하는 열을 모두 열거하면 둘 이상의 입력에 동일한 열 이름이 있을 수 있으므로 이름 충돌이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-146">If a SQL SELECT query that has a join has to be completed with a projection, when enumerating all the participating columns from the inputs, a name collision may occur, as more than one input may have the same column name.</span></span> <span data-ttu-id="77f87-147">충돌을 방지하려면 열에 서로 다른 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-147">Use a different name for the column to avoid the collision.</span></span>  
  
 <span data-ttu-id="77f87-148">또한 조인을 평면화할 때 참여하는 테이블(또는 하위 쿼리)에 충돌하는 별칭이 있을 수 있습니다. 이 경우 충돌하는 별칭의 이름을 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-148">Also, when flattening joins, participating tables (or subqueries) may have colliding aliases in which case these need to be renamed.</span></span>  
  
## <a name="avoid-select-"></a><span data-ttu-id="77f87-149">SELECT * 사용 금지</span><span class="sxs-lookup"><span data-stu-id="77f87-149">Avoid SELECT *</span></span>  
 <span data-ttu-id="77f87-150">기본 테이블에서 선택하기 위해 `SELECT *`를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="77f87-150">Do not use `SELECT *` to select from base tables.</span></span> <span data-ttu-id="77f87-151">저장소 모델에는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 응용 프로그램 데이터베이스 테이블에 있는 열의 하위 집합에만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-151">The storage model in an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] application may only include a subset of the columns that are in the database table.</span></span> <span data-ttu-id="77f87-152">이 경우 `SELECT *`는 잘못된 결과를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-152">In this case, `SELECT *` may produce an incorrect result.</span></span> <span data-ttu-id="77f87-153">대신, 참여하는 식의 결과 형식에서 열 이름을 사용하여 참여하는 모든 열을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-153">Instead, you should specify all participating columns by using the column names from the result type of the participating expressions.</span></span>  
  
## <a name="reuse-of-expressions"></a><span data-ttu-id="77f87-154">식의 재사용</span><span class="sxs-lookup"><span data-stu-id="77f87-154">Reuse of Expressions</span></span>  
 <span data-ttu-id="77f87-155">식은 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]에서 전달되는 쿼리 명령 트리에서 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-155">Expressions may be reused in the query command tree passed by the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="77f87-156">각 식이 쿼리 명령 트리에서 한 번만 나타난다고 가정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="77f87-156">Do not assume that each expression appears only once in the query command tree.</span></span>  
  
## <a name="mapping-primitive-types"></a><span data-ttu-id="77f87-157">기본 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="77f87-157">Mapping Primitive Types</span></span>  
 <span data-ttu-id="77f87-158">개념적(EDM) 형식을 공급자 형식에 매핑하는 경우 가능한 모든 값이 들어가도록 가장 넓은 형식(Int32)에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f87-158">When mapping conceptual (EDM) types to provider types, you should map to the widest type (Int32) so that all possible values fit.</span></span> <span data-ttu-id="77f87-159">또한 BLOB 형식과 같이 많은 작업에 사용할 수 없는 형식(예: `ntext`의 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)])에 매핑하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="77f87-159">Also, avoid mapping to types that cannot be used for many operations, like BLOB types (for example, `ntext` in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77f87-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77f87-160">See Also</span></span>  
 [<span data-ttu-id="77f87-161">SQL 생성</span><span class="sxs-lookup"><span data-stu-id="77f87-161">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
