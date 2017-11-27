---
title: "Namespace 문"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Namespace
helpviewer_keywords:
- namespaces [Visual Basic], root
- Namespace statement [Visual Basic]
- namespaces [Visual Basic], nested
- declaring namespaces [Visual Basic], syntax
- namespaces [Visual Basic], declaring
- root namespaces
- declarations [Visual Basic], namespaces
ms.assetid: a31fbd95-9ace-4c3d-bbb1-51222a2272b2
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9863286a8eda2559ab678c77a81cc7d6063c3e3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-statement"></a><span data-ttu-id="3a09d-102">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="3a09d-102">Namespace Statement</span></span>
<span data-ttu-id="3a09d-103">네임 스페이스의 이름을 선언 하 고 해당 네임 스페이스에서 컴파일되도록 선언 뒤에 오는 소스 코드.</span><span class="sxs-lookup"><span data-stu-id="3a09d-103">Declares the name of a namespace and causes the source code that follows the declaration to be compiled within that namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a09d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3a09d-104">Syntax</span></span>  
  
```  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## <a name="parts"></a><span data-ttu-id="3a09d-105">요소</span><span class="sxs-lookup"><span data-stu-id="3a09d-105">Parts</span></span>  
 <span data-ttu-id="3a09d-106">Global</span><span class="sxs-lookup"><span data-stu-id="3a09d-106">Global</span></span>  
 <span data-ttu-id="3a09d-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-107">Optional.</span></span> <span data-ttu-id="3a09d-108">프로젝트의 루트 네임 스페이스에서 네임 스페이스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-108">Allows you to define a namespace out of the root namespace of your project.</span></span> <span data-ttu-id="3a09d-109">참조 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-109">See [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
 `name`  
 <span data-ttu-id="3a09d-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="3a09d-110">Required.</span></span> <span data-ttu-id="3a09d-111">네임 스페이스를 식별 하는 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-111">A unique name that identifies the namespace.</span></span> <span data-ttu-id="3a09d-112">유효한 Visual Basic 식별자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-112">Must be a valid Visual Basic identifier.</span></span> <span data-ttu-id="3a09d-113">자세한 내용은 참조 [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-113">For more information, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
 `componenttypes`  
 <span data-ttu-id="3a09d-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-114">Optional.</span></span> <span data-ttu-id="3a09d-115">네임 스페이스를 구성 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-115">Elements that make up the namespace.</span></span> <span data-ttu-id="3a09d-116">이러한 포함 되지만 열거형, 구조체, 인터페이스, 클래스, 모듈, 대리자 및 다른 네임 스페이스에 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-116">These include, but are not limited to, enumerations, structures, interfaces, classes, modules, delegates, and other namespaces.</span></span>  
  
 `End Namespace`  
 <span data-ttu-id="3a09d-117">종료는 `Namespace` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-117">Terminates a `Namespace` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a09d-118">설명</span><span class="sxs-lookup"><span data-stu-id="3a09d-118">Remarks</span></span>  
 <span data-ttu-id="3a09d-119">네임 스페이스는 조직 시스템으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-119">Namespaces are used as an organizational system.</span></span> <span data-ttu-id="3a09d-120">분류 및 다른 프로그램 및 응용 프로그램에 노출 되는 프로그래밍 요소를 표시 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-120">They provide a way to classify and present programming elements that are exposed to other programs and applications.</span></span> <span data-ttu-id="3a09d-121">네임 스페이스 하지 않습니다는 *형식* 의미는 클래스 또는 구조체에서-네임 스페이스의 데이터 형식을 갖도록 프로그래밍 요소를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-121">Note that a namespace is not a *type* in the sense that a class or structure is—you cannot declare a programming element to have the data type of a namespace.</span></span>  
  
 <span data-ttu-id="3a09d-122">다음에 선언 된 모든 프로그래밍 요소는 `Namespace` 문을 해당 네임 스페이스에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-122">All programming elements declared after a `Namespace` statement belong to that namespace.</span></span> <span data-ttu-id="3a09d-123">Visual Basic를 컴파일하여 요소 마지막 선언 된 네임 스페이스 중 하나에 도달할 때까지 계속는 `End Namespace` 문 또는 다른 `Namespace` 문.</span><span class="sxs-lookup"><span data-stu-id="3a09d-123">Visual Basic continues to compile elements into the last declared namespace until it encounters either an `End Namespace` statement or another `Namespace` statement.</span></span>  
  
 <span data-ttu-id="3a09d-124">네임 스페이스는 이미 정의 된 경우, 프로젝트 외부도 프로그래밍 요소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-124">If a namespace is already defined, even outside your project, you can add programming elements to it.</span></span> <span data-ttu-id="3a09d-125">이 위해 사용 하는 `Namespace` 문을 해당 네임 스페이스에 요소를 컴파일하는 데 Visual basic입니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-125">To do this, you use a `Namespace` statement to direct Visual Basic to compile elements into that namespace.</span></span>  
  
 <span data-ttu-id="3a09d-126">사용할 수는 `Namespace` 파일이 나 네임 스페이스 수준 에서만 문입니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-126">You can use a `Namespace` statement only at the file or namespace level.</span></span> <span data-ttu-id="3a09d-127">즉,는 *선언 컨텍스트* 네임 스페이스는 소스 파일 또는 다른 네임 스페이스 이어야 하며 클래스, 구조체, 모듈, 인터페이스 또는 프로시저 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-127">This means the *declaration context* for a namespace must be a source file or another namespace, and cannot be a class, structure, module, interface, or procedure.</span></span> <span data-ttu-id="3a09d-128">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a09d-128">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="3a09d-129">내에서 다른 한 네임 스페이스를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-129">You can declare one namespace within another.</span></span> <span data-ttu-id="3a09d-130">를 선언할 수 있지만 기억 하는 다른 코드에서 가장 안쪽의 네임 스페이스에서 선언 된 요소에 액세스 하는 경우 사용 해야 중첩 계층의 모든 네임 스페이스 이름을 포함 하는 한정 문자열의 중첩 수준에는 엄격한 제한은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-130">There is no strict limit to the levels of nesting you can declare, but remember that when other code accesses the elements declared in the innermost namespace, it must use a qualification string that contains all the namespace names in the nesting hierarchy.</span></span>  
  
## <a name="access-level"></a><span data-ttu-id="3a09d-131">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="3a09d-131">Access Level</span></span>  
 <span data-ttu-id="3a09d-132">네임 스페이스는 것 처럼 처리 되는 `Public` 액세스 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-132">Namespaces are treated as if they have a `Public` access level.</span></span> <span data-ttu-id="3a09d-133">네임 스페이스는 같은 프로젝트의 코드, 프로젝트를 참조 하는 다른 프로젝트 및 프로젝트에서 빌드된 어셈블리에서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-133">A namespace can be accessed from code anywhere in the same project, from other projects that reference the project, and from any assembly built from the project.</span></span>  
  
 <span data-ttu-id="3a09d-134">네임 스페이스에 있지만 다른 요소에 포함 되지 않은 의미 하는 네임 스페이스 수준에서 선언 된 프로그래밍 요소 점이 `Public` 또는 `Friend` 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-134">Programming elements declared at namespace level, meaning in a namespace but not inside any other element, can have `Public` or `Friend` access.</span></span> <span data-ttu-id="3a09d-135">지정 하지 않으면 이러한 액세스 수준을 요소가 사용 하 여 `Friend` 기본적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-135">If unspecified, the access level of such an element uses `Friend` by default.</span></span> <span data-ttu-id="3a09d-136">클래스, 구조체, 모듈, 인터페이스, 열거형 및 대리자를 포함 하는 요소 네임 스페이스 수준에서 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-136">Elements you can declare at namespace level include classes, structures, modules, interfaces, enumerations, and delegates.</span></span> <span data-ttu-id="3a09d-137">자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a09d-137">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
## <a name="root-namespace"></a><span data-ttu-id="3a09d-138">루트 Namespace</span><span class="sxs-lookup"><span data-stu-id="3a09d-138">Root Namespace</span></span>  
 <span data-ttu-id="3a09d-139">프로젝트에서 모든 네임 스페이스 이름을 기반으로 한 *루트 네임 스페이스*합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-139">All namespace names in your project are based on a *root namespace*.</span></span> <span data-ttu-id="3a09d-140">Visual Studio는 프로젝트 이름을 프로젝트의 모든 코드에 대한 기본 루트 네임스페이스로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-140">Visual Studio assigns your project name as the default root namespace for all code in your project.</span></span> <span data-ttu-id="3a09d-141">예를 들어 프로젝트 이름이 `Payroll`이면 해당 프로그래밍 요소는 해당 네임스페이스 `Payroll`에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-141">For example, if your project is named `Payroll`, its programming elements belong to namespace `Payroll`.</span></span> <span data-ttu-id="3a09d-142">선언 하는 경우 `Namespace funding`, 해당 네임 스페이스의 전체 이름은 `Payroll.funding`합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-142">If you declare `Namespace funding`, the full name of that namespace is `Payroll.funding`.</span></span>  
  
 <span data-ttu-id="3a09d-143">기존 네임 스페이스를 지정 하려는 경우는 `Namespace` 문, 예: 제네릭 목록 클래스 예제에서 루트 네임 스페이스는 null 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-143">If you want to specify an existing namespace in a `Namespace` statement, such as in the generic list class example, you can set your root namespace to a null value.</span></span> <span data-ttu-id="3a09d-144">이 작업을 수행 하려면 **프로젝트 속성** 에서 **프로젝트** 메뉴와 선택을 취소 합니다는 **루트 네임 스페이스** 항목 상자가 비어 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-144">To do this, click **Project Properties** from the **Project** menu and then clear the **Root namespace** entry so that the box is empty.</span></span> <span data-ttu-id="3a09d-145">이 제네릭 목록 클래스 예제에서 수행 하지 않은 경우 Visual Basic 컴파일러가 수행 `System.Collections.Generic` 프로젝트 내에서 새 네임 스페이스로 `Payroll`를의 전체 이름으로 `Payroll.System.Collections.Generic`합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-145">If you did not do this in the generic list class example, the Visual Basic compiler would take `System.Collections.Generic` as a new namespace within project `Payroll`, with the full name of `Payroll.System.Collections.Generic`.</span></span>  
  
 <span data-ttu-id="3a09d-146">사용할 수 있습니다는 `Global` 프로젝트 외부에 정의 된 네임 스페이스의 요소를 참조 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-146">Alternatively, you can use the `Global` keyword to refer to elements of namespaces defined outside your project.</span></span> <span data-ttu-id="3a09d-147">이렇게 하면 프로젝트 이름을 루트 네임 스페이스도 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-147">Doing so lets you retain your project name as the root namespace.</span></span> <span data-ttu-id="3a09d-148">이렇게 하면 실수로 기존 네임 스페이스와 함께 프로그래밍 요소를 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-148">This reduces the chance of unintentionally merging your programming elements together with those of existing namespaces.</span></span> <span data-ttu-id="3a09d-149">자세한 내용은에서 "전역 키워드에 정규화 된 이름" 섹션을 참조 하십시오. [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-149">For more information, see the "Global Keyword in Fully Qualified Names" section in [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
 <span data-ttu-id="3a09d-150">`Global` 키워드 Namespace 문에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-150">The `Global` keyword can also be used in a Namespace statement.</span></span> <span data-ttu-id="3a09d-151">이렇게 하면 프로젝트의 루트 네임스페이스에서 네임스페이스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-151">This lets you define a namespace out of the root namespace of your project.</span></span> <span data-ttu-id="3a09d-152">자세한 내용은의 "Namespace 문을에서 글로벌 키워드" 섹션을 참조 하십시오. [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-152">For more information, see the "Global Keyword in Namespace Statements" section in [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
 <span data-ttu-id="3a09d-153">**문제를 해결 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3a09d-153">**Troubleshooting.**</span></span> <span data-ttu-id="3a09d-154">예기치 않은 네임 스페이스 이름 연결할 루트 네임 스페이스 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-154">The root namespace can lead to unexpected concatenations of namespace names.</span></span> <span data-ttu-id="3a09d-155">프로젝트 외부에 정의 된 네임 스페이스 참조를 만드는 경우 Visual Basic 컴파일러는 해당 루트 네임 스페이스에 중첩 된 네임 스페이스도 해석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-155">If you make reference to namespaces defined outside your project, the Visual Basic compiler can construe them as nested namespaces in the root namespace.</span></span> <span data-ttu-id="3a09d-156">이 경우 컴파일러는 외부 네임 스페이스에 이미 정의 되어 있는 형식이 인식 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-156">In such a case, the compiler does not recognize any types that have been already defined in the external namespaces.</span></span> <span data-ttu-id="3a09d-157">이 방지 하려면 루트 네임 스페이스 "루트 Namespace"에 설명 된 대로 null 값으로 설정 하거나 사용 된 `Global` 요소 외부 네임 스페이스에 액세스 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-157">To avoid this, either set your root namespace to a null value as described in "Root Namespace," or use the `Global` keyword to access elements of external namespaces.</span></span>  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="3a09d-158">특성 및 한정자</span><span class="sxs-lookup"><span data-stu-id="3a09d-158">Attributes and Modifiers</span></span>  
 <span data-ttu-id="3a09d-159">네임 스페이스에 특성을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-159">You cannot apply attributes to a namespace.</span></span> <span data-ttu-id="3a09d-160">특성은 네임 스페이스와 같은 소스 분류자에 의미가 없습니다 어셈블리의 메타 데이터에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-160">An attribute contributes information to the assembly's metadata, which is not meaningful for source classifiers such as namespaces.</span></span>  
  
 <span data-ttu-id="3a09d-161">네임 스페이스에 대 한 액세스 또는 프로시저 한정자 또는 다른 한정자를 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-161">You cannot apply any access or procedure modifiers, or any other modifiers, to a namespace.</span></span> <span data-ttu-id="3a09d-162">형식이 없기 때문에 이러한 한정자는 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-162">Because it is not a type, these modifiers are not meaningful.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a09d-163">예제</span><span class="sxs-lookup"><span data-stu-id="3a09d-163">Example</span></span>  
 <span data-ttu-id="3a09d-164">다음 예제에서는 다른 중첩 된 두 개의 네임 스페이스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-164">The following example declares two namespaces, one nested in the other.</span></span>  
  
 [!code-vb[VbVbalrStatements#43](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="3a09d-165">예제</span><span class="sxs-lookup"><span data-stu-id="3a09d-165">Example</span></span>  
 <span data-ttu-id="3a09d-166">다음 예제에서는 한 줄에 여러 개의 중첩 된 네임 스페이스를 선언 하 고 앞의 예와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-166">The following example declares multiple nested namespaces on a single line, and it is equivalent to the previous example.</span></span>  
  
 [!code-vb[VbVbalrStatements#41](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="3a09d-167">예제</span><span class="sxs-lookup"><span data-stu-id="3a09d-167">Example</span></span>  
 <span data-ttu-id="3a09d-168">다음 예제에서는 앞의 예제에 정의 된 클래스에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-168">The following example accesses the class defined in the previous examples.</span></span>  
  
 [!code-vb[VbVbalrStatements#42](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="3a09d-169">예제</span><span class="sxs-lookup"><span data-stu-id="3a09d-169">Example</span></span>  
 <span data-ttu-id="3a09d-170">다음 예제에서는 새 제네릭 목록 클래스의 기본 구조를 정의 하 고에 추가 된 <xref:System.Collections.Generic?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3a09d-170">The following example defines the skeleton of a new generic list class and adds it to the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a09d-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a09d-171">See Also</span></span>  
 [<span data-ttu-id="3a09d-172">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="3a09d-172">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="3a09d-173">선언 요소 이름</span><span class="sxs-lookup"><span data-stu-id="3a09d-173">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="3a09d-174">Visual Basic의 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="3a09d-174">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
