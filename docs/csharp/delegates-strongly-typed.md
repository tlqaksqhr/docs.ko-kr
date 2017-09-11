---
title: "강력한 형식의 대리자"
description: "대리자가 필요한 기능을 만들 때 제네릭 대리자 형식을 사용하여 사용자 지정 형식을 선언하는 방법을 알아봅니다."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 564a683d-352b-4e57-8bac-b466529daf6b
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0a8185c21e129c91b2c3ecb1f74f8ce2f75c5db9
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="strongly-typed-delegates"></a><span data-ttu-id="01764-104">강력한 형식의 대리자</span><span class="sxs-lookup"><span data-stu-id="01764-104">Strongly Typed Delegates</span></span>

[<span data-ttu-id="01764-105">이전</span><span class="sxs-lookup"><span data-stu-id="01764-105">Previous</span></span>](delegate-class.md)

<span data-ttu-id="01764-106">이전 문서에서는 `delegate` 키워드를 사용하여 특정 대리자 형식을 만드는 것을 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-106">In the previous article, you saw that you create specific delegate types using the `delegate` keyword.</span></span> 

<span data-ttu-id="01764-107">추상 대리자 클래스는 느슨한 결합 및 호출을 위한 인프라를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="01764-107">The abstract Delegate class provide the infrastructure for loose coupling and invocation.</span></span> <span data-ttu-id="01764-108">대리자 개체에 대한 호출 목록에 추가되는 메서드에 대해 형식 안정성을 도입하고 적용하면 구체적인 대리자 형식이 훨씬 더 유용해집니다.</span><span class="sxs-lookup"><span data-stu-id="01764-108">Concrete Delegate types become much more useful by embracing and enforcing type safety for the methods that are added to the invocation list for a delegate object.</span></span> <span data-ttu-id="01764-109">`delegate` 키워드를 사용하고 구체적인 대리자 형식을 정의하면 컴파일러에서 해당 메서드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="01764-109">When you use the `delegate` keyword and define a concrete delegate type, the compiler generates those methods.</span></span>

<span data-ttu-id="01764-110">실제로 이렇게 하면 다른 메서드 시그니처가 필요할 때마다 새로운 대리자 형식이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="01764-110">In practice, this would lead to creating new delegate types whenever you need a different method signature.</span></span> <span data-ttu-id="01764-111">일정 시간이 지나면 이 작업은 지루해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-111">This work could get tedious after a time.</span></span> <span data-ttu-id="01764-112">모든 새 기능에는 새 대리자 형식이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="01764-112">Every new feature requires new delegate types.</span></span>

<span data-ttu-id="01764-113">다행히도 반드시 필요하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-113">Thankfully, this isn't necessary.</span></span> <span data-ttu-id="01764-114">.NET Core 프레임워크에는 대리자 형식이 필요할 때마다 재사용할 수 있는 여러 가지 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-114">The .NET Core framework contains several types that you can reuse whenever you need delegate types.</span></span> <span data-ttu-id="01764-115">이러한 형식은 [제네릭](programming-guide/generics/index.md) 정의이므로 새 메서드 선언이 필요할 때 사용자 지정을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-115">These are [generic](programming-guide/generics/index.md) definitions so you can declare customizations when you need new method declarations.</span></span> 

<span data-ttu-id="01764-116">이러한 형식 중 첫 번째는 @System.Action 형식이며 여러 가지 변형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-116">The first of these types is the @System.Action type, and several variations:</span></span>

```csharp
public delegate void Action();
public delegate void Action<in T>(T arg);
public delegate void Action<in T1, in T2>(T1 arg1, T2 arg2);
// Other variations removed for brevity.
```

<span data-ttu-id="01764-117">제네릭 형식 인수에 대한 `in` 한정자는 공변성(Covariance)에 대한 문서에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="01764-117">The `in` modifier on the generic type argument is covered in the article on covariance.</span></span>

<span data-ttu-id="01764-118">@System.Action%6016 같이 최대 16개의 인수가 포함된 `Action` 대리자의 변형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-118">There are variations of the `Action` delegate that contain up to 16 arguments such as @System.Action%6016 .</span></span>
<span data-ttu-id="01764-119">이러한 정의에서는 각 대리자 인수에 대해 서로 다른 제네릭 인수를 사용하여 최대한의 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="01764-119">It's important that these definitions use different generic arguments for each of the delegate arguments: That gives you maximum flexibility.</span></span> <span data-ttu-id="01764-120">메서드 인수는 같은 형식일 필요가 없지만 같은 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-120">The method arguments need not be, but may be, the same type.</span></span>

<span data-ttu-id="01764-121">void 반환 형식을 갖는 대리자 형식에 대해 `Action` 형식 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01764-121">Use one of the `Action` types for any delegate type that has a void return type.</span></span>

<span data-ttu-id="01764-122">또한 프레임워크에는 값을 반환하는 대리자 형식에 사용할 수 있는 여러 가지 제네릭 대리자 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="01764-122">The framework also includes several generic delegate types that you can use for delegate types that return values:</span></span>

```csharp
public delegate TResult Func<out TResult>();
public delegate TResult Func<in T1, out TResult>(T1 arg);
public delegate TResult Func<in T1, in T2, out TResult>(T1 arg1, T2 arg2);
// Other variations removed for brevity
```

<span data-ttu-id="01764-123">결과 제네릭 형식 인수에 대한 `out` 한정자는 공변성(Covariance)에 대한 문서에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="01764-123">The `out` modifier on the result generic type argument is covered in the article on covariance.</span></span>

<span data-ttu-id="01764-124">@System.Func%6017 같이 최대 16개의 입력 인수가 포함된 `Func` 대리자의 변형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-124">There are variations of the `Func` delegate with up to 16 input arguments such as @System.Func%6017 .</span></span>
<span data-ttu-id="01764-125">규칙에 따라 결과의 형식은 모든 `Func` 선언에서 항상 마지막 형식 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="01764-125">The type of the result is always the last type parameter in all the `Func` declarations, by convention.</span></span>

<span data-ttu-id="01764-126">값을 반환하는 모든 대리자 형식에 대해 `Func` 형식 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01764-126">Use one of the `Func` types for any delegate type that returns a value.</span></span>

<span data-ttu-id="01764-127">또한 단일 값에 대한 테스트를 반환하는 대리자에 대해 특수화된 @System.Predicate%601 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-127">There's also a specialized @System.Predicate%601 type for a delegate that returns a test on a single value:</span></span>

```csharp
public delegate bool Predicate<in T>(T obj);
```

<span data-ttu-id="01764-128">모든 `Predicate` 형식에 대해 구조적으로 동일한 `Func` 형식이 있다는 것을 알 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-128">You may notice that for any `Predicate` type, a structurally equivalent `Func` type exists For example:</span></span>

```csharp
Func<string, bool> TestForString;
Predicate<string> AnotherTestForString;
```

<span data-ttu-id="01764-129">이러한 두 형식이 동일하다고 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-129">You might think these two types are equivalent.</span></span> <span data-ttu-id="01764-130">그러나 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-130">They are not.</span></span>
<span data-ttu-id="01764-131">이러한 두 변수는 서로 교환해서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-131">These two variables cannot be used interchangeably.</span></span> <span data-ttu-id="01764-132">한 형식의 변수에 다른 형식을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-132">A variable of one type cannot be assigned the other type.</span></span> <span data-ttu-id="01764-133">C# 형식 시스템에서는 구조체가 아니라 정의된 형식의 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01764-133">The C# type system uses the names of the defined types, not the structure.</span></span>

<span data-ttu-id="01764-134">.NET Core 라이브러리의 이러한 모든 대리자 형식 정의는 대리자가 필요한 새 기능에 대해 새 대리자 형식을 정의할 필요가 없음을 의미해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01764-134">All these delegate type definitions in the .NET Core Library should mean that you do not need to define a new delegate type for any new feature you create that requires delegates.</span></span> <span data-ttu-id="01764-135">이러한 제네릭 정의는 대부분의 상황에서 필요한 모든 대리자 형식을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01764-135">These generic definitions should provide all the delegate types you need under most situations.</span></span> <span data-ttu-id="01764-136">필수 형식 매개 변수를 사용하여 이러한 형식 중 하나를 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-136">You can simply instantiate one of these types with the required type parameters.</span></span> <span data-ttu-id="01764-137">제네릭으로 만들 수 있는 알고리즘의 경우 이러한 대리자를 제네릭 형식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01764-137">In the case of algorithms that can be made generic, these delegates can be used as generic types.</span></span> 

<span data-ttu-id="01764-138">그러면 시간이 절약되고 대리자로 작업하기 위해 만들어야 하는 새로운 형식 수가 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="01764-138">This should save time, and minimize the number of new types that you need to create in order to work with delegates.</span></span>

<span data-ttu-id="01764-139">다음 문서에서는 실제로 대리자로 작업하기 위한 몇 가지 일반적인 패턴이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="01764-139">In the next article, you'll see several common patterns for working with delegates in practice.</span></span>

[<span data-ttu-id="01764-140">다음</span><span class="sxs-lookup"><span data-stu-id="01764-140">Next</span></span>](delegates-patterns.md)

