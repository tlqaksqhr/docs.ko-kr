---
title: "Function 프로시저 (Visual Basic) | Microsoft 문서"
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
- Function procedures
- return values, function procedures
- Visual Basic code, procedures
- procedures, calling
- procedures, Function procedures
- syntax, function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fb36ee41e4b53f6e690ce5d48d34bbfc9f86c177
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="9a916-102">Function 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a916-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="9a916-103">A `Function` 절차는 일련의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 로 묶인 명령문의 `Function` 및 `End Function` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-103">A `Function` procedure is a series of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="9a916-104">`Function` 프로시저는 작업을 수행한 다음 호출 코드에 제어를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="9a916-105">제어를 반환 하기 호출 코드에도 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="9a916-106">프로시저가 호출 된 문이 실행 될 때마다 시작 후 첫 번째 실행 문에 `Function` 문과 여 첫 번째 `End Function`, `Exit Function`, 또는 `Return` 문을 발견 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="9a916-107">정의할 수는 `Function` 모듈, 클래스 또는 구조체에는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="9a916-108">`Public` 어디에서 나 호출할 수 있습니다 즉 기본적으로, 모듈, 클래스 또는 정의 된 구조에 액세스 권한이 있는 응용 프로그램에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="9a916-109">A `Function` 프로시저와 같은 상수, 변수 또는 호출 코드에 의해 전달 되는 식을 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="9a916-110">선언 구문</span><span class="sxs-lookup"><span data-stu-id="9a916-110">Declaration Syntax</span></span>  
 <span data-ttu-id="9a916-111">선언 구문은 `Function` 절차는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="9a916-112">*한정자* 오버 로드, 재정의 공유 및 숨김 관한 정보와 액세스 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="9a916-113">자세한 내용은 참조 [Function 문의](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="9a916-114">에 대 한와 동일한 방식으로 각 매개 변수를 선언 [Sub 프로시저](./sub-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="9a916-115">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9a916-115">Data Type</span></span>  
 <span data-ttu-id="9a916-116">모든 `Function` 프로시저에는 데이터 형식, 각 변수와 마찬가지로 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="9a916-117">이 데이터 형식은 지정 되는 `As` 절에는 `Function` 하며 문, 함수 호출 코드로 반환 값의 데이터 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="9a916-118">다음 샘플 선언 이러한 경우를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="9a916-119">자세한 내용은 "부분"의 참조 [Function 문의](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="9a916-120">값 반환</span><span class="sxs-lookup"><span data-stu-id="9a916-120">Returning Values</span></span>  
 <span data-ttu-id="9a916-121">값을 `Function` 프로시저에서 전송 하는 호출 하는 코드를 다시 반환 값 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="9a916-122">프로시저는 두 가지 방법 중 하나에서이 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-122">The procedure returns this value in one of two ways:</span></span>  
  
-   <span data-ttu-id="9a916-123">사용 하 여는 `Return` 반환 값 및 반환을 지정 하는 문을 호출 프로그램에 즉시 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="9a916-124">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   <span data-ttu-id="9a916-125">프로시저의 하나 이상의 문에서 함수 이름에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="9a916-126">제어 될 때까지 호출 프로그램에 반환 하지 않는 한 `Exit Function` 또는 `End Function` 문이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="9a916-127">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="9a916-128">함수 이름에는 반환 값을 할당의 장점은 만날 때까지 제어 프로시저에서 반환 되지 않는 한 `Exit Function` 또는 `End Function` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="9a916-129">이 옵션을 사용 하면 예비 값을 할당 하 고 필요한 경우 나중에 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="9a916-130">값을 반환 하는 방법에 대 한 자세한 내용은 참조 [Function 문의](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="9a916-131">배열을 반환 하는 방법에 대 한 정보를 참조 하십시오. [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="9a916-132">호출 구문</span><span class="sxs-lookup"><span data-stu-id="9a916-132">Calling Syntax</span></span>  
 <span data-ttu-id="9a916-133">호출 하는 `Function` 이름과 대입문의 또는 식의 오른쪽에 인수를 포함 하 여 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="9a916-134">선택적 인수가 아닌 모든 인수에 대 한 값을 제공 해야 하 고 인수 목록을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="9a916-135">없는 인수를 제공 하는 경우에 필요에 따라 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="9a916-136">에 대 한 호출에 대 한 구문은 `Function` 절차는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="9a916-137">*lvalue*`=`*functionname* `[(` *argumentlist*    `)]`</span><span class="sxs-lookup"><span data-stu-id="9a916-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="9a916-138">`If ((`*functionname* `[(` *argumentlist* `)] / 3) <=` *식*  `) Then`</span><span class="sxs-lookup"><span data-stu-id="9a916-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="9a916-139">호출 하는 경우는 `Function` 프로시저 않아도 해당 반환 값을 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="9a916-140">그렇지 않으면 함수는 모든 작업을 수행 하 고, 있지만 반환 값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="9a916-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>이 방법으로 흔히 이라고 합니다.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="9a916-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="9a916-142">선언 및 호출의 그림</span><span class="sxs-lookup"><span data-stu-id="9a916-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="9a916-143">다음 `Function` 프로시저 가장 긴 면 또는 다른 두 가지 측면에 대 한 값이 제공 하는 직각 삼각형의 빗변을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 <span data-ttu-id="9a916-144">[!code-vb[VbVbcnProcedures #&1;](./codesnippet/VisualBasic/function-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9a916-144">[!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="9a916-145">다음 예제에서는 호출을 `hypotenuse`합니다.</span><span class="sxs-lookup"><span data-stu-id="9a916-145">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 <span data-ttu-id="9a916-146">[!code-vb[VbVbcnProcedures #&6;](./codesnippet/VisualBasic/function-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="9a916-146">[!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a916-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a916-147">See Also</span></span>  
 <span data-ttu-id="9a916-148">[프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="9a916-148">[Procedures](./index.md) </span></span>  
<span data-ttu-id="9a916-149"> [Sub 프로시저](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="9a916-149"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="9a916-150"> [속성 프로시저](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="9a916-150"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="9a916-151"> [연산자 프로시저](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="9a916-151"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="9a916-152"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="9a916-152"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="9a916-153"> [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="9a916-153"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="9a916-154"> [방법: 값을 반환 하는 프로시저 만들기](./how-to-create-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="9a916-154"> [How to: Create a Procedure that Returns a Value](./how-to-create-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="9a916-155"> [방법: 프로시저에서 값을 반환 합니다.](./how-to-return-a-value-from-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="9a916-155"> [How to: Return a Value from a Procedure](./how-to-return-a-value-from-a-procedure.md) </span></span>  
<span data-ttu-id="9a916-156"> [방법: 값을 반환하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="9a916-156"> [How to: Call a Procedure That Returns a Value](./how-to-call-a-procedure-that-returns-a-value.md)</span></span>
