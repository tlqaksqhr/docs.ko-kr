---
title: "join 절 결과를 순서대로 정렬"
description: "join 절 결과를 순서대로 정렬하는 방법"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: a7458901-1201-4c25-b8d9-c04ca52e0eb9
ms.openlocfilehash: f948c18fb16a4f3ac02945b4a63583f1b01cad40
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="order-the-results-of-a-join-clause"></a><span data-ttu-id="27a46-104">join 절 결과를 순서대로 정렬</span><span class="sxs-lookup"><span data-stu-id="27a46-104">Order the results of a join clause</span></span>
<span data-ttu-id="27a46-105">이 예제에서는 조인 작업 결과를 순서대로 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27a46-105">This example shows how to order the results of a join operation.</span></span> <span data-ttu-id="27a46-106">조인 후 순서대로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="27a46-106">Note that the ordering is performed after the join.</span></span> <span data-ttu-id="27a46-107">조인 전에 하나 이상의 소스 시퀀스와 함께 `orderby` 절을 사용할 수도 있지만 일반적으로 권장되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27a46-107">Although you can use an `orderby` clause with one or more of the source sequences before the join, generally we do not recommend it.</span></span> <span data-ttu-id="27a46-108">일부 LINQ 공급자는 조인 후에 정렬 순서를 유지하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27a46-108">Some LINQ providers might not preserve that ordering after the join.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27a46-109">예제</span><span class="sxs-lookup"><span data-stu-id="27a46-109">Example</span></span>  
 <span data-ttu-id="27a46-110">이 쿼리는 그룹 조인을 만든 후 범위 내에 있는 범주 요소에 따라 그룹을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="27a46-110">This query creates a group join, and then sorts the groups based on the category element, which is still in scope.</span></span> <span data-ttu-id="27a46-111">무명 형식 이니셜라이저 내의 하위 쿼리는 제품 시퀀스에서 일치하는 모든 요소를 순서대로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="27a46-111">Inside the anonymous type initializer, a sub-query orders all the matching elements from the products sequence.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#81](../../../samples/snippets/csharp/concepts/linq/how-to-order-the-results-of-a-join-clause_1.cs)]  
 
## <a name="see-also"></a><span data-ttu-id="27a46-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27a46-112">See also</span></span>  
 [<span data-ttu-id="27a46-113">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="27a46-113">LINQ query expressions</span></span>](index.md)  
 [<span data-ttu-id="27a46-114">orderby 절</span><span class="sxs-lookup"><span data-stu-id="27a46-114">orderby clause</span></span>](../language-reference/keywords/orderby-clause.md)  
 [<span data-ttu-id="27a46-115">join 절</span><span class="sxs-lookup"><span data-stu-id="27a46-115">join clause</span></span>](../language-reference/keywords/join-clause.md) 
