---
title: 프로시저를 오버로드할 때 고려해야 할 사항(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
ms.openlocfilehash: e1768d0ac03cb6730c4337d7476ae163e75adfd3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654332"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="800d1-102">프로시저를 오버로드할 때 고려해야 할 사항(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="800d1-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="800d1-103">프로시저를 오버 로드할 때는 다른 사용 해야 *서명* 각 오버 로드 된 버전에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="800d1-104">일반적으로 즉, 각 버전에는 다른 매개 변수 목록을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="800d1-105">자세한 내용은 "다른 서명"의 참조 [프로시저 오버 로드](./procedure-overloading.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="800d1-106">오버 로드할 수 있습니다는 `Function` 사용 하 여 프로시저는 `Sub` 프로시저를 반대로 시그니처가 다르면를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="800d1-107">두 개의 오버 로드가 없습니다는 다를 하나에 값을 반환 하 고 다른 때는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="800d1-108">같은 방법으로 프로시저 오버 로드를 속성에 오버 로드와 동일한 제한이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="800d1-109">그러나 프로시저를 오버 로드할 수 없습니다 또는 그 반대로 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="800d1-110">오버 로드 된 버전에 대 한 대안</span><span class="sxs-lookup"><span data-stu-id="800d1-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="800d1-111">경우에 따라 해야 오버 로드 된 버전에 대 한 대안 특히의 수에는 변수 또는 인수를 생략할 경우.</span><span class="sxs-lookup"><span data-stu-id="800d1-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="800d1-112">선택적 인수 하 여 모든 언어에서 지원 되는 것은 아니며 및 매개 변수 배열이 Visual Basic로 제한 되어 염두에 둬야 합니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to Visual Basic.</span></span> <span data-ttu-id="800d1-113">여러 다른 언어로 작성 된 코드에서 호출 될 가능성이 있는 프로시저를 작성 하는 경우 버전 제공 시 뛰어난 유연성 오버 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="800d1-114">오버 로드 및 선택적 인수</span><span class="sxs-lookup"><span data-stu-id="800d1-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="800d1-115">호출 코드에서 필요에 따라 제공 하거나 하나 이상의 인수를 생략할 수, 하는 경우 여러 오버 로드 된 버전을 정의 또는 선택적 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="800d1-116">오버 로드 된 버전을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="800d1-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="800d1-117">다음과 같은 경우에는 일련의 오버 로드 된 버전을 정의 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="800d1-118">프로시저 코드의 논리는 호출 코드 제공 되는 선택적 인수 여부에 따라 크게 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
-   <span data-ttu-id="800d1-119">프로시저 코드는 호출 코드가 선택적 인수를 제공 했는지 여부에 안정적으로 테스트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="800d1-120">이 경우, 예를 들어, 기본 값에 대 한 가능한 후보 없는 경우 호출 코드 되지 않을을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="800d1-121">선택적 매개 변수를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="800d1-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="800d1-122">다음과 같은 경우에 하나 이상의 선택적 매개 변수를 선호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
-   <span data-ttu-id="800d1-123">필요한 작업만 호출 하는 코드는 선택적 인수를 제공 하지 않는 경우 기본값에 매개 변수를 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="800d1-124">이 경우 프로시저 코드 수 덜 복잡 하 게 하나 이상의 단일 버전을 정의 하는 경우 `Optional` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="800d1-125">자세한 내용은 참조 [선택적 매개 변수](./optional-parameters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="800d1-126">오버 로드와 ParamArrays</span><span class="sxs-lookup"><span data-stu-id="800d1-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="800d1-127">호출 코드에서 가변 개수의 인수를 전달할 수, 하는 경우 여러 오버 로드 된 버전을 정의 하거나 매개 변수 배열을 사용 하 여 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="800d1-128">오버 로드 된 버전을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="800d1-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="800d1-129">다음과 같은 경우에는 일련의 오버 로드 된 버전을 정의 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="800d1-130">호출 코드 되지을 통과 하는지 적은 수의 값 보다 많은 매개 변수 배열에 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
-   <span data-ttu-id="800d1-131">프로시저 코드의 논리는 호출 코드에서 전달 값의 개수에 따라 크게 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
-   <span data-ttu-id="800d1-132">호출 코드는 서로 다른 데이터 형식의 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="800d1-133">매개 변수 배열을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="800d1-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="800d1-134">여는 것이 좋습니다는 `ParamArray` 다음과 같은 경우에는 매개 변수:</span><span class="sxs-lookup"><span data-stu-id="800d1-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
-   <span data-ttu-id="800d1-135">호출 코드에서 매개 변수 배열에 전달할 수 값의 개수를 예측할 수 없는 및 많은 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
-   <span data-ttu-id="800d1-136">면 프로시저 논리가 인계 호출 코드에서 전달 기본적으로 모든 값에 같은 작업을 수행 하는 모든 값을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="800d1-137">자세한 내용은 참조 [매개 변수 배열](./parameter-arrays.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="800d1-138">선택적 매개 변수에 대 한 암시적 오버 로드</span><span class="sxs-lookup"><span data-stu-id="800d1-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="800d1-139">프로시저는 [옵션](../../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수는 선택적 매개 변수를 사용 하 고 하지 않는 두 개의 오버 로드 된 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="800d1-140">이 중 하나에 해당 하는 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="800d1-141">다음 선언을 이러한 경우를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-141">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 <span data-ttu-id="800d1-142">둘 이상의 선택적 매개 변수를 사용 하 여 프로시저, 앞의 예제에서와 비슷한 논리에 의해에 도착 한 암시적 오버 로드 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-142">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="800d1-143">ParamArray 매개 변수에 대 한 암시적 오버 로드</span><span class="sxs-lookup"><span data-stu-id="800d1-143">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="800d1-144">컴파일러에 사용 하 여 프로시저 있다고 간주는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 무한 어떤 호출 코드에서 전달 매개 변수 배열에 다음과 같이 서로 다른 오버 로드 중에 매개 변수:</span><span class="sxs-lookup"><span data-stu-id="800d1-144">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
-   <span data-ttu-id="800d1-145">호출 코드에 인수를 제공 하지 않는 하나의 오버 로드는 `ParamArray`</span><span class="sxs-lookup"><span data-stu-id="800d1-145">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
-   <span data-ttu-id="800d1-146">호출 코드 1 차원 배열을 제공 하는 경우 하나의 오버 로드는 `ParamArray` 요소 형식</span><span class="sxs-lookup"><span data-stu-id="800d1-146">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
-   <span data-ttu-id="800d1-147">양의 정수에 대해 하나의 오버 로드에 대 한 호출 코드를 해당 수의 각 인수를 제공 하는 경우는 `ParamArray` 요소 형식</span><span class="sxs-lookup"><span data-stu-id="800d1-147">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="800d1-148">다음 선언을 이러한 암시적 오버 로드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-148">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 <span data-ttu-id="800d1-149">매개 변수 배열에 대 한 1 차원 배열을 사용 하는 매개 변수 목록으로 이러한 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-149">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="800d1-150">그러나 다른 암시적 오버 로드의 서명에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-150">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="800d1-151">다음 선언을 이러한 경우를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-151">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="800d1-152">오버 로드 하는 대신 관대 한 형식의 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="800d1-152">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="800d1-153">호출 코드를 다른 데이터 형식 매개 변수에 전달 하려는 경우 또 다른 방법은 관대 한 형식의 프로그래밍 합니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-153">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="800d1-154">형식 검사 스위치를 설정할 수 있습니다 `Off` 하나로 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 또는 [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-154">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="800d1-155">다음 매개 변수의 데이터 형식을 선언할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-155">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="800d1-156">그러나이 방법에는 오버 로드에 비해 다음과 같은 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-156">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
-   <span data-ttu-id="800d1-157">관대 한 형식의 프로그래밍 덜 효율적인 실행 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-157">Typeless programming produces less efficient execution code.</span></span>  
  
-   <span data-ttu-id="800d1-158">프로시저는 전달 될 수 있는 모든 데이터 형식에 대 한 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-158">The procedure must test for every data type it anticipates being passed.</span></span>  
  
-   <span data-ttu-id="800d1-159">컴파일러 오류 호출 코드에서 프로시저를 지원 하지 않는 데이터 형식을 전달 하는 경우 신호 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="800d1-159">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="800d1-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="800d1-160">See Also</span></span>  
 [<span data-ttu-id="800d1-161">절차</span><span class="sxs-lookup"><span data-stu-id="800d1-161">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="800d1-162">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="800d1-162">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="800d1-163">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="800d1-163">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="800d1-164">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="800d1-164">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="800d1-165">방법: 오버로드된 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="800d1-165">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="800d1-166">방법: 선택적 매개 변수를 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="800d1-166">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="800d1-167">방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="800d1-167">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="800d1-168">오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="800d1-168">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="800d1-169">오버로드</span><span class="sxs-lookup"><span data-stu-id="800d1-169">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
