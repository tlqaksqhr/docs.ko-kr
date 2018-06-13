---
title: For...Next 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: 8c54189499b7d5b52cf93b4a0ae6cc47356bf57e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605331"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="b9560-102">For...Next 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9560-102">For...Next Statement (Visual Basic)</span></span>
<span data-ttu-id="b9560-103">문 그룹을 지정한 횟수 만큼을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-103">Repeats a group of statements a specified number of times.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9560-104">구문</span><span class="sxs-lookup"><span data-stu-id="b9560-104">Syntax</span></span>  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## <a name="parts"></a><span data-ttu-id="b9560-105">요소</span><span class="sxs-lookup"><span data-stu-id="b9560-105">Parts</span></span>  
  
|<span data-ttu-id="b9560-106">파트</span><span class="sxs-lookup"><span data-stu-id="b9560-106">Part</span></span>|<span data-ttu-id="b9560-107">설명</span><span class="sxs-lookup"><span data-stu-id="b9560-107">Description</span></span>|  
|----------|-----------------|  
|`counter`|<span data-ttu-id="b9560-108">에 필요한는 `For` 문.</span><span class="sxs-lookup"><span data-stu-id="b9560-108">Required in the `For` statement.</span></span> <span data-ttu-id="b9560-109">숫자 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-109">Numeric variable.</span></span> <span data-ttu-id="b9560-110">루프 제어 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-110">The control variable for the loop.</span></span> <span data-ttu-id="b9560-111">자세한 내용은 참조 [카운터 인수](#BKMK_Counter) 이 항목의 뒷부분에 나오는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`datatype`|<span data-ttu-id="b9560-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-112">Optional.</span></span> <span data-ttu-id="b9560-113">데이터 형식이 `counter`합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-113">Data type of `counter`.</span></span> <span data-ttu-id="b9560-114">자세한 내용은 참조 [카운터 인수](#BKMK_Counter) 이 항목의 뒷부분에 나오는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`start`|<span data-ttu-id="b9560-115">필수.</span><span class="sxs-lookup"><span data-stu-id="b9560-115">Required.</span></span> <span data-ttu-id="b9560-116">숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-116">Numeric expression.</span></span> <span data-ttu-id="b9560-117">`counter`의 초기 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-117">The initial value of `counter`.</span></span>|  
|`end`|<span data-ttu-id="b9560-118">필수.</span><span class="sxs-lookup"><span data-stu-id="b9560-118">Required.</span></span> <span data-ttu-id="b9560-119">숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-119">Numeric expression.</span></span> <span data-ttu-id="b9560-120">최종 값 `counter`합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-120">The final value of `counter`.</span></span>|  
|`step`|<span data-ttu-id="b9560-121">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-121">Optional.</span></span> <span data-ttu-id="b9560-122">숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-122">Numeric expression.</span></span> <span data-ttu-id="b9560-123">양입니다 `counter` 루프가 반복 될 때마다 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-123">The amount by which `counter` is incremented each time through the loop.</span></span>|  
|`statements`|<span data-ttu-id="b9560-124">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-124">Optional.</span></span> <span data-ttu-id="b9560-125">사이 하나 이상의 문이 `For` 및 `Next` 지정한 횟수 만큼을 실행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|  
|`Continue For`|<span data-ttu-id="b9560-126">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-126">Optional.</span></span> <span data-ttu-id="b9560-127">다음 루프 반복으로 제어를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-127">Transfers control to the next loop iteration.</span></span>|  
|`Exit For`|<span data-ttu-id="b9560-128">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-128">Optional.</span></span> <span data-ttu-id="b9560-129">밖으로 제어를 전송에서 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-129">Transfers control out of the `For` loop.</span></span>|  
|`Next`|<span data-ttu-id="b9560-130">필수.</span><span class="sxs-lookup"><span data-stu-id="b9560-130">Required.</span></span> <span data-ttu-id="b9560-131">정의 종료는 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-131">Terminates the definition of the `For` loop.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="b9560-132">`To` 카운터에 대 한 범위를 지정 하려면이 문을 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="b9560-133">이 키워드를 사용할 수도 있습니다는 [선택... Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md) 및 배열 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-133">You can also use this keyword in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="b9560-134">배열 선언에 대 한 자세한 내용은 참조 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-134">For more information about array declarations, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="simple-examples"></a><span data-ttu-id="b9560-135">간단한 예</span><span class="sxs-lookup"><span data-stu-id="b9560-135">Simple Examples</span></span>  
 <span data-ttu-id="b9560-136">사용 된 `For`... `Next` 횟수 만큼 문 집합을 반복할 때 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>  
  
 <span data-ttu-id="b9560-137">다음 예제에서는 `index` 변수 값이 1로 시작 하 고이 값의 끝에서 끝나는 루프의 각 반복 증가 `index` 5에 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>  
  
 [!code-vb[VbVbalrStatements#111](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_1.vb)]  
  
 <span data-ttu-id="b9560-138">다음 예제에서는 `number` 변수 2에서 시작 하 고 값의 끝에서 끝나는 루프의 각 반복에서 0.25에 의해 감소 `number` 0에 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="b9560-139">`Step` 의 인수 `-.25` 루프의 각 반복에서 0.25 하 여 값을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#112](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_2.vb)]  
  
> [!TIP]
>  <span data-ttu-id="b9560-140">A [동안... While 문 종료](../../../visual-basic/language-reference/statements/while-end-while-statement.md) 또는 [수행... Loop 문과](../../../visual-basic/language-reference/statements/do-loop-statement.md) 때 알 수 없는 사전에 루프에서 문을 실행 횟수 효과적으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-140">A [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) or [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="b9560-141">그러나 아는 경우 루프는 특정 횟수 만큼 실행 된 `For`... `Next` 루프는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="b9560-142">루프를 처음 입력할 때의 반복 횟수를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-142">You determine the number of iterations when you first enter the loop.</span></span>  
  
## <a name="nesting-loops"></a><span data-ttu-id="b9560-143">중첩 루프</span><span class="sxs-lookup"><span data-stu-id="b9560-143">Nesting Loops</span></span>  
 <span data-ttu-id="b9560-144">중첩할 수 `For` 서로 배치 하 여 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="b9560-145">다음 예제에서는 중첩 된 `For`... `Next` 단계 값이 있는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="b9560-146">외부 루프의 루프의 각 반복에 대해 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="b9560-147">내부 루프 루프의 각 반복에 대해 루프 카운터 변수를 감소 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#113](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_3.vb)]  
  
 <span data-ttu-id="b9560-148">중첩 루프를 각 루프는 고유 해야 `counter` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>  
  
 <span data-ttu-id="b9560-149">서로 다른 제어 구조가 서로 중첩할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="b9560-150">자세한 내용은 참조 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-150">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-for-and-continue-for"></a><span data-ttu-id="b9560-151">에 대 한 종료 하 고 계속 하기</span><span class="sxs-lookup"><span data-stu-id="b9560-151">Exit For and Continue For</span></span>  
 <span data-ttu-id="b9560-152">`Exit For` 문을 즉시 끝내는 `For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="b9560-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="b9560-153">루프 및 전송 컨트롤 뒤에 오는 문에 `Next` 문.</span><span class="sxs-lookup"><span data-stu-id="b9560-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>  
  
 <span data-ttu-id="b9560-154">`Continue For` 문은 제어 즉시 루프의 다음 반복으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="b9560-155">자세한 내용은 참조 [Continue 문을](../../../visual-basic/language-reference/statements/continue-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-155">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
 <span data-ttu-id="b9560-156">다음 예제에서는 `Continue For` 및 `Exit For` 문.</span><span class="sxs-lookup"><span data-stu-id="b9560-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#115](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_4.vb)]  
  
 <span data-ttu-id="b9560-157">개수에 관계 없이 넣을 수 `Exit For` 의 문에서 `For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="b9560-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="b9560-158">루프입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-158">loop.</span></span> <span data-ttu-id="b9560-159">사용할 경우 내에 중첩 `For`중...`Next`</span><span class="sxs-lookup"><span data-stu-id="b9560-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="b9560-160">루프, `Exit For` 가장 안쪽 루프를 끝내 고 중첩 다음으로 높은 수준으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="b9560-161">`Exit For` 일부 조건 평가 후에 주로 사용 됩니다 (예를 들어 한 `If`... `Then`... `Else` 구조).</span><span class="sxs-lookup"><span data-stu-id="b9560-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="b9560-162">사용 하려는 경우도 `Exit For` 다음 조건에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-162">You might want to use `Exit For` for the following conditions:</span></span>  
  
-   <span data-ttu-id="b9560-163">계속 반복은 불필요 하거나 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="b9560-164">잘못 된 값 이나 종료 요청에는이 조건을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-164">An erroneous value or a termination request might create this condition.</span></span>  
  
-   <span data-ttu-id="b9560-165">A `Try`... `Catch`... `Finally` 문이 된 예외를 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="b9560-166">사용할 수 있습니다 `Exit For` 의 끝에는 `Finally` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-166">You might use `Exit For` at the end of the `Finally` block.</span></span>  
  
-   <span data-ttu-id="b9560-167">크거나 무한도 가능 여러 번 실행 될 수 있는 루프는 무한 루프를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="b9560-168">사용할 수 있습니다 이러한 조건을 감지 하면 `Exit For` 루프를 이스케이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="b9560-169">자세한 내용은 참조 [수행... 문은 루프](../../../visual-basic/language-reference/statements/do-loop-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-169">For more information, see [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="b9560-170">기술 구현</span><span class="sxs-lookup"><span data-stu-id="b9560-170">Technical Implementation</span></span>  
 <span data-ttu-id="b9560-171">경우는 `For`... `Next` 루프가 시작, Visual Basic 조건이 `start`, `end`, 및 `step`합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="b9560-172">이 다시 할당에만 이러한 값을 평가 하는 Visual Basic `start` 를 `counter`합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="b9560-173">문 전에 블록 실행의 Visual Basic 비교 `counter` 를 `end`합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="b9560-174">경우 `counter` 보다 크면 이미는 `end` 값 (또는 더 작은 경우 `step` 가 음수), `For` 루프가 종료 되 고 제어를 다음 문으로 전달은 `Next` 문.</span><span class="sxs-lookup"><span data-stu-id="b9560-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="b9560-175">그렇지 않은 경우 문 블록이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-175">Otherwise, the statement block runs.</span></span>  
  
 <span data-ttu-id="b9560-176">Visual Basic 발생할 때마다는 `Next` 문 수를 늘리면 `counter` 여 `step` 돌아갑니다는 `For` 문.</span><span class="sxs-lookup"><span data-stu-id="b9560-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="b9560-177">비교 다시 `counter` 를 `end`, 다시 블록을 실행 하거나 결과 따라 루프를 종료 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="b9560-178">까지이 프로세스를 계속 `counter` 전달 `end` 또는 `Exit For` 문이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>  
  
 <span data-ttu-id="b9560-179">반복 될 때까지 중단 되지 않는 `counter` 경과 `end`합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="b9560-180">경우 `counter` 같으면 `end`, 루프가 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="b9560-181">블록을 실행할지 여부를 결정 하는 비교는 `counter`  <=  `end` 경우 `step` 가 양수 및 `counter`  >=  `end` 경우 `step` 음수입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>  
  
 <span data-ttu-id="b9560-182">값을 변경 하면 `counter` 루프 내부에 있는 동안 코드를 읽고 디버깅 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="b9560-183">값을 변경 `start`, `end`, 또는 `step` 루프를 먼저 입력 하는 경우 확인 된 반복 값에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>  
  
 <span data-ttu-id="b9560-184">루프를 중첩 하는 경우 컴파일러에서 오류를 알립니다 발견 하는 경우는 `Next` 하기 전에 외부 중첩 수준의 문이 `Next` 내부 수준의 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="b9560-185">하지만, 컴파일러가 검색할 수 있습니다이 지정 하는 경우에 중복 오류 `counter` 에 모든 `Next` 문.</span><span class="sxs-lookup"><span data-stu-id="b9560-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>  
  
### <a name="step-argument"></a><span data-ttu-id="b9560-186">단계 인수</span><span class="sxs-lookup"><span data-stu-id="b9560-186">Step Argument</span></span>  
 <span data-ttu-id="b9560-187">값 `step` 양수 또는 음수가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="b9560-188">이 매개 변수는 다음 표에 따라 루프 처리를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-188">This parameter determines loop processing according to the following table:</span></span>  
  
|<span data-ttu-id="b9560-189">**단계 값**</span><span class="sxs-lookup"><span data-stu-id="b9560-189">**Step value**</span></span>|<span data-ttu-id="b9560-190">**루프를 실행 하는 경우**</span><span class="sxs-lookup"><span data-stu-id="b9560-190">**Loop executes if**</span></span>|  
|--------------------|--------------------------|  
|<span data-ttu-id="b9560-191">양수 또는 0</span><span class="sxs-lookup"><span data-stu-id="b9560-191">Positive or zero</span></span>|`counter` <= `end`|  
|<span data-ttu-id="b9560-192">음수</span><span class="sxs-lookup"><span data-stu-id="b9560-192">Negative</span></span>|`counter` >= `end`|  
  
 <span data-ttu-id="b9560-193">기본값 `step` 는 1입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-193">The default value of `step` is 1.</span></span>  
  
###  <a name="BKMK_Counter"></a> <span data-ttu-id="b9560-194">카운터 인수</span><span class="sxs-lookup"><span data-stu-id="b9560-194">Counter Argument</span></span>  
 <span data-ttu-id="b9560-195">다음 표에서 여부 `counter` 전체 범위가 지정 된 새 지역 변수를 정의 `For…Next` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="b9560-196">이 결정에 따라 다릅니다. `datatype` 있는지 여부와 `counter` 이미 정의 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>  
  
|<span data-ttu-id="b9560-197">`datatype` 존재?</span><span class="sxs-lookup"><span data-stu-id="b9560-197">Is `datatype` present?</span></span>|<span data-ttu-id="b9560-198">`counter` 이미 정의 되어 있습니까?</span><span class="sxs-lookup"><span data-stu-id="b9560-198">Is `counter` already defined?</span></span>|<span data-ttu-id="b9560-199">결과 (여부 `counter` 전체 범위가 지정 된 새 지역 변수를 정의 `For...Next` 루프)</span><span class="sxs-lookup"><span data-stu-id="b9560-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="b9560-200">아니요</span><span class="sxs-lookup"><span data-stu-id="b9560-200">No</span></span>|<span data-ttu-id="b9560-201">예</span><span class="sxs-lookup"><span data-stu-id="b9560-201">Yes</span></span>|<span data-ttu-id="b9560-202">아니요, 때문에 `counter` 이미 정의 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="b9560-203">경우 범위 `counter` 되지 않습니다는 프로시저에 로컬인 컴파일 타임 경고 메시지가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|  
|<span data-ttu-id="b9560-204">아니요</span><span class="sxs-lookup"><span data-stu-id="b9560-204">No</span></span>|<span data-ttu-id="b9560-205">아니요</span><span class="sxs-lookup"><span data-stu-id="b9560-205">No</span></span>|<span data-ttu-id="b9560-206">예.</span><span class="sxs-lookup"><span data-stu-id="b9560-206">Yes.</span></span> <span data-ttu-id="b9560-207">데이터 형식에서 유추 됩니다는 `start`, `end`, 및 `step` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="b9560-208">형식 유추에 대 한 정보를 참조 하십시오. [Option Infer 문](../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-208">For information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>|  
|<span data-ttu-id="b9560-209">예</span><span class="sxs-lookup"><span data-stu-id="b9560-209">Yes</span></span>|<span data-ttu-id="b9560-210">예</span><span class="sxs-lookup"><span data-stu-id="b9560-210">Yes</span></span>|<span data-ttu-id="b9560-211">예, 하지만 경우에만 기존 `counter` 변수는 프로시저 밖에 서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="b9560-212">해당 변수는 별도 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-212">That variable remains separate.</span></span> <span data-ttu-id="b9560-213">경우 기존 범위 `counter` 변수가 프로시저에 로컬인는 컴파일 타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="b9560-214">예</span><span class="sxs-lookup"><span data-stu-id="b9560-214">Yes</span></span>|<span data-ttu-id="b9560-215">아니요</span><span class="sxs-lookup"><span data-stu-id="b9560-215">No</span></span>|<span data-ttu-id="b9560-216">예.</span><span class="sxs-lookup"><span data-stu-id="b9560-216">Yes.</span></span>|  
  
 <span data-ttu-id="b9560-217">데이터 형식이 `counter` 다음 유형 중 하나가 되도록 반복의 유형을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>  
  
-   <span data-ttu-id="b9560-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, 또는 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>  
  
-   <span data-ttu-id="b9560-219">사용 하 여 선언 하는 열거는 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-219">An enumeration that you declare by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
-   <span data-ttu-id="b9560-220">`Object`입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-220">An `Object`.</span></span>  
  
-   <span data-ttu-id="b9560-221">형식 `T` 다음과 같은 연산자가 있는 여기서 `B` 에 사용할 수 있는 형식인는 `Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 <span data-ttu-id="b9560-222">선택적으로 지정할 수는 `counter` 변수에 `Next` 문.</span><span class="sxs-lookup"><span data-stu-id="b9560-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="b9560-223">이 구문은 중첩 된 경우에 특히 프로그램의 가독성을 높일 수 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="b9560-224">해당 표시 되는 변수를 지정 해야 `For` 문.</span><span class="sxs-lookup"><span data-stu-id="b9560-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>  
  
 <span data-ttu-id="b9560-225">`start`, `end`, 및 `step` 식의 형식으로 확대 되는 모든 데이터 형식으로 평가할 수 `counter`합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="b9560-226">에 대 한 사용자 정의 형식을 사용 하면 `counter`를 정의 해야 할 수 있습니다는 `CType` 변환 연산자의 종류를 `start`, `end`, 또는 `step` 유형과 `counter`합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9560-227">예제</span><span class="sxs-lookup"><span data-stu-id="b9560-227">Example</span></span>  
 <span data-ttu-id="b9560-228">다음 예제에서는 제네릭 목록에서 모든 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="b9560-229">대신는 [각각에 대해... 다음 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md), 예제에 나와 있는 `For`... `Next` 내림차순 반복 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-229">Instead of a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="b9560-230">이 예제에서는 때문에이 기술을 사용 하 여는 `removeAt` 메서드 더 낮은 인덱스 값을 제거 하는 요소 뒤 요소를 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>  
  
 [!code-vb[VbVbalrStatements#114](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_5.vb)]  
  
## <a name="example"></a><span data-ttu-id="b9560-231">예제</span><span class="sxs-lookup"><span data-stu-id="b9560-231">Example</span></span>  
 <span data-ttu-id="b9560-232">다음 예제에서는 사용 하 여 선언 하는 열거형 반복는 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
 [!code-vb[VbVbalrStatements#116](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_6.vb)]  
  
## <a name="example"></a><span data-ttu-id="b9560-233">예제</span><span class="sxs-lookup"><span data-stu-id="b9560-233">Example</span></span>  
 <span data-ttu-id="b9560-234">다음 예제에서는 문 매개 변수 사용에 대 한 연산자 오버 로드가 있는 클래스는 `+`, `-`, `>=`, 및 `<=` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="b9560-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>  
  
 [!code-vb[VbVbalrStatements#117](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-next-statement_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b9560-235">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9560-235">See Also</span></span>  
 <xref:System.Collections.Generic.List%601>  
 [<span data-ttu-id="b9560-236">루프 구조</span><span class="sxs-lookup"><span data-stu-id="b9560-236">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="b9560-237">While...End While 문</span><span class="sxs-lookup"><span data-stu-id="b9560-237">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="b9560-238">Do...Loop 문</span><span class="sxs-lookup"><span data-stu-id="b9560-238">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="b9560-239">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="b9560-239">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="b9560-240">Exit 문</span><span class="sxs-lookup"><span data-stu-id="b9560-240">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="b9560-241">컬렉션</span><span class="sxs-lookup"><span data-stu-id="b9560-241">Collections</span></span>](../../programming-guide/concepts/collections.md)
