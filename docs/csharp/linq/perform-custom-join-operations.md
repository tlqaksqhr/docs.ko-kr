---
title: 사용자 지정 조인 작업 수행
description: 사용자 지정 조인 작업을 수행하는 방법
ms.date: 12/1/2016
ms.assetid: 56a2a4a5-7299-497d-b3c3-23c848678911
ms.openlocfilehash: df80f4382ad5fa96fcdc41b338cbb53a3d8e6cb9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288524"
---
# <a name="perform-custom-join-operations"></a><span data-ttu-id="540dc-103">사용자 지정 조인 작업 수행</span><span class="sxs-lookup"><span data-stu-id="540dc-103">Perform custom join operations</span></span>

<span data-ttu-id="540dc-104">이 예제에서는 `join` 절에 사용할 수 없는 조인 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-104">This example shows how to perform join operations that are not possible with the `join` clause.</span></span> <span data-ttu-id="540dc-105">쿼리 식에서 `join` 절은 조인 작업의 가장 일반적인 형식인 동등 조인으로 제한되고 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-105">In a query expression, the `join` clause is limited to, and optimized for, equijoins, which are by far the most common type of join operation.</span></span> <span data-ttu-id="540dc-106">동등 조인을 수행하는 경우 `join` 절을 사용하면 항상 최상의 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-106">When performing an equijoin, you will probably always get the best performance by using the `join` clause.</span></span>  
  
 <span data-ttu-id="540dc-107">그러나 `join` 절은 다음과 같은 경우에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-107">However, the `join` clause cannot be used in the following cases:</span></span>  
  
-   <span data-ttu-id="540dc-108">조인이 같지 않음(비동등 조인)의 식에서 서술된 경우</span><span class="sxs-lookup"><span data-stu-id="540dc-108">When the join is predicated on an expression of inequality (a non-equijoin).</span></span>  
  
-   <span data-ttu-id="540dc-109">조인이 둘 이상의 같음 또는 같지 않음에서 서술된 경우</span><span class="sxs-lookup"><span data-stu-id="540dc-109">When the join is predicated on more than one expression of equality or inequality.</span></span>  
  
-   <span data-ttu-id="540dc-110">조인 작업 앞에서 오른쪽(내부) 시퀀스에 대한 임시 범위 변수를 도입해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="540dc-110">When you have to introduce a temporary range variable for the right side (inner) sequence before the join operation.</span></span>  
  
 <span data-ttu-id="540dc-111">조인 동등이 아닌 조인을 수행하려면 여러 개의 `from` 절을 사용하여 각 데이터 소스를 독립적으로 도입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-111">To perform joins that are not equijoins, you can use multiple `from` clauses to introduce each data source independently.</span></span> <span data-ttu-id="540dc-112">그런 다음 `where` 절의 조건자 식을 각 소스에 대한 범위 변수에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-112">You then apply a predicate expression in a `where` clause to the range variable for each source.</span></span> <span data-ttu-id="540dc-113">식은 메서드 호출의 형식을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-113">The expression also can take the form of a method call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="540dc-114">여러 `from` 절을 사용하여 내부 컬렉션에 액세스하는 경우와 이러한 종류의 사용자 지정 조인 작업을 혼동하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="540dc-114">Do not confuse this kind of custom join operation with the use of multiple `from` clauses to access inner collections.</span></span> <span data-ttu-id="540dc-115">자세한 내용은 [join 절](../language-reference/keywords/join-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="540dc-115">For more information, see [join clause](../language-reference/keywords/join-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="540dc-116">예</span><span class="sxs-lookup"><span data-stu-id="540dc-116">Example</span></span>  
 <span data-ttu-id="540dc-117">다음 예제의 첫 번째 메서드는 간단한 크로스 조인을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-117">The first method in the following example shows a simple cross join.</span></span> <span data-ttu-id="540dc-118">크로스 조인은 매우 큰 결과 집합을 생성할 수 있으므로 주의해서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-118">Cross joins must be used with caution because they can produce very large result sets.</span></span> <span data-ttu-id="540dc-119">그러나 추가 쿼리가 실행되는 소스 시퀀스를 만들기 위해 일부 시나리오에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-119">However, they can be useful in some scenarios for creating source sequences against which additional queries are run.</span></span>  
  
 <span data-ttu-id="540dc-120">두 번째 메서드는 범주 ID가 왼쪽의 범주 목록에 나열된 모든 제품의 시퀀스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-120">The second method produces a sequence of all the products whose category ID is listed in the category list on the left side.</span></span> <span data-ttu-id="540dc-121">`let` 절과 `Contains` 메서드를 사용하여 임시 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-121">Note the use of the `let` clause and the `Contains` method to create a temporary array.</span></span> <span data-ttu-id="540dc-122">또한 쿼리 앞에서 배열을 만들고 첫 번째 `from` 절을 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-122">It also is possible to create the array before the query and eliminate the first `from` clause.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#64](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="540dc-123">예</span><span class="sxs-lookup"><span data-stu-id="540dc-123">Example</span></span>  
 <span data-ttu-id="540dc-124">다음 예제에서는 쿼리가 내부(오른쪽) 시퀀스의 경우 조인 절 앞에서 가져올 수 없는 일치 키에 따라 두 시퀀스를 조인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-124">In the following example, the query must join two sequences based on matching keys that, in the case of the inner (right side) sequence, cannot be obtained prior to the join clause itself.</span></span> <span data-ttu-id="540dc-125">`join` 절을 사용하여 이 조인을 수행하는 경우 각 요소에 대해 `Split` 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-125">If this join were performed with a `join` clause, then the `Split` method would have to be called for each element.</span></span> <span data-ttu-id="540dc-126">여러 개의 `from` 절을 사용하면 쿼리에서 반복된 메서드 호출의 오버헤드를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-126">The use of multiple `from` clauses enables the query to avoid the overhead of the repeated method call.</span></span> <span data-ttu-id="540dc-127">그러나 `join`이 최적화되었으므로 이 특정 사례에서는 여러 개의 `from` 절을 사용하는 것보다 더 빠를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-127">However, since `join` is optimized, in this particular case it might still be faster than using multiple `from` clauses.</span></span> <span data-ttu-id="540dc-128">결과는 주로 메서드 호출이 얼마나 광범위한지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="540dc-128">The results will vary depending primarily on how expensive the method call is.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#13](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="540dc-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="540dc-129">See also</span></span>  
 [<span data-ttu-id="540dc-130">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="540dc-130">LINQ query expressions</span></span>](index.md)  
 [<span data-ttu-id="540dc-131">join 절</span><span class="sxs-lookup"><span data-stu-id="540dc-131">join clause</span></span>](../language-reference/keywords/join-clause.md)  
 [<span data-ttu-id="540dc-132">Join 절 결과를 서순대로 정렬</span><span class="sxs-lookup"><span data-stu-id="540dc-132">Order the results of a join clause</span></span>](order-the-results-of-a-join-clause.md)
