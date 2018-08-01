---
title: Join 절 결과의 순서 정렬(C#의 LINQ)
description: C#의 LINQ Join 절 결과의 순서를 정렬하는 방법을 알아봅니다.
ms.date: 12/1/2016
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: e4a12b6f9b4a99decb1f64524ebe67a196084a04
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404738"
---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="5be40-103">join 절 결과를 순서대로 정렬</span><span class="sxs-lookup"><span data-stu-id="5be40-103">Order the results of a join clause</span></span>

<span data-ttu-id="5be40-104">이 예제에서는 조인 작업 결과를 순서대로 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5be40-104">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="5be40-105">조인 후 순서대로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="5be40-105">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="5be40-106">조인 전에 하나 이상의 소스 시퀀스와 함께 `orderby` 절을 사용할 수도 있지만 일반적으로 권장되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5be40-106">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="5be40-107">일부 LINQ 공급자는 조인 후에 정렬 순서를 유지하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5be40-107">Some LINQ providers might not preserve that ordering after the join.</span></span>

## <a name="example"></a><span data-ttu-id="5be40-108">예</span><span class="sxs-lookup"><span data-stu-id="5be40-108">Example</span></span>

<span data-ttu-id="5be40-109">이 쿼리는 그룹 조인을 만든 후 범위 내에 있는 범주 요소에 따라 그룹을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="5be40-109">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="5be40-110">무명 형식 이니셜라이저 내의 하위 쿼리는 제품 시퀀스에서 일치하는 모든 요소를 순서대로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="5be40-110">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>

[!code-csharp[csProgGuideLINQ#81](~/samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]

## <a name="see-also"></a><span data-ttu-id="5be40-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5be40-111">See also</span></span>

[<span data-ttu-id="5be40-112">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="5be40-112">Language Integrated Query (LINQ)</span></span>](index.md)  
[<span data-ttu-id="5be40-113">orderby 절</span><span class="sxs-lookup"><span data-stu-id="5be40-113">orderby clause</span></span>](../language-reference/keywords/orderby-clause.md)  
[<span data-ttu-id="5be40-114">join 절</span><span class="sxs-lookup"><span data-stu-id="5be40-114">join clause</span></span>](../language-reference/keywords/join-clause.md)  