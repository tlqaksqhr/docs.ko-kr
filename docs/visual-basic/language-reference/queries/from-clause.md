---
title: From 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: 1f113444efae83de7d299db330593937c7800bb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604720"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="a44ad-102">From 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a44ad-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="a44ad-103">하나 이상의 범위 변수와 쿼리할 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a44ad-104">구문</span><span class="sxs-lookup"><span data-stu-id="a44ad-104">Syntax</span></span>  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="a44ad-105">요소</span><span class="sxs-lookup"><span data-stu-id="a44ad-105">Parts</span></span>  
  
|<span data-ttu-id="a44ad-106">용어</span><span class="sxs-lookup"><span data-stu-id="a44ad-106">Term</span></span>|<span data-ttu-id="a44ad-107">정의</span><span class="sxs-lookup"><span data-stu-id="a44ad-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="a44ad-108">필수.</span><span class="sxs-lookup"><span data-stu-id="a44ad-108">Required.</span></span> <span data-ttu-id="a44ad-109">A *범위 변수* 컬렉션의 요소를 반복 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="a44ad-110">범위 변수는의 각 멤버를 참조 하는 데 사용 되는 `collection` 쿼리 반복으로 `collection`합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="a44ad-111">열거 가능한 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="a44ad-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-112">Optional.</span></span> <span data-ttu-id="a44ad-113">`element`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-113">The type of `element`.</span></span> <span data-ttu-id="a44ad-114">없는 경우 `type` 지정 된 유형의 `element` 에서 유추 `collection`합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="a44ad-115">필수.</span><span class="sxs-lookup"><span data-stu-id="a44ad-115">Required.</span></span> <span data-ttu-id="a44ad-116">쿼리할 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="a44ad-117">열거 가능한 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a44ad-118">설명</span><span class="sxs-lookup"><span data-stu-id="a44ad-118">Remarks</span></span>  
 <span data-ttu-id="a44ad-119">`From` 절을 사용 하는 쿼리 및 소스 컬렉션에서 요소를 참조 하는 데 사용 되는 변수에 대 한 원본 데이터를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="a44ad-120">이러한 변수 라고 *범위 변수*합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-120">These variables are called *range variables*.</span></span> <span data-ttu-id="a44ad-121">`From` 절이 필요한 경우를 제외 하 고 쿼리에 대 한는 `Aggregate` 반환 에서만 결과 집계 하는 쿼리를 식별 하려면 절을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="a44ad-122">자세한 내용은 참조 [Aggregate 절](../../../visual-basic/language-reference/queries/aggregate-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="a44ad-123">여러 개 지정할 수 `From` 여러 조인할 컬렉션을 식별 하는 쿼리 절.</span><span class="sxs-lookup"><span data-stu-id="a44ad-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="a44ad-124">여러 컬렉션을 지정 하는 반복할 독립적으로 수도 있고 관련 되어 조인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="a44ad-125">사용 하 여 컬렉션을 암시적으로 조인할 수는 `Select` 절, 또는 사용 하 여 명시적으로 `Join` 또는 `Group Join` 절.</span><span class="sxs-lookup"><span data-stu-id="a44ad-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="a44ad-126">지정할 수 있습니다 여러 범위 변수와 컬렉션 단일에서 `From` 절, 각 관련 된 다른 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="a44ad-127">다음 코드 예제에서는 두 구문 옵션에 대 한 표시는 `From` 절.</span><span class="sxs-lookup"><span data-stu-id="a44ad-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 <span data-ttu-id="a44ad-128">`From` 절 정의의 범위에 비슷한 쿼리의 범위는 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="a44ad-129">따라서 각 `element` 범위 변수는 쿼리의 범위에 고유한 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="a44ad-130">여러 개 지정할 수 있으므로 `From` 후속 쿼리의 절 `From` 절에서 범위 변수를 참조할 수는 `From` 또는 절은 이전에 범위 변수를 참조할 수 `From` 절.</span><span class="sxs-lookup"><span data-stu-id="a44ad-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="a44ad-131">예를 들어 다음 예제에서는 중첩 된 `From` 두 번째 절에서 컬렉션의 첫 번째 절의 범위 변수 속성은 기준 절.</span><span class="sxs-lookup"><span data-stu-id="a44ad-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 <span data-ttu-id="a44ad-132">각 `From` 절 쿼리를 구체화 하는 추가 쿼리 절의 조합이 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="a44ad-133">다음과 같은 방법으로 쿼리를 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-133">You can refine the query in the following ways:</span></span>  
  
-   <span data-ttu-id="a44ad-134">여러 컬렉션을 사용 하 여 암시적으로 결합는 `From` 및 `Select` 절을 사용 하 여 명시적으로 또는 `Join` 또는 `Group Join` 절.</span><span class="sxs-lookup"><span data-stu-id="a44ad-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
-   <span data-ttu-id="a44ad-135">사용 하 여는 `Where` 절 쿼리 결과를 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-135">Use the `Where` clause to filter the query result.</span></span>  
  
-   <span data-ttu-id="a44ad-136">사용 하 여 결과 정렬 된 `Order By` 절.</span><span class="sxs-lookup"><span data-stu-id="a44ad-136">Sort the result by using the `Order By` clause.</span></span>  
  
-   <span data-ttu-id="a44ad-137">사용 하 여 유사한 결과 함께 그룹화 된 `Group By` 절.</span><span class="sxs-lookup"><span data-stu-id="a44ad-137">Group similar results together by using the `Group By` clause.</span></span>  
  
-   <span data-ttu-id="a44ad-138">사용 하 여는 `Aggregate` 평가할 전체 쿼리 결과 대 한 집계 함수를 식별 하는 절.</span><span class="sxs-lookup"><span data-stu-id="a44ad-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
-   <span data-ttu-id="a44ad-139">사용 하 여는 `Let` 절 값을 갖는 컬렉션 대신 식에 의해 결정 됩니다는 반복 변수를 도입 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
-   <span data-ttu-id="a44ad-140">사용 하 여는 `Distinct` 절 중복 되는 쿼리 결과 무시 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
-   <span data-ttu-id="a44ad-141">사용 하 여 반환할 결과의 일부를 식별 된 `Skip`, `Take`, `Skip While`, 및 `Take While` 절.</span><span class="sxs-lookup"><span data-stu-id="a44ad-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a44ad-142">예제</span><span class="sxs-lookup"><span data-stu-id="a44ad-142">Example</span></span>  
 <span data-ttu-id="a44ad-143">다음 쿼리는 사용 되는 식은 `From` 범위 변수를 선언 하는 절 `cust` 각 `Customer` 개체는 `customers` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="a44ad-144">`Where` 절 범위 변수를 사용 하 여 지정된 된 지역에서 고객에 게 출력을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="a44ad-145">`For Each` 루프 쿼리 결과에서 각 고객의 회사 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a44ad-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a44ad-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a44ad-146">See Also</span></span>  
 [<span data-ttu-id="a44ad-147">쿼리</span><span class="sxs-lookup"><span data-stu-id="a44ad-147">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="a44ad-148">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="a44ad-148">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="a44ad-149">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="a44ad-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="a44ad-150">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="a44ad-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="a44ad-151">Select 절</span><span class="sxs-lookup"><span data-stu-id="a44ad-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="a44ad-152">Where 절</span><span class="sxs-lookup"><span data-stu-id="a44ad-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="a44ad-153">Aggregate 절</span><span class="sxs-lookup"><span data-stu-id="a44ad-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="a44ad-154">Distinct 절</span><span class="sxs-lookup"><span data-stu-id="a44ad-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 [<span data-ttu-id="a44ad-155">Join 절</span><span class="sxs-lookup"><span data-stu-id="a44ad-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)  
 [<span data-ttu-id="a44ad-156">Group Join 절</span><span class="sxs-lookup"><span data-stu-id="a44ad-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="a44ad-157">Order By 절</span><span class="sxs-lookup"><span data-stu-id="a44ad-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="a44ad-158">Let 절</span><span class="sxs-lookup"><span data-stu-id="a44ad-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 [<span data-ttu-id="a44ad-159">Skip 절</span><span class="sxs-lookup"><span data-stu-id="a44ad-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [<span data-ttu-id="a44ad-160">Take 절</span><span class="sxs-lookup"><span data-stu-id="a44ad-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 [<span data-ttu-id="a44ad-161">Skip While 절</span><span class="sxs-lookup"><span data-stu-id="a44ad-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="a44ad-162">Take While 절</span><span class="sxs-lookup"><span data-stu-id="a44ad-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
