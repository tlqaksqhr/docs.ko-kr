---
title: "방법: 람다 식 (Visual Basic) 만들기 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
caps.latest.revision: 27
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: edd475490dce81ff9cca32b5f9a5090d99f4d80d
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="b620c-102">방법: 람다 식 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b620c-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="b620c-103">A *람다 식을* 은 함수 또는 서브루틴에 이름이 없습니다입니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="b620c-104">람다 식은 대리자 형식이 유효한 모든 곳에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="b620c-105">한 줄 람다 식 함수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="b620c-105">To create a single-line lambda expression function</span></span>  
  
1.  <span data-ttu-id="b620c-106">대리자 형식을 사용할 수 있는 모든 상황에서 키워드를 입력 `Function`다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="b620c-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="b620c-107">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="b620c-108">괄호로 직후 `Function`를 함수 매개 변수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="b620c-109">뒤에 이름을 지정 하지 않으면 `Function`합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="b620c-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="b620c-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3.  <span data-ttu-id="b620c-111">매개 변수 목록 다음 단일 식 함수 본문으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="b620c-112">식이 계산 되는 값에는 함수에서 반환한 값이입니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="b620c-113">사용 하지 않는 한 `As` 절을 반환 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     <span data-ttu-id="b620c-114">[!code-vb[VbVbalrLambdas #&1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b620c-114">[!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]</span></span>  
  
     <span data-ttu-id="b620c-115">정수 인수를 전달 하 람다 식을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-115">You call the lambda expression by passing in an integer argument.</span></span>  
  
     <span data-ttu-id="b620c-116">[!code-vb[VbVbalrLambdas #&2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b620c-116">[!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]</span></span>  
  
4.  <span data-ttu-id="b620c-117">또는 동일한 결과 다음 예제에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-117">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     <span data-ttu-id="b620c-118">[!code-vb[VbVbalrLambdas #&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b620c-118">[!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="b620c-119">한 줄 람다 식 서브루틴을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b620c-119">To create a single-line lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="b620c-120">대리자 형식을 사용할 수 있는 모든 상황에서 키워드를 입력 `Sub`다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-120">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="b620c-121">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="b620c-121">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="b620c-122">괄호로 직후 `Sub`, 서브루틴의 매개 변수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-122">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="b620c-123">뒤에 이름을 지정 하지 않으면 `Sub`합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-123">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="b620c-124">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="b620c-124">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="b620c-125">매개 변수 목록 다음 단일 문을 서브루틴의 본문으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-125">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     <span data-ttu-id="b620c-126">[!code-vb[VbVbalrLambdas #&17;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="b620c-126">[!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]</span></span>  
  
     <span data-ttu-id="b620c-127">문자열 인수를 전달 하 람다 식을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-127">You call the lambda expression by passing in a string argument.</span></span>  
  
     <span data-ttu-id="b620c-128">[!code-vb[VbVbalrLambdas #&18;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="b620c-128">[!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]</span></span>  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="b620c-129">여러 줄 람다 식 함수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="b620c-129">To create a multiline lambda expression function</span></span>  
  
1.  <span data-ttu-id="b620c-130">대리자 형식을 사용할 수 있는 모든 상황에서 키워드를 입력 `Function`다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-130">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="b620c-131">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="b620c-131">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="b620c-132">괄호로 직후 `Function`를 함수 매개 변수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-132">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="b620c-133">뒤에 이름을 지정 하지 않으면 `Function`합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-133">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="b620c-134">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="b620c-134">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3.  <span data-ttu-id="b620c-135">Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-135">Press ENTER.</span></span> <span data-ttu-id="b620c-136">`End Function` 문이 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-136">The `End Function` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="b620c-137">함수 본문 내에서 식을 만들고 값을 반환 하는 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-137">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="b620c-138">사용 하지 않는 한 `As` 절을 반환 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-138">You do not use an `As` clause to specify the return type.</span></span>  
  
     <span data-ttu-id="b620c-139">[!code-vb[VbVbalrLambdas #&19;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="b620c-139">[!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]</span></span>  
  
     <span data-ttu-id="b620c-140">정수 인수를 전달 하 람다 식을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-140">You call the lambda expression by passing in an integer argument.</span></span>  
  
     <span data-ttu-id="b620c-141">[!code-vb[VbVbalrLambdas #&20;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="b620c-141">[!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]</span></span>  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="b620c-142">여러 줄 람다 식 서브루틴을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b620c-142">To create a multiline lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="b620c-143">대리자 형식을 사용할 수 있는 모든 상황에서 키워드를 입력 `Sub`다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-143">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="b620c-144">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="b620c-144">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="b620c-145">괄호로 직후 `Sub`, 서브루틴의 매개 변수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-145">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="b620c-146">뒤에 이름을 지정 하지 않으면 `Sub`합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-146">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="b620c-147">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="b620c-147">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="b620c-148">Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-148">Press ENTER.</span></span> <span data-ttu-id="b620c-149">`End Sub` 문이 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-149">The `End Sub` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="b620c-150">함수 본문 내에서 서브루틴 호출 될 때 실행 하는 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-150">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     <span data-ttu-id="b620c-151">[!code-vb[VbVbalrLambdas #&21;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="b620c-151">[!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]</span></span>  
  
     <span data-ttu-id="b620c-152">문자열 인수를 전달 하 람다 식을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-152">You call the lambda expression by passing in a string argument.</span></span>  
  
     <span data-ttu-id="b620c-153">[!code-vb[VbVbalrLambdas #&22;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="b620c-153">[!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b620c-154">예제</span><span class="sxs-lookup"><span data-stu-id="b620c-154">Example</span></span>  
 <span data-ttu-id="b620c-155">람다 식의 일반적인 사용 되는 형식의 매개 변수에 대해 인수로 전달 될 수 있는 함수를 정의 하는 `Delegate`합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-155">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="b620c-156">다음 예제에서는 <xref:System.Diagnostics.Process.GetProcesses%2A>메서드는 로컬 컴퓨터에서 실행 중인 프로세스의 배열을 반환 합니다.</xref:System.Diagnostics.Process.GetProcesses%2A></span><span class="sxs-lookup"><span data-stu-id="b620c-156">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="b620c-157"><xref:System.Linq.Enumerable.Where%2A>메서드에서 <xref:System.Linq.Enumerable>클래스 필요는 `Boolean` 인수로 위임.</xref:System.Linq.Enumerable> </xref:System.Linq.Enumerable.Where%2A></span><span class="sxs-lookup"><span data-stu-id="b620c-157">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="b620c-158">예에서 람다 식이 해당 용도로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-158">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="b620c-159">반환 `True` 각 프로세스에 대 한 스레드 한 개만 있으며에서 선택 됩니다 `filteredList`합니다.</span><span class="sxs-lookup"><span data-stu-id="b620c-159">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 <span data-ttu-id="b620c-160">[!code-vb[VbVbalrLambdas #&10;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="b620c-160">[!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]</span></span>  
  
 <span data-ttu-id="b620c-161">앞의 예제는 작성 된 다음 코드와 동일한 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] 구문:</span><span class="sxs-lookup"><span data-stu-id="b620c-161">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] syntax:</span></span>  
  
 <span data-ttu-id="b620c-162">[!code-vb[VbVbalrLambdas #&11;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="b620c-162">[!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b620c-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b620c-163">See Also</span></span>  
 <span data-ttu-id="b620c-164"><xref:System.Linq.Enumerable></xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="b620c-164"><xref:System.Linq.Enumerable></span></span>   
<span data-ttu-id="b620c-165"> [람다 식](./lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="b620c-165"> [Lambda Expressions](./lambda-expressions.md) </span></span>  
<span data-ttu-id="b620c-166"> [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b620c-166"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="b620c-167"> [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b620c-167"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="b620c-168"> [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="b620c-168"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="b620c-169"> [방법: 프로시저에 Visual Basic에서 다른 프로시저 전달](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="b620c-169"> [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span></span>  
<span data-ttu-id="b620c-170"> [Delegate 문](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b620c-170"> [Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="b620c-171"> [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="b620c-171"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
