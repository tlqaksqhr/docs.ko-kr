---
title: Where 절(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8c2572f513d00bc72e869cf28d382be799f7a303
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="af8e2-102">Where 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af8e2-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="af8e2-103">쿼리에 대 한 필터링 조건을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af8e2-104">구문</span><span class="sxs-lookup"><span data-stu-id="af8e2-104">Syntax</span></span>  
  
```  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="af8e2-105">요소</span><span class="sxs-lookup"><span data-stu-id="af8e2-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="af8e2-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="af8e2-106">Required.</span></span> <span data-ttu-id="af8e2-107">컬렉션에서 현재 항목의 값을 출력 컬렉션에 포함 되는지 여부를 결정 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="af8e2-108">에 식이 계산 되어야는 `Boolean` 값 또는 해당 하는 한 `Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="af8e2-109">조건이를 반환 하는 경우 `True`, 요소는 쿼리 결과에 포함 되지 않았으면, 쿼리 결과에서 요소 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af8e2-110">설명</span><span class="sxs-lookup"><span data-stu-id="af8e2-110">Remarks</span></span>  
 <span data-ttu-id="af8e2-111">`Where` 절을 사용 하면 특정 조건을 충족 하는 요소만 선택 하 여 쿼리 데이터를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="af8e2-112">값이 해당 요소는 `Where` 를 평가 하는 절 `True` ; 쿼리 결과에 포함 된 다른 요소가 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="af8e2-113">식에 사용 되는 한 `Where` 절으로 계산 되어야 합니다는 `Boolean` 또는 해당 하는 `Boolean`, 등으로 계산 되는 정수 `False` 때 그 값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="af8e2-114">여러 개의 식을 결합할 수는 `Where` 절과 같은 논리 연산자를 사용 하 여 `And`, `Or`, `AndAlso`, `OrElse`, `Is`, 및 `IsNot`합니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="af8e2-115">기본적으로 쿼리 식은 계산 되지 않습니다 액세스 될 때까지-예를 들어 경우는 데이터-바인딩되거나 통해는 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="af8e2-116">결과적으로 `Where` 절 쿼리 액세스 될 때까지 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="af8e2-117">에 사용 되는 쿼리 외부에 값이 있는 경우는 `Where` 절에 적절 한 값을 사용 해야는 `Where` 쿼리가 실행 될 때 절.</span><span class="sxs-lookup"><span data-stu-id="af8e2-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="af8e2-118">쿼리 실행에 대 한 자세한 내용은 참조 [쓰기 Your LINQ 쿼리 처음](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="af8e2-119">내에서 함수를 호출할 수는 `Where` 절 컬렉션의 현재 요소에서 계산 또는 값에 대 한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="af8e2-120">함수를 호출는 `Where` 절이 정의 될 때 대신 액세스할 때 즉시 실행할 쿼리를 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="af8e2-121">쿼리 실행에 대 한 자세한 내용은 참조 [쓰기 Your LINQ 쿼리 처음](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="af8e2-122">예제</span><span class="sxs-lookup"><span data-stu-id="af8e2-122">Example</span></span>  
 <span data-ttu-id="af8e2-123">다음 쿼리는 사용 되는 식은 `From` 범위 변수를 선언 하는 절 `cust` 각 `Customer` 개체는 `customers` 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="af8e2-124">`Where` 절 범위 변수를 사용 하 여 지정된 된 지역에서 고객에 게 출력을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="af8e2-125">`For Each` 루프 쿼리 결과에서 각 고객의 회사 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="af8e2-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="af8e2-126">예제</span><span class="sxs-lookup"><span data-stu-id="af8e2-126">Example</span></span>  
 <span data-ttu-id="af8e2-127">다음 예제에서는 `And` 및 `Or` 의 논리 연산자는 `Where` 절.</span><span class="sxs-lookup"><span data-stu-id="af8e2-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="af8e2-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af8e2-128">See Also</span></span>  
 [<span data-ttu-id="af8e2-129">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="af8e2-129">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="af8e2-130">쿼리</span><span class="sxs-lookup"><span data-stu-id="af8e2-130">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="af8e2-131">From 절</span><span class="sxs-lookup"><span data-stu-id="af8e2-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="af8e2-132">Select 절</span><span class="sxs-lookup"><span data-stu-id="af8e2-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="af8e2-133">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="af8e2-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
