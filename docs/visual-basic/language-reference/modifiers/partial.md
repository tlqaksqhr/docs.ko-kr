---
title: Partial(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Partial
- partial
helpviewer_keywords:
- structures [Visual Basic], partial
- classes [Visual Basic]
- partial, types [Visual Basic]
- partial, structures
- partial, classes [Visual Basic]
- classes [Visual Basic], partial
- Partial keyword [Visual Basic]
- type promotion
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
ms.openlocfilehash: c94c3bf1a1e3e4c724f90690f52e97e8216cb9a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604616"
---
# <a name="partial-visual-basic"></a><span data-ttu-id="7712e-102">Partial(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7712e-102">Partial (Visual Basic)</span></span>
<span data-ttu-id="7712e-103">형식 선언이 해당 형식에 대한 부분 정의임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-103">Indicates that a type declaration is a partial definition of the type.</span></span>  
  
 <span data-ttu-id="7712e-104">`Partial` 키워드를 사용하여 형식 정의를 다수의 선언으로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-104">You can divide the definition of a type among several declarations by using the `Partial` keyword.</span></span> <span data-ttu-id="7712e-105">원하는 만큼 다양한 소스 파일에서 원하는 만큼 partial 선언을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-105">You can use as many partial declarations as you want, in as many different source files as you want.</span></span> <span data-ttu-id="7712e-106">그러나 모든 선언이 동일한 어셈블리와 동일한 네임스페이스에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-106">However, all the declarations must be in the same assembly and the same namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7712e-107">Visual Basic에서는 *부분 메서드*는 속성은 일반적으로 partial 클래스에서 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-107">Visual Basic supports *partial methods*, which are typically implemented in partial classes.</span></span> <span data-ttu-id="7712e-108">자세한 내용은 참조 [부분 메서드](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) 및 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-108">For more information, see [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) and [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7712e-109">구문</span><span class="sxs-lookup"><span data-stu-id="7712e-109">Syntax</span></span>  
  
```  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## <a name="parts"></a><span data-ttu-id="7712e-110">요소</span><span class="sxs-lookup"><span data-stu-id="7712e-110">Parts</span></span>  
  
|<span data-ttu-id="7712e-111">용어</span><span class="sxs-lookup"><span data-stu-id="7712e-111">Term</span></span>|<span data-ttu-id="7712e-112">정의</span><span class="sxs-lookup"><span data-stu-id="7712e-112">Definition</span></span>|  
|---|---|  
|`attrlist`|<span data-ttu-id="7712e-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-113">Optional.</span></span> <span data-ttu-id="7712e-114">이 형식에 적용되는 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-114">List of attributes that apply to this type.</span></span> <span data-ttu-id="7712e-115">묶어야는 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호에서 (`< >`).</span><span class="sxs-lookup"><span data-stu-id="7712e-115">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets (`< >`).</span></span>|  
|`accessmodifier`|<span data-ttu-id="7712e-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-116">Optional.</span></span> <span data-ttu-id="7712e-117">이 형식에 액세스할 수 있는 코드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-117">Specifies what code can access this type.</span></span> <span data-ttu-id="7712e-118">참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-118">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`Shadows`|<span data-ttu-id="7712e-119">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-119">Optional.</span></span> <span data-ttu-id="7712e-120">참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>|  
|`MustInherit`|<span data-ttu-id="7712e-121">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-121">Optional.</span></span> <span data-ttu-id="7712e-122">참조 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-122">See [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).</span></span>|  
|`NotInheritable`|<span data-ttu-id="7712e-123">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-123">Optional.</span></span> <span data-ttu-id="7712e-124">참조 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-124">See [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).</span></span>|  
|`name`|<span data-ttu-id="7712e-125">필수.</span><span class="sxs-lookup"><span data-stu-id="7712e-125">Required.</span></span> <span data-ttu-id="7712e-126">이 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-126">Name of this type.</span></span> <span data-ttu-id="7712e-127">동일한 형식의 다른 모든 partial 선언에 정의된 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-127">Must match the name defined in all other partial declarations of the same type.</span></span>|  
|`Of`|<span data-ttu-id="7712e-128">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-128">Optional.</span></span> <span data-ttu-id="7712e-129">제네릭 형식임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-129">Specifies that this is a generic type.</span></span> <span data-ttu-id="7712e-130">참조 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-130">See [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>|  
|`typelist`|<span data-ttu-id="7712e-131">사용 하는 경우 필수 [의](../../../visual-basic/language-reference/statements/of-clause.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-131">Required if you use [Of](../../../visual-basic/language-reference/statements/of-clause.md).</span></span> <span data-ttu-id="7712e-132">참조 [목록을 입력](../../../visual-basic/language-reference/statements/type-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-132">See [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>|  
|`Inherits`|<span data-ttu-id="7712e-133">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-133">Optional.</span></span> <span data-ttu-id="7712e-134">참조 [Inherits 문](../../../visual-basic/language-reference/statements/inherits-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-134">See [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md).</span></span>|  
|`classname`|<span data-ttu-id="7712e-135">`Inherits`를 사용하는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-135">Required if you use `Inherits`.</span></span> <span data-ttu-id="7712e-136">이 클래스가 파생되는 출처인 인터페이스 또는 클래스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-136">The name of the class or interface from which this class derives.</span></span>|  
|`Implements`|<span data-ttu-id="7712e-137">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-137">Optional.</span></span> <span data-ttu-id="7712e-138">참조 [문을 구현](../../../visual-basic/language-reference/statements/implements-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-138">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>|  
|`interfacenames`|<span data-ttu-id="7712e-139">`Implements`를 사용하는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-139">Required if you use `Implements`.</span></span> <span data-ttu-id="7712e-140">이 형식이 구현하는 인터페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-140">The names of the interfaces this type implements.</span></span>|  
|`variabledeclarations`|<span data-ttu-id="7712e-141">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-141">Optional.</span></span> <span data-ttu-id="7712e-142">형식에 대한 추가 변수 및 이벤트를 선언하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-142">Statements which declare additional variables and events for the type.</span></span>|  
|`proceduredeclarations`|<span data-ttu-id="7712e-143">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-143">Optional.</span></span> <span data-ttu-id="7712e-144">형식에 대한 추가 프로시저를 선언하고 정의하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-144">Statements which declare and define additional procedures for the type.</span></span>|  
|<span data-ttu-id="7712e-145">`End Class` 또는 `End Structure`</span><span class="sxs-lookup"><span data-stu-id="7712e-145">`End Class` or `End Structure`</span></span>|<span data-ttu-id="7712e-146">`Class` 또는 `Structure`에 대한 이 부분적 정의를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-146">Ends this partial `Class` or `Structure` definition.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7712e-147">설명</span><span class="sxs-lookup"><span data-stu-id="7712e-147">Remarks</span></span>  
 <span data-ttu-id="7712e-148">Visual Basic에서는 사용자가 별도의 소스 파일에서 작성한 코드에서 생성된 코드를 구분하는 데 partial 클래스 정의를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-148">Visual Basic uses partial-class definitions to separate generated code from user-authored code in separate source files.</span></span> <span data-ttu-id="7712e-149">예를 들어, **Windows Form 디자이너**에서는 <xref:System.Windows.Forms.Form>과 같은 컨트롤에 대해 partial 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-149">For example, the **Windows Form Designer** defines partial classes for controls such as <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="7712e-150">이런 컨트롤에서 생성된 코드를 수정해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-150">You should not modify the generated code in these controls.</span></span>  
  
 <span data-ttu-id="7712e-151">부분 형식(Partial Type)을 만들면 클래스, 구조체, 인터페이스 및 모듈 만들기에 대한 모든 규칙(예; 한정자 사용 및 상속에 대한 규칙)이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-151">All the rules for class, structure, interface, and module creation, such as those for modifier usage and inheritance, apply when creating a partial type.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="7712e-152">모범 사례</span><span class="sxs-lookup"><span data-stu-id="7712e-152">Best Practices</span></span>  
  
-   <span data-ttu-id="7712e-153">일반적인 상황에서는 단일 형식의 개발을 두 개 이상의 선언으로 분할해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-153">Under normal circumstances, you should not split the development of a single type across two or more declarations.</span></span> <span data-ttu-id="7712e-154">따라서 대부분의 경우 `Partial` 키워드가 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-154">Therefore, in most cases you do not need the `Partial` keyword.</span></span>  
  
-   <span data-ttu-id="7712e-155">가독성을 위해, 형식에 대한 모든 partial 선언에는 `Partial` 키워드를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-155">For readability, every partial declaration of a type should include the `Partial` keyword.</span></span> <span data-ttu-id="7712e-156">컴파일러는 최대 하나의 partial 선언에서 이 키워드가 생략되는 것을 허용합니다. 두 개 이상의 partial 선언에서 이를 생략하는 경우 컴파일러에서 오류를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-156">The compiler allows at most one partial declaration to omit the keyword; if two or more omit it the compiler signals an error.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="7712e-157">동작</span><span class="sxs-lookup"><span data-stu-id="7712e-157">Behavior</span></span>  
  
-   <span data-ttu-id="7712e-158">**선언의 합집합입니다.**</span><span class="sxs-lookup"><span data-stu-id="7712e-158">**Union of Declarations.**</span></span> <span data-ttu-id="7712e-159">컴파일러는 이 형식을 모든 partial 선언의 공용 구조체로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-159">The compiler treats the type as the union of all its partial declarations.</span></span> <span data-ttu-id="7712e-160">모든 부분 정의의 모든 한정자는 전체 형식에 적용되며, 모든 부분 정의의 모든 멤버를 전체 형식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-160">Every modifier from every partial definition applies to the entire type, and every member from every partial definition is available to the entire type.</span></span>  
  
-   <span data-ttu-id="7712e-161">**형식 승격 모듈의 부분 형식에 사용할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="7712e-161">**Type Promotion Not Allowed For Partial Types in Modules.**</span></span> <span data-ttu-id="7712e-162">모듈 내부에 부분 정의가 있는 경우 해당 형식의 형식 승격은 자동으로 무효화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-162">If a partial definition is inside a module, type promotion of that type is automatically defeated.</span></span> <span data-ttu-id="7712e-163">이러한 경우 일련의 부분 정의로 인해 예기치 않은 결과뿐만 아니라 컴파일러 오류도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-163">In such a case, a set of partial definitions can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="7712e-164">자세한 내용은 참조 [형식 승격](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-164">For more information, see [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).</span></span>  
  
     <span data-ttu-id="7712e-165">컴파일러는 정규화된 경로가 동일한 경우에만 부분 정의를 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-165">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
 <span data-ttu-id="7712e-166">`Partial` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-166">The `Partial` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="7712e-167">Class 문</span><span class="sxs-lookup"><span data-stu-id="7712e-167">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="7712e-168">Structure 문</span><span class="sxs-lookup"><span data-stu-id="7712e-168">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
## <a name="example"></a><span data-ttu-id="7712e-169">예제</span><span class="sxs-lookup"><span data-stu-id="7712e-169">Example</span></span>  
 <span data-ttu-id="7712e-170">다음 예제에서는 클래스 `sampleClass`의 정의를 두 개의 선언으로 분할합니다(여기서 각 선언은 서로 다른 `Sub` 프로시저를 정의함).</span><span class="sxs-lookup"><span data-stu-id="7712e-170">The following example splits the definition of class `sampleClass` into two declarations, each of which defines a different `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrKeywords#3](../../../visual-basic/language-reference/codesnippet/VisualBasic/partial_1.vb)]  
  
 <span data-ttu-id="7712e-171">앞의 예제에서 두 개의 부분 정의는 동일한 소스 파일에 있거나 두 개의 서로 다른 소스 파일에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7712e-171">The two partial definitions in the preceding example could be in the same source file or in two different source files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7712e-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7712e-172">See Also</span></span>  
 [<span data-ttu-id="7712e-173">Class 문</span><span class="sxs-lookup"><span data-stu-id="7712e-173">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="7712e-174">Structure 문</span><span class="sxs-lookup"><span data-stu-id="7712e-174">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="7712e-175">형식 승격</span><span class="sxs-lookup"><span data-stu-id="7712e-175">Type Promotion</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)  
 [<span data-ttu-id="7712e-176">Shadows</span><span class="sxs-lookup"><span data-stu-id="7712e-176">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="7712e-177">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="7712e-177">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="7712e-178">부분 메서드</span><span class="sxs-lookup"><span data-stu-id="7712e-178">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
