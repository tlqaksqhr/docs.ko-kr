---
title: Sub 문(Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: 08be38cdbec82914b567ab5b86eed71181efcf57
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="69f23-102">Sub 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69f23-102">Sub Statement (Visual Basic)</span></span>
<span data-ttu-id="69f23-103">선언 이름과 매개 변수를 정의 하는 코드는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69f23-104">구문</span><span class="sxs-lookup"><span data-stu-id="69f23-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="69f23-105">요소</span><span class="sxs-lookup"><span data-stu-id="69f23-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="69f23-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-106">Optional.</span></span> <span data-ttu-id="69f23-107">참조 [특성 목록](attribute-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `Partial`  
  
     <span data-ttu-id="69f23-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-108">Optional.</span></span> <span data-ttu-id="69f23-109">부분 메서드의 정의 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="69f23-110">참조 [부분 메서드](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="69f23-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-111">Optional.</span></span> <span data-ttu-id="69f23-112">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="69f23-113">공용</span><span class="sxs-lookup"><span data-stu-id="69f23-113">Public</span></span>](../modifiers/public.md)  
  
    -   [<span data-ttu-id="69f23-114">보호됨</span><span class="sxs-lookup"><span data-stu-id="69f23-114">Protected</span></span>](../modifiers/protected.md)  
  
    -   [<span data-ttu-id="69f23-115">Friend</span><span class="sxs-lookup"><span data-stu-id="69f23-115">Friend</span></span>](../modifiers/friend.md)  
  
    -   [<span data-ttu-id="69f23-116">전용</span><span class="sxs-lookup"><span data-stu-id="69f23-116">Private</span></span>](../modifiers/private.md)  
  
    - [<span data-ttu-id="69f23-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="69f23-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

    - [<span data-ttu-id="69f23-118">보호 된 개인</span><span class="sxs-lookup"><span data-stu-id="69f23-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)
  
     <span data-ttu-id="69f23-119">참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="69f23-120">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-120">Optional.</span></span> <span data-ttu-id="69f23-121">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-121">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="69f23-122">오버로드</span><span class="sxs-lookup"><span data-stu-id="69f23-122">Overloads</span></span>](../modifiers/overloads.md)  
  
    -   [<span data-ttu-id="69f23-123">재정의</span><span class="sxs-lookup"><span data-stu-id="69f23-123">Overrides</span></span>](../modifiers/overrides.md)  
  
    -   [<span data-ttu-id="69f23-124">재정의 가능</span><span class="sxs-lookup"><span data-stu-id="69f23-124">Overridable</span></span>](../modifiers/overridable.md)  
  
    -   [<span data-ttu-id="69f23-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="69f23-125">NotOverridable</span></span>](../modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="69f23-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="69f23-126">MustOverride</span></span>](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="69f23-127">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-127">Optional.</span></span> <span data-ttu-id="69f23-128">참조 [공유](../modifiers/shared.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-128">See [Shared](../modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="69f23-129">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-129">Optional.</span></span> <span data-ttu-id="69f23-130">참조 [그림자](../modifiers/shadows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-130">See [Shadows](../modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="69f23-131">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-131">Optional.</span></span> <span data-ttu-id="69f23-132">참조 [비동기](../modifiers/async.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-132">See [Async](../modifiers/async.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="69f23-133">필수.</span><span class="sxs-lookup"><span data-stu-id="69f23-133">Required.</span></span> <span data-ttu-id="69f23-134">프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-134">Name of the procedure.</span></span> <span data-ttu-id="69f23-135">참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-135">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="69f23-136">생성자를 클래스에 대 한 프로시저를 만들려면 설정의 이름을 `Sub` 프로시저에는 `New` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="69f23-137">자세한 내용은 참조 [개체 수명: 개체가 만들어지고 소멸 되는 하는 방법을](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="69f23-138">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-138">Optional.</span></span> <span data-ttu-id="69f23-139">제네릭 프로시저에 대 한 형식 매개 변수의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="69f23-140">참조 [목록을 입력](type-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-140">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="69f23-141">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-141">Optional.</span></span> <span data-ttu-id="69f23-142">이 프로시저의 매개 변수를 나타내는 지역 변수 이름의 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="69f23-143">참조 [매개 변수 목록](parameter-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-143">See [Parameter List](parameter-list.md).</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="69f23-144">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-144">Optional.</span></span> <span data-ttu-id="69f23-145">하나 이상의이 절차를 구현 함을 나타냅니다 `Sub` 절차,이 프로시저의 포함 하는 클래스 또는 구조체에서 구현 되는 인터페이스에 정의 된 하나씩 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="69f23-146">참조 [문을 구현](implements-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-146">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="69f23-147">`Implements`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="69f23-148">구현할 `Sub` 프로시저 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-148">List of `Sub` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="69f23-149">각 `implementedprocedure`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-149">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="69f23-150">파트</span><span class="sxs-lookup"><span data-stu-id="69f23-150">Part</span></span>|<span data-ttu-id="69f23-151">설명</span><span class="sxs-lookup"><span data-stu-id="69f23-151">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="69f23-152">필수.</span><span class="sxs-lookup"><span data-stu-id="69f23-152">Required.</span></span> <span data-ttu-id="69f23-153">이 프로시저에 의해 구현 되는 인터페이스의 이름의 클래스 또는 구조체를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="69f23-154">필수.</span><span class="sxs-lookup"><span data-stu-id="69f23-154">Required.</span></span> <span data-ttu-id="69f23-155">프로시저가 `interface`에 정의되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-155">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="69f23-156">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-156">Optional.</span></span> <span data-ttu-id="69f23-157">이 절차에서 하나 이상의 특정 이벤트를 처리할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="69f23-158">참조 [처리](handles-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-158">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="69f23-159">`Handles`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="69f23-160">이 프로시저에서 처리 하는 이벤트 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-160">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="69f23-161">각 `eventspecifier`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-161">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="69f23-162">파트</span><span class="sxs-lookup"><span data-stu-id="69f23-162">Part</span></span>|<span data-ttu-id="69f23-163">설명</span><span class="sxs-lookup"><span data-stu-id="69f23-163">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="69f23-164">필수.</span><span class="sxs-lookup"><span data-stu-id="69f23-164">Required.</span></span> <span data-ttu-id="69f23-165">개체 변수는 이벤트를 발생 시키는 구조체 또는 클래스의 데이터 형식으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="69f23-166">필수.</span><span class="sxs-lookup"><span data-stu-id="69f23-166">Required.</span></span> <span data-ttu-id="69f23-167">이 프로시저에서 처리 하는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-167">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="69f23-168">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-168">Optional.</span></span> <span data-ttu-id="69f23-169">문 블록을이 절차 내에서 실행 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-169">Block of statements to run within this procedure.</span></span>  
  
-   `End Sub`  
  
     <span data-ttu-id="69f23-170">이 프로시저의 정의 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-170">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69f23-171">설명</span><span class="sxs-lookup"><span data-stu-id="69f23-171">Remarks</span></span>  
 <span data-ttu-id="69f23-172">모든 실행 코드는 프로시저 안에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="69f23-173">사용 하 여 한 `Sub` 호출 코드에 값을 반환 하지 않을 때 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="69f23-174">사용 하 여 한 `Function` 프로시저는 값을 반환 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="69f23-174">Use a `Function` procedure when you want to return a value.</span></span>  
  
## <a name="defining-a-sub-procedure"></a><span data-ttu-id="69f23-175">Sub 프로시저를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-175">Defining a Sub Procedure</span></span>  
 <span data-ttu-id="69f23-176">정의할 수는 `Sub` 모듈 수준에만 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="69f23-177">Sub 프로시저에 대 한 선언 컨텍스트, 따라서 해야를 클래스, 구조체, 모듈 또는 인터페이스 및 소스 파일, 네임 스페이스, 프로시저 또는 블록으로 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="69f23-178">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69f23-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="69f23-179">`Sub` 프로시저는 기본적으로 공용 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="69f23-180">액세스 한정자를 사용 하 여 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-180">You can adjust their access levels by using the access modifiers.</span></span>  
  
 <span data-ttu-id="69f23-181">프로시저를 사용 하는 경우는 `Implements` 키워드를 포함 하는 클래스나 구조체 있어야는 `Implements` 바로 뒤에 오는 문을 해당 `Class` 또는 `Structure` 문.</span><span class="sxs-lookup"><span data-stu-id="69f23-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="69f23-182">`Implements` 문을에 지정 된 각 인터페이스를 포함 해야 `implementslist`합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="69f23-183">그러나는 인터페이스를 정의 하 여 이름을 `Sub` (에서 `definedname`)이이 프로시저의 이름과 일치 하지 않아도 (에서 `name`).</span><span class="sxs-lookup"><span data-stu-id="69f23-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>  
  
## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="69f23-184">Sub 프로시저에서 반환</span><span class="sxs-lookup"><span data-stu-id="69f23-184">Returning from a Sub Procedure</span></span>  
 <span data-ttu-id="69f23-185">경우는 `Sub` 문을 호출한 다음 문이 실행 계속 프로시저가 호출 코드에 반환 되 면 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>  
  
 <span data-ttu-id="69f23-186">다음 예제에서는에서 반환 된 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-186">The following example shows a return from a `Sub` procedure.</span></span>  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 <span data-ttu-id="69f23-187">`Exit Sub` 및 `Return` 문을 사용 하면 즉시 종료 한 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="69f23-188">개수에 관계 없이 `Exit Sub` 및 `Return` 문은 프로시저에서 아무 곳 이나 나타날 수 있으며 함께 사용할 수 있습니다 `Exit Sub` 및 `Return` 문.</span><span class="sxs-lookup"><span data-stu-id="69f23-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>  
  
## <a name="calling-a-sub-procedure"></a><span data-ttu-id="69f23-189">Sub 프로시저를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-189">Calling a Sub Procedure</span></span>  
 <span data-ttu-id="69f23-190">호출 하는 `Sub` 문에서 프로시저 이름을 사용 하 고 해당 이름에에서 해당 인수 목록 괄호로 묶어를 누른 다음으로 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="69f23-191">인수를 제공 하지 않는 경우에 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="69f23-192">그러나 코드는 항상 괄호를 포함 하는 경우 더 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-192">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="69f23-193">A `Sub` 절차와 `Function` 프로시저 매개 변수를 업데이트 하 고 일련의 문 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="69f23-194">그러나 한 `Function` 프로시저 반환 값 및 `Sub` 프로시저 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="69f23-195">따라서 사용할 수 없습니다는 `Sub` 식에는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>  
  
 <span data-ttu-id="69f23-196">사용할 수는 `Call` 호출할 때 키워드는 `Sub` 프로시저만 해당 키워드는 대부분의 사용자에 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="69f23-197">자세한 내용은 참조 [Call 문을](call-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-197">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="69f23-198">Visual Basic에는 산술 식 내부 효율성을 높이기 위해 경우에 따라 다시 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="69f23-199">이러한 이유로, 인수 목록에 다른 프로시저를 호출 하는 식이 포함 되어 있으면 있습니다 서는 안 식 됩니다 호출할 것으로 가정을 특정 순서로 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>  
  
## <a name="async-sub-procedures"></a><span data-ttu-id="69f23-200">비동기 Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="69f23-200">Async Sub Procedures</span></span>  
 <span data-ttu-id="69f23-201">비동기 기능을 사용 하면 명시적 콜백을 사용 하거나 수동으로 여러 함수 또는 람다 식에 코드를 분할 하지 않고도 비동기 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="69f23-202">사용 하 여 프로시저를 표시 하는 경우는 [비동기](../modifiers/async.md) 사용할 수 있습니다 한정자는 [Await](../../../visual-basic/language-reference/operators/await-operator.md) 연산자 프로시저에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="69f23-203">에 도달할 때 제어는 `Await` 식에는 `Async` 프로시저 호출자에 게 제어가 반환와 프로시저에서 진행 대기 중인된 작업이 완료 될 때까지 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="69f23-204">작업이 완료 될 때 실행 절차에서 다시 시작 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-204">When the task is complete, execution can resume in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69f23-205">`Async` 프로시저 중 하나는 첫 번째 대기 된 개체를 아직 완료 되지 않은 발견 되 면 호출자 또는의 끝에 반환 된 `Async` 프로시저에 도달 중 먼저 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>  
  
 <span data-ttu-id="69f23-206">표시할 수도 있습니다는 [Function 문을](function-statement.md) 와 `Async` 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="69f23-207">`Async` 함수 반환 형식으로 지정할 수 있습니다 <xref:System.Threading.Tasks.Task%601> 또는 <xref:System.Threading.Tasks.Task>합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="69f23-208">예로 나중에이 항목에서는 `Async` 의 반환 형식을 가진 함수를 <xref:System.Threading.Tasks.Task%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="69f23-209">`Async` `Sub` 이벤트 처리기에 대 한 프로시저 주로 사용 됩니다이 값을 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="69f23-210">`Async``Sub` 프로시저 대기할 수 없습니다 및의 호출자는 `Async``Sub` 프로시저 예외를 catch 할 수 없습니다 하는 `Sub` 프로시저 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-210">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>  
  
 <span data-ttu-id="69f23-211">`Async` 프로시저 모두를 선언할 수 없습니다 [ByRef](../modifiers/byref.md) 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="69f23-212">에 대 한 자세한 내용은 `Async` 프로시저 참조 [Async 및 Await를 사용한 비동기 프로그래밍](../../../visual-basic/programming-guide/concepts/async/index.md), [비동기 프로그램의 제어 흐름](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), 및 [비동기 반환 형식](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="69f23-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="69f23-213">예제</span><span class="sxs-lookup"><span data-stu-id="69f23-213">Example</span></span>  
 <span data-ttu-id="69f23-214">다음 예제에서는 `Sub` 을 이름, 매개 변수 및 코드의 본문을 형성 하는 정의 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="69f23-215">예제</span><span class="sxs-lookup"><span data-stu-id="69f23-215">Example</span></span>  
 <span data-ttu-id="69f23-216">다음 예에서 `DelayAsync` 는 `Async``Function` 의 반환 형식이 있는 <xref:System.Threading.Tasks.Task%601>합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-216">In the following example, `DelayAsync` is an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="69f23-217">`DelayAsync`에는 정수를 반환하는 `Return` 문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="69f23-218">따라서 함수 선언의 `DelayAsync` 의 반환 형식이 있어야 합니다. `Task(Of Integer)`합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="69f23-219">반환 형식이 이기 `Task(Of Integer)`, 평가 `Await` 에 식을 `DoSomethingAsync` 다음 문과 같이 정수를 생성 합니다.: `Dim result As Integer = Await delayTask`합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="69f23-220">`startButton_Click` 절차의 한 예로 `Async Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="69f23-221">때문에 `DoSomethingAsync` 는 `Async` 함수, 작업에 대 한 호출에 대 한 `DoSomethingAsync` 기다려야, 다음 문과 같이: `Await DoSomethingAsync()`합니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="69f23-222">`startButton_Click``Sub` 프로시저 함께 정의 되어야 합니다는 `Async` 한정자 있기 때문에 `Await` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="69f23-222">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="69f23-223">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69f23-223">See Also</span></span>  
 [<span data-ttu-id="69f23-224">Implements 문</span><span class="sxs-lookup"><span data-stu-id="69f23-224">Implements Statement</span></span>](implements-statement.md)  
 [<span data-ttu-id="69f23-225">Function 문</span><span class="sxs-lookup"><span data-stu-id="69f23-225">Function Statement</span></span>](function-statement.md)  
 [<span data-ttu-id="69f23-226">매개 변수 목록</span><span class="sxs-lookup"><span data-stu-id="69f23-226">Parameter List</span></span>](parameter-list.md)  
 [<span data-ttu-id="69f23-227">Dim 문</span><span class="sxs-lookup"><span data-stu-id="69f23-227">Dim Statement</span></span>](dim-statement.md)  
 [<span data-ttu-id="69f23-228">Call 문</span><span class="sxs-lookup"><span data-stu-id="69f23-228">Call Statement</span></span>](call-statement.md)  
 [<span data-ttu-id="69f23-229">Of</span><span class="sxs-lookup"><span data-stu-id="69f23-229">Of</span></span>](of-clause.md)  
 [<span data-ttu-id="69f23-230">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="69f23-230">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [<span data-ttu-id="69f23-231">방법: 제네릭 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="69f23-231">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="69f23-232">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="69f23-232">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [<span data-ttu-id="69f23-233">부분 메서드</span><span class="sxs-lookup"><span data-stu-id="69f23-233">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
