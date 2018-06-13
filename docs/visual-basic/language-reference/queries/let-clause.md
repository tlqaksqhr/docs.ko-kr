---
title: Let 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 6484da5329c8240735b7c35f506637dd01cbeda4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604473"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="aa43a-102">Let 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa43a-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="aa43a-103">값을 계산 하 고 쿼리 내에서 새 변수를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa43a-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa43a-104">구문</span><span class="sxs-lookup"><span data-stu-id="aa43a-104">Syntax</span></span>  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="aa43a-105">요소</span><span class="sxs-lookup"><span data-stu-id="aa43a-105">Parts</span></span>  
  
|<span data-ttu-id="aa43a-106">용어</span><span class="sxs-lookup"><span data-stu-id="aa43a-106">Term</span></span>|<span data-ttu-id="aa43a-107">정의</span><span class="sxs-lookup"><span data-stu-id="aa43a-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="aa43a-108">필수.</span><span class="sxs-lookup"><span data-stu-id="aa43a-108">Required.</span></span> <span data-ttu-id="aa43a-109">지정된 된 식의 결과를 사용할 수 있는 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="aa43a-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="aa43a-110">필수.</span><span class="sxs-lookup"><span data-stu-id="aa43a-110">Required.</span></span> <span data-ttu-id="aa43a-111">평가 되 고 지정 된 변수에 할당 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="aa43a-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa43a-112">설명</span><span class="sxs-lookup"><span data-stu-id="aa43a-112">Remarks</span></span>  
 <span data-ttu-id="aa43a-113">`Let` 절을 사용 하면 계산 값 각각에 대 한 쿼리 결과 및 별칭을 사용 하 여 엔터티를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa43a-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="aa43a-114">다른 절에서와 같은 별칭을 사용할 수는 `Where` 절.</span><span class="sxs-lookup"><span data-stu-id="aa43a-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="aa43a-115">`Let` 절을 사용 하면 더 쉽게 읽을 쿼리에 포함 된 식 절에 별칭을 지정 하는 별칭 식 절을 사용할 때마다 대체할 수 있기 때문에 쿼리 문을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa43a-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="aa43a-116">개수에 관계 없이 포함할 수 있습니다 `variable` 및 `expression` 에 할당 된 `Let` 절.</span><span class="sxs-lookup"><span data-stu-id="aa43a-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="aa43a-117">쉼표 (,)로 각 할당을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa43a-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa43a-118">예제</span><span class="sxs-lookup"><span data-stu-id="aa43a-118">Example</span></span>  
 <span data-ttu-id="aa43a-119">다음 코드 예제에서는 `Let` 절 10% 할인 제품을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa43a-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="aa43a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa43a-120">See Also</span></span>  
 [<span data-ttu-id="aa43a-121">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="aa43a-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="aa43a-122">쿼리</span><span class="sxs-lookup"><span data-stu-id="aa43a-122">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="aa43a-123">Select 절</span><span class="sxs-lookup"><span data-stu-id="aa43a-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="aa43a-124">From 절</span><span class="sxs-lookup"><span data-stu-id="aa43a-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="aa43a-125">Where 절</span><span class="sxs-lookup"><span data-stu-id="aa43a-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
