---
title: "람다 식 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.LambdaFunction
dev_langs:
- VB
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: 52
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: e4624e5f20beeebf85656c893043030566200557
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017

---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="7827c-102">람다 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7827c-102">Lambda Expressions (Visual Basic)</span></span>
<span data-ttu-id="7827c-103">A *람다 식을* 은 함수 또는 대리자 유효한 모든 곳에서 사용할 수 있는 이름 없이 서브루틴입니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="7827c-104">람다 식 함수 또는 서브루틴이 수 있으며 또는 여러 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="7827c-105">람다 식에는 현재 범위에서 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-105">You can pass values from the current scope to a lambda expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7827c-106">`RemoveHandler` 문은 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="7827c-107">대리자 매개 변수는 람다 식을 전달할 수 없으며 `RemoveHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>  
  
 <span data-ttu-id="7827c-108">람다 식을 사용 하 여 만들는 `Function` 또는 `Sub` 표준 함수나 서브루틴을 만드는 경우와 마찬가지로 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="7827c-109">그러나 람다 식 문에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-109">However, lambda expressions are included in a statement.</span></span>  
  
 <span data-ttu-id="7827c-110">다음 예제에는 해당 인수를 증가 시키고 값을 반환 하는 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="7827c-111">함수에 대 한 두는 한 줄 및 여러 줄 람다 식 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>  
  
 <span data-ttu-id="7827c-112">[!code-vb[VbVbalrLambdas #&14;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7827c-112">[!code-vb[VbVbalrLambdas#14](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]</span></span>  
  
 <span data-ttu-id="7827c-113">다음 예제에는 값을 콘솔에 기록 하는 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-113">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="7827c-114">서브루틴에 대 한 두는 한 줄 및 여러 줄 람다 식 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-114">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>  
  
 <span data-ttu-id="7827c-115">[!code-vb[VbVbalrLambdas #&15;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="7827c-115">[!code-vb[VbVbalrLambdas#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]</span></span>  
  
 <span data-ttu-id="7827c-116">이전 예제에서 변수 이름에 람다 식이 할당 된 것을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-116">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="7827c-117">변수를 참조할 때마다 람다 식을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-117">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="7827c-118">선언 하 고 다음 예와에서 같이 같은 시간에 람다 식을 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-118">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>  
  
 <span data-ttu-id="7827c-119">[!code-vb[VbVbalrLambdas #&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="7827c-119">[!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]</span></span>  
  
 <span data-ttu-id="7827c-120">람다 식은 함수 호출의 값으로 반환 될 수 (의 예제 에서처럼는 [컨텍스트](#context) 이 항목의 뒷부분에 나오는 섹션), 또는 다음 예제와 같이 대리자 형식을 사용 하는 매개 변수를 인수로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-120">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>  
  
 <span data-ttu-id="7827c-121">[!code-vb[VbVbalrLambdas #&8;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="7827c-121">[!code-vb[VbVbalrLambdas#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="7827c-122">람다 식 구문</span><span class="sxs-lookup"><span data-stu-id="7827c-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="7827c-123">람다 식의 구문은 유사 표준 함수나 서브루틴의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-123">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="7827c-124">차이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="7827c-125">람다 식에 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="7827c-126">람다 식은와 같은 한정자를 가질 수 없습니다 `Overloads` 또는 `Overrides`합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="7827c-127">한 줄 람다 함수를 사용 하지 않는 한 `As` 절을 반환 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-127">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="7827c-128">대신, 형식은 반환 하는 람다 식의 본문이 값에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-128">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="7827c-129">예를 들어 람다 식의 본문이 `cust.City = "London"`, 해당 반환 형식은 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-129">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="7827c-130">여러 줄 람다 함수에서 지정 하거나 반환 형식을 사용 하 여는 `As` 절을 생략 하거나는 `As` 절 반환 형식이 유추 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-130">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="7827c-131">때는 `As` 여러 줄 람다 함수에 대 한 절을 생략 하면, 모든 주요 형식으로 반환 형식이 유추는 `Return` 문은 여러 줄 람다 함수에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-131">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="7827c-132">*지배적인 유형이* 는 다른 모든 형식은 변환할 수 있는 고유한 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-132">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="7827c-133">이 고유 형식을 확인할 수 없으면, 지배적인 유형이를 배열에 있는 다른 모든 형식의 범위를 좁힐 수 있는 고유 형식이입니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-133">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="7827c-134">이러한 고유 형식을 모두 확인할 수 없는 경우 기준 형식은 `Object`입니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-134">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="7827c-135">이 예제의 경우 `Option Strict` 로 설정 된 `On`, 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-135">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>  
  
     <span data-ttu-id="7827c-136">예를 들어 식에 제공 되는 `Return` 형식의 값을 포함 하는 문을 `Integer`, `Long`, 및 `Double`, 결과 배열 형식입니다 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-136">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="7827c-137">둘 다 `Integer` 및 `Long` 변환할 `Double` 만 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-137">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="7827c-138">따라서 기준 형식은 `Double` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-138">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="7827c-139">자세한 내용은 참조 [확장 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-139">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
-   <span data-ttu-id="7827c-140">한 줄 함수 본문에는 문이 아닌 값을 반환 하는 식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-140">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="7827c-141">없는 `Return` 한 줄 함수에 대 한 문입니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-141">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="7827c-142">한 줄 함수에 의해 반환 되는 값에는 함수 본문에 있는 식의 값이입니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-142">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>  
  
-   <span data-ttu-id="7827c-143">한 줄 서브루틴의 본문에는 단일 줄으로 된 문 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-143">The body of a single-line subroutine must be single-line statement.</span></span>  
  
-   <span data-ttu-id="7827c-144">한 줄 함수와 서브루틴이 포함 하지 않는 한 `End Function` 또는 `End Sub` 문.</span><span class="sxs-lookup"><span data-stu-id="7827c-144">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>  
  
-   <span data-ttu-id="7827c-145">람다 식 매개 변수의 데이터 형식을 사용 하 여 지정할 수 있습니다는 `As` 키워드 또는 매개 변수의 데이터 형식을 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-145">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="7827c-146">데이터 형식 중 하나 또는 모두를 유추 합니다 모든 매개 변수에 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-146">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="7827c-147">`Optional`및 `Paramarray` 매개 변수는 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-147">`Optional` and `Paramarray` parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="7827c-148">제네릭 매개 변수가 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-148">Generic parameters are not permitted.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="7827c-149">비동기 람다</span><span class="sxs-lookup"><span data-stu-id="7827c-149">Async Lambdas</span></span>  
 <span data-ttu-id="7827c-150">람다 식과 문을 사용 하 여 비동기 처리를 통합 하는 쉽게 만들 수는 [비동기](../../../../visual-basic/language-reference/modifiers/async.md) 및 [Await 연산자](../../../../visual-basic/language-reference/operators/await-operator.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-150">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="7827c-151">예를 들어 다음 Windows Forms 예제에는 비동기 메서드 `ExampleMethodAsync`를 호출하고 기다리는 이벤트 처리기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-151">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
```vb  
Public Class Form1  
  
    Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' ExampleMethodAsync returns a Task.  
        Await ExampleMethodAsync()  
        TextBox1.Text = vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 <span data-ttu-id="7827c-152">비동기 람다를 사용 하 여 동일한 이벤트 처리기를 추가할 수는 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-152">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="7827c-153">이 처리기를 추가하려면 다음 예제에 표시된 것처럼 람다 매개 변수 목록에 `Async` 한정자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-153">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
```vb  
Public Class Form1  
  
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load  
        AddHandler Button1.Click,   
            Async Sub(sender1, e1)  
                ' ExampleMethodAsync returns a Task.  
                Await ExampleMethodAsync()  
                TextBox1.Text = vbCrLf & "Control returned to Button1_ Click."  
            End Sub  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 <span data-ttu-id="7827c-154">만들고 비동기 메서드를 사용 하는 방법에 대 한 자세한 내용은 참조 [Async 및 Await를 사용한 비동기 프로그래밍](../../../../visual-basic/programming-guide/concepts/async/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-154">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
##  <span data-ttu-id="7827c-155"><a name="context"></a>컨텍스트</span><span class="sxs-lookup"><span data-stu-id="7827c-155"><a name="context"></a> Context</span></span>  
 <span data-ttu-id="7827c-156">정의 된 범위와 해당 컨텍스트를 공유 하는 람다 식을 합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-156">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="7827c-157">포함 범위에 작성 된 코드와 동일한 액세스 권한이 있음</span><span class="sxs-lookup"><span data-stu-id="7827c-157">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="7827c-158">멤버 변수, 함수 및 sub에 대 한 액세스를 포함 하는이 `Me`, 매개 변수 및 지역 변수 포함 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-158">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>  
  
 <span data-ttu-id="7827c-159">지역 변수 및 매개 변수를 포함 하는 범위에 대 한 액세스는 해당 범위의 수명 이후에도 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-159">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="7827c-160">으로 참조 하는 람다 식에 대리자를 가비지 수집에 사용할 수 없는 원본 환경에서 변수에 대 한 액세스가 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-160">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="7827c-161">다음 예제에서는 변수에서 `target` 로컬 `makeTheGame`, 메서드를 람다 식 `playTheGame` 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-161">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="7827c-162">반환 된 람다 식에 할당 되 `takeAGuess` 에서 `Main`, 지역 변수에 액세스할에 아직 `target`합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-162">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>  
  
 <span data-ttu-id="7827c-163">[!code-vb[VbVbalrLambdas #&12;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="7827c-163">[!code-vb[VbVbalrLambdas#12](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]</span></span>  
  
 <span data-ttu-id="7827c-164">다음 예제에서는 다양 한 범위의 중첩 된 람다 식의 액세스 권한 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-164">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="7827c-165">반환된 된 람다 식이 실행 되 면 `Main` 으로 `aDel`, 이러한 요소에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-165">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>  
  
-   <span data-ttu-id="7827c-166">이전에 정의 된 클래스의 필드:`aField`</span><span class="sxs-lookup"><span data-stu-id="7827c-166">A field of the class in which it is defined: `aField`</span></span>  
  
-   <span data-ttu-id="7827c-167">이전에 정의 된 클래스의 속성:`aProp`</span><span class="sxs-lookup"><span data-stu-id="7827c-167">A property of the class in which it is defined: `aProp`</span></span>  
  
-   <span data-ttu-id="7827c-168">메서드의 매개 변수 `functionWithNestedLambda`에서 정의 됩니다.`level1`</span><span class="sxs-lookup"><span data-stu-id="7827c-168">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>  
  
-   <span data-ttu-id="7827c-169">지역 변수가 `functionWithNestedLambda`:`localVar`</span><span class="sxs-lookup"><span data-stu-id="7827c-169">A local variable of `functionWithNestedLambda`: `localVar`</span></span>  
  
-   <span data-ttu-id="7827c-170">중첩 된 람다 식의 매개 변수:`level2`</span><span class="sxs-lookup"><span data-stu-id="7827c-170">A parameter of the lambda expression in which it is nested: `level2`</span></span>  
  
 <span data-ttu-id="7827c-171">[!code-vb[VbVbalrLambdas #&9;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="7827c-171">[!code-vb[VbVbalrLambdas#9](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]</span></span>  
  
## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="7827c-172">대리자 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="7827c-172">Converting to a Delegate Type</span></span>  
 <span data-ttu-id="7827c-173">람다 식은 호환 되는 대리자 형식으로 암시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-173">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="7827c-174">호환성에 대 한 일반 요구 사항에 대 한 정보를 참조 하십시오. [완화 된 대리자 변환](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-174">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="7827c-175">다음 코드 예제에서는 암시적으로 변환 하는 람다 식을 표시 하는 예를 들어 `Func(Of Integer, Boolean)` 또는 일치 하는 대리자 서명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-175">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>  
  
 <span data-ttu-id="7827c-176">[!code-vb[VbVbalrLambdas #&16;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="7827c-176">[!code-vb[VbVbalrLambdas#16](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]</span></span>  
  
 <span data-ttu-id="7827c-177">다음 코드 예제에서는 암시적으로 변환 하는 람다 식을 보여 줍니다. `Sub(Of Double, String, Double)` 또는 일치 하는 대리자 서명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-177">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>  
  
 <span data-ttu-id="7827c-178">[!code-vb[VbVbalrLambdas&23;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="7827c-178">[!code-vb[VbVbalrLambdas#23](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]</span></span>  
  
 <span data-ttu-id="7827c-179">람다 식은 대리자에 할당할 또는 프로시저에 인수로 전달 하는 경우에 매개 변수 이름을 지정할 수 있지만 형식을 가져오도록 될 대리자에서 해당 데이터 형식은 생략 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-179">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7827c-180">예제</span><span class="sxs-lookup"><span data-stu-id="7827c-180">Examples</span></span>  
  
-   <span data-ttu-id="7827c-181">다음 예제에서는 반환 하는 람다 식을 정의 `True` nullable 인수에 할당된 된 값 및 `False` 해당 값이 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-181">The following example defines a lambda expression that returns `True` if the nullable argument has an assigned value, and `False` if its value is `Nothing`.</span></span>  
  
     <span data-ttu-id="7827c-182">[!code-vb[VbVbalrLambdas #&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="7827c-182">[!code-vb[VbVbalrLambdas#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]</span></span>  
  
-   <span data-ttu-id="7827c-183">다음 예제에서는 배열에서 마지막 요소의 인덱스를 반환 하는 람다 식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7827c-183">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>  
  
     <span data-ttu-id="7827c-184">[!code-vb[VbVbalrLambdas #&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="7827c-184">[!code-vb[VbVbalrLambdas#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7827c-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7827c-185">See Also</span></span>  
 <span data-ttu-id="7827c-186">[프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="7827c-186">[Procedures](./index.md) </span></span>  
<span data-ttu-id="7827c-187"> [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="7827c-187"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="7827c-188"> [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="7827c-188"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="7827c-189"> [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7827c-189"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="7827c-190"> [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7827c-190"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="7827c-191"> [Nullable 값 형식](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span><span class="sxs-lookup"><span data-stu-id="7827c-191"> [Nullable Value Types](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span></span>  
<span data-ttu-id="7827c-192"> [방법: 프로시저에 Visual Basic에서 다른 프로시저 전달](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="7827c-192"> [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span></span>  
<span data-ttu-id="7827c-193"> [방법: 람다 식 만들기](./how-to-create-a-lambda-expression.md) </span><span class="sxs-lookup"><span data-stu-id="7827c-193"> [How to: Create a Lambda Expression](./how-to-create-a-lambda-expression.md) </span></span>  
<span data-ttu-id="7827c-194"> [완화된 대리자 변환](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="7827c-194"> [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span></span>

