---
title: "in 매개 변수 한정자(C# 참조)"
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 035aac3e6b902f607e533b709713eb1d07c9774a
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2018
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="a307b-102">in 매개 변수 한정자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a307b-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="a307b-103">`in` 키워드를 사용하면 참조를 통해 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a307b-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="a307b-104">`in` 인수는 호출된 메서드에서 수정될 수 없는 반면 `ref` 인수는 수정될 수 있다는 것을 제외하고 [ref](ref.md) 또는 [out](out-parameter-modifier.md) 키워드와 같습니다. `out` 인수는 호출자에서 수정되어야 하며 해당 수정 사항은 호출 컨텍스트에서 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a307b-104">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method, whereas `ref` arguments may be modified,  `out` arguments must be modified by the caller, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="a307b-105">위 예제는 `in` 한정자가 호출 사이트에서 필요하지 않다는 것을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a307b-105">The preceding example demonstrates that the `in` modifier is unnecessary at the call site.</span></span> <span data-ttu-id="a307b-106">메서드 선언에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a307b-106">It is only required in the method declaration.</span></span>

> [!NOTE] 
> <span data-ttu-id="a307b-107">`in` 키워드는 `foreach` 명령문의 일부 또는 LINQ 쿼리에서 `join` 절의 일부로 형식 매개 변수가 반공변(contravariant)임을 지정하도록 제네릭 형식 매개 변수와 함께 사용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a307b-107">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="a307b-108">이러한 컨텍스트에서 `in` 키워드의 사용에 대한 자세한 내용은 모든 해당 사용에 대한 링크를 제공하는 [in](in.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a307b-108">For more information on the use of the `in` keyword in these contexts, see [in](in.md) which provides links to all those uses.</span></span>
  
 <span data-ttu-id="a307b-109">`in` 인수로 전달되는 변수는 메서드 호출에서 전달되기 전에 초기화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a307b-109">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="a307b-110">그러나 호출된 메서드는 값을 할당하거나 인수를 수정하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a307b-110">However, the called method may not assign a value or modify the argument.</span></span>  
  
 <span data-ttu-id="a307b-111">`in`, `ref` 및 `out` 키워드는 서로 다른 런타임 동작을 수행하지만 컴파일 시간에 메서드 시그니처의 일부로 간주되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a307b-111">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="a307b-112">따라서 메서드 하나는 `ref` 또는 `in` 인수를 사용하고 다른 하나는 `out` 인수를 사용한다는 것 외에는 차이점이 없으면 메서드를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a307b-112">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="a307b-113">예를 들어 다음 코드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a307b-113">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="a307b-114">`in`의 존재 여부에 따른 오버로드는 허용되지만 컴파일러 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a307b-114">Overloading based on the presence of `in` is allowed, but generates a compiler warning:</span></span>  
  
```csharp
class InOverloads
{
    // Discouraged. Calling SampleMethod(value) is ambiguous.
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

<span data-ttu-id="a307b-115">속성 또는 상수는 호출 메서드가 해당 값을 수정할 수 없으므로 `in` 매개 변수로 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a307b-115">Properties or constants may be passed as `in` parameters, because the calling method may not modify their values.</span></span>
  
<span data-ttu-id="a307b-116">다음과 같은 종류의 메서드에는 `in`, `ref` 및 `out` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a307b-116">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="a307b-117">[async](../../../csharp/language-reference/keywords/async.md) 한정자를 사용하여 정의하는 비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="a307b-117">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
- <span data-ttu-id="a307b-118">[yield return](../../../csharp/language-reference/keywords/yield.md) 또는 `yield break` 문을 포함하는 반복기 메서드</span><span class="sxs-lookup"><span data-stu-id="a307b-118">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

<span data-ttu-id="a307b-119">일반적으로 값으로 인수 전달에 필요한 복사 작업을 방지하도록 `in` 인수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="a307b-119">You typically declare `in` arguments to avoid the copy operations necessary for passing arguments by value.</span></span> <span data-ttu-id="a307b-120">인수가 구조체 또는 구조체의 배열인 경우 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a307b-120">This is most useful when arguments are structures or arrays of structures.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a307b-121">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="a307b-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a307b-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a307b-122">See Also</span></span>  
 [<span data-ttu-id="a307b-123">C# 참조</span><span class="sxs-lookup"><span data-stu-id="a307b-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a307b-124">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a307b-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a307b-125">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="a307b-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="a307b-126">메서드 매개 변수</span><span class="sxs-lookup"><span data-stu-id="a307b-126">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
