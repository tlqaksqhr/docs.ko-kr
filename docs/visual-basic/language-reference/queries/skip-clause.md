---
title: Skip 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 1810bf4a6573c6fa36f1d8149bf341d45cfd6f52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602829"
---
# <a name="skip-clause-visual-basic"></a><span data-ttu-id="448a3-102">Skip 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="448a3-102">Skip Clause (Visual Basic)</span></span>
<span data-ttu-id="448a3-103">컬렉션에서 지정된 수의 요소를 무시하고 나머지 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="448a3-103">Bypasses a specified number of elements in a collection and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="448a3-104">구문</span><span class="sxs-lookup"><span data-stu-id="448a3-104">Syntax</span></span>  
  
```  
Skip count  
```  
  
## <a name="parts"></a><span data-ttu-id="448a3-105">요소</span><span class="sxs-lookup"><span data-stu-id="448a3-105">Parts</span></span>  
 `count`  
 <span data-ttu-id="448a3-106">필수.</span><span class="sxs-lookup"><span data-stu-id="448a3-106">Required.</span></span> <span data-ttu-id="448a3-107">값 또는 건너뛸 시퀀스의 요소 수로 계산 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="448a3-107">A value or an expression that evaluates to the number of elements of the sequence to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="448a3-108">설명</span><span class="sxs-lookup"><span data-stu-id="448a3-108">Remarks</span></span>  
 <span data-ttu-id="448a3-109">`Skip` 절로 인해 쿼리 결과 목록의 시작 부분에 있는 요소를 무시 하 고 나머지 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="448a3-109">The `Skip` clause causes a query to bypass elements at the beginning of a results list and return the remaining elements.</span></span> <span data-ttu-id="448a3-110">건너뛸 요소 수로 식별 되는 `count` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="448a3-110">The number of elements to skip is identified by the `count` parameter.</span></span>  
  
 <span data-ttu-id="448a3-111">사용할 수 있습니다는 `Skip` 절과 함께 `Take` 절 쿼리 세그먼트에서 데이터의 범위를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448a3-111">You can use the `Skip` clause with the `Take` clause to return a range of data from any segment of a query.</span></span> <span data-ttu-id="448a3-112">이 위해 전달 범위의 첫 번째 요소의 인덱스는 `Skip` 절과 범위의 크기는 `Take` 절.</span><span class="sxs-lookup"><span data-stu-id="448a3-112">To do this, pass the index of the first element of the range to the `Skip` clause and the size of the range to the `Take` clause.</span></span>  
  
 <span data-ttu-id="448a3-113">사용 하는 경우는 `Skip` 쿼리에서 절을 할 수도 있습니다는 결과 수 있게 하는 순서로 반환 되도록 하는 `Skip` 절에서 의도 한 결과 무시 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="448a3-113">When you use the `Skip` clause in a query, you may also need to ensure that the results are returned in an order that will enable the `Skip` clause to bypass the intended results.</span></span> <span data-ttu-id="448a3-114">쿼리 결과 정렬 하는 방법에 대 한 자세한 내용은 참조 [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="448a3-114">For more information about ordering query results, see [Order By Clause](../../../visual-basic/language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="448a3-115">사용할 수는 `SkipWhile` 절 제공된 조건에 따라 특정 요소에만 무시를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448a3-115">You can use the `SkipWhile` clause to specify that only certain elements are ignored, depending on a supplied condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="448a3-116">예제</span><span class="sxs-lookup"><span data-stu-id="448a3-116">Example</span></span>  
 <span data-ttu-id="448a3-117">다음 코드 예제에서는 `Skip` 절과 함께 `Take` 절을 페이지에 쿼리에서 데이터를에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="448a3-117">The following code example uses the `Skip` clause together with the `Take` clause to return data from a query in pages.</span></span> <span data-ttu-id="448a3-118">`GetCustomers` 함수는 `Skip` 절 값을 사용 하 여 인덱스를 지정 된 시작 될 때까지 목록에서 고객을 무시 하는 `Take` 절 해당 인덱스 값에서 시작 하는 고객의 페이지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="448a3-118">The `GetCustomers` function uses the `Skip` clause to bypass the customers in the list until the supplied starting index value, and uses the `Take` clause to return a page of customers starting from that index value.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="448a3-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="448a3-119">See Also</span></span>  
 [<span data-ttu-id="448a3-120">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="448a3-120">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="448a3-121">쿼리</span><span class="sxs-lookup"><span data-stu-id="448a3-121">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="448a3-122">Select 절</span><span class="sxs-lookup"><span data-stu-id="448a3-122">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="448a3-123">From 절</span><span class="sxs-lookup"><span data-stu-id="448a3-123">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="448a3-124">Order By 절</span><span class="sxs-lookup"><span data-stu-id="448a3-124">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="448a3-125">Skip While 절</span><span class="sxs-lookup"><span data-stu-id="448a3-125">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="448a3-126">Take 절</span><span class="sxs-lookup"><span data-stu-id="448a3-126">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
