---
title: 반복기
description: 기본 제공 C# 반복기를 사용하는 방법 및 사용자 지정 반복기 메서드를 만드는 방법을 알아봅니다.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 5cf36f45-f91a-4fca-a0b7-87f233e108e9
ms.openlocfilehash: 403a286e9b1168b9e913b3cb2764e7fe262017d4
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2018
---
# <a name="iterators"></a><span data-ttu-id="707d6-104">반복기</span><span class="sxs-lookup"><span data-stu-id="707d6-104">Iterators</span></span>

<span data-ttu-id="707d6-105">작성하는 거의 모든 프로그램에서 컬렉션을 반복해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-105">Almost every program you write will have some need to iterate over a collection.</span></span> <span data-ttu-id="707d6-106">컬렉션에 있는 모든 항목을 조사하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-106">You'll write code that examines every item in a collection.</span></span> 

<span data-ttu-id="707d6-107">또한 해당 클래스의 요소에 대해 반복기를 생성하는 메서드인 반복기 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-107">You'll also create iterator methods which are methods that produces an iterator for the elements of that class.</span></span> <span data-ttu-id="707d6-108">이러한 메서드는 다음과 같은 경우에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-108">These can be used for:</span></span>

+ <span data-ttu-id="707d6-109">컬렉션의 각 항목에 대한 작업 수행.</span><span class="sxs-lookup"><span data-stu-id="707d6-109">Performing an action on each item in a collection.</span></span>
+ <span data-ttu-id="707d6-110">사용자 지정 컬렉션 열거.</span><span class="sxs-lookup"><span data-stu-id="707d6-110">Enumerating a custom collection.</span></span>
+ <span data-ttu-id="707d6-111">[LINQ](linq/index.md) 또는 다른 라이브러리 확장.</span><span class="sxs-lookup"><span data-stu-id="707d6-111">Extending [LINQ](linq/index.md) or other libraries.</span></span>
+ <span data-ttu-id="707d6-112">데이터가 반복기 메서드를 통해 효율적으로 흐르는 데이터 파이프라인 만들기.</span><span class="sxs-lookup"><span data-stu-id="707d6-112">Creating a data pipeline where data flows efficiently through iterator methods.</span></span>

<span data-ttu-id="707d6-113">C# 언어는 이러한 두 시나리오에 대한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-113">The C# language provides features for both these scenarios.</span></span> <span data-ttu-id="707d6-114">이 문서에서는 해당 기능에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-114">This article provides an overview of those features.</span></span>

<span data-ttu-id="707d6-115">이 자습서는 여러 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-115">This tutorial has multiple steps.</span></span> <span data-ttu-id="707d6-116">각 단계 후에 응용 프로그램을 실행하고 진행 상황을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-116">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="707d6-117">이 항목에 대한 [전체 샘플을 보거나 다운로드](https://github.com/dotnet/samples/blob/master/csharp/iterators)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-117">You can also [view or download the completed sample](https://github.com/dotnet/samples/blob/master/csharp/iterators) for this topic.</span></span> <span data-ttu-id="707d6-118">다운로드 지침은 [샘플 및 자습서](../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="707d6-118">For download instructions, see [Samples and Tutorials](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="iterating-with-foreach"></a><span data-ttu-id="707d6-119">foreach로 반복 처리</span><span class="sxs-lookup"><span data-stu-id="707d6-119">Iterating with foreach</span></span>

<span data-ttu-id="707d6-120">컬렉션 열거는 간단합니다. `foreach` 키워드는 컬렉션을 열거하여 컬렉션의 각 요소에 대해 포함된 문을 한 번 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-120">Enumerating a collection is simple: The `foreach` keyword enumerates a collection, executing the embedded statement once for each element in the collection:</span></span>
 
```csharp
foreach (var item in collection)
{
   Console.WriteLine(item.ToString());
}
```

<span data-ttu-id="707d6-121">아주 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-121">That's all there is to it.</span></span> <span data-ttu-id="707d6-122">컬렉션의 모든 내용을 반복하려면 `foreach` 문만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-122">To iterate over all the contents of a collection, the `foreach` statement is all you need.</span></span> <span data-ttu-id="707d6-123">하지만 `foreach` 문이 마법은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-123">The `foreach` statement isn't magic, though.</span></span> <span data-ttu-id="707d6-124">이 문은 컬렉션을 반복하는 데 필요한 코드를 생성하기 위해 .NET Core 라이브러리에 정의된 두 개의 제네릭 인터페이스인 `IEnumerable<T>` 및 `IEnumerator<T>`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-124">It relies on two generic interfaces defined in the .NET core library in order to generate the code necessary to iterate a collection: `IEnumerable<T>` and `IEnumerator<T>`.</span></span> <span data-ttu-id="707d6-125">이 메커니즘은 아래에 더 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-125">This mechanism is explained in more detail below.</span></span>

<span data-ttu-id="707d6-126">이러한 인터페이스 둘 다에는 제네릭이 아닌 인터페이스 `IEnumerable` 및 `IEnumerator`도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-126">Both of these interfaces also have non-generic counterparts: `IEnumerable` and `IEnumerator`.</span></span> <span data-ttu-id="707d6-127">최신 코드에는 [제네릭](programming-guide/generics/index.md) 버전이 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-127">The [generic](programming-guide/generics/index.md) versions are preferred for modern code.</span></span>

## <a name="enumeration-sources-with-iterator-methods"></a><span data-ttu-id="707d6-128">반복기 메서드를 사용하는 열거형 소스</span><span class="sxs-lookup"><span data-stu-id="707d6-128">Enumeration sources with iterator methods</span></span>

<span data-ttu-id="707d6-129">C# 언어의 또 다른 유용한 기능을 통해 열거형 소스를 만드는 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-129">Another great feature of the C# language enables you to build methods that create a source for an enumeration.</span></span> <span data-ttu-id="707d6-130">이러한 메서드를 *반복기 메서드*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-130">These are referred to as *iterator methods*.</span></span> <span data-ttu-id="707d6-131">반복기 메서드는 요청될 때 시퀀스에서 개체를 생성하는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-131">An iterator method defines how to generate the objects in a sequence when requested.</span></span> <span data-ttu-id="707d6-132">`yield return` 상황별 키워드를 사용하여 반복기 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-132">You use the `yield return` contextual keywords to define an iterator method.</span></span> 

<span data-ttu-id="707d6-133">이 메서드를 작성하여 0에서 9 사이의 정수 시퀀스를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-133">You could write this method to produce the sequence of integers from 0 through 9:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    yield return 0;
    yield return 1;
    yield return 2;
    yield return 3;
    yield return 4;
    yield return 5;
    yield return 6;
    yield return 7;
    yield return 8;
    yield return 9;
}
```

<span data-ttu-id="707d6-134">위의 코드에서는 반복기 메서드에서 여러 개의 고유 `yield return` 문을 사용할 수 있다는 사실을 강조하기 위해 고유 `yield return` 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-134">The code above shows distinct `yield return` statements to highlight the fact that you can use multiple discrete `yield return` statements in an iterator method.</span></span>
<span data-ttu-id="707d6-135">다른 언어 구문을 사용하여 반복기 메서드의 코드를 단순화할 수 있으며 종종 그렇게 합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-135">You can (and often do) use other language constructs to simplify the code of an iterator method.</span></span> <span data-ttu-id="707d6-136">아래의 메서드 정의는 정확히 동일한 시퀀스의 숫자를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-136">The method definition below produces the exact same sequence of numbers:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index++ < 10)
        yield return index;
}
```

<span data-ttu-id="707d6-137">둘 중 하나를 결정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-137">You don't have to decide one or the other.</span></span> <span data-ttu-id="707d6-138">메서드의 요구를 충족하는 데 필요한 만큼 `yield return` 문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-138">You can have as many `yield return` statements as necessary to meet the needs of your method:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index++ < 10)
        yield return index;
        
    yield return 50;
    
    index = 100;
    while (index++ < 110)
        yield return index;
}
```

<span data-ttu-id="707d6-139">이 구문은 기본 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-139">That's the basic syntax.</span></span> <span data-ttu-id="707d6-140">반복기 메서드를 작성하는 실제 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-140">Let's consider a real world example where you would write an iterator method.</span></span> <span data-ttu-id="707d6-141">IoT 프로젝트를 진행하고 있고 장치 센서는 매우 큰 데이터 스트림을 생성한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-141">Imagine you're on an IoT project and the device sensors generate a very large stream of data.</span></span> <span data-ttu-id="707d6-142">데이터를 파악하려면 N번째 데이터 요소마다 샘플링하는 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-142">To get a feel for the data, you might write a method that samples every Nth data element.</span></span> <span data-ttu-id="707d6-143">이 작은 반복기 메서드면 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-143">This small iterator method does the trick:</span></span>

```csharp
public static IEnumerable<T> Sample(this IEnumerable<T> sourceSequence, int interval)
{
    int index = 0;
    foreach (T item in sourceSequence)
    {
        if (index++ % interval == 0)
            yield return item;
    }
}
```

<span data-ttu-id="707d6-144">반복기 메서드에는 한 가지 중요한 제한이 있습니다. `return` 문과 `yield return` 문 둘 다를 동일한 메서드에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-144">There is one important restriction on iterator methods: you can't have both a `return` statement and a `yield return` statement in the same method.</span></span> <span data-ttu-id="707d6-145">다음 코드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-145">The following will not compile:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index++ < 10)
        yield return index;
        
    yield return 50;
   
    // generates a compile time error: 
    var items = new int[] {100, 101, 102, 103, 104, 105, 106, 107, 108, 109 };
    return items;  
}
```

<span data-ttu-id="707d6-146">일반적으로 이 제한은 문제가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-146">This restriction normally isn't a problem.</span></span> <span data-ttu-id="707d6-147">메서드 전체에서 `yield return`을 사용하거나, 원래 메서드를 여러 메서드로 분리하여 일부는 `return`을 사용하고 일부는 `yield return`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-147">You have a choice of either using `yield return` throughout the method, or separating the original method into multiple methods, some using `return`, and some using `yield return`.</span></span>

<span data-ttu-id="707d6-148">모든 위치에서 `yield return`을 사용하기 위해 마지막 메서드를 약간 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-148">You can modify the last method slightly to use `yield return` everywhere:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index++ < 10)
        yield return index;
        
    yield return 50;
   
    var items = new int[] {100, 101, 102, 103, 104, 105, 106, 107, 108, 109 };
    foreach (var item in items)
        yield return item;
}
```
 
<span data-ttu-id="707d6-149">경우에 따라 반복기 메서드를 두 개의 다른 메서드로 분할하는 것이 정답일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-149">Sometimes, the right answer is to split an iterator method into two different methods.</span></span> <span data-ttu-id="707d6-150">하나는 `return`을 사용하고 다른 하나는 `yield return`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-150">One that uses `return`, and a second that uses `yield return`.</span></span> <span data-ttu-id="707d6-151">부울 인수에 따라 빈 컬렉션 또는 처음 5개의 홀수를 반환하려는 상황을 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="707d6-151">Consider a situation where you might want to return an empty collection, or the first 5 odd numbers, based on a boolean argument.</span></span> <span data-ttu-id="707d6-152">다음과 같은 두 메서드로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-152">You could write that as these two methods:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitOddNumbers(bool getCollection)
{
    if (getCollection == false)
        return new int[0];
    else
        return IteratorMethod();
}

private IEnumerable<int> IteratorMethod()
{
    int index = 0;
    while (index++ < 10)
        if (index % 2 == 1)
            yield return index;
}
```
 
<span data-ttu-id="707d6-153">위의 메서드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="707d6-153">Look at the methods above.</span></span> <span data-ttu-id="707d6-154">첫 번째 메서드는 표준 `return` 문을 사용하여 빈 컬렉션 또는 두 번째 메서드에서 만든 반복기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-154">The first uses the standard `return` statement to return either an empty collection, or the iterator created by the second method.</span></span> <span data-ttu-id="707d6-155">두 번째 메서드는 `yield return` 문을 사용하여 요청된 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-155">The second method uses the `yield return` statement to create the requested sequence.</span></span>

## <a name="deeper-dive-into-foreach"></a><span data-ttu-id="707d6-156">`foreach` 심층 분석</span><span class="sxs-lookup"><span data-stu-id="707d6-156">Deeper Dive into `foreach`</span></span>

<span data-ttu-id="707d6-157">`foreach` 문은 `IEnumerable<T>` 및 `IEnumerator<T>` 인터페이스를 사용하여 컬렉션의 모든 요소에서 반복하는 표준 관용구로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-157">The `foreach` statement expands into a standard idiom that uses the `IEnumerable<T>` and `IEnumerator<T>` interfaces to iterate across all elements of a collection.</span></span> <span data-ttu-id="707d6-158">또한 개발자가 리소스를 제대로 관리하지 못해 발생하는 오류를 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-158">It also  minimizes errors developers make by not properly managing resources.</span></span> 

<span data-ttu-id="707d6-159">컴파일러는 첫 번째 예제에 표시된 `foreach` 루프를 다음과 유사한 구문으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-159">The compiler translates the `foreach` loop shown in the first example into something similar to this construct:</span></span>

```csharp
IEnumerator<int> enumerator = collection.GetEnumerator();
while (enumerator.MoveNext())
{
    var item = enumerator.Current;
    Console.WriteLine(item.ToString());
}
```

<span data-ttu-id="707d6-160">위의 구문은 버전 5 이상의 C# 컴파일러에서 생성된 코드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-160">The construct above represents the code generated by the C# compiler as of version 5 and above.</span></span> <span data-ttu-id="707d6-161">버전 5 이전에는 `item` 변수의 범위가 달랐습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-161">Prior to version 5, the `item` variable had a different scope:</span></span>

```csharp
// C# versions 1 through 4:
IEnumerator<int> enumerator = collection.GetEnumerator();
int item = default(int);
while (enumerator.MoveNext())
{
    item = enumerator.Current;
    Console.WriteLine(item.ToString());
}
```

<span data-ttu-id="707d6-162">이전 동작에서는 람다 식과 관련된 버그를 진단하기가 어렵고 미묘할 수 있기 때문에 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-162">This was changed because the earlier behavior could lead to subtle and hard to diagnose bugs involving lambda expressions.</span></span> <span data-ttu-id="707d6-163">자세한 내용은 [람다 식](lambda-expressions.md)에 대한 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="707d6-163">See the section on [lambda expressions](lambda-expressions.md) for more information.</span></span> 

<span data-ttu-id="707d6-164">컴파일러에서 생성되는 정확한 코드는 약간 더 복잡하며 `GetEnumerator()`에서 반환된 개체가 `IDisposable` 인터페이스를 구현하는 상황을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-164">The exact code generated by the compiler is somewhat more complicated, and handles situations where the object returned by `GetEnumerator()` implements the `IDisposable` interface.</span></span> <span data-ttu-id="707d6-165">전체 확장에서는 다음과 더 유사한 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-165">The full expansion generates code more like this:</span></span>

```csharp
{
    var enumerator = collection.GetEnumerator();
    try 
    {
        while (enumerator.MoveNext())
        {
            var item = enumerator.Current;
            Console.WriteLine(item.ToString());
        }
    } finally 
    {
        // dispose of enumerator.
    }
}
```

<span data-ttu-id="707d6-166">열거자가 삭제되는 방식의 `enumerator` 형식의 특성에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-166">The manner in which the enumerator is disposed of depends on the characteristics of the type of `enumerator`.</span></span> <span data-ttu-id="707d6-167">일반적인 경우 `finally` 절은 다음과 같이 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-167">In the general case, the `finally` clause expands to:</span></span>

```csharp
finally 
{
   (enumerator as IDisposable)?.Dispose();
} 
```

<span data-ttu-id="707d6-168">그러나 `enumerator`의 형식이 sealed 형식이고 `enumerator`의 형식에서 `IDisposable`로의 암시적 변환이 없는 경우 `finally` 절은 빈 블록으로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-168">However, if the type of `enumerator` is a sealed type and there is no implicit conversion from the type of `enumerator` to `IDisposable`, the `finally` clause expands to an empty block:</span></span>
```csharp
finally 
{
} 
```

<span data-ttu-id="707d6-169">`enumerator`의 형식에서 `IDisposable`로의 암시적 변환이 있고 `enumerator` 형식이 nullable이 아닌 값 형식인 경우 `finally` 절은 다음과 같이 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-169">If there is an implicit conversion from the type of `enumerator` to `IDisposable`, and `enumerator` is a non-nullable value type, the `finally` clause expands to:</span></span>

```csharp
finally 
{
   ((IDisposable)enumerator).Dispose();
} 
```

<span data-ttu-id="707d6-170">다행히도 이러한 세부 정보를 모두 기억할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-170">Thankfully, you don't need to remember all these details.</span></span> <span data-ttu-id="707d6-171">`foreach` 문에서 이러한 차이를 모두 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-171">The `foreach` statement handles all those nuances for you.</span></span> <span data-ttu-id="707d6-172">컴파일러는 이러한 구문에 대한 올바른 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="707d6-172">The compiler will generate the correct code for any of these constructs.</span></span> 


