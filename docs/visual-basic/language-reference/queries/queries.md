---
title: "쿼리(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- queries [Visual Basic]
- LINQ, queries
ms.assetid: 8edc717c-4a24-4cbc-9c16-11f479c935db
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80038bae51f16daca19da73905f6bbce42a63b97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="queries-visual-basic"></a><span data-ttu-id="5c49d-102">쿼리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c49d-102">Queries (Visual Basic)</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="5c49d-103">만들 수 있습니다 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 코드의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="5c49d-103"> enables you to create [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] expressions in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5c49d-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="5c49d-104">In This Section</span></span>  
 [<span data-ttu-id="5c49d-105">Aggregate 절</span><span class="sxs-lookup"><span data-stu-id="5c49d-105">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 <span data-ttu-id="5c49d-106">설명의 `Aggregate` 를 컬렉션에 하나 이상의 집계 함수를 적용 하는 절.</span><span class="sxs-lookup"><span data-stu-id="5c49d-106">Describes the `Aggregate` clause, which applies one or more aggregate functions to a collection.</span></span>  
  
 [<span data-ttu-id="5c49d-107">Distinct 절</span><span class="sxs-lookup"><span data-stu-id="5c49d-107">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 <span data-ttu-id="5c49d-108">설명의 `Distinct` 쿼리 결과에서 중복 값을 제거 하 여 현재 범위 변수 값을 제한 하는 절.</span><span class="sxs-lookup"><span data-stu-id="5c49d-108">Describes the `Distinct` clause, which restricts the values of the current range variable to eliminate duplicate values in query results.</span></span>  
  
 [<span data-ttu-id="5c49d-109">From 절</span><span class="sxs-lookup"><span data-stu-id="5c49d-109">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 <span data-ttu-id="5c49d-110">설명의 `From` 컬렉션과 쿼리에 대 한 범위 변수를 지정 하는 절.</span><span class="sxs-lookup"><span data-stu-id="5c49d-110">Describes the `From` clause, which specifies a collection and a range variable for a query.</span></span>  
  
 [<span data-ttu-id="5c49d-111">Group By 절</span><span class="sxs-lookup"><span data-stu-id="5c49d-111">Group By Clause</span></span>](../../../visual-basic/language-reference/queries/group-by-clause.md)  
 <span data-ttu-id="5c49d-112">설명의 `Group By` 절 쿼리 결과의 요소를 그룹화와 각 그룹에 집계 함수를 적용 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c49d-112">Describes the `Group By` clause, which groups the elements of a query result and can be used to apply aggregate functions to each group.</span></span>  
  
 [<span data-ttu-id="5c49d-113">Group Join 절</span><span class="sxs-lookup"><span data-stu-id="5c49d-113">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 <span data-ttu-id="5c49d-114">설명의 `Group Join` 두 컬렉션을 단일 계층 구조 컬렉션으로 결합 하는 절.</span><span class="sxs-lookup"><span data-stu-id="5c49d-114">Describes the `Group Join` clause, which combines two collections into a single hierarchical collection.</span></span>  
  
 [<span data-ttu-id="5c49d-115">Join 절</span><span class="sxs-lookup"><span data-stu-id="5c49d-115">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)  
 <span data-ttu-id="5c49d-116">설명의 `Join` 두 컬렉션을 단일 컬렉션으로 결합 하는 절.</span><span class="sxs-lookup"><span data-stu-id="5c49d-116">Describes the `Join` clause, which combines two collections into a single collection.</span></span>  
  
 [<span data-ttu-id="5c49d-117">Let 절</span><span class="sxs-lookup"><span data-stu-id="5c49d-117">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 <span data-ttu-id="5c49d-118">설명의 `Let` 값을 계산 하 고 쿼리의 새 변수에 할당 하는 절.</span><span class="sxs-lookup"><span data-stu-id="5c49d-118">Describes the `Let` clause, which computes a value and assigns it to a new variable in the query.</span></span>  
  
 [<span data-ttu-id="5c49d-119">Order By 절</span><span class="sxs-lookup"><span data-stu-id="5c49d-119">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 <span data-ttu-id="5c49d-120">설명의 `Order By` 쿼리에서 열에 대 한 정렬 순서를 지정 하는 절.</span><span class="sxs-lookup"><span data-stu-id="5c49d-120">Describes the `Order By` clause, which specifies the sort order for columns in a query.</span></span>  
  
 [<span data-ttu-id="5c49d-121">Select 절</span><span class="sxs-lookup"><span data-stu-id="5c49d-121">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 <span data-ttu-id="5c49d-122">설명의 `Select` 쿼리에 대 한 범위 변수의 집합을 선언 하는 절.</span><span class="sxs-lookup"><span data-stu-id="5c49d-122">Describes the `Select` clause, which declares a set of range variables for a query.</span></span>  
  
 [<span data-ttu-id="5c49d-123">Skip 절</span><span class="sxs-lookup"><span data-stu-id="5c49d-123">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 <span data-ttu-id="5c49d-124">설명의 `Skip` 절을 지정된 하는 컬렉션의 요소 수가 건너뛴 다음 나머지 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c49d-124">Describes the `Skip` clause, which bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
 [<span data-ttu-id="5c49d-125">Skip While 절</span><span class="sxs-lookup"><span data-stu-id="5c49d-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 <span data-ttu-id="5c49d-126">설명의 `Skip While` 지정 된 조건이으로 컬렉션의 요소를 무시 하는 절 `true` 다음 나머지 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c49d-126">Describes the `Skip While` clause, which bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
 [<span data-ttu-id="5c49d-127">Take 절</span><span class="sxs-lookup"><span data-stu-id="5c49d-127">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 <span data-ttu-id="5c49d-128">설명의 `Take` 절 컬렉션의 시작 부분부터 연속 된 요소로 지정 된 수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c49d-128">Describes the `Take` clause, which returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
 [<span data-ttu-id="5c49d-129">Take While 절</span><span class="sxs-lookup"><span data-stu-id="5c49d-129">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 <span data-ttu-id="5c49d-130">설명의 `Take While` 지정 된 조건이으로 컬렉션의 요소를 포함 하는 절 `true` 나머지 요소를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c49d-130">Describes the `Take While` clause, which includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
 [<span data-ttu-id="5c49d-131">Where 절</span><span class="sxs-lookup"><span data-stu-id="5c49d-131">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
 <span data-ttu-id="5c49d-132">설명의 `Where` 쿼리에 대 한 필터링 조건을 지정 하는 절.</span><span class="sxs-lookup"><span data-stu-id="5c49d-132">Describes the `Where` clause, which specifies a filtering condition for a query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c49d-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c49d-133">See Also</span></span>  
 [<span data-ttu-id="5c49d-134">LINQ</span><span class="sxs-lookup"><span data-stu-id="5c49d-134">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="5c49d-135">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="5c49d-135">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
