---
title: Function 프로시저(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: 887c930cb757b012542c97d64a57a62882a2eed3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655537"
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="63a26-102">Function 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63a26-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="63a26-103">A `Function` 절차는 일련의 Visual Basic 문으로 둘러싸인는 `Function` 및 `End Function` 문.</span><span class="sxs-lookup"><span data-stu-id="63a26-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="63a26-104">`Function` 프로시저는 작업을 수행한 다음 호출 코드에 제어를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="63a26-105">제어를 반환 하기 호출 코드에도 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="63a26-106">다음의 첫 번째 실행 문에서로 프로시저가 호출 된 문이 실행 될 때마다 시작는 `Function` 문과 여 첫 번째 `End Function`, `Exit Function`, 또는 `Return` 문을 발견 했습니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="63a26-107">정의할 수는 `Function` 모듈, 클래스 또는 구조체의 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="63a26-108">`Public` 어디에서 나 호출할 수 즉 기본적으로 모듈, 클래스 또는 정의 된 구조체에 액세스 권한이 있는 응용 프로그램에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="63a26-109">A `Function` 프로시저 상수, 변수 또는 호출 코드에 의해 전달 된 식 등의 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="63a26-110">선언 구문</span><span class="sxs-lookup"><span data-stu-id="63a26-110">Declaration Syntax</span></span>  
 <span data-ttu-id="63a26-111">선언 구문이 `Function` 절차는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="63a26-112">*한정자* 오버 로드, 재정의 공유 및 숨김 관한 정보와 액세스 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="63a26-113">자세한 내용은 참조 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="63a26-114">에 대 한 작업을 수행한 동일한 방식으로 각 매개 변수를 선언 [Sub 프로시저](./sub-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="63a26-115">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="63a26-115">Data Type</span></span>  
 <span data-ttu-id="63a26-116">모든 `Function` 프로시저에는 데이터 형식, 각 변수와 마찬가지로 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="63a26-117">이 데이터 형식은 지정 되는 `As` 절에는 `Function` 문 및 함수 호출 코드에 반환 하는 값의 데이터 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="63a26-118">다음 샘플 선언 이러한 경우를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="63a26-119">자세한 내용은의 "부분" 참조 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="63a26-120">값 반환</span><span class="sxs-lookup"><span data-stu-id="63a26-120">Returning Values</span></span>  
 <span data-ttu-id="63a26-121">값을 `Function` 프로시저에서 전송 하는 호출 코드에 다시 반환 값에 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="63a26-122">프로시저는 두 가지 방법 중 하나에서이 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-122">The procedure returns this value in one of two ways:</span></span>  
  
-   <span data-ttu-id="63a26-123">사용 하 여는 `Return` 반환와 반환 값을 지정 하는 문을 호출 프로그램에 즉시 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="63a26-124">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   <span data-ttu-id="63a26-125">프로시저의 하나 이상의 문에서 함수 이름에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="63a26-126">제어 될 때까지 호출 프로그램에 반환 하지 않는 한 `Exit Function` 또는 `End Function` 문이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="63a26-127">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="63a26-128">함수 이름에 반환 값을 할당의 장점은입니다에 도달할 때까지 제어 프로시저에서 반환 하지 않는 한 `Exit Function` 또는 `End Function` 문.</span><span class="sxs-lookup"><span data-stu-id="63a26-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="63a26-129">이 예비 값을 할당 하 고 필요 하면 나중에 조정 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="63a26-130">값을 반환 하는 방법에 대 한 자세한 내용은 참조 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="63a26-131">배열을 반환 하는 방법에 대 한 정보를 참조 하십시오. [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="63a26-132">호출 구문</span><span class="sxs-lookup"><span data-stu-id="63a26-132">Calling Syntax</span></span>  
 <span data-ttu-id="63a26-133">호출 된 `Function` 프로시저 이름 및 인수는 식 또는 대입문의 오른쪽을 포함 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="63a26-134">모든 인수는 옵션에 대 한 값을 제공 해야 하 고 인수 목록을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="63a26-135">인수를 제공 하는 경우 괄호를 선택적으로 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="63a26-136">에 대 한 호출에 대 한 구문은 `Function` 절차는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="63a26-137">*lvalue*`=`*functionname* `[(` *argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="63a26-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="63a26-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=` *식* `) Then`</span><span class="sxs-lookup"><span data-stu-id="63a26-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="63a26-139">호출 하는 경우는 `Function` 프로시저 않아도 해당 반환 값을 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="63a26-140">이렇게 하지 않으면 함수는 모든 작업이 수행 되었는지, 있지만 반환 값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="63a26-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 이런이 방식으로 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="63a26-142">선언 및 호출의 그림</span><span class="sxs-lookup"><span data-stu-id="63a26-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="63a26-143">다음 `Function` 프로시저 가장 긴 면 또는 다른 두 변에 대 한 값을 지정 하는 직각 삼각형의 빗변을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 <span data-ttu-id="63a26-144">다음 예제에서는 호출을 `hypotenuse`합니다.</span><span class="sxs-lookup"><span data-stu-id="63a26-144">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="63a26-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63a26-145">See Also</span></span>  
 [<span data-ttu-id="63a26-146">절차</span><span class="sxs-lookup"><span data-stu-id="63a26-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="63a26-147">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="63a26-147">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="63a26-148">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="63a26-148">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="63a26-149">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="63a26-149">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="63a26-150">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="63a26-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="63a26-151">Function 문</span><span class="sxs-lookup"><span data-stu-id="63a26-151">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="63a26-152">방법: 값을 반환하는 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="63a26-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="63a26-153">방법: 프로시저에서 값 반환</span><span class="sxs-lookup"><span data-stu-id="63a26-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)  
 [<span data-ttu-id="63a26-154">방법: 값을 반환하는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="63a26-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
