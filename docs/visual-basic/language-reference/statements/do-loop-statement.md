---
title: "Do...Loop 문(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- "conditional statements [Visual Basic], Do�Loop"
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- "loop structures [Visual Basic], Do�Loop statements"
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
caps.latest.revision: "37"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 79d25dce963f383a84b56ce2c9b600fc2d5a7937
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="bd4c5-102">Do...Loop 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd4c5-102">Do...Loop Statement (Visual Basic)</span></span>
<span data-ttu-id="bd4c5-103">동안 문 블록을 반복 하는 `Boolean` 조건이 `True` 조건이 있을 때까지 또는 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-103">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd4c5-104">구문</span><span class="sxs-lookup"><span data-stu-id="bd4c5-104">Syntax</span></span>  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a><span data-ttu-id="bd4c5-105">요소</span><span class="sxs-lookup"><span data-stu-id="bd4c5-105">Parts</span></span>  
  
|<span data-ttu-id="bd4c5-106">용어</span><span class="sxs-lookup"><span data-stu-id="bd4c5-106">Term</span></span>|<span data-ttu-id="bd4c5-107">정의</span><span class="sxs-lookup"><span data-stu-id="bd4c5-107">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="bd4c5-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-108">Required.</span></span> <span data-ttu-id="bd4c5-109">시작의 정의 `Do` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-109">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="bd4c5-110">`Until`를 사용하는 경우를 제외하고는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-110">Required unless `Until` is used.</span></span> <span data-ttu-id="bd4c5-111">반복 될 때까지 루프 `condition` 은 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-111">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="bd4c5-112">`While`를 사용하는 경우를 제외하고는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-112">Required unless `While` is used.</span></span> <span data-ttu-id="bd4c5-113">반복 될 때까지 루프 `condition` 은 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-113">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="bd4c5-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-114">Optional.</span></span> <span data-ttu-id="bd4c5-115">`Boolean`식입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-115">`Boolean` expression.</span></span> <span data-ttu-id="bd4c5-116">경우 `condition` 은 `Nothing`, Visual Basic로 처리 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-116">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="bd4c5-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-117">Optional.</span></span> <span data-ttu-id="bd4c5-118">동안 또는 하기 전 까지는 반복 되는 하나 이상의 문을 `condition` 은 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-118">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="bd4c5-119">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-119">Optional.</span></span> <span data-ttu-id="bd4c5-120">다음 반복으로 제어를 전달는 `Do` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-120">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="bd4c5-121">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-121">Optional.</span></span> <span data-ttu-id="bd4c5-122">밖으로 제어를 전송에서 `Do` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-122">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="bd4c5-123">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-123">Required.</span></span> <span data-ttu-id="bd4c5-124">정의 종료는 `Do` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-124">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd4c5-125">설명</span><span class="sxs-lookup"><span data-stu-id="bd4c5-125">Remarks</span></span>  
 <span data-ttu-id="bd4c5-126">사용 하 여 한 `Do...Loop` 조건이 충족 될 때까지 여러 번 무한히 문 집합을 반복할 때 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-126">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="bd4c5-127">문을 횟수 만큼 반복 하려는 경우는 [에 대 한... 다음 문](../../../visual-basic/language-reference/statements/for-next-statement.md) 일반적으로 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-127">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="bd4c5-128">사용할 수 있습니다 `While` 또는 `Until` 지정 하려면 `condition`, 둘 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-128">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="bd4c5-129">테스트할 수 `condition` 시작 부분이 나 루프의 끝에만 한 번입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-129">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="bd4c5-130">테스트 하는 경우 `condition` 루프가 시작 될 때 (에 `Do` 문), 루프가 한 번도 실행 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-130">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="bd4c5-131">루프의 끝에서 테스트 하는 경우 (에 `Loop` 문), 루프는 항상 한 번 이상 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-131">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="bd4c5-132">두 값의 비교에서 조건 일반적으로 발생 하지만 모든 식으로 계산 되는 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값 (`True` 또는 `False`).</span><span class="sxs-lookup"><span data-stu-id="bd4c5-132">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="bd4c5-133">예: 숫자 형식으로 변환 된 다른 데이터 형식의 값을 포함이 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-133">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="bd4c5-134">중첩할 수 `Do` 서로 배치 하 여 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-134">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="bd4c5-135">서로 다른 제어 구조가 서로 중첩할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-135">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="bd4c5-136">자세한 내용은 참조 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-136">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd4c5-137">`Do...Loop` 구조 보다 더 많은 유연성을 제공 된 [동안... End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md) 하면 루프를 끝내 여부를 결정할 수 있기 때문에 때 `condition` 중지 되 `True` 되거나 먼저 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-137">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="bd4c5-138">테스트할 수도 있습니다 `condition` 시작 부분이 나 루프의 끝에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-138">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="bd4c5-139">종료 안 함</span><span class="sxs-lookup"><span data-stu-id="bd4c5-139">Exit Do</span></span>  
 <span data-ttu-id="bd4c5-140">[Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) 문을 종료 하는 다른 방법으로 제공할 수는 `Do…Loop`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-140">The [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="bd4c5-141">`Exit Do`뒤에 오는 문으로 제어를 즉시 전달는 `Loop` 문.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-141">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="bd4c5-142">`Exit Do`일부 조건이 계산에 사용 예는 대개는 `If...Then...Else` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-142">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="bd4c5-143">불필요 하거나 잘못 된 값 이나 종료 요청 같이 계속 반복할 수 있게 해 주는 조건을 발견 하면 루프를 끝낼 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-143">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="bd4c5-144">용도 중 하나 `Exit Do` 를 일으킬 수 있는 조건에 대해 테스트 하는 *무한 루프*, 상태가 대형 또는 무한도 가능 여러 번 실행 될 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-144">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="bd4c5-145">사용할 수 있습니다 `Exit Do` 루프를 이스케이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-145">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="bd4c5-146">개수에 관계 없이 포함할 수 있습니다 `Exit Do` 의 아무 곳 이나 문에서 `Do…Loop`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-146">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="bd4c5-147">사용할 경우 내에 중첩 `Do` 루프, `Exit Do` 제어 하며 다음 상위 수준의 중첩이 가장 안쪽 루프 밖으로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-147">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd4c5-148">예제</span><span class="sxs-lookup"><span data-stu-id="bd4c5-148">Example</span></span>  
 <span data-ttu-id="bd4c5-149">다음 예제에서는 루프에서 계속 실행 될 때까지 `index` 변수 10 보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="bd4c5-150">`Until` 절 루프의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-150">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="bd4c5-151">예제</span><span class="sxs-lookup"><span data-stu-id="bd4c5-151">Example</span></span>  
 <span data-ttu-id="bd4c5-152">다음 예제에서는 한 `While` 절 대신는 `Until` 절 및 `condition` 끝 대신 루프의 시작 부분에서 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-152">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="bd4c5-153">예제</span><span class="sxs-lookup"><span data-stu-id="bd4c5-153">Example</span></span>  
 <span data-ttu-id="bd4c5-154">다음 예에서 `condition` 루프를 중지 때는 `index` 변수는 100을 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-154">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="bd4c5-155">그러나 `If` 루프에 문을 지정 하면는 `Exit Do` 문의 인덱스 변수는 10 보다 큰 경우에 루프를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-155">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="bd4c5-156">예제</span><span class="sxs-lookup"><span data-stu-id="bd4c5-156">Example</span></span>  
 <span data-ttu-id="bd4c5-157">다음 예제에서는 텍스트 파일에 있는 모든 줄을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-157">The following example reads all lines in a text file.</span></span> <span data-ttu-id="bd4c5-158"><xref:System.IO.File.OpenText%2A> 메서드는 파일을 열고 반환는 <xref:System.IO.StreamReader> 는 문자를 읽는 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-158">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="bd4c5-159">에 `Do...Loop` 조건은 <xref:System.IO.StreamReader.Peek%2A> 의 메서드는 `StreamReader` 추가 문자가 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd4c5-159">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/do-loop-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bd4c5-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd4c5-160">See Also</span></span>  
 [<span data-ttu-id="bd4c5-161">루프 구조</span><span class="sxs-lookup"><span data-stu-id="bd4c5-161">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="bd4c5-162">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="bd4c5-162">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="bd4c5-163">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="bd4c5-163">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [<span data-ttu-id="bd4c5-164">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="bd4c5-164">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="bd4c5-165">Exit 문</span><span class="sxs-lookup"><span data-stu-id="bd4c5-165">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="bd4c5-166">While...End While 문</span><span class="sxs-lookup"><span data-stu-id="bd4c5-166">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
