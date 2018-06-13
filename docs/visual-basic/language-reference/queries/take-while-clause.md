---
title: Take While 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 7e0a6bd77ca2594e9d74e669fcd9cddf91ee1cad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600912"
---
# <a name="take-while-clause-visual-basic"></a><span data-ttu-id="4e52b-102">Take While 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e52b-102">Take While Clause (Visual Basic)</span></span>
<span data-ttu-id="4e52b-103">지정된 조건이 `true`이면 컬렉션의 요소를 포함하고 나머지 요소를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="4e52b-103">Includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e52b-104">구문</span><span class="sxs-lookup"><span data-stu-id="4e52b-104">Syntax</span></span>  
  
```  
Take While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="4e52b-105">요소</span><span class="sxs-lookup"><span data-stu-id="4e52b-105">Parts</span></span>  
  
|<span data-ttu-id="4e52b-106">용어</span><span class="sxs-lookup"><span data-stu-id="4e52b-106">Term</span></span>|<span data-ttu-id="4e52b-107">정의</span><span class="sxs-lookup"><span data-stu-id="4e52b-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="4e52b-108">필수.</span><span class="sxs-lookup"><span data-stu-id="4e52b-108">Required.</span></span> <span data-ttu-id="4e52b-109">에 대 한 요소를 테스트 하는 조건을 나타내는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="4e52b-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="4e52b-110">식은 반환 해야 합니다는 `Boolean` 값 또는 이와 동일한 기능와 같은 프로그램 `Integer` 으로 계산 되는 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e52b-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e52b-111">설명</span><span class="sxs-lookup"><span data-stu-id="4e52b-111">Remarks</span></span>  
 <span data-ttu-id="4e52b-112">`Take While` 까지 제공 된 쿼리 결과의 시작 부분에서 요소를 포함 하는 절 `expression` 반환 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e52b-112">The `Take While` clause includes elements from the start of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="4e52b-113">이후에 `expression` 반환 `false`, 나머지 모든 요소를 무시 하는 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e52b-113">After the `expression` returns `false`, the query will bypass all remaining elements.</span></span> <span data-ttu-id="4e52b-114">`expression` 나머지 결과 대해 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e52b-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="4e52b-115">`Take While` 절에서와 다른는 `Where` 절에 있는 `Where` 쿼리에서 특정 조건을 만족 하는 모든 요소를 포함 하려면 절을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e52b-115">The `Take While` clause differs from the `Where` clause in that the `Where` clause can be used to include all elements from a query that meet a particular condition.</span></span> <span data-ttu-id="4e52b-116">`Take While` 절 조건이 충족 되지 않은 처음 될 때까지 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e52b-116">The `Take While` clause includes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="4e52b-117">`Take While` 절은 순서가 지정 된 쿼리 결과 사용 하 여 작업할 때 가장 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e52b-117">The `Take While` clause is most useful when you are working with an ordered query result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e52b-118">예제</span><span class="sxs-lookup"><span data-stu-id="4e52b-118">Example</span></span>  
 <span data-ttu-id="4e52b-119">다음 코드 예제에서는 `Take While` 절 순서 없이 첫 번째 고객을 찾을 때까지 결과를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e52b-119">The following code example uses the `Take While` clause to retrieve results until the first customer without any orders is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#2](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-while-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4e52b-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e52b-120">See Also</span></span>  
 [<span data-ttu-id="4e52b-121">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="4e52b-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="4e52b-122">쿼리</span><span class="sxs-lookup"><span data-stu-id="4e52b-122">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="4e52b-123">Select 절</span><span class="sxs-lookup"><span data-stu-id="4e52b-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="4e52b-124">From 절</span><span class="sxs-lookup"><span data-stu-id="4e52b-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="4e52b-125">Take 절</span><span class="sxs-lookup"><span data-stu-id="4e52b-125">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 [<span data-ttu-id="4e52b-126">Skip While 절</span><span class="sxs-lookup"><span data-stu-id="4e52b-126">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="4e52b-127">Where 절</span><span class="sxs-lookup"><span data-stu-id="4e52b-127">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
