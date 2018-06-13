---
title: Operator Statement
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: cb7fe7929e4b6e61ca3b39be5615e09182f2fe0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605500"
---
# <a name="operator-statement"></a><span data-ttu-id="0dfa2-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="0dfa2-102">Operator Statement</span></span>
<span data-ttu-id="0dfa2-103">연산자 기호, 피연산자의 경우 클래스 또는 구조체에서 연산자 프로시저를 정의 하는 코드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dfa2-104">구문</span><span class="sxs-lookup"><span data-stu-id="0dfa2-104">Syntax</span></span>  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a><span data-ttu-id="0dfa2-105">요소</span><span class="sxs-lookup"><span data-stu-id="0dfa2-105">Parts</span></span>  
 `attrlist`  
 <span data-ttu-id="0dfa2-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-106">Optional.</span></span> <span data-ttu-id="0dfa2-107">참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `Public`  
 <span data-ttu-id="0dfa2-108">필수.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-108">Required.</span></span> <span data-ttu-id="0dfa2-109">이 연산자 프로시저에 있음을 나타냅니다 [공용](../../../visual-basic/language-reference/modifiers/public.md) 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>  
  
 `Overloads`  
 <span data-ttu-id="0dfa2-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-110">Optional.</span></span> <span data-ttu-id="0dfa2-111">참조 [오버 로드](../../../visual-basic/language-reference/modifiers/overloads.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>  
  
 `Shared`  
 <span data-ttu-id="0dfa2-112">필수.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-112">Required.</span></span> <span data-ttu-id="0dfa2-113">이 연산자 프로시저 임을 나타냅니다는 [Shared](../../../visual-basic/language-reference/modifiers/shared.md) 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>  
  
 `Shadows`  
 <span data-ttu-id="0dfa2-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-114">Optional.</span></span> <span data-ttu-id="0dfa2-115">참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `Widening`  
 <span data-ttu-id="0dfa2-116">지정 하지 않으면 변환 연산자에 필요한 `Narrowing`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="0dfa2-117">이 연산자 프로시저를 정의 함을 나타냅니다는 [Widening](../../../visual-basic/language-reference/modifiers/widening.md) 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="0dfa2-118">이 도움말 페이지에 "확대 변환과 축소 변환"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `Narrowing`  
 <span data-ttu-id="0dfa2-119">지정 하지 않으면 변환 연산자에 필요한 `Widening`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="0dfa2-120">이 연산자 프로시저를 정의 함을 나타냅니다는 [문제의 범위 제한](../../../visual-basic/language-reference/modifiers/narrowing.md) 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="0dfa2-121">이 도움말 페이지에 "확대 변환과 축소 변환"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `operatorsymbol`  
 <span data-ttu-id="0dfa2-122">필수.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-122">Required.</span></span> <span data-ttu-id="0dfa2-123">기호 또는이 연산자 프로시저가 정의 하는 연산자의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>  
  
 `operand1`  
 <span data-ttu-id="0dfa2-124">필수.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-124">Required.</span></span> <span data-ttu-id="0dfa2-125">이름 및 단항 연산자 (변환 연산자 포함)의 단일 피연산자 또는 이항 연산자의 왼쪽된 피연산자의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>  
  
 `operand2`  
 <span data-ttu-id="0dfa2-126">이항 연산자에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-126">Required for binary operators.</span></span> <span data-ttu-id="0dfa2-127">이름과 이항 연산자의 오른쪽 피연산자의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-127">The name and type of the right operand of a binary operator.</span></span>  
  
 <span data-ttu-id="0dfa2-128">`operand1` 및 `operand2` 다음과 같은 구문과 요소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-128">`operand1` and `operand2` have the following syntax and parts:</span></span>  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|<span data-ttu-id="0dfa2-129">파트</span><span class="sxs-lookup"><span data-stu-id="0dfa2-129">Part</span></span>|<span data-ttu-id="0dfa2-130">설명</span><span class="sxs-lookup"><span data-stu-id="0dfa2-130">Description</span></span>|  
|----------|-----------------|  
|`ByVal`|<span data-ttu-id="0dfa2-131">선택 사항 이지만 전달 메커니즘 해야 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|  
|`operandname`|<span data-ttu-id="0dfa2-132">필수.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-132">Required.</span></span> <span data-ttu-id="0dfa2-133">이 피연산자를 나타내는 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="0dfa2-134">참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`operandtype`|<span data-ttu-id="0dfa2-135">선택적 하지 않는 한 `Option Strict` 은 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="0dfa2-136">이 피연산자의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-136">Data type of this operand.</span></span>|  
  
 `type`  
 <span data-ttu-id="0dfa2-137">선택적 하지 않는 한 `Option Strict` 은 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="0dfa2-138">연산자 프로시저 값의 데이터 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-138">Data type of the value the operator procedure returns.</span></span>  
  
 `statements`  
 <span data-ttu-id="0dfa2-139">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-139">Optional.</span></span> <span data-ttu-id="0dfa2-140">연산자 프로시저를 실행 하는 문 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-140">Block of statements that the operator procedure runs.</span></span>  
  
 `returnvalue`  
 <span data-ttu-id="0dfa2-141">필수.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-141">Required.</span></span> <span data-ttu-id="0dfa2-142">연산자 프로시저 호출 코드에 반환 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-142">The value that the operator procedure returns to the calling code.</span></span>  
  
 <span data-ttu-id="0dfa2-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="0dfa2-143">`End` `Operator`</span></span>  
 <span data-ttu-id="0dfa2-144">필수.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-144">Required.</span></span> <span data-ttu-id="0dfa2-145">이 연산자 프로시저의 정의 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-145">Terminates the definition of this operator procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0dfa2-146">설명</span><span class="sxs-lookup"><span data-stu-id="0dfa2-146">Remarks</span></span>  
 <span data-ttu-id="0dfa2-147">사용할 수 있습니다 `Operator` 클래스 또는 구조체에만 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="0dfa2-148">즉,는 *선언 컨텍스트* 연산자 소스 파일, 네임 스페이스, 모듈, 인터페이스, 프로시저 또는 차단 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="0dfa2-149">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="0dfa2-150">모든 연산자는 반드시 `Public Shared`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="0dfa2-151">지정할 수 없으며 `ByRef`, `Optional`, 또는 `ParamArray` 피연산자에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>  
  
 <span data-ttu-id="0dfa2-152">연산자 기호 또는 식별자를 사용 하 여 반환 값을 보유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="0dfa2-153">사용 해야 합니다는 `Return` 문 및 해당 값을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="0dfa2-154">개수에 관계 없이 `Return` 문은 프로시저에서 아무 곳 이나 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>  
  
 <span data-ttu-id="0dfa2-155">이러한 방식으로 연산자 정의 라고 *연산자 오버 로드*사용 여부는 `Overloads` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="0dfa2-156">다음 표에는 정의할 수 있는 연산자가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-156">The following table lists the operators you can define.</span></span>  
  
|<span data-ttu-id="0dfa2-157">형식</span><span class="sxs-lookup"><span data-stu-id="0dfa2-157">Type</span></span>|<span data-ttu-id="0dfa2-158">연산자</span><span class="sxs-lookup"><span data-stu-id="0dfa2-158">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="0dfa2-159">단항</span><span class="sxs-lookup"><span data-stu-id="0dfa2-159">Unary</span></span>|<span data-ttu-id="0dfa2-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="0dfa2-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="0dfa2-161">이항</span><span class="sxs-lookup"><span data-stu-id="0dfa2-161">Binary</span></span>|<span data-ttu-id="0dfa2-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="0dfa2-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="0dfa2-163">변환(단항)</span><span class="sxs-lookup"><span data-stu-id="0dfa2-163">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="0dfa2-164">`=` 이진 목록의 연산자는 비교 연산자, 대입 연산자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="0dfa2-165">정의 하는 경우 `CType`를 지정 해야 `Widening` 또는 `Narrowing`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>  
  
## <a name="matched-pairs"></a><span data-ttu-id="0dfa2-166">일치 하는 쌍</span><span class="sxs-lookup"><span data-stu-id="0dfa2-166">Matched Pairs</span></span>  
 <span data-ttu-id="0dfa2-167">일치 하는 쌍으로 특정 연산자를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="0dfa2-168">이러한 쌍의 연산자 중 하나를 정의 하는 경우 다른도 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="0dfa2-169">일치 하는 쌍은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-169">The matched pairs are the following:</span></span>  
  
-   <span data-ttu-id="0dfa2-170">`=` 및 `<>`</span><span class="sxs-lookup"><span data-stu-id="0dfa2-170">`=` and `<>`</span></span>  
  
-   <span data-ttu-id="0dfa2-171">`>` 및 `<`</span><span class="sxs-lookup"><span data-stu-id="0dfa2-171">`>` and `<`</span></span>  
  
-   <span data-ttu-id="0dfa2-172">`>=` 및 `<=`</span><span class="sxs-lookup"><span data-stu-id="0dfa2-172">`>=` and `<=`</span></span>  
  
-   <span data-ttu-id="0dfa2-173">`IsTrue` 및 `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="0dfa2-173">`IsTrue` and `IsFalse`</span></span>  
  
## <a name="data-type-restrictions"></a><span data-ttu-id="0dfa2-174">데이터 형식 제한 사항</span><span class="sxs-lookup"><span data-stu-id="0dfa2-174">Data Type Restrictions</span></span>  
 <span data-ttu-id="0dfa2-175">정의한 모든 연산자는 클래스 또는 구조체 정의에 참여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="0dfa2-176">즉, 클래스 또는 구조체는 다음의 데이터 형식으로 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-176">This means that the class or structure must appear as the data type of the following:</span></span>  
  
-   <span data-ttu-id="0dfa2-177">단항 연산자의 피연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-177">The operand of a unary operator.</span></span>  
  
-   <span data-ttu-id="0dfa2-178">적어도 하나는 이항 연산자의 피연산자의입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-178">At least one of the operands of a binary operator.</span></span>  
  
-   <span data-ttu-id="0dfa2-179">피연산자 또는 변환 연산자의 반환 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-179">Either the operand or the return type of a conversion operator.</span></span>  
  
 <span data-ttu-id="0dfa2-180">특정 연산자는 제한 사항에 다음과 같이 입력 하는 추가 데이터:</span><span class="sxs-lookup"><span data-stu-id="0dfa2-180">Certain operators have additional data type restrictions, as follows:</span></span>  
  
-   <span data-ttu-id="0dfa2-181">정의 하는 경우는 `IsTrue` 및 `IsFalse` 연산자를 반환 해야 하므로 둘 다는 `Boolean` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>  
  
-   <span data-ttu-id="0dfa2-182">정의 하는 경우는 `<<` 및 `>>` 연산자를 둘 다 지정 해야는 `Integer` 에 대 한 입력은 `operandtype` 의 `operand2`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>  
  
 <span data-ttu-id="0dfa2-183">반환 형식은 피연산자 중 하나가 형식에 해당 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="0dfa2-184">예를 들어과 같은 비교 연산자 `=` 또는 `<>` 반환할 수 `Boolean` 두 피연산자 모두 경우에 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>  
  
## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="0dfa2-185">논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="0dfa2-185">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="0dfa2-186">`And`, `Or`, `Not`, 및 `Xor` 연산자 Visual Basic의 논리적 또는 비트 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="0dfa2-187">그러나 클래스 또는 구조체에서 이러한 연산자 중 하나를 정의 하는 경우에 비트 연산만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>  
  
 <span data-ttu-id="0dfa2-188">정의할 수 없습니다는 `AndAlso` 와 직접 연산자는 `Operator` 문.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="0dfa2-189">사용할 수 있습니다 `AndAlso` 다음 조건을 충족 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="0dfa2-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>  
  
-   <span data-ttu-id="0dfa2-190">정의한 `And` 동일한 피연산자 형식에 대 한 사용 하려는에 `AndAlso`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>  
  
-   <span data-ttu-id="0dfa2-191">정의 `And` 에 정의한 클래스 또는 구조체와 동일한 형식을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>  
  
-   <span data-ttu-id="0dfa2-192">정의한는 `IsFalse` 에 정의한 클래스 또는 구조체에서 연산자 `And`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>  
  
 <span data-ttu-id="0dfa2-193">마찬가지로, 사용할 수 있습니다 `OrElse` 정의한 경우 `Or` 동일한 피연산자에는 클래스 또는 구조체의 반환 형식을 갖는 정의한 `IsTrue` 클래스 또는 구조체에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>  
  
## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="0dfa2-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="0dfa2-194">Widening and Narrowing Conversions</span></span>  
 <span data-ttu-id="0dfa2-195">A *확대 변환* 런타임 시 항상 성공 하는 동안는 *축소 변환* 런타임 시 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="0dfa2-196">자세한 내용은 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
 <span data-ttu-id="0dfa2-197">변환 프로시저를 선언 하는 경우 `Widening`, 프로시저 코드가 발생 한 모든 오류를 생성 하지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="0dfa2-198">이것은 다음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-198">This means the following:</span></span>  
  
-   <span data-ttu-id="0dfa2-199">형식의 올바른 값을 항상 반환 해야 `type`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-199">It must always return a valid value of type `type`.</span></span>  
  
-   <span data-ttu-id="0dfa2-200">모든 가능한 예외 및 기타 오류 조건 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-200">It must handle all possible exceptions and other error conditions.</span></span>  
  
-   <span data-ttu-id="0dfa2-201">호출 하는 프로시저의 모든 오류 반환을 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-201">It must handle any error returns from any procedures it calls.</span></span>  
  
 <span data-ttu-id="0dfa2-202">으로 선언 해야에서 처리 되지 않은 예외가 발생 한다는 변환 프로시저 성공 하지 못할 수 있는 가능성이 있는 경우 `Narrowing`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0dfa2-203">예제</span><span class="sxs-lookup"><span data-stu-id="0dfa2-203">Example</span></span>  
 <span data-ttu-id="0dfa2-204">다음 코드 예제에서는 `Operator` 연산자 프로시저를 포함 하는 구조 윤곽선을 정의 하는 문에 `And`, `Or`, `IsFalse`, 및 `IsTrue` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="0dfa2-205">`And` 및 `Or` 형식의 두 개의 피연산자 `abc` 및 반환 형식을 `abc`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="0dfa2-206">`IsFalse` 및 `IsTrue` 형식의 단일 피연산자를 각각 사용 `abc` 다음 다시 돌아와 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="0dfa2-207">이러한 정의 사용 하도록 호출 코드를 사용 합니다. `And`, `AndAlso`, `Or`, 및 `OrElse` 형식의 피연산자와 함께 `abc`합니다.</span><span class="sxs-lookup"><span data-stu-id="0dfa2-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0dfa2-208">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0dfa2-208">See Also</span></span>  
 [<span data-ttu-id="0dfa2-209">IsFalse 연산자</span><span class="sxs-lookup"><span data-stu-id="0dfa2-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="0dfa2-210">IsTrue 연산자</span><span class="sxs-lookup"><span data-stu-id="0dfa2-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="0dfa2-211">확장</span><span class="sxs-lookup"><span data-stu-id="0dfa2-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="0dfa2-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="0dfa2-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="0dfa2-213">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="0dfa2-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="0dfa2-214">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="0dfa2-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="0dfa2-215">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="0dfa2-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="0dfa2-216">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="0dfa2-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="0dfa2-217">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="0dfa2-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="0dfa2-218">방법: 연산자를 정의하는 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="0dfa2-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
