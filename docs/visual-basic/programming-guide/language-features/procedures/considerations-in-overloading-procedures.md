---
title: "프로시저 (Visual Basic)를 오버 로드에 대 한 고려 사항 | Microsoft 문서"
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
- signatures, ParamArray arguments
- ParamArray keyword, parameter arrays
- ParamArray keyword, arguments and signatures
- function overloading, implicit overloads for ParamArray
- ParamArray keyword, signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures, overloading
- parameters, lists
- function overloading, typeless programming
- typeless programming
- function overloading, restrictions
- arguments [Visual Basic], optional
- optional arguments, overloading
- signatures, procedure
- parameter lists
- parameter arrays, overloading arguments
- Visual Basic code, parameter lists
- procedure overloading, considerations
- Option Explicit statement
- restrictions, overloading procedures
- procedures, parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
caps.latest.revision: 26
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
ms.openlocfilehash: 486e6c08fe6284cc9b5856fb848f7307a5651120
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="1765d-102">프로시저를 오버로드할 때 고려해야 할 사항(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1765d-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="1765d-103">프로시저를 오버 로드할 때는 다른 사용 해야 *서명* 각 오버 로드 된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="1765d-104">이 경우 대체로 각 버전에는 다른 매개 변수 목록을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="1765d-105">자세한 내용은 "서로 다른 서명"의 참조 [프로시저 오버 로딩](./procedure-overloading.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="1765d-106">오버 로드할 수 있습니다는 `Function` 있는 프로시저는 `Sub` 프로시저를 반대로 시그니처가 다르면를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="1765d-107">두 오버 로드만 된다는 하나에 값을 반환 하지 않으면 달라.</span><span class="sxs-lookup"><span data-stu-id="1765d-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="1765d-108">같은 방법으로 프로시저를 오버 로드를 속성에 오버 로드와 동일한 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="1765d-109">그러나 프로시저를 오버 로드할 수 없습니다 속성을 사용 하거나 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="1765d-110">오버 로드 된 버전에 대 한 대안</span><span class="sxs-lookup"><span data-stu-id="1765d-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="1765d-111">때로는 해야 오버 로드 된 버전에 대 한 대안의 수에는 변수 또는 인수를 생략할 경우에 특히 합니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="1765d-112">매개 변수 배열은를 제한 하 고 선택적 인수입니다. 모든 언어에서 지원 되는 것은 아니며 유의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="1765d-113">여러 다른 언어로 작성 된 코드에서 호출 될 가능성이 있는 프로시저를 작성 하는 경우 버전 제공 시 뛰어난 유연성을 오버 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="1765d-114">선택적 인수 및 오버 로드</span><span class="sxs-lookup"><span data-stu-id="1765d-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="1765d-115">호출 코드 필요에 따라 제공 하거나 하나 이상의 인수를 생략할 수, 하는 경우에 여러 오버 로드 된 버전을 정의 하거나 선택적 매개 변수를 사용 하 여 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="1765d-116">오버 로드 된 버전을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="1765d-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="1765d-117">다음과 같은 경우에는 일련의 오버 로드 된 버전을 정의 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="1765d-118">프로시저 코드의 논리는 호출 코드 제공 되는 선택적 인수 여부에 따라 크게 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
-   <span data-ttu-id="1765d-119">프로시저 코드는 호출 코드에는 선택적 인수를 제공 하는 여부에 안정적으로 테스트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="1765d-120">이 경우, 예를 들어, 기본 값에 대 한 가능한 후보 없는 경우 호출 코드 수 체계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="1765d-121">선택적 매개 변수를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="1765d-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="1765d-122">다음과 같은 경우에 하나 이상의 선택적 매개 변수를 선호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
-   <span data-ttu-id="1765d-123">유일한 필수 작업 호출 하는 코드는 선택적 인수를 제공 하지 않는 경우는 기본값을 매개 변수를 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="1765d-124">이 경우 프로시저 코드 수 덜 복잡 하 게 하나 이상의와 단일 버전을 정의 하는 경우 `Optional` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="1765d-125">자세한 내용은 참조 [선택적 매개 변수](./optional-parameters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="1765d-126">오버 로드와 ParamArrays</span><span class="sxs-lookup"><span data-stu-id="1765d-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="1765d-127">호출 코드에서 가변 개수의 인수를 전달할 수 여러 오버 로드 된 버전을 정의할 수도 있고 매개 변수 배열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="1765d-128">오버 로드 된 버전을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="1765d-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="1765d-129">다음과 같은 경우에는 일련의 오버 로드 된 버전을 정의 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="1765d-130">호출 코드는 되지 전달 적은 수의 값 보다 많은 매개 변수 배열에 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
-   <span data-ttu-id="1765d-131">프로시저 코드의 논리는 호출 코드에서 전달 값의 개수에 따라 크게 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
-   <span data-ttu-id="1765d-132">호출 하는 코드는 서로 다른 데이터 형식의 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="1765d-133">매개 변수 배열을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="1765d-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="1765d-134">여는 것이 좋습니다는 `ParamArray` 매개 변수는 다음과 같은 경우에서:</span><span class="sxs-lookup"><span data-stu-id="1765d-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
-   <span data-ttu-id="1765d-135">호출 코드에서 매개 변수 배열에 전달할 수는 얼마나 많은 값을 예측할 수 없는 하 고 많은 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
-   <span data-ttu-id="1765d-136">프로시저 논리가 기본적으로 모든 값에 동일한 작업을 수행 하는 호출 코드는가 전달 되는 모든 값을 반복에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="1765d-137">자세한 내용은 참조 [매개 변수 배열](./parameter-arrays.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="1765d-138">선택적 매개 변수에 대 한 암시적 오버 로드</span><span class="sxs-lookup"><span data-stu-id="1765d-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="1765d-139">프로시저는 [옵션](../../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수는 선택적 매개 변수를 사용 하 고 하지 않는 두 개의 오버 로드 된 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="1765d-140">이 중 하나에 해당 하는 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="1765d-141">다음과 같은 선언을 이러한 경우를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-141">The following declarations illustrate this.</span></span>  
  
 <span data-ttu-id="1765d-142">[!code-vb[VbVbcnProcedures #&58;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1765d-142">[!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="1765d-143">[!code-vb[VbVbcnProcedures #&60;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="1765d-143">[!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]</span></span>  
  
 <span data-ttu-id="1765d-144">[!code-vb[VbVbcnProcedures #&61;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="1765d-144">[!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]</span></span>  
  
 <span data-ttu-id="1765d-145">둘 이상의 선택적 매개 변수를 사용 하 여 프로시저를 앞의 예제와 비슷한 논리에 의해에 도착 한 암시적 오버 로드 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-145">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="1765d-146">ParamArray 매개 변수에 대 한 암시적 오버 로드</span><span class="sxs-lookup"><span data-stu-id="1765d-146">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="1765d-147">컴파일러가 고려 있는 프로시저는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 무한 수가 어떻게 호출 코드에서 전달 매개 변수 배열에 다음과 같이 각각 서로 다른 오버 로드에 매개 변수:</span><span class="sxs-lookup"><span data-stu-id="1765d-147">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
-   <span data-ttu-id="1765d-148">호출 코드에 인수를 제공 하지 않는 하나의 오버 로드는`ParamArray`</span><span class="sxs-lookup"><span data-stu-id="1765d-148">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
-   <span data-ttu-id="1765d-149">호출 코드는&1; 차원 배열을 제공 하는 경우 하나의 오버 로드는 `ParamArray` 요소 형식</span><span class="sxs-lookup"><span data-stu-id="1765d-149">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
-   <span data-ttu-id="1765d-150">양의 정수에 대 한 하나의 오버 로드에 대 한 호출 코드를 해당 수의 각 인수를 제공 하는 경우는 `ParamArray` 요소 형식</span><span class="sxs-lookup"><span data-stu-id="1765d-150">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="1765d-151">다음과 같은 선언을 이러한 암시적 오버 로드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-151">The following declarations illustrate these implicit overloads.</span></span>  
  
 <span data-ttu-id="1765d-152">[!code-vb[VbVbcnProcedures #&68;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="1765d-152">[!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]</span></span>  
  
 <span data-ttu-id="1765d-153">[!code-vb[VbVbcnProcedures #&70;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="1765d-153">[!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]</span></span>  
  
 <span data-ttu-id="1765d-154">매개 변수 배열에 대 한&1; 차원 배열을 사용 하는 매개 변수 목록으로는 이러한 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-154">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="1765d-155">그러나 다른 암시적 오버 로드의 서명에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-155">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="1765d-156">다음과 같은 선언을 이러한 경우를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-156">The following declarations illustrate this.</span></span>  
  
 <span data-ttu-id="1765d-157">[!code-vb[VbVbcnProcedures #&71;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="1765d-157">[!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]</span></span>  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="1765d-158">오버 로드 하는 대신 관대 한 형식의 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="1765d-158">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="1765d-159">호출 코드를 다른 데이터 형식을 매개 변수로 전달할 수 있도록 하려는 경우 또 다른 방법은 관대 한 형식의 프로그래밍 합니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-159">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="1765d-160">형식 검사 스위치를 설정할 수 있습니다 `Off` 하나로 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 또는 [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-160">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="1765d-161">다음 매개 변수의 데이터 형식을 선언할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-161">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="1765d-162">그러나이 방법에는 오버 로드에 비해 다음과 같은 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-162">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
-   <span data-ttu-id="1765d-163">관대 한 형식의 프로그래밍 덜 효율적인 실행 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-163">Typeless programming produces less efficient execution code.</span></span>  
  
-   <span data-ttu-id="1765d-164">프로시저는 전달 될 수 있는 모든 데이터 형식에 대 한 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-164">The procedure must test for every data type it anticipates being passed.</span></span>  
  
-   <span data-ttu-id="1765d-165">컴파일러 호출 코드에서 프로시저를 지원 하지 않는 데이터 형식을 전달 하는 경우 오류를 표시 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1765d-165">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1765d-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1765d-166">See Also</span></span>  
 <span data-ttu-id="1765d-167">[프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="1765d-167">[Procedures](./index.md) </span></span>  
<span data-ttu-id="1765d-168"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="1765d-168"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="1765d-169"> [문제 해결 절차](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="1765d-169"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="1765d-170"> [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="1765d-170"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="1765d-171"> [방법: 오버 로드 된 프로시저 호출](./how-to-call-an-overloaded-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="1765d-171"> [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md) </span></span>  
<span data-ttu-id="1765d-172"> [방법: 선택적 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="1765d-172"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="1765d-173"> [방법: 불특정 개수의 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="1765d-173"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="1765d-174"> [오버 로드 확인](./overload-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="1765d-174"> [Overload Resolution](./overload-resolution.md) </span></span>  
<span data-ttu-id="1765d-175"> [오버로드](../../../../visual-basic/language-reference/modifiers/overloads.md)</span><span class="sxs-lookup"><span data-stu-id="1765d-175"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)</span></span>
