---
title: "Visual Basic의 논리 및 비트 연산자"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- operators [Visual Basic], logical
- AndAlso operator [Visual Basic]
- Not operator [Visual Basic], Boolean expressions
- Xor operator [Visual Basic], Boolean expressions
- And operator [Visual Basic], logical operators
- logical operators [Visual Basic]
- expressions [Visual Basic], Boolean
- Or operator [Visual Basic], logical operators
- Visual Basic code, operators
- short-circuiting [Visual Basic], logical operators
- logical operators [Visual Basic], short-circuiting
- Visual Basic code, expressions
- logical operators [Visual Basic], binary
- OrElse operator [Visual Basic]
- logical operators [Visual Basic], unary
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ba48f722a11e93f82ae99aa407c3096a964e5ddd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a><span data-ttu-id="8f337-102">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="8f337-102">Logical and Bitwise Operators in Visual Basic</span></span>
<span data-ttu-id="8f337-103">논리 연산자 비교 `Boolean` 식 및 반환 된 `Boolean` 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-103">Logical operators compare `Boolean` expressions and return a `Boolean` result.</span></span> <span data-ttu-id="8f337-104">`And`, `Or`, `AndAlso`, `OrElse`, 및 `Xor` 연산자는 *이진* 동안 두 개의 피연산자를 고려 하기 때문에 `Not` 연산자는 *단항* 단일 피연산자를 사용 하기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-104">The `And`, `Or`, `AndAlso`, `OrElse`, and `Xor` operators are *binary* because they take two operands, while the `Not` operator is *unary* because it takes a single operand.</span></span> <span data-ttu-id="8f337-105">정수 계열 값의 비트 논리 연산을 수행할 수도 이러한 연산자 중 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-105">Some of these operators can also perform bitwise logical operations on integral values.</span></span>  
  
## <a name="unary-logical-operator"></a><span data-ttu-id="8f337-106">단항 논리 연산자</span><span class="sxs-lookup"><span data-stu-id="8f337-106">Unary Logical Operator</span></span>  
 <span data-ttu-id="8f337-107">[Not 연산자](../../../../visual-basic/language-reference/operators/not-operator.md) 논리 수행 *부정* 에 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-107">The [Not Operator](../../../../visual-basic/language-reference/operators/not-operator.md) performs logical *negation* on a `Boolean` expression.</span></span> <span data-ttu-id="8f337-108">피연산자의 논리적 반대를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-108">It yields the logical opposite of its operand.</span></span> <span data-ttu-id="8f337-109">식이 계산 되는 경우 `True`, 다음 `Not` 반환 `False`식이 계산 되는 경우; `False`, 다음 `Not` 반환 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-109">If the expression evaluates to `True`, then `Not` returns `False`; if the expression evaluates to `False`, then `Not` returns `True`.</span></span> <span data-ttu-id="8f337-110">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#77](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_1.vb)]  
  
## <a name="binary-logical-operators"></a><span data-ttu-id="8f337-111">이진 논리 연산자</span><span class="sxs-lookup"><span data-stu-id="8f337-111">Binary Logical Operators</span></span>  
 <span data-ttu-id="8f337-112">[및 연산자](../../../../visual-basic/language-reference/operators/and-operator.md) 논리 수행 *함께* 두 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-112">The [And Operator](../../../../visual-basic/language-reference/operators/and-operator.md) performs logical *conjunction* on two `Boolean` expressions.</span></span> <span data-ttu-id="8f337-113">두 식이 모두 `True`, 다음 `And` 반환 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-113">If both expressions evaluate to `True`, then `And` returns `True`.</span></span> <span data-ttu-id="8f337-114">식 중 하나 이상 계산 되 면 `False`, 다음 `And` 반환 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-114">If at least one of the expressions evaluates to `False`, then `And` returns `False`.</span></span>  
  
 <span data-ttu-id="8f337-115">[또는 연산자](../../../../visual-basic/language-reference/operators/or-operator.md) 논리 수행 *분리* 또는 *포함* 두 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-115">The [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) performs logical *disjunction* or *inclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="8f337-116">두 식 중 하나가 경우 `True`, 이거나 두 식이 `True`, 다음 `Or` 반환 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-116">If either expression evaluates to `True`, or both evaluate to `True`, then `Or` returns `True`.</span></span> <span data-ttu-id="8f337-117">두 식이 모두 경우 `True`, `Or` 반환 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-117">If neither expression evaluates to `True`, `Or` returns `False`.</span></span>  
  
 <span data-ttu-id="8f337-118">[Xor 연산자](../../../../visual-basic/language-reference/operators/xor-operator.md) 논리 수행 *제외* 두 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-118">The [Xor Operator](../../../../visual-basic/language-reference/operators/xor-operator.md) performs logical *exclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="8f337-119">정확히 하나의 식이 `True`, 두만 `Xor` 반환 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-119">If exactly one expression evaluates to `True`, but not both, `Xor` returns `True`.</span></span> <span data-ttu-id="8f337-120">두 식이 모두 `True` 이거나 두 식이 `False`, `Xor` 반환 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-120">If both expressions evaluate to `True` or both evaluate to `False`, `Xor` returns `False`.</span></span>  
  
 <span data-ttu-id="8f337-121">다음 예제는 `And`, `Or`, 및 `Xor` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-121">The following example illustrates the `And`, `Or`, and `Xor` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#78](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_2.vb)]  
  
## <a name="short-circuiting-logical-operations"></a><span data-ttu-id="8f337-122">논리 연산자를 단락 (short-circuiting)</span><span class="sxs-lookup"><span data-stu-id="8f337-122">Short-Circuiting Logical Operations</span></span>  
 <span data-ttu-id="8f337-123">[AndAlso 연산자](../../../../visual-basic/language-reference/operators/andalso-operator.md) 매우 비슷합니다는 `And` 연산자를 두 개에서 한 논리 결합을 수행 한다는 점에서 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-123">The [AndAlso Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md) is very similar to the `And` operator, in that it also performs logical conjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="8f337-124">둘 사이의 주요 차이점은 `AndAlso` 유효 *단락 (short-circuiting)* 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-124">The key difference between the two is that `AndAlso` exhibits *short-circuiting* behavior.</span></span> <span data-ttu-id="8f337-125">경우에 첫 번째 식은 `AndAlso` 식이 `False`, 최종 결과 변경할 수 있기 때문에 두 번째 식은 평가 되지 됩니다 및 `AndAlso` 반환 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-125">If the first expression in an `AndAlso` expression evaluates to `False`, then the second expression is not evaluated because it cannot alter the final result, and `AndAlso` returns `False`.</span></span>  
  
 <span data-ttu-id="8f337-126">마찬가지로,는 [OrElse 연산자](../../../../visual-basic/language-reference/operators/orelse-operator.md) 두에 논리 분리를 단락 수행 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-126">Similarly, the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md) performs short-circuiting logical disjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="8f337-127">경우에 첫 번째 식은 `OrElse` 식이 `True`, 최종 결과 변경할 수 있기 때문에 두 번째 식은 평가 되지 됩니다 및 `OrElse` 반환 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-127">If the first expression in an `OrElse` expression evaluates to `True`, then the second expression is not evaluated because it cannot alter the final result, and `OrElse` returns `True`.</span></span>  
  
### <a name="short-circuiting-trade-offs"></a><span data-ttu-id="8f337-128">상충 관계를 단락 (short-circuiting)</span><span class="sxs-lookup"><span data-stu-id="8f337-128">Short-Circuiting Trade-Offs</span></span>  
 <span data-ttu-id="8f337-129">단락 (short-circuiting) 하지 논리 작업의 결과 변경할 수 없는 식을 평가 하 여 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-129">Short-circuiting can improve performance by not evaluating an expression that cannot alter the result of the logical operation.</span></span> <span data-ttu-id="8f337-130">그러나 해당 식을 추가 작업을 수행 하는 경우 이러한 작업을 건너뜁니다 단락 (short-circuiting).</span><span class="sxs-lookup"><span data-stu-id="8f337-130">However, if that expression performs additional actions, short-circuiting skips those actions.</span></span> <span data-ttu-id="8f337-131">예를 들어, 식에 대 한 호출을 포함 하는 경우는 `Function` 프로시저, 식은 short-circuited, 및에 추가 코드가 포함 된 경우 프로시저가 호출 되지 않습니다는 `Function` 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-131">For example, if the expression includes a call to a `Function` procedure, that procedure is not called if the expression is short-circuited, and any additional code contained in the `Function` does not run.</span></span> <span data-ttu-id="8f337-132">따라서 함수 가끔씩만 실행할 수 있으며 올바르게 테스트 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-132">Therefore, the function might run only occasionally, and might not be tested correctly.</span></span> <span data-ttu-id="8f337-133">프로그램 논리의 코드에 따라 달라질 수 있습니다는 `Function`합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-133">Or the program logic might depend on the code in the `Function`.</span></span>  
  
 <span data-ttu-id="8f337-134">다음 예제에서는 차이점을 보여 줍니다. `And`, `Or`, 및 단락 대응 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-134">The following example illustrates the difference between `And`, `Or`, and their short-circuiting counterparts.</span></span>  
  
 [!code-vb[VbVbalrOperators#81](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_3.vb)]  
  
 [!code-vb[VbVbalrOperators#80](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_4.vb)]  
  
 [!code-vb[VbVbalrOperators#79](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/logical-and-bitwise-operators_5.vb)]  
  
 <span data-ttu-id="8f337-135">앞의 예제에서 몇 가지 중요 한 코드 내 `checkIfValid()` 호출이 short-circuited 될 때 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-135">In the preceding example, note that some important code inside `checkIfValid()` does not run when the call is short-circuited.</span></span> <span data-ttu-id="8f337-136">첫 번째 `If` 문 호출 `checkIfValid()` 있지만 `12 > 45` 반환 `False`때문에, `And` 단락 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-136">The first `If` statement calls `checkIfValid()` even though `12 > 45` returns `False`, because `And` does not short-circuit.</span></span> <span data-ttu-id="8f337-137">두 번째 `If` 호출 하지 않습니다 `checkIfValid()`때문에 때 `12 > 45` 반환 `False`, `AndAlso` short-circuits 두 번째 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-137">The second `If` statement does not call `checkIfValid()`, because when `12 > 45` returns `False`, `AndAlso` short-circuits the second expression.</span></span> <span data-ttu-id="8f337-138">세 번째 `If` 문 호출 `checkIfValid()` 있지만 `12 < 45` 반환 `True`때문에, `Or` 단락 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-138">The third `If` statement calls `checkIfValid()` even though `12 < 45` returns `True`, because `Or` does not short-circuit.</span></span> <span data-ttu-id="8f337-139">네 번째 `If` 호출 하지 않습니다 `checkIfValid()`때문에 때 `12 < 45` 반환 `True`, `OrElse` short-circuits 두 번째 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-139">The fourth `If` statement does not call `checkIfValid()`, because when `12 < 45` returns `True`, `OrElse` short-circuits the second expression.</span></span>  
  
## <a name="bitwise-operations"></a><span data-ttu-id="8f337-140">비트 연산</span><span class="sxs-lookup"><span data-stu-id="8f337-140">Bitwise Operations</span></span>  
 <span data-ttu-id="8f337-141">비트 연산 (밑 2) 이진 형식으로 두 정수 계열 값을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-141">Bitwise operations evaluate two integral values in binary (base 2) form.</span></span> <span data-ttu-id="8f337-142">해당 위치의 비트를 비교 하 고 비교를 기반으로 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-142">They compare the bits at corresponding positions and then assign values based on the comparison.</span></span> <span data-ttu-id="8f337-143">다음 예제는 `And` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-143">The following example illustrates the `And` operator.</span></span>  
  
 [!code-vb[VbVbalrConcepts#2](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/logical-and-bitwise-operators_6.vb)]  
  
 <span data-ttu-id="8f337-144">값을 설정 하는 앞의 예제 `x` 1입니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-144">The preceding example sets the value of `x` to 1.</span></span> <span data-ttu-id="8f337-145">이 다음과 같은 상황이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-145">This happens for the following reasons:</span></span>  
  
-   <span data-ttu-id="8f337-146">값은 이진으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-146">The values are treated as binary:</span></span>  
  
     <span data-ttu-id="8f337-147">이진 형식으로 3 011 =</span><span class="sxs-lookup"><span data-stu-id="8f337-147">3 in binary form = 011</span></span>  
  
     <span data-ttu-id="8f337-148">이진 형식으로 5 = 101</span><span class="sxs-lookup"><span data-stu-id="8f337-148">5 in binary form = 101</span></span>  
  
-   <span data-ttu-id="8f337-149">`And` 연산자는 한 번에 하나의 이진 위치 (비트)에서 이진 표현을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-149">The `And` operator compares the binary representations, one binary position (bit) at a time.</span></span> <span data-ttu-id="8f337-150">지정된 된 위치에서 두 비트가 모두 1 이면 1 결과의 해당 위치에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-150">If both bits at a given position are 1, then a 1 is placed in that position in the result.</span></span> <span data-ttu-id="8f337-151">두 비트 중 하나가 0 이면 0은 결과에서 해당 위치에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-151">If either bit is 0, then a 0 is placed in that position in the result.</span></span> <span data-ttu-id="8f337-152">앞의 예에서이 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-152">In the preceding example this works out as follows:</span></span>  
  
     <span data-ttu-id="8f337-153">011 (이진 형식으로 3)</span><span class="sxs-lookup"><span data-stu-id="8f337-153">011 (3 in binary form)</span></span>  
  
     <span data-ttu-id="8f337-154">101 (5의 이진 형식)</span><span class="sxs-lookup"><span data-stu-id="8f337-154">101 (5 in binary form)</span></span>  
  
     <span data-ttu-id="8f337-155">001 (이진 형식으로 결과)</span><span class="sxs-lookup"><span data-stu-id="8f337-155">001 (The result, in binary form)</span></span>  
  
-   <span data-ttu-id="8f337-156">결과 10 진수로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-156">The result is treated as decimal.</span></span> <span data-ttu-id="8f337-157">001 값은 1의 이진 표현 이므로 `x` = 1입니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-157">The value 001 is the binary representation of 1, so `x` = 1.</span></span>  
  
 <span data-ttu-id="8f337-158">비트 `Or` 연산도 비슷합니다 제외 하 고 비교 비트 중 하나 또는 모두 1 이면 결과 비트는 1이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-158">The bitwise `Or` operation is similar, except that a 1 is assigned to the result bit if either or both of the compared bits is 1.</span></span> <span data-ttu-id="8f337-159">`Xor`1 (멤버나) 비교 비트 중 정확히 하나의 이면 결과 비트에 1을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-159">`Xor` assigns a 1 to the result bit if exactly one of the compared bits (not both) is 1.</span></span> <span data-ttu-id="8f337-160">`Not`단일 피연산자를 사용 하 고 부호 비트를 포함 하 여 모든 비트를을 반전 하 고 결과에 해당 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-160">`Not` takes a single operand and inverts all the bits, including the sign bit, and assigns that value to the result.</span></span> <span data-ttu-id="8f337-161">즉, 부호 있는 양수, `Not` 항상 음수 값을 반환 하 고 음수 값에 대 한 `Not` 항상 양수 또는 0 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-161">This means that for signed positive numbers, `Not` always returns a negative value, and for negative numbers, `Not` always returns a positive or zero value.</span></span>  
  
 <span data-ttu-id="8f337-162">`AndAlso` 및 `OrElse` 연산자는 비트 연산을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-162">The `AndAlso` and `OrElse` operators do not support bitwise operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f337-163">비트 연산에서 정수 계열 형식 에서만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-163">Bitwise operations can be performed on integral types only.</span></span> <span data-ttu-id="8f337-164">부동 소수점 값은 비트 연산을 수행 하려면 먼저 정수 계열 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f337-164">Floating-point values must be converted to integral types before bitwise operation can proceed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f337-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f337-165">See Also</span></span>  
 [<span data-ttu-id="8f337-166">논리/비트 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f337-166">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="8f337-167">부울 식</span><span class="sxs-lookup"><span data-stu-id="8f337-167">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="8f337-168">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="8f337-168">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="8f337-169">Visual Basic의 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="8f337-169">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="8f337-170">Visual Basic의 연결 연산자</span><span class="sxs-lookup"><span data-stu-id="8f337-170">Concatenation Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [<span data-ttu-id="8f337-171">연산자의 효율적 결합</span><span class="sxs-lookup"><span data-stu-id="8f337-171">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
