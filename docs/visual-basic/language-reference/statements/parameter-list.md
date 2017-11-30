---
title: "매개 변수 목록(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c7190b618aa98c91b826ca7c065660d3b19c31a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="6f2b6-102">매개 변수 목록(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f2b6-102">Parameter List (Visual Basic)</span></span>
<span data-ttu-id="6f2b6-103">호출 될 때 프로시저에 필요한 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="6f2b6-104">매개 변수가 여러 개이면 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="6f2b6-105">다음은 매개 변수 하나에 대 한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-105">The following is the syntax for one parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f2b6-106">구문</span><span class="sxs-lookup"><span data-stu-id="6f2b6-106">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a><span data-ttu-id="6f2b6-107">요소</span><span class="sxs-lookup"><span data-stu-id="6f2b6-107">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="6f2b6-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-108">Optional.</span></span> <span data-ttu-id="6f2b6-109">이 매개 변수에 적용 되는 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="6f2b6-110">묶어야는 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호에서 ("`<`"및"`>`").</span><span class="sxs-lookup"><span data-stu-id="6f2b6-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `Optional`  
 <span data-ttu-id="6f2b6-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-111">Optional.</span></span> <span data-ttu-id="6f2b6-112">프로시저가 호출 될 때이 매개 변수가 필수가 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-112">Specifies that this parameter is not required when the procedure is called.</span></span>  
  
 `ByVal`  
 <span data-ttu-id="6f2b6-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-113">Optional.</span></span> <span data-ttu-id="6f2b6-114">프로시저 대체 하거나 호출 코드에서 해당 인수의 내부 변수 요소를 다시 할당할 수 없습니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>  
  
 `ByRef`  
 <span data-ttu-id="6f2b6-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-115">Optional.</span></span> <span data-ttu-id="6f2b6-116">호출 코드 자체 같은 방법으로 프로시저 수 호출 코드의 내부 변수 요소는 수정할 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>  
  
 `ParamArray`  
 <span data-ttu-id="6f2b6-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-117">Optional.</span></span> <span data-ttu-id="6f2b6-118">매개 변수 목록의 마지막 매개 변수는 지정 된 데이터 형식의 요소 선택적 배열 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="6f2b6-119">호출 코드를 프로시저에 임의 개수의 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>  
  
 `parametername`  
 <span data-ttu-id="6f2b6-120">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-120">Required.</span></span> <span data-ttu-id="6f2b6-121">매개 변수를 나타내는 지역 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-121">Name of the local variable representing the parameter.</span></span>  
  
 `parametertype`  
 <span data-ttu-id="6f2b6-122">필요한 경우 `Option Strict` 은 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="6f2b6-123">데이터 형식 인수를 나타내는 지역 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-123">Data type of the local variable representing the parameter.</span></span>  
  
 `defaultvalue`  
 <span data-ttu-id="6f2b6-124">에 필요한 `Optional` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="6f2b6-125">매개 변수의 데이터 형식으로 계산 되는 모든 상수 또는 상수 식입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="6f2b6-126">형식이 `Object`, 클래스, 인터페이스, 배열 또는 구조를 기본값만 될 수 있습니다 또는 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f2b6-127">설명</span><span class="sxs-lookup"><span data-stu-id="6f2b6-127">Remarks</span></span>  
 <span data-ttu-id="6f2b6-128">매개 변수는 괄호로 묶어 되며 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="6f2b6-129">모든 데이터 형식과 매개 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="6f2b6-130">지정 하지 않으면 `parametertype`, 기본적으로 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>  
  
 <span data-ttu-id="6f2b6-131">호출 코드에서 프로시저를 호출 할 때 전달 된 *인수* 각 필수 매개 변수를 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="6f2b6-132">자세한 내용은 참조 [차이점 간의 매개 변수 및 인수](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>  
  
 <span data-ttu-id="6f2b6-133">호출 코드에서 각 매개 변수에 전달 인수가 호출 코드의 내부 요소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="6f2b6-134">이 요소는 경우 *비가변* (상수, 리터럴, 열거형 또는 식)을 변경 하는 코드에 대 한 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="6f2b6-135">이 경우는 *변수* 요소 (선언 된 변수, 필드, 속성, 배열 요소 또는 구조 요소), 호출 코드에서 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="6f2b6-136">자세한 내용은 참조 [차이점 간의 수정할 수 있는 인수와 수정할 수 없는 인수](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>  
  
 <span data-ttu-id="6f2b6-137">Variable 요소에 전달 되는 경우 `ByRef`, 프로시저도 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="6f2b6-138">자세한 내용은 참조 [차이점 사이의 값과 참조로 인수를 전달](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="6f2b6-139">규칙</span><span class="sxs-lookup"><span data-stu-id="6f2b6-139">Rules</span></span>  
  
-   <span data-ttu-id="6f2b6-140">**괄호입니다.**</span><span class="sxs-lookup"><span data-stu-id="6f2b6-140">**Parentheses.**</span></span> <span data-ttu-id="6f2b6-141">매개 변수 목록을 지정 하면 괄호로 묶어 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="6f2b6-142">매개 변수가 없는 경우 빈 목록을 묶는 괄호를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="6f2b6-143">요소는 프로시저를 명확히 하 여 코드의 가독성 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>  
  
-   <span data-ttu-id="6f2b6-144">**선택적 매개 변수입니다.**</span><span class="sxs-lookup"><span data-stu-id="6f2b6-144">**Optional Parameters.**</span></span> <span data-ttu-id="6f2b6-145">사용 하는 경우는 `Optional` 매개 변수에 한정자를 모든 후속 매개 변수 목록에 선택적 및 사용 하 여 선언 된 `Optional` 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>  
  
     <span data-ttu-id="6f2b6-146">모든 선택적 매개 변수 선언에 제공 해야 합니다는 `defaultvalue` 절.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>  
  
     <span data-ttu-id="6f2b6-147">자세한 내용은 참조 [선택적 매개 변수](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>  
  
-   <span data-ttu-id="6f2b6-148">**매개 변수 배열입니다.**</span><span class="sxs-lookup"><span data-stu-id="6f2b6-148">**Parameter Arrays.**</span></span> <span data-ttu-id="6f2b6-149">지정 해야 `ByVal` 에 대 한 한 `ParamArray` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>  
  
     <span data-ttu-id="6f2b6-150">둘 다 사용할 수 없습니다 `Optional` 및 `ParamArray` 동일한 매개 변수 목록에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>  
  
     <span data-ttu-id="6f2b6-151">자세한 내용은 참조 [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
-   <span data-ttu-id="6f2b6-152">**전달 메커니즘입니다.**</span><span class="sxs-lookup"><span data-stu-id="6f2b6-152">**Passing Mechanism.**</span></span> <span data-ttu-id="6f2b6-153">모든 인수는 기본 메커니즘은 `ByVal`, 프로시저를 의미 하는 내부 변수 요소를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="6f2b6-154">그러나 요소 참조 형식인 경우 프로시저 수 내용이 나 기본 개체의 멤버는 없지만 수정할 바꾸거나 개체 자체를 다시 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>  
  
-   <span data-ttu-id="6f2b6-155">**매개 변수 이름입니다.**</span><span class="sxs-lookup"><span data-stu-id="6f2b6-155">**Parameter Names.**</span></span> <span data-ttu-id="6f2b6-156">매개 변수의 데이터 형식이 배열 인지에 따라 `parametername` 괄호 바로 뒤에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="6f2b6-157">매개 변수 이름에 대 한 자세한 내용은 참조 하십시오. [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f2b6-158">예제</span><span class="sxs-lookup"><span data-stu-id="6f2b6-158">Example</span></span>  
 <span data-ttu-id="6f2b6-159">다음 예제에서는 한 `Function` 두 개의 매개 변수를 정의 하는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="6f2b6-159">The following example shows a `Function` procedure that defines two parameters.</span></span>  
  
 [!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6f2b6-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f2b6-160">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [<span data-ttu-id="6f2b6-161">Function 문</span><span class="sxs-lookup"><span data-stu-id="6f2b6-161">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="6f2b6-162">Sub 문</span><span class="sxs-lookup"><span data-stu-id="6f2b6-162">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="6f2b6-163">Declare 문</span><span class="sxs-lookup"><span data-stu-id="6f2b6-163">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="6f2b6-164">Structure 문</span><span class="sxs-lookup"><span data-stu-id="6f2b6-164">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="6f2b6-165">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="6f2b6-165">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="6f2b6-166">특성 개요</span><span class="sxs-lookup"><span data-stu-id="6f2b6-166">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="6f2b6-167">방법: 코드에서 문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="6f2b6-167">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
