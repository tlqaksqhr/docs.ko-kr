---
title: Group By 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement [Visual Basic]
- Group By clause [Visual Basic]
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
ms.openlocfilehash: 7cf688dc2e0ccd10c8bfbe5f0308f0aa808fbef0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605032"
---
# <a name="group-by-clause-visual-basic"></a><span data-ttu-id="b7a4a-102">Group By 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7a4a-102">Group By Clause (Visual Basic)</span></span>
<span data-ttu-id="b7a4a-103">쿼리 결과의 요소를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-103">Groups the elements of a query result.</span></span> <span data-ttu-id="b7a4a-104">각 그룹에 집계 함수를 적용하는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-104">Can also be used to apply aggregate functions to each group.</span></span> <span data-ttu-id="b7a4a-105">그룹화 작업은 하나 이상의 키를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-105">The grouping operation is based on one or more keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7a4a-106">구문</span><span class="sxs-lookup"><span data-stu-id="b7a4a-106">Syntax</span></span>  
  
```  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a><span data-ttu-id="b7a4a-107">요소</span><span class="sxs-lookup"><span data-stu-id="b7a4a-107">Parts</span></span>  
  
-   <span data-ttu-id="b7a4a-108">`listField1`, `listField2`</span><span class="sxs-lookup"><span data-stu-id="b7a4a-108">`listField1`, `listField2`</span></span>  
  
     <span data-ttu-id="b7a4a-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-109">Optional.</span></span> <span data-ttu-id="b7a4a-110">그룹화된 결과에 포함할 필드를 명시적으로 식별하는 쿼리 변수의 하나 이상 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-110">One or more fields of the query variable or variables that explicitly identify the fields to be included in the grouped result.</span></span> <span data-ttu-id="b7a4a-111">필드를 지정하지 않으면 쿼리 변수의 모든 필드가 그룹화된 결과에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-111">If no fields are specified, all fields of the query variable or variables are included in the grouped result.</span></span>  
  
-   `keyExp1`  
  
     <span data-ttu-id="b7a4a-112">필수.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-112">Required.</span></span> <span data-ttu-id="b7a4a-113">요소 그룹을 결정하는 데 사용할 키를 식별하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-113">An expression that identifies the key to use to determine the groups of elements.</span></span> <span data-ttu-id="b7a4a-114">둘 이상의 키를 지정하여 복합 키를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-114">You can specify more than one key to specify a composite key.</span></span>  
  
-   `keyExp2`  
  
     <span data-ttu-id="b7a4a-115">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-115">Optional.</span></span> <span data-ttu-id="b7a4a-116">복합 키를 만들기 위해 `keyExp1` 와 결합되는 하나 이상의 추가 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-116">One or more additional keys that are combined with `keyExp1` to create a composite key.</span></span>  
  
-   `aggregateList`  
  
     <span data-ttu-id="b7a4a-117">필수.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-117">Required.</span></span> <span data-ttu-id="b7a4a-118">그룹의 집계 방법을 식별하는 하나 이상의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-118">One or more expressions that identify how the groups are aggregated.</span></span> <span data-ttu-id="b7a4a-119">그룹화된 결과의 멤버 이름을 식별하려면 다음 형식 중 하나일 수 있는 `Group` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-119">To identify a member name for the grouped results, use the `Group` keyword, which can be in either of the following forms:</span></span>  
  
    ```  
    Into Group  
    ```  
  
     <span data-ttu-id="b7a4a-120">-또는-</span><span class="sxs-lookup"><span data-stu-id="b7a4a-120">-or-</span></span>  
  
    ```  
    Into <alias> = Group  
    ```  
  
     <span data-ttu-id="b7a4a-121">그룹에 적용할 집계 함수를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-121">You can also include aggregate functions to apply to the group.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7a4a-122">설명</span><span class="sxs-lookup"><span data-stu-id="b7a4a-122">Remarks</span></span>  
 <span data-ttu-id="b7a4a-123">`Group By` 절을 사용하여 쿼리 결과를 그룹으로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-123">You can use the `Group By` clause to break the results of a query into groups.</span></span> <span data-ttu-id="b7a4a-124">그룹화는 키 또는 여러 키로 구성된 복합 키를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-124">The grouping is based on a key or a composite key consisting of multiple keys.</span></span> <span data-ttu-id="b7a4a-125">일치하는 키 값과 연결된 요소는 동일한 그룹에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-125">Elements that are associated with matching key values are included in the same group.</span></span>  
  
 <span data-ttu-id="b7a4a-126">`aggregateList` 절의 `Into` 매개 변수와 `Group` 키워드를 사용하여 그룹을 참조하는 데 사용되는 멤버 이름을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-126">You use the `aggregateList` parameter of the `Into` clause and the `Group` keyword to identify the member name that is used to reference the group.</span></span> <span data-ttu-id="b7a4a-127">`Into` 절에 집계 함수를 포함하여 그룹화된 요소의 값을 계산할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-127">You can also include aggregate functions in the `Into` clause to compute values for the grouped elements.</span></span> <span data-ttu-id="b7a4a-128">목록이 표준 집계 함수에 대 한 참조 [Aggregate 절](../../../visual-basic/language-reference/queries/aggregate-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-128">For a list of standard aggregate functions, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7a4a-129">예제</span><span class="sxs-lookup"><span data-stu-id="b7a4a-129">Example</span></span>  
 <span data-ttu-id="b7a4a-130">다음 코드 예제에서는 해당 위치(국가)를 기준으로 고객 목록을 그룹화하고 각 그룹에 있는 고객 수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-130">The following code example groups a list of customers based on their location (country) and provides a count of the customers in each group.</span></span> <span data-ttu-id="b7a4a-131">결과는 국가 이름별로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-131">The results are ordered by country name.</span></span> <span data-ttu-id="b7a4a-132">그룹화된 결과는 도시 이름별로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-132">The grouped results are ordered by city name.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#11](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-by-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b7a4a-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7a4a-133">See Also</span></span>  
 [<span data-ttu-id="b7a4a-134">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="b7a4a-134">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="b7a4a-135">쿼리</span><span class="sxs-lookup"><span data-stu-id="b7a4a-135">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="b7a4a-136">Select 절</span><span class="sxs-lookup"><span data-stu-id="b7a4a-136">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="b7a4a-137">From 절</span><span class="sxs-lookup"><span data-stu-id="b7a4a-137">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="b7a4a-138">Order By 절</span><span class="sxs-lookup"><span data-stu-id="b7a4a-138">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="b7a4a-139">Aggregate 절</span><span class="sxs-lookup"><span data-stu-id="b7a4a-139">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="b7a4a-140">Group Join 절</span><span class="sxs-lookup"><span data-stu-id="b7a4a-140">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
