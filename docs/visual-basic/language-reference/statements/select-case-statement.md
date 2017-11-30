---
title: "Select...Case 문(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Select
- vb.Case
helpviewer_keywords:
- Select statement [Visual Basic]
- Case statement [Visual Basic]
- Select...Case statements
- conditional statements [Visual Basic], Select Case
- control flow [Visual Basic], branching
- Else keyword [Visual Basic], in Select...Case statements
- execution [Visual Basic], conditional
- To keyword [Visual Basic], in Select...Case statements
- Select Case statement [Visual Basic], Select...Case
- Select statement [Visual Basic], Select...Case
- Is operator [Visual Basic], in Select...Case statements
- branching [Visual Basic], conditional
- Case Else statement [Visual Basic], Select...Case
- End keyword [Visual Basic], Select Case statements
- Case statement [Visual Basic], Select...Case
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a7527763a05ec32af88c6ba66ef717d839c33154
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="selectcase-statement-visual-basic"></a><span data-ttu-id="57483-102">Select...Case 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57483-102">Select...Case Statement (Visual Basic)</span></span>
<span data-ttu-id="57483-103">여러 식의 값에 따라 문 그룹 중 하나를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-103">Runs one of several groups of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57483-104">구문</span><span class="sxs-lookup"><span data-stu-id="57483-104">Syntax</span></span>  
  
```  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a><span data-ttu-id="57483-105">요소</span><span class="sxs-lookup"><span data-stu-id="57483-105">Parts</span></span>  
  
|<span data-ttu-id="57483-106">용어</span><span class="sxs-lookup"><span data-stu-id="57483-106">Term</span></span>|<span data-ttu-id="57483-107">정의</span><span class="sxs-lookup"><span data-stu-id="57483-107">Definition</span></span>|  
|---|---|  
|`testexpression`|<span data-ttu-id="57483-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="57483-108">Required.</span></span> <span data-ttu-id="57483-109">식입니다.</span><span class="sxs-lookup"><span data-stu-id="57483-109">Expression.</span></span> <span data-ttu-id="57483-110">기본 데이터 형식 중 하나로 계산 되어야 합니다 (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, 및 `UShort`).</span><span class="sxs-lookup"><span data-stu-id="57483-110">Must evaluate to one of the elementary data types (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, and `UShort`).</span></span>|  
|`expressionlist`|<span data-ttu-id="57483-111">에 필요한는 `Case` 문.</span><span class="sxs-lookup"><span data-stu-id="57483-111">Required in a `Case` statement.</span></span> <span data-ttu-id="57483-112">식 절에 대 한 일치 하는 값을 나타내는 목록 `testexpression`합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-112">List of expression clauses representing match values for `testexpression`.</span></span> <span data-ttu-id="57483-113">여러 개의 식 절은 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57483-113">Multiple expression clauses are separated by commas.</span></span> <span data-ttu-id="57483-114">각 절에는 다음 형식 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57483-114">Each clause can take one of the following forms:</span></span><br /><br /> <span data-ttu-id="57483-115">-   *expression1* `To` *expression2*</span><span class="sxs-lookup"><span data-stu-id="57483-115">-   *expression1* `To` *expression2*</span></span><br /><span data-ttu-id="57483-116">-[ `Is` ] *comparisonoperator* *식*</span><span class="sxs-lookup"><span data-stu-id="57483-116">-   [ `Is` ] *comparisonoperator* *expression*</span></span><br /><span data-ttu-id="57483-117">-   *식*</span><span class="sxs-lookup"><span data-stu-id="57483-117">-   *expression*</span></span><br /><br /> <span data-ttu-id="57483-118">사용 하 여는 `To` 다양 한 일치 항목의 경계를 지정 하려면 키워드에 대 한 값 `testexpression`합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-118">Use the `To` keyword to specify the boundaries of a range of match values for `testexpression`.</span></span> <span data-ttu-id="57483-119">값 `expression1` 의 값 보다 작거나 같아야 합니다 `expression2`합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-119">The value of `expression1` must be less than or equal to the value of `expression2`.</span></span><br /><br /> <span data-ttu-id="57483-120">사용 하 여는 `Is` 에 비교 연산자 키워드 (`=`, `<>`, `<`, `<=`, `>`, 또는 `>=`)에 대 한 일치 항목 값에 대 한 제한을 지정할 `testexpression`합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-120">Use the `Is` keyword with a comparison operator (`=`, `<>`, `<`, `<=`, `>`, or `>=`) to specify a restriction on the match values for `testexpression`.</span></span> <span data-ttu-id="57483-121">경우는 `Is` 키워드를 제공 하지 않으면, 하기 전에 자동으로 삽입 *comparisonoperator*합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-121">If the `Is` keyword is not supplied, it is automatically inserted before *comparisonoperator*.</span></span><br /><br /> <span data-ttu-id="57483-122">만 지정 하는 폼 `expression` 의 특수 한 경우로 처리 되는 `Is` where 형성 *comparisonoperator* 는 등호 (`=`).</span><span class="sxs-lookup"><span data-stu-id="57483-122">The form specifying only `expression` is treated as a special case of the `Is` form where *comparisonoperator* is the equal sign (`=`).</span></span> <span data-ttu-id="57483-123">이 형식으로 계산 됩니다 `testexpression`  =  `expression`합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-123">This form is evaluated as `testexpression` = `expression`.</span></span><br /><br /> <span data-ttu-id="57483-124">에 있는 식은 `expressionlist` 의 형식으로 암시적으로 변환할 수 있는 데이터 형식일 수 있습니다 `testexpression` 및 적절 한 `comparisonoperator` 함께 사용 되는 두 형식에 대해 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-124">The expressions in `expressionlist` can be of any data type, provided they are implicitly convertible to the type of `testexpression` and the appropriate `comparisonoperator` is valid for the two types it is being used with.</span></span>|  
|`statements`|<span data-ttu-id="57483-125">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="57483-125">Optional.</span></span> <span data-ttu-id="57483-126">하나 이상의 문 다음 `Case` 실행 `testexpression` 에 모든 절과 일치할 `expressionlist`합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-126">One or more statements following `Case` that run if `testexpression` matches any clause in `expressionlist`.</span></span>|  
|`elsestatements`|<span data-ttu-id="57483-127">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="57483-127">Optional.</span></span> <span data-ttu-id="57483-128">하나 이상의 문 다음 `Case Else` 실행 `testexpression` 모든 절이 일치 하지 않습니다는 `expressionlist` 중 아무 메서드나는 `Case` 문.</span><span class="sxs-lookup"><span data-stu-id="57483-128">One or more statements following `Case Else` that run if `testexpression` does not match any clause in the `expressionlist` of any of the `Case` statements.</span></span>|  
|`End Select`|<span data-ttu-id="57483-129">정의 종료는 `Select`... `Case` 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-129">Terminates the definition of the `Select`...`Case` construction.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57483-130">설명</span><span class="sxs-lookup"><span data-stu-id="57483-130">Remarks</span></span>  
 <span data-ttu-id="57483-131">경우 `testexpression` 하 나와 일치 `Case` `expressionlist` 절, 다음에 `Case` 문을 실행 하는 다음 `Case`, `Case Else`, 또는 `End Select` 문.</span><span class="sxs-lookup"><span data-stu-id="57483-131">If `testexpression` matches any `Case` `expressionlist` clause, the statements following that `Case` statement run up to the next `Case`, `Case Else`, or `End Select` statement.</span></span> <span data-ttu-id="57483-132">제어가 다음 다음 문으로 전달 `End Select`합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-132">Control then passes to the statement following `End Select`.</span></span> <span data-ttu-id="57483-133">경우 `testexpression` 일치는 `expressionlist` 절에 둘 이상의 `Case` 절만 첫 번째 일치 문은 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-133">If `testexpression` matches an `expressionlist` clause in more than one `Case` clause, only the statements following the first match run.</span></span>  
  
 <span data-ttu-id="57483-134">`Case Else` 소개 하기 위한 문을 사용 하는 `elsestatements` 간에 일치 항목이 없을 경우을 실행 하는 `testexpression` 및 `expressionlist` 의 다른 절 `Case` 문.</span><span class="sxs-lookup"><span data-stu-id="57483-134">The `Case Else` statement is used to introduce the `elsestatements` to run if no match is found between the `testexpression` and an `expressionlist` clause in any of the other `Case` statements.</span></span> <span data-ttu-id="57483-135">것이 좋습니다 있어야 하 고 필요 하지는 않지만 `Case Else` 의 문에서 프로그램 `Select Case` 처리 하는 생성 예기치 못한 `testexpression` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="57483-135">Although not required, it is a good idea to have a `Case Else` statement in your `Select Case` construction to handle unforeseen `testexpression` values.</span></span> <span data-ttu-id="57483-136">없는 경우 `Case` `expressionlist` 절과 일치 `testexpression` 있으면 없는 `Case Else` 문을 다음 문으로 제어가 전달 `End Select`합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-136">If no `Case` `expressionlist` clause matches `testexpression` and there is no `Case Else` statement, control passes to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="57483-137">각 범위 또는 다중 식을 사용할 수 있습니다 `Case` 절.</span><span class="sxs-lookup"><span data-stu-id="57483-137">You can use multiple expressions or ranges in each `Case` clause.</span></span> <span data-ttu-id="57483-138">예를 들어 다음 줄이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="57483-138">For example, the following line is valid.</span></span>  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  <span data-ttu-id="57483-139">`Is` 에서 사용 된 키워드는 `Case` 및 `Case Else` 문에 같지는 않습니다는 [Is 연산자](../../../visual-basic/language-reference/operators/is-operator.md), 개체 참조 비교에 사용 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-139">The `Is` keyword used in the `Case` and `Case Else` statements is not the same as the [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md), which is used for object reference comparison.</span></span>  
  
 <span data-ttu-id="57483-140">범위와 문자열에 대 한 여러 개의 식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57483-140">You can specify ranges and multiple expressions for character strings.</span></span> <span data-ttu-id="57483-141">다음 예에서 `Case` "사과" 정확히 같습니다, 알파벳 순서로 "nuts"와 "soup" 사이의 값이 또는의 현재 값과 정확히 동일한 값을 포함 하는 모든 문자열과 일치 `testItem`합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-141">In the following example, `Case` matches any string that is exactly equal to "apples", has a value between "nuts" and "soup" in alphabetical order, or contains the exact same value as the current value of `testItem`.</span></span>  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 <span data-ttu-id="57483-142">설정 `Option Compare` 문자열 비교에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57483-142">The setting of `Option Compare` can affect string comparisons.</span></span> <span data-ttu-id="57483-143">아래 `Option Compare Text`, 문자열 "사과" 및 "사과" 같다고, 하지만 아래에서 비교 `Option Compare Binary`, 디렉터리가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-143">Under `Option Compare Text`, the strings "Apples" and "apples" compare as equal, but under `Option Compare Binary`, they do not.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57483-144">A `Case` 여러 절을 사용 하 여 문을 라고 하는 동작을 나타낼 수 *단락 (short-circuiting)*합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-144">A `Case` statement with multiple clauses can exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="57483-145">Visual Basic 절을 왼쪽에서 오른쪽으로 계산한 경우 일치 하는 항목을 생성 합니다. `testexpression`, 나머지 절 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57483-145">Visual Basic evaluates the clauses from left to right, and if one produces a match with `testexpression`, the remaining clauses are not evaluated.</span></span> <span data-ttu-id="57483-146">단락 (short-circuiting) 성능을 높일 수 있지만 모든 식에 두어야 하는 경우 예기치 않은 결과가 발생할 수 있습니다이 `expressionlist` 계산 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-146">Short-circuiting can improve performance, but it can produce unexpected results if you are expecting every expression in `expressionlist` to be evaluated.</span></span> <span data-ttu-id="57483-147">단락 (short-circuiting)에 대 한 자세한 내용은 참조 하십시오. [부울 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-147">For more information on short-circuiting, see [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span></span>  
  
 <span data-ttu-id="57483-148">경우 내의 코드는 `Case` 또는 `Case Else` 블록의 문이 더 이상 실행 하지 않아도 문 블록을 사용 하 여 블록을 종료할 수 있습니다는 `Exit Select` 문.</span><span class="sxs-lookup"><span data-stu-id="57483-148">If the code within a `Case` or `Case Else` statement block does not need to run any more of the statements in the block, it can exit the block by using the `Exit Select` statement.</span></span> <span data-ttu-id="57483-149">컨트롤을 즉시 이동이 다음 문으로 `End Select`합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-149">This transfers control immediately to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="57483-150">`Select Case`구조를 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57483-150">`Select Case` constructions can be nested.</span></span> <span data-ttu-id="57483-151">중첩 된 각 `Select Case` 짝이 되는 생성 되어 있어야 `End Select` 문을 단일에 완전히 포함 되어야 하 고 `Case` 또는 `Case Else` 외부의 문 블록 `Select Case` 중첩 된 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-151">Each nested `Select Case` construction must have a matching `End Select` statement and must be completely contained within a single `Case` or `Case Else` statement block of the outer `Select Case` construction within which it is nested.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57483-152">예제</span><span class="sxs-lookup"><span data-stu-id="57483-152">Example</span></span>  
 <span data-ttu-id="57483-153">다음 예제에서는 한 `Select Case` 변수 값에 해당 하는 줄을 쓰는 생성 `number`합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-153">The following example uses a `Select Case` construction to write a line corresponding to the value of the variable `number`.</span></span> <span data-ttu-id="57483-154">두 번째 `Case` 의 현재 값과 일치 하는 값을 포함 하는 문을 `number`이므로 6 및 8, inclusive"" 사이의 작성 하는 문을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57483-154">The second `Case` statement contains the value that matches the current value of `number`, so the statement that writes "Between 6 and 8, inclusive" runs.</span></span>  
  
 [!code-vb[VbVbalrStatements#54](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/select-case-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="57483-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57483-155">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>  
 [<span data-ttu-id="57483-156">End 문</span><span class="sxs-lookup"><span data-stu-id="57483-156">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)  
 [<span data-ttu-id="57483-157">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="57483-157">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="57483-158">Option Compare 문</span><span class="sxs-lookup"><span data-stu-id="57483-158">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="57483-159">Exit 문</span><span class="sxs-lookup"><span data-stu-id="57483-159">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
