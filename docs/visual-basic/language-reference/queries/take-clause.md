---
title: "Take 절(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ee289a24c15226126a526af116ed53b4a9055b35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="take-clause-visual-basic"></a><span data-ttu-id="88ee5-102">Take 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88ee5-102">Take Clause (Visual Basic)</span></span>
<span data-ttu-id="88ee5-103">컬렉션의 시작 위치에서 지정된 수의 연속 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="88ee5-103">Returns a specified number of contiguous elements from the start of a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88ee5-104">구문</span><span class="sxs-lookup"><span data-stu-id="88ee5-104">Syntax</span></span>  
  
```  
Take count  
```  
  
## <a name="parts"></a><span data-ttu-id="88ee5-105">요소</span><span class="sxs-lookup"><span data-stu-id="88ee5-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="88ee5-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="88ee5-106">Required.</span></span> <span data-ttu-id="88ee5-107">값 또는 반환 되는 시퀀스의 요소 수로 계산 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="88ee5-107">A value or an expression that evaluates to the number of elements of the sequence to return.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88ee5-108">설명</span><span class="sxs-lookup"><span data-stu-id="88ee5-108">Remarks</span></span>  
 <span data-ttu-id="88ee5-109">`Take` 절로 인해 쿼리를 지정 된 수의 결과 목록에는의 시작 부분부터 연속 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ee5-109">The `Take` clause causes a query to include a specified number of contiguous elements from the start of a results list.</span></span> <span data-ttu-id="88ee5-110">요소를 포함 하도록 수가 붙습니다는 `count` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="88ee5-110">The number of elements to include is specified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="88ee5-111">사용할 수 있습니다는 `Take` 절과 함께 `Skip` 절 쿼리 세그먼트에서 데이터의 범위를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ee5-111">You can use the `Take` clause with the `Skip` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="88ee5-112">이 위해 전달 범위의 첫 번째 요소의 인덱스는 `Skip` 절과 범위의 크기는 `Take` 절.</span><span class="sxs-lookup"><span data-stu-id="88ee5-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span> <span data-ttu-id="88ee5-113">이 경우에 `Take` 뒤에 절을 지정 해야 합니다는 `Skip` 절.</span><span class="sxs-lookup"><span data-stu-id="88ee5-113">In this case, the `Take` clause must be specified after the `Skip` clause.</span></span>  
  
 <span data-ttu-id="88ee5-114">사용 하는 경우는 `Take` 쿼리에서 절을 할 수도 있습니다는 결과 수 있게 하는 순서로 반환 되도록 하는 `Take` 절에서 의도 한 결과 포함 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ee5-114">When you use the `Take` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Take` clause to include the intended results.</span></span> <span data-ttu-id="88ee5-115">쿼리 결과 정렬 하는 방법에 대 한 자세한 내용은 참조 [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88ee5-115">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="88ee5-116">사용할 수는 `TakeWhile` 절 제공된 조건에 따라 특정 요소에만 반환 되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ee5-116">You can use the `TakeWhile` clause to specify that only certain elements be returned, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88ee5-117">예제</span><span class="sxs-lookup"><span data-stu-id="88ee5-117">Example</span></span>  
 <span data-ttu-id="88ee5-118">다음 코드 예제에서는 `Take` 절과 함께 `Skip` 절을 페이지에 쿼리에서 데이터를에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ee5-118">The following code example uses the `Take` clause together with the `Skip` clause to return data from a query in pages.</span></span> <span data-ttu-id="88ee5-119">GetCustomers 사용 하 여 함수는 `Skip` 절 값을 사용 하 여 인덱스를 지정 된 시작 될 때까지 목록에서 고객을 무시 하는 `Take` 절 해당 인덱스 값에서 시작 하는 고객의 페이지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ee5-119">The GetCustomers function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="88ee5-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88ee5-120">See Also</span></span>  
 [<span data-ttu-id="88ee5-121">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="88ee5-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="88ee5-122">쿼리</span><span class="sxs-lookup"><span data-stu-id="88ee5-122">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="88ee5-123">Select 절</span><span class="sxs-lookup"><span data-stu-id="88ee5-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="88ee5-124">From 절</span><span class="sxs-lookup"><span data-stu-id="88ee5-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="88ee5-125">Order By 절</span><span class="sxs-lookup"><span data-stu-id="88ee5-125">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="88ee5-126">Take While 절</span><span class="sxs-lookup"><span data-stu-id="88ee5-126">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [<span data-ttu-id="88ee5-127">Skip 절</span><span class="sxs-lookup"><span data-stu-id="88ee5-127">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
