---
title: "참조 (Visual Basic) 및 값으로 인수를 전달 | Microsoft 문서"
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
- ByRef keyword, passing arguments by reference
- Visual Basic code, procedures
- passing arguments, by value or by reference
- ByVal keyword, passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing, by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
caps.latest.revision: 23
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
ms.openlocfilehash: 44107171d6f24e22614788470c65cf7ad8d28640
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="23a12-102">값 및 참조로 인수 전달(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23a12-102">Passing Arguments by Value and by Reference (Visual Basic)</span></span>
<span data-ttu-id="23a12-103">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], 프로시저에 인수를 전달할 수 있습니다 *값별로* 또는 *참조에 의해*합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-103">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], you can pass an argument to a procedure *by value* or *by reference*.</span></span> <span data-ttu-id="23a12-104">이 이라고는 *전달 메커니즘*, 프로시저 내부에서 호출 코드의 인수로 사용 하는 프로그래밍 요소를 수정할 수 있는지 여부를 결정 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-104">This is known as the *passing mechanism*, and it determines whether the procedure can modify the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="23a12-105">지정 하 여 각 매개 변수에 대해 전달 메커니즘을 결정 하는 프로시저 선언에서 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-105">The procedure declaration determines the passing mechanism for each parameter by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword.</span></span>  
  
## <a name="distinctions"></a><span data-ttu-id="23a12-106">차이점</span><span class="sxs-lookup"><span data-stu-id="23a12-106">Distinctions</span></span>  
 <span data-ttu-id="23a12-107">프로시저에 인수를 전달 하는 경우에 몇 가지 다른 차이점 서로 상호 작용을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-107">When passing an argument to a procedure, be aware of several different distinctions that interact with each other:</span></span>  
  
-   <span data-ttu-id="23a12-108">기본 프로그래밍 요소를 수정할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="23a12-108">Whether the underlying programming element is modifiable or nonmodifiable</span></span>  
  
-   <span data-ttu-id="23a12-109">인수 자체를 수정할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="23a12-109">Whether the argument itself is modifiable or nonmodifiable</span></span>  
  
-   <span data-ttu-id="23a12-110">값별 또는 참조로 인수 전달 되 고 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="23a12-110">Whether the argument is being passed by value or by reference</span></span>  
  
-   <span data-ttu-id="23a12-111">값 형식 또는 참조 형식 인수 데이터 형식 인지</span><span class="sxs-lookup"><span data-stu-id="23a12-111">Whether the argument data type is a value type or a reference type</span></span>  
  
 <span data-ttu-id="23a12-112">자세한 내용은 참조 [수정 간의 차이점 및 수정할 수 없는 인수](./differences-between-modifiable-and-nonmodifiable-arguments.md) 및 [차이 사이 값과 참조로 인수를 전달](./differences-between-passing-an-argument-by-value-and-by-reference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-112">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) and [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="choice-of-passing-mechanism"></a><span data-ttu-id="23a12-113">전달 메커니즘의 선택</span><span class="sxs-lookup"><span data-stu-id="23a12-113">Choice of Passing Mechanism</span></span>  
 <span data-ttu-id="23a12-114">각 인수에 대해 신중 하 게 전달 메커니즘을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-114">You should choose the passing mechanism carefully for each argument.</span></span>  
  
-   <span data-ttu-id="23a12-115">**보호**합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-115">**Protection**.</span></span> <span data-ttu-id="23a12-116">두 전달 메커니즘 중 하나를 선택할 가장 중요 한 조건이 변경 하는 변수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-116">In choosing between the two passing mechanisms, the most important criterion is the exposure of calling variables to change.</span></span> <span data-ttu-id="23a12-117">인수를 전달 `ByRef` 프로시저가 해당 인수를 통해 호출 코드에 값을 반환할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-117">The advantage of passing an argument `ByRef` is that the procedure can return a value to the calling code through that argument.</span></span> <span data-ttu-id="23a12-118">인수를 전달 `ByVal` 변수는 프로시저에 의해 변경 되지 않도록 보호 하는지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-118">The advantage of passing an argument `ByVal` is that it protects a variable from being changed by the procedure.</span></span>  
  
-   <span data-ttu-id="23a12-119">**성능**합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-119">**Performance**.</span></span> <span data-ttu-id="23a12-120">전달 메커니즘은 코드의 성능에 영향을 줄 수, 있지만 차이 일반적으로 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-120">Although the passing mechanism can affect the performance of your code, the difference is usually insignificant.</span></span> <span data-ttu-id="23a12-121">이 한 가지 예외는 전달 되는 값 형식 `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-121">One exception to this is a value type passed `ByVal`.</span></span> <span data-ttu-id="23a12-122">이 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 인수의 전체 데이터 내용을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-122">In this case, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] copies the entire data contents of the argument.</span></span> <span data-ttu-id="23a12-123">따라서 구조체와 같은 큰 값 형식에 대해 수 전달 하는 것이 효율적 `ByRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-123">Therefore, for a large value type such as a structure, it can be more efficient to pass it `ByRef`.</span></span>  
  
     <span data-ttu-id="23a12-124">참조 형식에 대 한 데이터에 대 한 포인터만 복사 된 (4 바이트 32 비트 플랫폼에서는 64 비트 플랫폼에서 8 바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-124">For reference types, only the pointer to the data is copied (four bytes on 32-bit platforms, eight bytes on 64-bit platforms).</span></span> <span data-ttu-id="23a12-125">따라서 형식의 인수를 전달할 수 있습니다 `String` 또는 `Object` 성능 영향을 주지 않고 값입니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-125">Therefore, you can pass arguments of type `String` or `Object` by value without harming performance.</span></span>  
  
## <a name="determination-of-the-passing-mechanism"></a><span data-ttu-id="23a12-126">전달 메커니즘의 결정</span><span class="sxs-lookup"><span data-stu-id="23a12-126">Determination of the Passing Mechanism</span></span>  
 <span data-ttu-id="23a12-127">각 매개 변수에 대해 전달 메커니즘을 지정 하는 프로시저 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-127">The procedure declaration specifies the passing mechanism for each parameter.</span></span> <span data-ttu-id="23a12-128">재정의할 수 없습니다. 호출 하는 코드는 `ByVal` 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-128">The calling code can't override a `ByVal` mechanism.</span></span>  
  
 <span data-ttu-id="23a12-129">매개 변수가 선언 된 경우 `ByRef`, 호출 코드 하는 메커니즘을 강제할 수 `ByVal` 인수 이름에서에서 괄호로 묶어 호출에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-129">If a parameter is declared with `ByRef`, the calling code can force the mechanism to `ByVal` by enclosing the argument name in parentheses in the call.</span></span> <span data-ttu-id="23a12-130">자세한 내용은 참조 [하는 방법: 인수가 값으로 전달 되도록 설정](./how-to-force-an-argument-to-be-passed-by-value.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-130">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
 <span data-ttu-id="23a12-131">대화 상자에서 기본 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 값으로 인수를 전달 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-131">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-value"></a><span data-ttu-id="23a12-132">값으로 인수를 전달 하는 경우</span><span class="sxs-lookup"><span data-stu-id="23a12-132">When to Pass an Argument by Value</span></span>  
  
-   <span data-ttu-id="23a12-133">인수를 내부 호출 코드 요소가 수정할 수 없는 요소는 해당 매개 변수를 선언 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-133">If the calling code element underlying the argument is a nonmodifiable element, declare the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="23a12-134">코드 없이 수정할 수 없는 요소 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-134">No code can change the value of a nonmodifiable element.</span></span>  
  
-   <span data-ttu-id="23a12-135">기본 요소는 수정할 수 있도록 해당 값을 변경 하는 절차를 원하지 않는 표시 되지만 매개 변수를 선언 `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-135">If the underlying element is modifiable, but you do not want the procedure to be able to change its value, declare the parameter `ByVal`.</span></span> <span data-ttu-id="23a12-136">호출 코드에만 값으로 전달 하는 수정 가능한 요소 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-136">Only the calling code can change the value of a modifiable element passed by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-reference"></a><span data-ttu-id="23a12-137">참조로 인수를 전달 하는 경우</span><span class="sxs-lookup"><span data-stu-id="23a12-137">When to Pass an Argument by Reference</span></span>  
  
-   <span data-ttu-id="23a12-138">프로시저 호출 코드에서 요소를 반드시 변경 해야 하는 경우 해당 매개 변수를 선언 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-138">If the procedure has a genuine need to change the underlying element in the calling code, declare the corresponding parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span>  
  
-   <span data-ttu-id="23a12-139">코드의 올바르게 실행 되는 호출 코드에서 해당 요소를 변경 하는 절차에 따라 달라 지, 매개 변수를 선언 `ByRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-139">If the correct execution of the code depends on the procedure changing the underlying element in the calling code, declare the parameter `ByRef`.</span></span> <span data-ttu-id="23a12-140">값으로 전달 하는 경우 또는 호출 하는 코드를 재정의 하는 경우는 `ByRef` 인수를 괄호로 묶어 전달 메커니즘 프로시저 호출에 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-140">If you pass it by value, or if the calling code overrides the `ByRef` passing mechanism by enclosing the argument in parentheses, the procedure call might produce unexpected results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23a12-141">예제</span><span class="sxs-lookup"><span data-stu-id="23a12-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="23a12-142">설명</span><span class="sxs-lookup"><span data-stu-id="23a12-142">Description</span></span>  
 <span data-ttu-id="23a12-143">다음 예제에서는 값으로 인수를 전달 하는 시기 및 참조로 전달 하는 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-143">The following example illustrates when to pass arguments by value and when to pass them by reference.</span></span> <span data-ttu-id="23a12-144">프로시저 `Calculate` 둘 다는 `ByVal` 및 `ByRef` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-144">Procedure `Calculate` has both a `ByVal` and a `ByRef` parameter.</span></span> <span data-ttu-id="23a12-145">이자율을 지정 된 `rate`, 금액의 합계와 `debt`, 프로시저의 작업에 대 한 새 값을 계산 하는 `debt` 이자의 원래 값을 적용 한 결과인 `debt`합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-145">Given an interest rate, `rate`, and a sum of money, `debt`, the task of the procedure is to calculate a new value for `debt` that is the result of applying the interest rate to the original value of `debt`.</span></span> <span data-ttu-id="23a12-146">때문에 `debt` 는 `ByRef` 매개 변수를 새 합계에 해당 하는 호출 코드에서 인수 값에 반영 됩니다 `debt`합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-146">Because `debt` is a `ByRef` parameter, the new total is reflected in the value of the argument in the calling code that corresponds to `debt`.</span></span> <span data-ttu-id="23a12-147">매개 변수 `rate` 는 `ByVal` 매개 변수 때문에 `Calculate` 값을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23a12-147">Parameter `rate` is a `ByVal` parameter because `Calculate` should not change its value.</span></span>  
  
### <a name="code"></a><span data-ttu-id="23a12-148">코드</span><span class="sxs-lookup"><span data-stu-id="23a12-148">Code</span></span>  
 <span data-ttu-id="23a12-149">[!code-vb[VbVbcnProcedures #&74;](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="23a12-149">[!code-vb[VbVbcnProcedures#74](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23a12-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23a12-150">See Also</span></span>  
 <span data-ttu-id="23a12-151">[프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="23a12-151">[Procedures](./index.md) </span></span>  
<span data-ttu-id="23a12-152"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="23a12-152"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="23a12-153"> [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="23a12-153"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="23a12-154"> [방법: 프로시저 인수의 값 변경](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="23a12-154"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="23a12-155"> [방법: 값 변경에 대해 프로시저 인수 보호](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="23a12-155"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="23a12-156"> [방법: 인수가 값으로 전달 되도록 설정](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="23a12-156"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="23a12-157"> [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="23a12-157"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="23a12-158"> [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="23a12-158"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
