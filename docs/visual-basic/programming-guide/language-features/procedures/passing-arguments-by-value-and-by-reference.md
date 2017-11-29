---
title: "값 및 참조로 인수 전달(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 752c0c8e90cafe457cbd5d684bc984a1ea4632ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="21e4d-102">값 및 참조로 인수 전달(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21e4d-102">Passing Arguments by Value and by Reference (Visual Basic)</span></span>
<span data-ttu-id="21e4d-103">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], 프로시저에 인수를 전달할 수 *값별로* 또는 *참조에 의해*합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-103">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], you can pass an argument to a procedure *by value* or *by reference*.</span></span> <span data-ttu-id="21e4d-104">로 알려져는 *전달 메커니즘*, 프로시저가 호출 코드의 기반이 되는 프로그래밍 요소를 수정할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-104">This is known as the *passing mechanism*, and it determines whether the procedure can modify the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="21e4d-105">지정 하 여 각 매개 변수에 대해 전달 메커니즘을 결정 하는 프로시저 선언에서 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-105">The procedure declaration determines the passing mechanism for each parameter by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword.</span></span>  
  
## <a name="distinctions"></a><span data-ttu-id="21e4d-106">차이점</span><span class="sxs-lookup"><span data-stu-id="21e4d-106">Distinctions</span></span>  
 <span data-ttu-id="21e4d-107">프로시저에 인수를 전달 하는 경우 여러 다른 차이점 서로 상호 작용을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-107">When passing an argument to a procedure, be aware of several different distinctions that interact with each other:</span></span>  
  
-   <span data-ttu-id="21e4d-108">기본 프로그래밍 요소를 수정할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="21e4d-108">Whether the underlying programming element is modifiable or nonmodifiable</span></span>  
  
-   <span data-ttu-id="21e4d-109">인수 자체를 수정할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="21e4d-109">Whether the argument itself is modifiable or nonmodifiable</span></span>  
  
-   <span data-ttu-id="21e4d-110">값 이나 참조로 인수 전달 되 고 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="21e4d-110">Whether the argument is being passed by value or by reference</span></span>  
  
-   <span data-ttu-id="21e4d-111">값 형식 또는 참조 형식 인수 데이터 형식 인지</span><span class="sxs-lookup"><span data-stu-id="21e4d-111">Whether the argument data type is a value type or a reference type</span></span>  
  
 <span data-ttu-id="21e4d-112">자세한 내용은 참조 [차이점 간의 수정할 수 있는 인수와 수정할 수 없는 인수](./differences-between-modifiable-and-nonmodifiable-arguments.md) 및 [차이점 사이의 값과 참조로 인수를 전달](./differences-between-passing-an-argument-by-value-and-by-reference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-112">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) and [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="choice-of-passing-mechanism"></a><span data-ttu-id="21e4d-113">전달 메커니즘의 선택</span><span class="sxs-lookup"><span data-stu-id="21e4d-113">Choice of Passing Mechanism</span></span>  
 <span data-ttu-id="21e4d-114">각 인수에 대해 신중 하 게 전달 메커니즘을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-114">You should choose the passing mechanism carefully for each argument.</span></span>  
  
-   <span data-ttu-id="21e4d-115">**보호**합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-115">**Protection**.</span></span> <span data-ttu-id="21e4d-116">두 전달 메커니즘 중 하나를 선택할 가장 중요 한 기준인 변경 하려면 변수를 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-116">In choosing between the two passing mechanisms, the most important criterion is the exposure of calling variables to change.</span></span> <span data-ttu-id="21e4d-117">인수를 전달 `ByRef` 는 프로시저가 해당 인수를 통해 호출 코드에 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-117">The advantage of passing an argument `ByRef` is that the procedure can return a value to the calling code through that argument.</span></span> <span data-ttu-id="21e4d-118">인수를 전달 `ByVal` 변수는 프로시저에 의해 변경 되지 않도록 보호 하는지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-118">The advantage of passing an argument `ByVal` is that it protects a variable from being changed by the procedure.</span></span>  
  
-   <span data-ttu-id="21e4d-119">**성능**합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-119">**Performance**.</span></span> <span data-ttu-id="21e4d-120">전달 메커니즘 수 코드의 성능에 영향을 주지만 차이 일반적으로 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-120">Although the passing mechanism can affect the performance of your code, the difference is usually insignificant.</span></span> <span data-ttu-id="21e4d-121">이 한 가지 예외는 전달 되는 값 형식 `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-121">One exception to this is a value type passed `ByVal`.</span></span> <span data-ttu-id="21e4d-122">이 경우 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 인수의 전체 데이터 내용을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-122">In this case, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] copies the entire data contents of the argument.</span></span> <span data-ttu-id="21e4d-123">따라서 구조체와 같은 큰 값 형식에 대 한 수를 전달 하는 더 효율적 `ByRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-123">Therefore, for a large value type such as a structure, it can be more efficient to pass it `ByRef`.</span></span>  
  
     <span data-ttu-id="21e4d-124">참조 형식에 대 한 데이터에 대 한 포인터만 복사 된 (4 바이트 32 비트 플랫폼에서는 64 비트 플랫폼에 8 바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-124">For reference types, only the pointer to the data is copied (four bytes on 32-bit platforms, eight bytes on 64-bit platforms).</span></span> <span data-ttu-id="21e4d-125">형식의 인수를 전달할 수는 따라서 `String` 또는 `Object` 성능 영향을 주지 않고 값별로 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-125">Therefore, you can pass arguments of type `String` or `Object` by value without harming performance.</span></span>  
  
## <a name="determination-of-the-passing-mechanism"></a><span data-ttu-id="21e4d-126">전달 메커니즘의 결정</span><span class="sxs-lookup"><span data-stu-id="21e4d-126">Determination of the Passing Mechanism</span></span>  
 <span data-ttu-id="21e4d-127">프로시저 선언 각 매개 변수의 전달 메커니즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-127">The procedure declaration specifies the passing mechanism for each parameter.</span></span> <span data-ttu-id="21e4d-128">호출 코드에서 재정의할 수 없습니다. 한 `ByVal` 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-128">The calling code can't override a `ByVal` mechanism.</span></span>  
  
 <span data-ttu-id="21e4d-129">매개 변수는 선언 된 경우 `ByRef`, 호출 코드에는 메커니즘을 강제로 실행할 수 `ByVal` 호출에서 괄호 안에 인수 이름을 포함 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-129">If a parameter is declared with `ByRef`, the calling code can force the mechanism to `ByVal` by enclosing the argument name in parentheses in the call.</span></span> <span data-ttu-id="21e4d-130">자세한 내용은 참조 [하는 방법: 인수가 값으로 전달 되도록 설정](./how-to-force-an-argument-to-be-passed-by-value.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-130">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
 <span data-ttu-id="21e4d-131">대화 상자에서 기본 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 값으로 인수를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-131">The default in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is to pass arguments by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-value"></a><span data-ttu-id="21e4d-132">값으로 인수를 전달 하는 경우</span><span class="sxs-lookup"><span data-stu-id="21e4d-132">When to Pass an Argument by Value</span></span>  
  
-   <span data-ttu-id="21e4d-133">호출 코드 요소가 기반이 되는 수정할 수 없는 요소는 해당 매개 변수를 선언 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-133">If the calling code element underlying the argument is a nonmodifiable element, declare the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="21e4d-134">코드가 없는 수정할 수 없는 요소 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-134">No code can change the value of a nonmodifiable element.</span></span>  
  
-   <span data-ttu-id="21e4d-135">매개 변수를 선언 내부 요소는 수정할 수, 하는 경우 해당 값을 변경할 수 하는 절차를 원하지 않는 `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-135">If the underlying element is modifiable, but you do not want the procedure to be able to change its value, declare the parameter `ByVal`.</span></span> <span data-ttu-id="21e4d-136">호출 코드에만 값으로 전달 된 수정 가능한 요소의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-136">Only the calling code can change the value of a modifiable element passed by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-reference"></a><span data-ttu-id="21e4d-137">참조로 인수를 전달 하는 경우</span><span class="sxs-lookup"><span data-stu-id="21e4d-137">When to Pass an Argument by Reference</span></span>  
  
-   <span data-ttu-id="21e4d-138">프로시저가 호출 코드에서 요소를 반드시 변경 해야 하는 경우 해당 매개 변수를 선언 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-138">If the procedure has a genuine need to change the underlying element in the calling code, declare the corresponding parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span>  
  
-   <span data-ttu-id="21e4d-139">호출 코드의 해당 요소를 변경 하는 프로시저에 종속 되는 코드의 올바르게 실행 되는, 매개 변수를 선언 `ByRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-139">If the correct execution of the code depends on the procedure changing the underlying element in the calling code, declare the parameter `ByRef`.</span></span> <span data-ttu-id="21e4d-140">값으로 전달 하는 경우 또는 호출 하는 코드를 재정의 하는 경우는 `ByRef` 전달 메커니즘에 있는 괄호 안에 인수를 포함 하 여 프로시저 호출에 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-140">If you pass it by value, or if the calling code overrides the `ByRef` passing mechanism by enclosing the argument in parentheses, the procedure call might produce unexpected results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21e4d-141">예제</span><span class="sxs-lookup"><span data-stu-id="21e4d-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="21e4d-142">설명</span><span class="sxs-lookup"><span data-stu-id="21e4d-142">Description</span></span>  
 <span data-ttu-id="21e4d-143">다음 예제는 인수를 값으로 전달 하는 시기 및 참조로 전달 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-143">The following example illustrates when to pass arguments by value and when to pass them by reference.</span></span> <span data-ttu-id="21e4d-144">프로시저 `Calculate` 둘 다를 포함 한 `ByVal` 및 `ByRef` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-144">Procedure `Calculate` has both a `ByVal` and a `ByRef` parameter.</span></span> <span data-ttu-id="21e4d-145">이자율을 지정 된 `rate`, 비용의 합계와 `debt`, 프로시저의 작업에 대 한 새 값을 계산 하는 `debt` 이자의 원래 값에 적용 한 결과인 `debt`합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-145">Given an interest rate, `rate`, and a sum of money, `debt`, the task of the procedure is to calculate a new value for `debt` that is the result of applying the interest rate to the original value of `debt`.</span></span> <span data-ttu-id="21e4d-146">때문에 `debt` 는 `ByRef` 매개 변수를 새 합계로 호출 코드에 해당 하는 인수 값에 반영 된 `debt`합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-146">Because `debt` is a `ByRef` parameter, the new total is reflected in the value of the argument in the calling code that corresponds to `debt`.</span></span> <span data-ttu-id="21e4d-147">매개 변수 `rate` 는 `ByVal` 매개 변수 이므로 `Calculate` 값을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e4d-147">Parameter `rate` is a `ByVal` parameter because `Calculate` should not change its value.</span></span>  
  
### <a name="code"></a><span data-ttu-id="21e4d-148">코드</span><span class="sxs-lookup"><span data-stu-id="21e4d-148">Code</span></span>  
 [!code-vb[VbVbcnProcedures#74](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="21e4d-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21e4d-149">See Also</span></span>  
 [<span data-ttu-id="21e4d-150">절차</span><span class="sxs-lookup"><span data-stu-id="21e4d-150">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="21e4d-151">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="21e4d-151">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="21e4d-152">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="21e4d-152">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="21e4d-153">방법: 프로시저 인수의 값 변경</span><span class="sxs-lookup"><span data-stu-id="21e4d-153">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="21e4d-154">방법: 값 변경에 대해 프로시저 인수 보호</span><span class="sxs-lookup"><span data-stu-id="21e4d-154">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="21e4d-155">방법: 인수가 값으로 전달되도록 설정</span><span class="sxs-lookup"><span data-stu-id="21e4d-155">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="21e4d-156">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="21e4d-156">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="21e4d-157">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="21e4d-157">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
