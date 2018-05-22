---
title: C# 7.0의 새로운 기능 - C# 가이드
description: C# 언어의 새 버전 7에서 제공되는 새로운 기능을 간단히 살펴봅니다.
ms.date: 12/21/2016
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: a78b30411d734d6dadc52b7dbd402763d4eb7f5e
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
---
# <a name="whats-new-in-c-70"></a><span data-ttu-id="0cf77-103">C# 7.0의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="0cf77-103">What's new in C# 7.0</span></span>

<span data-ttu-id="0cf77-104">C# 7.0에서는 C# 언어에 많은 새로운 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-104">C# 7.0 adds a number of new features to the C# language:</span></span>
* [<span data-ttu-id="0cf77-105">`out` 변수</span><span class="sxs-lookup"><span data-stu-id="0cf77-105">`out` variables</span></span>](#out-variables)
    - <span data-ttu-id="0cf77-106">`out` 값을 사용되는 메서드에 대한 인수로 인라인으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-106">You can declare `out` values inline as arguments to the method where they are used.</span></span>
* [<span data-ttu-id="0cf77-107">튜플</span><span class="sxs-lookup"><span data-stu-id="0cf77-107">Tuples</span></span>](#tuples)
    - <span data-ttu-id="0cf77-108">여러 public 필드가 포함된 간단한 명명되지 않은 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-108">You can create lightweight, unnamed types that contain multiple public fields.</span></span> <span data-ttu-id="0cf77-109">컴파일러 및 IDE 도구는 이러한 형식의 의미 체계를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-109">Compilers and IDE tools understand the semantics of these types.</span></span>
* [<span data-ttu-id="0cf77-110">삭제</span><span class="sxs-lookup"><span data-stu-id="0cf77-110">Discards</span></span>](#discards)
    - <span data-ttu-id="0cf77-111">삭제는 할당된 값에 신경 쓰지 않을 때 할당에서 사용되는 임시 쓰기 전용 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-111">Discards are temporary, write-only variables used in assignments when you don't care about the value assigned.</span></span> <span data-ttu-id="0cf77-112">매개 변수는 `out` 매개 변수를 사용하여 메서드를 호출할 때뿐만 아니라 튜플 및 사용자 정의 형식을 분해할 때 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-112">They are particularly useful when deconstructing tuples and user-defined types, as well as when calling methods with `out` parameters.</span></span>
* [<span data-ttu-id="0cf77-113">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="0cf77-113">Pattern Matching</span></span>](#pattern-matching)
    - <span data-ttu-id="0cf77-114">임의 형식 및 해당 형식의 멤버 값에 따라 분기 논리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-114">You can create branching logic based on arbitrary types and values of the members of those types.</span></span>
* [<span data-ttu-id="0cf77-115">`ref` local 및 return</span><span class="sxs-lookup"><span data-stu-id="0cf77-115">`ref` locals and returns</span></span>](#ref-locals-and-returns)
    - <span data-ttu-id="0cf77-116">메서드 인수와 지역 변수는 다른 저장소에 대한 참조일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-116">Method arguments and local variables can be references to other storage.</span></span>
* [<span data-ttu-id="0cf77-117">로컬 함수</span><span class="sxs-lookup"><span data-stu-id="0cf77-117">Local Functions</span></span>](#local-functions)
    - <span data-ttu-id="0cf77-118">함수를 다른 함수 내부에 중첩하여 범위와 표시 여부를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-118">You can nest functions inside other functions to limit their scope and visibility.</span></span>
* [<span data-ttu-id="0cf77-119">추가 식 본문 멤버</span><span class="sxs-lookup"><span data-stu-id="0cf77-119">More expression-bodied members</span></span>](#more-expression-bodied-members)
    - <span data-ttu-id="0cf77-120">식을 사용하여 작성할 수 있는 멤버 목록이 증가했습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-120">The list of members that can be authored using expressions has grown.</span></span>
* [<span data-ttu-id="0cf77-121">`throw` 식</span><span class="sxs-lookup"><span data-stu-id="0cf77-121">`throw` Expressions</span></span>](#throw-expressions)
    - <span data-ttu-id="0cf77-122">`throw` 문이었기 때문에 이전에 허용되지 않은 코드 구문에서 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-122">You can throw exceptions in code constructs that previously were not allowed because `throw` was a statement.</span></span> 
* [<span data-ttu-id="0cf77-123">일반화된 비동기 반환 형식</span><span class="sxs-lookup"><span data-stu-id="0cf77-123">Generalized async return types</span></span>](#generalized-async-return-types)
    - <span data-ttu-id="0cf77-124">`async` 한정자를 사용하여 선언된 메서드는 `Task` 및 `Task<T>` 외에 다른 형식을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-124">Methods declared with the `async` modifier can return other types in addition to `Task` and `Task<T>`.</span></span>
* [<span data-ttu-id="0cf77-125">숫자 리터럴 구문 개선 사항</span><span class="sxs-lookup"><span data-stu-id="0cf77-125">Numeric literal syntax improvements</span></span>](#numeric-literal-syntax-improvements)
    - <span data-ttu-id="0cf77-126">새로운 토큰으로 숫자 상수의 가독성이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-126">New tokens improve readability for numeric constants.</span></span>

<span data-ttu-id="0cf77-127">이 항목의 나머지 부분에서는 각 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-127">The remainder of this topic discusses each of the features.</span></span> <span data-ttu-id="0cf77-128">각 기능의 배경과 원리를 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-128">For each feature, you'll learn the reasoning behind it.</span></span> <span data-ttu-id="0cf77-129">구문을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-129">You'll learn the syntax.</span></span> <span data-ttu-id="0cf77-130">새로운 기능을 사용하여 개발자로서 생산성을 높일 수 있는 몇 가지 샘플 시나리오를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-130">You'll see some sample scenarios where using the new feature will make you more productive as a developer.</span></span> 

## <a name="out-variables"></a><span data-ttu-id="0cf77-131">`out` 변수</span><span class="sxs-lookup"><span data-stu-id="0cf77-131">`out` variables</span></span>

<span data-ttu-id="0cf77-132">`out` 매개 변수를 지원하는 기존 구문이 이 버전에서 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-132">The existing syntax that supports `out` parameters has been improved in this version.</span></span>  

<span data-ttu-id="0cf77-133">이전에는 out 변수의 선언과 초기화를 두 개의 다른 문으로 구분해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-133">Previously, you would need to separate the declaration of the out variable and its initialization into two different statements:</span></span>

[!code-csharp[OutVariableOldStyle](../../../samples/snippets/csharp/new-in-7/program.cs#03_OutVariableOldStyle "classic out variable declaration")]

<span data-ttu-id="0cf77-134">이제 개별 선언 문을 작성하는 대신 메서드 호출의 인수 목록에서 `out` 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-134">You can now declare `out` variables in the argument list of a method call, rather than writing a separate declaration statement:</span></span>

[!code-csharp[OutVariableDeclarations](../../../samples/snippets/csharp/new-in-7/program.cs#01_OutVariableDeclarations "Out variable declarations")]

<span data-ttu-id="0cf77-135">위에 나와 있는 대로 쉽게 구별할 수 있도록 `out` 변수의 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-135">You may want to specify the type of the `out` variable for clarity, as shown above.</span></span> <span data-ttu-id="0cf77-136">그러나 이 언어는 암시적 형식 지역 변수를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-136">However, the language does support using an implicitly typed local variable:</span></span>

[!code-csharp[OutVarVariableDeclarations](../../../samples/snippets/csharp/new-in-7/program.cs#02_OutVarVariableDeclarations "Implicitly typed Out variable")]

* <span data-ttu-id="0cf77-137">코드를 읽기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-137">The code is easier to read.</span></span> 
    - <span data-ttu-id="0cf77-138">위의 다른 줄이 아니라 사용하는 위치에서 out 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-138">You declare the out variable where you use it, not on another line above.</span></span>
* <span data-ttu-id="0cf77-139">초기 값을 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-139">No need to assign an initial value.</span></span>
    - <span data-ttu-id="0cf77-140">메서드 호출에서 사용되는 위치에 `out` 변수를 선언하면 변수가 선언되기 전에 실수로 사용할 가능성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-140">By declaring the `out` variable where it is used in a method call, you can't accidentally use it before it is assigned.</span></span>

<span data-ttu-id="0cf77-141">이 기능은 `Try` 패턴에 가장 일반적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-141">The most common use for this feature will be the `Try` pattern.</span></span> <span data-ttu-id="0cf77-142">이 패턴에서 메서드는 성공 또는 실패를 나타내는 `bool` 및 메서드가 성공할 경우 결과를 제공하는 `out` 변수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-142">In this pattern, a method returns a `bool` indicating success or failure and an `out` variable that provides the result if the method succeeds.</span></span>

<span data-ttu-id="0cf77-143">`out` 변수 선언을 사용할 경우 선언된 변수가 if 문의 외부 범위로 "누수"됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-143">When using the `out` variable declaration, the declared variable "leaks" into the outer scope of the if statement.</span></span> <span data-ttu-id="0cf77-144">따라서 이후에도 해당 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-144">This allows you to use the variable afterwards:</span></span>

```csharp
if (!int.TryParse(input, out int result))
{    
    return null;
}

return result;
```

## <a name="tuples"></a><span data-ttu-id="0cf77-145">튜플</span><span class="sxs-lookup"><span data-stu-id="0cf77-145">Tuples</span></span>

> [!NOTE]
> <span data-ttu-id="0cf77-146">새 튜플 기능을 사용하려면 <xref:System.ValueTuple> 형식이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-146">The new tuples features require the <xref:System.ValueTuple> types.</span></span>
> <span data-ttu-id="0cf77-147">형식을 포함하지 않는 플랫폼에서 사용하려면 NuGet 패키지 [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/)을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-147">You must add the NuGet package [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) in order to use it on platforms that do not include the types.</span></span>
>
> <span data-ttu-id="0cf77-148">이는 프레임워크에서 제공되는 형식을 사용하는 다른 언어 기능과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-148">This is similar to other language features that rely on types delivered in the framework.</span></span> <span data-ttu-id="0cf77-149">예를 들어 `async` 및 `await`는 `INotifyCompletion` 인터페이스를 사용하고 LINQ는 `IEnumerable<T>`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-149">Example include `async` and `await` relying on the `INotifyCompletion` interface, and LINQ relying on `IEnumerable<T>`.</span></span> <span data-ttu-id="0cf77-150">그러나 .NET이 점점 더 플랫폼 독립적으로 되면서 배달 메커니즘도 변하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-150">However, the delivery mechanism is changing as .NET is becoming more platform independent.</span></span> <span data-ttu-id="0cf77-151">.NET Framework가 언어 컴파일러와 동일한 주기로 제공되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-151">The .NET Framework may not always ship on the same cadence as the language compiler.</span></span> <span data-ttu-id="0cf77-152">새로운 언어 기능이 새 형식을 사용하는 경우 해당 형식은 언어 기능이 제공될 때 NuGet 패키지로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-152">When new language features rely on new types, those types will be available as NuGet packages when the language features ship.</span></span> <span data-ttu-id="0cf77-153">이러한 새로운 형식이 .NET Standard API에 추가되고 프레임워크의 일부로 제공되면, NuGet 패키지 요구 사항이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-153">As these new types get added to the .NET Standard API and delivered as part of the framework, the NuGet package requirement will be removed.</span></span>

<span data-ttu-id="0cf77-154">C#에서는 디자인 의도를 설명하는 데 사용되는 클래스 및 구조체에 대한 다양한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-154">C# provides a rich syntax for classes and structs that is used to explain your design intent.</span></span> <span data-ttu-id="0cf77-155">하지만 다양한 구문에는 이점이 거의 없는데 추가 작업이 필요한 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-155">But sometimes that rich syntax requires extra work with minimal benefit.</span></span> <span data-ttu-id="0cf77-156">일반적으로 두 개 이상의 데이터 요소가 포함된 간단한 구조체가 필요한 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-156">You may often write methods that need a simple structure containing more than one data element.</span></span> <span data-ttu-id="0cf77-157">이러한 시나리오를 지원하기 위해 *튜플*이 C#에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-157">To support these scenarios *tuples* were added to C#.</span></span> <span data-ttu-id="0cf77-158">튜플은 데이터 멤버를 나타내는 여러 필드가 포함된 간단한 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-158">Tuples are lightweight data structures that contain multiple fields to represent the data members.</span></span>
<span data-ttu-id="0cf77-159">필드는 유효성이 검사되지 않고 자체 메서드를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-159">The fields are not validated, and you cannot define your own methods</span></span>

> [!NOTE]
> <span data-ttu-id="0cf77-160">튜플은 C# 7.0 이전부터 사용할 수 있었지만 비효율적이었고 언어 지원이 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-160">Tuples were available before C# 7.0, but they were inefficient and had no language support.</span></span>
> <span data-ttu-id="0cf77-161">즉, 튜플 요소는 `Item1`, `Item2` 등으로만 참조될 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-161">This meant that tuple elements could only be referenced as `Item1`, `Item2` and so on.</span></span> <span data-ttu-id="0cf77-162">C# 7.0은 새롭고 보다 효율적인 튜플 유형을 사용하여 튜플의 필드에 대해 의미론적 이름을 사용할 수 있는 튜플에 대한 언어 지원을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-162">C# 7.0 introduces language support for tuples, which enables semantic names for the fields of a tuple using new, more efficient tuple types.</span></span>

<span data-ttu-id="0cf77-163">각 멤버에 값을 할당하여 튜플을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-163">You can create a tuple by assigning a value to each member:</span></span>

[!code-csharp[UnnamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#04_UnnamedTuple "Unnamed tuple")]

<span data-ttu-id="0cf77-164">이 할당은 멤버가 `Item1` 및 `Item2`이고 <xref:System.Tuple>과 동일한 방식으로 사용할 수 있는 튜플을 생성합니다. 구문을 변경하여 의미론적 이름을 튜플의 각 멤버에 제공하는 튜플을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-164">That assignment creates a tuple whose members are `Item1` and `Item2`, which you can use in the same way as <xref:System.Tuple> You can change the syntax to create a tuple that provides semantic names to each of the members of the tuple:</span></span>

[!code-csharp[NamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#05_NamedTuple "Named tuple")]

<span data-ttu-id="0cf77-165">`namedLetters` 튜플에는 `Alpha` 및 `Beta`라는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-165">The `namedLetters` tuple contains fields referred to as `Alpha` and `Beta`.</span></span> <span data-ttu-id="0cf77-166">이러한 이름은 컴파일 시간에만 존재하며 런타임 시 반영을 통해 튜플을 검사하는 경우 등을 위해 보존되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-166">Those names exist only at compile time and are not preserved for example when inspecting the tuple using reflection at runtime.</span></span>

<span data-ttu-id="0cf77-167">튜플 할당에서 할당의 오른쪽에 필드의 이름을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-167">In a tuple assignment, you can also specify the names of the fields on the right-hand side of the assignment:</span></span>

[!code-csharp[ImplicitNamedTuple](../../../samples/snippets/csharp/new-in-7/program.cs#06_ImplicitNamedTuple "Implicitly named tuple")]

<span data-ttu-id="0cf77-168">할당의 왼쪽 및 오른쪽에서 모두 필드의 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-168">You can specify names for the fields on both the left and right-hand side of the assignment:</span></span>

[!code-csharp[NamedTupleConflict](../../../samples/snippets/csharp/new-in-7/program.cs#07_NamedTupleConflict "Named tuple conflict")]

<span data-ttu-id="0cf77-169">위 줄에서는 할당의 오른쪽에 있는 이름 `Alpha` 및 `Beta`가 왼쪽에 있는 이름 `First` 및 `Second`와 충돌하기 때문에 무시됨을 알리는 경고 `CS8123`을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-169">The line above generates a warning, `CS8123`, telling you that the names on the right side of the assignment, `Alpha` and `Beta` are ignored because they conflict with the names on the left side, `First` and `Second`.</span></span>

<span data-ttu-id="0cf77-170">위 예제에서는 튜플을 선언하는 기본 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-170">The examples above show the basic syntax to declare tuples.</span></span> <span data-ttu-id="0cf77-171">튜플은 `private` 및 `internal` 메서드의 반환 형식으로 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-171">Tuples are most useful as return types for `private` and `internal` methods.</span></span> <span data-ttu-id="0cf77-172">튜플은 여러 개별 값을 반환하기 위한 해당 메서드에 대한 간단한 구문을 제공합니다. 반환되는 형식을 정의하는 `class` 또는 `struct`를 작성하는 작업을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-172">Tuples provide a simple syntax for those methods to return multiple discrete values: You save the work of authoring a `class` or a `struct` that defines the type returned.</span></span> <span data-ttu-id="0cf77-173">새 형식을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-173">There is no need for creating a new type.</span></span>

<span data-ttu-id="0cf77-174">튜플을 만드는 것이 더 효율적이고 더 생산적입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-174">Creating a tuple is more efficient and more productive.</span></span>
<span data-ttu-id="0cf77-175">두 개 이상의 값을 전달하는 데이터 구조를 정의하는 것이 더 간단한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-175">It is a simpler, lightweight syntax to define a data structure that carries more than one value.</span></span> <span data-ttu-id="0cf77-176">아래 예제 메서드는 정수 시퀀스에서 발견된 최소값 및 최대값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-176">The example method below returns the minimum and maximum values found in a sequence of integers:</span></span>

[!code-csharp[TupleReturningMethod](../../../samples/snippets/csharp/new-in-7/program.cs#08_TupleReturningMethod "Tuple returning method")]

<span data-ttu-id="0cf77-177">이 방법으로 튜플을 사용하는 것에는 몇 가지 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-177">Using tuples in this way offers several advantages:</span></span>

* <span data-ttu-id="0cf77-178">반환되는 형식을 정의하는 `class` 또는 `struct`를 작성하는 작업을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-178">You save the work of authoring a `class` or a `struct` that defines the type returned.</span></span> 
* <span data-ttu-id="0cf77-179">새 형식을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-179">You do not need to create new type.</span></span>
* <span data-ttu-id="0cf77-180">언어가 향상되어 <xref:System.Tuple.Create``1(``0)> 메서드를 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-180">The language enhancements removes the need to call the <xref:System.Tuple.Create``1(``0)> methods.</span></span>

<span data-ttu-id="0cf77-181">메서드 선언은 반환되는 튜플의 필드 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-181">The declaration for the method provides the names for the fields of the tuple that is returned.</span></span> <span data-ttu-id="0cf77-182">메서드를 호출할 경우 반환 값은 필드가 `Max` 및 `Min`인 튜플입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-182">When you call the method, the return value is a tuple whose fields are `Max` and `Min`:</span></span>

[!code-csharp[CallingTupleMethod](../../../samples/snippets/csharp/new-in-7/program.cs#09_CallingTupleMethod "Calling a tuple returning method")]

<span data-ttu-id="0cf77-183">메서드에서 반환된 튜플의 멤버를 패키지 해제하려는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-183">There may be times when you want to unpackage the members of a tuple that were returned from a method.</span></span>  <span data-ttu-id="0cf77-184">이 작업을 수행하려면 튜플에서 각 값에 대한 개별 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-184">You can do that by declaring separate variables for each of the values in the tuple.</span></span> <span data-ttu-id="0cf77-185">이 작업을 튜플 *분해*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-185">This is called *deconstructing* the tuple:</span></span>

[!code-csharp[CallingWithDeconstructor](../../../samples/snippets/csharp/new-in-7/program.cs#10_CallingWithDeconstructor "Deconstructing a tuple")]

<span data-ttu-id="0cf77-186">.NET에 있는 형식에 대한 비슷한 분해를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-186">You can also provide a similar deconstruction for any type in .NET.</span></span> <span data-ttu-id="0cf77-187">이 작업을 수행하려면 `Deconstruct` 메서드를 클래스의 멤버로 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-187">This is done by writing a `Deconstruct` method as a member of the class.</span></span> <span data-ttu-id="0cf77-188">해당 `Deconstruct` 메서드는 추출하려는 각 속성에 대한 `out` 인수 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-188">That `Deconstruct` method provides a set of `out` arguments for each of the properties you want to extract.</span></span> <span data-ttu-id="0cf77-189">`X` 및 `Y` 좌표를 추출하는 분해자 메서드를 제공하는 이 `Point` 클래스를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-189">Consider this `Point` class that provides a deconstructor method that extracts the `X` and `Y` coordinates:</span></span>

[!code-csharp[PointWithDeconstruction](../../../samples/snippets/csharp/new-in-7/point.cs#11_PointWithDeconstruction "Point with deconstruction method")]
 
<span data-ttu-id="0cf77-190">튜플에 `Point`을 할당하여 개별 필드를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-190">You can extract the individual fields by assigning a `Point` to a tuple:</span></span>

[!code-csharp[DeconstructPoint](../../../samples/snippets/csharp/new-in-7/program.cs#12_DeconstructPoint "Deconstruct a point")]

<span data-ttu-id="0cf77-191">`Deconstruct` 메서드에 정의된 아름으로 바인딩되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-191">You are not bound by the names defined in the `Deconstruct` method.</span></span> <span data-ttu-id="0cf77-192">할당의 일부로 추출 변수의 이름을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-192">You can rename the extract variables as part of the assignment:</span></span>  

[!code-csharp[DeconstructNames](../../../samples/snippets/csharp/new-in-7/program.cs#13_DeconstructNames "Deconstruct with new names")]

<span data-ttu-id="0cf77-193">[튜플 항목](../tuples.md)에서 튜플에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-193">You can learn more in depth about tuples in the [tuples topic](../tuples.md).</span></span>

## <a name="discards"></a><span data-ttu-id="0cf77-194">버림</span><span class="sxs-lookup"><span data-stu-id="0cf77-194">Discards</span></span>

<span data-ttu-id="0cf77-195">종종 튜플을 분해하거나 `out` 매개 변수로 메서드를 호출할 때 값을 신경 쓰지 않고 사용하지 않을 변수를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-195">Often when deconstructing a tuple or calling a method with `out` parameters, you're forced to define a variable whose value you don't care about and don't intend to use.</span></span> <span data-ttu-id="0cf77-196">C#은 *버림*에 대한 지원을 추가하여 이 시나리오를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-196">C# adds support for *discards* to handle this scenario.</span></span> <span data-ttu-id="0cf77-197">무시는 이름이 `_`(밑줄 문자)인 쓰기 전용 변수입니다. 단일 변수에 버리려는 모든 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-197">A discard is a write-only variable whose name is `_` (the underscore character); you can assign all of the values that you intend to discard to the single variable.</span></span> <span data-ttu-id="0cf77-198">버림은 할당 문과 별도로 분리되는 할당되지 않은 변수와 같습니다. 코드에서 버림을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-198">A discard is like an unassigned variable; apart from the assignment statement, the discard can't be used in code.</span></span>

<span data-ttu-id="0cf77-199">다음 시나리오에서는 버림이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-199">Discards are supported in the following scenarios:</span></span>

* <span data-ttu-id="0cf77-200">튜플이나 사용자 정의 형식을 분해할 때.</span><span class="sxs-lookup"><span data-stu-id="0cf77-200">When deconstructing tuples or user-defined types.</span></span>

* <span data-ttu-id="0cf77-201">[out](../language-reference/keywords/out-parameter-modifier.md) 매개 변수로 메서드를 호출할 때.</span><span class="sxs-lookup"><span data-stu-id="0cf77-201">When calling methods with [out](../language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>

* <span data-ttu-id="0cf77-202">[is](../language-reference/keywords/is.md) 및 [switch](../language-reference/keywords/switch.md) 문을 사용한 패턴 일치 작업에서.</span><span class="sxs-lookup"><span data-stu-id="0cf77-202">In a pattern matching operation with the [is](../language-reference/keywords/is.md) and [switch](../language-reference/keywords/switch.md) statements.</span></span>

* <span data-ttu-id="0cf77-203">할당 값을 버림으로 명시적으로 지정할 때 독립 실행형 식별자인 경우.</span><span class="sxs-lookup"><span data-stu-id="0cf77-203">As a standalone identifier when you want to explicitly identify the value of an assignment as a discard.</span></span>

<span data-ttu-id="0cf77-204">다음 예제는 서로 다른 2년 동안 도시에 대한 데이터를 포함한 6 튜플을 반환하는 `QueryCityDataForYears` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-204">The following example defines a `QueryCityDataForYears` method that returns a 6-tuple that contains a data for a city for two different years.</span></span> <span data-ttu-id="0cf77-205">예제의 메서드 호출은 메서드에 의해 반환된 두 개의 채우기 값에만 관련되어 있으므로 튜플을 해체할 때 튜플의 나머지 값을 버림으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-205">The method call in the example is concerned only with the two population values returned by the method and so treats the remaining values in the tuple as discards when it deconstructs the tuple.</span></span>

[!code-csharp[Tuple-discard](../../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

<span data-ttu-id="0cf77-206">자세한 내용은 [버림](../discards.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0cf77-206">For more information, see [Discards](../discards.md).</span></span>
 
## <a name="pattern-matching"></a><span data-ttu-id="0cf77-207">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="0cf77-207">Pattern matching</span></span>

<span data-ttu-id="0cf77-208">*패턴 일치*는 개체 형식이 아닌 속성에 대한 메서드 디스패치를 구현할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-208">*Pattern matching* is a feature that allows you to implement method dispatch on properties other than the type of an object.</span></span> <span data-ttu-id="0cf77-209">개체 형식에 따른 메서드 디스패치에 이미 익숙할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-209">You're probably already familiar with method dispatch based on the type of an object.</span></span> <span data-ttu-id="0cf77-210">개체 지향 프로그래밍에서 가상 및 재정의 메서드는 개체 형식에 따라 메서드 디스패치를 구현하기 위한 언어 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-210">In Object Oriented programming, virtual and override methods provide language syntax to implement method dispatching based on an object's type.</span></span> <span data-ttu-id="0cf77-211">기본 및 파생 클래스는 서로 다른 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-211">Base and Derived classes provide different implementations.</span></span> <span data-ttu-id="0cf77-212">패턴 일치 식은 상속 계층 구조를 통해 관련되지 않은 형식 및 데이터 요소에 대한 비슷한 디스패치 패턴을 쉽게 구현할 수 있도록 이 개념을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-212">Pattern matching expressions extend this concept so that you can easily implement similar dispatch patterns for types and data elements that are not related through an inheritance hierarchy.</span></span> 

<span data-ttu-id="0cf77-213">패턴 일치는 `is` 식과 `switch` 식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-213">Pattern matching supports `is` expressions and `switch` expressions.</span></span> <span data-ttu-id="0cf77-214">각 식을 통해 개체 및 관련 속성을 검사하여 해당 개체가 검색된 패턴을 충족하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-214">Each enables inspecting an object and its properties to determine if that object satisfies the sought pattern.</span></span> <span data-ttu-id="0cf77-215">`when` 키워드를 사용하여 패턴에 대한 추가 규칙을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-215">You use the `when` keyword to specify additional rules to the pattern.</span></span>

### <a name="is-expression"></a><span data-ttu-id="0cf77-216">`is` 식</span><span class="sxs-lookup"><span data-stu-id="0cf77-216">`is` expression</span></span>

<span data-ttu-id="0cf77-217">`is` 패턴 식은 친숙한 `is` 연산자를 확장하여 형식을 넘어서서 개체를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-217">The `is` pattern expression extends the familiar `is` operator to query an object beyond its type.</span></span>

<span data-ttu-id="0cf77-218">먼저 간단한 시나리오를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-218">Let's start with a simple scenario.</span></span> <span data-ttu-id="0cf77-219">패턴 일치 식을 통해 관련되지 않은 형식을 사용하는 알고리즘을 단순화하는 기능을 이 시나리오에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-219">We'll add capabilities to this scenario that demonstrate how pattern matching expressions make algorithms that work with unrelated types easy.</span></span> <span data-ttu-id="0cf77-220">먼저 많은 주사위 굴리기의 합계를 계산하는 메서드를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-220">We'll start with a method that computes the sum of a number of die rolls:</span></span>

[!code-csharp[SumDieRolls](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#14_SumDieRolls "Sum die rolls")]

<span data-ttu-id="0cf77-221">여러 개의 주사위를 굴리는 경우 주사위 굴리기의 합계를 빠르게 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-221">You might quickly find that you need to find the sum of die rolls where some of the rolls are made with multiple dice (dice is the plural of die).</span></span> <span data-ttu-id="0cf77-222">입력 시퀀스의 일부는 단일 숫자가 아닌 여러 결과일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-222">Part of the input sequence may be multiple results instead of a single number:</span></span>

[!code-csharp[SumDieRollsWithGroups](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#15_SumDieRollsWithGroups "Sum die rolls with groups")]

<span data-ttu-id="0cf77-223">이 시나리오에서는 `is` 패턴 식이 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-223">The `is` pattern expression works quite well in this scenario.</span></span> <span data-ttu-id="0cf77-224">형식 검사의 일부로 변수 초기화를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-224">As part of checking the type, you write a variable initialization.</span></span> <span data-ttu-id="0cf77-225">이렇게 하면 유효성 검사된 런타임 형식의 새 변수가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-225">This creates a new variable of the validated runtime type.</span></span>

<span data-ttu-id="0cf77-226">이러한 시나리오를 계속 확장하면 더 많은 `if` 및 `else if` 문을 빌드한다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-226">As you keep extending these scenarios, you may find that you build more `if` and `else if` statements.</span></span> <span data-ttu-id="0cf77-227">구조가 너무 복잡해지면 `switch` 패턴 식으로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-227">Once that becomes unwieldy, you'll likely want to switch to `switch` pattern expressions.</span></span>

### <a name="switch-statement-updates"></a><span data-ttu-id="0cf77-228">`switch` 문 업데이트</span><span class="sxs-lookup"><span data-stu-id="0cf77-228">`switch` statement updates</span></span>

<span data-ttu-id="0cf77-229">*일치 식*에는 이미 C# 언어의 일부인 `switch` 문에 기반을 둔 친숙한 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-229">The *match expression* has a familiar syntax, based on the `switch` statement already part of the C# language.</span></span> <span data-ttu-id="0cf77-230">새 사례를 추가하기 전에 일치 식을 사용하도록 기존 코드를 변환해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-230">Let's translate the existing code to use a match expression before adding new cases:</span></span> 

[!code-csharp[SumUsingSwitch](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#16_SumUsingSwitch "Sum using switch")]

<span data-ttu-id="0cf77-231">일치 식에는 `case` 식의 시작 부분에 형식과 변수를 선언하는 `is` 식과 약간 다른 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-231">The match expressions have a slightly different syntax than the `is` expressions, where you declare the type and variable at the beginning of the `case` expression.</span></span>

<span data-ttu-id="0cf77-232">일치 식은 상수도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-232">The match expressions also support constants.</span></span> <span data-ttu-id="0cf77-233">이 방법에서는 간단한 사례를 제외하여 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-233">This can save time by factoring out simple cases:</span></span>

[!code-csharp[SwitchWithConstants](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#17_SwitchWithConstants "Switch with constants")]

<span data-ttu-id="0cf77-234">위의 코드는 `0`에 대한 사례를 `int`의 특수 사례로 추가하고 입력이 없는 경우 `null`을 특수 사례로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-234">The code above adds cases for `0` as a special case of `int`, and `null` as a special case when there is no input.</span></span> <span data-ttu-id="0cf77-235">이것은 스위치 패턴 식의 한 가지 중요한 새로운 기능을 보여 줍니다. 이제 `case` 식의 순서는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-235">This demonstrates one important new feature in switch pattern expressions: the order of the `case` expressions now matters.</span></span> <span data-ttu-id="0cf77-236">`0` 사례는 일반적인 `int` 사례 앞에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-236">The `0` case must appear before the general `int` case.</span></span> <span data-ttu-id="0cf77-237">그렇지 않으면 값이 `0`인 경우에도 일치시킬 첫 번째 패턴이 `int` 사례가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-237">Otherwise, the first pattern to match would be the `int` case, even when the value is `0`.</span></span> <span data-ttu-id="0cf77-238">일치 식의 순서를 잘못 지정하여 나중 사례가 이미 처리되었다면 컴파일러는 여기에 플래그를 지정하고 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-238">If you accidentally order match expressions such that a later case has already been handled, the compiler will flag that and generate an error.</span></span>

<span data-ttu-id="0cf77-239">이런 동일한 동작을 통해 빈 입력 시퀀스에 대한 특수 사례가 가능해집니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-239">This same behavior enables the special case for an empty input sequence.</span></span>
<span data-ttu-id="0cf77-240">요소가 포함된 `IEnumerable` 항목에 대한 사례가 일반적인 `IEnumerable` 사례 앞에 나타나야 함을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-240">You can see that the case for an `IEnumerable` item that has elements must appear before the general `IEnumerable` case.</span></span>

<span data-ttu-id="0cf77-241">이 버전에서는 `default` 사례를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-241">This version has also added a `default` case.</span></span> <span data-ttu-id="0cf77-242">`default` 사례는 소스에서 나타나는 순서에 관계없이 항상 마지막으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-242">The `default` case is always evaluated last, regardless of the order it appears in the source.</span></span> <span data-ttu-id="0cf77-243">이런 이유로 `default` 사례를 마지막에 배치하는 것이 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-243">For that reason, convention is to put the `default` case last.</span></span>

<span data-ttu-id="0cf77-244">마지막으로 새로운 주사위 스타일에 대한 하나의 마지막 `case`를 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-244">Finally, let's add one last `case` for a new style of die.</span></span> <span data-ttu-id="0cf77-245">일부 게임에서는 백분위수 주사위를 사용하여 더 큰 범위의 숫자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-245">Some games use percentile dice to represent larger ranges of numbers.</span></span> 

> [!NOTE]
> <span data-ttu-id="0cf77-246">두 개의 10면 백분위수 주사위는 0~99의 모든 숫자를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-246">Two 10-sided percentile dice can represent every number from 0 through 99.</span></span> <span data-ttu-id="0cf77-247">하나의 주사위에는 `00`, `10`, `20`, ... `90`이 표시된 면이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-247">One die has sides labelled `00`, `10`, `20`, ... `90`.</span></span> <span data-ttu-id="0cf77-248">다른 주사위에는 `0`, `1`, `2`, ... `9`가 표시된 면이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-248">The other die has sides labeled `0`, `1`, `2`, ... `9`.</span></span> <span data-ttu-id="0cf77-249">두 주사위 값을 더하면 0~99의 모든 숫자를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-249">Add the two die values together and you can get every number from 0 through 99.</span></span>

<span data-ttu-id="0cf77-250">이 유형의 주사위를 컬렉션에 추가하려면 먼저 백분위수 주사위를 나타내는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-250">To add this kind of die to your collection, first define a type to represent the percentile dice.</span></span> <span data-ttu-id="0cf77-251">`TensDigit` 속성은 `0`, `10`, `20`, 최대 `90` 값을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-251">The `TensDigit` property stores values `0`, `10`, `20`, up to `90`:</span></span>

[!code-csharp[18_PercentileDice](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#18_PercentileDice "Percentile Die type")]

<span data-ttu-id="0cf77-252">그런 다음 새 형식에 대한 `case` 일치 식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-252">Then, add a `case` match expression for the new type:</span></span>

[!code-csharp[SwitchWithNewTypes](../../../samples/snippets/csharp/new-in-7/patternmatch.cs#19_SwitchWithNewTypes "Include Percentile Die type")]

<span data-ttu-id="0cf77-253">패턴 일치 식에 대한 새로운 구문을 사용하면 분명하고 간결한 구문을 통해 개체 형식에 따른 디스패치 알고리즘 또는 기타 속성을 더 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-253">The new syntax for pattern matching expressions makes it easier to create dispatch algorithms based on an object's type, or other properties, using a clear and concise syntax.</span></span> <span data-ttu-id="0cf77-254">패턴 일치 식을 사용하면 상속이 관련되지 않은 데이터 형식에서 이러한 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-254">Pattern matching expressions enable these constructs on data types that are unrelated by inheritance.</span></span>

<span data-ttu-id="0cf77-255">패턴 일치에 대한 자세한 내용은 [C#의 패턴 일치](../pattern-matching.md)에 관련된 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0cf77-255">You can learn more about pattern matching in the topic dedicated to [pattern matching in C#](../pattern-matching.md).</span></span>

## <a name="ref-locals-and-returns"></a><span data-ttu-id="0cf77-256">Ref local 및 return</span><span class="sxs-lookup"><span data-stu-id="0cf77-256">Ref locals and returns</span></span>

<span data-ttu-id="0cf77-257">이 기능을 통해 다른 곳에 정의된 변수에 대한 참조를 사용 및 반환하는 알고리즘이 가능해집니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-257">This feature enables algorithms that use and return references to variables defined elsewhere.</span></span> <span data-ttu-id="0cf77-258">한 가지 예는 큰 매트릭스를 사용하고 특정 특징을 가진 하나의 위치를 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-258">One example is working with large matrices, and finding a single location with certain characteristics.</span></span> <span data-ttu-id="0cf77-259">하나의 메서드가 매트릭스에 있는 하나의 위치에 대한 두 개의 인덱스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-259">One method would return the two indices for a single location in the matrix:</span></span>

[!code-csharp[FindReturningIndices](../../../samples/snippets/csharp/new-in-7/MatrixSearch.cs#20_FindReturningIndices "Find returning indices")]

<span data-ttu-id="0cf77-260">이 코드에는 많은 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-260">There are many issues with this code.</span></span> <span data-ttu-id="0cf77-261">무엇보다 이 코드는 튜플을 반환하는 public 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-261">First of all, it's a public method that's returning a tuple.</span></span> <span data-ttu-id="0cf77-262">언어에서는 이 코드를 지원하지만 public API의 경우 사용자 지정 형식(클래스 또는 구조체)이 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-262">The language supports this, but user defined types (either classes or structs) are preferred for public APIs.</span></span>

<span data-ttu-id="0cf77-263">두 번째로, 이 메서드는 매트릭스의 항목으로 인덱스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-263">Second, this method is returning the indices to the item in the matrix.</span></span>
<span data-ttu-id="0cf77-264">이에 따라 호출자는 해당 인덱스를 사용하여 매트릭을 역참조하고 단일 요소를 수정하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-264">That leads callers to write code that uses those indices to dereference the matrix and modify a single element:</span></span>

[!code-csharp[UpdateItemFromIndices](../../../samples/snippets/csharp/new-in-7/program.cs#21_UpdateItemFromIndices "Update Item From Indices")]

<span data-ttu-id="0cf77-265">변경할 매트릭스의 요소에 대한 *참조*를 반환하는 메서드를 작성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-265">You'd rather write a method that returns a *reference* to the element of the matrix that you want to change.</span></span> <span data-ttu-id="0cf77-266">이 작업을 수행하려면 안전하지 않은 코드를 사용하고 이전 버전의 `int`로 포인터를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-266">You could only accomplish this by using unsafe code and returning a pointer to an `int` in previous versions.</span></span>

<span data-ttu-id="0cf77-267">ref local 기능을 보여 주고 내부 저장소에 대한 참조를 반환하는 메서드를 만드는 방법을 보여 주는 일련의 변경을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-267">Let's walk through a series of changes to demonstrate the ref local feature and show how to create a method that returns a reference to internal storage.</span></span>
<span data-ttu-id="0cf77-268">계속해서 실수로 잘못 사용하는 경우를 방지하는 ref return 및 ref local 기능의 규칙을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-268">Along the way, you'll learn the rules of the ref return and ref local feature that protects you from accidentally misusing it.</span></span>

<span data-ttu-id="0cf77-269">먼저 튜플 대신 `ref int`를 반환하도록 `Find` 메서드 선언을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-269">Start by modifying the `Find` method declaration so that it returns a `ref int` instead of a tuple.</span></span> <span data-ttu-id="0cf77-270">그런 다음 두 개의 인덱스 대신 매트릭스에 저장된 값을 반환하도록 return 문을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-270">Then, modify the return statement so it returns the value stored in the matrix instead of the two indices:</span></span>

```csharp
// Note that this won't compile. 
// Method declaration indicates ref return,
// but return statement specifies a value return.
public static ref int Find2(int[,] matrix, Func<int, bool> predicate)
{
    for (int i = 0; i < matrix.GetLength(0); i++)
        for (int j = 0; j < matrix.GetLength(1); j++)
            if (predicate(matrix[i, j]))
                return matrix[i, j];
    throw new InvalidOperationException("Not found");
}
```

<span data-ttu-id="0cf77-271">메서드가 `ref` 변수를 반환하도록 선언할 경우 각 return 문에 `ref` 키워드도 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-271">When you declare that a method returns a `ref` variable, you must also add the `ref` keyword to each return statement.</span></span> <span data-ttu-id="0cf77-272">이는 참조에 의한 반환을 나타내고 나중에 코드를 읽는 개발자가 메서드가 참조에 의해 반환된다는 것을 기억하도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-272">That indicates return by reference, and helps developers reading the code later remember that the method returns by reference:</span></span>

[!code-csharp[FindReturningRef](../../../samples/snippets/csharp/new-in-7/MatrixSearch.cs#22_FindReturningRef "Find returning by reference")]

<span data-ttu-id="0cf77-273">이제 메서드는 매트릭스의 정수 값에 대한 참조를 반환하므로 메서드가 호출되는 위치를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-273">Now that the method returns a reference to the integer value in the matrix, you need to modify where it's called.</span></span>  <span data-ttu-id="0cf77-274">`var` 선언은 `valItem`이 이제 튜플이 아닌 `int`임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-274">The `var` declaration means that `valItem` is now an `int` rather than a tuple:</span></span>

[!code-csharp[AssignRefReturnToValue](../../../samples/snippets/csharp/new-in-7/program.cs#23_AssignRefReturnToValue "Assign ref return to value")]

<span data-ttu-id="0cf77-275">위 예제의 두 번째 `WriteLine` 문은 `24`가 아닌 `42` 값을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-275">The second `WriteLine` statement in the example above prints out the value `42`, not `24`.</span></span> <span data-ttu-id="0cf77-276">`valItem` 변수는 `ref int`가 아닌 `int`입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-276">The variable `valItem` is an `int`, not a `ref int`.</span></span> <span data-ttu-id="0cf77-277">`var` 키워드를 사용하면 컴파일러가 형식을 지정할 수 있지만 `ref` 한정자가 암시적으로 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-277">The `var` keyword enables the compiler to specify the type, but will not implicitly add the `ref` modifier.</span></span> <span data-ttu-id="0cf77-278">대신, `ref return`이 참조하는 값이 할당의 왼쪽에 있는 변수로 *복사*됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-278">Instead, the value referred to by the `ref return` is *copied* to the variable on the left-hand side of the assignment.</span></span> <span data-ttu-id="0cf77-279">변수는 `ref` local이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-279">The variable is not a `ref` local.</span></span>

<span data-ttu-id="0cf77-280">원하는 결과를 얻으려면 지역 변수 선언에 `ref` 한정자를 추가하여 반환 값이 참조인 경우 변수를 참조로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-280">In order to get the result you want, you need to add the `ref` modifier to the local variable declaration to make the variable a reference when the return value is a reference:</span></span>

[!code-csharp[AssignRefReturn](../../../samples/snippets/csharp/new-in-7/program.cs#24_AssignRefReturn "Assign ref return")]

<span data-ttu-id="0cf77-281">이제 위 예제의 두 번째 `WriteLine` 문은 매트릭스의 저장소가 수정되었음을 나타내는 `24` 값을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-281">Now, the second `WriteLine` statement in the example above will print out the value `24`, indicating that the storage in the matrix has been modified.</span></span> <span data-ttu-id="0cf77-282">지역 변수는 `ref` 한정자로 선언되었고 `ref` return을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-282">The local variable has been declared with the `ref` modifier, and it will take a `ref` return.</span></span> <span data-ttu-id="0cf77-283">`ref` 변수는 선언될 때 초기화해야 합니다. 선언과 초기화를 분할할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-283">You must initialize a `ref` variable when it is declared, you cannot split the declaration and the initialization.</span></span>

<span data-ttu-id="0cf77-284">C# 언어에는 `ref` local 및 return을 잘못 사용하는 경우를 방지하는 세 가지 다른 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-284">The C# language has three other rules that protect you from misusing the `ref` locals and returns:</span></span>

* <span data-ttu-id="0cf77-285">표준 메서드 반환 값을 `ref` 로컬 변수에 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-285">You cannot assign a standard method return value to a `ref` local variable.</span></span>
    - <span data-ttu-id="0cf77-286">이로 인해 `ref int i = sequence.Count();` 같은 문이 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-286">That disallows statements like `ref int i = sequence.Count();`</span></span>
* <span data-ttu-id="0cf77-287">메서드 실행보다 길게 수명이 연장되지 않는 변수로 `ref`를 반환할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-287">You cannot return a `ref` to a variable whose lifetime does not extend beyond the execution of the method.</span></span>
    - <span data-ttu-id="0cf77-288">이는 지역 변수 또는 비슷한 범위의 변수에 대한 참조를 반환할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-288">That means you cannot return a reference to a local variable or a variable with a similar scope.</span></span>
* <span data-ttu-id="0cf77-289">`ref` local 및 return은 비동기 메서드와 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-289">`ref` locals and returns can't be used with async methods.</span></span>
    - <span data-ttu-id="0cf77-290">컴파일러는 비동기 메서드가 반환될 때 참조된 변수가 최종 값으로 설정되었는지 여부를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-290">The compiler can't know if the referenced variable has been set to its final value when the async method returns.</span></span>

<span data-ttu-id="0cf77-291">ref local 및 ref return을 추가하면 값을 복사하거나 역참조 작업을 여러 번 수행하는 경우를 방지하여 더 효율적인 알고리즘이 가능해집니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-291">The addition of ref locals and ref returns enable algorithms that are more efficient by avoiding copying values, or performing dereferencing operations multiple times.</span></span> 

## <a name="local-functions"></a><span data-ttu-id="0cf77-292">로컬 함수</span><span class="sxs-lookup"><span data-stu-id="0cf77-292">Local functions</span></span>

<span data-ttu-id="0cf77-293">클래스에 대한 대부분의 디자인에는 한 위치에서만 호출되는 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-293">Many designs for classes include methods that are called from only one location.</span></span> <span data-ttu-id="0cf77-294">이러한 추가 private 메서드는 각 메서드를 작고 집중되게 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-294">These additional private methods keep each method small and focused.</span></span> <span data-ttu-id="0cf77-295">그러나 이러한 메서드를 사용하면 클래스를 처음 읽을 때 이해하기가 더 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-295">However, they can make it harder to understand a class when reading it the first time.</span></span> <span data-ttu-id="0cf77-296">이러한 메서드는 단일 호출 위치의 컨텍스트 외부에서 이해되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-296">These methods must be understood outside of the context of the single calling location.</span></span>

<span data-ttu-id="0cf77-297">해당 디자인의 경우 *로컬 함수*를 사용하여 다른 메서드의 컨텍스트 내부에서 메서드를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-297">For those designs, *local functions* enable you to declare methods inside the context of another method.</span></span> <span data-ttu-id="0cf77-298">이렇게 하면 클래스 판독기는 로컬 메서드가 선언된 컨텍스트에서만 호출됨을 더 쉽게 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-298">This makes it easier for readers of the class to see that the local method is only called from the context in which is it declared.</span></span>

<span data-ttu-id="0cf77-299">로컬 함수의 매우 일반적인 두 가지 사용 사례는 public 반복기 메서드 및 public 비동기 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-299">There are two very common use cases for local functions: public iterator methods and public async methods.</span></span> <span data-ttu-id="0cf77-300">두 메서드 형식 모두 프로그래머가 예상한 것보다 늦게 오류를 보고하는 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-300">Both types of methods generate code that reports errors later than programmers might expect.</span></span> <span data-ttu-id="0cf77-301">반복기 메서드의 경우 모든 예외는 반환된 시퀀스를 열거하는 코드를 호출할 경우에만 관찰됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-301">In the case of iterator methods, any exceptions are observed only when calling code that enumerates the returned sequence.</span></span> <span data-ttu-id="0cf77-302">비동기 메서드의 경우 모든 예외는 반환된 `Task`가 대기 상태일 경우에만 관찰됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-302">In the case of async methods, any exceptions are only observed when the returned `Task` is awaited.</span></span>

<span data-ttu-id="0cf77-303">먼저 반복기 메서드를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-303">Let's start with an iterator method:</span></span>

[!code-csharp[IteratorMethod](../../../samples/snippets/csharp/new-in-7/Iterator.cs#25_IteratorMethod "Iterator method")]

<span data-ttu-id="0cf77-304">반복기 메서드를 잘못 호출하는 아래 코드를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-304">Examine the code below that calls the iterator method incorrectly:</span></span>

[!code-csharp[CallIteratorMethod](../../../samples/snippets/csharp/new-in-7/program.cs#26_CallIteratorMethod "Call iterator method")]

<span data-ttu-id="0cf77-305">`resultSet`가 만들어질 때가 아니라 `resultSet`가 반복될 때 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-305">The exception is thrown when `resultSet` is iterated, not when `resultSet` is created.</span></span>
<span data-ttu-id="0cf77-306">이 포함된 예제에서 대부분 개발자는 문제를 빠르게 진단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-306">In this contained example, most developers could quickly diagnose the problem.</span></span> <span data-ttu-id="0cf77-307">그러나 코드베이스가 커지면 반복기를 만드는 코드가 결과를 열거하는 코드와 가깝지 않은 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-307">However, in larger codebases, the code that creates an iterator often isn't as close to the code that enumerates the result.</span></span> <span data-ttu-id="0cf77-308">public 메서드가 모든 인수의 유효성을 검사하고 private 메서드가 열거형을 생성하도록 코드를 리팩터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-308">You can refactor the code so that the public method validates all arguments, and a private method generates the enumeration:</span></span>

[!code-csharp[IteratorMethodRefactored](../../../samples/snippets/csharp/new-in-7/Iterator.cs#27_IteratorMethodRefactored "Iterator method refactored")]

<span data-ttu-id="0cf77-309">public 메서드가 반복기 메서드가 아니고 private 메서드만 `yield return` 구문을 사용하므로 이 리팩터링된 버전은 즉시 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-309">This refactored version will throw exceptions immediately because the public method is not an iterator method; only the private method uses the `yield return` syntax.</span></span> <span data-ttu-id="0cf77-310">그러나 이 리팩터링에서 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-310">However, there are potential problems with this refactoring.</span></span> <span data-ttu-id="0cf77-311">private 메서드는 public 인터페이스 메서드에서만 호출되어야 합니다. 그렇지 않으면 모든 인수 유효성 검사를 건너뛰기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-311">The private method should only be called from the public interface method, because otherwise all argument validation is skipped.</span></span>
<span data-ttu-id="0cf77-312">클래스 판독기는 전체 클래스를 읽고 `alphabetSubsetImplementation` 메서드에 대한 다른 참조를 검색하여 이 사실을 발견해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-312">Readers of the class must discover this fact by reading the entire class and searching for any other references to the `alphabetSubsetImplementation` method.</span></span>

<span data-ttu-id="0cf77-313">public API 메서드 내부에서 `alphabetSubsetImplementation`을 로컬 함수로 선언하여 디자인 의도를 더 분명히 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-313">You can make that design intent more clear by declaring the `alphabetSubsetImplementation` as a local function inside the public API method:</span></span>

[!code-csharp[22_IteratorMethodLocal](../../../samples/snippets/csharp/new-in-7/Iterator.cs#28_IteratorMethodLocal "Iterator method with local function")]

<span data-ttu-id="0cf77-314">위 버전을 사용하면 로컬 메서드가 외부 메서드의 컨텍스트에서만 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-314">The version above makes it clear that the local method is referenced only in the context of the outer method.</span></span> <span data-ttu-id="0cf77-315">로컬 함수에 대한 규칙을 적용하면 개발자가 클래스의 다른 위치에서 로컬 함수를 실수로 호출하고 인수 유효성 검사를 건너뛸 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-315">The rules for local functions also ensure that a developer can't accidentally call the local function from another location in the class and bypass the argument validation.</span></span>

<span data-ttu-id="0cf77-316">`async` 메서드에서 같은 방법을 사용하면 인수 유효성 검사에서 발생하는 예외가 비동기 작업이 시작되기 전에 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-316">The same technique can be employed with `async` methods to ensure that exceptions arising from argument validation are thrown before the asynchronous work begins:</span></span>

[!code-csharp[TaskExample](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Task returning method with local function")]

> [!NOTE]
> <span data-ttu-id="0cf77-317">로컬 함수가 지원하는 일부 디자인은 *람다 식*을 사용하여 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-317">Some of the designs that are supported by local functions could also be accomplished using *lambda expressions*.</span></span> <span data-ttu-id="0cf77-318">관심 있는 사용자는 [차이점을 자세히 확인](../local-functions-vs-lambdas.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-318">Those interested can [read more about the differences](../local-functions-vs-lambdas.md)</span></span>

## <a name="more-expression-bodied-members"></a><span data-ttu-id="0cf77-319">추가 식 본문 멤버</span><span class="sxs-lookup"><span data-stu-id="0cf77-319">More expression-bodied members</span></span>

<span data-ttu-id="0cf77-320">C# 6에서는 멤버 함수의 [식 본문 멤버](csharp-6.md#expression-bodied-function-members) 및 읽기 전용 속성을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-320">C# 6 introduced [expression-bodied members](csharp-6.md#expression-bodied-function-members) for member functions, and read-only properties.</span></span> <span data-ttu-id="0cf77-321">C# 7.0에서는 식으로 구현될 수 있는 허용 멤버를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-321">C# 7.0 expands the allowed members that can be implemented as expressions.</span></span> <span data-ttu-id="0cf77-322">C# 7.0에서는 *속성* 및 *인덱서*에 대한 *생성자*, *종료자* 및 `get`/`set` 접근자를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-322">In C# 7.0, you can implement *constructors*, *finalizers*, and `get` and `set` accessors on *properties* and *indexers*.</span></span> <span data-ttu-id="0cf77-323">다음 코드는 각각에 대한 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-323">The following code shows examples of each:</span></span>

[!code-csharp[ExpressionBodiedMembers](../../../samples/snippets/csharp/new-in-7/expressionmembers.cs#36_ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> <span data-ttu-id="0cf77-324">이 예제에는 종료자가 필요하지 않지만 구문을 보여 주기 위해 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-324">This example does not need a finalizer, but it is shown to demonstrate the syntax.</span></span> <span data-ttu-id="0cf77-325">관리되지 않는 리소스를 릴리스해야 하는 경우가 아니면 클래스에서 종료자를 구현하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-325">You should not implement a finalizer in your class unless it is necessary to  release unmanaged resources.</span></span> <span data-ttu-id="0cf77-326">관리되지 않는 리소스를 직접 관리하지 않고 <xref:System.Runtime.InteropServices.SafeHandle> 클래스를 사용하는 것도 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-326">You should also consider using the <xref:System.Runtime.InteropServices.SafeHandle> class instead of managing unmanaged resources directly.</span></span>

<span data-ttu-id="0cf77-327">식 본문 멤버의 이러한 새 위치는 C# 언어에 대한 중요한 기준을 나타냅니다. 이러한 기능은 오픈 소스 [Roslyn](https://github.com/dotnet/Roslyn) 프로젝트에 대한 작업을 수행하는 커뮤니티 멤버가 구현했습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-327">These new locations for expression-bodied members represent an important milestone for the C# language: These features were implemented by community members working on the open-source [Roslyn](https://github.com/dotnet/Roslyn) project.</span></span>

## <a name="throw-expressions"></a><span data-ttu-id="0cf77-328">Throw 식</span><span class="sxs-lookup"><span data-stu-id="0cf77-328">Throw expressions</span></span>

<span data-ttu-id="0cf77-329">C#에서 `throw`는 항상 문이었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-329">In C#, `throw` has always been a statement.</span></span> <span data-ttu-id="0cf77-330">`throw`는 식이 아닌 문이므로 이 문을 사용할 수 없는 C# 구문이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-330">Because `throw` is a statement, not an expression, there were C# constructs where you could not use it.</span></span> <span data-ttu-id="0cf77-331">이러한 구문에는 조건식, null 병합 식 및 몇몇 람다 식이 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-331">These included conditional expressions, null coalescing expressions, and some lambda expressions.</span></span> <span data-ttu-id="0cf77-332">식 본문 멤버가 추가됨에 따라 `throw` 식이 유용할 수 있는 추가 위치도 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-332">The addition of expression-bodied members adds more locations where `throw` expressions would be useful.</span></span> <span data-ttu-id="0cf77-333">이러한 구문을 작성할 수 있도록 C# 7.0에서는 *throw 식*을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-333">So that you can write any of these constructs, C# 7.0 introduces *throw expressions*.</span></span>

<span data-ttu-id="0cf77-334">구문은 항상 `throw` 문에 사용하던 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-334">The syntax is the same as you've always used for `throw` statements.</span></span> <span data-ttu-id="0cf77-335">유일한 차이점은 이제 이러한 구문을 조건식과 같은 새 위치에 배치할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-335">The only difference is that now you can place them in new locations, such as in a conditional expression:</span></span>

[!code-csharp[Throw_ExpressionExample](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#37_Throw_ExpressionExample "conditional throw expressions")]

<span data-ttu-id="0cf77-336">이 기능을 통해 초기화 식에서 throw 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-336">This features enables using throw expressions in initialization expressions:</span></span>

[!code-csharp[ThrowInInitialization](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#38_ThrowInInitialization "conditional throw expressions")]

<span data-ttu-id="0cf77-337">이전에는 해당 초기화가 생성자 내에 있고 throw 문이 생성자 본문 내에 있어야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-337">Previously, those initializations would need to be in a constructor, with the throw statements in the body of the constructor:</span></span>


[!code-csharp[ThrowInConstructor](../../../samples/snippets/csharp/new-in-7/throwexpressions.cs#39_ThrowInConstructor "throw statements")]

> [!NOTE]
> <span data-ttu-id="0cf77-338">이전 구문에서는 둘 다 개체 생성 중에 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-338">Both of the preceding constructs will cause exceptions to be thrown during the construction of an object.</span></span> <span data-ttu-id="0cf77-339">이러한 경우는 보통 복구하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-339">Those are often difficult to recover from.</span></span>
> <span data-ttu-id="0cf77-340">이런 이유로 생성 중에 예외를 throw하는 디자인은 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-340">For that reason, designs that throw exceptions during construction are discouraged.</span></span>

## <a name="generalized-async-return-types"></a><span data-ttu-id="0cf77-341">일반화된 비동기 반환 형식</span><span class="sxs-lookup"><span data-stu-id="0cf77-341">Generalized async return types</span></span>

<span data-ttu-id="0cf77-342">비동기 메서드에서 `Task` 개체를 반환하면 특정 경로에 성능 병목 현상이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-342">Returning a `Task` object from async methods can introduce performance bottlenecks in certain paths.</span></span> <span data-ttu-id="0cf77-343">`Task`는 참조 형식이므로 이를 사용하는 것은 개체 할당을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-343">`Task` is a reference type, so using it means allocating an object.</span></span> <span data-ttu-id="0cf77-344">`async` 한정자로 선언된 메서드가 캐시된 결과를 반환하거나 동기적으로 완료된 경우 코드의 성능이 중요한 섹션에서 추가 할당에 상당한 시간이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-344">In cases where a method declared with the `async` modifier returns a cached result, or completes synchronously, the extra allocations can become a significant time cost in performance critical sections of code.</span></span> <span data-ttu-id="0cf77-345">연속 루프에서 이러한 할당이 발생하면 큰 부담이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-345">It can become very costly if those allocations occur in tight loops.</span></span>

<span data-ttu-id="0cf77-346">새로운 언어 기능은 비동기 메서드가 `Task`, `Task<T>` 및 `void` 외에 다른 형식을 반환할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-346">The new language feature means that async methods may return other types in addition to `Task`, `Task<T>` and `void`.</span></span> <span data-ttu-id="0cf77-347">반환된 형식은 비동기 패턴을 충족해야 합니다. 즉, `GetAwaiter` 메서드에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-347">The returned type must still satisfy the async pattern, meaning a `GetAwaiter` method must be accessible.</span></span> <span data-ttu-id="0cf77-348">한 가지 구체적인 예로 이 새로운 언어 기능을 사용할 수 있도록 `ValueTask` 형식이 .NET Framework에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-348">As one concrete example, the `ValueTask` type has been added to the .NET framework to make use of this new language feature:</span></span> 

[!code-csharp[UsingValueTask](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#30_UsingValueTask "Using ValueTask")]

> [!NOTE]
> <span data-ttu-id="0cf77-349"><xref:System.Threading.Tasks.ValueTask%601> 형식을 사용하려면 NuGet 패키지 [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/)를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-349">You need to add the NuGet package [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) in order to use the <xref:System.Threading.Tasks.ValueTask%601> type.</span></span>

<span data-ttu-id="0cf77-350">간단한 최적화는 이전에 `Task`가 사용된 위치에서 `ValueTask`를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-350">A simple optimization would be to use `ValueTask` in places where `Task` would be used before.</span></span> <span data-ttu-id="0cf77-351">그러나 추가 최적화를 직접 수행하려는 경우 비동기 작업에서 결과를 캐시하고 후속 호출에서 결과를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-351">However, if you want to perform extra optimizations by hand, you can cache results from async work and reuse the result in subsequent calls.</span></span> <span data-ttu-id="0cf77-352">`ValueTask` 구조체에는 기존 비동기 메서드의 반환 값에서 `ValueTask`를 생성할 수 있도록 `Task` 매개 변수가 포함된 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-352">The `ValueTask` struct has a constructor with a `Task` parameter so that you can construct a `ValueTask` from the return value of any existing async method:</span></span>

[!code-csharp[AsyncOptimizedValueTask](../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#31_AsyncOptimizedValueTask "Return async result or cached value")]
 
<span data-ttu-id="0cf77-353">모든 성능 권장 사항처럼 코드를 대규모로 변경하기 전에 두 가지 버전을 모두 벤치마크해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-353">As with all performance recommendations, you should benchmark both versions before making large scale changes to your code.</span></span>

## <a name="numeric-literal-syntax-improvements"></a><span data-ttu-id="0cf77-354">숫자 리터럴 구문 개선 사항</span><span class="sxs-lookup"><span data-stu-id="0cf77-354">Numeric literal syntax improvements</span></span>

<span data-ttu-id="0cf77-355">숫자 상수를 잘못 읽으면 코드를 처음 읽을 때 이해하기가 더 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-355">Misreading numeric constants can make it harder to understand code when reading it for the first time.</span></span> <span data-ttu-id="0cf77-356">이 문제는 일반적으로 해당 숫자가 숫자 값이 아닌 비트 마스크나 다른 기호로 사용될 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-356">This often occurs when those numbers are used as bit masks or other symbolic rather than numeric values.</span></span> <span data-ttu-id="0cf77-357">C# 7.0에는 의도한 용도에 맞게 가장 읽기 쉬운 방식으로 숫자를 더 쉽게 작성할 수 있는 두 가지 새로운 기능인 *이진 리터럴* 및 *숫자 구분 기호*가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-357">C# 7.0 includes two new features to make it easier to write numbers in the most readable fashion for the intended use: *binary literals*, and *digit separators*.</span></span>

<span data-ttu-id="0cf77-358">비트 마스크를 만들 경우 또는 숫자의 이진 표현이 가장 읽기 쉬운 코드를 만들 때마다 해당 숫자를 이진으로 작성하세요.</span><span class="sxs-lookup"><span data-stu-id="0cf77-358">For those times when you are creating bit masks, or whenever a binary representation of a number makes the most readable code, write that number in binary:</span></span>

[!code-csharp[BinaryConstants](../../../samples/snippets/csharp/new-in-7/Program.cs#32_BinaryConstants "Binary constants")]

<span data-ttu-id="0cf77-359">상수의 시작 부분에 있는 `0b`는 숫자가 이진 숫자로 작성되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-359">The `0b` at the beginning of the constant indicates that the number is written as a binary number.</span></span>

<span data-ttu-id="0cf77-360">이진 숫자는 매우 길어질 수 있으므로 `_`을 숫자 구분 기호로 추가하면 비트 패턴을 더 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-360">Binary numbers can get very long, so it's often easier to see the bit patterns by introducing the `_` as a digit separator:</span></span>

[!code-csharp[ThousandSeparators](../../../samples/snippets/csharp/new-in-7/Program.cs#33_ThousandSeparators "Thousands separators")]

<span data-ttu-id="0cf77-361">숫자 구분 기호는 상수 내의 어디에나 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-361">The digit separator can appear anywhere in the constant.</span></span> <span data-ttu-id="0cf77-362">기본 10개 숫자의 경우 일반적으로 숫자 구분 기호가 천 단위 구분 기호로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-362">For base 10 numbers, it would be common to use it as a thousands separator:</span></span>

[!code-csharp[LargeIntegers](../../../samples/snippets/csharp/new-in-7/Program.cs#34_LargeIntegers "Large integer")]

<span data-ttu-id="0cf77-363">숫자 구분 기호는 `decimal`, `float` 및 `double` 형식에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-363">The digit separator can be used with `decimal`, `float` and `double` types as well:</span></span>

[!code-csharp[OtherConstants](../../../samples/snippets/csharp/new-in-7/Program.cs#35_OtherConstants "non-integral constants")]

<span data-ttu-id="0cf77-364">함께 사용하면 숫자 상수를 훨씬 더 읽기 쉽게 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf77-364">Taken together, you can declare numeric constants with much more readability.</span></span>
