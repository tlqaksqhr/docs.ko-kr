---
title: 반복기
description: 기본 제공 C# 반복기를 사용하는 방법 및 사용자 지정 반복기 메서드를 만드는 방법을 알아봅니다.
ms.date: 06/20/2016
ms.assetid: 5cf36f45-f91a-4fca-a0b7-87f233e108e9
ms.openlocfilehash: d9139f565fb1e426cc1b8cef530187877bdde0e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218347"
---
# <a name="iterators"></a><span data-ttu-id="d7fb0-103">반복기</span><span class="sxs-lookup"><span data-stu-id="d7fb0-103">Iterators</span></span>

<span data-ttu-id="d7fb0-104">작성하는 거의 모든 프로그램에서 컬렉션을 반복해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-104">Almost every program you write will have some need to iterate over a collection.</span></span> <span data-ttu-id="d7fb0-105">컬렉션에 있는 모든 항목을 조사하는 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-105">You'll write code that examines every item in a collection.</span></span> 

<span data-ttu-id="d7fb0-106">또한 해당 클래스의 요소에 대해 반복기를 생성하는 메서드인 반복기 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-106">You'll also create iterator methods which are methods that produces an iterator for the elements of that class.</span></span> <span data-ttu-id="d7fb0-107">이러한 메서드는 다음과 같은 경우에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-107">These can be used for:</span></span>

+ <span data-ttu-id="d7fb0-108">컬렉션의 각 항목에 대한 작업 수행.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-108">Performing an action on each item in a collection.</span></span>
+ <span data-ttu-id="d7fb0-109">사용자 지정 컬렉션 열거.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-109">Enumerating a custom collection.</span></span>
+ <span data-ttu-id="d7fb0-110">[LINQ](linq/index.md) 또는 다른 라이브러리 확장.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-110">Extending [LINQ](linq/index.md) or other libraries.</span></span>
+ <span data-ttu-id="d7fb0-111">데이터가 반복기 메서드를 통해 효율적으로 흐르는 데이터 파이프라인 만들기.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-111">Creating a data pipeline where data flows efficiently through iterator methods.</span></span>

<span data-ttu-id="d7fb0-112">C# 언어는 이러한 두 시나리오에 대한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-112">The C# language provides features for both these scenarios.</span></span> <span data-ttu-id="d7fb0-113">이 문서에서는 해당 기능에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-113">This article provides an overview of those features.</span></span>

<span data-ttu-id="d7fb0-114">이 자습서는 여러 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-114">This tutorial has multiple steps.</span></span> <span data-ttu-id="d7fb0-115">각 단계 후에 응용 프로그램을 실행하고 진행 상황을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-115">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="d7fb0-116">이 항목에 대한 [전체 샘플을 보거나 다운로드](https://github.com/dotnet/samples/blob/master/csharp/iterators)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-116">You can also [view or download the completed sample](https://github.com/dotnet/samples/blob/master/csharp/iterators) for this topic.</span></span> <span data-ttu-id="d7fb0-117">다운로드 지침은 [샘플 및 자습서](../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-117">For download instructions, see [Samples and Tutorials](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="iterating-with-foreach"></a><span data-ttu-id="d7fb0-118">foreach로 반복 처리</span><span class="sxs-lookup"><span data-stu-id="d7fb0-118">Iterating with foreach</span></span>

<span data-ttu-id="d7fb0-119">컬렉션 열거는 간단합니다. `foreach` 키워드는 컬렉션을 열거하여 컬렉션의 각 요소에 대해 포함된 문을 한 번 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-119">Enumerating a collection is simple: The `foreach` keyword enumerates a collection, executing the embedded statement once for each element in the collection:</span></span>
 
```csharp
foreach (var item in collection)
{
   Console.WriteLine(item.ToString());
}
```

<span data-ttu-id="d7fb0-120">아주 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-120">That's all there is to it.</span></span> <span data-ttu-id="d7fb0-121">컬렉션의 모든 내용을 반복하려면 `foreach` 문만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-121">To iterate over all the contents of a collection, the `foreach` statement is all you need.</span></span> <span data-ttu-id="d7fb0-122">하지만 `foreach` 문이 마법은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-122">The `foreach` statement isn't magic, though.</span></span> <span data-ttu-id="d7fb0-123">이 문은 컬렉션을 반복하는 데 필요한 코드를 생성하기 위해 .NET Core 라이브러리에 정의된 두 개의 제네릭 인터페이스인 `IEnumerable<T>` 및 `IEnumerator<T>`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-123">It relies on two generic interfaces defined in the .NET core library in order to generate the code necessary to iterate a collection: `IEnumerable<T>` and `IEnumerator<T>`.</span></span> <span data-ttu-id="d7fb0-124">이 메커니즘은 아래에 더 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-124">This mechanism is explained in more detail below.</span></span>

<span data-ttu-id="d7fb0-125">이러한 인터페이스 둘 다에는 제네릭이 아닌 인터페이스 `IEnumerable` 및 `IEnumerator`도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-125">Both of these interfaces also have non-generic counterparts: `IEnumerable` and `IEnumerator`.</span></span> <span data-ttu-id="d7fb0-126">최신 코드에는 [제네릭](programming-guide/generics/index.md) 버전이 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-126">The [generic](programming-guide/generics/index.md) versions are preferred for modern code.</span></span>

## <a name="enumeration-sources-with-iterator-methods"></a><span data-ttu-id="d7fb0-127">반복기 메서드를 사용하는 열거형 소스</span><span class="sxs-lookup"><span data-stu-id="d7fb0-127">Enumeration sources with iterator methods</span></span>

<span data-ttu-id="d7fb0-128">C# 언어의 또 다른 유용한 기능을 통해 열거형 소스를 만드는 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-128">Another great feature of the C# language enables you to build methods that create a source for an enumeration.</span></span> <span data-ttu-id="d7fb0-129">이러한 메서드를 *반복기 메서드*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-129">These are referred to as *iterator methods*.</span></span> <span data-ttu-id="d7fb0-130">반복기 메서드는 요청될 때 시퀀스에서 개체를 생성하는 방법을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-130">An iterator method defines how to generate the objects in a sequence when requested.</span></span> <span data-ttu-id="d7fb0-131">`yield return` 상황별 키워드를 사용하여 반복기 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-131">You use the `yield return` contextual keywords to define an iterator method.</span></span> 

<span data-ttu-id="d7fb0-132">이 메서드를 작성하여 0에서 9 사이의 정수 시퀀스를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-132">You could write this method to produce the sequence of integers from 0 through 9:</span></span>

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

<span data-ttu-id="d7fb0-133">위의 코드에서는 반복기 메서드에서 여러 개의 고유 `yield return` 문을 사용할 수 있다는 사실을 강조하기 위해 고유 `yield return` 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-133">The code above shows distinct `yield return` statements to highlight the fact that you can use multiple discrete `yield return` statements in an iterator method.</span></span>
<span data-ttu-id="d7fb0-134">다른 언어 구문을 사용하여 반복기 메서드의 코드를 단순화할 수 있으며 종종 그렇게 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-134">You can (and often do) use other language constructs to simplify the code of an iterator method.</span></span> <span data-ttu-id="d7fb0-135">아래의 메서드 정의는 정확히 동일한 시퀀스의 숫자를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-135">The method definition below produces the exact same sequence of numbers:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index++ < 10)
        yield return index;
}
```

<span data-ttu-id="d7fb0-136">둘 중 하나를 결정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-136">You don't have to decide one or the other.</span></span> <span data-ttu-id="d7fb0-137">메서드의 요구를 충족하는 데 필요한 만큼 `yield return` 문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-137">You can have as many `yield return` statements as necessary to meet the needs of your method:</span></span>

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

<span data-ttu-id="d7fb0-138">이 구문은 기본 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-138">That's the basic syntax.</span></span> <span data-ttu-id="d7fb0-139">반복기 메서드를 작성하는 실제 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-139">Let's consider a real world example where you would write an iterator method.</span></span> <span data-ttu-id="d7fb0-140">IoT 프로젝트를 진행하고 있고 장치 센서는 매우 큰 데이터 스트림을 생성한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-140">Imagine you're on an IoT project and the device sensors generate a very large stream of data.</span></span> <span data-ttu-id="d7fb0-141">데이터를 파악하려면 N번째 데이터 요소마다 샘플링하는 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-141">To get a feel for the data, you might write a method that samples every Nth data element.</span></span> <span data-ttu-id="d7fb0-142">이 작은 반복기 메서드면 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-142">This small iterator method does the trick:</span></span>

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

<span data-ttu-id="d7fb0-143">반복기 메서드에는 한 가지 중요한 제한이 있습니다. `return` 문과 `yield return` 문 둘 다를 동일한 메서드에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-143">There is one important restriction on iterator methods: you can't have both a `return` statement and a `yield return` statement in the same method.</span></span> <span data-ttu-id="d7fb0-144">다음 코드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-144">The following will not compile:</span></span>

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

<span data-ttu-id="d7fb0-145">일반적으로 이 제한은 문제가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-145">This restriction normally isn't a problem.</span></span> <span data-ttu-id="d7fb0-146">메서드 전체에서 `yield return`을 사용하거나, 원래 메서드를 여러 메서드로 분리하여 일부는 `return`을 사용하고 일부는 `yield return`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-146">You have a choice of either using `yield return` throughout the method, or separating the original method into multiple methods, some using `return`, and some using `yield return`.</span></span>

<span data-ttu-id="d7fb0-147">모든 위치에서 `yield return`을 사용하기 위해 마지막 메서드를 약간 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-147">You can modify the last method slightly to use `yield return` everywhere:</span></span>

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
 
<span data-ttu-id="d7fb0-148">경우에 따라 반복기 메서드를 두 개의 다른 메서드로 분할하는 것이 정답일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-148">Sometimes, the right answer is to split an iterator method into two different methods.</span></span> <span data-ttu-id="d7fb0-149">하나는 `return`을 사용하고 다른 하나는 `yield return`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-149">One that uses `return`, and a second that uses `yield return`.</span></span> <span data-ttu-id="d7fb0-150">부울 인수에 따라 빈 컬렉션 또는 처음 5개의 홀수를 반환하려는 상황을 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-150">Consider a situation where you might want to return an empty collection, or the first 5 odd numbers, based on a boolean argument.</span></span> <span data-ttu-id="d7fb0-151">다음과 같은 두 메서드로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-151">You could write that as these two methods:</span></span>

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
 
<span data-ttu-id="d7fb0-152">위의 메서드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-152">Look at the methods above.</span></span> <span data-ttu-id="d7fb0-153">첫 번째 메서드는 표준 `return` 문을 사용하여 빈 컬렉션 또는 두 번째 메서드에서 만든 반복기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-153">The first uses the standard `return` statement to return either an empty collection, or the iterator created by the second method.</span></span> <span data-ttu-id="d7fb0-154">두 번째 메서드는 `yield return` 문을 사용하여 요청된 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-154">The second method uses the `yield return` statement to create the requested sequence.</span></span>

## <a name="deeper-dive-into-foreach"></a><span data-ttu-id="d7fb0-155">`foreach` 심층 분석</span><span class="sxs-lookup"><span data-stu-id="d7fb0-155">Deeper Dive into `foreach`</span></span>

<span data-ttu-id="d7fb0-156">`foreach` 문은 `IEnumerable<T>` 및 `IEnumerator<T>` 인터페이스를 사용하여 컬렉션의 모든 요소에서 반복하는 표준 관용구로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-156">The `foreach` statement expands into a standard idiom that uses the `IEnumerable<T>` and `IEnumerator<T>` interfaces to iterate across all elements of a collection.</span></span> <span data-ttu-id="d7fb0-157">또한 개발자가 리소스를 제대로 관리하지 못해 발생하는 오류를 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-157">It also  minimizes errors developers make by not properly managing resources.</span></span> 

<span data-ttu-id="d7fb0-158">컴파일러는 첫 번째 예제에 표시된 `foreach` 루프를 다음과 유사한 구문으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-158">The compiler translates the `foreach` loop shown in the first example into something similar to this construct:</span></span>

```csharp
IEnumerator<int> enumerator = collection.GetEnumerator();
while (enumerator.MoveNext())
{
    var item = enumerator.Current;
    Console.WriteLine(item.ToString());
}
```

<span data-ttu-id="d7fb0-159">위의 구문은 버전 5 이상의 C# 컴파일러에서 생성된 코드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-159">The construct above represents the code generated by the C# compiler as of version 5 and above.</span></span> <span data-ttu-id="d7fb0-160">버전 5 이전에는 `item` 변수의 범위가 달랐습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-160">Prior to version 5, the `item` variable had a different scope:</span></span>

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

<span data-ttu-id="d7fb0-161">이전 동작에서는 람다 식과 관련된 버그를 진단하기가 어렵고 미묘할 수 있기 때문에 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-161">This was changed because the earlier behavior could lead to subtle and hard to diagnose bugs involving lambda expressions.</span></span> <span data-ttu-id="d7fb0-162">자세한 내용은 [람다 식](lambda-expressions.md)에 대한 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-162">See the section on [lambda expressions](lambda-expressions.md) for more information.</span></span> 

<span data-ttu-id="d7fb0-163">컴파일러에서 생성되는 정확한 코드는 약간 더 복잡하며 `GetEnumerator()`에서 반환된 개체가 `IDisposable` 인터페이스를 구현하는 상황을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-163">The exact code generated by the compiler is somewhat more complicated, and handles situations where the object returned by `GetEnumerator()` implements the `IDisposable` interface.</span></span> <span data-ttu-id="d7fb0-164">전체 확장에서는 다음과 더 유사한 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-164">The full expansion generates code more like this:</span></span>

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

<span data-ttu-id="d7fb0-165">열거자가 삭제되는 방식의 `enumerator` 형식의 특성에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-165">The manner in which the enumerator is disposed of depends on the characteristics of the type of `enumerator`.</span></span> <span data-ttu-id="d7fb0-166">일반적인 경우 `finally` 절은 다음과 같이 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-166">In the general case, the `finally` clause expands to:</span></span>

```csharp
finally 
{
   (enumerator as IDisposable)?.Dispose();
} 
```

<span data-ttu-id="d7fb0-167">그러나 `enumerator`의 형식이 sealed 형식이고 `enumerator`의 형식에서 `IDisposable`로의 암시적 변환이 없는 경우 `finally` 절은 빈 블록으로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-167">However, if the type of `enumerator` is a sealed type and there is no implicit conversion from the type of `enumerator` to `IDisposable`, the `finally` clause expands to an empty block:</span></span>
```csharp
finally 
{
} 
```

<span data-ttu-id="d7fb0-168">`enumerator`의 형식에서 `IDisposable`로의 암시적 변환이 있고 `enumerator` 형식이 nullable이 아닌 값 형식인 경우 `finally` 절은 다음과 같이 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-168">If there is an implicit conversion from the type of `enumerator` to `IDisposable`, and `enumerator` is a non-nullable value type, the `finally` clause expands to:</span></span>

```csharp
finally 
{
   ((IDisposable)enumerator).Dispose();
} 
```

<span data-ttu-id="d7fb0-169">다행히도 이러한 세부 정보를 모두 기억할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-169">Thankfully, you don't need to remember all these details.</span></span> <span data-ttu-id="d7fb0-170">`foreach` 문에서 이러한 차이를 모두 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-170">The `foreach` statement handles all those nuances for you.</span></span> <span data-ttu-id="d7fb0-171">컴파일러는 이러한 구문에 대한 올바른 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fb0-171">The compiler will generate the correct code for any of these constructs.</span></span> 


