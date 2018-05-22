---
title: 튜플 - C# 가이드
description: C#의 명명되지 않은 튜플 형식과 명명된 튜플 형식에 대한 자세한 정보
ms.date: 11/23/2016
ms.assetid: ee8bf7c3-aa3e-4c9e-a5c6-e05cc6138baa
ms.openlocfilehash: a5240c47dce695759c6e9b76b506077772b58aeb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="c-tuple-types"></a><span data-ttu-id="c9b2b-103">C# 튜플 형식</span><span class="sxs-lookup"><span data-stu-id="c9b2b-103">C# Tuple types</span></span> #

<span data-ttu-id="c9b2b-104">C# 튜플은 간단한 구문을 사용하여 정의하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-104">C# Tuples are types that you define using a lightweight syntax.</span></span> <span data-ttu-id="c9b2b-105">장점으로 더 간단한 구문, 요소 수(카디널리티라고 함) 및 형식에 따른 변환 규칙, 복사 및 할당에 대한 일관된 규칙 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-105">The advantages include a simpler syntax, rules for conversions based on number (referred to as cardinality) and types of elements, and consistent rules for copies and assignments.</span></span> <span data-ttu-id="c9b2b-106">반면, 튜플은 상속과 관련된 개체 지향 구문의 일부를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-106">As a tradeoff, Tuples do not support some of the object oriented idioms associated with inheritance.</span></span> <span data-ttu-id="c9b2b-107">[C# 7.0 새로운 기능의 튜플](whats-new/csharp-7.md#tuples) 항목에 대한 섹션에서 전반적인 개요를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-107">You can get an overview in the section on [Tuples in the What's new in C# 7.0](whats-new/csharp-7.md#tuples) topic.</span></span>

<span data-ttu-id="c9b2b-108">이 항목에서는 C# 7.0 이상에서 튜플을 제어하는 언어 규칙, 다양한 사용 방법 및 튜플 작업에 대한 초기 지침을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-108">In this topic, you'll learn the language rules governing Tuples in C# 7.0 and later, different ways to use them, and initial guidance on working with Tuples.</span></span>

> [!NOTE]
> <span data-ttu-id="c9b2b-109">새 튜플 기능을 사용하려면 <xref:System.ValueTuple> 형식이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-109">The new tuples features require the <xref:System.ValueTuple> types.</span></span>
> <span data-ttu-id="c9b2b-110">형식을 포함하지 않는 플랫폼에서 사용하려면 NuGet 패키지 [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/)을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-110">You must add the NuGet package [`System.ValueTuple`](https://www.nuget.org/packages/System.ValueTuple/) in order to use it on platforms that do not include the types.</span></span>
>
> <span data-ttu-id="c9b2b-111">이는 프레임워크에서 제공되는 형식을 사용하는 다른 언어 기능과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-111">This is similar to other language features that rely on types delivered in the framework.</span></span> <span data-ttu-id="c9b2b-112">예를 들어 `async` 및 `await`는 `INotifyCompletion` 인터페이스를 사용하고 LINQ는 `IEnumerable<T>`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-112">Examples include `async` and `await` relying on the `INotifyCompletion` interface, and LINQ relying on `IEnumerable<T>`.</span></span> <span data-ttu-id="c9b2b-113">그러나 .NET이 점점 더 플랫폼 독립적으로 되면서 배달 메커니즘도 변하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-113">However, the delivery mechanism is changing as .NET is becoming more platform independent.</span></span> <span data-ttu-id="c9b2b-114">.NET Framework가 언어 컴파일러와 동일한 주기로 제공되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-114">The .NET Framework may not always ship on the same cadence as the language compiler.</span></span> <span data-ttu-id="c9b2b-115">새로운 언어 기능이 새 형식을 사용하는 경우 해당 형식은 언어 기능이 제공될 때 NuGet 패키지로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-115">When new language features rely on new types, those types will be available as NuGet packages when the language features ship.</span></span> <span data-ttu-id="c9b2b-116">이러한 새로운 형식이 .NET Standard API에 추가되고 프레임워크의 일부로 제공되면, NuGet 패키지 요구 사항이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-116">As these new types get added to the .NET Standard API and delivered as part of the framework, the NuGet package requirement will be removed.</span></span>

<span data-ttu-id="c9b2b-117">새 튜플 지원을 추가하는 이유부터 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-117">Let's start with the reasons for adding new Tuple support.</span></span> <span data-ttu-id="c9b2b-118">메서드는 단일 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-118">Methods return a single object.</span></span> <span data-ttu-id="c9b2b-119">튜플을 사용하면 해당 단일 개체에 여러 값을 보다 쉽게 패키징할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-119">Tuples enable you to package multiple values in that single object more easily.</span></span>

<span data-ttu-id="c9b2b-120">.NET Framework에는 제네릭 `Tuple` 클래스가 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-120">The .NET Framework already has generic `Tuple` classes.</span></span> <span data-ttu-id="c9b2b-121">그러나 이러한 클래스에는 두 가지 주요 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-121">These classes, however, had two major limitations.</span></span> <span data-ttu-id="c9b2b-122">한 가지는 `Tuple` 클래스의 속성 이름이 `Item1`, `Item2` 등으로 지정된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-122">For one, the `Tuple` classes named their properties `Item1`, `Item2`, and so on.</span></span> <span data-ttu-id="c9b2b-123">이 이름에는 의미 체계 정보가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-123">Those names carry no semantic information.</span></span> <span data-ttu-id="c9b2b-124">이러한 `Tuple` 형식을 사용하면 각 속성의 의미를 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-124">Using these `Tuple` types does not enable communicating the meaning of each of the properties.</span></span> <span data-ttu-id="c9b2b-125">새로운 언어 기능을 사용하여 튜플의 요소에 대한 의미 있는 의미 체계 이름을 선언하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-125">The new language features enable you to declare and use semantically meaningful names for the elements in a tuple.</span></span>

<span data-ttu-id="c9b2b-126">또 다른 문제는 `Tuple` 클래스가 참조 형식이라는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-126">Another concern is that the `Tuple` classes are reference types.</span></span> <span data-ttu-id="c9b2b-127">`Tuple` 형식 중 하나를 사용한다는 것은 개체 할당을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-127">Using one of the `Tuple` types means allocating objects.</span></span> <span data-ttu-id="c9b2b-128">실행 부하 과다 경로에서는 이로 인해 응용 프로그램 성능이 크게 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-128">On hot paths, this can have a measurable impact on your application's performance.</span></span> <span data-ttu-id="c9b2b-129">그러므로 튜플에 대한 언어 지원은 새 `ValueTuple` 구조체를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-129">Therefore, the language support for tuples leverages the new `ValueTuple` structs.</span></span>

<span data-ttu-id="c9b2b-130">이러한 결함을 방지하기 위해 `class` 또는 `struct`를 만들어 여러 요소를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-130">To avoid those deficiencies, you could create a `class` or a `struct` to carry multiple elements.</span></span> <span data-ttu-id="c9b2b-131">하지만 이 경우 작업량이 증가하며 설계 의도가 모호해집니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-131">Unfortunately, that's more work for you, and it obscures your design intent.</span></span> <span data-ttu-id="c9b2b-132">`struct` 또는 `class` 생성은 데이터와 동작 둘 다를 사용하여 형식을 정의하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-132">Making a `struct` or `class` implies that you are defining a type with both data and behavior.</span></span> <span data-ttu-id="c9b2b-133">단순히 여러 값을 단일 개체에 저장하려는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-133">Many times, you simply want to store multiple values in a single object.</span></span>

<span data-ttu-id="c9b2b-134">언어 기능 및 `ValueTuple` 제네릭 구조체는 이러한 튜플 형식에 동작(메서드)을 추가할 수 없다는 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-134">The language features and the `ValueTuple` generic structs enforce the rule that you cannot add any behavior (methods) to these tuple types.</span></span>
<span data-ttu-id="c9b2b-135">모든 `ValueTuple` 형식은 *변경할 수 있는 구조체*입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-135">All the `ValueTuple` types are *mutable structs*.</span></span> <span data-ttu-id="c9b2b-136">각 멤버 필드는 공용 필드이므로</span><span class="sxs-lookup"><span data-stu-id="c9b2b-136">Each member field is a public field.</span></span> <span data-ttu-id="c9b2b-137">필드가 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-137">That makes them very lightweight.</span></span> <span data-ttu-id="c9b2b-138">그러나 이 때문에 불변성이 중요한 경우에는 튜플을 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-138">However, that means tuples should not be used where immutability is important.</span></span>

<span data-ttu-id="c9b2b-139">튜플은 `class` 및 `struct` 형식보다 더 간단하고 유연한 데이터 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-139">Tuples are both simpler and more flexible data containers than `class` and `struct` types.</span></span> <span data-ttu-id="c9b2b-140">이러한 차이점을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-140">Let's explore those differences.</span></span>

## <a name="named-and-unnamed-tuples"></a><span data-ttu-id="c9b2b-141">명명된 튜플 및 명명되지 않은 튜플</span><span class="sxs-lookup"><span data-stu-id="c9b2b-141">Named and unnamed tuples</span></span>

<span data-ttu-id="c9b2b-142">`ValueTuple` 구조체에는 `Item1`, `Item2`, `Item3` 등으로 이름이 지정된 필드가 있습니다. 이러한 필드는 기존 `Tuple` 형식에서 정의된 속성과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-142">The `ValueTuple` struct has fields named `Item1`, `Item2`, `Item3` and so on, similar to the properties defined in the existing `Tuple` types.</span></span>
<span data-ttu-id="c9b2b-143">이러한 이름만 *명명되지 않은 튜플*에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-143">These names are the only names you can use for *unnamed tuples*.</span></span> <span data-ttu-id="c9b2b-144">튜플에 대체 필드 이름을 지정하지 않는 경우 명명되지 않은 튜플을 만든 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-144">When you do not provide any alternative field names to a tuple, you've created an unnamed tuple:</span></span>

[!code-csharp[UnnamedTuple](../../samples/snippets/csharp/tuples/tuples/program.cs#01_UnNamedTuple "Unnamed tuple")]

<span data-ttu-id="c9b2b-145">이전 예제의 튜플은 리터럴 상수를 사용하여 초기화되었고 C# 7.1의 *Tuple field name projections*(튜플 필드 이름 프로젝션)를 사용하여 만들어진 요소 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-145">The tuple in the previous example was initialized using literal constants and won't have element names created using *Tuple field name projections* in C# 7.1.</span></span>

<span data-ttu-id="c9b2b-146">그러나 튜플을 초기화할 때 각 필드에 더 나은 이름을 지정하는 새로운 언어 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-146">However, when you initialize a tuple, you can use new language features that give better names to each field.</span></span> <span data-ttu-id="c9b2b-147">이렇게 하면 *명명된 튜플*이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-147">Doing so creates a *named tuple*.</span></span>
<span data-ttu-id="c9b2b-148">명명된 튜플에도 `Item1`, `Item2`, `Item3` 등으로 이름이 지정된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-148">Named tuples still have elements named `Item1`, `Item2`, `Item3` and so on.</span></span>
<span data-ttu-id="c9b2b-149">그러나 명명된 요소에 대한 동의어도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-149">But they also have synonyms for any of those elements that you have named.</span></span>
<span data-ttu-id="c9b2b-150">각 요소에 대한 이름을 지정하여 명명된 튜플을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-150">You create a named tuple by specifying the names for each element.</span></span> <span data-ttu-id="c9b2b-151">한 가지 방법은 튜플 초기화의 일부로 이름을 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-151">One way is to specify the names as part of the tuple initialization:</span></span>

[!code-csharp[NamedTuple](../../samples/snippets/csharp/tuples/tuples/program.cs#02_NamedTuple "Named tuple")]

<span data-ttu-id="c9b2b-152">이러한 동의어는 명명된 튜플을 효과적으로 사용할 수 있도록 컴파일러 및 언어에 의해 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-152">These synonyms are handled by the compiler and the language so that you can use named tuples effectively.</span></span> <span data-ttu-id="c9b2b-153">IDE 및 편집기는 Roslyn API를 사용하여 이러한 의미 체계 이름을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-153">IDEs and editors can read these semantic names using the Roslyn APIs.</span></span> <span data-ttu-id="c9b2b-154">따라서 동일한 어셈블리의 모든 위치에서 해당 의미 체계 이름으로 명명된 튜플의 요소를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-154">This enables you to reference the elements of a named tuple by those semantic names anywhere in the same assembly.</span></span> <span data-ttu-id="c9b2b-155">컴파일러는 컴파일된 출력을 생성할 때 정의된 이름을 동등한 `Item*` 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-155">The compiler replaces the names you've defined with `Item*` equivalents when generating the compiled output.</span></span> <span data-ttu-id="c9b2b-156">컴파일된 MSIL(Microsoft Intermediate Language)에는 이러한 요소에 지정한 이름이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-156">The compiled Microsoft Intermediate Language (MSIL) does not include the names you've given these elements.</span></span>

<span data-ttu-id="c9b2b-157">C# 7.1부터 튜플에 대한 필드 이름은 튜플을 초기화하는 데 사용되는 변수로부터 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-157">Beginning with C# 7.1, the field names for a tuple may be provided from the variables used to initialize the tuple.</span></span> <span data-ttu-id="c9b2b-158">이를 **[튜플 프로젝션 이니셜라이저](#tuple-projection-initializers)** 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-158">This is referred to as **[tuple projection initializers](#tuple-projection-initializers)**.</span></span> <span data-ttu-id="c9b2b-159">다음 코드에서는 `count`(정수) 및 `sum`(double) 요소가 있는 `accumulation`이라는 이름의 튜플을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-159">The following code creates a tuple named `accumulation` with elements `count` (an integer), and `sum` (a double).</span></span>

[!code-csharp[ProjectedTuple](../../samples/snippets/csharp/tuples/tuples/program.cs#ProjectedTupleNames "Named tuple")]

<span data-ttu-id="c9b2b-160">컴파일러는 public 메서드 또는 속성에서 반환된 튜플에 대해 생성된 이름을 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-160">The compiler must communicate those names you created for tuples that are returned from public methods or properties.</span></span> <span data-ttu-id="c9b2b-161">이러한 경우 컴파일러는 메서드에 <xref:System.Runtime.CompilerServices.TupleElementNamesAttribute> 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-161">In those cases, the compiler adds a <xref:System.Runtime.CompilerServices.TupleElementNamesAttribute> attribute on the method.</span></span> <span data-ttu-id="c9b2b-162">이 특성에는 튜플의 각 요소에 지정된 이름이 포함된 <xref:System.Runtime.CompilerServices.TupleElementNamesAttribute.TransformNames> 목록 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-162">This attribute contains a <xref:System.Runtime.CompilerServices.TupleElementNamesAttribute.TransformNames> list property that contains the names given to each of the elements in the Tuple.</span></span>

> [!NOTE]
> <span data-ttu-id="c9b2b-163">또한 Visual Studio 등의 개발 도구는 메타데이터를 읽고 IntelliSense 및 메타데이터 필드 이름을 사용하는 기타 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-163">Development Tools, such as Visual Studio, also read that metadata, and provide IntelliSense and other features using the metadata field names.</span></span>

<span data-ttu-id="c9b2b-164">명명된 튜플을 서로에게 할당하는 규칙을 파악하려면 새 튜플 및 `ValueTuple` 형식의 이러한 기본 사항을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-164">It is important to understand these underlying fundamentals of the new tuples and the `ValueTuple` type in order to understand the rules for assigning named tuples to each other.</span></span>

## <a name="tuple-projection-initializers"></a><span data-ttu-id="c9b2b-165">튜플 프로젝션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="c9b2b-165">Tuple projection initializers</span></span>

<span data-ttu-id="c9b2b-166">일반적으로 튜플 프로젝션 이니셜라이저는 튜플 초기화 문의 오른쪽에 있는 변수 또는 필드 이름을 사용하여 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-166">In general, tuple projection initializers work by using the variable or field names from the right-hand side of a tuple initialization statement.</span></span>
<span data-ttu-id="c9b2b-167">명시적 이름이 지정되는 경우 해당 이름이 프로젝션된 이름보다 우선됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-167">If an explicit name is given, that takes precedence over any projected name.</span></span> <span data-ttu-id="c9b2b-168">예를 들어 다음 이니셜라이저에서 요소는 `localVariableOne` 및 `localVariableTwo`가 아니라 `explicitFieldOne` 및 `explicitFieldTwo`입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-168">For example, in the following initializer, the elements are `explicitFieldOne` and `explicitFieldTwo`, not `localVariableOne` and `localVariableTwo`:</span></span>

[!code-csharp[ExplicitNamedTuple](../../samples/snippets/csharp/tuples/tuples/program.cs#ProjectionExample_Explicit "Explicitly named tuple")]

<span data-ttu-id="c9b2b-169">명시적 이름이 제공되지 않은 필드의 경우, 적용할 수 있는 암시적 이름이 프로젝션됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-169">For any field where an explicit name is not provided, an applicable implicit name will be projected.</span></span> <span data-ttu-id="c9b2b-170">명시적이든 암시적이든 의미 체계 이름을 제공해야 하는 요구 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-170">Note that there is no requirement to provide semantic names, either explicitly or implicitly.</span></span> <span data-ttu-id="c9b2b-171">다음 이니셜라이저의 필드 이름은 `Item1`이며, 값은 `42` 및 `StringContent`이고, 값이 “모든 것에 대한 답입니다”.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-171">The following initializer will have field names `Item1`, whose value is `42` and `StringContent`, whose value is "The answer to everything":</span></span>

[!code-csharp[MixedTuple](../../samples/snippets/csharp/tuples/tuples/program.cs#MixedTuple "mixed tuple")]

<span data-ttu-id="c9b2b-172">후보 필드 이름이 튜플 필드에 프로젝션되지 않는 두 가지 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-172">There are two conditions where candidate field names are not projected onto the tuple field:</span></span>

1. <span data-ttu-id="c9b2b-173">후보 이름이 예약된 튜플 이름인 경우.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-173">When the candidate name is a reserved tuple name.</span></span> <span data-ttu-id="c9b2b-174">예를 들면 `Item3`, `ToString` 또는 `Rest`입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-174">Examples include `Item3`, `ToString` or `Rest`.</span></span>
1. <span data-ttu-id="c9b2b-175">후보 이름이 명시적이든 암시적이든 다른 튜플 필드 이름과 중복되는 경우.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-175">When the candidate name is a duplicate of another tuple field name, either explicit or implicit.</span></span>

<span data-ttu-id="c9b2b-176">이러한 경우는 모호성을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-176">These conditions avoid ambiguity.</span></span> <span data-ttu-id="c9b2b-177">이러한 이름은 튜플의 필드에 대한 필드 이름으로 사용될 경우 모호성을 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-177">These names would cause an ambiguity if they were used as the field names for a field in a tuple.</span></span> <span data-ttu-id="c9b2b-178">이러한 경우에는 컴파일 타임 오류가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-178">Neither of these conditions cause compile time errors.</span></span> <span data-ttu-id="c9b2b-179">대신, 프로젝션된 이름이 없는 요소에는 프로젝션된 의미 체계 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-179">Instead, the elements without projected names do not have semantic names projected for them.</span></span>  <span data-ttu-id="c9b2b-180">다음 예제에서는 이러한 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-180">The following examples demonstrate these conditions:</span></span>

[!code-csharp[Ambiguity](../../samples/snippets/csharp/tuples/tuples/program.cs#ProjectionAmbiguities "tuples where projections are not performed")]

<span data-ttu-id="c9b2b-181">이러한 경우에는 튜플 필드 이름 프로젝션을 사용할 수 없을 때 C# 7.0으로 작성된 코드에 대한 새로운 변경 사항이므로 컴파일러 오류가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-181">These situations do not cause compiler errors because that would be a breaking change for code written with C# 7.0, when tuple field name projections were not available.</span></span>

## <a name="assignment-and-tuples"></a><span data-ttu-id="c9b2b-182">할당 및 튜플</span><span class="sxs-lookup"><span data-stu-id="c9b2b-182">Assignment and tuples</span></span>

<span data-ttu-id="c9b2b-183">이 언어는 요소 수가 같은 튜플 형식 간의 할당 및 각 요소에 대한 형식의 암시적 변환을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-183">The language supports assignment between tuple types that have the same number of elements and implicit conversions for the types for each of those elements.</span></span> <span data-ttu-id="c9b2b-184">다른 변환은 할당에 고려되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-184">Other conversions are not considered for assignments.</span></span> <span data-ttu-id="c9b2b-185">튜플 형식 간에 허용되는 할당 종류를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-185">Let's look at the kinds of assignments that are allowed between tuple types.</span></span>

<span data-ttu-id="c9b2b-186">다음 예제에서 사용되는 이러한 변수를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-186">Consider these variables used in the following examples:</span></span>

[!code-csharp[VariableCreation](../../samples/snippets/csharp/tuples/tuples/program.cs#03_VariableCreation "Variable creation")]

<span data-ttu-id="c9b2b-187">처음 두 변수인 `unnamed`와 `anonymous`에는 요소에 대해 지정된 의미 체계 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-187">The first two variables, `unnamed` and `anonymous` do not have semantic names provided for the elements.</span></span> <span data-ttu-id="c9b2b-188">필드 이름은 `Item1` 및 `Item2`입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-188">The field names are `Item1` and `Item2`.</span></span>
<span data-ttu-id="c9b2b-189">마지막 두 변수인 `named` 및 `differentName`에는 요소에 대해 지정된 의미 체계 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-189">The last two variables, `named` and `differentName` have semantic names given for the elements.</span></span> <span data-ttu-id="c9b2b-190">이러한 두 튜플의 요소 이름은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-190">Note that these two tuples have different names for the elements.</span></span>

<span data-ttu-id="c9b2b-191">이러한 네 튜플에서 요소 수('카디널리티'라고도 함)는 같으며, 해당 요소의 형식도 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-191">All four of these tuples have the same number of elements (referred to as 'cardinality') and the types of those elements are identical.</span></span> <span data-ttu-id="c9b2b-192">따라서 다음 할당이 모든 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-192">Therefore, all of these assignments work:</span></span>

[!code-csharp[VariableAssignment](../../samples/snippets/csharp/tuples/tuples/program.cs#04_VariableAssignment "Variable assignment")]

<span data-ttu-id="c9b2b-193">튜플 이름은 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-193">Notice that the names of the tuples are not assigned.</span></span> <span data-ttu-id="c9b2b-194">요소 값은 튜플의 요소 순서에 따라 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-194">The values of the elements are assigned following the order of the elements in the tuple.</span></span>

<span data-ttu-id="c9b2b-195">요소 수나 형식이 다른 튜플은 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-195">Tuples of different types or numbers of elements are not assignable:</span></span>

```csharp
// Does not compile.
// CS0029: Cannot assign Tuple(int,int,int) to Tuple(int, string)
var differentShape = (1, 2, 3);
named = differentShape;
```

## <a name="tuples-as-method-return-values"></a><span data-ttu-id="c9b2b-196">메서드 반환 값으로의 튜플</span><span class="sxs-lookup"><span data-stu-id="c9b2b-196">Tuples as method return values</span></span>

<span data-ttu-id="c9b2b-197">튜플의 가장 일반적인 사용 중 하나는 메서드 반환 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-197">One of the most common uses for Tuples is as a method return value.</span></span> <span data-ttu-id="c9b2b-198">한 가지 예를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-198">Let's walk through one example.</span></span> <span data-ttu-id="c9b2b-199">숫자 시퀀스의 표준 편차를 계산하는 다음 메서드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-199">Consider this method that computes the standard deviation for a sequence of numbers:</span></span>

[!code-csharp[StandardDeviation](../../samples/snippets/csharp/tuples/tuples/statistics.cs#05_StandardDeviation "Compute Standard Deviation")]

> [!NOTE]
> <span data-ttu-id="c9b2b-200">이 예제에서는 수정되지 않은 샘플 표준 편차를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-200">These examples compute the uncorrected sample standard deviation.</span></span>
> <span data-ttu-id="c9b2b-201">수정된 샘플 표준 편차 수식은 `Average` 확장 메서드와 같이 평균과의 차이를 거듭제곱한 값의 합계를 N 대신 (N-1)로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-201">The corrected sample standard deviation formula would divide the sum of the squared differences from the mean by (N-1) instead of N, as the `Average` extension method does.</span></span> <span data-ttu-id="c9b2b-202">이러한 표준 편차 수식 간의 차이점에 대한 자세한 내용은 통계 텍스트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-202">Consult a statistics text for more details on the differences between these formulas for standard deviation.</span></span>

<span data-ttu-id="c9b2b-203">여기서는 교재에 나오는 표준 편차 수식을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-203">This follows the textbook formula for the standard deviation.</span></span> <span data-ttu-id="c9b2b-204">올바른 답을 생성하지만 매우 비효율적인 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-204">It produces the correct answer, but it's a very inefficient implementation.</span></span> <span data-ttu-id="c9b2b-205">이 메서드는 시퀀스를 두 번 열거합니다. 한 번은 평균을 생성하기 위해, 다른 한 번은 평균 차이의 거듭제곱 평균을 생성하기 위해 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-205">This method enumerates the sequence twice: Once to produce the average, and once to produce the average of the square of the difference of the average.</span></span>
<span data-ttu-id="c9b2b-206">LINQ 쿼리는 지연 평가되므로 평가와의 차이 계산과 이러한 차이의 평균은 하나의 열거형만 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-206">(Remember that LINQ queries are evaluated lazily, so the computation of the differences from the mean and the average of those differences makes only one enumeration.)</span></span>

<span data-ttu-id="c9b2b-207">하나의 시퀀스 열거형만 사용하여 표준 편차를 계산하는 다른 수식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-207">There is an alternative formula that computes standard deviation using only one enumeration of the sequence.</span></span>  <span data-ttu-id="c9b2b-208">이 계산은 시퀀스를 열거하면서 시퀀스의 모든 항목 합계와 각 값의 거듭제곱 합계인 두 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-208">This computation produces two values as it enumerates the sequence: the sum of all items in the sequence, and the sum of the each value squared:</span></span>

[!code-csharp[SumOfSquaresFormula](../../samples/snippets/csharp/tuples/tuples/statistics.cs#06_SumOfSquaresFormula "Compute Standard Deviation using the sum of squares")]

<span data-ttu-id="c9b2b-209">이 버전에서는 시퀀스를 정확히 한 번만 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-209">This version enumerates the sequence exactly once.</span></span> <span data-ttu-id="c9b2b-210">그러나 어디서나 다시 사용할 수 있는 코드는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-210">But, it's not very reusable code.</span></span> <span data-ttu-id="c9b2b-211">계속 작업하면 시퀀스의 항목 수, 시퀀스의 합계, 시퀀스의 거듭제곱 합계가 다양한 통계 계산에서 사용되는 것을 발견할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-211">As you keep working, you'll find that many different statistical computations use the number of items in the sequence, the sum of the sequence, and the sum of the squares of the sequence.</span></span> <span data-ttu-id="c9b2b-212">이 메서드를 리팩터링하고 세 개의 값을 모두 생성하는 유틸리티 메서드를 작성하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-212">Let's refactor this method and write a utility method that produces all three of those values.</span></span>

<span data-ttu-id="c9b2b-213">이 경우 튜플이 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-213">This is where tuples come in very useful.</span></span> 

<span data-ttu-id="c9b2b-214">열거 중에 계산된 세 개의 값이 튜플에 저장되도록 이 메서드를 업데이트하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-214">Let's update this method so the three values computed during the enumeration are stored in a tuple.</span></span> <span data-ttu-id="c9b2b-215">다음 버전이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-215">That creates this version:</span></span>

[!code-csharp[TupleVersion](../../samples/snippets/csharp/tuples/tuples/statistics.cs#07_TupleVersion "Refactor to use tuples")]

<span data-ttu-id="c9b2b-216">Visual Studio의 리팩터링 지원을 사용하면 핵심 통계 기능을 private 메서드로 쉽게 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-216">Visual Studio's Refactoring support makes it easy to extract the functionality for the core statistics into a private method.</span></span> <span data-ttu-id="c9b2b-217">그러면 세 개의 값 `Sum`, `SumOfSquares` 및 `Count`가 포함된 튜플 형식을 반환하는 `private static` 메서드가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-217">That gives you a `private static` method that returns the tuple type with the three values of `Sum`, `SumOfSquares`, and `Count`:</span></span>

[!code-csharp[TupleMethodVersion](../../samples/snippets/csharp/tuples/tuples/statistics.cs#08_TupleMethodVersion "After extracting utility method")]
 
<span data-ttu-id="c9b2b-218">이 언어에서는 직접 몇 가지 빠른 편집을 수행하려는 경우 두 가지 옵션을 더 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-218">The language enables a couple more options that you can use, if you want to make a few quick edits by hand.</span></span> <span data-ttu-id="c9b2b-219">첫째, `var` 선언을 사용하여 `ComputeSumAndSumOfSquares` 메서드 호출에서 튜플 결과를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-219">First, you can use the `var` declaration to initialize the tuple result from the `ComputeSumAndSumOfSquares` method call.</span></span> <span data-ttu-id="c9b2b-220">`ComputeSumAndSumOfSquares` 메서드 내에서 세 개의 개별 변수를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-220">You can also create three discrete variables inside the `ComputeSumAndSumOfSquares` method.</span></span> <span data-ttu-id="c9b2b-221">최종 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-221">The final version is below:</span></span>

[!code-csharp[CleanedTupleVersion](../../samples/snippets/csharp/tuples/tuples/statistics.cs#09_CleanedTupleVersion "After final cleanup")]

<span data-ttu-id="c9b2b-222">이 최종 버전은 이러한 세 개의 값이나 값의 하위 집합이 필요한 모든 메서드에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-222">This final version can be used for any method that needs those three values, or any subset of them.</span></span>

<span data-ttu-id="c9b2b-223">이 언어는 이러한 튜플 반환 메서드의 요소 이름을 관리하기 위한 다른 옵션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-223">The language supports other options in managing the names of the elements in these tuple-returning methods.</span></span>

<span data-ttu-id="c9b2b-224">반환 값 선언에서 필드 이름을 제거하고 명명되지 않은 튜플을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-224">You can remove the field names from the return value declaration and return an unnamed tuple:</span></span>

```csharp
private static (double, double, int) ComputeSumAndSumOfSquares(IEnumerable<double> sequence)
{
    double sum = 0;
    double sumOfSquares = 0;
    int count = 0;

    foreach (var item in sequence)
    {
        count++;
        sum += item;
        sumOfSquares += item * item;
    }

    return (sum, sumOfSquares, count);
}
```

<span data-ttu-id="c9b2b-225">이 튜플의 필드를 `Item1`, `Item2` 및 `Item3`으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-225">You must address the fields of this tuple as `Item1`, `Item2`, and `Item3`.</span></span>
<span data-ttu-id="c9b2b-226">메서드에서 반환된 튜플의 요소에 의미 체계 이름을 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-226">It's recommended that you provide semantic names to the elements of tuples returned from methods.</span></span>

<span data-ttu-id="c9b2b-227">튜플이 매우 유용할 수 있는 또 다른 구문은 최종 결과가 선택하는 개체의 일부 속성만 포함된 프로젝션인 LINQ 쿼리를 작성하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-227">Another idiom where tuples can be very useful is when you are authoring LINQ queries where the final result is a projection that contains some, but not all, of the properties of the objects being selected.</span></span>

<span data-ttu-id="c9b2b-228">기존에는 쿼리 결과를 무명 형식인 개체 시퀀스로 프로젝션했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-228">You would traditionally project the results of the query into a sequence of objects that were an anonymous type.</span></span> <span data-ttu-id="c9b2b-229">이 경우 주로 메서드의 반환 형식에서 무명 형식의 이름을 편리하게 지정할 수 없기 때문에 많은 제한 사항이 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-229">That presented many limitations, primarily because anonymous types could not conveniently be named in the return type for a method.</span></span> <span data-ttu-id="c9b2b-230">`object` 또는 `dynamic`을 결과 형식으로 사용하는 대안의 경우 성능이 훨씬 저하되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-230">Alternatives using `object` or `dynamic` as the type of the result came with significant performance costs.</span></span>

<span data-ttu-id="c9b2b-231">튜플 형식 시퀀스를 반환하는 것은 간단하며, 컴파일 시간에 IDE 도구를 통해 요소 이름 및 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-231">Returning a sequence of a tuple type is easy, and the names and types of the elements are available at compile time and through IDE tools.</span></span>
<span data-ttu-id="c9b2b-232">예를 들어 ToDo 응용 프로그램을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-232">For example, consider a ToDo application.</span></span> <span data-ttu-id="c9b2b-233">다음과 유사한 클래스를 정의하여 할 일 목록의 단일 항목을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-233">You might define a class similar to the following to represent a single entry in the ToDo list:</span></span>

[!code-csharp[ToDoItem](../../samples/snippets/csharp/tuples/tuples/projectionsample.cs#14_ToDoItem "To Do Item")]

<span data-ttu-id="c9b2b-234">모바일 응용 프로그램은 제목만 표시되는 현재 할 일 항목의 간단한 형식을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-234">Your mobile applications may support a compact form of the current ToDo items that only displays the title.</span></span> <span data-ttu-id="c9b2b-235">해당 LINQ 쿼리는 ID와 제목만 포함된 프로젝션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-235">That LINQ query would make a projection that includes only the ID and the title.</span></span> <span data-ttu-id="c9b2b-236">튜플 시퀀스를 반환하는 메서드는 해당 디자인도 매우 잘 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-236">A method that returns a sequence of tuples expresses that design very well:</span></span>

[!code-csharp[QueryReturningTuple](../../samples/snippets/csharp/tuples/tuples/projectionsample.cs#15_QueryReturningTuple "Query returning a tuple")]

> [!NOTE]
> <span data-ttu-id="c9b2b-237">C# 7.1에서는 무명 형식으로 속성 이름을 지정하는 것과 유사한 방식으로 튜플 프로젝션을 통해 요소를 사용하여 명명된 튜플을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-237">In C# 7.1, tuple projections enable you to create named tuples using elements, in a manner similar to the property naming in anonymous types.</span></span> <span data-ttu-id="c9b2b-238">위 코드에서 쿼리 프로젝션의 `select` 문은 `ID` 및 `Title` 요소가 있는 튜플을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-238">In the above code, the `select` statement in the query projection creates a tuple that has elements `ID` and `Title`.</span></span>

<span data-ttu-id="c9b2b-239">명명된 튜플은 시그니처의 일부일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-239">The named tuple can be part of the signature.</span></span> <span data-ttu-id="c9b2b-240">명명된 튜플을 사용하면 컴파일러 및 IDE 도구가 결과를 올바르게 사용하고 있는지에 대한 정적 검사를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-240">It lets the compiler and IDE tools provide static checking that you are using the result correctly.</span></span> <span data-ttu-id="c9b2b-241">명명된 튜플은 정적 형식 정보도 전달하므로 결과 작업을 위해 리플렉션 또는 동적 바인딩과 같은 비용이 많이 드는 런타임 기능을 사용하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-241">The named tuple also carries the static type information so there is no need to use expensive run time features like reflection or dynamic binding to work with the results.</span></span>

## <a name="deconstruction"></a><span data-ttu-id="c9b2b-242">분해</span><span class="sxs-lookup"><span data-stu-id="c9b2b-242">Deconstruction</span></span>

<span data-ttu-id="c9b2b-243">메서드에서 반환된 튜플을 *분해*하여 튜플의 모든 항목을 패키지 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-243">You can unpackage all the items in a tuple by *deconstructing* the tuple returned by a method.</span></span> <span data-ttu-id="c9b2b-244">세 가지 방법으로 튜플을 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-244">There are three different approaches to deconstructing tuples.</span></span>  <span data-ttu-id="c9b2b-245">첫째, 각 필드의 형식을 괄호 안에 명시적으로 선언하여 튜플의 각 요소에 대한 개별 변수를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-245">First, you can explicitly declare the type of each field inside parentheses to create discrete variables for each of the elements in the tuple:</span></span>

[!code-csharp[Deconstruct](../../samples/snippets/csharp/tuples/tuples/statistics.cs#10_Deconstruct "Deconstruct")]

<span data-ttu-id="c9b2b-246">괄호 밖에 `var` 키워드를 사용하여 튜플의 각 필드에 대해 암시적 형식 변수를 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-246">You can also declare implicitly typed variables for each field in a tuple by using the `var` keyword outside the parentheses:</span></span>

[!code-csharp[DeconstructToVar](../../samples/snippets/csharp/tuples/tuples/statistics.cs#11_DeconstructToVar "Deconstruct to Var")]

<span data-ttu-id="c9b2b-247">괄호 안에 일부 또는 모든 변수 선언과 함께 `var` 키워드를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-247">It is also legal to use the `var` keyword with any, or all of the variable declarations inside the parentheses.</span></span> 

```csharp
(double sum, var sumOfSquares, var count) = ComputeSumAndSumOfSquares(sequence);
```

<span data-ttu-id="c9b2b-248">튜플에 있는 모든 필드의 형식이 같은 경우에도 괄호 밖에 특정 형식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-248">Note that you cannot use a specific type outside the parentheses, even if every field in the tuple has the same type.</span></span>

<span data-ttu-id="c9b2b-249">기존 선언을 사용하여 튜플을 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-249">You can deconstruct tuples with existing declarations as well:</span></span>

```csharp
public class Point
{
    public int X { get; set; }
    public int Y { get; set; }

    public Point(int x, int y) => (X, Y) = (x, y);
}
```

> [!WARNING]
>  <span data-ttu-id="c9b2b-250">선언을 사용하여 기존 선언을 괄호 안에 혼합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-250">You cannot mix existing declarations with declarations inside the parentheses.</span></span> <span data-ttu-id="c9b2b-251">예를 들어 다음 `(var x, y) = MyMethod();`는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-251">For instance, the following is not allowed: `(var x, y) = MyMethod();`.</span></span> <span data-ttu-id="c9b2b-252">*x*는 괄호 안에서 선언되고 *y*는 이전에 다른 곳에서 선언됐기 때문에 CS8184 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-252">This produces error CS8184 because *x* is declared inside the parentheses and *y* is previously declared elsewhere.</span></span>

### <a name="deconstructing-user-defined-types"></a><span data-ttu-id="c9b2b-253">사용자 정의 형식 분해</span><span class="sxs-lookup"><span data-stu-id="c9b2b-253">Deconstructing user defined types</span></span>

<span data-ttu-id="c9b2b-254">위와 같이 모든 튜플 형식을 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-254">Any tuple type can be deconstructed as shown above.</span></span> <span data-ttu-id="c9b2b-255">또한 사용자 정의 형식(클래스, 구조체 또는 인터페이스)에서 쉽게 분해를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-255">It's also easy to enable deconstruction on any user defined type (classes, structs, or even interfaces).</span></span>

<span data-ttu-id="c9b2b-256">형식 작성자는 형식을 구성하는 데이터 요소를 나타내는 임의 개수의 `out` 변수에 값을 할당하는 `Deconstruct` 메서드를 하나 이상 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-256">The type author can define one or more `Deconstruct` methods that assign values to any number of `out` variables representing the data elements that make up the type.</span></span> <span data-ttu-id="c9b2b-257">예를 들어 다음 `Person` 형식은 이름과 성을 나타내는 요소로 사용자 개체를 분해하는 `Deconstruct` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-257">For example, the following `Person` type defines a `Deconstruct` method that deconstructs a person object into the elements representing the first name and last name:</span></span>

[!code-csharp[TypeWithDeconstructMethod](../../samples/snippets/csharp/tuples/tuples/person.cs#12_TypeWithDeconstructMethod "Type with a deconstruct method")]

<span data-ttu-id="c9b2b-258">Deconstruct 메서드를 사용하면 `Person`에서 `FirstName` 및 `LastName` 속성을 나타내는 두 문자열에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-258">The deconstruct method enables assignment from a `Person` to two strings, representing the `FirstName` and `LastName` properties:</span></span>

[!code-csharp[Deconstruct Type](../../samples/snippets/csharp/tuples/tuples/program.cs#12A_DeconstructType "Deconstruct a class type")]

<span data-ttu-id="c9b2b-259">직접 작성하지 않은 형식에 대해서도 분해를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-259">You can enable deconstruction even for types you did not author.</span></span>
<span data-ttu-id="c9b2b-260">`Deconstruct` 메서드는 개체의 액세스 가능 데이터 멤버를 패키지 해제하는 확장 메서드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-260">The `Deconstruct` method can be an extension method that unpackages the accessible data members of an object.</span></span> <span data-ttu-id="c9b2b-261">아래 예제에서는 `Person` 형식에서 파생된 `Student` 형식과 `FirstName`, `LastName` 및 `GPA`를 나타내는 세 개의 변수로 `Student`를 분해하는 확장 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-261">The example below shows a `Student` type, derived from the `Person` type, and an extension method that deconstructs a `Student` into three variables, representing the `FirstName`, the `LastName` and the `GPA`:</span></span>

[!code-csharp[ExtensionDeconstructMethod](../../samples/snippets/csharp/tuples/tuples/person.cs#13_ExtensionDeconstructMethod "Type with a deconstruct extension method")]

<span data-ttu-id="c9b2b-262">이제 `Student` 개체에 액세스할 수 있는 `Deconstruct` 메서드 두 개(`Student` 형식에 대해 선언된 확장 메서드 및 `Person` 형식의 멤버)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-262">A `Student` object now has two accessible `Deconstruct` methods: the extension method declared for `Student` types, and the member of the `Person` type.</span></span> <span data-ttu-id="c9b2b-263">둘 다 범위에 있으며, `Student`가 두 변수나 세 변수로 분해될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-263">Both are in scope, and that enables a `Student` to be deconstructed into either two variables or three.</span></span>
<span data-ttu-id="c9b2b-264">세 개의 변수에 학생을 할당하는 경우 이름, 성 및 GPA가 모두 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-264">If you assign a student to three variables, the first name, last name, and GPA are all returned.</span></span> <span data-ttu-id="c9b2b-265">두 개의 변수에 학생을 할당하는 경우 이름과 성만 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-265">If you assign a student to two variables, only the first name and the last name are returned.</span></span>

[!code-csharp[Deconstruct extension method](../../samples/snippets/csharp/tuples/tuples/program.cs#13A_DeconstructExtension "Deconstruct a class type using an extension method")]

<span data-ttu-id="c9b2b-266">클래스 또는 클래스 계층 구조에서 `Deconstruct` 메서드를 여러 개 정의할 때는 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-266">You should be very careful defining multiple `Deconstruct` methods in a class or a class hierarchy.</span></span> <span data-ttu-id="c9b2b-267">`out` 매개 변수 개수가 같은 `Deconstruct` 메서드가 여러 개 있으면 빠르게 모호성이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-267">Multiple `Deconstruct` methods that have the same number of `out` parameters can quickly cause ambiguities.</span></span> <span data-ttu-id="c9b2b-268">호출자가 원하는 `Deconstruct` 메서드를 쉽게 호출하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-268">Callers may not be able to easily call the desired `Deconstruct` method.</span></span>

<span data-ttu-id="c9b2b-269">이 예제에서는 `Person`에 대한 `Deconstruct` 메서드에 두 개의 출력 매개 변수가 있고 `Student`에 대한 `Deconstruct` 메서드에 세 개가 있으므로 모호한 호출이 발생할 가능성이 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-269">In this example, there is minimal chance for an ambiguous call because the `Deconstruct` method for `Person` has two output parameters, and the `Deconstruct` method for `Student` has three.</span></span>

## <a name="conclusion"></a><span data-ttu-id="c9b2b-270">결론</span><span class="sxs-lookup"><span data-stu-id="c9b2b-270">Conclusion</span></span> 

<span data-ttu-id="c9b2b-271">명명된 튜플에 대한 새로운 언어 및 라이브러리 지원을 사용하면 여러 요소를 저장하지만 클래스 및 구조체처럼 동작을 정의하지 않는 데이터 구조를 사용하는 디자인 작업이 훨씬 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-271">The new language and library support for named tuples makes it much easier to work with designs that use data structures that store multiple elements but do not define behavior, as classes and structs do.</span></span> <span data-ttu-id="c9b2b-272">해당 형식에 튜플을 쉽고 간단하게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-272">It's easy and concise to use tuples for those types.</span></span> <span data-ttu-id="c9b2b-273">자세한 `class` 또는 `struct` 구문을 사용하여 형식을 작성하지 않고도 정적 형식 검사의 모든 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-273">You get all the benefits of static type checking, without needing to author types using the more verbose `class` or `struct` syntax.</span></span> <span data-ttu-id="c9b2b-274">그렇지만 `private` 또는 `internal`인 유틸리티 메서드에 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-274">Even so, they are most useful for utility methods that are `private`, or `internal`.</span></span> <span data-ttu-id="c9b2b-275">public 메서드에서 여러 요소가 있는 값을 반환하는 경우 `class` 또는 `struct` 형식인 사용자 정의 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9b2b-275">Create user defined types, either `class` or `struct` types when your public methods return a value that has multiple elements.</span></span>
