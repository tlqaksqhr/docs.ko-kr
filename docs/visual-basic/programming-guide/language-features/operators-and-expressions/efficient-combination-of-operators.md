---
title: "연산자의 효율적 결합(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b0f1d637bc1757515cf271a8c70d62effab0843
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="efficient-combination-of-operators-visual-basic"></a><span data-ttu-id="0365e-102">연산자의 효율적 결합(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0365e-102">Efficient Combination of Operators (Visual Basic)</span></span>
<span data-ttu-id="0365e-103">복잡 한 식은 여러 다른 연산자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0365e-103">Complex expressions can contain many different operators.</span></span> <span data-ttu-id="0365e-104">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0365e-104">The following example illustrates this.</span></span>  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 <span data-ttu-id="0365e-105">앞의 예제에 대 한 것과 같은 복잡 한 식 작성 연산자 우선 순위 규칙을 파악을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0365e-105">Creating complex expressions such as the one in the preceding example requires a thorough understanding of the rules of operator precedence.</span></span> <span data-ttu-id="0365e-106">자세한 내용은 참조 [Visual Basic의 연산자 우선 순위](../../../../visual-basic/language-reference/operators/operator-precedence.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0365e-106">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="0365e-107">괄호 식</span><span class="sxs-lookup"><span data-stu-id="0365e-107">Parenthetical Expressions</span></span>  
 <span data-ttu-id="0365e-108">연산자 우선 순위에 의해 결정 된 것과 다른 순서로 연산을 할 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0365e-108">Often you want operations to proceed in a different order from that determined by operator precedence.</span></span> <span data-ttu-id="0365e-109">다음 예제를 살펴보십시오.</span><span class="sxs-lookup"><span data-stu-id="0365e-109">Consider the following example.</span></span>  
  
 `x = z * y + 4`  
  
 <span data-ttu-id="0365e-110">앞의 예제를 곱합니다 `z` 여 `y`, 그런 다음 결과를 `4`합니다.</span><span class="sxs-lookup"><span data-stu-id="0365e-110">The preceding example multiplies `z` by `y`, then adds the result to `4`.</span></span> <span data-ttu-id="0365e-111">추가 하려는 경우 `y` 및 `4` 기준으로 결과 곱하기 전에 `z`, 괄호를 사용 하 여 일반 연산자 우선 순위를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0365e-111">But if you want to add `y` and `4` before multiplying the result by `z`, you can override normal operator precedence by using parentheses.</span></span> <span data-ttu-id="0365e-112">식을 괄호로 묶어, 묶으면 연산자 우선 순위에 관계 없이, 먼저 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0365e-112">By enclosing an expression in parentheses, you force that expression to be evaluated first, regardless of operator precedence.</span></span> <span data-ttu-id="0365e-113">먼저 추가 작업을 수행 하는 앞의 예제를 강제로 표시 하려면 다음 예제와 같이 다시를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0365e-113">To force the preceding example to do the addition first, you could rewrite it as in the following example.</span></span>  
  
 `x = z * (y + 4)`  
  
 <span data-ttu-id="0365e-114">위의 예제에서는 `y` 및 `4`를 더한 값에 곱합니다 `z`합니다.</span><span class="sxs-lookup"><span data-stu-id="0365e-114">The preceding example adds `y` and `4`, then multiplies that sum by `z`.</span></span>  
  
### <a name="nested-parenthetical-expressions"></a><span data-ttu-id="0365e-115">중첩 된 괄호 식</span><span class="sxs-lookup"><span data-stu-id="0365e-115">Nested Parenthetical Expressions</span></span>  
 <span data-ttu-id="0365e-116">식에 여러 수준의 우선 순위를 더욱 해소를 무시 하려면 괄호를 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0365e-116">You can nest expressions in multiple levels of parentheses to override precedence even further.</span></span> <span data-ttu-id="0365e-117">가장 깊게 중첩 등을 가장 깊이 중첩 된 마지막 괄호 외부의 식이 다음으로 가장 깊이 중첩 된 괄호 안에 식은 먼저 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0365e-117">The expressions most deeply nested in parentheses are evaluated first, followed by the next most deeply nested, and so on to the least deeply nested, and finally the expressions outside parentheses.</span></span> <span data-ttu-id="0365e-118">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0365e-118">The following example illustrates this.</span></span>  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 <span data-ttu-id="0365e-119">앞의 예제에서 `z + 2` 가장 먼저 평가 된 다음 다른 괄호 식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0365e-119">In the preceding example, `z + 2` is evaluated first, then the other parenthetical expressions.</span></span> <span data-ttu-id="0365e-120">지 수 연산자, 더하기 나 빼기 보다 높은 우선 순위에 일반적으로, 다른 식을 괄호로 묶여 있기 때문에이 예에서 마지막 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0365e-120">Exponentiation, which normally has higher precedence than addition or multiplication, is evaluated last in this example because the other expressions are enclosed in parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0365e-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0365e-121">See Also</span></span>  
 [<span data-ttu-id="0365e-122">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="0365e-122">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="0365e-123">Visual Basic의 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="0365e-123">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="0365e-124">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="0365e-124">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="0365e-125">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0365e-125">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="0365e-126">부울 식</span><span class="sxs-lookup"><span data-stu-id="0365e-126">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="0365e-127">값 비교</span><span class="sxs-lookup"><span data-stu-id="0365e-127">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="0365e-128">방법: 숫자 값 계산</span><span class="sxs-lookup"><span data-stu-id="0365e-128">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [<span data-ttu-id="0365e-129">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="0365e-129">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
