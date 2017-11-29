---
title: "If...Then...Else 문(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 898b72055345e88ca35f805de211c0c57cd74200
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="d5e13-102">If...Then...Else 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5e13-102">If...Then...Else Statement (Visual Basic)</span></span>
<span data-ttu-id="d5e13-103">식의 값에 따라 문 그룹을 조건부로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5e13-104">구문</span><span class="sxs-lookup"><span data-stu-id="d5e13-104">Syntax</span></span>  
  
```  
' Multiple-line syntax:  
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
  
## <a name="parts"></a><span data-ttu-id="d5e13-105">요소</span><span class="sxs-lookup"><span data-stu-id="d5e13-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="d5e13-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="d5e13-106">Required.</span></span> <span data-ttu-id="d5e13-107">식입니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-107">Expression.</span></span> <span data-ttu-id="d5e13-108">로 계산 되어야 `True` 또는 `False`, 또는로 암시적으로 변환할 수 있는 데이터 형식 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-108">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 <span data-ttu-id="d5e13-109">식의 값을 [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` 계산 되는 변수 [아무](../../../visual-basic/language-reference/nothing.md), 조건 식이 있지 않은 것 처럼 처리 됩니다 `True`, 및 `Else` 블록은 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-109">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is not `True`, and the `Else` block is executed.</span></span>  
  
 `Then`  
 <span data-ttu-id="d5e13-110">한 줄 구문;에 필요한 여러 줄로 이루어진 구문에서 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-110">Required in the single-line syntax; optional in the multiple-line syntax.</span></span>  
  
 `statements`  
 <span data-ttu-id="d5e13-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-111">Optional.</span></span> <span data-ttu-id="d5e13-112">하나 이상의 문 다음 `If`... `Then` 경우 실행 되는 `condition` 계산 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-112">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>  
  
 `elseifcondition`  
 <span data-ttu-id="d5e13-113">필요한 경우 `ElseIf` 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-113">Required if `ElseIf` is present.</span></span> <span data-ttu-id="d5e13-114">식입니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-114">Expression.</span></span> <span data-ttu-id="d5e13-115">로 계산 되어야 `True` 또는 `False`, 또는로 암시적으로 변환할 수 있는 데이터 형식 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-115">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>  
  
 `elseifstatements`  
 <span data-ttu-id="d5e13-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-116">Optional.</span></span> <span data-ttu-id="d5e13-117">하나 이상의 문 다음 `ElseIf`... `Then` 경우 실행 되는 `elseifcondition` 계산 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-117">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>  
  
 `elsestatements`  
 <span data-ttu-id="d5e13-118">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-118">Optional.</span></span> <span data-ttu-id="d5e13-119">앞에 나오는 경우 실행 되는 하나 이상의 문 `condition` 또는 `elseifcondition` 식이 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-119">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>  
  
 `End If`  
 <span data-ttu-id="d5e13-120">종료는 `If`... `Then`... `Else` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-120">Terminates the `If`...`Then`...`Else` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5e13-121">설명</span><span class="sxs-lookup"><span data-stu-id="d5e13-121">Remarks</span></span>  
  
## <a name="multiple-line-syntax"></a><span data-ttu-id="d5e13-122">여러 줄로 이루어진 구문</span><span class="sxs-lookup"><span data-stu-id="d5e13-122">Multiple-Line Syntax</span></span>  
 <span data-ttu-id="d5e13-123">경우는 `If`... `Then`... `Else` 문이 실행 될 `condition` 테스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-123">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="d5e13-124">경우 `condition` 은 `True`, 다음 문을 `Then` 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-124">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="d5e13-125">경우 `condition` 은 `False`, 각 `ElseIf` 문 (있는 경우) 순서로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-125">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="d5e13-126">경우는 `True``elseifcondition` 발견 되 면 바로 다음에 관련 된 문을 `ElseIf` 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-126">When a `True``elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="d5e13-127">없는 경우 `elseifcondition` 계산 `True`, 없는 경우 또는 없습니다 `ElseIf` 다음 문은 `Else` 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-127">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="d5e13-128">다음 문을 실행 한 후 `Then`, `ElseIf`, 또는 `Else`, 실행이 계속 다음 문으로 `End If`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-128">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>  
  
 <span data-ttu-id="d5e13-129">`ElseIf` 및 `Else` 절은 모두 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-129">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="d5e13-130">만큼 가질 수 `ElseIf` 때 절에서 원하는 `If`... `Then`... `Else` 문은 되지만 아니요 `ElseIf` 절 뒤에 나타날 수는 `Else` 절.</span><span class="sxs-lookup"><span data-stu-id="d5e13-130">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="d5e13-131">`If`... `Then`... `Else` 문은은 서로 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-131">`If`...`Then`...`Else` statements can be nested within each other.</span></span>  
  
 <span data-ttu-id="d5e13-132">여러 줄로 이루어진 구문에는 `If` 문은 첫 번째 줄에서 유일한 문 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-132">In the multiple-line syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="d5e13-133">`ElseIf`, `Else`, 및 `End If` 문 앞에 줄 레이블을 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-133">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="d5e13-134">`If`... `Then`... `Else` 로 끝나야 합니다. 블록은 `End If` 문.</span><span class="sxs-lookup"><span data-stu-id="d5e13-134">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="d5e13-135">[선택... Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md) 가능한 값이 여러 개 있는 단일 식을 계산 하는 경우 더 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-135">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>  
  
## <a name="single-line-syntax"></a><span data-ttu-id="d5e13-136">한 줄 구문</span><span class="sxs-lookup"><span data-stu-id="d5e13-136">Single-Line Syntax</span></span>  
 <span data-ttu-id="d5e13-137">짧은, 간단한 테스트에 대 한 단일 인라인 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-137">You can use the single-line syntax for short, simple tests.</span></span> <span data-ttu-id="d5e13-138">그러나 다중 인라인 구문을 유연성과 구조를 제공 하며을 더 쉽게 읽고, 유지 관리 하 고 디버깅 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-138">However, the multiple-line syntax provides more structure and flexibility and is usually easier to read, maintain, and debug.</span></span>  
  
 <span data-ttu-id="d5e13-139">다음은 `Then` 키워드를 검사 하는 문을 한 줄 인지 확인 `If`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-139">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="d5e13-140">주석 이외의 뒤에 표시 하는 경우 `Then` 같은 줄에는 문을 한 줄으로 처리 됩니다 `If` 문.</span><span class="sxs-lookup"><span data-stu-id="d5e13-140">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="d5e13-141">경우 `Then` 이 없음, 여러 줄의 시작 해야 `If`... `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="d5e13-141">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>  
  
 <span data-ttu-id="d5e13-142">한 줄 구문에서의 결과로 실행 하는 여러 개의 문을 포함할 수 있습니다는 `If`... `Then` 의사 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-142">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="d5e13-143">모든 문이 같은 줄에 있어야 하며 콜론으로 구분 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-143">All statements must be on the same line and be separated by colons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5e13-144">예제</span><span class="sxs-lookup"><span data-stu-id="d5e13-144">Example</span></span>  
 <span data-ttu-id="d5e13-145">다음 예제에서는 여러 줄 구문의 사용을 보여 줍니다.는 `If`... `Then`... `Else` 문.</span><span class="sxs-lookup"><span data-stu-id="d5e13-145">The following example illustrates the use of the multiple-line syntax of the `If`...`Then`...`Else` statement.</span></span>  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="d5e13-146">예제</span><span class="sxs-lookup"><span data-stu-id="d5e13-146">Example</span></span>  
 <span data-ttu-id="d5e13-147">다음 예제에는 중첩 된 `If`... `Then`... `Else` 문.</span><span class="sxs-lookup"><span data-stu-id="d5e13-147">The following example contains nested `If`...`Then`...`Else` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="d5e13-148">예제</span><span class="sxs-lookup"><span data-stu-id="d5e13-148">Example</span></span>  
 <span data-ttu-id="d5e13-149">다음 예제는 한 줄 구문 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e13-149">The following example illustrates the use of the single-line syntax.</span></span>  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d5e13-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5e13-150">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>  
 [<span data-ttu-id="d5e13-151">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="d5e13-151">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="d5e13-152">Select...Case 문</span><span class="sxs-lookup"><span data-stu-id="d5e13-152">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="d5e13-153">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="d5e13-153">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="d5e13-154">판단 구조</span><span class="sxs-lookup"><span data-stu-id="d5e13-154">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="d5e13-155">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="d5e13-155">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="d5e13-156">If 연산자</span><span class="sxs-lookup"><span data-stu-id="d5e13-156">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
