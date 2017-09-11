---
title: "함수 문 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Function
dev_langs:
- VB
helpviewer_keywords:
- procedures, creating
- Function procedures, Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword, Function statements
- Private keyword, Function statements
- declarations, procedures
- procedures, declaration
- Public keyword, in Function statement
- ByVal keyword, Function statements
- procedures, recursive
- Implements keyword, Function statements
- procedures, returning values
- Exit statement, in Function procedures
- recursive procedures
- As keyword, in Function statement
- Optional keyword, Function statements
- Function statement
- Visual Basic code, Function procedures
- procedures, function
- ByRef keyword, Function statements
- Friend keyword, Function statements
- End keyword, Function statements
- Handles keyword, Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
caps.latest.revision: 62
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
ms.sourcegitcommit: dc1c456c71efb3cc6e60a8fdc77384e65975f110
ms.openlocfilehash: d875fe6df3ef7ac9390346588b1c2d48497d7116
ms.contentlocale: ko-kr
ms.lasthandoff: 05/15/2017

---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="b73b7-102">Function 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b73b7-102">Function Statement (Visual Basic)</span></span>
<span data-ttu-id="b73b7-103">선언 이름과 매개 변수를 정의 하는 코드는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b73b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="b73b7-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="b73b7-105">요소</span><span class="sxs-lookup"><span data-stu-id="b73b7-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="b73b7-106">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-106">Optional.</span></span> <span data-ttu-id="b73b7-107">참조 [특성 목록](attribute-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="b73b7-108">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-108">Optional.</span></span> <span data-ttu-id="b73b7-109">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="b73b7-110">공용</span><span class="sxs-lookup"><span data-stu-id="b73b7-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="b73b7-111">보호됨</span><span class="sxs-lookup"><span data-stu-id="b73b7-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="b73b7-112">Friend</span><span class="sxs-lookup"><span data-stu-id="b73b7-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="b73b7-113">전용</span><span class="sxs-lookup"><span data-stu-id="b73b7-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="b73b7-114">참조 [액세스 수준 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-114">See [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="b73b7-115">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-115">Optional.</span></span> <span data-ttu-id="b73b7-116">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-116">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="b73b7-117">오버로드</span><span class="sxs-lookup"><span data-stu-id="b73b7-117">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="b73b7-118">재정의</span><span class="sxs-lookup"><span data-stu-id="b73b7-118">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="b73b7-119">재정의 가능</span><span class="sxs-lookup"><span data-stu-id="b73b7-119">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="b73b7-120">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="b73b7-120">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="b73b7-121">MustOverride</span><span class="sxs-lookup"><span data-stu-id="b73b7-121">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="b73b7-122">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-122">Optional.</span></span> <span data-ttu-id="b73b7-123">참조 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-123">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="b73b7-124">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-124">Optional.</span></span> <span data-ttu-id="b73b7-125">참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-125">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="b73b7-126">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-126">Optional.</span></span> <span data-ttu-id="b73b7-127">참조 [비동기](../../../visual-basic/language-reference/modifiers/async.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-127">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="b73b7-128">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-128">Optional.</span></span> <span data-ttu-id="b73b7-129">참조 [반복기](../../../visual-basic/language-reference/modifiers/iterator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-129">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="b73b7-130">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-130">Required.</span></span> <span data-ttu-id="b73b7-131">프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-131">Name of the procedure.</span></span> <span data-ttu-id="b73b7-132">참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-132">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="b73b7-133">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-133">Optional.</span></span> <span data-ttu-id="b73b7-134">제네릭 프로시저에 대 한 형식 매개 변수의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-134">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="b73b7-135">참조 [목록을 입력](type-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-135">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="b73b7-136">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-136">Optional.</span></span> <span data-ttu-id="b73b7-137">이 절차의 매개 변수를 나타내는 로컬 변수 이름의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-137">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="b73b7-138">참조 [매개 변수 목록](parameter-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-138">See [Parameter List](parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="b73b7-139">필요한 경우 `Option Strict` 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-139">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="b73b7-140">이 프로시저에서 반환 된 값의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-140">Data type of the value returned by this procedure.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="b73b7-141">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-141">Optional.</span></span> <span data-ttu-id="b73b7-142">이 절차를 하나 이상 구현 함을 나타냅니다 `Function` 절차,이 절차의 포함 하는 클래스 또는 구조체에서 구현 되는 인터페이스에 정의 된 각 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-142">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="b73b7-143">참조 [문을 구현](implements-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-143">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="b73b7-144">`Implements`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-144">Required if `Implements` is supplied.</span></span> <span data-ttu-id="b73b7-145">구현할 `Function` 프로시저 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-145">List of `Function` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="b73b7-146">각 `implementedprocedure`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-146">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="b73b7-147">파트</span><span class="sxs-lookup"><span data-stu-id="b73b7-147">Part</span></span>|<span data-ttu-id="b73b7-148">설명</span><span class="sxs-lookup"><span data-stu-id="b73b7-148">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="b73b7-149">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-149">Required.</span></span> <span data-ttu-id="b73b7-150">이 프로시저에 의해 구현 되는 인터페이스의 이름의 클래스 또는 구조체를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-150">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="b73b7-151">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-151">Required.</span></span> <span data-ttu-id="b73b7-152">프로시저가 `interface`에 정의되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-152">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="b73b7-153">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-153">Optional.</span></span> <span data-ttu-id="b73b7-154">이 절차에서 하나 이상의 특정 이벤트를 처리할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-154">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="b73b7-155">참조 [처리](handles-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-155">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="b73b7-156">`Handles`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-156">Required if `Handles` is supplied.</span></span> <span data-ttu-id="b73b7-157">이 프로시저에서 처리 하는 이벤트 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-157">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="b73b7-158">각 `eventspecifier`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-158">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="b73b7-159">파트</span><span class="sxs-lookup"><span data-stu-id="b73b7-159">Part</span></span>|<span data-ttu-id="b73b7-160">설명</span><span class="sxs-lookup"><span data-stu-id="b73b7-160">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="b73b7-161">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-161">Required.</span></span> <span data-ttu-id="b73b7-162">클래스 또는 이벤트를 발생 하는 구조체의 데이터 형식으로 선언 된 개체 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-162">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="b73b7-163">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-163">Required.</span></span> <span data-ttu-id="b73b7-164">이 프로시저에서 처리 하는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-164">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="b73b7-165">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="b73b7-165">Optional.</span></span> <span data-ttu-id="b73b7-166">문 블록을이 프로시저 내에서 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-166">Block of statements to be executed within this procedure.</span></span>  
  
-   `End Function`  
  
     <span data-ttu-id="b73b7-167">이 프로시저의 정의 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-167">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b73b7-168">주의</span><span class="sxs-lookup"><span data-stu-id="b73b7-168">Remarks</span></span>  
 <span data-ttu-id="b73b7-169">모든 실행 코드는 프로시저 안에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-169">All executable code must be inside a procedure.</span></span> <span data-ttu-id="b73b7-170">차례로 각 프로시저에는 클래스, 구조체 또는 포함 하는 클래스, 구조체 또는 모듈 참조 하는 모듈 내에서 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-170">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>  
  
 <span data-ttu-id="b73b7-171">호출 코드에는 값을 반환 하려면 사용을 `Function` 프로시저 그렇지 사용 하 여는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-171">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>  
  
## <a name="defining-a-function"></a><span data-ttu-id="b73b7-172">함수 정의</span><span class="sxs-lookup"><span data-stu-id="b73b7-172">Defining a Function</span></span>  
 <span data-ttu-id="b73b7-173">정의할 수는 `Function` 모듈 수준에만 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-173">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="b73b7-174">따라서 함수에 대 한 선언 컨텍스트 클래스, 구조체, 모듈의 경우, 또는 인터페이스 여야 하며 소스 파일, 네임 스페이스, 프로시저 또는 블록 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-174">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="b73b7-175">자세한 내용은 참조 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-175">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="b73b7-176">`Function`프로시저는 기본적으로 공용 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-176">`Function` procedures default to public access.</span></span> <span data-ttu-id="b73b7-177">액세스 한정자로 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-177">You can adjust their access levels with the access modifiers.</span></span>  
  
 <span data-ttu-id="b73b7-178">A `Function` 프로시저는 프로시저에서 반환 된 값의 데이터 형식을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-178">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="b73b7-179">모든 데이터 형식이 나 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-179">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="b73b7-180">지정 하지 않으면는 `returntype` 프로시저에서 반환 하는 매개 변수를 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-180">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>  
  
 <span data-ttu-id="b73b7-181">이 절차를 사용 하는 경우는 `Implements` 있어야 키워드를 포함 하는 클래스나 구조체는 `Implements` 문 바로 뒤에 오는 해당 `Class` 또는 `Structure` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-181">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="b73b7-182">`Implements` 문을에 지정 된 각 인터페이스를 포함 해야 `implementslist`합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="b73b7-183">그러나 인터페이스 정의는 이름에서 `Function` (에서 `definedname`)이이 프로시저의 이름과 일치 하도록 필요 하지 않습니다 (에서 `name`).</span><span class="sxs-lookup"><span data-stu-id="b73b7-183">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b73b7-184">식 인라인 함수를 정의 하려면 람다 식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-184">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="b73b7-185">자세한 내용은 참조 [함수 식](../../../visual-basic/language-reference/operators/function-expression.md) 및 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-185">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="returning-from-a-function"></a><span data-ttu-id="b73b7-186">함수에서 반환</span><span class="sxs-lookup"><span data-stu-id="b73b7-186">Returning from a Function</span></span>  
 <span data-ttu-id="b73b7-187">경우는 `Function` 프로시저가 호출 코드로 반환 되 면 실행이 프로시저를 호출한 문 다음에 오는 문을 사용 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-187">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>  
  
 <span data-ttu-id="b73b7-188">함수에서 값을 반환 하려면 함수 이름에 값을 할당 하거나 포함 한 `Return` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-188">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>  
  
 <span data-ttu-id="b73b7-189">`Return` 문은 동시에 반환 값을 할당 하 고 다음 예제와 같이 함수를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-189">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>  
  
 <span data-ttu-id="b73b7-190">[!code-vb[VbVbalrStatements #&24;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b73b7-190">[!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="b73b7-191">함수 이름에 반환 값을 할당 하는 다음 예제에서는 `myFunction` 다음 사용 하 여는 `Exit Function` 문을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-191">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>  
  
 <span data-ttu-id="b73b7-192">[!code-vb[VbVbalrStatements&23;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b73b7-192">[!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]</span></span>  
  
 <span data-ttu-id="b73b7-193">`Exit Function` 및 `Return` 문을 사용 하면 즉시 종료 한 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="b73b7-194">개수에 관계 없이 `Exit Function` 및 `Return` 문을 프로시저에서 아무 곳 이나 나타날 수 있으며 혼합할 수 `Exit Function` 및 `Return` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>  
  
 <span data-ttu-id="b73b7-195">사용 하는 경우 `Exit Function` 값을 할당 하지 않고 `name`에 지정 된 데이터 형식에 대 한 기본 값을 반환 하는 프로시저 `returntype`합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="b73b7-196">경우 `returntype` 지정 하지 않은 경우에 프로시저가 반환 `Nothing`에 대 한 기본 값 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>  
  
## <a name="calling-a-function"></a><span data-ttu-id="b73b7-197">함수 호출</span><span class="sxs-lookup"><span data-stu-id="b73b7-197">Calling a Function</span></span>  
 <span data-ttu-id="b73b7-198">호출 된 `Function` 프로시저 이름 뒤에 식의 괄호 안에 인수 목록을 사용 하 여 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="b73b7-199">모든 인수를 제공 하지 하는 경우에 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="b73b7-200">그러나이 코드는 항상 괄호를 포함 하는 경우 보다 읽기 쉬운.</span><span class="sxs-lookup"><span data-stu-id="b73b7-200">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="b73b7-201">호출을 `Function` 모든 라이브러리를 호출 하는 동일한 방식으로 같은 함수는 프로시저 `Sqrt`, `Cos`, 또는 `ChrW`합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>  
  
 <span data-ttu-id="b73b7-202">사용 하 여 함수를 호출도 `Call` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="b73b7-203">이 경우 반환 값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="b73b7-204">사용은 `Call` 키워드는 대부분의 경우에 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="b73b7-205">자세한 내용은 참조 [Call 문을](call-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-205">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="b73b7-206">Visual Basic에는 산술 식 내부 효율성을 높이기 위해 경우에 따라 다시 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="b73b7-207">이런 이유로 사용 하면 안는 `Function` 함수 같은 식에서 변수 값이 변경 될 때 산술 식에는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>  
  
## <a name="async-functions"></a><span data-ttu-id="b73b7-208">비동기 함수</span><span class="sxs-lookup"><span data-stu-id="b73b7-208">Async Functions</span></span>  
 <span data-ttu-id="b73b7-209">*비동기* 기능 명시적 콜백을 사용 하거나 수동으로 여러 함수 또는 람다 식에 코드를 분할 하지 않고도 비동기 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="b73b7-210">사용 하는 함수를 표시 하는 경우는 [비동기](../../../visual-basic/language-reference/modifiers/async.md) 한정자를 사용해는 [Await](../../../visual-basic/language-reference/operators/await-operator.md) 함수에서 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-210">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="b73b7-211">때에 수신 되 면 제어는 `Await` 식에는 `Async` 함수, 호출자에 게 제어가 반환 하 고 함수에서 진행 대기 중인된 작업이 완료 될 때까지 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="b73b7-212">작업이 완료 되 면 실행 함수에서 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-212">When the task is complete, execution can resume in the function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b73b7-213">`Async` 의 끝에 도달 하거나 아직 완료 되지 않은 첫 번째 대기 중이 던된 개체 발생 하거나 프로시저가 호출자에 게 반환 된 `Async` 프로시저 중 먼저 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>  
  
 <span data-ttu-id="b73b7-214">`Async` 함수 <xref:System.Threading.Tasks.Task%601>또는 <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601> 의 반환 형식을 가질 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="b73b7-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="b73b7-215">예로 `Async` 의 반환 형식을 갖는 함수 <xref:System.Threading.Tasks.Task%601>아래에 나와 있습니다.</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="b73b7-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>  
  
 <span data-ttu-id="b73b7-216">`Async` 모든 함수를 선언할 수 없습니다 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-216">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="b73b7-217">A [Sub 문을](sub-statement.md) 로 표시할 수 있습니다는 `Async` 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="b73b7-218">이 주로 사용 이벤트 처리기에 대 한 값을 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="b73b7-219">`Async``Sub` 프로시저 대기할 수 없습니다 및의 호출자는 `Async``Sub` 프로시저에 의해 throw 되는 예외를 catch 할 수 없습니다는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-219">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>  
  
 <span data-ttu-id="b73b7-220">에 대 한 자세한 내용은 `Async` 함수 참조 [Async 및 Await를 사용한 비동기 프로그래밍](../../../visual-basic/programming-guide/concepts/async/index.md), [비동기 프로그램의 제어 흐름](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), 및 [비동기 반환 형식](../../../visual-basic/programming-guide/concepts/async/async-return-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="iterator-functions"></a><span data-ttu-id="b73b7-221">반복기 함수</span><span class="sxs-lookup"><span data-stu-id="b73b7-221">Iterator Functions</span></span>  
 <span data-ttu-id="b73b7-222">*반복기* 함수 등 목록 또는 배열로 컬렉션에 대해 사용자 지정 반복을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="b73b7-223">반복기 함수를 사용 하 여는 [Yield](yield-statement.md) 문을 한 번에 각 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="b73b7-224">경우는 [생성](yield-statement.md) 문에 도달 하면, 코드에서 현재 위치 기억 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="b73b7-225">실행이 다시 시작 해당 위치에서 다음에 반복기 함수가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-225">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="b73b7-226">반복기를 사용 하 여 호출 클라이언트 코드에서 한 [각각에 대해... 다음](for-each-next-statement.md) 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>  
  
 <span data-ttu-id="b73b7-227">반복기 함수의 반환 형식은 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, 또는 <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="b73b7-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="b73b7-228">자세한 내용은 [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b73b7-228">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b73b7-229">예제</span><span class="sxs-lookup"><span data-stu-id="b73b7-229">Example</span></span>  
 <span data-ttu-id="b73b7-230">다음 예제에서는 `Function` 이름, 매개 변수, 및의 본문을 형성 하는 코드를 선언 하는 문에 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="b73b7-231">`ParamArray` 한정자를 사용 하면 여러 개의 인수를 수락 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>  
  
 <span data-ttu-id="b73b7-232">[!code-vb[VbVbalrStatements #&25;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b73b7-232">[!code-vb[VbVbalrStatements#25](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b73b7-233">예제</span><span class="sxs-lookup"><span data-stu-id="b73b7-233">Example</span></span>  
 <span data-ttu-id="b73b7-234">다음 예제에서는 앞의 예제에서 선언한 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-234">The following example invokes the function declared in the preceding example.</span></span>  
  
 <span data-ttu-id="b73b7-235">[!code-vb[VbVbalrStatements #&26;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="b73b7-235">[!code-vb[VbVbalrStatements#26](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b73b7-236">예제</span><span class="sxs-lookup"><span data-stu-id="b73b7-236">Example</span></span>  
 <span data-ttu-id="b73b7-237">다음 예에서 `DelayAsync` 는 `Async``Function` <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> 의 반환 형식이 있는</span><span class="sxs-lookup"><span data-stu-id="b73b7-237">In the following example, `DelayAsync` is an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="b73b7-238">`DelayAsync`에는 정수를 반환하는 `Return` 문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-238">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="b73b7-239">따라서 함수 선언의 `DelayAsync` 반환 형식이 있어야 하며 `Task(Of Integer)`합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-239">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="b73b7-240">반환 형식이 이기 `Task(Of Integer)`, 평가 `Await` 식 `DoSomethingAsync` 정수를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-240">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="b73b7-241">이 문에서이 확인할: `Dim result As Integer = Await delayTask`합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-241">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="b73b7-242">`startButton_Click` 프로시저의 한 예로 `Async Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-242">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="b73b7-243">때문에 `DoSomethingAsync` 는 `Async` 함수, 작업에 대 한 호출에 대 한 `DoSomethingAsync` 다음 문 에서처럼 대기할 수 해야: `Await DoSomethingAsync()`합니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-243">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="b73b7-244">`startButton_Click``Sub` 으로 프로시저를 정의 해야는 `Async` 한정자 되었기 때문에 `Await` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b73b7-244">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 <span data-ttu-id="b73b7-245">[!code-vb[csAsyncMethod&#1;](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="b73b7-245">[!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b73b7-246">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b73b7-246">See Also</span></span>  
 <span data-ttu-id="b73b7-247">[Sub 문](sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b73b7-247">[Sub Statement](sub-statement.md) </span></span>  
<span data-ttu-id="b73b7-248"> [Function 프로시저](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="b73b7-248"> [Function Procedures](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span></span>  
<span data-ttu-id="b73b7-249"> [매개 변수 목록](parameter-list.md) </span><span class="sxs-lookup"><span data-stu-id="b73b7-249"> [Parameter List](parameter-list.md) </span></span>  
<span data-ttu-id="b73b7-250"> [Dim 문](dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b73b7-250"> [Dim Statement](dim-statement.md) </span></span>  
<span data-ttu-id="b73b7-251"> [Call 문](call-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b73b7-251"> [Call Statement](call-statement.md) </span></span>  
<span data-ttu-id="b73b7-252"> [Of](of-clause.md) </span><span class="sxs-lookup"><span data-stu-id="b73b7-252"> [Of](of-clause.md) </span></span>  
<span data-ttu-id="b73b7-253"> [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="b73b7-253"> [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md) </span></span>  
<span data-ttu-id="b73b7-254"> [방법: 제네릭 클래스 사용](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span><span class="sxs-lookup"><span data-stu-id="b73b7-254"> [How to: Use a Generic Class](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span></span>  
<span data-ttu-id="b73b7-255"> [문제 해결 절차](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="b73b7-255"> [Troubleshooting Procedures](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="b73b7-256"> [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="b73b7-256"> [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span></span>  
<span data-ttu-id="b73b7-257"> [함수 식](../../../visual-basic/language-reference/operators/function-expression.md)</span><span class="sxs-lookup"><span data-stu-id="b73b7-257"> [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md)</span></span>

