---
title: Exit 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: 05a65dd84a00478f52c8cd7d8b46341644512718
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605279"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="7479c-102">Exit 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7479c-102">Exit Statement (Visual Basic)</span></span>
<span data-ttu-id="7479c-103">프로시저 또는 블록을 종료 하 고 프로시저 호출 또는 블록 정의 다음 문으로 제어를 즉시 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7479c-104">구문</span><span class="sxs-lookup"><span data-stu-id="7479c-104">Syntax</span></span>  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a><span data-ttu-id="7479c-105">문</span><span class="sxs-lookup"><span data-stu-id="7479c-105">Statements</span></span>  
 `Exit Do`  
 <span data-ttu-id="7479c-106">즉시 끝내는 `Do` 을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="7479c-107">실행이 계속 다음 문으로 `Loop` 문.</span><span class="sxs-lookup"><span data-stu-id="7479c-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="7479c-108">`Exit Do` 내 에서만 사용할 수는 `Do` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="7479c-109">사용할 경우 내에 중첩 `Do` 루프, `Exit Do` 가장 안쪽 루프를 끝내 고 중첩 다음으로 높은 수준으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit For`  
 <span data-ttu-id="7479c-110">즉시 끝내는 `For` 을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="7479c-111">실행이 계속 다음 문으로 `Next` 문.</span><span class="sxs-lookup"><span data-stu-id="7479c-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="7479c-112">`Exit For` 내 에서만 사용할 수는 `For`... `Next` 또는 `For Each`... `Next` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="7479c-113">사용할 경우 내에 중첩 `For` 루프, `Exit For` 가장 안쪽 루프를 끝내 고 중첩 다음으로 높은 수준으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit Function`  
 <span data-ttu-id="7479c-114">즉시 끝내는 `Function` 나타나는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="7479c-115">실행이 계속 호출 하는 문을 다음 문으로 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="7479c-116">`Exit Function` 내 에서만 사용할 수는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>  
  
 <span data-ttu-id="7479c-117">반환 값을 지정 하려면 값 앞에 줄에 함수 이름에 할당할 수 있습니다는 `Exit Function` 문.</span><span class="sxs-lookup"><span data-stu-id="7479c-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="7479c-118">반환 값 할당 exit 하나의 문에서 함수를 대신 사용할 수 있습니다는 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 `Exit Property`  
 <span data-ttu-id="7479c-119">즉시 끝내는 `Property` 나타나는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="7479c-120">호출한 문의 실행이 계속는 `Property` 프로시저, 즉, 요청 하거나 속성의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="7479c-121">`Exit Property` 속성의 내 에서만 사용할 수 `Get` 또는 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>  
  
 <span data-ttu-id="7479c-122">반환 값을 지정 하는 `Get` 프로시저, 함수 이름 앞에 있는 줄에 값을 할당할 수 있습니다는 `Exit Property` 문.</span><span class="sxs-lookup"><span data-stu-id="7479c-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="7479c-123">반환 값 및 종료를 할당 하는 `Get` 하나의 문에서 프로시저를 대신 사용할 수 있습니다는 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="7479c-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>  
  
 <span data-ttu-id="7479c-124">에 `Set` 프로시저는 `Exit Property` 문을 같습니다는 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="7479c-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Select`  
 <span data-ttu-id="7479c-125">즉시 끝내는 `Select Case` 나타나는 것을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="7479c-126">실행이 계속 다음 문으로 `End Select` 문.</span><span class="sxs-lookup"><span data-stu-id="7479c-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="7479c-127">`Exit Select` 내 에서만 사용할 수는 `Select Case` 문.</span><span class="sxs-lookup"><span data-stu-id="7479c-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>  
  
 `Exit Sub`  
 <span data-ttu-id="7479c-128">즉시 끝내는 `Sub` 나타나는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="7479c-129">실행이 계속 호출 하는 문을 다음 문으로 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="7479c-130">`Exit Sub` 내 에서만 사용할 수는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>  
  
 <span data-ttu-id="7479c-131">에 `Sub` 프로시저는 `Exit Sub` 문을 같습니다는 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="7479c-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Try`  
 <span data-ttu-id="7479c-132">즉시 끝내는 `Try` 또는 `Catch` 나타나는 것을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="7479c-133">실행이 계속는 `Finally` 블록 있는 경우, 또는 문 다음의 `End Try` 문.</span><span class="sxs-lookup"><span data-stu-id="7479c-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="7479c-134">`Exit Try` 내 에서만 사용할 수는 `Try` 또는 `Catch` 블록 내부가 아니라는 `Finally` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>  
  
 `Exit While`  
 <span data-ttu-id="7479c-135">즉시 끝내는 `While` 을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="7479c-136">실행이 계속 다음 문으로 `End While` 문.</span><span class="sxs-lookup"><span data-stu-id="7479c-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="7479c-137">`Exit While` 내 에서만 사용할 수는 `While` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="7479c-138">사용할 경우 내에 중첩 `While` 루프, `Exit While` 제어 루프 위에 중첩된 수준이 하나 있는 루프를 전달 여기서 `Exit While` 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7479c-139">설명</span><span class="sxs-lookup"><span data-stu-id="7479c-139">Remarks</span></span>  
 <span data-ttu-id="7479c-140">혼동 하지 마십시오. `Exit` 으로 문을 `End` 문.</span><span class="sxs-lookup"><span data-stu-id="7479c-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="7479c-141">`Exit` 문의 끝을 정의 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-141">`Exit` does not define the end of a statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7479c-142">예제</span><span class="sxs-lookup"><span data-stu-id="7479c-142">Example</span></span>  
 <span data-ttu-id="7479c-143">루프 조건에서 다음 예제에서는 루프를 중지 때는 `index` 변수는 100을 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="7479c-144">그러나 `If` 루프에 문을 지정 하면는 `Exit Do` 문의 인덱스 변수는 10 보다 큰 경우에 루프를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="7479c-145">예제</span><span class="sxs-lookup"><span data-stu-id="7479c-145">Example</span></span>  
 <span data-ttu-id="7479c-146">다음 예제에서는 함수 이름에 반환 값을 할당 `myFunction`, 다음 사용 하 여 `Exit Function` 함수에서 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7479c-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="7479c-147">예제</span><span class="sxs-lookup"><span data-stu-id="7479c-147">Example</span></span>  
 <span data-ttu-id="7479c-148">다음 예제에서는 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md) 반환 값을 할당 하는 함수를 종료 하려면.</span><span class="sxs-lookup"><span data-stu-id="7479c-148">The following example uses the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) to assign the return value and exit the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7479c-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7479c-149">See Also</span></span>  
 [<span data-ttu-id="7479c-150">Continue 문</span><span class="sxs-lookup"><span data-stu-id="7479c-150">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)  
 [<span data-ttu-id="7479c-151">Do...Loop 문</span><span class="sxs-lookup"><span data-stu-id="7479c-151">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="7479c-152">End 문</span><span class="sxs-lookup"><span data-stu-id="7479c-152">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)  
 [<span data-ttu-id="7479c-153">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="7479c-153">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="7479c-154">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="7479c-154">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="7479c-155">Function 문</span><span class="sxs-lookup"><span data-stu-id="7479c-155">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="7479c-156">Return 문</span><span class="sxs-lookup"><span data-stu-id="7479c-156">Return Statement</span></span>](../../../visual-basic/language-reference/statements/return-statement.md)  
 [<span data-ttu-id="7479c-157">Stop 문</span><span class="sxs-lookup"><span data-stu-id="7479c-157">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [<span data-ttu-id="7479c-158">Sub 문</span><span class="sxs-lookup"><span data-stu-id="7479c-158">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="7479c-159">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="7479c-159">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
