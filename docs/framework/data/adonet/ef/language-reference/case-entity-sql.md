---
title: CASE(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9afc5e3bbf8e6fe732aca9e65c8ba5bd5f620c85
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="case-entity-sql"></a><span data-ttu-id="c1bae-102">CASE(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c1bae-102">CASE (Entity SQL)</span></span>
<span data-ttu-id="c1bae-103">`Boolean` 식 집합을 계산하여 결과를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-103">Evaluates a set of `Boolean` expressions to determine the result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1bae-104">구문</span><span class="sxs-lookup"><span data-stu-id="c1bae-104">Syntax</span></span>  
  
```  
CASE  
     WHEN Boolean_expression THEN result_expression   
    [ ...n ]   
     [   
    ELSE else_result_expression   
     ]   
END  
```  
  
## <a name="arguments"></a><span data-ttu-id="c1bae-105">인수</span><span class="sxs-lookup"><span data-stu-id="c1bae-105">Arguments</span></span>  
 `n`  
 <span data-ttu-id="c1bae-106">여러 WHEN `Boolean_expression` THEN `result_expression` 절을 사용할 수 있음을 나타내는 자리 표시자입니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-106">Is a placeholder that indicates that multiple WHEN `Boolean_expression` THEN `result_expression` clauses can be used.</span></span>  
  
 <span data-ttu-id="c1bae-107">THEN `result_expression`</span><span class="sxs-lookup"><span data-stu-id="c1bae-107">THEN `result_expression`</span></span>  
 <span data-ttu-id="c1bae-108">`Boolean_expression` 이 `true`인 경우에 반환되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-108">Is the expression returned when `Boolean_expression` evaluates to `true`.</span></span> <span data-ttu-id="c1bae-109">`result expression` 은 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-109">`result expression` is any valid expression.</span></span>  
  
 <span data-ttu-id="c1bae-110">ELSE `else_result_expression`</span><span class="sxs-lookup"><span data-stu-id="c1bae-110">ELSE `else_result_expression`</span></span>  
 <span data-ttu-id="c1bae-111">`true`인 비교 연산이 없는 경우 반환되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-111">Is the expression returned if no comparison operation evaluates to `true`.</span></span> <span data-ttu-id="c1bae-112">이 인수가 생략되고 `true`인 비교 연산이 없는 경우 CASE는 null을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-112">If this argument is omitted and no comparison operation evaluates to `true`, CASE returns null.</span></span> <span data-ttu-id="c1bae-113">`else_result_expression` 은 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-113">`else_result_expression` is any valid expression.</span></span> <span data-ttu-id="c1bae-114">`else_result_expression` 과 `result_expression` 의 데이터 형식은 동일하거나 암시적으로 변환되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-114">The data types of `else_result_expression` and any `result_expression` must be the same or must be an implicit conversion.</span></span>  
  
 <span data-ttu-id="c1bae-115">WHEN `Boolean_expression`</span><span class="sxs-lookup"><span data-stu-id="c1bae-115">WHEN `Boolean_expression`</span></span>  
 <span data-ttu-id="c1bae-116">검색된 CASE 형식을 사용할 때 계산되는 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-116">Is the `Boolean` expression evaluated when the searched CASE format is used.</span></span> <span data-ttu-id="c1bae-117">`Boolean_expression` 은 유효한 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-117">`Boolean_expression` is any valid `Boolean` expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1bae-118">반환 값</span><span class="sxs-lookup"><span data-stu-id="c1bae-118">Return Value</span></span>  
 <span data-ttu-id="c1bae-119">`result_expression` 과 선택적 요소인 `else_result_expression`의 형식 집합에서 우선 순위가 가장 높은 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-119">Returns the highest precedence type from the set of types in the `result_expression` and the optional `else_result_expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1bae-120">설명</span><span class="sxs-lookup"><span data-stu-id="c1bae-120">Remarks</span></span>  
 <span data-ttu-id="c1bae-121">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] CASE 식은 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] CASE 식과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-121">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] case expression resembles the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] case expression.</span></span> <span data-ttu-id="c1bae-122">CASE 식을 사용하면 적절한 결과를 생성하는 식을 결정하는 일련의 조건 테스트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-122">You use the case expression to make a series of conditional tests to determine which expression will yield the appropriate result.</span></span> <span data-ttu-id="c1bae-123">이러한 CASE 식 형식은 하나 이상으로 구성된 일련의 `Boolean` 식에 적용되어 올바른 결과 식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-123">This form of the case expression applies to a series of one or more `Boolean` expressions to determine the correct resulting expression.</span></span>  
  
 <span data-ttu-id="c1bae-124">CASE 함수는 지정된 순서대로 각 WHEN 절에 대해 `Boolean_expression` 을 계산한 다음 `result_expression` 인 첫 번째 `Boolean_expression` 의 `true`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-124">The CASE function evaluates `Boolean_expression` for each WHEN clause in the order specified, and returns `result_expression` of the first `Boolean_expression` that evaluates to `true`.</span></span> <span data-ttu-id="c1bae-125">나머지 식은 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-125">The remaining expressions are not evaluated.</span></span> <span data-ttu-id="c1bae-126">`Boolean_expression` 인 `true`이 없으면 ELSE 절이 지정된 경우 데이터베이스 엔진에서 `else_result_expression` 을 반환하고 ELSE 절이 지정되지 않은 경우 null 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-126">If no `Boolean_expression` evaluates to `true`, the Database Engine returns the `else_result_expression` if an ELSE clause is specified, or a null value if no ELSE clause is specified.</span></span>  
  
 <span data-ttu-id="c1bae-127">CASE 문은 multiset을 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-127">A CASE statement cannot return a multiset.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1bae-128">예</span><span class="sxs-lookup"><span data-stu-id="c1bae-128">Example</span></span>  
 <span data-ttu-id="c1bae-129">다음 Entity SQL 쿼리에서는 결과를 결정하기 위해 CASE 식을 사용하여 일련의 `Boolean` 식을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-129">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions in order to determine the result.</span></span> <span data-ttu-id="c1bae-130">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-130">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c1bae-131">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="c1bae-131">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="c1bae-132">절차에 따라 [하는 방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-132">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="c1bae-133">다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c1bae-133">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="c1bae-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1bae-134">See Also</span></span>  
 [<span data-ttu-id="c1bae-135">THEN</span><span class="sxs-lookup"><span data-stu-id="c1bae-135">THEN</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/then-entity-sql.md)  
 [<span data-ttu-id="c1bae-136">SELECT</span><span class="sxs-lookup"><span data-stu-id="c1bae-136">SELECT</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)  
 [<span data-ttu-id="c1bae-137">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="c1bae-137">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
