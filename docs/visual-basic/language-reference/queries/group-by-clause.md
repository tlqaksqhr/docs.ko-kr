---
title: "Group By 절 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
dev_langs:
- VB
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement
- Group By clause
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a27e2f15e61456b2e7ac0ede81c66cdb4e8fd612
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="group-by-clause-visual-basic"></a><span data-ttu-id="5a650-102">Group By 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a650-102">Group By Clause (Visual Basic)</span></span>
<span data-ttu-id="5a650-103">쿼리 결과의 요소를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-103">Groups the elements of a query result.</span></span> <span data-ttu-id="5a650-104">각 그룹에 집계 함수를 적용하는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-104">Can also be used to apply aggregate functions to each group.</span></span> <span data-ttu-id="5a650-105">그룹화 작업은 하나 이상의 키를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-105">The grouping operation is based on one or more keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a650-106">구문</span><span class="sxs-lookup"><span data-stu-id="5a650-106">Syntax</span></span>  
  
```  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a><span data-ttu-id="5a650-107">요소</span><span class="sxs-lookup"><span data-stu-id="5a650-107">Parts</span></span>  
  
-   <span data-ttu-id="5a650-108">`listField1`, `listField2`</span><span class="sxs-lookup"><span data-stu-id="5a650-108">`listField1`, `listField2`</span></span>  
  
     <span data-ttu-id="5a650-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-109">Optional.</span></span> <span data-ttu-id="5a650-110">그룹화된 결과에 포함할 필드를 명시적으로 식별하는 쿼리 변수의 하나 이상 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-110">One or more fields of the query variable or variables that explicitly identify the fields to be included in the grouped result.</span></span> <span data-ttu-id="5a650-111">필드를 지정하지 않으면 쿼리 변수의 모든 필드가 그룹화된 결과에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-111">If no fields are specified, all fields of the query variable or variables are included in the grouped result.</span></span>  
  
-   `keyExp1`  
  
     <span data-ttu-id="5a650-112">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="5a650-112">Required.</span></span> <span data-ttu-id="5a650-113">요소 그룹을 결정하는 데 사용할 키를 식별하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-113">An expression that identifies the key to use to determine the groups of elements.</span></span> <span data-ttu-id="5a650-114">둘 이상의 키를 지정하여 복합 키를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-114">You can specify more than one key to specify a composite key.</span></span>  
  
-   `keyExp2`  
  
     <span data-ttu-id="5a650-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-115">Optional.</span></span> <span data-ttu-id="5a650-116">복합 키를 만들기 위해 `keyExp1` 와 결합되는 하나 이상의 추가 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-116">One or more additional keys that are combined with `keyExp1` to create a composite key.</span></span>  
  
-   `aggregateList`  
  
     <span data-ttu-id="5a650-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="5a650-117">Required.</span></span> <span data-ttu-id="5a650-118">그룹의 집계 방법을 식별하는 하나 이상의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-118">One or more expressions that identify how the groups are aggregated.</span></span> <span data-ttu-id="5a650-119">그룹화된 결과의 멤버 이름을 식별하려면 다음 형식 중 하나일 수 있는 `Group` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-119">To identify a member name for the grouped results, use the `Group` keyword, which can be in either of the following forms:</span></span>  
  
    ```  
    Into Group  
    ```  
  
     <span data-ttu-id="5a650-120">또는</span><span class="sxs-lookup"><span data-stu-id="5a650-120">-or-</span></span>  
  
    ```  
    Into <alias> = Group  
    ```  
  
     <span data-ttu-id="5a650-121">그룹에 적용할 집계 함수를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-121">You can also include aggregate functions to apply to the group.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a650-122">주의</span><span class="sxs-lookup"><span data-stu-id="5a650-122">Remarks</span></span>  
 <span data-ttu-id="5a650-123">`Group By` 절을 사용하여 쿼리 결과를 그룹으로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-123">You can use the `Group By` clause to break the results of a query into groups.</span></span> <span data-ttu-id="5a650-124">그룹화는 키 또는 여러 키로 구성된 복합 키를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-124">The grouping is based on a key or a composite key consisting of multiple keys.</span></span> <span data-ttu-id="5a650-125">일치하는 키 값과 연결된 요소는 동일한 그룹에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-125">Elements that are associated with matching key values are included in the same group.</span></span>  
  
 <span data-ttu-id="5a650-126">`aggregateList` 절의 `Into` 매개 변수와 `Group` 키워드를 사용하여 그룹을 참조하는 데 사용되는 멤버 이름을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-126">You use the `aggregateList` parameter of the `Into` clause and the `Group` keyword to identify the member name that is used to reference the group.</span></span> <span data-ttu-id="5a650-127">`Into` 절에 집계 함수를 포함하여 그룹화된 요소의 값을 계산할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-127">You can also include aggregate functions in the `Into` clause to compute values for the grouped elements.</span></span> <span data-ttu-id="5a650-128">표준 집계 함수 목록은 참조 하십시오. [Aggregate 절](../../../visual-basic/language-reference/queries/aggregate-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-128">For a list of standard aggregate functions, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a650-129">예제</span><span class="sxs-lookup"><span data-stu-id="5a650-129">Example</span></span>  
 <span data-ttu-id="5a650-130">다음 코드 예제에서는 해당 위치(국가)를 기준으로 고객 목록을 그룹화하고 각 그룹에 있는 고객 수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-130">The following code example groups a list of customers based on their location (country) and provides a count of the customers in each group.</span></span> <span data-ttu-id="5a650-131">결과는 국가 이름별로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-131">The results are ordered by country name.</span></span> <span data-ttu-id="5a650-132">그룹화된 결과는 도시 이름별로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a650-132">The grouped results are ordered by city name.</span></span>  
  
 <span data-ttu-id="5a650-133">[!code-vb[VbSimpleQuerySamples #&11;](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-by-clause_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5a650-133">[!code-vb[VbSimpleQuerySamples#11](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-by-clause_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a650-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a650-134">See Also</span></span>  
 <span data-ttu-id="5a650-135">[Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="5a650-135">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="5a650-136"> [쿼리](../../../visual-basic/language-reference/queries/queries.md) </span><span class="sxs-lookup"><span data-stu-id="5a650-136"> [Queries](../../../visual-basic/language-reference/queries/queries.md) </span></span>  
<span data-ttu-id="5a650-137"> [Select 절](../../../visual-basic/language-reference/queries/select-clause.md) </span><span class="sxs-lookup"><span data-stu-id="5a650-137"> [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md) </span></span>  
<span data-ttu-id="5a650-138"> [From 절](../../../visual-basic/language-reference/queries/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="5a650-138"> [From Clause](../../../visual-basic/language-reference/queries/from-clause.md) </span></span>  
<span data-ttu-id="5a650-139"> [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md) </span><span class="sxs-lookup"><span data-stu-id="5a650-139"> [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md) </span></span>  
<span data-ttu-id="5a650-140"> [Aggregate 절](../../../visual-basic/language-reference/queries/aggregate-clause.md) </span><span class="sxs-lookup"><span data-stu-id="5a650-140"> [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md) </span></span>  
<span data-ttu-id="5a650-141"> [Group Join 절](../../../visual-basic/language-reference/queries/group-join-clause.md)</span><span class="sxs-lookup"><span data-stu-id="5a650-141"> [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md)</span></span>
