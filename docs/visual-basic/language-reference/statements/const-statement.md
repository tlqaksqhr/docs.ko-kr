---
title: Const 문(Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: a5842e284eaa858e7a66160060123edc21858a3a
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34233849"
---
# <a name="const-statement-visual-basic"></a><span data-ttu-id="f3bf2-102">Const 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3bf2-102">Const Statement (Visual Basic)</span></span>
<span data-ttu-id="f3bf2-103">선언 하 고 하나 이상의 상수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-103">Declares and defines one or more constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3bf2-104">구문</span><span class="sxs-lookup"><span data-stu-id="f3bf2-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## <a name="parts"></a><span data-ttu-id="f3bf2-105">요소</span><span class="sxs-lookup"><span data-stu-id="f3bf2-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="f3bf2-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-106">Optional.</span></span> <span data-ttu-id="f3bf2-107">이 문에서 선언 된 모든 상수에 적용 되는 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-107">List of attributes that apply to all the constants declared in this statement.</span></span> <span data-ttu-id="f3bf2-108">참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호에서 ("`<`"및"`>`").</span><span class="sxs-lookup"><span data-stu-id="f3bf2-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="f3bf2-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-109">Optional.</span></span> <span data-ttu-id="f3bf2-110">이러한 상수에 액세스할 수 있는 코드를 지정 하려면이 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-110">Use this to specify what code can access these constants.</span></span> <span data-ttu-id="f3bf2-111">수 [공용](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [개인](../../../visual-basic/language-reference/modifiers/private.md), 또는 [보호 된 개인](../../language-reference/modifiers/private-protected.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-111">Can be [Public](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [Private](../../../visual-basic/language-reference/modifiers/private.md), or [Private Protected](../../language-reference/modifiers/private-protected.md).</span></span>
  
 `Shadows`  
 <span data-ttu-id="f3bf2-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-112">Optional.</span></span> <span data-ttu-id="f3bf2-113">이 사용 하 여 다시 선언 하 고 기본 클래스에는 프로그래밍 요소를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-113">Use this to redeclare and hide a programming element in a base class.</span></span> <span data-ttu-id="f3bf2-114">참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-114">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `constantlist`  
 <span data-ttu-id="f3bf2-115">필수.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-115">Required.</span></span> <span data-ttu-id="f3bf2-116">이 문에서 선언 되는 상수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-116">List of constants being declared in this statement.</span></span>  
  
 <span data-ttu-id="f3bf2-117">`constant` `[ ,` `constant` `... ]`</span><span class="sxs-lookup"><span data-stu-id="f3bf2-117">`constant` `[ ,` `constant` `... ]`</span></span>  
  
 <span data-ttu-id="f3bf2-118">각 `constant`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-118">Each `constant` has the following syntax and parts:</span></span>  
  
 <span data-ttu-id="f3bf2-119">`constantname` `[ As` `datatype` `] =` `initializer`</span><span class="sxs-lookup"><span data-stu-id="f3bf2-119">`constantname` `[ As` `datatype` `] =` `initializer`</span></span>  
  
|<span data-ttu-id="f3bf2-120">파트</span><span class="sxs-lookup"><span data-stu-id="f3bf2-120">Part</span></span>|<span data-ttu-id="f3bf2-121">설명</span><span class="sxs-lookup"><span data-stu-id="f3bf2-121">Description</span></span>|  
|----------|-----------------|  
|`constantname`|<span data-ttu-id="f3bf2-122">필수.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-122">Required.</span></span> <span data-ttu-id="f3bf2-123">상수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-123">Name of the constant.</span></span> <span data-ttu-id="f3bf2-124">참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-124">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`datatype`|<span data-ttu-id="f3bf2-125">필요한 경우 `Option Strict` 은 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-125">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="f3bf2-126">상수 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-126">Data type of the constant.</span></span>|  
|`initializer`|<span data-ttu-id="f3bf2-127">필수.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-127">Required.</span></span> <span data-ttu-id="f3bf2-128">컴파일 타임에 계산 되 고 상수에 할당 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-128">Expression that is evaluated at compile time and assigned to the constant.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3bf2-129">설명</span><span class="sxs-lookup"><span data-stu-id="f3bf2-129">Remarks</span></span>  
 <span data-ttu-id="f3bf2-130">응용 프로그램에서 변경 되지 않는 값을 설정한 경우에 명명 된 상수를 정의 하 고 리터럴 값 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-130">If you have a value that never changes in your application, you can define a named constant and use it in place of a literal value.</span></span> <span data-ttu-id="f3bf2-131">이름은 지정 된 값 보다 기억 하기 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-131">A name is easier to remember than a value.</span></span> <span data-ttu-id="f3bf2-132">한 번만 상수를 정의 하 고 코드에서이 한 곳에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-132">You can define the constant just once and use it in many places in your code.</span></span> <span data-ttu-id="f3bf2-133">최신 버전에서 값을 다시 정의 해야 하는 경우는 `Const` 문을 변경 하려면 필요한 유일한 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-133">If in a later version you need to redefine the value, the `Const` statement is the only place you need to make a change.</span></span>  
  
 <span data-ttu-id="f3bf2-134">사용할 수 있습니다 `Const` 모듈 또는 프로시저 수준 에서만.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-134">You can use `Const` only at module or procedure level.</span></span> <span data-ttu-id="f3bf2-135">즉,는 *선언 컨텍스트* 변수 클래스, 구조체, 모듈, 프로시저 또는 블록 이어야 하며 소스 파일, 네임 스페이스 또는 인터페이스 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-135">This means the *declaration context* for a variable must be a class, structure, module, procedure, or block, and cannot be a source file, namespace, or interface.</span></span> <span data-ttu-id="f3bf2-136">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-136">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="f3bf2-137">지역 상수 (내부의 프로시저의 경우) 기본적으로 공용 액세스에 액세스 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-137">Local constants (inside a procedure) default to public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="f3bf2-138">클래스 및 모듈 멤버 (프로시저) 외부 상수 기본적으로 개인 액세스 및 구조 멤버 상수 기본적으로 공용 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-138">Class and module member constants (outside any procedure) default to private access, and structure member constants default to public access.</span></span> <span data-ttu-id="f3bf2-139">액세스 한정자로 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-139">You can adjust their access levels with the access modifiers.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="f3bf2-140">규칙</span><span class="sxs-lookup"><span data-stu-id="f3bf2-140">Rules</span></span>  
  
-   <span data-ttu-id="f3bf2-141">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="f3bf2-141">**Declaration Context.**</span></span> <span data-ttu-id="f3bf2-142">모든 프로시저 외부의 모듈 수준에서 선언 된 상수는 *멤버 상수*; 클래스, 구조체의 멤버인 또는 선언 하는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-142">A constant declared at module level, outside any procedure, is a *member constant*; it is a member of the class, structure, or module that declares it.</span></span>  
  
     <span data-ttu-id="f3bf2-143">프로시저 수준에서 선언 된 상수는 *지역 상수*; 지역적으로 선언 하는 블록 또는 프로시저일 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-143">A constant declared at procedure level is a *local constant*; it is local to the procedure or block that declares it.</span></span>  
  
-   <span data-ttu-id="f3bf2-144">**특성입니다.**</span><span class="sxs-lookup"><span data-stu-id="f3bf2-144">**Attributes.**</span></span> <span data-ttu-id="f3bf2-145">지역 상수 아니라 멤버 상수에만 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-145">You can apply attributes only to member constants, not to local constants.</span></span> <span data-ttu-id="f3bf2-146">특성은 지역 상수와 같은 임시 저장소에 의미가 없습니다 어셈블리의 메타 데이터에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-146">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local constants.</span></span>  
  
-   <span data-ttu-id="f3bf2-147">**한정자입니다.**</span><span class="sxs-lookup"><span data-stu-id="f3bf2-147">**Modifiers.**</span></span> <span data-ttu-id="f3bf2-148">기본적으로 모든 상수는 `Shared`, `Static`, 및 `ReadOnly`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-148">By default, all constants are `Shared`, `Static`, and `ReadOnly`.</span></span> <span data-ttu-id="f3bf2-149">상수를 선언 하는 경우 이러한 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-149">You cannot use any of these keywords when declaring a constant.</span></span>  
  
     <span data-ttu-id="f3bf2-150">프로시저 수준에서 사용할 수 없습니다 `Shadows` 또는 액세스 한정자를 지역 상수 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-150">At procedure level, you cannot use `Shadows` or any access modifiers to declare local constants.</span></span>  
  
-   <span data-ttu-id="f3bf2-151">**여러 상수입니다.**</span><span class="sxs-lookup"><span data-stu-id="f3bf2-151">**Multiple Constants.**</span></span> <span data-ttu-id="f3bf2-152">동일한 선언문에서 여러 상수를 선언할 수를 지정 하는 `constantname` 각각에 대 한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-152">You can declare several constants in the same declaration statement, specifying the `constantname` part for each one.</span></span> <span data-ttu-id="f3bf2-153">여러 상수는 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-153">Multiple constants are separated by commas.</span></span>  
  
## <a name="data-type-rules"></a><span data-ttu-id="f3bf2-154">데이터 형식 규칙</span><span class="sxs-lookup"><span data-stu-id="f3bf2-154">Data Type Rules</span></span>  
  
-   <span data-ttu-id="f3bf2-155">**데이터 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="f3bf2-155">**Data Types.**</span></span> <span data-ttu-id="f3bf2-156">`Const` 문은 변수의 데이터 형식을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-156">The `Const` statement can declare the data type of a variable.</span></span> <span data-ttu-id="f3bf2-157">모든 데이터 형식 또는 열거형의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-157">You can specify any data type or the name of an enumeration.</span></span>  
  
-   <span data-ttu-id="f3bf2-158">**기본 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="f3bf2-158">**Default Type.**</span></span> <span data-ttu-id="f3bf2-159">지정 하지 않으면 `datatype`, 상수의 데이터 형식은 `initializer`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-159">If you do not specify `datatype`, the constant takes the data type of `initializer`.</span></span> <span data-ttu-id="f3bf2-160">모두 지정 하면 `datatype` 및 `initializer`의 데이터 형식이 `initializer` 변환할 수 있어야 `datatype`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-160">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="f3bf2-161">모두 `datatype` 나 `initializer` 가 있는 경우 데이터 형식의 기본값으로 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-161">If neither `datatype` nor `initializer` is present, the data type defaults to `Object`.</span></span>  
  
-   <span data-ttu-id="f3bf2-162">**다른 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="f3bf2-162">**Different Types.**</span></span> <span data-ttu-id="f3bf2-163">별도 사용 하 여 서로 다른 데이터 형식이 서로 다른 상수를 지정할 수 있습니다 `As` 선언 하는 각 변수에 대해 절.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-163">You can specify different data types for different constants by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="f3bf2-164">그러나 공통을 사용 하 여 동일한 형식으로 여러 상수를 선언할 수 없습니다 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-164">However, you cannot declare several constants to be of the same type by using a common `As` clause.</span></span>  
  
-   <span data-ttu-id="f3bf2-165">**초기화 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f3bf2-165">**Initialization.**</span></span> <span data-ttu-id="f3bf2-166">모든 상수 값을 초기화 해야 `constantlist`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-166">You must initialize the value of every constant in `constantlist`.</span></span> <span data-ttu-id="f3bf2-167">사용 하면 `initializer` 상수에 할당 하는 식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-167">You use `initializer` to supply an expression to be assigned to the constant.</span></span> <span data-ttu-id="f3bf2-168">식은은 리터럴, 이미 정의 되어 있는 다른 상수 이미 정의 된 열거형 멤버의 조합 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-168">The expression can be any combination of literals, other constants that are already defined, and enumeration members that are already defined.</span></span> <span data-ttu-id="f3bf2-169">이러한 요소를 결합 하 산술 및 논리 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-169">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
     <span data-ttu-id="f3bf2-170">변수 또는 함수에서 사용할 수 없습니다 `initializer`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-170">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="f3bf2-171">그러나와 같은 변환 키워드를 사용할 수는 `CByte` 및 `CShort`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-171">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="f3bf2-172">사용할 수도 있습니다 `AscW` 상수와 호출 하는 경우 `String` 또는 `Char` 인수를 컴파일 타임에 계산 될 수 있으므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-172">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="f3bf2-173">동작</span><span class="sxs-lookup"><span data-stu-id="f3bf2-173">Behavior</span></span>  
  
-   <span data-ttu-id="f3bf2-174">**범위입니다.**</span><span class="sxs-lookup"><span data-stu-id="f3bf2-174">**Scope.**</span></span> <span data-ttu-id="f3bf2-175">지역 상수는 해당 프로시저 또는 블록 내 에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-175">Local constants are accessible only from within their procedure or block.</span></span> <span data-ttu-id="f3bf2-176">멤버 상수는 해당 클래스, 구조체 또는 모듈 내의 모든 위치에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-176">Member constants are accessible from anywhere within their class, structure, or module.</span></span>  
  
-   <span data-ttu-id="f3bf2-177">**검증 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f3bf2-177">**Qualification.**</span></span> <span data-ttu-id="f3bf2-178">코드는 클래스 외부 또는 모듈 정해야 멤버 상수 이름을 해당 클래스, 구조체 또는 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-178">Code outside a class, structure, or module must qualify a member constant's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="f3bf2-179">코드 바깥쪽 블록 또는 프로시저일 해당 프로시저 또는 블록에 있는 로컬 상수를 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-179">Code outside a procedure or block cannot refer to any local constants within that procedure or block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3bf2-180">예제</span><span class="sxs-lookup"><span data-stu-id="f3bf2-180">Example</span></span>  
 <span data-ttu-id="f3bf2-181">다음 예제에서는 `Const` 문을 리터럴 값 대신 사용할 상수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-181">The following example uses the `Const` statement to declare constants for use in place of literal values.</span></span>  
  
 [!code-vb[VbVbalrStatements#13](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="f3bf2-182">예제</span><span class="sxs-lookup"><span data-stu-id="f3bf2-182">Example</span></span>  
 <span data-ttu-id="f3bf2-183">데이터 형식 상수를 정의 하는 경우 `Object`, Visual Basic 컴파일러의 형식을 제공 `initializer`, 대신 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-183">If you define a constant with data type `Object`, the Visual Basic compiler gives it the type of `initializer`, instead of `Object`.</span></span> <span data-ttu-id="f3bf2-184">다음 예제에서는 상수 `naturalLogBase` 런타임 형식이 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-184">In the following example, the constant `naturalLogBase` has the run-time type `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrStatements#87](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_2.vb)]  
  
 <span data-ttu-id="f3bf2-185">앞의 예제를 사용 하 여는 <xref:System.Type.ToString%2A> 메서드를는 <xref:System.Type> 에서 반환 된 개체는 [GetType 연산자](../../../visual-basic/language-reference/operators/gettype-operator.md)때문에, <xref:System.Type> 변환할 수 없습니다 `String` 를 사용 하 여 `CStr`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3bf2-185">The preceding example uses the <xref:System.Type.ToString%2A> method on the <xref:System.Type> object returned by the [GetType Operator](../../../visual-basic/language-reference/operators/gettype-operator.md), because <xref:System.Type> cannot be converted to `String` using `CStr`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3bf2-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3bf2-186">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 [<span data-ttu-id="f3bf2-187">Enum 문</span><span class="sxs-lookup"><span data-stu-id="f3bf2-187">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="f3bf2-188">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="f3bf2-188">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
 [<span data-ttu-id="f3bf2-189">Dim 문</span><span class="sxs-lookup"><span data-stu-id="f3bf2-189">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="f3bf2-190">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="f3bf2-190">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="f3bf2-191">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="f3bf2-191">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="f3bf2-192">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="f3bf2-192">Constants and Enumerations</span></span>](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 [<span data-ttu-id="f3bf2-193">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="f3bf2-193">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="f3bf2-194">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="f3bf2-194">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
