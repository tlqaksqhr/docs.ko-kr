---
title: 연산자 우선 순위(Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: ab5158a2af18a422cb82f0d44412bcd85a04dc2a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="operator-precedence-entity-sql"></a><span data-ttu-id="e145a-102">연산자 우선 순위(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e145a-102">Operator Precedence (Entity SQL)</span></span>
<span data-ttu-id="e145a-103">경우는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에 여러 명의 연산자, 연산자 우선 순위가 연산 수행 순서를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e145a-103">When an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query has multiple operators, operator precedence determines the sequence in which the operations are performed.</span></span> <span data-ttu-id="e145a-104">실행 순서는 쿼리 결과에 상당한 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e145a-104">The order of execution can significantly affect the query result.</span></span>  
  
 <span data-ttu-id="e145a-105">다음 표에서는 연산자 우선 순위를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e145a-105">Operators have the precedence levels shown in the following table.</span></span> <span data-ttu-id="e145a-106">높은 수준의 연산자는 낮은 수준의 연산자보다 먼저 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="e145a-106">An operator with a higher level is evaluated before an operator with a lower level.</span></span>  
  
|<span data-ttu-id="e145a-107">수준</span><span class="sxs-lookup"><span data-stu-id="e145a-107">Level</span></span>|<span data-ttu-id="e145a-108">연산 유형</span><span class="sxs-lookup"><span data-stu-id="e145a-108">Operation type</span></span>|<span data-ttu-id="e145a-109">연산자</span><span class="sxs-lookup"><span data-stu-id="e145a-109">Operator</span></span>|  
|-----------|--------------------|--------------|  
|<span data-ttu-id="e145a-110">1</span><span class="sxs-lookup"><span data-stu-id="e145a-110">1</span></span>|<span data-ttu-id="e145a-111">기본 연산자</span><span class="sxs-lookup"><span data-stu-id="e145a-111">Primary</span></span>|`. , [] ()`|  
|<span data-ttu-id="e145a-112">2</span><span class="sxs-lookup"><span data-stu-id="e145a-112">2</span></span>|<span data-ttu-id="e145a-113">단항</span><span class="sxs-lookup"><span data-stu-id="e145a-113">Unary</span></span>|`! not`|  
|<span data-ttu-id="e145a-114">3</span><span class="sxs-lookup"><span data-stu-id="e145a-114">3</span></span>|<span data-ttu-id="e145a-115">곱하기</span><span class="sxs-lookup"><span data-stu-id="e145a-115">Multiplicative</span></span>|`* / %`|  
|<span data-ttu-id="e145a-116">4</span><span class="sxs-lookup"><span data-stu-id="e145a-116">4</span></span>|<span data-ttu-id="e145a-117">더하기</span><span class="sxs-lookup"><span data-stu-id="e145a-117">Additive</span></span>|`+ -`|  
|<span data-ttu-id="e145a-118">5</span><span class="sxs-lookup"><span data-stu-id="e145a-118">5</span></span>|<span data-ttu-id="e145a-119">정렬</span><span class="sxs-lookup"><span data-stu-id="e145a-119">Ordering</span></span>|`< > <= >=`|  
|<span data-ttu-id="e145a-120">6</span><span class="sxs-lookup"><span data-stu-id="e145a-120">6</span></span>|<span data-ttu-id="e145a-121">같음</span><span class="sxs-lookup"><span data-stu-id="e145a-121">Equality</span></span>|`= != <>`|  
|<span data-ttu-id="e145a-122">7</span><span class="sxs-lookup"><span data-stu-id="e145a-122">7</span></span>|<span data-ttu-id="e145a-123">조건부 AND</span><span class="sxs-lookup"><span data-stu-id="e145a-123">Conditional AND</span></span>|`and &&`|  
|<span data-ttu-id="e145a-124">8</span><span class="sxs-lookup"><span data-stu-id="e145a-124">8</span></span>|<span data-ttu-id="e145a-125">조건부 OR</span><span class="sxs-lookup"><span data-stu-id="e145a-125">Conditional OR</span></span>|`or &#124;&#124;`|  
  
 <span data-ttu-id="e145a-126">식에 연산자 우선 순위 수준이 동일한 두 연산자가 있으면 쿼리 내의 위치를 기준으로 왼쪽에서 오른쪽으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="e145a-126">When two operators in an expression have the same operator precedence level, they are evaluated left to right, based on their position in the query.</span></span> <span data-ttu-id="e145a-127">예를 들어, `x+y-z`는 `(x+y)-z`로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="e145a-127">For example, `x+y-z` is evaluated as `(x+y)-z`.</span></span>  
  
 <span data-ttu-id="e145a-128">괄호를 사용하여 쿼리에서 연산자에 정의된 우선 순위를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e145a-128">You can use parentheses to override the defined precedence of the operators in a query.</span></span> <span data-ttu-id="e145a-129">괄호 안의 모든 연산자를 먼저 계산하여 단일 결과를 생성한 후, 이 결과를 괄호 밖의 연산자에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e145a-129">Everything within parentheses is evaluated first to yield a single result before that result can be used by any operator outside the parentheses.</span></span> <span data-ttu-id="e145a-130">예를 들어 `x+y*z` 곱합니다 `y` 여 `z` 다음 추가 `x`, 하지만 `(x+y)*z` 추가 `x` 를 `y` 을 다음 기준으로 결과 곱합니다 `z`합니다.</span><span class="sxs-lookup"><span data-stu-id="e145a-130">For example, `x+y*z` multiplies `y` by `z` and then adds `x`, but `(x+y)*z` adds `x` to `y` and then multiplies the result by `z`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e145a-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e145a-131">See Also</span></span>  
 [<span data-ttu-id="e145a-132">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="e145a-132">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
