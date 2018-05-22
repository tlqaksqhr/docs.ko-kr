---
title: Function 문(Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
ms.openlocfilehash: 908aa594ecbdd8ae2ec5a06de8181a1b16bb7e40
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="bf946-102">Function 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf946-102">Function Statement (Visual Basic)</span></span>
<span data-ttu-id="bf946-103">선언 이름과 매개 변수를 정의 하는 코드는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf946-104">구문</span><span class="sxs-lookup"><span data-stu-id="bf946-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="bf946-105">요소</span><span class="sxs-lookup"><span data-stu-id="bf946-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="bf946-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-106">Optional.</span></span> <span data-ttu-id="bf946-107">참조 [특성 목록](attribute-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="bf946-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-108">Optional.</span></span> <span data-ttu-id="bf946-109">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="bf946-110">공용</span><span class="sxs-lookup"><span data-stu-id="bf946-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="bf946-111">보호됨</span><span class="sxs-lookup"><span data-stu-id="bf946-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="bf946-112">Friend</span><span class="sxs-lookup"><span data-stu-id="bf946-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="bf946-113">전용</span><span class="sxs-lookup"><span data-stu-id="bf946-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [<span data-ttu-id="bf946-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="bf946-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

    - [<span data-ttu-id="bf946-115">보호 된 개인</span><span class="sxs-lookup"><span data-stu-id="bf946-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)  
  
     <span data-ttu-id="bf946-116">참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="bf946-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-117">Optional.</span></span> <span data-ttu-id="bf946-118">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-118">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="bf946-119">오버로드</span><span class="sxs-lookup"><span data-stu-id="bf946-119">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="bf946-120">재정의</span><span class="sxs-lookup"><span data-stu-id="bf946-120">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="bf946-121">재정의 가능</span><span class="sxs-lookup"><span data-stu-id="bf946-121">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="bf946-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="bf946-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="bf946-123">MustOverride</span><span class="sxs-lookup"><span data-stu-id="bf946-123">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="bf946-124">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-124">Optional.</span></span> <span data-ttu-id="bf946-125">참조 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-125">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="bf946-126">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-126">Optional.</span></span> <span data-ttu-id="bf946-127">참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-127">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="bf946-128">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-128">Optional.</span></span> <span data-ttu-id="bf946-129">참조 [비동기](../../../visual-basic/language-reference/modifiers/async.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-129">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="bf946-130">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-130">Optional.</span></span> <span data-ttu-id="bf946-131">참조 [반복기](../../../visual-basic/language-reference/modifiers/iterator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-131">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="bf946-132">필수.</span><span class="sxs-lookup"><span data-stu-id="bf946-132">Required.</span></span> <span data-ttu-id="bf946-133">프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-133">Name of the procedure.</span></span> <span data-ttu-id="bf946-134">참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="bf946-135">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-135">Optional.</span></span> <span data-ttu-id="bf946-136">제네릭 프로시저에 대 한 형식 매개 변수의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-136">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="bf946-137">참조 [목록을 입력](type-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-137">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="bf946-138">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-138">Optional.</span></span> <span data-ttu-id="bf946-139">이 프로시저의 매개 변수를 나타내는 지역 변수 이름의 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-139">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="bf946-140">참조 [매개 변수 목록](parameter-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-140">See [Parameter List](parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="bf946-141">필요한 경우 `Option Strict` 은 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-141">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="bf946-142">이 프로시저에서 반환 된 값의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-142">Data type of the value returned by this procedure.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="bf946-143">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-143">Optional.</span></span> <span data-ttu-id="bf946-144">하나 이상의이 절차를 구현 함을 나타냅니다 `Function` 절차,이 프로시저의 포함 하는 클래스 또는 구조체에서 구현 되는 인터페이스에 정의 된 하나씩 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-144">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="bf946-145">참조 [문을 구현](implements-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-145">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="bf946-146">`Implements`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-146">Required if `Implements` is supplied.</span></span> <span data-ttu-id="bf946-147">구현할 `Function` 프로시저 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-147">List of `Function` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="bf946-148">각 `implementedprocedure`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-148">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="bf946-149">파트</span><span class="sxs-lookup"><span data-stu-id="bf946-149">Part</span></span>|<span data-ttu-id="bf946-150">설명</span><span class="sxs-lookup"><span data-stu-id="bf946-150">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="bf946-151">필수.</span><span class="sxs-lookup"><span data-stu-id="bf946-151">Required.</span></span> <span data-ttu-id="bf946-152">이 프로시저에 의해 구현 되는 인터페이스의 이름의 클래스 또는 구조체를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-152">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="bf946-153">필수.</span><span class="sxs-lookup"><span data-stu-id="bf946-153">Required.</span></span> <span data-ttu-id="bf946-154">프로시저가 `interface`에 정의되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-154">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="bf946-155">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-155">Optional.</span></span> <span data-ttu-id="bf946-156">이 절차에서 하나 이상의 특정 이벤트를 처리할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-156">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="bf946-157">참조 [처리](handles-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-157">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="bf946-158">`Handles`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-158">Required if `Handles` is supplied.</span></span> <span data-ttu-id="bf946-159">이 프로시저에서 처리 하는 이벤트 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-159">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="bf946-160">각 `eventspecifier`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-160">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="bf946-161">파트</span><span class="sxs-lookup"><span data-stu-id="bf946-161">Part</span></span>|<span data-ttu-id="bf946-162">설명</span><span class="sxs-lookup"><span data-stu-id="bf946-162">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="bf946-163">필수.</span><span class="sxs-lookup"><span data-stu-id="bf946-163">Required.</span></span> <span data-ttu-id="bf946-164">개체 변수는 이벤트를 발생 시키는 구조체 또는 클래스의 데이터 형식으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-164">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="bf946-165">필수.</span><span class="sxs-lookup"><span data-stu-id="bf946-165">Required.</span></span> <span data-ttu-id="bf946-166">이 프로시저에서 처리 하는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-166">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="bf946-167">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-167">Optional.</span></span> <span data-ttu-id="bf946-168">이 프로시저 내에서 실행할 문 블록.</span><span class="sxs-lookup"><span data-stu-id="bf946-168">Block of statements to be executed within this procedure.</span></span>  
  
-   `End Function`  
  
     <span data-ttu-id="bf946-169">이 프로시저의 정의 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-169">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf946-170">설명</span><span class="sxs-lookup"><span data-stu-id="bf946-170">Remarks</span></span>  
 <span data-ttu-id="bf946-171">모든 실행 코드는 프로시저 안에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-171">All executable code must be inside a procedure.</span></span> <span data-ttu-id="bf946-172">차례로 각 프로시저에는 클래스, 구조체 또는 포함 하는 클래스, 구조체 또는 모듈 참조 하는 모듈 내에서 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-172">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>  
  
 <span data-ttu-id="bf946-173">호출 코드에는 값을 반환 하려면 사용는 `Function` 프로시저; 사용 그렇지 않은 경우는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-173">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>  
  
## <a name="defining-a-function"></a><span data-ttu-id="bf946-174">함수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-174">Defining a Function</span></span>  
 <span data-ttu-id="bf946-175">정의할 수는 `Function` 모듈 수준에만 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-175">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="bf946-176">따라서 함수에 대 한 선언 컨텍스트 클래스, 구조체, 모듈의 경우, 또는 인터페이스 여야 하며 소스 파일, 네임 스페이스, 프로시저 또는 블록 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-176">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="bf946-177">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf946-177">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="bf946-178">`Function` 프로시저는 기본적으로 공용 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-178">`Function` procedures default to public access.</span></span> <span data-ttu-id="bf946-179">액세스 한정자로 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-179">You can adjust their access levels with the access modifiers.</span></span>  
  
 <span data-ttu-id="bf946-180">A `Function` 프로시저는 프로시저에서 반환 하는 값의 데이터 형식을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-180">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="bf946-181">모든 데이터 형식이 나 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-181">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="bf946-182">지정 하지 않으면는 `returntype` 매개 변수, 프로시저 반환 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-182">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>  
  
 <span data-ttu-id="bf946-183">이 절차를 사용 하는 경우는 `Implements` 있어야 키워드, 클래스 또는 구조체는 `Implements` 바로 뒤에 오는 문을 해당 `Class` 또는 `Structure` 문.</span><span class="sxs-lookup"><span data-stu-id="bf946-183">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="bf946-184">`Implements` 문을에 지정 된 각 인터페이스를 포함 해야 `implementslist`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-184">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="bf946-185">그러나는 인터페이스를 정의 하 여 이름을 `Function` (에서 `definedname`)이이 프로시저의 이름과 일치할 필요가 없습니다 (에서 `name`).</span><span class="sxs-lookup"><span data-stu-id="bf946-185">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf946-186">함수 식 인라인으로 정의를 람다 식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-186">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="bf946-187">자세한 내용은 참조 [함수 식](../../../visual-basic/language-reference/operators/function-expression.md) 및 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-187">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="returning-from-a-function"></a><span data-ttu-id="bf946-188">함수에서 반환</span><span class="sxs-lookup"><span data-stu-id="bf946-188">Returning from a Function</span></span>  
 <span data-ttu-id="bf946-189">경우는 `Function` 프로시저가 호출 코드에 반환 되 면 실행이 프로시저를 호출한 문 다음에 오는 문을 사용 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-189">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>  
  
 <span data-ttu-id="bf946-190">함수에서 값을 반환 하려면 함수 이름에 값을 할당 하거나 포함 된 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="bf946-190">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>  
  
 <span data-ttu-id="bf946-191">`Return` 문은 동시에 반환 값을 할당 하 고 다음 예와 같이 함수를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-191">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]  
  
 <span data-ttu-id="bf946-192">다음 예제에서는 함수 이름에 반환 값을 할당 `myFunction` 다음 사용 하 여는 `Exit Function` 문 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-192">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]  
  
 <span data-ttu-id="bf946-193">`Exit Function` 및 `Return` 문을 사용 하면 즉시 종료 한 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="bf946-194">개수에 관계 없이 `Exit Function` 및 `Return` 문은 프로시저에서 아무 곳 이나 나타날 수 있으며 함께 사용할 수 있습니다 `Exit Function` 및 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="bf946-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>  
  
 <span data-ttu-id="bf946-195">사용 하는 경우 `Exit Function` 값을 할당 하지 않고 `name`에 지정 된 데이터 형식에 대 한 기본값을 반환 하는 프로시저 `returntype`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="bf946-196">경우 `returntype` 지정 하지 않은 경우 프로시저가 반환 `Nothing`에 대 한 기본 값인 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>  
  
## <a name="calling-a-function"></a><span data-ttu-id="bf946-197">함수 호출</span><span class="sxs-lookup"><span data-stu-id="bf946-197">Calling a Function</span></span>  
 <span data-ttu-id="bf946-198">호출 하는 `Function` 프로시저 이름, 식의 괄호 안에 인수 목록을 사용 하 여 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="bf946-199">인수를 제공 하지 하는 경우에 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="bf946-200">그러나 코드는 항상 괄호를 포함 하는 경우 더 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-200">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="bf946-201">호출 하는 `Function` 모든 라이브러리를 호출 하는 동일한 방식으로 작동와 같은 절차 `Sqrt`, `Cos`, 또는 `ChrW`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>  
  
 <span data-ttu-id="bf946-202">사용 하 여 함수를 호출할 수도 있습니다는 `Call` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="bf946-203">이 경우 반환 값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="bf946-204">사용은 `Call` 키워드는 대부분의 경우에 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="bf946-205">자세한 내용은 참조 [Call 문을](call-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-205">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="bf946-206">Visual Basic에는 산술 식 내부 효율성을 높이기 위해 경우에 따라 다시 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="bf946-207">이런 이유로 사용해 서는 안는 `Function` 함수 같은 식에서 변수 값이 변경 될 때 산술 식에는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>  
  
## <a name="async-functions"></a><span data-ttu-id="bf946-208">비동기 함수</span><span class="sxs-lookup"><span data-stu-id="bf946-208">Async Functions</span></span>  
 <span data-ttu-id="bf946-209">*비동기* 기능을 사용 하면 명시적 콜백을 사용 하거나 수동으로 여러 함수 또는 람다 식에 코드를 분할 하지 않고도 비동기 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="bf946-210">사용 하는 함수를 표시 하는 경우는 [비동기](../../../visual-basic/language-reference/modifiers/async.md) 사용할 수 있습니다 한정자는 [Await](../../../visual-basic/language-reference/operators/await-operator.md) 함수에 연산자.</span><span class="sxs-lookup"><span data-stu-id="bf946-210">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="bf946-211">에 도달할 때 제어는 `Await` 식에는 `Async` 호출자에 게 제어가 반환 함수와 함수에서 진행 대기 중인된 작업이 완료 될 때까지 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="bf946-212">작업이 완료 될 때 실행 함수에서 다시 시작 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-212">When the task is complete, execution can resume in the function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf946-213">`Async` 는 첫 번째 대기 된 개체를 아직 완료 되지 않은 발생 하거나 프로시저가 호출자에 게 반환 또는의 끝에 도달는 `Async` 프로시저 중 먼저 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>  
  
 <span data-ttu-id="bf946-214">`Async` 함수 반환 형식으로 지정할 수 있습니다 <xref:System.Threading.Tasks.Task%601> 또는 <xref:System.Threading.Tasks.Task>합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="bf946-215">예로 `Async` 의 반환 형식을 가진 함수를 <xref:System.Threading.Tasks.Task%601> 아래에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>  
  
 <span data-ttu-id="bf946-216">`Async` 함수는 선언할 수 없습니다 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-216">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="bf946-217">A [Sub 문을](sub-statement.md) 로 표시할 수 있습니다는 `Async` 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="bf946-218">이 주로 사용 이벤트 처리기에 대 한 값을 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="bf946-219">`Async``Sub` 프로시저 대기할 수 없습니다 및의 호출자는 `Async``Sub` 프로시저에 의해 throw 되는 예외를 catch 할 수 없습니다는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-219">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>  
  
 <span data-ttu-id="bf946-220">에 대 한 자세한 내용은 `Async` 함수 참조 [Async 및 Await를 사용한 비동기 프로그래밍](../../../visual-basic/programming-guide/concepts/async/index.md), [비동기 프로그램의 제어 흐름](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), 및 [비동기 반환 형식](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="bf946-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="iterator-functions"></a><span data-ttu-id="bf946-221">반복기 함수</span><span class="sxs-lookup"><span data-stu-id="bf946-221">Iterator Functions</span></span>  
 <span data-ttu-id="bf946-222">*반복기* 함수 목록 또는 배열의 같은 컬렉션에 대해 사용자 지정 반복을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="bf946-223">반복기 함수를 사용 하 여는 [Yield](yield-statement.md) 문을 한 번에 각 요소를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="bf946-224">경우는 [Yield](yield-statement.md) 문에 도달 하면 코드의 현재 위치가 기억 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="bf946-225">다음에 반복기 함수가 호출되면 해당 위치에서 실행이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-225">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="bf946-226">사용 하 여 클라이언트 코드에서 반복기를 호출는 [각각에 대해... 다음](for-each-next-statement.md) 문.</span><span class="sxs-lookup"><span data-stu-id="bf946-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>  
  
 <span data-ttu-id="bf946-227">반복기 함수의 반환 형식은 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, 또는 <xref:System.Collections.Generic.IEnumerator%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="bf946-228">자세한 내용은 [반복기](../../programming-guide/concepts/iterators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf946-228">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf946-229">예제</span><span class="sxs-lookup"><span data-stu-id="bf946-229">Example</span></span>  
 <span data-ttu-id="bf946-230">다음 예제에서는 `Function` 이름, 매개 변수, 및의 본문을 형성 하는 코드를 선언 하는 문에 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="bf946-231">`ParamArray` 한정자를 통해 함수에 가변 개수의 인수를 수락 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#25](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="bf946-232">예제</span><span class="sxs-lookup"><span data-stu-id="bf946-232">Example</span></span>  
 <span data-ttu-id="bf946-233">다음 예제에서는 앞의 예제에서 선언 된 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-233">The following example invokes the function declared in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="bf946-234">예제</span><span class="sxs-lookup"><span data-stu-id="bf946-234">Example</span></span>  
 <span data-ttu-id="bf946-235">다음 예에서 `DelayAsync` 는 `Async``Function` 의 반환 형식이 있는 <xref:System.Threading.Tasks.Task%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-235">In the following example, `DelayAsync` is an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="bf946-236">`DelayAsync`에는 정수를 반환하는 `Return` 문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-236">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="bf946-237">따라서 함수 선언의 `DelayAsync` 의 반환 형식이 있어야 `Task(Of Integer)`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-237">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="bf946-238">반환 형식이 이기 `Task(Of Integer)`, 평가 `Await` 에 식을 `DoSomethingAsync` 정수가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-238">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="bf946-239">이 문에서이 확인할: `Dim result As Integer = Await delayTask`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-239">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="bf946-240">`startButton_Click` 절차의 한 예로 `Async Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-240">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="bf946-241">때문에 `DoSomethingAsync` 는 `Async` 함수, 작업에 대 한 호출에 대 한 `DoSomethingAsync` 기다려야, 다음 문과 같이: `Await DoSomethingAsync()`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-241">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="bf946-242">`startButton_Click``Sub` 프로시저 함께 정의 되어야 합니다는 `Async` 한정자 있기 때문에 `Await` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="bf946-242">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bf946-243">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf946-243">See Also</span></span>  
 [<span data-ttu-id="bf946-244">Sub 문</span><span class="sxs-lookup"><span data-stu-id="bf946-244">Sub Statement</span></span>](sub-statement.md)  
 [<span data-ttu-id="bf946-245">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="bf946-245">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [<span data-ttu-id="bf946-246">매개 변수 목록</span><span class="sxs-lookup"><span data-stu-id="bf946-246">Parameter List</span></span>](parameter-list.md)  
 [<span data-ttu-id="bf946-247">Dim 문</span><span class="sxs-lookup"><span data-stu-id="bf946-247">Dim Statement</span></span>](dim-statement.md)  
 [<span data-ttu-id="bf946-248">Call 문</span><span class="sxs-lookup"><span data-stu-id="bf946-248">Call Statement</span></span>](call-statement.md)  
 [<span data-ttu-id="bf946-249">Of</span><span class="sxs-lookup"><span data-stu-id="bf946-249">Of</span></span>](of-clause.md)  
 [<span data-ttu-id="bf946-250">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="bf946-250">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [<span data-ttu-id="bf946-251">방법: 제네릭 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="bf946-251">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="bf946-252">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="bf946-252">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [<span data-ttu-id="bf946-253">람다 식</span><span class="sxs-lookup"><span data-stu-id="bf946-253">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="bf946-254">함수 식</span><span class="sxs-lookup"><span data-stu-id="bf946-254">Function Expression</span></span>](../../../visual-basic/language-reference/operators/function-expression.md)
