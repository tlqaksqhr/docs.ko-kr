---
title: "Join 절(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2bb25c9dac8994e7f975539c1d036f0f0d9d239e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="131ed-102">Join 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="131ed-102">Join Clause (Visual Basic)</span></span>
<span data-ttu-id="131ed-103">두 컬렉션을 단일 컬렉션으로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="131ed-104">조인 연산은 일치 하는 키에 기반 하며 사용 하 여 `Equals` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="131ed-105">구문</span><span class="sxs-lookup"><span data-stu-id="131ed-105">Syntax</span></span>  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a><span data-ttu-id="131ed-106">요소</span><span class="sxs-lookup"><span data-stu-id="131ed-106">Parts</span></span>  
 `element`  
 <span data-ttu-id="131ed-107">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="131ed-107">Required.</span></span> <span data-ttu-id="131ed-108">조인 중인 컬렉션에 대 한 제어 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-108">The control variable for the collection being joined.</span></span>  
  
 `collection`  
 <span data-ttu-id="131ed-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="131ed-109">Required.</span></span> <span data-ttu-id="131ed-110">컬렉션의 왼쪽에 식별 된 컬렉션으로 결합 하는 `Join` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="131ed-111">A `Join` 다른에 중첩 절 `Join` 절 또는 `Group Join` 절.</span><span class="sxs-lookup"><span data-stu-id="131ed-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>  
  
 `joinClause`  
 <span data-ttu-id="131ed-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-112">Optional.</span></span> <span data-ttu-id="131ed-113">하나 이상의 추가 `Join` 는 쿼리를 구체화 하는 절을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-113">One or more additional `Join` clauses to further refine the query.</span></span>  
  
 `groupJoinClause`  
 <span data-ttu-id="131ed-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-114">Optional.</span></span> <span data-ttu-id="131ed-115">하나 이상의 추가 `Group Join` 는 쿼리를 구체화 하는 절을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-115">One or more additional `Group Join` clauses to further refine the query.</span></span>  
  
 <span data-ttu-id="131ed-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="131ed-116">`key1` `Equals` `key2`</span></span>  
 <span data-ttu-id="131ed-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="131ed-117">Required.</span></span> <span data-ttu-id="131ed-118">조인 중인 컬렉션에 대 한 키를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="131ed-119">사용 해야 합니다는 `Equals` 조인 중인 컬렉션에서 키를 비교 연산자.</span><span class="sxs-lookup"><span data-stu-id="131ed-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="131ed-120">사용 하 여 조인 조건을 결합할 수 있습니다는 `And` 여러 키를 식별 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="131ed-121">`key1`왼쪽에 있는 컬렉션에서 이어야 합니다는 `Join` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="131ed-122">`key2`오른쪽에 있는 컬렉션에서 이어야 합니다는 `Join` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>  
  
 <span data-ttu-id="131ed-123">조인 조건에 사용 되는 키 컬렉션에서 둘 이상의 항목을 포함 하는 식을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="131ed-124">그러나 각 키의 식에는 해당 컬렉션의 항목에만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-124">However, each key expression can contain only items from its respective collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="131ed-125">설명</span><span class="sxs-lookup"><span data-stu-id="131ed-125">Remarks</span></span>  
 <span data-ttu-id="131ed-126">`Join` 절 조인 중인 컬렉션의 키 값을 일치 하는 두 개의 컬렉션을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="131ed-127">결과 컬렉션의 왼쪽에 식별 된 컬렉션에서 값의 조합이 포함 될 수 있습니다는 `Join` 연산자 및에서 식별 된 컬렉션의 `Join` 절.</span><span class="sxs-lookup"><span data-stu-id="131ed-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="131ed-128">쿼리는 반환 하 여 지정 된 조건이 결과만 `Equals` 연산자 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="131ed-129">이 해당 하는 `INNER JOIN` sql에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>  
  
 <span data-ttu-id="131ed-130">여러 개 사용할 수 있습니다 `Join` 에 둘 이상의 컬렉션을 단일 컬렉션으로 조인 쿼리에서 절.</span><span class="sxs-lookup"><span data-stu-id="131ed-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>  
  
 <span data-ttu-id="131ed-131">결합 하지 않고 컬렉션 암시적 조인을 수행할 수 있습니다는 `Join` 절.</span><span class="sxs-lookup"><span data-stu-id="131ed-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="131ed-132">이 위해 여러 개 포함 `In` 절을 프로그램 `From` 절을 지정 하 고는 `Where` 는 조인에 사용 하려는 하는 키를 식별 하는 절.</span><span class="sxs-lookup"><span data-stu-id="131ed-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>  
  
 <span data-ttu-id="131ed-133">사용할 수는 `Group Join` 절 단일 계층 구조 컬렉션으로 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="131ed-134">이 비슷하지만 `LEFT OUTER JOIN` sql에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="131ed-135">예제</span><span class="sxs-lookup"><span data-stu-id="131ed-135">Example</span></span>  
 <span data-ttu-id="131ed-136">다음 코드 예제에서는 고객 목록을 고객의 주문을와 결합할 암시적 조인을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="131ed-137">예제</span><span class="sxs-lookup"><span data-stu-id="131ed-137">Example</span></span>  
 <span data-ttu-id="131ed-138">다음 코드 예제에서는 사용 하 여 두 컬렉션 조인는 `Join` 절.</span><span class="sxs-lookup"><span data-stu-id="131ed-138">The following code example joins two collections by using the `Join` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 <span data-ttu-id="131ed-139">이 예제에는 다음과 유사한 결과가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-139">This example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a><span data-ttu-id="131ed-140">예제</span><span class="sxs-lookup"><span data-stu-id="131ed-140">Example</span></span>  
 <span data-ttu-id="131ed-141">다음 코드 예제에서는 사용 하 여 두 컬렉션 조인는 `Join` 절 두 개의 키 열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 <span data-ttu-id="131ed-142">이 예제에는 다음과 유사한 결과가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="131ed-142">The example will produce output similar to the following:</span></span>  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a><span data-ttu-id="131ed-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="131ed-143">See Also</span></span>  
 [<span data-ttu-id="131ed-144">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="131ed-144">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="131ed-145">쿼리</span><span class="sxs-lookup"><span data-stu-id="131ed-145">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="131ed-146">Select 절</span><span class="sxs-lookup"><span data-stu-id="131ed-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="131ed-147">From 절</span><span class="sxs-lookup"><span data-stu-id="131ed-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="131ed-148">Group Join 절</span><span class="sxs-lookup"><span data-stu-id="131ed-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="131ed-149">Where 절</span><span class="sxs-lookup"><span data-stu-id="131ed-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
