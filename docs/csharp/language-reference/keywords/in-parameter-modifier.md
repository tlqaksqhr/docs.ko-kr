---
title: in 매개 변수 한정자(C# 참조)
ms.date: 03/06/2018
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
ms.openlocfilehash: 58500cf2caa1446af6b663f1b765c0be92309f1d
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2018
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="b4be4-102">in 매개 변수 한정자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="b4be4-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="b4be4-103">`in` 키워드를 사용하면 참조를 통해 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="b4be4-104">이 키워드는 호출된 메서드에서 `in` 인수를 수정할 수 없다는 점을 제외하고 [ref](ref.md) 또는 [out](out-parameter-modifier.md) 키워드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-104">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method.</span></span> <span data-ttu-id="b4be4-105">`ref` 인수는 수정할 수 있지만 `out` 인수는 호출자가 수정해야 하며, 해당 수정 사항은 호출 컨텍스트에서 식별 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-105">Whereas `ref` arguments may be modified,  `out` arguments must be modified by the caller, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="b4be4-106">앞의 예제는 호출 사이트에서 일반적으로 `in` 한정자가 필요하지 않다는 것을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-106">The preceding example demonstrates that the `in` modifier is usually unnecessary at the call site.</span></span> <span data-ttu-id="b4be4-107">메서드 선언에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-107">It is only required in the method declaration.</span></span>

> [!NOTE] 
> <span data-ttu-id="b4be4-108">`in` 키워드는 `foreach` 명령문의 일부 또는 LINQ 쿼리에서 `join` 절의 일부로 형식 매개 변수가 반공변(contravariant)임을 지정하도록 제네릭 형식 매개 변수와 함께 사용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-108">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="b4be4-109">이러한 컨텍스트에서 `in` 키워드의 사용에 대한 자세한 내용은 모든 해당 사용에 대한 링크를 제공하는 [in](in.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4be4-109">For more information on the use of the `in` keyword in these contexts, see [in](in.md), which provides links to all those uses.</span></span>
  
 <span data-ttu-id="b4be4-110">`in` 인수로 전달되는 변수는 메서드 호출에서 전달되기 전에 초기화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-110">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="b4be4-111">그러나 호출된 메서드는 값을 할당하거나 인수를 수정하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-111">However, the called method may not assign a value or modify the argument.</span></span>  
  
 <span data-ttu-id="b4be4-112">`in`, `ref` 및 `out` 키워드는 서로 다른 런타임 동작을 수행하지만 컴파일 시간에 메서드 시그니처의 일부로 간주되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-112">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="b4be4-113">따라서 메서드 하나는 `ref` 또는 `in` 인수를 사용하고 다른 하나는 `out` 인수를 사용한다는 것 외에는 차이점이 없으면 메서드를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-113">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="b4be4-114">예를 들어 다음 코드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-114">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="b4be4-115">`in`의 존재에 기반한 오버로딩이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-115">Overloading based on the presence of `in` is allowed:</span></span>  
  
```csharp
class InOverloads
{
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

## <a name="overload-resolution-rules"></a><span data-ttu-id="b4be4-116">오버로드 해결 규칙</span><span class="sxs-lookup"><span data-stu-id="b4be4-116">Overload resolution rules</span></span>

<span data-ttu-id="b4be4-117">`in` 인수에 대한 동기를 이해하여 값과 `in` 인수로 메서드의 오버로드 해결 규칙을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-117">You can understand the overload resolution rules for methods with by value vs. `in` arguments by understanding the motivation for `in` arguments.</span></span> <span data-ttu-id="b4be4-118">`in` 매개 변수를 사용하여 메서드를 정의하면 잠재적인 성능 최적화가 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-118">Defining methods using `in` parameters is a potential performance optimization.</span></span> <span data-ttu-id="b4be4-119">일부 `struct` 형식 인수는 크기가 클 수 있으며 긴밀한 루프 또는 중요한 코드 경로에서 메서드를 호출할 때 해당 구조를 복사하는 비용이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-119">Some `struct` type arguments may be large in size, and when methods are called in tight loops or critical code paths, the cost of copying those structures is critical.</span></span> <span data-ttu-id="b4be4-120">메서드는 호출된 메서드가 인수의 상태를 수정하지 않으므로 `in` 매개 변수를 선언하여 해당 인수가 참조로 안전하게 전달될 수 있음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-120">Methods declare `in` parameters to specify that arguments may be passed by reference safely because the called method does not modify the state of that argument.</span></span> <span data-ttu-id="b4be4-121">이러한 인수를 참조로 전달하면 (잠재적으로) 비용이 많이 드는 복사본을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-121">Passing those arguments by reference avoids the (potentially) expensive copy.</span></span> 

<span data-ttu-id="b4be4-122">호출 사이트의 인수에 `in`을 지정하는 것은 일반적으로 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-122">Specifying `in` for arguments at the call site is typically optional.</span></span> <span data-ttu-id="b4be4-123">값으로 인수를 전달하고 `in` 한정자를 사용하여 인수를 전달하는 것 사이에는 의미 체계상 차이가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-123">There is no semantic difference between passing arguments by value and passing them by reference using the `in` modifier.</span></span> <span data-ttu-id="b4be4-124">호출 사이트의 `in` 한정자는 인수 값이 변경될 수 있음을 나타내지 않아도 되므로 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-124">The `in` modifier at the call site is optional because you don't need to indicate that the argument's value might be changed.</span></span> <span data-ttu-id="b4be4-125">호출 사이트에서 `in` 한정자를 명시적으로 추가하여 인수가 값이 아닌 참조로 전달되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-125">You explicitly add the `in` modifier at the call site to ensure the argument is passed by reference, not by value.</span></span> <span data-ttu-id="b4be4-126">명시적으로 `in`을 사용하는 경우 다음과 같은 두 가지 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-126">Explicitly using `in` has the following two effects:</span></span>

<span data-ttu-id="b4be4-127">먼저 호출 사이트에서 `in`을 지정하면 컴파일러가 일치하는 `in` 매개 변수로 정의된 메서드를 선택하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-127">First, specifying `in` at the call site forces the compiler to select a method defined with a matching `in` parameter.</span></span> <span data-ttu-id="b4be4-128">그렇지 않으면 두 메서드가 `in`이 있을 때만 다른 경우 by 값 오버로드가 더 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-128">Otherwise, when two methods differ only in the presence of `in`, the by value overload is a better match.</span></span>

<span data-ttu-id="b4be4-129">둘째, `in`을 지정하면 참조로 인수를 전달할 의사가 있음을 선언하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-129">Second, specifying `in` declares your intent to pass an argument by reference.</span></span> <span data-ttu-id="b4be4-130">`in`에 사용된 인수는 직접 참조할 수 있는 위치를 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-130">The argument used with `in` must represent a location that can be directly referred to.</span></span> <span data-ttu-id="b4be4-131">`out` 및 `ref` 인수에는 동일한 일반 규칙이 적용됩니다. 상수, 일반 속성 또는 값을 생성하는 다른 식은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-131">The same general rules for `out` and `ref` arguments apply: You cannot use constants, ordinary properties, or other expressions that produce values.</span></span> <span data-ttu-id="b4be4-132">그렇지 않으면 호출 사이트에서 `in`을 생략할 경우 메서드에 대한 읽기 전용 참조로 전달할 임시 변수를 만들 수 있도록 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-132">Otherwise, omitting `in` at the call site informs the compiler that you will allow it to create a temporary variable to pass by read-only reference to the method.</span></span> <span data-ttu-id="b4be4-133">컴파일러는 `in` 인수를 사용하여 몇 가지 제한 사항을 해결하기 위해 임시 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-133">The compiler creates a temporary variable to overcome several restrictions with `in` arguments:</span></span>

- <span data-ttu-id="b4be4-134">임시 변수는 컴파일 시간 상수를 `in` 매개 변수로 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-134">A temporary variable allows compile-time constants as `in` parameters.</span></span>
- <span data-ttu-id="b4be4-135">임시 변수는 속성 또는 `in` 매개 변수에 대한 다른 식을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-135">A temporary variable allows properties, or other expressions for `in` parameters.</span></span>
- <span data-ttu-id="b4be4-136">임시 변수는 인수 형식에서 매개 변수 형식으로의 암시적 변환이 있는 경우 인수를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-136">A temporary variable allows arguments where there is an implicit conversion from the argument type to the parameter type.</span></span>

<span data-ttu-id="b4be4-137">앞의 모든 인스턴스에서 컴파일러는 상수, 속성 또는 다른 식의 값을 저장하는 임시 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-137">In all the preceding instances, the compiler creates a temporary variable that stores the value of the constant, property, or other expression.</span></span>

<span data-ttu-id="b4be4-138">다음 코드에서는 이러한 규칙을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-138">The following code illustrates these rules:</span></span>

```csharp
static void Method(in int argument)
{
    // implementation removed
}

Method(5); // OK, temporary variable created.
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // OK, temporary int created with the value 0
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // passed by readonly reference
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="b4be4-139">이제 by 값 인수를 사용하는 다른 메서드를 사용할 수 있다고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-139">Now, suppose another method using by value arguments was available.</span></span> <span data-ttu-id="b4be4-140">결과는 다음 코드와 같이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-140">The results change as shown in the following code:</span></span>

```csharp
static void Method(int argument)
{
    // implementation removed
}

static void Method(in int argument)
{
    // implementation removed
}

Method(5); // Calls overload passed by value
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // Calls overload passed by value.
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // Calls overload passed by value
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="b4be4-141">인수가 참조로 전달되는 유일한 메서드 호출이 마지막입니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-141">The only method call where the argument is passed by reference is the final one.</span></span>

> [!NOTE]
> <span data-ttu-id="b4be4-142">앞의 코드는 단순화를 위해 인수 형식으로 `int`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-142">The preceding code uses `int` as the argument type for simplicity.</span></span> <span data-ttu-id="b4be4-143">`int`는 대부분의 최신 컴퓨터에서 참조보다 크지 않기 때문에 단일 `int`를 읽기 전용 참조로 전달하면 아무런 이점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-143">Because `int` is no larger than a reference in most modern machines, there is no benefit to passing a single `int` as a readonly reference.</span></span> 

## <a name="limitations-on-in-parameters"></a><span data-ttu-id="b4be4-144">`in` 매개 변수에 대한 제한 사항</span><span class="sxs-lookup"><span data-stu-id="b4be4-144">Limitations on `in` parameters</span></span>

<span data-ttu-id="b4be4-145">다음과 같은 종류의 메서드에는 `in`, `ref` 및 `out` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4be4-145">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="b4be4-146">[async](async.md) 한정자를 사용하여 정의하는 비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="b4be4-146">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="b4be4-147">[yield return](yield.md) 또는 `yield break` 문을 포함하는 반복기 메서드</span><span class="sxs-lookup"><span data-stu-id="b4be4-147">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="b4be4-148">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="b4be4-148">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b4be4-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4be4-149">See Also</span></span>  
 [<span data-ttu-id="b4be4-150">C# 참조</span><span class="sxs-lookup"><span data-stu-id="b4be4-150">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="b4be4-151">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b4be4-151">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="b4be4-152">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="b4be4-152">C# Keywords</span></span>](index.md)  
 <span data-ttu-id="b4be4-153">[메서드 매개 변수](method-parameters.md) [값 형식과 참조 의미 체계](../../reference-semantics-with-value-types.md)</span><span class="sxs-lookup"><span data-stu-id="b4be4-153">[Method Parameters](method-parameters.md) [Reference Semantics with Value Types](../../reference-semantics-with-value-types.md)</span></span>
