---
title: Partial 클래스 및 메서드(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
ms.openlocfilehash: d257846821f14a377c505099e38971dd5d8a297a
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172440"
---
# <a name="partial-classes-and-methods-c-programming-guide"></a><span data-ttu-id="23d28-102">Partial 클래스 및 메서드(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="23d28-102">Partial Classes and Methods (C# Programming Guide)</span></span>
<span data-ttu-id="23d28-103">[클래스](../../../csharp/language-reference/keywords/class.md) 또는 [구조체](../../../csharp/language-reference/keywords/struct.md), [인터페이스](../../../csharp/language-reference/keywords/interface.md) 또는 메서드의 정의를 둘 이상의 소스 파일에 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-103">It is possible to split the definition of a [class](../../../csharp/language-reference/keywords/class.md) or a [struct](../../../csharp/language-reference/keywords/struct.md), an [interface](../../../csharp/language-reference/keywords/interface.md) or a method over two or more source files.</span></span> <span data-ttu-id="23d28-104">각 소스 파일에는 형식 또는 메서드 정의 섹션이 있으며 모든 부분은 응용 프로그램이 컴파일될 때 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-104">Each source file contains a section of the type or method definition, and all parts are combined when the application is compiled.</span></span>  
  
## <a name="partial-classes"></a><span data-ttu-id="23d28-105">partial 클래스</span><span class="sxs-lookup"><span data-stu-id="23d28-105">Partial Classes</span></span>  
 <span data-ttu-id="23d28-106">클래스 정의를 분할하는 것이 바람직한 몇 가지 상황이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-106">There are several situations when splitting a class definition is desirable:</span></span>  
  
-   <span data-ttu-id="23d28-107">대규모 프로젝트에서 작업하는 경우 클래스를 개별 파일에 분산하면 여러 프로그래머가 동시에 클래스에 대해 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-107">When working on large projects, spreading a class over separate files enables multiple programmers to work on it at the same time.</span></span>  
  
-   <span data-ttu-id="23d28-108">자동으로 생성된 소스로 작업하는 경우 소스 파일을 다시 만들지 않고도 클래스에 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-108">When working with automatically generated source, code can be added to the class without having to recreate the source file.</span></span> <span data-ttu-id="23d28-109">Visual Studio에서는 Windows Forms, 웹 서비스 래퍼 코드 등에 만들 때 이 방식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-109">Visual Studio uses this approach when it creates Windows Forms, Web service wrapper code, and so on.</span></span> <span data-ttu-id="23d28-110">Visual Studio에서 만든 파일을 수정하지 않고도 이러한 클래스를 사용하는 코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-110">You can create code that uses these classes without having to modify the file created by Visual Studio.</span></span>  
  
-   <span data-ttu-id="23d28-111">클래스 정의를 분할하려면 다음과 같이 [partial](../../../csharp/language-reference/keywords/partial-type.md) 키워드 한정자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-111">To split a class definition, use the [partial](../../../csharp/language-reference/keywords/partial-type.md) keyword modifier, as shown here:</span></span>  
  
 [!code-csharp[csProgGuideObjects#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_1.cs)]  
  
 <span data-ttu-id="23d28-112">`partial` 키워드는 클래스, 구조체 또는 인터페이스의 다른 부분을 네임스페이스에서 정의할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-112">The `partial` keyword indicates that other parts of the class, struct, or interface can be defined in the namespace.</span></span> <span data-ttu-id="23d28-113">모든 부분은 `partial` 키워드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-113">All the parts must use the `partial` keyword.</span></span> <span data-ttu-id="23d28-114">최종 형식을 생성하려면 컴파일 시간에 모든 부분을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-114">All the parts must be available at compile time to form the final type.</span></span> <span data-ttu-id="23d28-115">모든 부분에 `public`, `private` 등의 동일한 액세스 가능성이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-115">All the parts must have the same accessibility, such as `public`, `private`, and so on.</span></span>  
  
 <span data-ttu-id="23d28-116">부분이 abstract로 선언된 경우 전체 형식이 abstract로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-116">If any part is declared abstract, then the whole type is considered abstract.</span></span> <span data-ttu-id="23d28-117">부분이 sealed로 선언된 경우 전체 형식이 sealed로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-117">If any part is declared sealed, then the whole type is considered sealed.</span></span> <span data-ttu-id="23d28-118">부분이 기본 형식을 선언하는 경우 전체 형식이 해당 클래스를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-118">If any part declares a base type, then the whole type inherits that class.</span></span>  
  
 <span data-ttu-id="23d28-119">기본 클래스를 지정하는 부분은 모두 일치해야 하지만 기본 클래스를 생략하는 부분도 여전히 기본 형식을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-119">All the parts that specify a base class must agree, but parts that omit a base class still inherit the base type.</span></span> <span data-ttu-id="23d28-120">부분에서 다른 기본 인터페이스를 지정할 수 있으며, 최종 형식은 모든 partial 선언에 나열된 모든 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-120">Parts can specify different base interfaces, and the final type implements all the interfaces listed by all the partial declarations.</span></span> <span data-ttu-id="23d28-121">부분 정의에 선언된 클래스, 구조체 또는 인터페이스 멤버는 다른 모든 부분에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-121">Any class, struct, or interface members declared in a partial definition are available to all the other parts.</span></span> <span data-ttu-id="23d28-122">최종 형식은 컴파일 시간의 모든 부분 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-122">The final type is the combination of all the parts at compile time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23d28-123">대리자 또는 열거형 선언에서는 `partial` 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-123">The `partial` modifier is not available on delegate or enumeration declarations.</span></span>  
  
 <span data-ttu-id="23d28-124">다음 예제에서는 중첩된 대상 형식 자체는 부분이 아니어도 중첩된 형식이 부분일 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-124">The following example shows that nested types can be partial, even if the type they are nested within is not partial itself.</span></span>  
  
 [!code-csharp[csProgGuideObjects#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_2.cs)]  
  
 <span data-ttu-id="23d28-125">컴파일 시간에 부분 형식(Partial Type) 정의의 특성이 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-125">At compile time, attributes of partial-type definitions are merged.</span></span> <span data-ttu-id="23d28-126">예를 들어 다음 선언을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="23d28-126">For example, consider the following declarations:</span></span>  
  
 [!code-csharp[csProgGuideObjects#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_3.cs)]  
  
 <span data-ttu-id="23d28-127">이러한 선언은 다음 선언과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-127">They are equivalent to the following declarations:</span></span>  
  
 [!code-csharp[csProgGuideObjects#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_4.cs)]  
  
 <span data-ttu-id="23d28-128">다음은 모든 부분 형식(Partial Type) 정의에서 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-128">The following are merged from all the partial-type definitions:</span></span>  
  
-   <span data-ttu-id="23d28-129">XML 주석</span><span class="sxs-lookup"><span data-stu-id="23d28-129">XML comments</span></span>  
  
-   <span data-ttu-id="23d28-130">인터페이스</span><span class="sxs-lookup"><span data-stu-id="23d28-130">interfaces</span></span>  
  
-   <span data-ttu-id="23d28-131">제네릭 형식 매개 변수 특성</span><span class="sxs-lookup"><span data-stu-id="23d28-131">generic-type parameter attributes</span></span>  
  
-   <span data-ttu-id="23d28-132">클래스 특성</span><span class="sxs-lookup"><span data-stu-id="23d28-132">class attributes</span></span>  
  
-   <span data-ttu-id="23d28-133">멤버</span><span class="sxs-lookup"><span data-stu-id="23d28-133">members</span></span>  
  
 <span data-ttu-id="23d28-134">예를 들어 다음 선언을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="23d28-134">For example, consider the following declarations:</span></span>  
  
 [!code-csharp[csProgGuideObjects#21](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_5.cs)]  
  
 <span data-ttu-id="23d28-135">이러한 선언은 다음 선언과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-135">They are equivalent to the following declarations:</span></span>  
  
 [!code-csharp[csProgGuideObjects#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_6.cs)]  
  
### <a name="restrictions"></a><span data-ttu-id="23d28-136">제한</span><span class="sxs-lookup"><span data-stu-id="23d28-136">Restrictions</span></span>  
 <span data-ttu-id="23d28-137">partial 클래스 정의로 작업할 때 따라야 할 몇 가지 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-137">There are several rules to follow when you are working with partial class definitions:</span></span>  
  
-   <span data-ttu-id="23d28-138">동일한 형식의 일부로 작성된 모든 부분 형식(Partial Type) 정의를 `partial`로 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-138">All partial-type definitions meant to be parts of the same type must be modified with `partial`.</span></span> <span data-ttu-id="23d28-139">예를 들어 다음 클래스 선언은 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-139">For example, the following class declarations generate an error:</span></span>  
  
     [!code-csharp[csProgGuideObjects#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_7.cs)]  
  
-   <span data-ttu-id="23d28-140">`partial` 한정자는 `class`, `struct` 또는 `interface` 키워드 바로 앞에만 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-140">The `partial` modifier can only appear immediately before the keywords `class`, `struct`, or `interface`.</span></span>  
  
-   <span data-ttu-id="23d28-141">다음 예제와 같이 부분 형식(Partial Type) 정의에 중첩된 부분 형식(Partial Type)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-141">Nested partial types are allowed in partial-type definitions as illustrated in the following example:</span></span>  
  
     [!code-csharp[csProgGuideObjects#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_8.cs)]  
  
-   <span data-ttu-id="23d28-142">동일한 형식의 일부로 작성된 모든 부분 형식(Partial Type) 정의는 동일한 어셈블리와 동일한 모듈(.exe 또는 .dll 파일)에서 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-142">All partial-type definitions meant to be parts of the same type must be defined in the same assembly and the same module (.exe or .dll file).</span></span> <span data-ttu-id="23d28-143">부분 정의는 여러 모듈에 걸쳐 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-143">Partial definitions cannot span multiple modules.</span></span>  
  
-   <span data-ttu-id="23d28-144">모든 부분 형식(Partial Type) 정의에서 클래스 이름 및 제네릭 형식 매개 변수가 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-144">The class name and generic-type parameters must match on all partial-type definitions.</span></span> <span data-ttu-id="23d28-145">제네릭 형식은 부분일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-145">Generic types can be partial.</span></span> <span data-ttu-id="23d28-146">각 부분 선언에서 동일한 매개 변수 이름을 동일한 순서로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-146">Each partial declaration must use the same parameter names in the same order.</span></span>  
  
-   <span data-ttu-id="23d28-147">부분 형식(Partial Type) 정의에서 다음 키워드는 선택 사항이지만, 부분 형식(Partial Type) 정의에 있는 경우 동일한 형식의 다른 부분 정의에서 지정된 키워드와 충돌할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-147">The following keywords on a partial-type definition are optional, but if present on one partial-type definition, cannot conflict with the keywords specified on another partial definition for the same type:</span></span>  
  
    -   [<span data-ttu-id="23d28-148">public</span><span class="sxs-lookup"><span data-stu-id="23d28-148">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
    -   [<span data-ttu-id="23d28-149">private</span><span class="sxs-lookup"><span data-stu-id="23d28-149">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
    -   [<span data-ttu-id="23d28-150">protected</span><span class="sxs-lookup"><span data-stu-id="23d28-150">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
    -   [<span data-ttu-id="23d28-151">internal</span><span class="sxs-lookup"><span data-stu-id="23d28-151">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
    -   [<span data-ttu-id="23d28-152">abstract</span><span class="sxs-lookup"><span data-stu-id="23d28-152">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
  
    -   [<span data-ttu-id="23d28-153">sealed</span><span class="sxs-lookup"><span data-stu-id="23d28-153">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)  
  
    -   <span data-ttu-id="23d28-154">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="23d28-154">base class</span></span>  
  
    -   <span data-ttu-id="23d28-155">[new](../../../csharp/language-reference/keywords/new.md) 한정자(중첩된 부분)</span><span class="sxs-lookup"><span data-stu-id="23d28-155">[new](../../../csharp/language-reference/keywords/new.md) modifier (nested parts)</span></span>  
  
    -   <span data-ttu-id="23d28-156">제네릭 제약 조건</span><span class="sxs-lookup"><span data-stu-id="23d28-156">generic constraints</span></span>  
  
         <span data-ttu-id="23d28-157">자세한 내용은 [형식 매개 변수에 대한 제약 조건](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23d28-157">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="23d28-158">예제 1</span><span class="sxs-lookup"><span data-stu-id="23d28-158">Example 1</span></span>  
  
### <a name="description"></a><span data-ttu-id="23d28-159">설명</span><span class="sxs-lookup"><span data-stu-id="23d28-159">Description</span></span>  
 <span data-ttu-id="23d28-160">다음 예제에서는 `CoOrds` 클래스의 생성자 및 필드가 하나의 partial 클래스 정의에서 선언되고 `PrintCoOrds` 멤버가 다른 partial 클래스 정의에서 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-160">In the following example, the fields and the constructor of the class, `CoOrds`, are declared in one partial class definition, and the member, `PrintCoOrds`, is declared in another partial class definition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="23d28-161">코드</span><span class="sxs-lookup"><span data-stu-id="23d28-161">Code</span></span>  
 [!code-csharp[csProgGuideObjects#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_9.cs)]  
  
## <a name="example-2"></a><span data-ttu-id="23d28-162">예제 2</span><span class="sxs-lookup"><span data-stu-id="23d28-162">Example 2</span></span>  
  
### <a name="description"></a><span data-ttu-id="23d28-163">설명</span><span class="sxs-lookup"><span data-stu-id="23d28-163">Description</span></span>  
 <span data-ttu-id="23d28-164">다음 예제에서는 partial 구조체와 인터페이스도 개발할 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-164">The following example shows that you can also develop partial structs and interfaces.</span></span>  
  
### <a name="code"></a><span data-ttu-id="23d28-165">코드</span><span class="sxs-lookup"><span data-stu-id="23d28-165">Code</span></span>  
 [!code-csharp[csProgGuideObjects#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_10.cs)]  
  
## <a name="partial-methods"></a><span data-ttu-id="23d28-166">부분 메서드</span><span class="sxs-lookup"><span data-stu-id="23d28-166">Partial Methods</span></span>  
 <span data-ttu-id="23d28-167">partial 클래스 또는 구조체에는 부분 메서드(Partial Method)가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-167">A partial class or struct may contain a partial method.</span></span> <span data-ttu-id="23d28-168">클래스의 한 부분에는 메서드의 시그니처가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-168">One part of the class contains the signature of the method.</span></span> <span data-ttu-id="23d28-169">동일한 부분이나 다른 부분에서 선택적 구현을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-169">An optional implementation may be defined in the same part or another part.</span></span> <span data-ttu-id="23d28-170">구현을 제공하지 않으면 메서드와 모든 메서드 호출이 컴파일 시간에 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-170">If the implementation is not supplied, then the method and all calls to the method are removed at compile time.</span></span>  
  
 <span data-ttu-id="23d28-171">부분 메서드(Partial Method)를 사용하면 클래스 중 한 부분의 구현자가 이벤트와 비슷하게 메서드를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-171">Partial methods enable the implementer of one part of a class to define a method, similar to an event.</span></span> <span data-ttu-id="23d28-172">클래스 중 다른 부분의 구현자는 메서드를 구현할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-172">The implementer of the other part of the class can decide whether to implement the method or not.</span></span> <span data-ttu-id="23d28-173">메서드가 구현되지 않은 경우 컴파일러는 메서드 시그니처 및 모든 메서드 호출을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-173">If the method is not implemented, then the compiler removes the method signature and all calls to the method.</span></span> <span data-ttu-id="23d28-174">호출의 인수 평가에서 발생하는 모든 결과를 포함하여 메서드 호출은 런타임에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-174">The calls to the method, including any results that would occur from evaluation of arguments in the calls, have no effect at run time.</span></span> <span data-ttu-id="23d28-175">따라서 partial 클래스의 코드는 구현이 제공되지 않은 경우에도 부분 메서드(Partial Method)를 자유롭게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-175">Therefore, any code in the partial class can freely use a partial method, even if the implementation is not supplied.</span></span> <span data-ttu-id="23d28-176">메서드가 호출되었지만 구현되지 않은 경우 컴파일 시간 또는 런타임 오류가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-176">No compile-time or run-time errors will result if the method is called but not implemented.</span></span>  
  
 <span data-ttu-id="23d28-177">부분 메서드(Partial Method)는 생성된 코드를 사용자 지정하는 방법으로 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-177">Partial methods are especially useful as a way to customize generated code.</span></span> <span data-ttu-id="23d28-178">생성된 코드가 메서드를 호출할 수 있지만 개발자가 메서드를 구현할지 여부를 결정할 수 있도록 메서드 이름과 시그니처를 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-178">They allow for a method name and signature to be reserved, so that generated code can call the method but the developer can decide whether to implement the method.</span></span> <span data-ttu-id="23d28-179">partial 클래스와 마찬가지로, 부분 메서드(Partial Method)는 코드 생성기에 의해 생성된 코드와 개발자가 직접 만든 코드가 런타임 비용 없이 함께 작동할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-179">Much like partial classes, partial methods enable code created by a code generator and code created by a human developer to work together without run-time costs.</span></span>  
  
 <span data-ttu-id="23d28-180">부분 메서드(Partial Method) 선언은 정의와 구현, 두 부분으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-180">A partial method declaration consists of two parts: the definition, and the implementation.</span></span> <span data-ttu-id="23d28-181">partial 클래스의 개별 부분이나 동일한 부분에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-181">These may be in separate parts of a partial class, or in the same part.</span></span> <span data-ttu-id="23d28-182">구현 선언이 없는 경우 컴파일러는 정의하는 선언과 모든 메서드 호출을 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-182">If there is no implementation declaration, then the compiler optimizes away both the defining declaration and all calls to the method.</span></span>  
  
```csharp  
// Definition in file1.cs  
partial void onNameChanged();  
  
// Implementation in file2.cs  
partial void onNameChanged()  
{  
  // method body  
}  
```  
  
-   <span data-ttu-id="23d28-183">부분 메서드(Partial Method) 선언은 상황별 키워드 [partial](../../../csharp/language-reference/keywords/partial-type.md)로 시작해야 하고, 메서드에서 [void](../../../csharp/language-reference/keywords/void.md)를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-183">Partial method declarations must begin with the contextual keyword [partial](../../../csharp/language-reference/keywords/partial-type.md) and the method must return [void](../../../csharp/language-reference/keywords/void.md).</span></span>  
  
-   <span data-ttu-id="23d28-184">부분 메서드(Partial Method)는 [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) 또는 [ref](../../../csharp/language-reference/keywords/ref.md) 매개 변수를 사용할 수 있지만 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 매개 변수는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-184">Partial methods can have [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) or [ref](../../../csharp/language-reference/keywords/ref.md) but not [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>  
  
-   <span data-ttu-id="23d28-185">부분 메서드(Partial Method)는 암시적으로 [private](../../../csharp/language-reference/keywords/private.md)이므로 [가상](../../../csharp/language-reference/keywords/virtual.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-185">Partial methods are implicitly [private](../../../csharp/language-reference/keywords/private.md), and therefore they cannot be [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
-   <span data-ttu-id="23d28-186">부분 메서드(Partial Method)는 본문의 존재 여부에 따라 정의하는지, 구현하는지가 결정되기 때문에 [extern](../../../csharp/language-reference/keywords/extern.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-186">Partial methods cannot be [extern](../../../csharp/language-reference/keywords/extern.md), because the presence of the body determines whether they are defining or implementing.</span></span>  
  
-   <span data-ttu-id="23d28-187">부분 메서드(Partial Method)는 [static](../../../csharp/language-reference/keywords/static.md) 및 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-187">Partial methods can have [static](../../../csharp/language-reference/keywords/static.md) and [unsafe](../../../csharp/language-reference/keywords/unsafe.md) modifiers.</span></span>  
  
-   <span data-ttu-id="23d28-188">부분 메서드(Partial Method)는 제네릭일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-188">Partial methods can be generic.</span></span> <span data-ttu-id="23d28-189">제약 조건은 정의하는 부분 메서드(Partial Method) 선언에 배치되며 필요에 따라 구현하는 선언에서 반복될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-189">Constraints are put on the defining partial method declaration, and may optionally be repeated on the implementing one.</span></span> <span data-ttu-id="23d28-190">매개 변수 및 형식 매개 변수 이름이 정의하는 선언과 구현하는 선언에서 동일할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-190">Parameter and type parameter names do not have to be the same in the implementing declaration as in the defining one.</span></span>  
  
-   <span data-ttu-id="23d28-191">정의 및 구현된 부분 메서드(Partial Method)에 대한 [대리자](../../../csharp/language-reference/keywords/delegate.md)는 만들 수 있지만 정의만 된 부분 메서드(Partial Method)에 대한 대리자는 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23d28-191">You can make a [delegate](../../../csharp/language-reference/keywords/delegate.md) to a partial method that has been defined and implemented, but not to a partial method that has only been defined.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="23d28-192">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="23d28-192">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="23d28-193">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23d28-193">See Also</span></span>  
 [<span data-ttu-id="23d28-194">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="23d28-194">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="23d28-195">클래스</span><span class="sxs-lookup"><span data-stu-id="23d28-195">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
 [<span data-ttu-id="23d28-196">구조체</span><span class="sxs-lookup"><span data-stu-id="23d28-196">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
 [<span data-ttu-id="23d28-197">인터페이스</span><span class="sxs-lookup"><span data-stu-id="23d28-197">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)  
 [<span data-ttu-id="23d28-198">partial(형식)</span><span class="sxs-lookup"><span data-stu-id="23d28-198">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)
