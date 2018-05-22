---
title: class(C# 참조)
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 20968d2f72195db6d16de1b726c6e946b91ffcd5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="class-c-reference"></a><span data-ttu-id="5a55d-102">class(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="5a55d-102">class (C# Reference)</span></span>

<span data-ttu-id="5a55d-103">클래스는 다음 예제와 같이 `class` 키워드를 사용하여 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-103">Classes are declared using the keyword `class`, as shown in the following example:</span></span>

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates 
    // and nested classes go here.
}
```

## <a name="remarks"></a><span data-ttu-id="5a55d-104">설명</span><span class="sxs-lookup"><span data-stu-id="5a55d-104">Remarks</span></span>
<span data-ttu-id="5a55d-105">C#에서는 단일 상속만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-105">Only single inheritance is allowed in C#.</span></span> <span data-ttu-id="5a55d-106">즉, 한 클래스는 하나의 기본 클래스에서만 구현을 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-106">In other words, a class can inherit implementation from one base class only.</span></span> <span data-ttu-id="5a55d-107">그러나 한 클래스는 두 개 이상의 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-107">However, a class can implement more than one interface.</span></span> <span data-ttu-id="5a55d-108">다음 표에는 클래스 상속 및 인터페이스 구현에 대한 예제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-108">The following table shows examples of class inheritance and interface implementation:</span></span>

|<span data-ttu-id="5a55d-109">상속</span><span class="sxs-lookup"><span data-stu-id="5a55d-109">Inheritance</span></span>|<span data-ttu-id="5a55d-110">예</span><span class="sxs-lookup"><span data-stu-id="5a55d-110">Example</span></span>|
|-----------------|-------------|
|<span data-ttu-id="5a55d-111">없음</span><span class="sxs-lookup"><span data-stu-id="5a55d-111">None</span></span>|`class ClassA { }`|
|<span data-ttu-id="5a55d-112">Single</span><span class="sxs-lookup"><span data-stu-id="5a55d-112">Single</span></span>|`class DerivedClass: BaseClass { }`|
|<span data-ttu-id="5a55d-113">없음. 두 개의 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="5a55d-113">None, implements two interfaces</span></span>|`class ImplClass: IFace1, IFace2 { }`|
|<span data-ttu-id="5a55d-114">단일. 하나의 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="5a55d-114">Single, implements one interface</span></span>|`class ImplDerivedClass: BaseClass, IFace1 { }`|

<span data-ttu-id="5a55d-115">다른 클래스 내에 중첩되는 것이 아니라 네임스페이스 내에서 직접 선언되는 클래스는 [public](../../../csharp/language-reference/keywords/public.md) 또는 [internal](../../../csharp/language-reference/keywords/internal.md)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-115">Classes that you declare directly within a namespace, not nested within other classes, can be either [public](../../../csharp/language-reference/keywords/public.md) or [internal](../../../csharp/language-reference/keywords/internal.md).</span></span> <span data-ttu-id="5a55d-116">기본적으로 클래스는 `internal`입니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-116">Classes are `internal` by default.</span></span>

<span data-ttu-id="5a55d-117">중첩 클래스를 포함한 클래스 멤버는 [public](../../../csharp/language-reference/keywords/public.md), `protected internal`, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [private](../../../csharp/language-reference/keywords/private.md) 또는 `private protected`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-117">Class members, including nested classes, can be [public](../../../csharp/language-reference/keywords/public.md), `protected internal`, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [private](../../../csharp/language-reference/keywords/private.md), or `private protected`.</span></span> <span data-ttu-id="5a55d-118">기본적으로 멤버는 [private](../../../csharp/language-reference/keywords/private.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-118">Members are [private](../../../csharp/language-reference/keywords/private.md) by default.</span></span>

<span data-ttu-id="5a55d-119">자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a55d-119">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>

<span data-ttu-id="5a55d-120">형식 매개 변수가 포함된 제네릭 클래스를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-120">You can declare generic classes that have type parameters.</span></span> <span data-ttu-id="5a55d-121">자세한 내용은 [제네릭 클래스](../../../csharp/programming-guide/generics/generic-classes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a55d-121">For more information, see [Generic Classes](../../../csharp/programming-guide/generics/generic-classes.md).</span></span>

<span data-ttu-id="5a55d-122">클래스에는 다음 멤버의 선언이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-122">A class can contain declarations of the following members:</span></span>

- [<span data-ttu-id="5a55d-123">생성자</span><span class="sxs-lookup"><span data-stu-id="5a55d-123">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)

- [<span data-ttu-id="5a55d-124">상수</span><span class="sxs-lookup"><span data-stu-id="5a55d-124">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)

- [<span data-ttu-id="5a55d-125">필드</span><span class="sxs-lookup"><span data-stu-id="5a55d-125">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)

- [<span data-ttu-id="5a55d-126">종료자</span><span class="sxs-lookup"><span data-stu-id="5a55d-126">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

- [<span data-ttu-id="5a55d-127">메서드</span><span class="sxs-lookup"><span data-stu-id="5a55d-127">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="5a55d-128">속성</span><span class="sxs-lookup"><span data-stu-id="5a55d-128">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

- [<span data-ttu-id="5a55d-129">인덱서</span><span class="sxs-lookup"><span data-stu-id="5a55d-129">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)

- [<span data-ttu-id="5a55d-130">연산자</span><span class="sxs-lookup"><span data-stu-id="5a55d-130">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)

- [<span data-ttu-id="5a55d-131">이벤트</span><span class="sxs-lookup"><span data-stu-id="5a55d-131">Events</span></span>](../../../csharp/programming-guide/events/index.md)

- [<span data-ttu-id="5a55d-132">대리자</span><span class="sxs-lookup"><span data-stu-id="5a55d-132">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)

- [<span data-ttu-id="5a55d-133">클래스</span><span class="sxs-lookup"><span data-stu-id="5a55d-133">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)

- [<span data-ttu-id="5a55d-134">인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a55d-134">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

- [<span data-ttu-id="5a55d-135">구조체</span><span class="sxs-lookup"><span data-stu-id="5a55d-135">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)

## <a name="example"></a><span data-ttu-id="5a55d-136">예</span><span class="sxs-lookup"><span data-stu-id="5a55d-136">Example</span></span>
<span data-ttu-id="5a55d-137">다음 예제에서는 클래스 필드, 생성자 및 메서드를 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-137">The following example demonstrates declaring class fields, constructors, and methods.</span></span> <span data-ttu-id="5a55d-138">또한 개체 인스턴스화 및 인스턴스 데이터 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-138">It also demonstrates object instantiation and printing instance data.</span></span> <span data-ttu-id="5a55d-139">이 예제에서는 두 개의 클래스가 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-139">In this example, two classes are declared.</span></span> <span data-ttu-id="5a55d-140">첫 번째 클래스인 `Child`는 private 필드 2개(`name` 및 `age`), public 생성자 2개, public 메서드 1개를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-140">The first class, `Child`, contains two private fields (`name` and `age`), two public constructors and one public method.</span></span> <span data-ttu-id="5a55d-141">두 번째 클래스인 `StringTest`는 `Main`을 포함하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-141">The second class, `StringTest`, is used to contain `Main`.</span></span>

[!code-csharp[csrefKeywordsTypes#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/class_1.cs)]

## <a name="comments"></a><span data-ttu-id="5a55d-142">설명</span><span class="sxs-lookup"><span data-stu-id="5a55d-142">Comments</span></span>
<span data-ttu-id="5a55d-143">이전 예제에서 private 필드(`name` 및 `age`)는 `Child` 클래스의 public 메서드를 통해서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-143">Notice that in the previous example the private fields (`name` and `age`) can only be accessed through the public method of the `Child` class.</span></span> <span data-ttu-id="5a55d-144">예를 들어 다음과 같은 문을 사용하여 `Main` 메서드에서 자식의 이름을 출력할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-144">For example, you cannot print the child's name, from the `Main` method, using a statement like this:</span></span>

```csharp
Console.Write(child1.name);   // Error
```

<span data-ttu-id="5a55d-145">`Main`이 클래스의 멤버인 경우에만 `Main`에서 `Child`의 private 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-145">Accessing private members of `Child` from `Main` would only be possible if `Main` were a member of the class.</span></span>

<span data-ttu-id="5a55d-146">액세스 한정자 없이 클래스 내부에 선언된 형식은 기본적으로 `private`로 설정되므로 키워드가 제거된 경우 이 예제의 데이터 멤버는 `private`입니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-146">Types declared inside a class without an access modifier default to `private`, so the data members in this example would still be `private` if the keyword were removed.</span></span>

<span data-ttu-id="5a55d-147">마지막으로 기본 생성자(`child3`)를 사용하여 만들어진 개체의 경우 연령 필드는 기본적으로 0으로 초기화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5a55d-147">Finally, notice that for the object created using the default constructor (`child3`), the age field was initialized to zero by default.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5a55d-148">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="5a55d-148">C# Language Specification</span></span>
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5a55d-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a55d-149">See Also</span></span>
 [<span data-ttu-id="5a55d-150">C# 참조</span><span class="sxs-lookup"><span data-stu-id="5a55d-150">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5a55d-151">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="5a55d-151">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5a55d-152">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="5a55d-152">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="5a55d-153">참조 형식</span><span class="sxs-lookup"><span data-stu-id="5a55d-153">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)
