---
title: "형식 목록(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 35e72414b236615dc230b654ccfeed290841fb31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="8909d-102">형식 목록(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8909d-102">Type List (Visual Basic)</span></span>
<span data-ttu-id="8909d-103">지정 된 *형식 매개 변수* 에 대 한는 *제네릭* 프로그래밍 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="8909d-104">매개 변수가 여러 개이면 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="8909d-105">다음은 한 형식 매개 변수에 대 한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-105">Following is the syntax for one type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8909d-106">구문</span><span class="sxs-lookup"><span data-stu-id="8909d-106">Syntax</span></span>  
  
```  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## <a name="parts"></a><span data-ttu-id="8909d-107">요소</span><span class="sxs-lookup"><span data-stu-id="8909d-107">Parts</span></span>  
  
|<span data-ttu-id="8909d-108">용어</span><span class="sxs-lookup"><span data-stu-id="8909d-108">Term</span></span>|<span data-ttu-id="8909d-109">정의</span><span class="sxs-lookup"><span data-stu-id="8909d-109">Definition</span></span>|  
|---|---|  
|`genericmodifier`|<span data-ttu-id="8909d-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-110">Optional.</span></span> <span data-ttu-id="8909d-111">제네릭 인터페이스 및 대리자 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="8909d-112">형식을 선언할 수 있습니다는 공변 (covariant)를 사용 하 여는 [아웃](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) 키워드 또는 사용 하 여 반공 분산의 [에](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-112">You can declare a type covariant by using the [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="8909d-113">[공변성(Covariance) 및 반공변성(Contravariance)](../../programming-guide/concepts/covariance-contravariance/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8909d-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|  
|`typename`|<span data-ttu-id="8909d-114">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8909d-114">Required.</span></span> <span data-ttu-id="8909d-115">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-115">Name of the type parameter.</span></span> <span data-ttu-id="8909d-116">해당 형식 인수가 제공 하는 정의 된 형식으로 대체 되어야 하는 자리 표시자입니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|  
|`constraintlist`|<span data-ttu-id="8909d-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-117">Optional.</span></span> <span data-ttu-id="8909d-118">에 제공할 수 있는 데이터 형식을 제한 하는 요구 사항 목록은 `typename`합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="8909d-119">여러 제약 조건이 있는 경우 중괄호로 묶습니다 (`{ }`) 하 고 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="8909d-120">사용 제약 조건 목록을 정의 해야는 [으로](../../../visual-basic/language-reference/statements/as-clause.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-120">You must introduce the constraint list with the [As](../../../visual-basic/language-reference/statements/as-clause.md) keyword.</span></span> <span data-ttu-id="8909d-121">사용 하면 `As` 목록 맨 앞에 한 번만 합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-121">You use `As` only once, at the beginning of the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8909d-122">설명</span><span class="sxs-lookup"><span data-stu-id="8909d-122">Remarks</span></span>  
 <span data-ttu-id="8909d-123">모든 제네릭 프로그래밍 요소는 하나 이상의 형식 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="8909d-124">형식 매개 변수는 특정 형식에 대 한 자리 표시자 (한 *생성 된 요소*) 클라이언트 코드는 제네릭 형식의 인스턴스를 만들 때을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="8909d-125">제네릭 클래스를 정의 구조체, 인터페이스, 프로시저 하거나 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>  
  
 <span data-ttu-id="8909d-126">제네릭 형식 정의 하는 시점에 대 한 자세한 내용은 참조 하십시오. [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="8909d-127">형식 매개 변수 이름에 대 한 자세한 내용은 참조 하십시오. [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-127">For more information on type parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="8909d-128">규칙</span><span class="sxs-lookup"><span data-stu-id="8909d-128">Rules</span></span>  
  
-   <span data-ttu-id="8909d-129">**괄호입니다.**</span><span class="sxs-lookup"><span data-stu-id="8909d-129">**Parentheses.**</span></span> <span data-ttu-id="8909d-130">형식 매개 변수 목록을 제공 하 고 괄호로 묶어야 사용 목록을 정의 해야 하는 경우는 [의](../../../visual-basic/language-reference/statements/of-clause.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](../../../visual-basic/language-reference/statements/of-clause.md) keyword.</span></span> <span data-ttu-id="8909d-131">사용 하면 `Of` 목록 맨 앞에 한 번만 합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-131">You use `Of` only once, at the beginning of the list.</span></span>  
  
-   <span data-ttu-id="8909d-132">**제약 조건입니다.**</span><span class="sxs-lookup"><span data-stu-id="8909d-132">**Constraints.**</span></span> <span data-ttu-id="8909d-133">목록이 *제약 조건을* 형식에 매개 변수 수는 다음 항목이 포함 원하는 방식:</span><span class="sxs-lookup"><span data-stu-id="8909d-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>  
  
    -   <span data-ttu-id="8909d-134">원하는 수의 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-134">Any number of interfaces.</span></span> <span data-ttu-id="8909d-135">제공 된 유형을이 목록의 모든 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-135">The supplied type must implement every interface in this list.</span></span>  
  
    -   <span data-ttu-id="8909d-136">최대 하나의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-136">At most one class.</span></span> <span data-ttu-id="8909d-137">제공 된 형식이 해당 클래스에서 상속 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-137">The supplied type must inherit from that class.</span></span>  
  
    -   <span data-ttu-id="8909d-138">`New` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-138">The `New` keyword.</span></span> <span data-ttu-id="8909d-139">제공 된 형식이 제네릭 형식에 액세스할 수 있는 매개 변수가 없는 생성자를 노출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="8909d-140">하나 이상의 인터페이스에서 형식 매개 변수를 제한 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="8909d-141">인터페이스를 구현 하는 형식 생성자를 반드시 노출 하지 않습니다 및 생성자의 액세스 수준에 따라 제네릭 형식 내에서 코드 못할에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>  
  
    -   <span data-ttu-id="8909d-142">중 하나는 `Class` 키워드 또는 `Structure` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="8909d-143">`Class` 키워드에 전달 된 형식 인수가 참조 형식, 문자열, 배열 또는 대리자, 예를 들어 이어야 또는 클래스에서 만든 개체가 제네릭 형식 매개 변수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="8909d-144">`Structure` 키워드는 구조체, 열거형 또는 기본 데이터의 형식 예를 들어는 제네릭 형식 매개 변수 전달 된 형식 인수가 값 형식이 록 요구할를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="8909d-145">둘 모두를 포함할 수 없으며 `Class` 및 `Structure` 같은 `constraintlist`합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>  
  
     <span data-ttu-id="8909d-146">제공 된 형식에 포함할 모든 요구 사항을 충족 해야 `constraintlist`합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>  
  
     <span data-ttu-id="8909d-147">각 형식 매개 변수에 대 한 제약 조건을 서로 다른 형식 매개 변수에서 제약 조건의 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="8909d-148">동작</span><span class="sxs-lookup"><span data-stu-id="8909d-148">Behavior</span></span>  
  
-   <span data-ttu-id="8909d-149">**컴파일 타임 대체 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8909d-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="8909d-150">제네릭 프로그래밍 요소에서 생성된 된 형식의 만들 때 각 형식 매개 변수에 대해 정의 된 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="8909d-151">Visual Basic 컴파일러의 모든 위치에 대해 제공 된 해당 형식을 대체 `typename` 를 제네릭 요소 내에서.</span><span class="sxs-lookup"><span data-stu-id="8909d-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>  
  
-   <span data-ttu-id="8909d-152">**제약 조건 없음입니다.**</span><span class="sxs-lookup"><span data-stu-id="8909d-152">**Absence of Constraints.**</span></span> <span data-ttu-id="8909d-153">형식 매개 변수에 대 한 제약 조건을 지정 하지 않으면 경우에 코드는 작업 및 멤버에서 지 원하는로 제한 됩니다는 [Object 데이터 형식](../../../visual-basic/language-reference/data-types/object-data-type.md) 해당 형식 매개 변수에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) for that type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8909d-154">예제</span><span class="sxs-lookup"><span data-stu-id="8909d-154">Example</span></span>  
 <span data-ttu-id="8909d-155">다음 예제에서는 새 항목을 사전에 추가 하는 기본 함수를 포함 하는 제네릭 사전 클래스의 기본 정의 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>  
  
 [!code-vb[VbVbalrStatements#3](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="8909d-156">예제</span><span class="sxs-lookup"><span data-stu-id="8909d-156">Example</span></span>  
 <span data-ttu-id="8909d-157">때문에 `dictionary` 은 일반, 사용 하는 코드에서 만들 수는 다양 한 개체를 각각 다른 데이터 형식에 적용 되지만 동일한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="8909d-158">다음 예제에서는 만드는 코드의 줄을 `dictionary` 개체 `String` 항목 및 `Integer` 키입니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>  
  
 [!code-vb[VbVbalrStatements#4](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="8909d-159">예제</span><span class="sxs-lookup"><span data-stu-id="8909d-159">Example</span></span>  
 <span data-ttu-id="8909d-160">다음 예제에서는 앞의 예제에서 생성 된 해당 하는 기본 정의 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8909d-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#5](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8909d-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8909d-161">See Also</span></span>  
 [<span data-ttu-id="8909d-162">Of</span><span class="sxs-lookup"><span data-stu-id="8909d-162">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
 [<span data-ttu-id="8909d-163">New 연산자</span><span class="sxs-lookup"><span data-stu-id="8909d-163">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="8909d-164">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="8909d-164">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="8909d-165">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8909d-165">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="8909d-166">Function 문</span><span class="sxs-lookup"><span data-stu-id="8909d-166">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="8909d-167">Structure 문</span><span class="sxs-lookup"><span data-stu-id="8909d-167">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="8909d-168">Sub 문</span><span class="sxs-lookup"><span data-stu-id="8909d-168">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="8909d-169">방법: 제네릭 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="8909d-169">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="8909d-170">공 분산 및 반공 분산</span><span class="sxs-lookup"><span data-stu-id="8909d-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [<span data-ttu-id="8909d-171">In</span><span class="sxs-lookup"><span data-stu-id="8909d-171">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [<span data-ttu-id="8909d-172">Out</span><span class="sxs-lookup"><span data-stu-id="8909d-172">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
