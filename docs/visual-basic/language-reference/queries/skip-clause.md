---
title: Skip 절(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 508f3c094df4c834305bcb4a78223c1cee82b1c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="c29fe-102">Skip 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c29fe-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="c29fe-103">컬렉션에서 지정된 수의 요소를 무시하고 나머지 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c29fe-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c29fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="c29fe-104">Syntax</span></span>  
  
```  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="c29fe-105">요소</span><span class="sxs-lookup"><span data-stu-id="c29fe-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="c29fe-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="c29fe-106">Required.</span></span> <span data-ttu-id="c29fe-107">값 또는 건너뛸 시퀀스의 요소 수로 계산 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="c29fe-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c29fe-108">설명</span><span class="sxs-lookup"><span data-stu-id="c29fe-108">Remarks</span></span>  
 <span data-ttu-id="c29fe-109">`Skip` 절로 인해 쿼리 결과 목록의 시작 부분에 있는 요소를 무시 하 고 나머지 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c29fe-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="c29fe-110">건너뛸 요소 수로 식별 되는 `count` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="c29fe-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="c29fe-111">사용할 수 있습니다는 `Skip` 절과 함께 `Take` 절 쿼리 세그먼트에서 데이터의 범위를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c29fe-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="c29fe-112">이 위해 전달 범위의 첫 번째 요소의 인덱스는 `Skip` 절과 범위의 크기는 `Take` 절.</span><span class="sxs-lookup"><span data-stu-id="c29fe-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="c29fe-113">사용 하는 경우는 `Skip` 쿼리에서 절을 할 수도 있습니다는 결과 수 있게 하는 순서로 반환 되도록 하는 `Skip` 절에서 의도 한 결과 무시 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c29fe-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="c29fe-114">쿼리 결과 정렬 하는 방법에 대 한 자세한 내용은 참조 [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c29fe-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="c29fe-115">사용할 수는 `SkipWhile` 절 제공된 조건에 따라 특정 요소에만 무시를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c29fe-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c29fe-116">예제</span><span class="sxs-lookup"><span data-stu-id="c29fe-116">Example</span></span>  
 <span data-ttu-id="c29fe-117">다음 코드 예제에서는 `Skip` 절과 함께 `Take` 절을 페이지에 쿼리에서 데이터를에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c29fe-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="c29fe-118">`GetCustomers` 함수는 `Skip` 절 값을 사용 하 여 인덱스를 지정 된 시작 될 때까지 목록에서 고객을 무시 하는 `Take` 절 해당 인덱스 값에서 시작 하는 고객의 페이지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c29fe-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c29fe-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c29fe-119">See Also</span></span>  
 [<span data-ttu-id="c29fe-120">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="c29fe-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="c29fe-121">쿼리</span><span class="sxs-lookup"><span data-stu-id="c29fe-121">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="c29fe-122">Select 절</span><span class="sxs-lookup"><span data-stu-id="c29fe-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="c29fe-123">From 절</span><span class="sxs-lookup"><span data-stu-id="c29fe-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="c29fe-124">Order By 절</span><span class="sxs-lookup"><span data-stu-id="c29fe-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="c29fe-125">Skip While 절</span><span class="sxs-lookup"><span data-stu-id="c29fe-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="c29fe-126">Take 절</span><span class="sxs-lookup"><span data-stu-id="c29fe-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
