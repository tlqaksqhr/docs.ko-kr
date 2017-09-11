---
title: "수량자 작업 (Visual Basic) | Microsoft 문서"
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
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
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
ms.openlocfilehash: 4e0c982508640ef1ecb47d477d3e9330198474ca
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="a06d4-102">수량자 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a06d4-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="a06d4-103">수량자 작업에서 반환 된 <xref:System.Boolean>시퀀스의 요소 중 일부 또는 모두에 조건을 만족 하는지 여부를 나타내는 값입니다.</xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="a06d4-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="a06d4-104">다음 그림에서는 두 개의 서로 다른 소스 시퀀스에서 두 개의 다른 수량자 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a06d4-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="a06d4-105">첫 번째 작업 인지 묻고 요소 중 하나 이상이 문자 'A', 결과 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="a06d4-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="a06d4-106">두 번째 작업 인지 묻고 모든 요소는 문자 'A', 결과 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="a06d4-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="a06d4-107">![LINQ 수량자 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="a06d4-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="a06d4-108">수량자 작업을 수행 하는 표준 쿼리 연산자 메서드는 다음 섹션에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a06d4-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a06d4-109">메서드</span><span class="sxs-lookup"><span data-stu-id="a06d4-109">Methods</span></span>  
  
|<span data-ttu-id="a06d4-110">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="a06d4-110">Method Name</span></span>|<span data-ttu-id="a06d4-111">설명</span><span class="sxs-lookup"><span data-stu-id="a06d4-111">Description</span></span>|<span data-ttu-id="a06d4-112">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="a06d4-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="a06d4-113">추가 정보</span><span class="sxs-lookup"><span data-stu-id="a06d4-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="a06d4-114">모두</span><span class="sxs-lookup"><span data-stu-id="a06d4-114">All</span></span>|<span data-ttu-id="a06d4-115">시퀀스의 모든 요소가 조건을 만족 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a06d4-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<span data-ttu-id="a06d4-116"><xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a06d4-116"><xref:System.Linq.Enumerable.All%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="a06d4-117"><xref:System.Linq.Queryable.All%2A?displayProperty=fullName></xref:System.Linq.Queryable.All%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a06d4-117"><xref:System.Linq.Queryable.All%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="a06d4-118">임의의 값</span><span class="sxs-lookup"><span data-stu-id="a06d4-118">Any</span></span>|<span data-ttu-id="a06d4-119">시퀀스의 모든 요소가 조건을 만족 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a06d4-119">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<span data-ttu-id="a06d4-120"><xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a06d4-120"><xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="a06d4-121"><xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a06d4-121"><xref:System.Linq.Queryable.Any%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="a06d4-122">포함</span><span class="sxs-lookup"><span data-stu-id="a06d4-122">Contains</span></span>|<span data-ttu-id="a06d4-123">시퀀스에 지정 된 요소가 들어 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a06d4-123">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="a06d4-124">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="a06d4-124">Not applicable.</span></span>|<span data-ttu-id="a06d4-125"><xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a06d4-125"><xref:System.Linq.Enumerable.Contains%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="a06d4-126"><xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a06d4-126"><xref:System.Linq.Queryable.Contains%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="a06d4-127">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="a06d4-127">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="a06d4-128">이 예제에서는 사용 된 `Aggregate` Visual basic LINQ 쿼리에서 필터링 조건의 일부로 절.</span><span class="sxs-lookup"><span data-stu-id="a06d4-128">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="a06d4-129">다음 예제에서는 `Aggregate` 절 및 <xref:System.Linq.Enumerable.All%2A>확장 메서드를가지고 있는 애완 동물 모두 지정 된 보존 기간 보다 오래 된 사용자는 컬렉션에서 반환할.</xref:System.Linq.Enumerable.All%2A></span><span class="sxs-lookup"><span data-stu-id="a06d4-129">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 <span data-ttu-id="a06d4-130">[!code-vb[CsLINQAnyAll #&1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a06d4-130">[!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]</span></span>  
  
 <span data-ttu-id="a06d4-131">사용 하 여 다음 예제는 `Aggregate` 절 및 <xref:System.Linq.Enumerable.Any%2A>하나 이상 포함 하는 사람들 있는 애완 동물을 컬렉션에서 반환할 확장 메서드는 지정 된 기간 보다 오래 된.</xref:System.Linq.Enumerable.Any%2A></span><span class="sxs-lookup"><span data-stu-id="a06d4-131">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 <span data-ttu-id="a06d4-132">[!code-vb[CsLINQAnyAll #&2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a06d4-132">[!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a06d4-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a06d4-133">See Also</span></span>  
 <span data-ttu-id="a06d4-134"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="a06d4-134"><xref:System.Linq></span></span>   
<span data-ttu-id="a06d4-135"> [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="a06d4-135"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="a06d4-136"> [Aggregate 절](../../../../visual-basic/language-reference/queries/aggregate-clause.md) </span><span class="sxs-lookup"><span data-stu-id="a06d4-136"> [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) </span></span>  
<span data-ttu-id="a06d4-137"> [방법: 지정된 된 단어 (LINQ) (Visual Basic) 집합이 들어 있는 문장 쿼리](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)</span><span class="sxs-lookup"><span data-stu-id="a06d4-137"> [How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)</span></span>
