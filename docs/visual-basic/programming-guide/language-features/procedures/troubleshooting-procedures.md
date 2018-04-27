---
title: 프로시저 문제 해결(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e54c965dc15131734be2c5bcfe04ad70292bf23
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="troubleshooting-procedures-visual-basic"></a><span data-ttu-id="68e07-102">프로시저 문제 해결(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68e07-102">Troubleshooting Procedures (Visual Basic)</span></span>
<span data-ttu-id="68e07-103">이 페이지는 프로시저를 작업할 때 발생할 수 있는 몇 가지 일반적인 문제를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-103">This page lists some common problems that can occur when working with procedures.</span></span>  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a><span data-ttu-id="68e07-104">Function 프로시저에서 배열 형식 반환</span><span class="sxs-lookup"><span data-stu-id="68e07-104">Returning an Array Type from a Function Procedure</span></span>  
 <span data-ttu-id="68e07-105">경우는 `Function` 프로시저가 반환 배열 데이터 형식, 사용할 수 없습니다는 `Function` 이름 배열의 요소에 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-105">If a `Function` procedure returns an array data type, you cannot use the `Function` name to store values in the elements of the array.</span></span> <span data-ttu-id="68e07-106">이 작업을 수행 하려고 하면 컴파일러로 해석에 대 한 호출에서 `Function`합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-106">If you attempt to do this, the compiler interprets it as a call to the `Function`.</span></span> <span data-ttu-id="68e07-107">다음 예제에서는 컴파일러 오류가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-107">The following example generates compiler errors.</span></span>  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 <span data-ttu-id="68e07-108">`' The following statement generates a`   `COMPILER ERROR`  `.`</span><span class="sxs-lookup"><span data-stu-id="68e07-108">`' The following statement generates a`   `COMPILER ERROR`  `.`</span></span>  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 <span data-ttu-id="68e07-109">`' The following statement generates a`   `COMPILER ERROR`  `.`</span><span class="sxs-lookup"><span data-stu-id="68e07-109">`' The following statement generates a`   `COMPILER ERROR`  `.`</span></span>  
  
 `Return allOnes()`  
  
 `End Function`  
  
 <span data-ttu-id="68e07-110">문이 `allOnes(i) = 1` 호출 하기 때문에 컴파일러 오류가 생성 `allOnes` 의 데이터 형식이 잘못 된 인수가 지정 된 (단일 `Integer` 대신는 `Integer` 배열)입니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-110">The statement `allOnes(i) = 1` generates a compiler error because it appears to call `allOnes` with an argument of the wrong data type (a singleton `Integer` instead of an `Integer` array).</span></span> <span data-ttu-id="68e07-111">문이 `Return allOnes()` 호출 하기 때문에 컴파일러 오류가 생성 `allOnes` 인수가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-111">The statement `Return allOnes()` generates a compiler error because it appears to call `allOnes` with no argument.</span></span>  
  
 <span data-ttu-id="68e07-112">**올바른 방법은:** 반환 되는 배열의 요소를 수정할 수 있으려면 내부 배열 지역 변수로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-112">**Correct Approach:** To be able to modify the elements of an array that is to be returned, define an internal array as a local variable.</span></span> <span data-ttu-id="68e07-113">다음 예제에서는 오류 없이 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-113">The following example compiles without error.</span></span>  
  
 [!code-vb[VbVbcnProcedures#66](./codesnippet/VisualBasic/troubleshooting-procedures_1.vb)]  
  
## <a name="argument-not-being-modified-by-procedure-call"></a><span data-ttu-id="68e07-114">수정 되지 인수 프로시저 호출으로</span><span class="sxs-lookup"><span data-stu-id="68e07-114">Argument Not Being Modified by Procedure Call</span></span>  
 <span data-ttu-id="68e07-115">호출 코드의 기반이 되는 프로그래밍 요소를 변경 하는 절차를 허용 하려는 경우 참조로 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-115">If you intend to allow a procedure to change a programming element underlying an argument in the calling code, you must pass it by reference.</span></span> <span data-ttu-id="68e07-116">하지만 값으로 전달 하는 경우에 프로시저 참조 형식 인수 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-116">But a procedure can access the elements of a reference type argument even if you pass it by value.</span></span>  
  
-   <span data-ttu-id="68e07-117">**내부 변수**합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-117">**Underlying Variable**.</span></span> <span data-ttu-id="68e07-118">프로시저는 내부 변수 요소의 값을 대체 하는 절차를 허용 하려면 매개 변수를 선언 해야 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-118">To allow the procedure to replace the value of the underlying variable element itself, the procedure must declare the parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="68e07-119">또한 호출 하는 코드 묶지 마십시오 인수에 있는 괄호 안에 재정의 되기 때문에 `ByRef` 전달 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-119">Also, the calling code must not enclose the argument in parentheses, because that would override the `ByRef` passing mechanism.</span></span>  
  
-   <span data-ttu-id="68e07-120">**형식 요소 참조**합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-120">**Reference Type Elements**.</span></span> <span data-ttu-id="68e07-121">매개 변수를 선언 하는 경우 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md), 프로시저는 내부 변수 요소를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-121">If you declare a parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md), the procedure cannot modify the underlying variable element itself.</span></span> <span data-ttu-id="68e07-122">그러나 인수 참조 형식인 경우 변수의 값을 바꿀 수 없습니다 없지만 프로시저 가리키는, 개체의 멤버를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-122">However, if the argument is a reference type, the procedure can modify the members of the object to which it points, even though it cannot replace the variable's value.</span></span> <span data-ttu-id="68e07-123">예를 들어 인수는 배열 변수, 프로시저, 새 배열을 할당할 수 없습니다 하지만 해당 요소 중 하나 이상을 변경할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-123">For example, if the argument is an array variable, the procedure cannot assign a new array to it, but it can change one or more of its elements.</span></span> <span data-ttu-id="68e07-124">변경 된 요소에서 호출 코드의 내부 배열 변수에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-124">The changed elements are reflected in the underlying array variable in the calling code.</span></span>  
  
 <span data-ttu-id="68e07-125">다음 예제에서는 요소를 값으로 배열 변수를 받아을 작업을 수행 하는 두 가지 절차를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-125">The following example defines two procedures that take an array variable by value and operate on its elements.</span></span> <span data-ttu-id="68e07-126">프로시저 `increase` 각 요소에 1을 더 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-126">Procedure `increase` simply adds one to each element.</span></span> <span data-ttu-id="68e07-127">프로시저 `replace` 매개 변수는 새 배열을 할당 `a()` 다음 각 요소에 1을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-127">Procedure `replace` assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="68e07-128">그러나 캡처하기 영향을 주지 않습니다 호출 코드의 내부 배열 변수 이므로 `a()` 선언 `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-128">However, the reassignment does not affect the underlying array variable in the calling code because `a()` is declared `ByVal`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/troubleshooting-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/troubleshooting-procedures_3.vb)]  
  
 <span data-ttu-id="68e07-129">다음 예제에 대 한 호출에서는 `increase` 및 `replace`합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-129">The following example makes calls to `increase` and `replace`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/troubleshooting-procedures_4.vb)]  
  
 <span data-ttu-id="68e07-130">첫 번째 `MsgBox` 표시 호출 "increase(n) 후: 11, 21, 31, 41"입니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="68e07-131">때문에 `n` 참조 형식인 `increase` 전달 되는 경우에 해당 멤버를 변경할 수 `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-131">Because `n` is a reference type, `increase` can change its members, even though it is passed `ByVal`.</span></span>  
  
 <span data-ttu-id="68e07-132">두 번째 `MsgBox` 표시 호출 "replace(n) 후: 11, 21, 31, 41"입니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-132">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="68e07-133">때문에 `n` 전달 `ByVal`, `replace` 변수를 수정할 수 없습니다 `n` 새 배열을 할당 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-133">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` by assigning a new array to it.</span></span> <span data-ttu-id="68e07-134">때 `replace` 배열의 새 인스턴스를 만듭니다. `k` 로컬 변수에 할당 하 고 `a`에 대 한 참조를 잃을 `n` 호출 코드에 의해 전달 된입니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-134">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="68e07-135">멤버를 늘리면 `a`, 지역 배열만 `k` 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-135">When it increments the members of `a`, only the local array `k` is affected.</span></span>  
  
 <span data-ttu-id="68e07-136">**올바른 방법은:** 자체는 내부 변수 요소를 수정할 수 있으려면 참조로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-136">**Correct Approach:** To be able to modify an underlying variable element itself, pass it by reference.</span></span> <span data-ttu-id="68e07-137">다음 예제에서는 선언에 변화를 보여 줍니다. `replace` 배열로 ब द ल 호출 코드로 바꾸는 것을 허용 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-137">The following example shows the change in the declaration of `replace` that allows it to replace one array with another in the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#64](./codesnippet/VisualBasic/troubleshooting-procedures_5.vb)]  
  
## <a name="unable-to-define-an-overload"></a><span data-ttu-id="68e07-138">오버 로드를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-138">Unable to Define an Overload</span></span>  
 <span data-ttu-id="68e07-139">프로시저의 오버 로드 된 버전을 정의 하려는 경우에 같지만 시그니처를 다르게 동일한 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-139">If you want to define an overloaded version of a procedure, you must use the same name but a different signature.</span></span> <span data-ttu-id="68e07-140">컴파일러는 동일한 서명으로 오버 로드에서 선언 구분할 수 없습니다, 하는 경우 오류가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-140">If the compiler cannot differentiate your declaration from an overload with the same signature, it generates an error.</span></span>  
  
 <span data-ttu-id="68e07-141">*서명* 프로시저의 프로시저 이름과 매개 변수 목록에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-141">The *signature* of a procedure is determined by the procedure name and the parameter list.</span></span> <span data-ttu-id="68e07-142">각 오버 로드는 다른 모든 오버 로드와 동일한 이름이 해야 하지만 서명의 다른 구성 요소 중 하나 이상 있는 모든 대상에서 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-142">Each overload must have the same name as all the other overloads but must differ from all of them in at least one of the other components of the signature.</span></span> <span data-ttu-id="68e07-143">자세한 내용은 참조 [프로시저 오버 로드](./procedure-overloading.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-143">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="68e07-144">다음 항목을 매개 변수 목록에 포함 되어 있더라도 없는 프로시저의 서명의 구성 요소:</span><span class="sxs-lookup"><span data-stu-id="68e07-144">The following items, even though they pertain to the parameter list, are not components of a procedure's signature:</span></span>  
  
-   <span data-ttu-id="68e07-145">프로시저 한정자 키워드와 같은 `Public`, `Shared`, 및 `Static`</span><span class="sxs-lookup"><span data-stu-id="68e07-145">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>  
  
-   <span data-ttu-id="68e07-146">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="68e07-146">Parameter names</span></span>  
  
-   <span data-ttu-id="68e07-147">매개 변수 한정자 키워드와 같은 `ByRef` 및 `Optional`</span><span class="sxs-lookup"><span data-stu-id="68e07-147">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>  
  
-   <span data-ttu-id="68e07-148">반환 값 (변환 연산자 제외)의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="68e07-148">The data type of the return value (except for a conversion operator)</span></span>  
  
 <span data-ttu-id="68e07-149">하나 이상의 이전 항목만 변경 하 여 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-149">You cannot overload a procedure by varying only one or more of the preceding items.</span></span>  
  
 <span data-ttu-id="68e07-150">**올바른 방법은:** 프로시저 오버 로드를 정의할 수 있으려면 시그니처를 다르게 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-150">**Correct Approach:** To be able to define a procedure overload, you must vary the signature.</span></span> <span data-ttu-id="68e07-151">이름이 같은 사용 해야 하므로 번호, 순서 또는 데이터 유형의 매개 변수 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-151">Because you must use the same name, you must vary the number, order, or data types of the parameters.</span></span> <span data-ttu-id="68e07-152">제네릭 프로시저가 형식 매개 변수 수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-152">In a generic procedure, you can vary the number of type parameters.</span></span> <span data-ttu-id="68e07-153">변환 연산자에서 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md))를 반환 형식을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-153">In a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)), you can vary the return type.</span></span>  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="68e07-154">선택적으로 확인 및 ParamArray 인수 오버 로드</span><span class="sxs-lookup"><span data-stu-id="68e07-154">Overload Resolution with Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="68e07-155">하나 이상의 프로시저 오버 로드 된 경우 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수 또는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수 중 하나를 중복을 피해 야 할는 *암시적 오버 로드*합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-155">If you are overloading a procedure with one or more [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameters or a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you must avoid duplicating any of the *implicit overloads*.</span></span> <span data-ttu-id="68e07-156">자세한 내용은 참조 [프로시저 오버 로드에 대 한 고려 사항](./considerations-in-overloading-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-156">For information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="calling-a-wrong-version-of-an-overloaded-procedure"></a><span data-ttu-id="68e07-157">잘못 된 버전의 오버 로드 된 프로시저를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-157">Calling a Wrong Version of an Overloaded Procedure</span></span>  
 <span data-ttu-id="68e07-158">프로시저에 있는 여러 오버 로드 된 버전을 모든 매개 변수 목록은 잘 알고 있어야 하 고 Visual Basic에서 오버 로드 간의 호출을 확인 하는 방법을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-158">If a procedure has several overloaded versions, you should be familiar with all their parameter lists and understand how Visual Basic resolves calls among the overloads.</span></span> <span data-ttu-id="68e07-159">그렇지 않은 경우 원하지 않은 오버 로드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-159">Otherwise you could call an overload other than the intended one.</span></span>  
  
 <span data-ttu-id="68e07-160">호출 하려는 오버 로드를 확인 한 다음 규칙을 준수 해야:</span><span class="sxs-lookup"><span data-stu-id="68e07-160">When you have determined which overload you want to call, be careful to observe the following rules:</span></span>  
  
-   <span data-ttu-id="68e07-161">올바른 수의 인수를 올바른 순서로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-161">Supply the correct number of arguments, and in the correct order.</span></span>  
  
-   <span data-ttu-id="68e07-162">이상적으로 인수가 정확히 동일한 데이터 형식을 해당 매개 변수의 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-162">Ideally, your arguments should have the exact same data types as the corresponding parameters.</span></span> <span data-ttu-id="68e07-163">어떤 경우 든, 각 인수의 데이터 형식을 해당 매개 변수를 확장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-163">In any case, the data type of each argument must widen to that of its corresponding parameter.</span></span> <span data-ttu-id="68e07-164">된 경우에 마찬가지입니다는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 로 설정 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-164">This is true even with the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) set to `Off`.</span></span> <span data-ttu-id="68e07-165">오버 로드는 인수 목록에서의 축소 변환이 필요한 호출할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-165">If an overload requires any narrowing conversion from your argument list, that overload is not eligible to be called.</span></span>  
  
-   <span data-ttu-id="68e07-166">확대 변환에 필요한 인수를 제공 하는 경우 해당 데이터 형식이 해당 매개 변수 데이터 형식에 최대한 가까운를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-166">If you supply arguments that require widening, make their data types as close as possible to the corresponding parameter data types.</span></span> <span data-ttu-id="68e07-167">두 개 이상의 오버 로드는 인수 데이터 형식과 수락 컴파일러가 확대 변환 부분이 가장 적은 호출 하는 오버 로드를 호출 하 여 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-167">If two or more overloads accept your argument data types, the compiler resolves your call to the overload that calls for the least amount of widening.</span></span>  
  
 <span data-ttu-id="68e07-168">사용 하 여 데이터 형식 불일치 가능성을 줄일 수는 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 인수를 준비할 때 변환 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-168">You can reduce the chance of data type mismatches by using the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) conversion keyword when preparing your arguments.</span></span>  
  
### <a name="overload-resolution-failure"></a><span data-ttu-id="68e07-169">오버 로드 확인 실패</span><span class="sxs-lookup"><span data-stu-id="68e07-169">Overload Resolution Failure</span></span>  
 <span data-ttu-id="68e07-170">오버 로드 된 프로시저를 호출 하면 컴파일러에서 오버 로드 중 하나만 남기고 모두 제거 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-170">When you call an overloaded procedure, the compiler attempts to eliminate all but one of the overloads.</span></span> <span data-ttu-id="68e07-171">성공 하면 해당 오버 로드에 대 한 호출을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-171">If it succeeds, it resolves the call to that overload.</span></span> <span data-ttu-id="68e07-172">모든 오버 로드를 제거 하거나 단일 후보 오버 로드가 줄일 수 없을 경우 오류가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-172">If it eliminates all the overloads, or if it cannot reduce the eligible overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="68e07-173">다음 예제에서는 오버 로드 확인 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-173">The following example illustrates the overload resolution process.</span></span>  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/troubleshooting-procedures_6.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/troubleshooting-procedures_7.vb)]  
  
 <span data-ttu-id="68e07-174">첫 번째 호출에서 컴파일러는 첫 번째 오버 로드를 제거 하기 때문에 첫 번째 인수의 형식 (`Short`) 해당 매개 변수의 형식으로 축소 (`Byte`).</span><span class="sxs-lookup"><span data-stu-id="68e07-174">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="68e07-175">두 번째 오버 로드에 각 인수를 입력 하기 때문에 다음 세 번째 오버 로드를 제거 (`Short` 및 `Single`) 세 번째 오버 로드에서 해당 형식으로 확장 되는지를 (`Integer` 및 `Single`).</span><span class="sxs-lookup"><span data-stu-id="68e07-175">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="68e07-176">두 번째 오버 로드 컴파일러 호출에 사용 되므로 적은 확대 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-176">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="68e07-177">두 번째 호출에서 컴파일러 축소 변환을 기반으로 오버 로드를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-177">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="68e07-178">적은 확대 인수 형식의 두 번째 오버 로드를 호출할 수 있으므로 첫 번째 호출에서와 같은 이유로 세 번째 오버 로드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-178">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="68e07-179">그러나 컴파일러는 첫 번째 및 두 번째 오버 로드 간의 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-179">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="68e07-180">각각 다른의 해당 형식으로 확대 되는 하나의 정의 된 매개 변수 형식을 갖는 (`Byte` 를 `Short`, 하지만 `Single` 를 `Double`).</span><span class="sxs-lookup"><span data-stu-id="68e07-180">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="68e07-181">따라서 컴파일러는 오버 로드 확인 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-181">The compiler therefore generates an overload resolution error.</span></span>  
  
 <span data-ttu-id="68e07-182">**올바른 방법은:** 를 명확 하 게 오버 로드 된 프로시저 호출을 사용 하 여 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 매개 변수 형식과 인수 데이터 형식과 일치 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-182">**Correct Approach:** To be able to call an overloaded procedure without ambiguity, use [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to match the argument data types to the parameter types.</span></span> <span data-ttu-id="68e07-183">다음 예제에 대 한 호출에서는 `z` 두 번째 오버 로드를 확인 하 게 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-183">The following example shows a call to `z` that forces resolution to the second overload.</span></span>  
  
 [!code-vb[VbVbcnProcedures#65](./codesnippet/VisualBasic/troubleshooting-procedures_8.vb)]  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="68e07-184">선택적으로 확인 및 ParamArray 인수 오버 로드</span><span class="sxs-lookup"><span data-stu-id="68e07-184">Overload Resolution with Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="68e07-185">마지막 매개 변수가 선언 된 점을 제외 하 고 프로시저의 두 개의 오버 로드 시그니처가 같은 경우 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) 하나 및 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 컴파일러 해당 프로시저에 대 한 호출을 해결 하 고 다른 일치 하는 가장 가까운 항목을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-185">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure according to the closest match.</span></span> <span data-ttu-id="68e07-186">자세한 내용은 참조 [오버 로드 확인](./overload-resolution.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="68e07-186">For more information, see [Overload Resolution](./overload-resolution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68e07-187">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68e07-187">See Also</span></span>  
 [<span data-ttu-id="68e07-188">절차</span><span class="sxs-lookup"><span data-stu-id="68e07-188">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="68e07-189">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="68e07-189">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="68e07-190">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="68e07-190">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="68e07-191">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="68e07-191">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="68e07-192">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="68e07-192">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="68e07-193">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="68e07-193">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="68e07-194">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="68e07-194">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="68e07-195">프로시저를 오버로드할 때 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="68e07-195">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="68e07-196">오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="68e07-196">Overload Resolution</span></span>](./overload-resolution.md)
