---
title: "While...End While 문(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5f831f233eaa4f1c38d56f3a89bda9b0cf1bccaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="b71b9-102">While...End While 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b71b9-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="b71b9-103">지정한 조건이으로 일련의 문 실행 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b71b9-104">구문</span><span class="sxs-lookup"><span data-stu-id="b71b9-104">Syntax</span></span>  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="b71b9-105">요소</span><span class="sxs-lookup"><span data-stu-id="b71b9-105">Parts</span></span>  
  
|<span data-ttu-id="b71b9-106">용어</span><span class="sxs-lookup"><span data-stu-id="b71b9-106">Term</span></span>|<span data-ttu-id="b71b9-107">정의</span><span class="sxs-lookup"><span data-stu-id="b71b9-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="b71b9-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b71b9-108">Required.</span></span> <span data-ttu-id="b71b9-109">`Boolean`식입니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-109">`Boolean` expression.</span></span> <span data-ttu-id="b71b9-110">경우 `condition` 은 `Nothing`, Visual Basic로 처리 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="b71b9-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-111">Optional.</span></span> <span data-ttu-id="b71b9-112">하나 이상의 문 다음 `While`, 때마다 실행 `condition` 은 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="b71b9-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-113">Optional.</span></span> <span data-ttu-id="b71b9-114">다음 반복으로 제어를 전달는 `While` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="b71b9-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-115">Optional.</span></span> <span data-ttu-id="b71b9-116">밖으로 제어를 전송에서 `While` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="b71b9-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b71b9-117">Required.</span></span> <span data-ttu-id="b71b9-118">`While` 블록의 정의를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b71b9-119">설명</span><span class="sxs-lookup"><span data-stu-id="b71b9-119">Remarks</span></span>  
 <span data-ttu-id="b71b9-120">사용 하 여 한 `While...End While` 조건이으로 문을 번 무한히 반복 하려는 경우 구조체 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="b71b9-121">조건을 테스트 하는 위치 또는 결과 합니다 유연한이 할 것에 대 한 테스트 하려는 경우는 [수행... 문은 루프](../../../visual-basic/language-reference/statements/do-loop-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="b71b9-122">문을 횟수 만큼 반복 하려는 경우는 [에 대 한... 다음 문](../../../visual-basic/language-reference/statements/for-next-statement.md) 일반적으로 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b71b9-123">`While` 키워드는 또한는 [수행... 문은 루프](../../../visual-basic/language-reference/statements/do-loop-statement.md), [Skip While 절](../../../visual-basic/language-reference/queries/skip-while-clause.md) 및 [Take While 절](../../../visual-basic/language-reference/queries/take-while-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="b71b9-124">경우 `condition` 은 `True`모든의 `statements` 실행 될 때까지 `End While` 문이 합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="b71b9-125">돌아올 제어는 `While` 문, 및 `condition` 를 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="b71b9-126">경우 `condition` 여전히 `True`, 프로세스를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="b71b9-127">설정한 경우 `False`, 제어 뒤에 오는 문으로 전달은 `End While` 문.</span><span class="sxs-lookup"><span data-stu-id="b71b9-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="b71b9-128">`While` 문은 항상 루프를 시작 하기 전에 조건을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="b71b9-129">조건이 동안 계속 반복 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="b71b9-130">경우 `condition` 은 `False` 루프 처음 입력할 때 실행 되는 한 번도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="b71b9-131">`condition` 일반적으로 두 값의 비교 결과로 계산 되는 식일 수는 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값 (`True` 또는 `False`).</span><span class="sxs-lookup"><span data-stu-id="b71b9-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="b71b9-132">이 식은로 변환 된 하는 숫자 형식과 같은 다른 데이터 형식의 값을 포함할 수 있습니다 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="b71b9-133">중첩할 수 `While` 서로 배치 하 여 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="b71b9-134">또한 다른 종류의 제어 구조를 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="b71b9-135">자세한 내용은 참조 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="b71b9-136">종료 하는 동안</span><span class="sxs-lookup"><span data-stu-id="b71b9-136">Exit While</span></span>  
 <span data-ttu-id="b71b9-137">[종료 동안](../../../visual-basic/language-reference/statements/exit-statement.md) 문을 종료 하는 다른 방법은 제공할 수는 `While` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="b71b9-138">`Exit While`바로 뒤에 오는 문으로 제어를 전송에서 `End While` 문.</span><span class="sxs-lookup"><span data-stu-id="b71b9-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="b71b9-139">일반적으로 사용 `Exit While` 일부 조건이 계산 된 후 (예를 들어 한 `If...Then...Else` 구조).</span><span class="sxs-lookup"><span data-stu-id="b71b9-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="b71b9-140">불필요 하거나 잘못 된 값 이나 종료 요청 같이 계속 반복할 수 있게 해 주는 조건을 발견 하면 루프를 끝낼 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="b71b9-141">사용할 수 있습니다 `Exit While` 를 일으킬 수 있는 조건에 대 한 테스트는 *무한 루프*, 상태가 매우 크거나 무한도 가능 여러 번 실행 될 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="b71b9-142">사용할 수 있습니다 `Exit While` 루프를 이스케이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="b71b9-143">개수에 관계 없이 배치할 수 `Exit While` 의 아무 곳 이나 문에서 `While` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="b71b9-144">사용할 경우 내에 중첩 `While` 루프, `Exit While` 제어 하며 다음 상위 수준의 중첩이 가장 안쪽 루프 밖으로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="b71b9-145">`Continue While` 문은 루프의 다음 반복으로 즉시 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="b71b9-146">자세한 내용은 참조 [Continue 문을](../../../visual-basic/language-reference/statements/continue-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b71b9-147">예제</span><span class="sxs-lookup"><span data-stu-id="b71b9-147">Example</span></span>  
 <span data-ttu-id="b71b9-148">다음 예제에서는 루프에서 계속 실행 될 때까지 `index` 변수 10 보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="b71b9-149">예제</span><span class="sxs-lookup"><span data-stu-id="b71b9-149">Example</span></span>  
 <span data-ttu-id="b71b9-150">다음 예제에서는 `Continue While` 및 `Exit While` 문.</span><span class="sxs-lookup"><span data-stu-id="b71b9-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="b71b9-151">예제</span><span class="sxs-lookup"><span data-stu-id="b71b9-151">Example</span></span>  
 <span data-ttu-id="b71b9-152">다음 예제에서는 텍스트 파일에 있는 모든 줄을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="b71b9-153"><xref:System.IO.File.OpenText%2A> 메서드는 파일을 열고 반환는 <xref:System.IO.StreamReader> 는 문자를 읽는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="b71b9-154">에 `While` 조건은 <xref:System.IO.StreamReader.Peek%2A> 의 메서드는 `StreamReader` 파일에 추가 문자가 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b71b9-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b71b9-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b71b9-155">See Also</span></span>  
 [<span data-ttu-id="b71b9-156">루프 구조</span><span class="sxs-lookup"><span data-stu-id="b71b9-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="b71b9-157">Do...Loop 문</span><span class="sxs-lookup"><span data-stu-id="b71b9-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="b71b9-158">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="b71b9-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="b71b9-159">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b71b9-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [<span data-ttu-id="b71b9-160">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="b71b9-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="b71b9-161">Exit 문</span><span class="sxs-lookup"><span data-stu-id="b71b9-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="b71b9-162">Continue 문</span><span class="sxs-lookup"><span data-stu-id="b71b9-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
