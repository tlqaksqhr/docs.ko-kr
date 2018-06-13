---
title: If...Then...Else 문(Visual Basic)
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: 08d51326ee0c9f91eec02467ebcb116354b5033f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604993"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="874d3-102">If...Then...Else 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="874d3-102">If...Then...Else Statement (Visual Basic)</span></span>
<span data-ttu-id="874d3-103">식의 값에 따라 문 그룹을 조건부로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="874d3-104">구문</span><span class="sxs-lookup"><span data-stu-id="874d3-104">Syntax</span></span>  
  
```  
' Multiline syntax:  
If condition [ Then ]  
    [ statements ]  
[ ElseIf elseifcondition [ Then ]  
    [ elseifstatements ] ]  
[ Else  
    [ elsestatements ] ]  
End If  
  
' Single-line syntax:  
If condition Then [ statements ] [ Else [ elsestatements ] ]  
```  

## <a name="quick-links-to-example-code"></a><span data-ttu-id="874d3-105">예제 코드에 대 한 빠른 링크</span><span class="sxs-lookup"><span data-stu-id="874d3-105">Quick links to example code</span></span>

<span data-ttu-id="874d3-106">이 문서 포함의 용도 설명 하는 샘플 몇 가지 예는 `If`... `Then`... `Else` 문:</span><span class="sxs-lookup"><span data-stu-id="874d3-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

* [<span data-ttu-id="874d3-107">여러 줄로 된 구문 예제</span><span class="sxs-lookup"><span data-stu-id="874d3-107">Multiline syntax example</span></span>](#multi-line)
* [<span data-ttu-id="874d3-108">중첩 된 구문 예제</span><span class="sxs-lookup"><span data-stu-id="874d3-108">Nested syntax example</span></span>](#nested)
* [<span data-ttu-id="874d3-109">한 줄 구문 예제</span><span class="sxs-lookup"><span data-stu-id="874d3-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="874d3-110">요소</span><span class="sxs-lookup"><span data-stu-id="874d3-110">Parts</span></span>  
 `condition`  
 <span data-ttu-id="874d3-111">필수.</span><span class="sxs-lookup"><span data-stu-id="874d3-111">Required.</span></span> <span data-ttu-id="874d3-112">식입니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-112">Expression.</span></span> <span data-ttu-id="874d3-113">로 계산 되어야 `True` 또는 `False`, 또는로 암시적으로 변환할 수 있는 데이터 형식 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 <span data-ttu-id="874d3-114">식이 [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` 변수 [Nothing](../../../visual-basic/language-reference/nothing.md), 조건 식은 처럼 처리 됩니다 `False` 및 `Else` 블록이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False` and the `Else` block is executed.</span></span>  
  
 `Then`  
 <span data-ttu-id="874d3-115">한 줄 구문;에 필요한 여러 줄 구문에서 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>  
  
 `statements`  
 <span data-ttu-id="874d3-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-116">Optional.</span></span> <span data-ttu-id="874d3-117">하나 이상의 문 다음 `If`... `Then` 경우 실행 되는 `condition` 계산 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>  
  
 `elseifcondition`  
 <span data-ttu-id="874d3-118">필요한 경우 `ElseIf` 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="874d3-119">식입니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-119">Expression.</span></span> <span data-ttu-id="874d3-120">로 계산 되어야 `True` 또는 `False`, 또는로 암시적으로 변환할 수 있는 데이터 형식 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 `elseifstatements`  
 <span data-ttu-id="874d3-121">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-121">Optional.</span></span> <span data-ttu-id="874d3-122">하나 이상의 문 다음 `ElseIf`... `Then` 경우 실행 되는 `elseifcondition` 계산 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>  
  
 `elsestatements`  
 <span data-ttu-id="874d3-123">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-123">Optional.</span></span> <span data-ttu-id="874d3-124">앞에 나오는 경우 실행 되는 하나 이상의 문 `condition` 또는 `elseifcondition` 식이 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>  
  
 `End If`  
 <span data-ttu-id="874d3-125">여러 줄로 된 버전의 종료 `If`... `Then`... `Else` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="874d3-126">설명</span><span class="sxs-lookup"><span data-stu-id="874d3-126">Remarks</span></span>  
  
### <a name="multiline-syntax"></a><span data-ttu-id="874d3-127">여러 줄 구문</span><span class="sxs-lookup"><span data-stu-id="874d3-127">Multiline syntax</span></span>  
 <span data-ttu-id="874d3-128">경우는 `If`... `Then`... `Else` 문이 실행 될 `condition` 테스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="874d3-129">경우 `condition` 은 `True`, 다음 문을 `Then` 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="874d3-130">경우 `condition` 은 `False`, 각 `ElseIf` 문 (있는 경우) 순서로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="874d3-131">경우는 `True` `elseifcondition` 발견 되 면 바로 다음에 관련 된 문을 `ElseIf` 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="874d3-132">없는 경우 `elseifcondition` 계산 `True`, 없는 경우 또는 없습니다 `ElseIf` 다음 문은 `Else` 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="874d3-133">다음 문을 실행 한 후 `Then`, `ElseIf`, 또는 `Else`, 실행이 계속 다음 문으로 `End If`합니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>  
  
 <span data-ttu-id="874d3-134">`ElseIf` 및 `Else` 절은 모두 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="874d3-135">만큼 가질 수 `ElseIf` 때 절에서 원하는 `If`... `Then`... `Else` 문은 되지만 아니요 `ElseIf` 절 뒤에 나타날 수는 `Else` 절.</span><span class="sxs-lookup"><span data-stu-id="874d3-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="874d3-136">`If`... `Then`... `Else` 문은은 서로 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>  
  
 <span data-ttu-id="874d3-137">여러 줄로 된 구문에는 `If` 문은 첫 번째 줄에서 유일한 문 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="874d3-138">`ElseIf`, `Else`, 및 `End If` 문 앞에 줄 레이블을 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="874d3-139">`If`... `Then`... `Else` 로 끝나야 합니다. 블록은 `End If` 문.</span><span class="sxs-lookup"><span data-stu-id="874d3-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="874d3-140">[선택... Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md) 가능한 값이 여러 개 있는 단일 식을 계산 하는 경우 더 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>  
  
### <a name="single-line-syntax"></a><span data-ttu-id="874d3-141">한 줄 구문</span><span class="sxs-lookup"><span data-stu-id="874d3-141">Single-Line syntax</span></span>  
 <span data-ttu-id="874d3-142">True 일 경우 실행할 코드를 사용 하 여 단일 조건 단일 인라인 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="874d3-143">그러나 다중 인라인 구문을 유연성과 구조를 제공 하며 읽고 유지 관리 하 고, 디버깅 하기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>  
  
 <span data-ttu-id="874d3-144">다음은 `Then` 키워드를 검사 하는 문을 한 줄 인지 확인 `If`합니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="874d3-145">주석 이외의 뒤에 표시 하는 경우 `Then` 같은 줄에는 문을 한 줄으로 처리 됩니다 `If` 문.</span><span class="sxs-lookup"><span data-stu-id="874d3-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="874d3-146">경우 `Then` 이 없음, 여러 줄의 시작 해야 `If`... `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="874d3-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>  
  
 <span data-ttu-id="874d3-147">한 줄 구문에서의 결과로 실행 하는 여러 개의 문을 포함할 수 있습니다는 `If`... `Then` 의사 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="874d3-148">모든 문이 같은 줄에 있어야 하며 콜론으로 구분 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-148">All statements must be on the same line and be separated by colons.</span></span>  

## <a name="multiline-syntax-example"></a><span data-ttu-id="874d3-149">여러 줄로 된 구문 예제</span><span class="sxs-lookup"><span data-stu-id="874d3-149">Multiline syntax example</span></span>

<a name="multi-line"></a>
 
 <span data-ttu-id="874d3-150">다음 예제에서는 여러 줄 구문의 사용을 보여 줍니다.는 `If`... `Then`... `Else` 문.</span><span class="sxs-lookup"><span data-stu-id="874d3-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb?highlight=11,14,17,19)]

## <a name="nested-syntax-example"></a><span data-ttu-id="874d3-151">중첩 된 구문 예제</span><span class="sxs-lookup"><span data-stu-id="874d3-151">Nested syntax example</span></span>

<a name="nested"></a>

 <span data-ttu-id="874d3-152">다음 예제에는 중첩 된 `If`... `Then`... `Else` 문.</span><span class="sxs-lookup"><span data-stu-id="874d3-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb?highlight=14,15,17,19,20,21,23,25,26,28)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="874d3-153">한 줄 구문 예제</span><span class="sxs-lookup"><span data-stu-id="874d3-153">Single-Line syntax example</span></span>
  
<a name="single-line"></a> <span data-ttu-id="874d3-154">다음 예제는 한 줄 구문 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="874d3-154">The following example illustrates the use of the single-line syntax.</span></span>  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb?highlight=18)]
  
## <a name="see-also"></a><span data-ttu-id="874d3-155">참고자료</span><span class="sxs-lookup"><span data-stu-id="874d3-155">See also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [<span data-ttu-id="874d3-156">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="874d3-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="874d3-157">Select...Case 문</span><span class="sxs-lookup"><span data-stu-id="874d3-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="874d3-158">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="874d3-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="874d3-159">판단 구조</span><span class="sxs-lookup"><span data-stu-id="874d3-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="874d3-160">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="874d3-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="874d3-161">If 연산자</span><span class="sxs-lookup"><span data-stu-id="874d3-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
