---
title: 형식 승격(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
ms.openlocfilehash: 104fa906fecc5a5bb8704fe3ab839f9f200cf73b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649427"
---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="18f99-102">형식 승격(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18f99-102">Type Promotion (Visual Basic)</span></span>
<span data-ttu-id="18f99-103">모듈에는 프로그래밍 요소를 선언 하면 Visual Basic 모듈을 포함 하는 네임 스페이스에 해당 범위를 승격 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-103">When you declare a programming element in a module, Visual Basic promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="18f99-104">로 알려져 *형식 승격*합니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="18f99-105">다음 예제에서는 모듈의 기본 정 및 해당 모듈의 두 명의 멤버를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 <span data-ttu-id="18f99-106">내에서 `projModule`프로그래밍, 모듈 수준에서 선언 된 요소 수준이 올라간 `projNamespace`합니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-106">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="18f99-107">앞의 예제에서 `basicEnum` 및 `innerClass` 승격 되 면 하지만 `numberSub` 모듈 수준에서 선언 되지 않았으므로 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-107">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="18f99-108">형식 승격의 효과</span><span class="sxs-lookup"><span data-stu-id="18f99-108">Effect of Type Promotion</span></span>  
 <span data-ttu-id="18f99-109">형식 승격의 효과 모듈의 이름을 포함 하는 한정 문자열 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-109">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="18f99-110">다음 예제에서는 앞의 예제에서 프로시저에 두 개의 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-110">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 <span data-ttu-id="18f99-111">앞의 예제에서 첫 번째 호출 완전 한 한정 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-111">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="18f99-112">그러나이 필요한으로 인해 않습니다 형식 승격 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-112">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="18f99-113">두 번째 호출 또한 액세스 모듈의 멤버를 포함 하지 않고 `projModule` 한정 문자열에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-113">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="18f99-114">형식 승격의 무효화</span><span class="sxs-lookup"><span data-stu-id="18f99-114">Defeat of Type Promotion</span></span>  
 <span data-ttu-id="18f99-115">네임 스페이스 모듈 멤버와 동일한 이름 가진 멤버가 이미 있으면 형식 승격 해당 모듈 멤버에 대 한 타원를 통과 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-115">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="18f99-116">다음 예제에서는 열거형과 동일한 네임 스페이스 내에서 모듈의 기본 정의 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-116">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 <span data-ttu-id="18f99-117">위의 예제에서는 Visual Basic 클래스를 승격할 수 없습니다 `abc` 를 `thisNameSpace` 네임 스페이스 수준에서 동일한 이름 가진 열거형 이미 있기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-117">In the preceding example, Visual Basic cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="18f99-118">에 액세스 하려면 `abcSub`, 정규화 문자열을 사용 해야 `thisNamespace.thisModule.abc.abcSub`합니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-118">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="18f99-119">그러나 클래스 `xyz` 여전히 승격에 액세스할 수 있습니다 및 `xyzSub` 짧은 한정 문자열 `thisNamespace.xyz.xyzSub`합니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-119">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="18f99-120">부분 형식에 대 한 형식 승격의 무효화</span><span class="sxs-lookup"><span data-stu-id="18f99-120">Defeat of Type Promotion for Partial Types</span></span>  
 <span data-ttu-id="18f99-121">클래스 또는 모듈 내 구조를 사용 하는 경우는 [부분](../../../../visual-basic/language-reference/modifiers/partial.md) 키워드를 네임 스페이스에 같은 이름의 멤버가 여부 형식 승격 해당 클래스 또는 구조체에 대 한 자동으로 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-121">If a class or structure inside a module uses the [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="18f99-122">모듈의 다른 요소는 여전히 형식 승격에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-122">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="18f99-123">**결과가 발생 합니다.**</span><span class="sxs-lookup"><span data-stu-id="18f99-123">**Consequences.**</span></span> <span data-ttu-id="18f99-124">부분 정의의 형식 승격의 무효화 예기치 않은 결과 뿐만 아니라 컴파일러 오류도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-124">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="18f99-125">다음 예제에서는 그 중 하나는 모듈 내 클래스의 기본 부분 정의 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-125">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 <span data-ttu-id="18f99-126">앞의 예제에서 개발자의 두 개의 부분 정의 병합 하려면 컴파일러 예상 `sampleClass`합니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-126">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="18f99-127">그러나 컴파일러 내 부분 정의 대 한 승격을 고려 하지 않습니다 `sampleModule`합니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-127">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="18f99-128">결과적으로, 두 개의 개별 클래스를 컴파일하려고 시도 이라는 `sampleClass` 로 같지만 서로 다른 한정 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-128">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="18f99-129">컴파일러는 정규화된 경로가 동일한 경우에만 부분 정의를 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-129">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="18f99-130">권장 사항</span><span class="sxs-lookup"><span data-stu-id="18f99-130">Recommendations</span></span>  
 <span data-ttu-id="18f99-131">다음 권장 사항을 바람직한 프로그래밍 관행을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-131">The following recommendations represent good programming practice.</span></span>  
  
-   <span data-ttu-id="18f99-132">**고유 이름입니다.**</span><span class="sxs-lookup"><span data-stu-id="18f99-132">**Unique Names.**</span></span> <span data-ttu-id="18f99-133">프로그래밍 요소 이름은 대 한 모든 권한의 사용 하는 경우 항상 이므로 고유 이름을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-133">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="18f99-134">동일한 추가 한정 필요 이름과를 읽기 어려울 코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-134">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="18f99-135">사소한 오류와 예기치 않은 결과가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-135">They can also lead to subtle errors and unexpected results.</span></span>  
  
-   <span data-ttu-id="18f99-136">**전체 경로입니다.**</span><span class="sxs-lookup"><span data-stu-id="18f99-136">**Full Qualification.**</span></span> <span data-ttu-id="18f99-137">모듈 및 동일한 네임 스페이스의 다른 요소와 함께 작업 하는 항상 모든 프로그래밍 요소에 대 한 전체 경로 사용 하는 가장 안전한 방법이입니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-137">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="18f99-138">형식 승격 모듈 멤버에 대 한 타원를 하는 경우 해당 멤버를 완벽 하 게 지정 하지 않으면 다른 프로그래밍 요소를 실수로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f99-138">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f99-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18f99-139">See Also</span></span>  
 [<span data-ttu-id="18f99-140">Module 문</span><span class="sxs-lookup"><span data-stu-id="18f99-140">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [<span data-ttu-id="18f99-141">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="18f99-141">Namespace Statement</span></span>](../../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [<span data-ttu-id="18f99-142">부분</span><span class="sxs-lookup"><span data-stu-id="18f99-142">Partial</span></span>](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [<span data-ttu-id="18f99-143">Visual Basic의 범위</span><span class="sxs-lookup"><span data-stu-id="18f99-143">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [<span data-ttu-id="18f99-144">방법: 변수의 범위 제어</span><span class="sxs-lookup"><span data-stu-id="18f99-144">How to: Control the Scope of a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [<span data-ttu-id="18f99-145">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="18f99-145">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
