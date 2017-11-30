---
title: "Visual Basic의 범위"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- module scope [Visual Basic]
- scope [Visual Basic], levels
- module level
- procedures [Visual Basic], scope
- declared elements [Visual Basic], scope
- namespaces [Visual Basic], scope
- scope [Visual Basic], declared elements
- scope [Visual Basic], about scope
- levels of scope [Visual Basic]
- block scope [Visual Basic]
- scope [Visual Basic], Visual Basic
- procedure scope [Visual Basic]
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9bfda19b9f5ee96d45a0322541b35dfab7635d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="scope-in-visual-basic"></a><span data-ttu-id="98bab-102">Visual Basic의 범위</span><span class="sxs-lookup"><span data-stu-id="98bab-102">Scope in Visual Basic</span></span>
<span data-ttu-id="98bab-103">*범위* 의 선언 된 요소는 집합을 통해 사용할 수 있도록 하거나 이름을 한정 하지 않고 변수를 참조할 수 있는 모든 코드는 [Imports 문 (.NET Namespace 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-103">The *scope* of a declared element is the set of all code that can refer to it without qualifying its name or making it available through an [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span> <span data-ttu-id="98bab-104">요소는 다음 수준 중 하나에서 범위를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-104">An element can have scope at one of the following levels:</span></span>  
  
|<span data-ttu-id="98bab-105">수준</span><span class="sxs-lookup"><span data-stu-id="98bab-105">Level</span></span>|<span data-ttu-id="98bab-106">설명</span><span class="sxs-lookup"><span data-stu-id="98bab-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="98bab-107">블록 범위</span><span class="sxs-lookup"><span data-stu-id="98bab-107">Block scope</span></span>|<span data-ttu-id="98bab-108">선언 된 블록 코드 내 에서만 사용 가능</span><span class="sxs-lookup"><span data-stu-id="98bab-108">Available only within the code block in which it is declared</span></span>|  
|<span data-ttu-id="98bab-109">프로시저 범위</span><span class="sxs-lookup"><span data-stu-id="98bab-109">Procedure scope</span></span>|<span data-ttu-id="98bab-110">선언 된 프로시저 내의 모든 코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-110">Available to all code within the procedure in which it is declared</span></span>|  
|<span data-ttu-id="98bab-111">모듈 범위</span><span class="sxs-lookup"><span data-stu-id="98bab-111">Module scope</span></span>|<span data-ttu-id="98bab-112">모듈, 클래스 또는 선언 된 구조 내의 모든 코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-112">Available to all code within the module, class, or structure in which it is declared</span></span>|  
|<span data-ttu-id="98bab-113">Namespace 범위</span><span class="sxs-lookup"><span data-stu-id="98bab-113">Namespace scope</span></span>|<span data-ttu-id="98bab-114">선언 된 네임 스페이스의 모든 코드에서 사용할 수</span><span class="sxs-lookup"><span data-stu-id="98bab-114">Available to all code in the namespace in which it is declared</span></span>|  
  
 <span data-ttu-id="98bab-115">이러한 범위의 수준은 범위는 가장 좁은 (블록)에서 가장 넓은 (네임 스페이스), 여기서 *가장 좁은 범위* 한정자 없이 요소를 참조할 수 있는 코드의 가장 작은 집합을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-115">These levels of scope progress from the narrowest (block) to the widest (namespace), where *narrowest scope* means the smallest set of code that can refer to the element without qualification.</span></span> <span data-ttu-id="98bab-116">자세한 내용은이 페이지에 "범위 수준"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="98bab-116">For more information, see "Levels of Scope" on this page.</span></span>  
  
## <a name="specifying-scope-and-defining-variables"></a><span data-ttu-id="98bab-117">범위를 지정 하 고 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-117">Specifying Scope and Defining Variables</span></span>  
 <span data-ttu-id="98bab-118">선언할 때에 요소의 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-118">You specify the scope of an element when you declare it.</span></span> <span data-ttu-id="98bab-119">범위는 다음 요인에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-119">The scope can depend on the following factors:</span></span>  
  
-   <span data-ttu-id="98bab-120">요소를 선언한 지역 (블록, 프로시저, 모듈, 클래스 또는 구조체)</span><span class="sxs-lookup"><span data-stu-id="98bab-120">The region (block, procedure, module, class, or structure) in which you declare the element</span></span>  
  
-   <span data-ttu-id="98bab-121">요소의 선언이 포함 된 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="98bab-121">The namespace containing the element's declaration</span></span>  
  
-   <span data-ttu-id="98bab-122">요소에 대해 선언 하는 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="98bab-122">The access level you declare for the element</span></span>  
  
 <span data-ttu-id="98bab-123">이렇게 하기 때문에 이름은 같지만 다른 범위를 사용 하 여 변수를 정의 하는 경우 주의 해야 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-123">Use care when you define variables with the same name but different scope, because doing so can lead to unexpected results.</span></span> <span data-ttu-id="98bab-124">자세한 내용은 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98bab-124">For more information, see [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="levels-of-scope"></a><span data-ttu-id="98bab-125">범위 수준</span><span class="sxs-lookup"><span data-stu-id="98bab-125">Levels of Scope</span></span>  
 <span data-ttu-id="98bab-126">프로그래밍 요소 선언에 있는 영역을 통해 ´ ù.</span><span class="sxs-lookup"><span data-stu-id="98bab-126">A programming element is available throughout the region in which you declare it.</span></span> <span data-ttu-id="98bab-127">동일한 지역에 있는 모든 코드 요소에 해당 이름을 한정 하지 않고 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-127">All code in the same region can refer to the element without qualifying its name.</span></span>  
  
### <a name="block-scope"></a><span data-ttu-id="98bab-128">블록 범위</span><span class="sxs-lookup"><span data-stu-id="98bab-128">Block Scope</span></span>  
 <span data-ttu-id="98bab-129">블록은 시작 하 고 다음과 같은 선언문 종료 사이 포함 된 문 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-129">A block is a set of statements enclosed within initiating and terminating declaration statements, such as the following:</span></span>  
  
-   <span data-ttu-id="98bab-130">`Do` 및 `Loop`</span><span class="sxs-lookup"><span data-stu-id="98bab-130">`Do` and `Loop`</span></span>  
  
-   <span data-ttu-id="98bab-131">`For`[`Each`] 및`Next`</span><span class="sxs-lookup"><span data-stu-id="98bab-131">`For` [`Each`] and `Next`</span></span>  
  
-   <span data-ttu-id="98bab-132">`If` 및 `End If`</span><span class="sxs-lookup"><span data-stu-id="98bab-132">`If` and `End If`</span></span>  
  
-   <span data-ttu-id="98bab-133">`Select` 및 `End Select`</span><span class="sxs-lookup"><span data-stu-id="98bab-133">`Select` and `End Select`</span></span>  
  
-   <span data-ttu-id="98bab-134">`SyncLock` 및 `End SyncLock`</span><span class="sxs-lookup"><span data-stu-id="98bab-134">`SyncLock` and `End SyncLock`</span></span>  
  
-   <span data-ttu-id="98bab-135">`Try` 및 `End Try`</span><span class="sxs-lookup"><span data-stu-id="98bab-135">`Try` and `End Try`</span></span>  
  
-   <span data-ttu-id="98bab-136">`While` 및 `End While`</span><span class="sxs-lookup"><span data-stu-id="98bab-136">`While` and `End While`</span></span>  
  
-   <span data-ttu-id="98bab-137">`With` 및 `End With`</span><span class="sxs-lookup"><span data-stu-id="98bab-137">`With` and `End With`</span></span>  
  
 <span data-ttu-id="98bab-138">블록 내에서 변수를 선언 하는 경우 해당 블록 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-138">If you declare a variable within a block, you can use it only within that block.</span></span> <span data-ttu-id="98bab-139">다음 예제에서는 정수 변수의 범위에에서 `cube` 사이의 블록 `If` 및 `End If`, 있으며 더 이상 참조할 수 없습니다 `cube` 때 실행 블록 밖으로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-139">In the following example, the scope of the integer variable `cube` is the block between `If` and `End If`, and you can no longer refer to `cube` when execution passes out of the block.</span></span>  
  
```  
If n < 1291 Then  
    Dim cube As Integer  
    cube = n ^ 3  
End If  
```  
  
> [!NOTE]
>  <span data-ttu-id="98bab-140">변수 범위를 블록으로 제한 하는 경우에 해당 수명은 전체 절차의 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-140">Even if the scope of a variable is limited to a block, its lifetime is still that of the entire procedure.</span></span> <span data-ttu-id="98bab-141">절차 중 블록을 여러 번 입력 하는 경우 각 블록 변수는 이전 값을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-141">If you enter the block more than once during the procedure, each block variable retains its previous value.</span></span> <span data-ttu-id="98bab-142">이러한 경우 예기치 않은 결과 방지 하려면 블록의 시작 부분에 블록 변수를 초기화 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-142">To avoid unexpected results in such a case, it is wise to initialize block variables at the beginning of the block.</span></span>  
  
### <a name="procedure-scope"></a><span data-ttu-id="98bab-143">프로시저 범위</span><span class="sxs-lookup"><span data-stu-id="98bab-143">Procedure Scope</span></span>  
 <span data-ttu-id="98bab-144">프로시저 내에서 선언 된 요소를 해당 프로시저 밖에 서 사용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="98bab-144">An element declared within a procedure is not available outside that procedure.</span></span> <span data-ttu-id="98bab-145">선언을 포함 하는 프로시저에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-145">Only the procedure that contains the declaration can use it.</span></span> <span data-ttu-id="98bab-146">이 수준에서 변수는 라고도 *지역 변수*합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-146">Variables at this level are also known as *local variables*.</span></span> <span data-ttu-id="98bab-147">사용 하 여 선언 된 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md), 하거나 사용 하지 않고는 [정적](../../../../visual-basic/language-reference/modifiers/static.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-147">You declare them with the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), with or without the [Static](../../../../visual-basic/language-reference/modifiers/static.md) keyword.</span></span>  
  
 <span data-ttu-id="98bab-148">프로시저와 블록 범위 밀접 한 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-148">Procedure and block scope are closely related.</span></span> <span data-ttu-id="98bab-149">해당 절차 내에서 모든 블록 외부에 있으면 서 프로시저 내의 변수를 선언 하는 경우에 변수의 블록 범위를 블록 전체 프로시저 인 것으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-149">If you declare a variable inside a procedure but outside any block within that procedure, you can think of the variable as having block scope, where the block is the entire procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98bab-150">모든 로컬 요소는 경우에 `Static` 변수는 표시 된 프로시저 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-150">All local elements, even if they are `Static` variables, are private to the procedure in which they appear.</span></span> <span data-ttu-id="98bab-151">사용 하는 모든 요소를 선언할 수 없습니다는 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 프로시저 내에서 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-151">You cannot declare any element using the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword within a procedure.</span></span>  
  
### <a name="module-scope"></a><span data-ttu-id="98bab-152">모듈 범위</span><span class="sxs-lookup"><span data-stu-id="98bab-152">Module Scope</span></span>  
 <span data-ttu-id="98bab-153">편의 위해 제공 되는 단일 용어에 대 한 *모듈 수준* 모듈, 클래스 및 구조체에 동일 하 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-153">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="98bab-154">선언 문 블록 또는 프로시저일 속하지 않지만 모듈, 클래스 또는 구조체를 배치 하 여이 수준의 요소를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-154">You can declare elements at this level by placing the declaration statement outside of any procedure or block but within the module, class, or structure.</span></span>  
  
 <span data-ttu-id="98bab-155">모듈 수준에서 선언을 만들 때 선택한 액세스 수준 범위를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-155">When you make a declaration at the module level, the access level you choose determines the scope.</span></span> <span data-ttu-id="98bab-156">모듈, 클래스 또는 구조체를 포함 하는 네임 스페이스 범위를도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-156">The namespace that contains the module, class, or structure also affects the scope.</span></span>  
  
 <span data-ttu-id="98bab-157">있는 선언한 요소 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 액세스 수준으로 다른 모듈의 모든 코드 아니라 해당 모듈의 모든 절차를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-157">Elements for which you declare [Private](../../../../visual-basic/language-reference/modifiers/private.md) access level are available to every procedure in that module, but not to any code in a different module.</span></span> <span data-ttu-id="98bab-158">`Dim` 모듈 수준의 문은 기본적으로 `Private` 액세스 수준 키워드를 사용 하지 않는 경우.</span><span class="sxs-lookup"><span data-stu-id="98bab-158">The `Dim` statement at module level defaults to `Private` if you do not use any access level keywords.</span></span> <span data-ttu-id="98bab-159">그러나 가능 범위 및 액세스 수준을 더욱 명확 하 게 사용 하 여는 `Private` 키워드는 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="98bab-159">However, you can make the scope and access level more obvious by using the `Private` keyword in the `Dim` statement.</span></span>  
  
 <span data-ttu-id="98bab-160">다음 예제에서는 모듈에 정의 된 모든 프로시저 문자열 변수를 참조할 수 있습니다 `strMsg`합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-160">In the following example, all procedures defined in the module can refer to the string variable `strMsg`.</span></span> <span data-ttu-id="98bab-161">두 번째 절차를 호출할 때 문자열 변수의 내용을 표시 `strMsg` 대화 상자에서.</span><span class="sxs-lookup"><span data-stu-id="98bab-161">When the second procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
```  
' Put the following declaration at module level (not in any procedure).  
Private strMsg As String  
' Put the following Sub procedure in the same module.  
Sub initializePrivateVariable()  
    strMsg = "This variable cannot be used outside this module."  
End Sub  
' Put the following Sub procedure in the same module.  
Sub usePrivateVariable()  
    MsgBox(strMsg)  
End Sub  
```  
  
### <a name="namespace-scope"></a><span data-ttu-id="98bab-162">Namespace 범위</span><span class="sxs-lookup"><span data-stu-id="98bab-162">Namespace Scope</span></span>  
 <span data-ttu-id="98bab-163">모듈이 사용 하 여 수준에 있는 요소를 선언 하는 경우는 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 또는 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 요소가 선언 된 네임 스페이스 모든 프로시저를 사용할 수 키워드를 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-163">If you declare an element at module level using the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword, it becomes available to all procedures throughout the namespace in which the element is declared.</span></span> <span data-ttu-id="98bab-164">위의 예제에서는 문자열 변수를 다음과 같이 변경 하면 `strMsg` 선언의 네임 스페이스에 있는 모든 코드에서 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-164">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```  
' Include this declaration at module level (not inside any procedure).  
Public strMsg As String  
```  
  
 <span data-ttu-id="98bab-165">Namespace 범위는 중첩 된 네임 스페이스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-165">Namespace scope includes nested namespaces.</span></span> <span data-ttu-id="98bab-166">네임 스페이스 내에서 사용할 수 있는 요소를 해당 네임 스페이스 내에 중첩 된 모든 네임 스페이스 내에서 사용할 수 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-166">An element available from within a namespace is also available from within any namespace nested inside that namespace.</span></span>  
  
 <span data-ttu-id="98bab-167">프로젝트에 포함 하지 않는 경우 [Namespace 문](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, 프로젝트의 모든 항목은 동일한 네임 스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-167">If your project does not contain any [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, everything in the project is in the same namespace.</span></span> <span data-ttu-id="98bab-168">이 예에서 네임 스페이스 범위 프로젝트 범위로 간주 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-168">In this case, namespace scope can be thought of as project scope.</span></span> <span data-ttu-id="98bab-169">`Public`모듈, 클래스 또는 구조체의 요소는 해당 프로젝트를 참조 하는 모든 프로젝트에 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-169">`Public` elements in a module, class, or structure are also available to any project that references their project.</span></span>  
  
## <a name="choice-of-scope"></a><span data-ttu-id="98bab-170">범위 선택</span><span class="sxs-lookup"><span data-stu-id="98bab-170">Choice of Scope</span></span>  
 <span data-ttu-id="98bab-171">변수를 선언 해야 점만 기억 한다면 다음 사항을 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-171">When you declare a variable, you should keep in mind the following points when choosing its scope.</span></span>  
  
### <a name="advantages-of-local-variables"></a><span data-ttu-id="98bab-172">지역 변수의 장점</span><span class="sxs-lookup"><span data-stu-id="98bab-172">Advantages of Local Variables</span></span>  
 <span data-ttu-id="98bab-173">지역 변수는 다음과 같은 이유로 임시 계산에 대 한 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-173">Local variables are a good choice for any kind of temporary calculation, for the following reasons:</span></span>  
  
-   <span data-ttu-id="98bab-174">**이름 충돌 방지 합니다.**</span><span class="sxs-lookup"><span data-stu-id="98bab-174">**Name Conflict Avoidance.**</span></span> <span data-ttu-id="98bab-175">지역 변수 이름 충돌을 쉽게 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-175">Local variable names are not susceptible to conflict.</span></span> <span data-ttu-id="98bab-176">예를 들어 라는 변수를 여러 프로시저를 만들 수 있습니다 `intTemp`합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-176">For example, you can create several different procedures containing a variable called `intTemp`.</span></span> <span data-ttu-id="98bab-177">각 `intTemp` 지역 변수로 선언 된 각 프로시저 자체 버전에만 인식의 `intTemp`합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-177">As long as each `intTemp` is declared as a local variable, each procedure recognizes only its own version of `intTemp`.</span></span> <span data-ttu-id="98bab-178">프로시저를 하나는 로컬의 값을 변경할 수 `intTemp` 영향을 주지 않고 `intTemp` 다른 프로시저에서 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-178">Any one procedure can alter the value in its local `intTemp` without affecting `intTemp` variables in other procedures.</span></span>  
  
-   <span data-ttu-id="98bab-179">**메모리 소비 합니다.**</span><span class="sxs-lookup"><span data-stu-id="98bab-179">**Memory Consumption.**</span></span> <span data-ttu-id="98bab-180">지역 변수는 해당 프로시저가 실행 되는 동안에 메모리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-180">Local variables consume memory only while their procedure is running.</span></span> <span data-ttu-id="98bab-181">프로시저가 호출 코드에 반환 되는 메모리 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-181">Their memory is released when the procedure returns to the calling code.</span></span> <span data-ttu-id="98bab-182">이와 반대로 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) 및 [정적](../../../../visual-basic/language-reference/modifiers/static.md) 변수 응용 프로그램의 실행이 중지 될 때까지 메모리 리소스를 사용, 필요한 경우에 해 서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-182">By contrast, [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) and [Static](../../../../visual-basic/language-reference/modifiers/static.md) variables consume memory resources until your application stops running, so use them only when necessary.</span></span> <span data-ttu-id="98bab-183">*인스턴스 변수* 는 지역 변수를 보다 효율적이 지 않지만 보다 효율적 해당 인스턴스는 계속 존재 하는 동안 메모리 소모 `Shared` 또는 `Static` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-183">*Instance variables* consume memory while their instance continues to exist, which makes them less efficient than local variables, but potentially more efficient than `Shared` or `Static` variables.</span></span>  
  
### <a name="minimizing-scope"></a><span data-ttu-id="98bab-184">범위를 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-184">Minimizing Scope</span></span>  
 <span data-ttu-id="98bab-185">일반적으로 모든 변수 또는 상수를 선언할 때 것이 바람직한 프로그래밍 습관 범위를 가능한 한 좁게 (블록 범위는 가장 좁은 임).</span><span class="sxs-lookup"><span data-stu-id="98bab-185">In general, when declaring any variable or constant, it is good programming practice to make the scope as narrow as possible (block scope is the narrowest).</span></span> <span data-ttu-id="98bab-186">메모리를 유지할 수 있게 하 고 잘못 된 변수를 잘못 참조할 코드의 가능성을 최소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-186">This helps conserve memory and minimizes the chances of your code erroneously referring to the wrong variable.</span></span> <span data-ttu-id="98bab-187">변수를 선언 해야 마찬가지로, [정적](../../../../visual-basic/language-reference/modifiers/static.md) 경우에 프로시저 호출 하는 동안 값을 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98bab-187">Similarly, you should declare a variable to be [Static](../../../../visual-basic/language-reference/modifiers/static.md) only when it is necessary to preserve its value between procedure calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98bab-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98bab-188">See Also</span></span>  
 [<span data-ttu-id="98bab-189">선언 요소의 특징</span><span class="sxs-lookup"><span data-stu-id="98bab-189">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="98bab-190">방법: 변수의 범위 제어</span><span class="sxs-lookup"><span data-stu-id="98bab-190">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [<span data-ttu-id="98bab-191">Visual Basic의 수명</span><span class="sxs-lookup"><span data-stu-id="98bab-191">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [<span data-ttu-id="98bab-192">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="98bab-192">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="98bab-193">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="98bab-193">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="98bab-194">변수 선언</span><span class="sxs-lookup"><span data-stu-id="98bab-194">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
