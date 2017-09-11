---
title: "매개 변수 목록 (Visual Basic) | Microsoft 문서"
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
- Visual Basic code, procedures
- parameters, Visual Basic
- parameters, lists
- parameter lists
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures, parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
caps.latest.revision: 19
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
ms.openlocfilehash: cc56d90db9a732928773fa549cb1456d368e1dbe
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="ae9e7-102">매개 변수 목록(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae9e7-102">Parameter List (Visual Basic)</span></span>
<span data-ttu-id="ae9e7-103">프로시저를 호출할 때에 필요한 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="ae9e7-104">매개 변수가 여러 개이면 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="ae9e7-105">다음은 하나의 매개 변수를 포함 하는 구문은입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-105">The following is the syntax for one parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae9e7-106">구문</span><span class="sxs-lookup"><span data-stu-id="ae9e7-106">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a><span data-ttu-id="ae9e7-107">요소</span><span class="sxs-lookup"><span data-stu-id="ae9e7-107">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="ae9e7-108">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-108">Optional.</span></span> <span data-ttu-id="ae9e7-109">이 매개 변수에 적용 되는 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="ae9e7-110">묶어야는 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호에서 ("`<`"및"`>`").</span><span class="sxs-lookup"><span data-stu-id="ae9e7-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `Optional`  
 <span data-ttu-id="ae9e7-111">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-111">Optional.</span></span> <span data-ttu-id="ae9e7-112">이 매개 변수가 필요 하지 않음을 프로시저가 호출 될 때 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-112">Specifies that this parameter is not required when the procedure is called.</span></span>  
  
 `ByVal`  
 <span data-ttu-id="ae9e7-113">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-113">Optional.</span></span> <span data-ttu-id="ae9e7-114">프로시저 교체 하거나 호출 코드에서 해당 하는 인수를 내부 변수 요소를 다시 할당할 수 없습니다를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>  
  
 `ByRef`  
 <span data-ttu-id="ae9e7-115">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-115">Optional.</span></span> <span data-ttu-id="ae9e7-116">과정 수 수정 호출 코드에서 내부 변수 요소는 방식으로 호출 코드 자체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>  
  
 `ParamArray`  
 <span data-ttu-id="ae9e7-117">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-117">Optional.</span></span> <span data-ttu-id="ae9e7-118">매개 변수 목록의 마지막 매개 변수는 지정 된 데이터 형식의 요소 선택적 배열 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="ae9e7-119">이 프로시저에는 임의 개수의 인수를 전달 하는 호출 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>  
  
 `parametername`  
 <span data-ttu-id="ae9e7-120">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-120">Required.</span></span> <span data-ttu-id="ae9e7-121">매개 변수를 나타내는 로컬 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-121">Name of the local variable representing the parameter.</span></span>  
  
 `parametertype`  
 <span data-ttu-id="ae9e7-122">필요한 경우 `Option Strict` 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="ae9e7-123">데이터 형식 인수를 나타내는 지역 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-123">Data type of the local variable representing the parameter.</span></span>  
  
 `defaultvalue`  
 <span data-ttu-id="ae9e7-124">에 필요한 `Optional` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="ae9e7-125">매개 변수의 데이터 형식으로 계산 되는 모든 상수 또는 상수 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="ae9e7-126">형식이 `Object`, 클래스, 인터페이스, 배열 또는 구조를 기본값만 수 또는 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae9e7-127">주의</span><span class="sxs-lookup"><span data-stu-id="ae9e7-127">Remarks</span></span>  
 <span data-ttu-id="ae9e7-128">매개 변수는 괄호로 묶어 고 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="ae9e7-129">데이터 형식과 매개 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="ae9e7-130">지정 하지 않으면 `parametertype`, 기본적으로 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>  
  
 <span data-ttu-id="ae9e7-131">호출 코드에서 프로시저를 호출 할 때 전달 된 *인수* 각 필수 매개 변수를 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="ae9e7-132">자세한 내용은 참조 [차이 간의 매개 변수 및 인수](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>  
  
 <span data-ttu-id="ae9e7-133">호출 코드에서 각 매개 변수에 전달 된 인수는 호출 코드의 내부 요소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="ae9e7-134">이 요소를 *비가변* (상수, 리터럴, 열거형 또는 식)를 변경 하는 모든 코드에 대 한 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="ae9e7-135">있으면는 *변수* 요소 (선언 된 변수, 필드, 속성, 배열 요소 또는 구조 요소)를 호출 하는 코드를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="ae9e7-136">자세한 내용은 참조 [수정 간의 차이점 및 수정할 수 없는 인수](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>  
  
 <span data-ttu-id="ae9e7-137">Variable 요소에 전달 되는 경우 `ByRef`, 프로시저도 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="ae9e7-138">자세한 내용은 참조 [차이 사이 값과 참조로 인수를 전달](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ae9e7-139">규칙</span><span class="sxs-lookup"><span data-stu-id="ae9e7-139">Rules</span></span>  
  
-   <span data-ttu-id="ae9e7-140">**괄호입니다.**</span><span class="sxs-lookup"><span data-stu-id="ae9e7-140">**Parentheses.**</span></span> <span data-ttu-id="ae9e7-141">매개 변수 목록을 지정 하면 괄호로 묶을 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="ae9e7-142">매개 변수가 없는 경우 빈 목록을 괄호를 여전히 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="ae9e7-143">요소는 프로시저는 명확 하 게 설명 하 여 코드의 가독성이 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>  
  
-   <span data-ttu-id="ae9e7-144">**선택적 매개 변수입니다.**</span><span class="sxs-lookup"><span data-stu-id="ae9e7-144">**Optional Parameters.**</span></span> <span data-ttu-id="ae9e7-145">사용 하는 경우는 `Optional` 매개 변수 한정자를 모든 후속 매개 변수 목록에 선택적 및 사용 하 여 선언할 수는 `Optional` 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>  
  
     <span data-ttu-id="ae9e7-146">모든 선택적 매개 변수 선언을 제공 해야는 `defaultvalue` 절.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>  
  
     <span data-ttu-id="ae9e7-147">자세한 내용은 참조 [선택적 매개 변수](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>  
  
-   <span data-ttu-id="ae9e7-148">**매개 변수 배열입니다.**</span><span class="sxs-lookup"><span data-stu-id="ae9e7-148">**Parameter Arrays.**</span></span> <span data-ttu-id="ae9e7-149">지정 해야 `ByVal` 에 대 한 한 `ParamArray` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>  
  
     <span data-ttu-id="ae9e7-150">함께 사용할 수 없습니다 `Optional` 및 `ParamArray` 동일한 매개 변수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>  
  
     <span data-ttu-id="ae9e7-151">자세한 내용은 참조 [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
-   <span data-ttu-id="ae9e7-152">**전달 메커니즘입니다.**</span><span class="sxs-lookup"><span data-stu-id="ae9e7-152">**Passing Mechanism.**</span></span> <span data-ttu-id="ae9e7-153">모든 인수에 대 한 기본 메커니즘은 `ByVal`, 프로시저를 의미 하는 내부 변수 요소를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="ae9e7-154">그러나 요소 참조 형식인 경우 프로시저 수정할 수 내용이 나 기본 개체의 멤버는 교체 또는 개체 자체를 다시 할당할 수 없는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>  
  
-   <span data-ttu-id="ae9e7-155">**매개 변수 이름입니다.**</span><span class="sxs-lookup"><span data-stu-id="ae9e7-155">**Parameter Names.**</span></span> <span data-ttu-id="ae9e7-156">매개 변수의 데이터 형식이 배열 인지에 따라 `parametername` 괄호 바로 뒤에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="ae9e7-157">매개 변수 이름에 대 한 자세한 내용은 참조 하십시오. [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae9e7-158">예제</span><span class="sxs-lookup"><span data-stu-id="ae9e7-158">Example</span></span>  
 <span data-ttu-id="ae9e7-159">다음 예제는 `Function` 두 개의 매개 변수를 정의 하는 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="ae9e7-159">The following example shows a `Function` procedure that defines two parameters.</span></span>  
  
 <span data-ttu-id="ae9e7-160">[!code-vb[VbVbalrStatements #&2;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ae9e7-160">[!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9e7-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae9e7-161">See Also</span></span>  
 <span data-ttu-id="ae9e7-162"><xref:System.Runtime.InteropServices.DllImportAttribute></xref:System.Runtime.InteropServices.DllImportAttribute></span><span class="sxs-lookup"><span data-stu-id="ae9e7-162"><xref:System.Runtime.InteropServices.DllImportAttribute></span></span>   
<span data-ttu-id="ae9e7-163"> [Function 문](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ae9e7-163"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="ae9e7-164"> [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ae9e7-164"> [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="ae9e7-165"> [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ae9e7-165"> [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) </span></span>  
<span data-ttu-id="ae9e7-166"> [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ae9e7-166"> [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="ae9e7-167"> [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ae9e7-167"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="ae9e7-168"> [특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="ae9e7-168"> [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span></span>  
<span data-ttu-id="ae9e7-169"> [방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)</span><span class="sxs-lookup"><span data-stu-id="ae9e7-169"> [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)</span></span>
