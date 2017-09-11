---
title: "형식 승격 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declared elements, scope
- visibility, declared elements
- Partial keyword, unexpected results with type promotion
- scope, declared elements
- scope, Visual Basic
- type promotion
- declared elements, visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: 17
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 383f4b1d29e9bbf81eee44bf78762a80aea9eb36
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="type-promotion-visual-basic"></a><span data-ttu-id="0d73c-102">형식 승격(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d73c-102">Type Promotion (Visual Basic)</span></span>
<span data-ttu-id="0d73c-103">모듈에는 프로그래밍 요소를 선언 하는 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 범위 모듈을 포함 하는 네임 스페이스를 승격 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-103">When you declare a programming element in a module, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] promotes its scope to the namespace containing the module.</span></span> <span data-ttu-id="0d73c-104">이 이라고 *형식 승격*합니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-104">This is known as *type promotion*.</span></span>  
  
 <span data-ttu-id="0d73c-105">다음 예제에서는 모듈의 기본 정 및 해당 모듈의 두 가지 멤버를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-105">The following example shows a skeleton definition of a module and two members of that module.</span></span>  
  
 <span data-ttu-id="0d73c-106">[!code-vb[VbVbalrDeclaredElements #&1;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0d73c-106">[!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]</span></span>  
  
 <span data-ttu-id="0d73c-107">내에서 `projModule`프로그래밍, 모듈 수준에서 선언 된 요소 수준이 올라간 `projNamespace`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-107">Within `projModule`, programming elements declared at module level are promoted to `projNamespace`.</span></span> <span data-ttu-id="0d73c-108">앞의 예제에서 `basicEnum` 및 `innerClass` 승격 된 되지만 `numberSub` 않으므로, 모듈 수준에서 선언 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-108">In the preceding example, `basicEnum` and `innerClass` are promoted, but `numberSub` is not, because it is not declared at module level.</span></span>  
  
## <a name="effect-of-type-promotion"></a><span data-ttu-id="0d73c-109">형식 승격의 효과</span><span class="sxs-lookup"><span data-stu-id="0d73c-109">Effect of Type Promotion</span></span>  
 <span data-ttu-id="0d73c-110">형식 승격의 효과 한정 문자열 모듈 이름을 포함할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-110">The effect of type promotion is that a qualification string does not need to include the module name.</span></span> <span data-ttu-id="0d73c-111">다음 예제는 앞의 예제에서 프로시저를 두 번 호출을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-111">The following example makes two calls to the procedure in the preceding example.</span></span>  
  
 <span data-ttu-id="0d73c-112">[!code-vb[VbVbalrDeclaredElements #&2;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="0d73c-112">[!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]</span></span>  
  
 <span data-ttu-id="0d73c-113">앞의 예제에서 첫 번째 호출 완전 한 한정 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-113">In the preceding example, the first call uses complete qualification strings.</span></span> <span data-ttu-id="0d73c-114">그러나이 필요 없는 인해 형식 승격 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-114">However, this is not necessary because of type promotion.</span></span> <span data-ttu-id="0d73c-115">두 번째 호출도 액세스 모듈의 멤버를 포함 하지 않고 `projModule` 한정 문자열에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-115">The second call also accesses the module's members without including `projModule` in the qualification strings.</span></span>  
  
## <a name="defeat-of-type-promotion"></a><span data-ttu-id="0d73c-116">형식 승격의 무효화</span><span class="sxs-lookup"><span data-stu-id="0d73c-116">Defeat of Type Promotion</span></span>  
 <span data-ttu-id="0d73c-117">네임 스페이스에는 모듈 멤버와 동일한 이름 가진 멤버 이미 있으면 형식 승격이 무효화 됩니다 해당 모듈 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-117">If the namespace already has a member with the same name as a module member, type promotion is defeated for that module member.</span></span> <span data-ttu-id="0d73c-118">다음 예제에서는 열거형과 같은 네임 스페이스 내에서 모듈의 기본 정의 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-118">The following example shows a skeleton definition of an enumeration and a module within the same namespace.</span></span>  
  
 <span data-ttu-id="0d73c-119">[!code-vb[VbVbalrDeclaredElements #&3;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="0d73c-119">[!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]</span></span>  
  
 <span data-ttu-id="0d73c-120">앞의 예제에서 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 클래스를 승격할 수 없습니다 `abc` 를 `thisNameSpace` 네임 스페이스 수준에서 동일한 이름의 열거형 이미 있기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-120">In the preceding example, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot promote class `abc` to `thisNameSpace` because there is already an enumeration with the same name at namespace level.</span></span> <span data-ttu-id="0d73c-121">에 액세스 하려면 `abcSub`, 정규화 문자열을 사용 해야 `thisNamespace.thisModule.abc.abcSub`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-121">To access `abcSub`, you must use the full qualification string `thisNamespace.thisModule.abc.abcSub`.</span></span> <span data-ttu-id="0d73c-122">그러나 클래스 `xyz` 는 여전히 승격 액세스할 수 있습니다 `xyzSub` 짧은 한정 문자열 `thisNamespace.xyz.xyzSub`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-122">However, class `xyz` is still promoted, and you can access `xyzSub` with the shorter qualification string `thisNamespace.xyz.xyzSub`.</span></span>  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a><span data-ttu-id="0d73c-123">부분 형식에 대 한 형식 승격의 무효화</span><span class="sxs-lookup"><span data-stu-id="0d73c-123">Defeat of Type Promotion for Partial Types</span></span>  
 <span data-ttu-id="0d73c-124">클래스 또는 구조체 모듈 내에서 사용 하는 경우는 [부분](../../../../visual-basic/language-reference/modifiers/partial.md) 키워드, 형식 승격을 자동으로 해당 클래스 또는 구조체에 대 한 네임 스페이스에 동일한 이름 가진 멤버가 있는지 여부.</span><span class="sxs-lookup"><span data-stu-id="0d73c-124">If a class or structure inside a module uses the [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) keyword, type promotion is automatically defeated for that class or structure, whether or not the namespace has a member with the same name.</span></span> <span data-ttu-id="0d73c-125">모듈에서 다른 요소는 여전히 형식 승격에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-125">Other elements in the module are still eligible for type promotion.</span></span>  
  
 <span data-ttu-id="0d73c-126">**결과가 발생 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0d73c-126">**Consequences.**</span></span> <span data-ttu-id="0d73c-127">부분 정의의 형식 승격의 무효화도 컴파일러 오류 및 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-127">Defeat of type promotion of a partial definition can cause unexpected results and even compiler errors.</span></span> <span data-ttu-id="0d73c-128">다음 예제에서는 그 중 하나는 모듈 내 클래스의 기본 부분 정의 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-128">The following example shows skeleton partial definitions of a class, one of which is inside a module.</span></span>  
  
 <span data-ttu-id="0d73c-129">[!code-vb[VbVbalrDeclaredElements #&4;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="0d73c-129">[!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]</span></span>  
  
 <span data-ttu-id="0d73c-130">앞의 예제에서 개발자의 두 부분 정의를 병합할 컴파일러 예상 `sampleClass`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-130">In the preceding example, the developer might expect the compiler to merge the two partial definitions of `sampleClass`.</span></span> <span data-ttu-id="0d73c-131">그러나 컴파일러 내의 부분 정의 대 한 승격 고려 하지 않습니다 `sampleModule`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-131">However, the compiler does not consider promotion for the partial definition inside `sampleModule`.</span></span> <span data-ttu-id="0d73c-132">결과적으로, 두 개의 개별 클래스를 컴파일하려고 시도 이라는 `sampleClass` 로 같지만 서로 다른 한정 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-132">As a result, it attempts to compile two separate and distinct classes, both named `sampleClass` but with different qualification paths.</span></span>  
  
 <span data-ttu-id="0d73c-133">컴파일러는 정규화된 경로가 동일한 경우에만 부분 정의를 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-133">The compiler merges partial definitions only when their fully qualified paths are identical.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="0d73c-134">권장 사항</span><span class="sxs-lookup"><span data-stu-id="0d73c-134">Recommendations</span></span>  
 <span data-ttu-id="0d73c-135">다음 권장 사항을 바람직한 프로그래밍 관행을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-135">The following recommendations represent good programming practice.</span></span>  
  
-   <span data-ttu-id="0d73c-136">**고유 이름입니다.**</span><span class="sxs-lookup"><span data-stu-id="0d73c-136">**Unique Names.**</span></span> <span data-ttu-id="0d73c-137">프로그래밍 요소 이름 지정에 대 한 모든 권한을 있으면 고유 이름을 사용 하는 것은입니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-137">When you have full control over the naming of programming elements, it is always a good idea to use unique names everywhere.</span></span> <span data-ttu-id="0d73c-138">동일한 이름을 추가 정해야 할 수 있으며 코드를 읽기 어려울.</span><span class="sxs-lookup"><span data-stu-id="0d73c-138">Identical names require extra qualification and can make your code harder to read.</span></span> <span data-ttu-id="0d73c-139">사소한 오류와 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-139">They can also lead to subtle errors and unexpected results.</span></span>  
  
-   <span data-ttu-id="0d73c-140">**전체 경로입니다.**</span><span class="sxs-lookup"><span data-stu-id="0d73c-140">**Full Qualification.**</span></span> <span data-ttu-id="0d73c-141">모듈 및 기타 요소는 동일한 네임 스페이스에서와 작업 하는 항상 모든 프로그래밍 요소에 대 한 정규화를 사용 하는 가장 안전한 방법은입니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-141">When you are working with modules and other elements in the same namespace, the safest approach is to always use full qualification for all programming elements.</span></span> <span data-ttu-id="0d73c-142">형식 승격 모듈 멤버에 대 한 패배 하 고 해당 멤버를 완벽 하 게 지정 하지 않으면 실수로 다른 프로그래밍 요소를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d73c-142">If type promotion is defeated for a module member and you do not fully qualify that member, you could inadvertently access a different programming element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d73c-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d73c-143">See Also</span></span>  
 <span data-ttu-id="0d73c-144">[Module 문](../../../../visual-basic/language-reference/statements/module-statement.md) </span><span class="sxs-lookup"><span data-stu-id="0d73c-144">[Module Statement](../../../../visual-basic/language-reference/statements/module-statement.md) </span></span>  
<span data-ttu-id="0d73c-145"> [Namespace 문](../../../../visual-basic/language-reference/statements/namespace-statement.md) </span><span class="sxs-lookup"><span data-stu-id="0d73c-145"> [Namespace Statement](../../../../visual-basic/language-reference/statements/namespace-statement.md) </span></span>  
<span data-ttu-id="0d73c-146"> [부분](../../../../visual-basic/language-reference/modifiers/partial.md) </span><span class="sxs-lookup"><span data-stu-id="0d73c-146"> [Partial](../../../../visual-basic/language-reference/modifiers/partial.md) </span></span>  
<span data-ttu-id="0d73c-147"> [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span><span class="sxs-lookup"><span data-stu-id="0d73c-147"> [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md) </span></span>  
<span data-ttu-id="0d73c-148"> [방법: 변수의 범위 제어](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md) </span><span class="sxs-lookup"><span data-stu-id="0d73c-148"> [How to: Control the Scope of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md) </span></span>  
<span data-ttu-id="0d73c-149"> [선언된 요소 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span><span class="sxs-lookup"><span data-stu-id="0d73c-149"> [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)</span></span>
