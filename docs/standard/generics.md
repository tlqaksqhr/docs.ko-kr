---
title: 제네릭 형식(제네릭) 개요
description: 제네릭이 실제 데이터 형식에 커밋하지 않고 형식이 안전한 데이터 구조를 정의할 수 있게 해주는 코드 템플릿으로 사용되는 방법을 알아봅니다.
author: kuhlenh
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: a315b111-8e48-446c-ab19-acb6405894a7
ms.openlocfilehash: ad6216998dff70ca7e36b52b374c5ffb9fd0cd45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575481"
---
# <a name="generic-types-generics-overview"></a><span data-ttu-id="da4e8-103">제네릭 형식(제네릭) 개요</span><span class="sxs-lookup"><span data-stu-id="da4e8-103">Generic Types (Generics) Overview</span></span>

<span data-ttu-id="da4e8-104">암시적이든 명시적이든 C#에서는 항상 제네릭을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-104">We use generics all the time in C#, whether implicitly or explicitly.</span></span> <span data-ttu-id="da4e8-105">C#에서 LINQ를 사용할 때 IEnumerable<T>로 작업하고 있다는 것을 알아차리셨나요?</span><span class="sxs-lookup"><span data-stu-id="da4e8-105">When you use LINQ in C#, did you ever notice that you are working with IEnumerable<T>?</span></span> <span data-ttu-id="da4e8-106">또는 Entity Framework를 사용하여 데이터베이스에 통신하기 위한 “제네릭 리포지토리”의 온라인 샘플을 본 적이 있다면 대부분의 메서드가 IQueryable<T>를 반환하는 것을 보셨나요?</span><span class="sxs-lookup"><span data-stu-id="da4e8-106">Or if you ever saw an online sample of a "generic repository" for talking to databases using Entity Framework, did you see that most methods return IQueryable<T>?</span></span> <span data-ttu-id="da4e8-107">이러한 예제에서 **T**가 무엇이고 왜 사용되는지 궁금하게 여겼을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-107">You may have wondered what the **T** is in these examples and why is it in there?</span></span>

<span data-ttu-id="da4e8-108">.NET Framework 2.0에서 처음 도입된 제네릭은 C# 언어와 CLR(공용 언어 런타임) 둘 다를 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-108">First introduced to the .NET Framework 2.0, generics involved changes to both the C# language and the Common Language Runtime (CLR).</span></span> <span data-ttu-id="da4e8-109">**제네릭**은 기본적으로 개발자가 실제 데이터 형식에 커밋하지 않고 [형식이 안전한](https://msdn.microsoft.com/library/hbzz1a9a.aspx) 데이터 구조를 정의할 수 있게 해주는 “코드 템플릿”입니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-109">**Generics** are essentially a "code template" that allows developers to define [type-safe](https://msdn.microsoft.com/library/hbzz1a9a.aspx) data structures without committing to an actual data type.</span></span> <span data-ttu-id="da4e8-110">예를 들어 `List<T>`는 `List<int>`, `List<string>`, `List<Person>` 등 모든 형식으로 선언하고 사용할 수 있는 [제네릭 컬렉션](xref:System.Collections.Generic)입니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-110">For example, `List<T>` is a [Generic Collection](xref:System.Collections.Generic) that can be declared and used with any type: `List<int>`, `List<string>`, `List<Person>`, etc.</span></span>

<span data-ttu-id="da4e8-111">그렇다면 무엇을 말하고 싶은 것일까요?</span><span class="sxs-lookup"><span data-stu-id="da4e8-111">So, what’s the point?</span></span> <span data-ttu-id="da4e8-112">왜 제네릭이 유용한 것일까요?</span><span class="sxs-lookup"><span data-stu-id="da4e8-112">Why are generics useful?</span></span> <span data-ttu-id="da4e8-113">이러한 사항을 이해하려면 제네릭을 추가하기 전과 이후의 특정 클래스를 살펴봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-113">In order to understand this, we need to take a look at a specific class before and after adding generics.</span></span> <span data-ttu-id="da4e8-114">`ArrayList`를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-114">Let’s look at the `ArrayList`.</span></span> <span data-ttu-id="da4e8-115">C# 1.0에서는 `ArrayList` 요소가 `object` 형식이었습니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-115">In C# 1.0, the `ArrayList` elements were of type `object`.</span></span> <span data-ttu-id="da4e8-116">즉, 추가된 모든 요소가 `object`로 자동으로 변환되었습니다. 목록에서 요소를 읽는 경우에도 마찬가지입니다. 이 프로세스를 각각 [boxing](../../docs/csharp/programming-guide/types/boxing-and-unboxing.md) 및 unboxing이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-116">This meant that any element that was added was silently converted into an `object`; same thing happens on reading the elements from the list (this process is known as [boxing](../../docs/csharp/programming-guide/types/boxing-and-unboxing.md) and unboxing respectively).</span></span> <span data-ttu-id="da4e8-117">boxing 및 unboxing은 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-117">Boxing and unboxing have an impact of performance.</span></span> <span data-ttu-id="da4e8-118">그러나 이보다 더 중요한 사항은 컴파일 시간에 목록에 있는 데이터의 실제 형식을 알 수 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-118">More than that, however, there is no way to tell at compile time what is the actual type of the data in the list.</span></span> <span data-ttu-id="da4e8-119">이 때문에 손상되기 쉬운 일부 코드가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-119">This makes for some fragile code.</span></span> <span data-ttu-id="da4e8-120">제네릭은 각 목록 인스턴스에 포함될 데이터 형식과 관련된 추가 정보를 제공하여 이 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-120">Generics solve this problem by providing additional information the type of data each instance of list will contain.</span></span> <span data-ttu-id="da4e8-121">간단히 말해서, `List<int>`에는 정수만 추가하고 `List<Person>`에는 사용자만 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-121">Put simply, you can only add integers to `List<int>` and only add Persons to `List<Person>`, etc.</span></span>

<span data-ttu-id="da4e8-122">또한 제네릭은 런타임에 사용하거나 **확인**할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-122">Generics are also available at runtime, or **reified**.</span></span> <span data-ttu-id="da4e8-123">즉, 런타임에서 사용 중인 데이터 구조의 형식을 알고 메모리에 보다 효율적으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-123">This means the runtime knows what type of data structure you are using and can store it in memory more efficiently.</span></span>

<span data-ttu-id="da4e8-124">아래에는 런타임에 데이터 구조 형식을 알고 있을 경우의 효율성을 보여 주는 작은 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-124">Here is a small program that illustrates the efficiency of knowing the data structure type at runtime:</span></span>

```csharp
  using System;
  using System.Collections;
  using System.Collections.Generic;
  using System.Diagnostics;

  namespace GenericsExample {
    class Program {
      static void Main(string[] args) {
        //generic list
        List<int> ListGeneric = new List<int> { 5, 9, 1, 4 };
        //non-generic list
        ArrayList ListNonGeneric = new ArrayList { 5, 9, 1, 4 };
        // timer for generic list sort
        Stopwatch s = Stopwatch.StartNew();
        ListGeneric.Sort();
        s.Stop();
        Console.WriteLine($"Generic Sort: {ListGeneric}  \n Time taken: {s.Elapsed.TotalMilliseconds}ms");

        //timer for non-generic list sort
        Stopwatch s2 = Stopwatch.StartNew();
        ListNonGeneric.Sort();
        s2.Stop();
        Console.WriteLine($"Non-Generic Sort: {ListNonGeneric}  \n Time taken: {s2.Elapsed.TotalMilliseconds}ms");
        Console.ReadLine();
      }
    }
  }
```

<span data-ttu-id="da4e8-125">이 프로그램에서는 다음이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-125">This program yields the following output:</span></span>

```console
Generic Sort: System.Collections.Generic.List\`1[System.Int32] Time taken: 0.0789ms
Non-Generic Sort: System.Collections.ArrayList Time taken: 2.4324ms
```

<span data-ttu-id="da4e8-126">여기서 알 수 있는 첫 번째 사항은 제네릭 목록의 정렬 속도가 제네릭이 아닌 목록보다 훨씬 빠르다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-126">The first thing you notice here is that sorting the generic list is significantly faster than for the non-generic list.</span></span> <span data-ttu-id="da4e8-127">제네릭 목록의 형식은 고유 형식([System.Int32])인 반면 제네릭이 아닌 목록의 형식은 일반 형식이라는 것도 발견했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-127">You might also notice that the type for the generic list is distinct ([System.Int32]) whereas the type for the non-generic list is generalized.</span></span> <span data-ttu-id="da4e8-128">제네릭 `List<int>`는 int 형식임을 런타임에서 알고 있기 때문에 메모리의 기본 정수 배열에 목록 요소를 저장할 수 있는 반면, 제네릭이 아닌 `ArrayList`는 각 목록 요소를 개체로 캐스트해야 메모리의 개체 배열에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-128">Because the runtime knows the generic `List<int>` is of type int, it can store the list elements in an underlying integer array in memory while the non-generic `ArrayList` has to cast each list element as an object as stored in an object array in memory.</span></span> <span data-ttu-id="da4e8-129">이 예제에서 알 수 있듯이 추가 캐스팅 작업은 시간이 걸리며 목록 정렬 속도가 느려집니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-129">As shown through this example, the extra castings take up time and slow down the list sort.</span></span>

<span data-ttu-id="da4e8-130">런타임에서 제네릭 형식을 알고 있을 경우의 마지막 이점은 향상된 디버깅 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-130">The last useful thing about the runtime knowing the type of your generic is a better debugging experience.</span></span> <span data-ttu-id="da4e8-131">C#에서 제네릭을 디버그하는 경우 데이터 구조의 각 요소가 어떤 형식인지 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-131">When you are debugging a generic in C#, you know what type each element is in your data structure.</span></span> <span data-ttu-id="da4e8-132">제네릭이 없었다면 각 요소의 형식을 알 수 없었을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="da4e8-132">Without generics, you would have no idea what type each element was.</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="da4e8-133">추가 정보 및 리소스</span><span class="sxs-lookup"><span data-stu-id="da4e8-133">Further reading and resources</span></span>

*   [<span data-ttu-id="da4e8-134">C# 제네릭 소개</span><span class="sxs-lookup"><span data-stu-id="da4e8-134">An Introduction to C# Generics</span></span>](https://msdn.microsoft.com/library/ms379564.aspx)
*   [<span data-ttu-id="da4e8-135">C# 프로그래밍 가이드 - 제네릭</span><span class="sxs-lookup"><span data-stu-id="da4e8-135">C# Programming Guide - Generics</span></span>](../../docs/csharp/programming-guide/generics/index.md)
