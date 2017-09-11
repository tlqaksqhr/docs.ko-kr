---
title: "집합 작업 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2b9fd7ec122fff2601296ae3a46bb7607b2b32ef
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="set-operations-visual-basic"></a><span data-ttu-id="f6ab4-102">집합 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6ab4-102">Set Operations (Visual Basic)</span></span>
<span data-ttu-id="f6ab4-103">LINQ의 set 작업은 동일 하거나 별도 컬렉션 (또는 집합)에 동등한 요소가 있는지 여부를 기반으로 하는 결과 집합을 생성 하는 쿼리 작업을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-103">Set operations in LINQ refer to query operations that produce a result set that is based on the presence or absence of equivalent elements within the same or separate collections (or sets).</span></span>  
  
 <span data-ttu-id="f6ab4-104">집합 작업을 수행 하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-104">The standard query operator methods that perform set operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f6ab4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f6ab4-105">Methods</span></span>  
  
|<span data-ttu-id="f6ab4-106">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="f6ab4-106">Method Name</span></span>|<span data-ttu-id="f6ab4-107">설명</span><span class="sxs-lookup"><span data-stu-id="f6ab4-107">Description</span></span>|<span data-ttu-id="f6ab4-108">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="f6ab4-108">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="f6ab4-109">추가 정보</span><span class="sxs-lookup"><span data-stu-id="f6ab4-109">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="f6ab4-110">Distinct</span><span class="sxs-lookup"><span data-stu-id="f6ab4-110">Distinct</span></span>|<span data-ttu-id="f6ab4-111">컬렉션에서 값 중복을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-111">Removes duplicate values from a collection.</span></span>|`Distinct`|<span data-ttu-id="f6ab4-112"><xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f6ab4-112"><xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f6ab4-113"><xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName></xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f6ab4-113"><xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="f6ab4-114">제외</span><span class="sxs-lookup"><span data-stu-id="f6ab4-114">Except</span></span>|<span data-ttu-id="f6ab4-115">차집합 즉, 두 번째 컬렉션에 표시 되지 않는 한 컬렉션의 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-115">Returns the set difference, which means the elements of one collection that do not appear in a second collection.</span></span>|<span data-ttu-id="f6ab4-116">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-116">Not applicable.</span></span>|<span data-ttu-id="f6ab4-117"><xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f6ab4-117"><xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f6ab4-118"><xref:System.Linq.Queryable.Except%2A?displayProperty=fullName></xref:System.Linq.Queryable.Except%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f6ab4-118"><xref:System.Linq.Queryable.Except%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="f6ab4-119">교차</span><span class="sxs-lookup"><span data-stu-id="f6ab4-119">Intersect</span></span>|<span data-ttu-id="f6ab4-120">두 컬렉션의 각 항목에 표시 되는 요소를 의미는 교집합을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-120">Returns the set intersection, which means elements that appear in each of two collections.</span></span>|<span data-ttu-id="f6ab4-121">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-121">Not applicable.</span></span>|<span data-ttu-id="f6ab4-122"><xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f6ab4-122"><xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f6ab4-123"><xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName></xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f6ab4-123"><xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="f6ab4-124">공용 구조체</span><span class="sxs-lookup"><span data-stu-id="f6ab4-124">Union</span></span>|<span data-ttu-id="f6ab4-125">즉, 두 컬렉션 중 하나에 있는 고유 요소가 합집합을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-125">Returns the set union, which means unique elements that appear in either of two collections.</span></span>|<span data-ttu-id="f6ab4-126">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-126">Not applicable.</span></span>|<span data-ttu-id="f6ab4-127"><xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f6ab4-127"><xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="f6ab4-128"><xref:System.Linq.Queryable.Union%2A?displayProperty=fullName></xref:System.Linq.Queryable.Union%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f6ab4-128"><xref:System.Linq.Queryable.Union%2A?displayProperty=fullName></span></span>|  
  
## <a name="comparison-of-set-operations"></a><span data-ttu-id="f6ab4-129">집합 작업의 비교</span><span class="sxs-lookup"><span data-stu-id="f6ab4-129">Comparison of Set Operations</span></span>  
  
### <a name="distinct"></a><span data-ttu-id="f6ab4-130">Distinct</span><span class="sxs-lookup"><span data-stu-id="f6ab4-130">Distinct</span></span>  
 <span data-ttu-id="f6ab4-131">다음 그림의 동작을 보여 줍니다.는 <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName>메서드 문자 시퀀스를.</xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f6ab4-131">The following illustration depicts the behavior of the <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName> method on a sequence of characters.</span></span> <span data-ttu-id="f6ab4-132">반환 된 시퀀스는 입력된 시퀀스에서 고유 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-132">The returned sequence contains the unique elements from the input sequence.</span></span>  
  
 <span data-ttu-id="f6ab4-133">![Distinct ()의 동작을 보여 주는 그래픽입니다. ] (../../../../csharp/programming-guide/concepts/linq/media/distinct.png "고유")</span><span class="sxs-lookup"><span data-stu-id="f6ab4-133">![Graphic showing the behavior of Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")</span></span>  
  
### <a name="except"></a><span data-ttu-id="f6ab4-134">제외</span><span class="sxs-lookup"><span data-stu-id="f6ab4-134">Except</span></span>  
 <span data-ttu-id="f6ab4-135">다음 그림 <xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>.</xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName> 의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-135">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="f6ab4-136">반환 된 시퀀스는 두 번째 입력된 시퀀스에 있지 않은 첫 번째 입력된 시퀀스에서 요소만 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-136">The returned sequence contains only the elements from the first input sequence that are not in the second input sequence.</span></span>  
  
 <span data-ttu-id="f6ab4-137">![Except ()의 동작을 보여 주는 그래픽입니다. ](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span><span class="sxs-lookup"><span data-stu-id="f6ab4-137">![Graphic showing the action of Except&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")</span></span>  
  
### <a name="intersect"></a><span data-ttu-id="f6ab4-138">교차</span><span class="sxs-lookup"><span data-stu-id="f6ab4-138">Intersect</span></span>  
 <span data-ttu-id="f6ab4-139">다음 그림 <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>.</xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName> 의 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-139">The following illustration depicts the behavior of <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="f6ab4-140">반환 된 시퀀스는 입력된 시퀀스의 양쪽에 공통 된 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-140">The returned sequence contains the elements that are common to both of the input sequences.</span></span>  
  
 <span data-ttu-id="f6ab4-141">![두 시퀀스의 교집합을 보여 주는 그래픽입니다. ] (../../../../csharp/programming-guide/concepts/linq/media/intersect.png "교차")</span><span class="sxs-lookup"><span data-stu-id="f6ab4-141">![Graphic showing the intersection of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")</span></span>  
  
### <a name="union"></a><span data-ttu-id="f6ab4-142">공용 구조체</span><span class="sxs-lookup"><span data-stu-id="f6ab4-142">Union</span></span>  
 <span data-ttu-id="f6ab4-143">다음 그림은 문자 두 시퀀스에 대해 union 연산을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-143">The following illustration depicts a union operation on two sequences of characters.</span></span> <span data-ttu-id="f6ab4-144">반환 된 시퀀스는 두 입력된 시퀀스에서 고유 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-144">The returned sequence contains the unique elements from both input sequences.</span></span>  
  
 <span data-ttu-id="f6ab4-145">![두 시퀀스의 결합을 보여주는 그래픽입니다. ](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span><span class="sxs-lookup"><span data-stu-id="f6ab4-145">![Graphic showing the union of two sequences.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")</span></span>  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="f6ab4-146">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="f6ab4-146">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="f6ab4-147">다음 예제에서는 `Distinct` 정수 목록에서 고유한 숫자를 반환 하는 LINQ 쿼리에서 절.</span><span class="sxs-lookup"><span data-stu-id="f6ab4-147">The following example uses the `Distinct` clause in a LINQ query to return the unique numbers from a list of integers.</span></span>  
  
 <span data-ttu-id="f6ab4-148">[!code-vb[CsLINQSetOps #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f6ab4-148">[!code-vb[CsLINQSetOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ab4-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6ab4-149">See Also</span></span>  
 <span data-ttu-id="f6ab4-150"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="f6ab4-150"><xref:System.Linq></span></span>   
<span data-ttu-id="f6ab4-151"> [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="f6ab4-151"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="f6ab4-152"> [Distinct 절](../../../../visual-basic/language-reference/queries/distinct-clause.md) </span><span class="sxs-lookup"><span data-stu-id="f6ab4-152"> [Distinct Clause](../../../../visual-basic/language-reference/queries/distinct-clause.md) </span></span>  
<span data-ttu-id="f6ab4-153"> [방법: 문자열 컬렉션 (Visual Basic) (LINQ) 결합 및 비교](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md) </span><span class="sxs-lookup"><span data-stu-id="f6ab4-153"> [How to: Combine and Compare String Collections (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md) </span></span>  
<span data-ttu-id="f6ab4-154"> [방법: 두 목록 (Visual Basic) (LINQ) 간의 차집합 구하기](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)</span><span class="sxs-lookup"><span data-stu-id="f6ab4-154"> [How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)</span></span>
