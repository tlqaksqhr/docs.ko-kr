---
title: LINQ(Language-Integrated Query)
description: "LINQ가 표현력 있는 선언형 코드를 작성하는 한 가지 방법으로 API와 언어 수준 쿼리 기능을 C# 및 VB에 제공하는 방법을 알아봅니다."
keywords: .NET, .NET Core
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c00939e1-59e3-4e61-8fe9-08ad6b3f1295
ms.openlocfilehash: 1478b5dc5844cef0abfea44eba88a12801d32bd4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="linq-language-integrated-query"></a><span data-ttu-id="fafa3-104">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="fafa3-104">LINQ (Language Integrated Query)</span></span>

## <a name="what-is-it"></a><span data-ttu-id="fafa3-105">LINQ란?</span><span class="sxs-lookup"><span data-stu-id="fafa3-105">What is it?</span></span>

<span data-ttu-id="fafa3-106">LINQ는 표현력 있는 선언형 코드를 작성하는 한 가지 방법으로 [고차 함수](https://en.wikipedia.org/wiki/Higher-order_function) API와 언어 수준 쿼리 기능을 C# 및 VB에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-106">LINQ provides language-level querying capabilities and a [higher-order function](https://en.wikipedia.org/wiki/Higher-order_function) API to C# and VB as a way to write expressive, declarative code.</span></span>

<span data-ttu-id="fafa3-107">언어 수준 쿼리 구문:</span><span class="sxs-lookup"><span data-stu-id="fafa3-107">Language-level query syntax:</span></span>

```csharp
var linqExperts = from p in programmers
                  where p.IsNewToLINQ
                  select new LINQExpert(p);
```

<span data-ttu-id="fafa3-108">`IEnumerable<T>` API를 사용한 동일한 예제:</span><span class="sxs-lookup"><span data-stu-id="fafa3-108">Same example using the `IEnumerable<T>` API:</span></span>

```csharp
var linqExperts = programmers.Where(p => IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

## <a name="linq-is-expressive"></a><span data-ttu-id="fafa3-109">LINQ의 뛰어난 표현력</span><span class="sxs-lookup"><span data-stu-id="fafa3-109">LINQ is Expressive</span></span>

<span data-ttu-id="fafa3-110">애완 동물 목록이 있고, 해당 `RFID` 값으로 애완 동물에 직접 액세스할 수 있는 사전으로 이 목록을 변환하려 한다고 가정해봅시다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-110">Imagine you have a list of pets, but want to convert it into a dictionary where you can access a pet directly by its `RFID` value.</span></span>

<span data-ttu-id="fafa3-111">기존의 명령형 코드:</span><span class="sxs-lookup"><span data-stu-id="fafa3-111">Traditional imperative code:</span></span>

```csharp
var petLookup = new Dictionary<int, Pet>();

foreach (var pet in pets)
{
    petLookup.Add(pet.RFID, pet);
}
```

<span data-ttu-id="fafa3-112">코드의 숨은 의도는 새 `Dictionary<int, Pet>`을 만들고 루프를 통해 사전에 추가하는 것이 아니라 기존 목록을 사전으로 변환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-112">The intention behind the code is not to create a new `Dictionary<int, Pet>` and add to it via a loop, it is to convert an existing list into a dictionary!</span></span> <span data-ttu-id="fafa3-113">LINQ는 이 의도를 유지하지만 명령형 코드는 유지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-113">LINQ preserves the intention whereas the imperative code does not.</span></span>

<span data-ttu-id="fafa3-114">해당되는 LINQ 식:</span><span class="sxs-lookup"><span data-stu-id="fafa3-114">Equivalent LINQ expression:</span></span>

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

<span data-ttu-id="fafa3-115">LINQ를 사용하는 코드는 프로그래머로 추론할 때 의도와 코드를 일치시키기 때문에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-115">The code using LINQ is valuable because it evens the playing field between intent and code when reasoning as a programmer.</span></span> <span data-ttu-id="fafa3-116">그 외에도 코드가 간소화되는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-116">Another bonus is code brevity.</span></span> <span data-ttu-id="fafa3-117">위와 같이 코드베이스의 상당 부분이 1/3만큼 줄어든다고 상상해 보세요.</span><span class="sxs-lookup"><span data-stu-id="fafa3-117">Imagine reducing large portions of a codebase by 1/3 as done above.</span></span> <span data-ttu-id="fafa3-118">멋지지 않나요?</span><span class="sxs-lookup"><span data-stu-id="fafa3-118">Pretty sweet deal, right?</span></span>

## <a name="linq-providers-simplify-data-access"></a><span data-ttu-id="fafa3-119">데이터 액세스를 간소화하는 LINQ 공급자</span><span class="sxs-lookup"><span data-stu-id="fafa3-119">LINQ Providers Simplify Data Access</span></span>

<span data-ttu-id="fafa3-120">소프트웨어의 상당 부분은 실생활에서 일부 소스(데이터베이스, JSON, XML 등)의 데이터를 처리하면서 발전합니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-120">For a significant chunk of software out in the wild, everything revolves around dealing with data from some source (Databases, JSON, XML, etc).</span></span> <span data-ttu-id="fafa3-121">이 과정에서 각 데이터 소스에 대한 새로운 API를 학습해야 하며, 이는 꽤 번거로울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-121">Often this involves learning a new API for each data source, which can be annoying.</span></span> <span data-ttu-id="fafa3-122">LINQ는 데이터 액세스의 공통 요소를 선택한 데이터 소스에 관계없이 동일하게 표시되는 쿼리 구문으로 추상화하여 이 과정을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-122">LINQ simplifies this by abstracting common elements of data access into a query syntax which looks the same no matter which data source you pick.</span></span>

<span data-ttu-id="fafa3-123">특정 특성 값을 가진 모든 XML 요소를 찾는다고 가정해봅시다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-123">Consider the following: finding all XML elements with a specific attribute value.</span></span>

```csharp
public static IEnumerable<XElement> FindAllElementsWithAttribute(XElement documentRoot, string elementName,
                                           string attributeName, string value)
{
    return from el in documentRoot.Elements(elementName)
           where (string)el.Element(attributeName) == value
           select el;
}
```

<span data-ttu-id="fafa3-124">이 작업을 수행하기 위해 수동으로 XML 문서를 트래버스하는 코드를 작성하는 것이 훨씬 더 어려울 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-124">Writing code to manually traverse the XML document to perform this task would be far more challenging.</span></span>

<span data-ttu-id="fafa3-125">XML 조작이 LINQ 공급자로 수행할 수 있는 유일한 작업은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-125">Interacting with XML isn’t the only thing you can do with LINQ Providers.</span></span> <span data-ttu-id="fafa3-126">[LINQ to SQL](https://msdn.microsoft.com/library/bb386976.aspx)은 MSSQL Server Database에 대한 기본적인 ORM(개체 관계형 매퍼)입니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-126">[Linq to SQL](https://msdn.microsoft.com/library/bb386976.aspx) is a fairly bare-bones Object-Relational Mapper (ORM) for an MSSQL Server Database.</span></span> <span data-ttu-id="fafa3-127">[JSON.NET](http://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) 라이브러리는 LINQ를 통한 효율적인 JSON 문서 통과 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-127">The [JSON.NET](http://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) library provides efficient JSON Document traversal via LINQ.</span></span> <span data-ttu-id="fafa3-128">또한 필요한 작업을 수행하는 라이브러리가 없을 경우 [고유한 LINQ 공급자를 작성](https://msdn.microsoft.com/library/Bb546158.aspx)할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-128">Furthermore, if there isn’t a library which does what you need, you can also [write your own LINQ Provider](https://msdn.microsoft.com/library/Bb546158.aspx)!</span></span>

## <a name="why-use-the-query-syntax"></a><span data-ttu-id="fafa3-129">왜 쿼리 구문을 사용하나요?</span><span class="sxs-lookup"><span data-stu-id="fafa3-129">Why Use the Query Syntax?</span></span>

<span data-ttu-id="fafa3-130">자주 제기되는 질문입니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-130">This is a question which often comes up.</span></span> <span data-ttu-id="fafa3-131">결국,</span><span class="sxs-lookup"><span data-stu-id="fafa3-131">After all, this,</span></span>

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

<span data-ttu-id="fafa3-132">위 코드가 아래 코드보다 훨씬 더 간결합니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-132">is a lot more concise than this:</span></span>

```csharp
var filteredItems = from item in myItems
                    where item.Foo
                    select item;
```

<span data-ttu-id="fafa3-133">API 구문이 쿼리 구문보다 더 간결한 방법이 아닌가요?</span><span class="sxs-lookup"><span data-stu-id="fafa3-133">Isn’t the API syntax just a more concise way to do the query syntax?</span></span>

<span data-ttu-id="fafa3-134">아니요.</span><span class="sxs-lookup"><span data-stu-id="fafa3-134">No.</span></span> <span data-ttu-id="fafa3-135">쿼리 구문에서는 **let** 절을 사용할 수 있습니다. 이 절을 통해 식 범위 내에서 변수를 도입 및 바인딩하고 식의 후속 부분에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-135">The query syntax allows for the use the **let** clause, which allows you to introduce and bind a variable within the scope of the expression, using it in subsequent pieces of the expression.</span></span> <span data-ttu-id="fafa3-136">API 구문만 사용하여 동일한 코드를 재현할 수도 있지만 읽기 어려운 코드가 될 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-136">Reproducing the same code with only the API syntax can be done, but will most likely lead to code which is hard to read.</span></span>

<span data-ttu-id="fafa3-137">따라서 **쿼리 구문을 사용해야 하나요?**란 질문을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-137">So this begs the question, **should you just use the query syntax?**</span></span>

<span data-ttu-id="fafa3-138">다음과 같은 경우 이 질문에 대한 대답은 **예**입니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-138">The answer to this question is **yes** if...</span></span>

*   <span data-ttu-id="fafa3-139">기존 코드베이스에서 이미 쿼리 구문을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="fafa3-139">Your existing codebase already uses the query syntax</span></span>
*   <span data-ttu-id="fafa3-140">복잡성으로 인해 쿼리 내에서 변수 범위를 지정해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="fafa3-140">You need to scope variables within your queries due to complexity</span></span>
*   <span data-ttu-id="fafa3-141">쿼리 구문을 선호하며 코드베이스에 방해가 되지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="fafa3-141">You prefer the query syntax and it won’t distract from your codebase</span></span>

<span data-ttu-id="fafa3-142">다음과 같은 경우 이 질문에 대한 대답은 **아니요**입니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-142">The answer to this question is **no** if...</span></span>

*   <span data-ttu-id="fafa3-143">기존 코드베이스에서 이미 API 구문을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="fafa3-143">Your existing codebase already uses the API syntax</span></span>
*   <span data-ttu-id="fafa3-144">쿼리 내에서 변수 범위를 지정할 필요가 없는 경우</span><span class="sxs-lookup"><span data-stu-id="fafa3-144">You have no need to scope variables within your queries</span></span>
*   <span data-ttu-id="fafa3-145">API 구문을 선호하며 코드베이스에 방해가 되지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="fafa3-145">You prefer the API syntax and it won’t distract from your codebase</span></span>

## <a name="essential-samples"></a><span data-ttu-id="fafa3-146">필수 샘플</span><span class="sxs-lookup"><span data-stu-id="fafa3-146">Essential Samples</span></span>

<span data-ttu-id="fafa3-147">LINQ 샘플의 포괄적인 목록은 [101 LINQ 샘플](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fafa3-147">For a truly comprehensive list of LINQ samples, visit [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b).</span></span>

<span data-ttu-id="fafa3-148">다음은 일부 LINQ 핵심 부분의 간단한 데모입니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-148">The following is a quick demonstration of some of the essential pieces of LINQ.</span></span> <span data-ttu-id="fafa3-149">LINQ는 여기에 설명된 것보다 훨씬 더 많은 기능을 제공하기 때문에 포괄적인 목록은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-149">This is in no way comprehensive, as LINQ provides significantly more functionality than what is showcased here.</span></span>

*   <span data-ttu-id="fafa3-150">가장 중요한 요소 - `Where`, `Select` 및 `Aggregate`:</span><span class="sxs-lookup"><span data-stu-id="fafa3-150">The bread and butter - `Where`, `Select`, and `Aggregate`:</span></span>

```csharp
// Filtering a list
var germanShepards = dogs.Where(dog => dog.Breed == DogBreed.GermanShepard);

// Using the query syntax
var queryGermanShepards = from dog in dogs
                          where dog.Breed == DogBreed.GermanShepard
                          select dog;

// Mapping a list from type A to type B
var cats = dogs.Select(dog => dog.TurnIntoACat());

// Using the query syntax
var queryCats = from dog in dogs
                select dog.TurnIntoACat();

// Summing then lengths of a set of strings
int seed = 0;
int sumOfStrings = strings.Aggregate(seed, (s1, s2) => s1.Length + s2.Length);
```

*   <span data-ttu-id="fafa3-151">목록의 목록 평면화:</span><span class="sxs-lookup"><span data-stu-id="fafa3-151">Flattening a list of lists:</span></span>

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

*   <span data-ttu-id="fafa3-152">두 집합 간의 합집합(사용자 지정 비교 연산자 사용):</span><span class="sxs-lookup"><span data-stu-id="fafa3-152">Union between two sets (with custom comparator):</span></span>

```csharp
public class DogHairLengthComparer : IEqualityComparer<Dog>
{
    public bool Equals(Dog a, Dog b)
    {
        if (a == null && b == null)
        {
            return true;
        }
        else if ((a == null && b != null) ||
                 (a != null && b == null))
        {
            return false;
        }
        else
        {
            return a.HairLengthType == b.HairLengthType;
        }
    }

    public int GetHashCode(Dog d)
    {
        // default hashcode is enough here, as these are simple objects.
        return b.GetHashCode();
    }
}

...

// Gets all the short-haired dogs between two different kennels
var allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, new DogHairLengthComparer());
```

*   <span data-ttu-id="fafa3-153">두 집합 간의 교집합:</span><span class="sxs-lookup"><span data-stu-id="fafa3-153">Intersection between two sets:</span></span>

```csharp
// Gets the volunteers who spend share time with two humane societies.
var volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     new VolunteerTimeComparer());
```

*   <span data-ttu-id="fafa3-154">순서:</span><span class="sxs-lookup"><span data-stu-id="fafa3-154">Ordering:</span></span>

```csharp
// Get driving directions, ordering by if it's toll-free before estimated driving time.
var results = DirectionsProcessor.GetDirections(start, end)
              .OrderBy(direction => direction.HasNoTolls)
              .ThenBy(direction => direction.EstimatedTime);
```

*   <span data-ttu-id="fafa3-155">마지막으로, 고급 샘플: 동일한 형식을 가진 두 인스턴스의 속성 값이 같은지 확인([이 StackOverflow 게시물](http://stackoverflow.com/a/844855)에서 가져와 수정함):</span><span class="sxs-lookup"><span data-stu-id="fafa3-155">Finally, a more advanced sample: determining if the values of the properties of two instances of the same type are equal (Borrowed and modified from [this StackOverflow post](http://stackoverflow.com/a/844855)):</span></span>

```csharp
public static bool PublicInstancePropertiesEqual<T>(this T self, T to, params string[] ignore) where T : class
{
    if (self != null && to != null)
    {
        var type = typeof(T);
        var ignoreList = new List<string>(ignore);

        // Selects the properties which have unequal values into a sequence of those properties.
        var unequalProperties = from pi in type.GetProperties(BindingFlags.Public | BindingFlags.Instance)
                                where !ignoreList.Contains(pi.Name)
                                let selfValue = type.GetProperty(pi.Name).GetValue(self, null)
                                let toValue = type.GetProperty(pi.Name).GetValue(to, null)
                                where selfValue != toValue && (selfValue == null || !selfValue.Equals(toValue))
                                select new { Prop = pi.Name, selfValue, toValue };
        return !unequalProperties.Any();
    }

    return self == to;
}
```

## <a name="plinq"></a><span data-ttu-id="fafa3-156">PLINQ</span><span class="sxs-lookup"><span data-stu-id="fafa3-156">PLINQ</span></span>

<span data-ttu-id="fafa3-157">PLINQ 또는 병렬 LINQ는 LINQ 식에 대한 병렬 실행 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-157">PLINQ, or Parallel LINQ, is a parallel execution engine for LINQ expressions.</span></span> <span data-ttu-id="fafa3-158">즉, 여러 스레드 간에 LINQ 정규식을 일반적으로 병렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-158">In other words, a regular LINQ expressions can be trivially parallelized across any number of threads.</span></span> <span data-ttu-id="fafa3-159">이 작업은 식 앞의 `AsParallel()` 호출을 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-159">This is accomplished via a call to `AsParallel()` preceding the expression.</span></span>

<span data-ttu-id="fafa3-160">다음을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="fafa3-160">Consider the following:</span></span>

```csharp
public static string GetAllFacebookUserLikesMessage(IEnumerable<FacebookUser> facebookUsers)
{
    var seed = default(UInt64);

    Func<UInt64, UInt64, UInt64> threadAccumulator = (t1, t2) => t1 + t2;
    Func<UInt64, UInt64, UInt64> threadResultAccumulator = (t1, t2) => t1 + t2;
    Func<Uint64, string> resultSelector = total => $"Facebook has {total} likes!";

    return facebookUsers.AsParallel()
                        .Aggregate(seed, threadAccumulator, threadResultAccumulator, resultSelector);
}
```

<span data-ttu-id="fafa3-161">이 코드는 필요에 따라 시스템 스레드 간에 `facebookUsers`를 분할하고, 각 스레드의 총계를 병렬로 합산한 다음, 각 스레드에서 계산된 결과를 합산하고 그 결과를 멋진 문자열로 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-161">This code will partition `facebookUsers` across system threads as necessary, sum up the total likes on each thread in parallel, sum the results computed by each thread, and project that result into a nice string.</span></span>

<span data-ttu-id="fafa3-162">다이어그램 형식:</span><span class="sxs-lookup"><span data-stu-id="fafa3-162">In diagram form:</span></span>

![PLINQ 다이어그램](./media/using-linq/plinq-diagram.png)

<span data-ttu-id="fafa3-164">LINQ를 통해 쉽게 표현될 수 있는 병렬화 가능한 CPU 바인딩된 작업(즉, 순수 함수이며 부작용 없음)에 PLINQ를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-164">Parallelizable CPU-bound jobs which can be easily expressed via LINQ (in other words, are pure functions and have no side effects) are a great candidate for PLINQ.</span></span> <span data-ttu-id="fafa3-165">부작용이 _있는_ 작업의 경우 [작업 병렬 라이브러리](https://msdn.microsoft.com/library/dd460717.aspx)를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fafa3-165">For jobs which _do_ have a side effect, consider using the [Task Parallel Library](https://msdn.microsoft.com/library/dd460717.aspx).</span></span>

## <a name="further-resources"></a><span data-ttu-id="fafa3-166">추가 리소스:</span><span class="sxs-lookup"><span data-stu-id="fafa3-166">Further Resources:</span></span>

*   [<span data-ttu-id="fafa3-167">101 LINQ 샘플</span><span class="sxs-lookup"><span data-stu-id="fafa3-167">101 LINQ Samples</span></span>](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b)
*   <span data-ttu-id="fafa3-168">[Linqpad](https://www.linqpad.net/), 실습 환경 및 C#/F#/VB에 대한 데이터베이스 쿼리 엔진</span><span class="sxs-lookup"><span data-stu-id="fafa3-168">[Linqpad](https://www.linqpad.net/), a playground environment and Database querying engine for C#/F#/VB</span></span>
*   <span data-ttu-id="fafa3-169">[EduLinq](http://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), LINQ-to-objects 구현 방법 학습을 위한 전자책</span><span class="sxs-lookup"><span data-stu-id="fafa3-169">[EduLinq](http://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), an e-book for learning how LINQ-to-objects is implemented</span></span>
