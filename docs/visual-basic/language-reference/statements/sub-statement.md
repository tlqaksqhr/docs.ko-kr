---
title: "Sub 문 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Sub
dev_langs:
- VB
helpviewer_keywords:
- Public keyword, Sub statements
- procedures, creating
- declaring procedures, Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword, Sub statements
- Optional keyword, Sub statements
- declarations, procedures
- Sub keyword
- Handles keyword, Sub statements
- Protected Friend keyword
- ParamArray keyword, Sub statements
- Implements keyword, Sub statements
- Sub statement
- subroutines
- ByRef keyword, Sub statements
- Sub procedures, Sub statement
- recursive procedures
- Private keyword, Sub statements
- Friend keyword, Sub statements
- Exit statement, Sub statements
- procedures, Sub
- End keyword, Sub statements
- ByVal keyword, Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
caps.latest.revision: 52
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
ms.openlocfilehash: 61853a4f2321837683997b8e4241b688bc9f622c
ms.contentlocale: ko-kr
ms.lasthandoff: 05/15/2017

---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="70e75-102">Sub 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70e75-102">Sub Statement (Visual Basic)</span></span>
<span data-ttu-id="70e75-103">선언 이름과 매개 변수를 정의 하는 코드는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70e75-104">구문</span><span class="sxs-lookup"><span data-stu-id="70e75-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="70e75-105">요소</span><span class="sxs-lookup"><span data-stu-id="70e75-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="70e75-106">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-106">Optional.</span></span> <span data-ttu-id="70e75-107">참조 [특성 목록](attribute-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `Partial`  
  
     <span data-ttu-id="70e75-108">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-108">Optional.</span></span> <span data-ttu-id="70e75-109">부분 메서드의 정의 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="70e75-110">참조 [부분 메서드](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="70e75-111">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-111">Optional.</span></span> <span data-ttu-id="70e75-112">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="70e75-113">공용</span><span class="sxs-lookup"><span data-stu-id="70e75-113">Public</span></span>](../modifiers/public.md)  
  
    -   [<span data-ttu-id="70e75-114">보호됨</span><span class="sxs-lookup"><span data-stu-id="70e75-114">Protected</span></span>](../modifiers/protected.md)  
  
    -   [<span data-ttu-id="70e75-115">Friend</span><span class="sxs-lookup"><span data-stu-id="70e75-115">Friend</span></span>](../modifiers/friend.md)  
  
    -   [<span data-ttu-id="70e75-116">전용</span><span class="sxs-lookup"><span data-stu-id="70e75-116">Private</span></span>](../modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="70e75-117">참조 [액세스 수준 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-117">See [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="70e75-118">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-118">Optional.</span></span> <span data-ttu-id="70e75-119">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-119">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="70e75-120">오버로드</span><span class="sxs-lookup"><span data-stu-id="70e75-120">Overloads</span></span>](../modifiers/overloads.md)  
  
    -   [<span data-ttu-id="70e75-121">재정의</span><span class="sxs-lookup"><span data-stu-id="70e75-121">Overrides</span></span>](../modifiers/overrides.md)  
  
    -   [<span data-ttu-id="70e75-122">재정의 가능</span><span class="sxs-lookup"><span data-stu-id="70e75-122">Overridable</span></span>](../modifiers/overridable.md)  
  
    -   [<span data-ttu-id="70e75-123">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="70e75-123">NotOverridable</span></span>](../modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="70e75-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="70e75-124">MustOverride</span></span>](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="70e75-125">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-125">Optional.</span></span> <span data-ttu-id="70e75-126">참조 [공유](../modifiers/shared.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-126">See [Shared](../modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="70e75-127">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-127">Optional.</span></span> <span data-ttu-id="70e75-128">참조 [그림자](../modifiers/shadows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-128">See [Shadows](../modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="70e75-129">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-129">Optional.</span></span> <span data-ttu-id="70e75-130">참조 [비동기](../modifiers/async.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-130">See [Async](../modifiers/async.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="70e75-131">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-131">Required.</span></span> <span data-ttu-id="70e75-132">프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-132">Name of the procedure.</span></span> <span data-ttu-id="70e75-133">참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-133">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="70e75-134">클래스의 생성자를 프로시저를 만들려면 설정의 이름을 `Sub` 하는 절차는 `New` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-134">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="70e75-135">자세한 내용은 참조 [개체 수명: 개체가 만들어지고 소멸 되는 하는 방법을](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-135">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="70e75-136">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-136">Optional.</span></span> <span data-ttu-id="70e75-137">제네릭 프로시저에 대 한 형식 매개 변수의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-137">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="70e75-138">참조 [목록을 입력](type-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-138">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="70e75-139">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-139">Optional.</span></span> <span data-ttu-id="70e75-140">이 절차의 매개 변수를 나타내는 로컬 변수 이름의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-140">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="70e75-141">참조 [매개 변수 목록](parameter-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-141">See [Parameter List](parameter-list.md).</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="70e75-142">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-142">Optional.</span></span> <span data-ttu-id="70e75-143">이 절차를 하나 이상 구현 함을 나타냅니다 `Sub` 절차,이 절차의 포함 하는 클래스 또는 구조체에서 구현 되는 인터페이스에 정의 된 각 것입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-143">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="70e75-144">참조 [문을 구현](implements-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-144">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="70e75-145">`Implements`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-145">Required if `Implements` is supplied.</span></span> <span data-ttu-id="70e75-146">구현할 `Sub` 프로시저 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-146">List of `Sub` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="70e75-147">각 `implementedprocedure`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-147">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="70e75-148">파트</span><span class="sxs-lookup"><span data-stu-id="70e75-148">Part</span></span>|<span data-ttu-id="70e75-149">설명</span><span class="sxs-lookup"><span data-stu-id="70e75-149">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="70e75-150">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-150">Required.</span></span> <span data-ttu-id="70e75-151">이 프로시저에 의해 구현 되는 인터페이스의 이름의 클래스 또는 구조체를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-151">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="70e75-152">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-152">Required.</span></span> <span data-ttu-id="70e75-153">프로시저가 `interface`에 정의되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-153">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="70e75-154">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-154">Optional.</span></span> <span data-ttu-id="70e75-155">이 절차에서 하나 이상의 특정 이벤트를 처리할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-155">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="70e75-156">참조 [처리](handles-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-156">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="70e75-157">`Handles`가 제공된 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-157">Required if `Handles` is supplied.</span></span> <span data-ttu-id="70e75-158">이 프로시저에서 처리 하는 이벤트 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-158">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="70e75-159">각 `eventspecifier`에는 다음과 같은 구문과 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-159">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="70e75-160">파트</span><span class="sxs-lookup"><span data-stu-id="70e75-160">Part</span></span>|<span data-ttu-id="70e75-161">설명</span><span class="sxs-lookup"><span data-stu-id="70e75-161">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="70e75-162">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-162">Required.</span></span> <span data-ttu-id="70e75-163">클래스 또는 이벤트를 발생 하는 구조체의 데이터 형식으로 선언 된 개체 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-163">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="70e75-164">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-164">Required.</span></span> <span data-ttu-id="70e75-165">이 프로시저에서 처리 하는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-165">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="70e75-166">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="70e75-166">Optional.</span></span> <span data-ttu-id="70e75-167">이 프로시저 내에서 실행 하는 문 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-167">Block of statements to run within this procedure.</span></span>  
  
-   `End Sub`  
  
     <span data-ttu-id="70e75-168">이 프로시저의 정의 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-168">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70e75-169">주의</span><span class="sxs-lookup"><span data-stu-id="70e75-169">Remarks</span></span>  
 <span data-ttu-id="70e75-170">모든 실행 코드는 프로시저 안에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-170">All executable code must be inside a procedure.</span></span> <span data-ttu-id="70e75-171">사용 하는 `Sub` 호출 코드에는 값을 반환 하지 않을 때 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-171">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="70e75-172">사용 된 `Function` 프로시저는 값을 반환 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="70e75-172">Use a `Function` procedure when you want to return a value.</span></span>  
  
## <a name="defining-a-sub-procedure"></a><span data-ttu-id="70e75-173">Sub 프로시저를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-173">Defining a Sub Procedure</span></span>  
 <span data-ttu-id="70e75-174">정의할 수는 `Sub` 모듈 수준에만 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-174">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="70e75-175">Sub 프로시저에 대 한 선언 컨텍스트, 따라서 해야 클래스, 구조체, 모듈의 경우, 또는 인터페이스 및 소스 파일, 네임 스페이스, 프로시저 또는 블록 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-175">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="70e75-176">자세한 내용은 참조 [선언 컨텍스트 및 기본 액세스 수준](declaration-contexts-and-default-access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-176">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="70e75-177">`Sub`프로시저는 기본적으로 공용 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-177">`Sub` procedures default to public access.</span></span> <span data-ttu-id="70e75-178">액세스 한정자를 사용 하 여 액세스 수준을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-178">You can adjust their access levels by using the access modifiers.</span></span>  
  
 <span data-ttu-id="70e75-179">프로시저를 사용 하는 경우는 `Implements` 키워드를 포함 하는 클래스나 구조체 있어야는 `Implements` 문 바로 뒤에 오는 해당 `Class` 또는 `Structure` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-179">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="70e75-180">`Implements` 문을에 지정 된 각 인터페이스를 포함 해야 `implementslist`합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-180">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="70e75-181">그러나 인터페이스 정의는 이름에서 `Sub` (에서 `definedname`)이이 프로시저의 이름과 일치 하지 않아도 (에서 `name`).</span><span class="sxs-lookup"><span data-stu-id="70e75-181">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>  
  
## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="70e75-182">Sub 프로시저에서 반환</span><span class="sxs-lookup"><span data-stu-id="70e75-182">Returning from a Sub Procedure</span></span>  
 <span data-ttu-id="70e75-183">경우는 `Sub` 프로시저가 호출 코드로 반환 되 면 실행이 호출 하는 문 다음 문을 사용 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-183">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>  
  
 <span data-ttu-id="70e75-184">다음 예제에서 반환 된 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-184">The following example shows a return from a `Sub` procedure.</span></span>  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 <span data-ttu-id="70e75-185">`Exit Sub` 및 `Return` 문을 사용 하면 즉시 종료 한 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-185">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="70e75-186">개수에 관계 없이 `Exit Sub` 및 `Return` 문을 프로시저에서 아무 곳 이나 나타날 수 있으며 혼합할 수 `Exit Sub` 및 `Return` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-186">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>  
  
## <a name="calling-a-sub-procedure"></a><span data-ttu-id="70e75-187">Sub 프로시저를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-187">Calling a Sub Procedure</span></span>  
 <span data-ttu-id="70e75-188">호출을 `Sub` 문에서 프로시저 이름을 사용 하 여 해당 인수 목록 괄호로 묶어 해당 이름 뒤에 다음 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-188">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="70e75-189">모든 인수를 지정 하지 않으면 경우에 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-189">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="70e75-190">그러나이 코드는 항상 괄호를 포함 하는 경우 보다 읽기 쉬운.</span><span class="sxs-lookup"><span data-stu-id="70e75-190">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="70e75-191">A `Sub` 절차와 `Function` 프로시저 매개 변수를 업데이트 하 고 일련의 문 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-191">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="70e75-192">그러나 한 `Function` 프로시저 반환 값, 그리고 `Sub` 프로시저 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-192">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="70e75-193">따라서 사용할 수 없습니다는 `Sub` 식에는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-193">Therefore, you can't use a `Sub` procedure in an expression.</span></span>  
  
 <span data-ttu-id="70e75-194">사용할 수는 `Call` 를 호출할 때 키워드는 `Sub` 프로시저 되지만 해당 키워드는 대부분의 사용에 대 한 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-194">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="70e75-195">자세한 내용은 참조 [Call 문을](call-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-195">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="70e75-196">Visual Basic에는 산술 식 내부 효율성을 높이기 위해 경우에 따라 다시 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-196">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="70e75-197">이런 이유로 인수 목록에 다른 프로시저를 호출 하는 식이 포함 되어 있는 경우 서는 안 가정 해당 식을 특정 한 순서로 이라는.</span><span class="sxs-lookup"><span data-stu-id="70e75-197">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>  
  
## <a name="async-sub-procedures"></a><span data-ttu-id="70e75-198">비동기 Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="70e75-198">Async Sub Procedures</span></span>  
 <span data-ttu-id="70e75-199">비동기 기능을 사용 하 여 명시적 콜백을 사용 하거나 수동으로 여러 함수 또는 람다 식에 코드를 분할 하지 않고 비동기 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-199">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="70e75-200">프로시저를 표시 하는 경우는 [비동기](../modifiers/async.md) 한정자를 사용해는 [Await](../../../visual-basic/language-reference/operators/await-operator.md) 절차에서 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-200">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="70e75-201">때에 수신 되 면 제어는 `Await` 식에는 `Async` 프로시저 호출자에 게 제어가 반환 및 절차에서 진행 대기 중인된 작업이 완료 될 때까지 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-201">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="70e75-202">작업이 완료 되 면 실행 절차에서 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-202">When the task is complete, execution can resume in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70e75-203">`Async` 프로시저 중 하나는 첫 번째 대기 된 개체를 아직 완료 되지 않은 발생 하면 호출자 또는 끝에 반환 된 `Async` 프로시저에 도달 하는 중 먼저 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-203">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>  
  
 <span data-ttu-id="70e75-204">표시할 수도 있습니다는 [Function 문의](function-statement.md) 와 `Async` 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-204">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="70e75-205">`Async` 함수 <xref:System.Threading.Tasks.Task%601>또는 <xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601> 의 반환 형식을 가질 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="70e75-205">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="70e75-206">예로 나중에이 항목에서는 한 `Async` <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> 의 반환 형식을 갖는 함수</span><span class="sxs-lookup"><span data-stu-id="70e75-206">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="70e75-207">`Async``Sub` 프로시저는 주로 사용 이벤트 처리기에 대 한 값을 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-207">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="70e75-208">`Async``Sub` 프로시저 대기할 수 없습니다 및의 호출자는 `Async``Sub` 프로시저 예외를 catch 할 수 없습니다 하는 `Sub` 프로시저 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-208">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>  
  
 <span data-ttu-id="70e75-209">`Async` 모든 프로시저를 선언할 수 없습니다 [ByRef](../modifiers/byref.md) 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-209">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="70e75-210">에 대 한 자세한 내용은 `Async` 프로시저 참조 [Async 및 Await를 사용한 비동기 프로그래밍](../../../visual-basic/programming-guide/concepts/async/index.md), [비동기 프로그램의 제어 흐름](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), 및 [비동기 반환 형식](../../../visual-basic/programming-guide/concepts/async/async-return-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-210">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="70e75-211">예제</span><span class="sxs-lookup"><span data-stu-id="70e75-211">Example</span></span>  
 <span data-ttu-id="70e75-212">사용 하 여 다음 예제는 `Sub` 이름, 매개 변수, 및의 본문을 형성 하는 코드를 정의 하는 문에 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-212">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>  
  
 <span data-ttu-id="70e75-213">[!code-vb[VbVbalrStatements #&58;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="70e75-213">[!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="70e75-214">예제</span><span class="sxs-lookup"><span data-stu-id="70e75-214">Example</span></span>  
 <span data-ttu-id="70e75-215">다음 예에서 `DelayAsync` 는는 `Async``Function` <xref:System.Threading.Tasks.Task%601>.</xref:System.Threading.Tasks.Task%601> 의 반환 형식이 있는</span><span class="sxs-lookup"><span data-stu-id="70e75-215">In the following example, `DelayAsync` is an an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="70e75-216">`DelayAsync`에는 정수를 반환하는 `Return` 문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-216">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="70e75-217">따라서 함수 선언의 `DelayAsync` 의 반환 형식이 있어야 `Task(Of Integer)`합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-217">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="70e75-218">반환 형식이 이기 `Task(Of Integer)`의 평가 `Await` 식 `DoSomethingAsync` 정수, 다음 문 에서처럼 생성: `Dim result As Integer = Await delayTask`합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-218">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="70e75-219">`startButton_Click` 프로시저의 한 예로 `Async Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-219">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="70e75-220">때문에 `DoSomethingAsync` 는 `Async` 함수, 작업에 대 한 호출에 대 한 `DoSomethingAsync` 다음 문 에서처럼 대기 해야 합니다: `Await DoSomethingAsync()`합니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-220">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="70e75-221">`startButton_Click``Sub` 으로 프로시저를 정의 해야는 `Async` 한정자 되었기 때문에 `Await` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="70e75-221">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 <span data-ttu-id="70e75-222">[!code-vb[csAsyncMethod&#1;](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="70e75-222">[!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70e75-223">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70e75-223">See Also</span></span>  
 <span data-ttu-id="70e75-224">[Implements 문](implements-statement.md) </span><span class="sxs-lookup"><span data-stu-id="70e75-224">[Implements Statement](implements-statement.md) </span></span>  
<span data-ttu-id="70e75-225"> [Function 문](function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="70e75-225"> [Function Statement](function-statement.md) </span></span>  
<span data-ttu-id="70e75-226"> [매개 변수 목록](parameter-list.md) </span><span class="sxs-lookup"><span data-stu-id="70e75-226"> [Parameter List](parameter-list.md) </span></span>  
<span data-ttu-id="70e75-227"> [Dim 문](dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="70e75-227"> [Dim Statement](dim-statement.md) </span></span>  
<span data-ttu-id="70e75-228"> [Call 문](call-statement.md) </span><span class="sxs-lookup"><span data-stu-id="70e75-228"> [Call Statement](call-statement.md) </span></span>  
<span data-ttu-id="70e75-229"> [Of](of-clause.md) </span><span class="sxs-lookup"><span data-stu-id="70e75-229"> [Of](of-clause.md) </span></span>  
<span data-ttu-id="70e75-230"> [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="70e75-230"> [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md) </span></span>  
<span data-ttu-id="70e75-231"> [방법: 제네릭 클래스 사용](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span><span class="sxs-lookup"><span data-stu-id="70e75-231"> [How to: Use a Generic Class](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span></span>  
<span data-ttu-id="70e75-232"> [문제 해결 절차](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="70e75-232"> [Troubleshooting Procedures](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="70e75-233"> [부분 메서드](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)</span><span class="sxs-lookup"><span data-stu-id="70e75-233"> [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)</span></span>

