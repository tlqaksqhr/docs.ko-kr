---
title: 수량자 작업 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: ae1a2b73-503c-4f4b-a3fd-31b5adbee67c
ms.openlocfilehash: 0a0a5fae35a14ab6451f2f56fb2eedd92ac437e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33645836"
---
# <a name="quantifier-operations-visual-basic"></a><span data-ttu-id="ecc06-102">수량자 작업 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecc06-102">Quantifier Operations (Visual Basic)</span></span>
<span data-ttu-id="ecc06-103">수량자 작업은 시퀀스에서 조건을 충족하는 요소가 일부인지 전체인지를 나타내는 <xref:System.Boolean> 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc06-103">Quantifier operations return a <xref:System.Boolean> value that indicates whether some or all of the elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="ecc06-104">다음 그림은 두 개의 서로 다른 소스 시퀀스에 대한 두 개의 서로 다른 수량자 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ecc06-104">The following illustration depicts two different quantifier operations on two different source sequences.</span></span> <span data-ttu-id="ecc06-105">첫 번째 작업은 요소 중 하나 이상이 문자 'A'이고 결과가 `true`인지 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc06-105">The first operation asks if one or more of the elements are the character 'A', and the result is `true`.</span></span> <span data-ttu-id="ecc06-106">두 번째 작업은 모든 요소가 문자 'A'이고 결과가 `true`인지 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc06-106">The second operation asks if all the elements are the character 'A', and the result is `true`.</span></span>  
  
 <span data-ttu-id="ecc06-107">![LINQ 수량자 작업](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span><span class="sxs-lookup"><span data-stu-id="ecc06-107">![LINQ Quantifier Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_quantifier.png "LINQ_Quantifier")</span></span>  
  
 <span data-ttu-id="ecc06-108">다음 섹션에는 수량자 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecc06-108">The standard query operator methods that perform quantifier operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ecc06-109">메서드</span><span class="sxs-lookup"><span data-stu-id="ecc06-109">Methods</span></span>  
  
|<span data-ttu-id="ecc06-110">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="ecc06-110">Method Name</span></span>|<span data-ttu-id="ecc06-111">설명</span><span class="sxs-lookup"><span data-stu-id="ecc06-111">Description</span></span>|<span data-ttu-id="ecc06-112">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="ecc06-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="ecc06-113">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ecc06-113">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="ecc06-114">모두</span><span class="sxs-lookup"><span data-stu-id="ecc06-114">All</span></span>|<span data-ttu-id="ecc06-115">시퀀스의 모든 요소가 조건을 만족하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc06-115">Determines whether all the elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into All(…)`|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ecc06-116">임의의 값</span><span class="sxs-lookup"><span data-stu-id="ecc06-116">Any</span></span>|<span data-ttu-id="ecc06-117">시퀀스의 임의의 요소가 조건을 만족하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc06-117">Determines whether any elements in a sequence satisfy a condition.</span></span>|`Aggregate … In … Into Any()`|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="ecc06-118">포함</span><span class="sxs-lookup"><span data-stu-id="ecc06-118">Contains</span></span>|<span data-ttu-id="ecc06-119">시퀀스에 지정된 요소가 들어 있는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc06-119">Determines whether a sequence contains a specified element.</span></span>|<span data-ttu-id="ecc06-120">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="ecc06-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="ecc06-121">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="ecc06-121">Query Expression Syntax Examples</span></span>  
 <span data-ttu-id="ecc06-122">이러한 예에서 사용 된 `Aggregate` Visual basic의 LINQ 쿼리의 필터링 조건의 일부로 절 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc06-122">These examples use the `Aggregate` clause in Visual Basic as part of the filtering condition in a LINQ query.</span></span>  
  
 <span data-ttu-id="ecc06-123">다음 예제에서는 `Aggregate` 절 및 <xref:System.Linq.Enumerable.All%2A> 확장 메서드를가지고 있는 애완 동물 모든 지정 된 보존 기간 보다 오래 된 사용자를 컬렉션에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc06-123">The following example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.All%2A> extension method to return from a collection those people whose pets are all older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_1.vb)]  
  
 <span data-ttu-id="ecc06-124">사용 하 여 다음 예제는 `Aggregate` 절 및 <xref:System.Linq.Enumerable.Any%2A> 있는 애완 동물 적어도 한 대상 컬렉션에서 반환할 확장 메서드는 지정 된 보존 기간 보다 오래 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecc06-124">The next example uses the `Aggregate` clause and the <xref:System.Linq.Enumerable.Any%2A> extension method to return from a collection those people who have at least one pet that is older than a specified age.</span></span>  
  
 [!code-vb[CsLINQAnyAll#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/quantifier-operations_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ecc06-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ecc06-125">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="ecc06-126">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecc06-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="ecc06-127">Aggregate 절</span><span class="sxs-lookup"><span data-stu-id="ecc06-127">Aggregate Clause</span></span>](../../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="ecc06-128">방법: 지정된 된 단어 (LINQ) (Visual Basic) 집합이 들어 있는 문장 쿼리</span><span class="sxs-lookup"><span data-stu-id="ecc06-128">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)
