---
title: LINQ 작업
description: 이 자습서에서는 LINQ를 사용하여 시퀀스를 생성하고, LINQ 쿼리에서 사용할 메서드를 작성하고, 즉시 계산 및 지연 계산 간을 구분하는 방법을 알아봅니다.
ms.date: 03/28/2017
ms.assetid: 0db12548-82cb-4903-ac88-13103d70aa77
ms.openlocfilehash: 17c294a372a05a05d3893fce7b3adc426c6305fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="working-with-linq"></a><span data-ttu-id="908f6-103">LINQ 작업</span><span class="sxs-lookup"><span data-stu-id="908f6-103">Working with LINQ</span></span>

## <a name="introduction"></a><span data-ttu-id="908f6-104">소개</span><span class="sxs-lookup"><span data-stu-id="908f6-104">Introduction</span></span>

<span data-ttu-id="908f6-105">이 자습서에서는 .NET Core 및 C# 언어의 다양한 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="908f6-106">다음을 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-106">You’ll learn:</span></span>

*   <span data-ttu-id="908f6-107">LINQ를 사용하여 시퀀스를 생성하는 방법</span><span class="sxs-lookup"><span data-stu-id="908f6-107">How to generate sequences with LINQ</span></span>
*   <span data-ttu-id="908f6-108">LINQ 쿼리에서 쉽게 사용할 수 있는 메서드를 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="908f6-108">How to write methods that can be easily used in LINQ queries.</span></span>
*   <span data-ttu-id="908f6-109">즉시 계산 및 지연 계산을 구분하는 방법</span><span class="sxs-lookup"><span data-stu-id="908f6-109">How to distinguish between eager and lazy evaluation.</span></span>

<span data-ttu-id="908f6-110">모든 마술사들이 기본적으로 익히는 기술 중 하나인 [파로 셔플](https://en.wikipedia.org/wiki/Faro_shuffle)을 보여 주는 응용 프로그램을 빌드하여 이러한 기술을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-110">You'll learn these techniques by building an application that demonstrates one of the basic skills of any magician: the [faro shuffle](https://en.wikipedia.org/wiki/Faro_shuffle).</span></span> <span data-ttu-id="908f6-111">간단히 말해서 파로 셔플은 카드 데크를 정확히 절반으로 분할한 다음 각 절반의 각 카드를 교차로 섞어 원래 데크 순서로 다시 빌드하는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-111">Briefly, a faro shuffle is a technique where you split a card deck exactly in half, then the shuffle interleaves each one card from each half to rebuild the original deck.</span></span>

<span data-ttu-id="908f6-112">마술사들은 카드를 섞은 후에 모든 카드가 알려진 위치로 들어가고 순서가 반복 패턴을 가지게 되므로 이 기술을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-112">Magicians use this technique because every card is in a known location after each shuffle, and the order is a repeating pattern.</span></span> 

<span data-ttu-id="908f6-113">이 자습서에서는 데이터 시퀀스 조작 과정을 가볍게 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-113">For our purposes, it is a light hearted look at manipulating sequences of data.</span></span> <span data-ttu-id="908f6-114">빌드할 응용 프로그램은 카드 데크를 생성하고 섞은 다음 매번 섞는 시퀀스를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-114">The application you'll build will construct a card deck, and then perform a sequence of shuffles, writing the sequence out each time.</span></span> <span data-ttu-id="908f6-115">또한 업데이트된 순서를 원래 순서와 비교할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-115">You'll also compare the updated order to the original order.</span></span>

<span data-ttu-id="908f6-116">이 자습서는 여러 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-116">This tutorial has multiple steps.</span></span> <span data-ttu-id="908f6-117">각 단계 후에 응용 프로그램을 실행하고 진행 상황을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-117">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="908f6-118">[완료된 샘플](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq)은 GitHub의 dotnet/samples 리포지토리에서도 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-118">You can also see the [completed sample](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) in the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="908f6-119">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="908f6-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="908f6-120">전제 조건</span><span class="sxs-lookup"><span data-stu-id="908f6-120">Prerequisites</span></span>

<span data-ttu-id="908f6-121">.NET Core를 실행하도록 컴퓨터에 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-121">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="908f6-122">[.NET Core](https://www.microsoft.com/net/core) 페이지에서 설치 지침을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-122">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="908f6-123">Windows, Ubuntu Linux, OS X 또는 Docker 컨테이너에서 이 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-123">You can run this application on Windows, Ubuntu Linux, OS X or in a Docker container.</span></span> <span data-ttu-id="908f6-124">선호하는 코드 편집기를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="908f6-125">아래 설명에서는 오픈 소스 플랫폼 간 편집기인 [Visual Studio Code](https://code.visualstudio.com/)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="908f6-126">그러나 익숙한 어떤 도구도 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="908f6-127">응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="908f6-127">Create the Application</span></span>

<span data-ttu-id="908f6-128">첫 번째 단계에서는 새 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-128">The first step is to create a new application.</span></span> <span data-ttu-id="908f6-129">명령 프롬프트를 열고 응용 프로그램에 대한 새 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="908f6-130">해당 디렉터리를 현재 디렉터리로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-130">Make that the current directory.</span></span> <span data-ttu-id="908f6-131">명령 프롬프트에 명령 `dotnet new console`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-131">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="908f6-132">이렇게 하면 기본 "Hello World" 응용 프로그램에 대한 시작 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-132">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="908f6-133">이전에 C#을 사용해본 적이 없으면 [이 자습서](console-teleprompter.md)에서 C# 프로그램의 구조를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="908f6-133">If you've never used C# before, [this tutorial](console-teleprompter.md) explains the structure of a C# program.</span></span> <span data-ttu-id="908f6-134">해당 부분을 읽고 여기로 돌아와 LINQ에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-134">You can read that and then return here to learn more about LINQ.</span></span> 

## <a name="creating-the-data-set"></a><span data-ttu-id="908f6-135">데이터 집합 만들기</span><span class="sxs-lookup"><span data-stu-id="908f6-135">Creating the Data Set</span></span>

<span data-ttu-id="908f6-136">먼저 카드 데크를 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-136">Let's start by creating a deck of cards.</span></span> <span data-ttu-id="908f6-137">두 개의 소스(4개 카드 세트에 대해 1개, 13개 값에 대해 1개)가 있는 LINQ 쿼리를 사용하여 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-137">You'll do this using a LINQ query that has two sources (one for the four suits, one for the thirteen values).</span></span> <span data-ttu-id="908f6-138">이러한 소스를 52개 카드 데크로 조합합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-138">You'll combine those sources into a 52 card deck.</span></span> <span data-ttu-id="908f6-139">`foreach` 루프 내의 `Console.WriteLine` 문이 카드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-139">A `Console.WriteLine` statement inside a `foreach` loop displays the cards.</span></span>

<span data-ttu-id="908f6-140">쿼리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-140">Here's the query:</span></span>

```csharp
var startingDeck = from s in Suits()
                   from r in Ranks()
                   select new { Suit = s, Rank = r };

foreach (var c in startingDeck)
{
    Console.WriteLine(c);
}
```

<span data-ttu-id="908f6-141">여러 `from` 절이 `SelectMany`를 생성합니다. 그러면 첫 번째 시퀀스의 각 요소를 두 번째 시퀀스의 각 요소와 조합하는 단일 시퀀스가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-141">The multiple `from` clauses produce a `SelectMany`, which creates a single sequence from combining each element in the first sequence with each element in the second sequence.</span></span> <span data-ttu-id="908f6-142">이 순서는 현재 목적에 따라 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-142">The order is important for our purposes.</span></span> <span data-ttu-id="908f6-143">첫 번째 소스 시퀀스(Suites)의 첫 번째 요소는 두 번째 시퀀스(Values)의 모든 요소와 조합됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-143">The first element in the first source sequence (Suits) is combined with every element in the second sequence (Values).</span></span> <span data-ttu-id="908f6-144">그 결과 첫 번째 세트의 13개 카드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-144">This produces all thirteen cards of first suit.</span></span> <span data-ttu-id="908f6-145">이 프로세스는 첫 번째 시퀀스(Suites)의 각 요소에 대해 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-145">That process is repeated with each element in the first sequence (Suits).</span></span> <span data-ttu-id="908f6-146">최종 결과는 카드 데크를 세트별로 정렬한 후 다시 값별로 정렬한 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-146">The end result is a deck of cards ordered by suits, followed by values.</span></span>

<span data-ttu-id="908f6-147">다음으로 Suits() 및 Ranks() 메서드를 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-147">Next, you'll need to build the Suits() and Ranks() methods.</span></span> <span data-ttu-id="908f6-148">시퀀스를 문자열 열거형으로 생성하는 정말 간단한 *반복기 메서드*부터 시작해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-148">Let's start with a really simple set of *iterator methods* that generate the sequence as an enumerable of strings:</span></span>

```csharp
static IEnumerable<string> Suits()
{
    yield return "clubs";
    yield return "diamonds";
    yield return "hearts";
    yield return "spades";
}

static IEnumerable<string> Ranks()
{
    yield return "two";
    yield return "three";
    yield return "four";
    yield return "five";
    yield return "six";
    yield return "seven";
    yield return "eight";
    yield return "nine";
    yield return "ten";
    yield return "jack";
    yield return "queen";
    yield return "king";
    yield return "ace";
}
```

<span data-ttu-id="908f6-149">이러한 두 메서드는 `yield return` 구문을 활용하여 실행 시 시퀀스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-149">These two methods both utilize the `yield return` syntax to produce a sequence as they run.</span></span> <span data-ttu-id="908f6-150">컴파일러는 `IEnumerable<T>`을 구현하는 개체를 빌드하고 요청 시 문자열 시퀀스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-150">The compiler builds an object that implements `IEnumerable<T>` and generates the sequence of strings as they are requested.</span></span>

<span data-ttu-id="908f6-151">계속해서 지금 빌드한 샘플을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-151">Go ahead and run the sample you've built at this point.</span></span> <span data-ttu-id="908f6-152">데크에 있는 52개의 모든 카드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-152">It will display all 52 cards in the deck.</span></span> <span data-ttu-id="908f6-153">디버거에서 이 샘플을 실행하면 `Suits()` 및 `Values()` 메서드가 실행되는 방식을 확인할 수 있어서 매우 유용하다는 것을 알게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-153">You may find it very helpful to run this sample under a debugger to observe how the `Suits()` and `Values()` methods execute.</span></span> <span data-ttu-id="908f6-154">각 시퀀스의 각 문자열이 필요할 때만 생성된다는 것도 명확히 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-154">You can clearly see that each string in each sequence is generated only as it is needed.</span></span>

![52개의 카드를 작성하는 앱을 표시하는 콘솔 창](./media/working-with-linq/console.png)

## <a name="manipulating-the-order"></a><span data-ttu-id="908f6-156">순서 조작</span><span class="sxs-lookup"><span data-stu-id="908f6-156">Manipulating the Order</span></span>

<span data-ttu-id="908f6-157">다음에는 순서 섞기를 수행할 수 있는 유틸리티 메서드를 빌드해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-157">Next, let's build a utility method that can perform the shuffle.</span></span> <span data-ttu-id="908f6-158">첫 번째 단계는 데크를 하나로 분할하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-158">The first step is to split the deck in two.</span></span> <span data-ttu-id="908f6-159">LINQ API에 속하는 `Take()` 및 `Skip()` 메서드가 이 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-159">The `Take()` and `Skip()` methods that are part of the LINQ APIs provide that feature for us:</span></span>

```csharp
var top = startingDeck.Take(26);
var bottom = startingDeck.Skip(26);
```

<span data-ttu-id="908f6-160">순서 섞기 메서드는 표준 라이브러리에 들어 있지 않으므로 직접 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-160">The shuffle method doesn't exist in the standard library, so you'll have to write your own.</span></span> <span data-ttu-id="908f6-161">이 새 메서드는 LINQ 기반 프로그램에서 사용하게 되는 몇 가지 기법을 보여 주므로 이 메서드의 각 부분을 단계별로 설명해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-161">This new method illustrates several techniques that you'll use with LINQ-based programs, so let's explain each part of the method in steps.</span></span>

<span data-ttu-id="908f6-162">이 메서드에 대한 시그니처는 *확장 메서드*를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-162">The signature for the method creates an *extension method*:</span></span>

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T>
    (this IEnumerable<T> first, IEnumerable<T> second)
```

<span data-ttu-id="908f6-163">확장 메서드는 특수한 용도의 *정적 메서드*입니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-163">An extension method is a special purpose *static method.*</span></span> <span data-ttu-id="908f6-164">이 메서드에 첫 번째 인수에 대한 `this` 한정자가 추가되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-164">You can see the addition of the `this` modifier on the first argument to the method.</span></span> <span data-ttu-id="908f6-165">즉, 마치 첫 번째 인수 형식의 멤버 메서드인 것처럼 이 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-165">That means you call the method as though it were a member method of the type of the first argument.</span></span>

<span data-ttu-id="908f6-166">확장 메서드는 `static` 클래스 내부에서만 선언할 수 있으므로 이 기능을 위해 `extensions`라는 새 정적 클래스를 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-166">Extension methods can be declared only inside `static` classes, so let's create a new static class called `extensions` for this functionality.</span></span> <span data-ttu-id="908f6-167">이 자습서를 계속 진행하면서 확장 메서드를 더 추가하게 될 것이며 이러한 메서드도 같은 클래스에 포함될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-167">You'll add more extension methods as you continue this tutorial, and those will be placed in the same class.</span></span>

<span data-ttu-id="908f6-168">또한 이 메서드 선언은 입력 및 출력 형식이 `IEnumerable<T>`인 표준 관용구를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-168">This method declaration also follows a standard idiom where the input and output types are `IEnumerable<T>`.</span></span> <span data-ttu-id="908f6-169">이러한 방식에서는 LINQ 메서드가 서로 사슬처럼 연결되어 좀 더 복잡한 쿼리를 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-169">That practice enables LINQ methods to be chained together to perform more complex queries.</span></span>

```csharp
using System.Collections.Generic;

namespace LinqFaroShuffle
{
    public static class Extensions
    {
        public static IEnumerable<T> InterleaveSequenceWith<T>
            (this IEnumerable<T> first, IEnumerable<T> second)
        {
            // implementation coming.
        }
    }
}
```

<span data-ttu-id="908f6-170">한 번에 두 시퀀스를 열거하고 요소를 인터리브하여 하나의 개체를 만들게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-170">You will be enumerating both sequences at once, interleaving the elements, and creating one object.</span></span>  <span data-ttu-id="908f6-171">두 시퀀스에 작동하는 LINQ 메서드를 작성하려면 `IEnumerable` 작동 방식을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-171">Writing a LINQ method that works with two sequences requires that you understand how `IEnumerable` works.</span></span>

<span data-ttu-id="908f6-172">`IEnumerable` 인터페이스는 한 가지 메서드인 `GetEnumerator()`를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-172">The `IEnumerable` interface has one method: `GetEnumerator()`.</span></span> <span data-ttu-id="908f6-173">`GetEnumerator()`에서 반환된 개체에는 다음 요소로 이동하기 위한 메서드와 시퀀스의 현재 요소를 검색하는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-173">The object returned by `GetEnumerator()` has a method to move to the next element, and a property that retrieves the current element in the sequence.</span></span> <span data-ttu-id="908f6-174">이러한 두 멤버를 사용하여 컬렉션을 열거하고 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-174">You will use those two members to enumerate the collection and return the elements.</span></span> <span data-ttu-id="908f6-175">이 Interleave 메서드는 반복기 메서드이므로, 컬렉션을 빌드하고 반환하는 대신, 위에 표시된 `yield return` 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-175">This Interleave method will be an iterator method, so instead of building a collection and returning the collection, you'll use the `yield return` syntax shown above.</span></span> 

<span data-ttu-id="908f6-176">해당 메서드의 구현은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-176">Here's the implementation of that method:</span></span>

[!CODE-csharp[InterleaveSequenceWith](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

<span data-ttu-id="908f6-177">이 메서드를 작성했으므로 `Main` 메서드로 돌아가 데크 순서를 한 번 섞습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-177">Now that you've written this method, go back to the `Main` method and shuffle the deck once:</span></span>

```csharp
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }
        
    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
    var shuffle = top.InterleaveSequenceWith(bottom);

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }
}
```

## <a name="comparisons"></a><span data-ttu-id="908f6-178">비교</span><span class="sxs-lookup"><span data-stu-id="908f6-178">Comparisons</span></span>

<span data-ttu-id="908f6-179">데크가 원래 순서로 돌아가는 데 몇 번을 섞어야 하는지 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-179">Let's see how many shuffles it takes to set the deck back to its original order.</span></span> <span data-ttu-id="908f6-180">두 시퀀스가 서로 같은지 확인하는 메서드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-180">You'll need to write a method that determines if two sequences are equal.</span></span> <span data-ttu-id="908f6-181">이 메서드를 만든 후에는 데크 순서를 섞는 코드를 루프에 배치하고 데크가 원래 순서로 돌아갈 때를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-181">After you have that method, you'll need to place the code that shuffles the deck in a loop, and check to see when the deck is back in order.</span></span>

<span data-ttu-id="908f6-182">두 시퀀스가 서로 같은지를 확인하는 메서드를 작성하는 작업은 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-182">Writing a method to determine if the two sequences are equal should be straightforward.</span></span> <span data-ttu-id="908f6-183">데크를 섞기 위해 작성한 메서드와 비슷한 구조를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-183">It's a similar structure to the method you wrote to shuffle the deck.</span></span> <span data-ttu-id="908f6-184">그렇지만 이 경우는 각 요소를 반환하지 말고 각 시퀀스의 일치하는 요소를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-184">Only this time, instead of yield returning each element, you'll compare the matching elements of each sequence.</span></span> <span data-ttu-id="908f6-185">전체 시퀀스가 열거된 경우 모든 요소가 일치하면 시퀀스도 같습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-185">When the entire sequence has been enumerated, if every element matches, the sequences are the same:</span></span>

[!CODE-csharp[SequenceEquals](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

<span data-ttu-id="908f6-186">다음에서는 두 번째 Linq 관용구인 터미널 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-186">This shows a second Linq idiom: terminal methods.</span></span> <span data-ttu-id="908f6-187">여기서는 시퀀스를 입력으로 사용하고(또는 이 경우 두 개의 시퀀스) 단일 스칼라 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-187">They take a sequence as input (or in this case, two sequences), and return a single scalar value.</span></span> <span data-ttu-id="908f6-188">이러한 메서드를 사용한다면 항상 쿼리의 마지막 메서드로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-188">These methods, when they are used, are always the final method of a query.</span></span> <span data-ttu-id="908f6-189">(그래서 이러한 이름을 갖습니다.)</span><span class="sxs-lookup"><span data-stu-id="908f6-189">(Hence the name).</span></span> 

<span data-ttu-id="908f6-190">이 메서드를 사용하여 데크가 원래 순서로 돌아갈 때를 확인하면 작동 방식을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-190">You can see this in action when you use it to determine when the deck is back in its original order.</span></span> <span data-ttu-id="908f6-191">순서 섞기 코드를 루프 내에 포함하고, `SequenceEquals()` 메서드를 적용하여 시퀀스가 원래 순서가 될 때 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-191">Put the shuffle code inside a loop, and stop when the sequence is back in its original order by applying the `SequenceEquals()` method.</span></span> <span data-ttu-id="908f6-192">이 메서드는 시퀀스 대신 단일 값을 반환하므로 어떤 쿼리에서든지 항상 마지막 메서드로 사용되는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-192">You can see it would always be the final method in any query, because it returns a single value instead of a sequence:</span></span>

```csharp
var times = 0;
var shuffle = startingDeck;

do
{
    shuffle = shuffle.Take(26).InterleaveSequenceWith(shuffle.Skip(26));

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }

    Console.WriteLine();
    times++;
} while (!startingDeck.SequenceEquals(shuffle));

Console.WriteLine(times);
```

<span data-ttu-id="908f6-193">샘플을 실행하고, 8회 반복 후 원래 구성으로 돌아갈 때까지 각 순서 섞기에서 데크가 재정렬되는 방식을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-193">Run the sample, and see how the deck rearranges on each shuffle, until it returns to its original configuration after 8 iterations.</span></span>

## <a name="optimizations"></a><span data-ttu-id="908f6-194">최적화</span><span class="sxs-lookup"><span data-stu-id="908f6-194">Optimizations</span></span>

<span data-ttu-id="908f6-195">지금까지 빌드한 샘플은 *내부 순서 섞기*을 실행합니다. 즉, 맨 위 및 맨 아래 카드가 실행할 때마다 항상 같은 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-195">The sample you've built so far executes an *in shuffle*, where the top and bottom cards stay the same on each run.</span></span> <span data-ttu-id="908f6-196">한 가지 부분을 변경하여 52장 카드가 모두 위치를 바꾸는 *외부 순서 섞기*를 실행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-196">Let's make one change, and run an *out shuffle*, where all 52 cards change position.</span></span> <span data-ttu-id="908f6-197">외부 순서 섞기의 경우 반으로 나눈 아래쪽 부분의 첫 번째 카드가 데크의 첫 번째 카드가 되도록 데크를 인터리브합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-197">For an out shuffle, you interleave the deck so that the first card in the bottom half becomes the first card in the deck.</span></span> <span data-ttu-id="908f6-198">즉, 반으로 나눈 위쪽 부분의 마지막 카드가 맨 아래 카드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-198">That means the last card in the top half becomes the bottom card.</span></span> <span data-ttu-id="908f6-199">이를 위해 한 줄만 변경하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-199">That's just a one line change.</span></span> <span data-ttu-id="908f6-200">데크의 위쪽 절반과 아래쪽 절반의 순서를 변경하도록 순서 섞기 호출을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-200">Update the call to shuffle to change the order of the top and bottom halves of the deck:</span></span>

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

<span data-ttu-id="908f6-201">프로그램을 다시 실행합니다. 그러면 데크가 자체적으로 순서를 변경하는 데 52회 반복된다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-201">Run the program again, and you'll see that it takes 52 iterations for the deck to reorder itself.</span></span> <span data-ttu-id="908f6-202">또한 프로그램이 계속 실행될 때 몇 가지 심각한 성능 저하를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-202">You'll also start to notice some serious performance degradations as the program continues to run.</span></span>

<span data-ttu-id="908f6-203">그 이유로는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-203">There are a number of reasons for this.</span></span> <span data-ttu-id="908f6-204">주요 원인 중 하나인 비효율적인 *지연 계산* 사용을 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-204">Let's tackle one of the major causes: inefficient use of *lazy evaluation*.</span></span>

<span data-ttu-id="908f6-205">LINQ 쿼리는 느리게 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-205">LINQ queries are evaluated lazily.</span></span> <span data-ttu-id="908f6-206">요소가 요청될 때만 시퀀스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-206">The sequences are generated only as the elements are requested.</span></span> <span data-ttu-id="908f6-207">일반적으로 이것이 LINQ의 큰 장점입니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-207">Usually, that's a major benefit of LINQ.</span></span> <span data-ttu-id="908f6-208">그러나 이러한 프로그램에서 사용하면 실행 시간이 기하급수적으로 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-208">However, in a use such as this program, this causes exponential growth in execution time.</span></span>

<span data-ttu-id="908f6-209">원래 데크는 LINQ 쿼리를 사용하여 생성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-209">The original deck was generated using a LINQ query.</span></span> <span data-ttu-id="908f6-210">각 순서 섞기는 이전 데크에 대해 세 개의 LINQ 쿼리를 수행하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-210">Each shuffle is generated by performing three LINQ queries on the previous deck.</span></span> <span data-ttu-id="908f6-211">이러한 모든 쿼리는 느리게 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-211">All these are performed lazily.</span></span> <span data-ttu-id="908f6-212">즉, 시퀀스가 요청될 때마다 다시 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-212">That also means they are performed again each time the sequence is requested.</span></span> <span data-ttu-id="908f6-213">52번째 반복에 도달할 때까지 원래 데크를 아주 여러 번 다시 생성하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-213">By the time you get to the 52nd iteration, you're regenerating the original deck many, many times.</span></span> <span data-ttu-id="908f6-214">이 동작을 보여 주기 위해 로그를 작성해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-214">Let's write a log to demonstrate this behavior.</span></span> <span data-ttu-id="908f6-215">그런 후에 문제를 해결해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-215">Then, you'll fix it.</span></span>

<span data-ttu-id="908f6-216">해당 쿼리가 실행되었음을 표시하기 위해 쿼리에 추가될 수 있는 로그 메서드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-216">Here's a log method that can be appended to any query to mark that the query executed.</span></span>

[!CODE-csharp[LogQuery](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

<span data-ttu-id="908f6-217">그런 후 로그 메시지를 사용하여 각 쿼리의 정의를 계측합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-217">Next, instrument the definition of each query with a log message:</span></span>

```csharp
public static void Main(string[] args)
{
    var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                        from r in Ranks().LogQuery("Rank Generation")
                        select new { Suit = s, Rank = r }).LogQuery("Starting Deck");

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }
        
    Console.WriteLine();
    var times = 0;
    var shuffle = startingDeck;

    do
    {
        /*
        shuffle = shuffle.Take(26)
            .LogQuery("Top Half")
            .InterleaveSequenceWith(shuffle.Skip(26)
            .LogQuery("Bottom Half"))
            .LogQuery("Shuffle");
        */

        shuffle = shuffle.Skip(26)
            .LogQuery("Bottom Half")
            .InterleaveSequenceWith(shuffle.Take(26).LogQuery("Top Half"))
            .LogQuery("Shuffle");

        foreach (var c in shuffle)
        {
            Console.WriteLine(c);
        }

        times++;
        Console.WriteLine(times);
    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

<span data-ttu-id="908f6-218">쿼리에 액세스할 때마다 로깅하지는 않고,</span><span class="sxs-lookup"><span data-stu-id="908f6-218">Notice that you don't log every time you access a query.</span></span> <span data-ttu-id="908f6-219">원래 쿼리를 만들 때만 로깅합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-219">You log only when you create the original query.</span></span> <span data-ttu-id="908f6-220">프로그램을 실행하는 데 여전히 오래 걸리지만 이제 이유를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-220">The program still takes a long time to run, but now you can see why.</span></span> <span data-ttu-id="908f6-221">로깅을 켠 상태로 외부 순서 섞기를 실행하다가 지치면 내부 순서 섞기로 다시 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-221">If you run out of patience running the outer shuffle with logging turned on, switch back to the inner shuffle.</span></span> <span data-ttu-id="908f6-222">여전히 지연 계산 효과가 나타날 것입니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-222">You'll still see the lazy evaluation effects.</span></span> <span data-ttu-id="908f6-223">한 번 실행에서 모든 값 및 세트 생성을 비롯한 2592개의 쿼리가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-223">In one run, it executes 2592 queries, including all the value and suit generation.</span></span>

<span data-ttu-id="908f6-224">이러한 모든 실행을 피하도록 이 프로그램을 업데이트하는 쉬운 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-224">There is an easy way to update this program to avoid all those executions.</span></span> <span data-ttu-id="908f6-225">LINQ 메서드 `ToArray()` 및 `ToList()`가 있습니다. 이러한 메서드는 쿼리를 실행한 다음 결과를 각각 배열 또는 목록으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-225">There are LINQ methods `ToArray()` and `ToList()` that cause the query to run, and store the results in an array or a list, respectively.</span></span> <span data-ttu-id="908f6-226">이러한 메서드를 사용하여 소스 쿼리를 다시 실행하는 대신 쿼리의 데이터 결과를 캐시합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-226">You use these methods to cache the data results of a query rather than execute the source query again.</span></span>  <span data-ttu-id="908f6-227">`ToArray()`를 호출하여 카드 데크를 생성하는 쿼리를 추가한 후 퀴리를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-227">Append the queries that generate the card decks with a call to `ToArray()` and run the query again:</span></span>

[!CODE-csharp[Main](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

<span data-ttu-id="908f6-228">다시 실행합니다. 그러면 내부 순서 섞기가 30개 쿼리로 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-228">Run again, and the inner shuffle is down to 30 queries.</span></span> <span data-ttu-id="908f6-229">외부 순서 섞기를 다시 실행해도 비슷하게 개선된 것을 볼 수 있을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-229">Run again with the outer shuffle and you'll see similar improvements.</span></span> <span data-ttu-id="908f6-230">(이제 162개의 쿼리가 실행됨)</span><span class="sxs-lookup"><span data-stu-id="908f6-230">(It now executes 162 queries).</span></span>

<span data-ttu-id="908f6-231">이 예제에서 모든 쿼리가 즉시 실행되어야 한다고 잘못 생각하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="908f6-231">Don't misinterpret this example by thinking that all queries should run eagerly.</span></span> <span data-ttu-id="908f6-232">이 예제는 지연 계산이 성능 문제를 일으킬 수 있는 사용 사례를 중점적으로 나타내도록 고안되었습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-232">This example is designed to highlight the use cases where lazy evaluation can cause performance difficulties.</span></span> <span data-ttu-id="908f6-233">카드 데크의 각 새 배열이 이전 배열에서 만들어지기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-233">That's because each new arrangement of the deck of cards is built from the previous arrangement.</span></span> <span data-ttu-id="908f6-234">지연 계산을 사용한다는 것은 각 새 데크 구성이 원래 데크에서 빌드되며, 심지어 `startingDeck`를 빌드한 코드를 실행하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-234">Using lazy evaluation means each new deck configuration is built from the original deck, even executing the code that built the `startingDeck`.</span></span> <span data-ttu-id="908f6-235">이로 인해 많은 양의 추가 작업이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-235">That causes a large amount of extra work.</span></span> 

<span data-ttu-id="908f6-236">실제로 즉시 계산을 사용할 때 성능이 더 좋아지는 알고리즘도 있고, 지연 계산을 사용할 때 성능이 더 좋아지는 알고리즘도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-236">In practice, some algorithms run much better using eager evaluation, and others run much better using lazy evaluation.</span></span> <span data-ttu-id="908f6-237">(일반적으로 지연 계산은 데이터베이스 엔진과 같이 데이터 소스가 별도 프로세스일 때 사용하면 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-237">(In general, lazy evaluation is a much better choice when the data source is a separate process, like a database engine.</span></span> <span data-ttu-id="908f6-238">이러한 경우 지연 계산은 좀 더 복잡한 쿼리를 통해 데이터베이스 프로세스에 대해 단일 왕복만 실행하도록 합니다.) LINQ는 지연 및 즉시 계산을 모두 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-238">In those cases, lazy evaluation enables more complex queries to execute only one round trip to the database process.) LINQ enables both lazy and eager evaluation.</span></span> <span data-ttu-id="908f6-239">계산해 보고 최상의 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-239">Measure, and pick the best choice.</span></span>

## <a name="preparing-for-new-features"></a><span data-ttu-id="908f6-240">새 기능 준비</span><span class="sxs-lookup"><span data-stu-id="908f6-240">Preparing for New Features</span></span>

<span data-ttu-id="908f6-241">이 샘플에 대해 작성한 코드는 작업을 수행하는 간단한 프로토타입을 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-241">The code you've written for this sample is an example of creating a simple prototype that does the job.</span></span> <span data-ttu-id="908f6-242">이러한 방식은 문제 영역을 탐색할 수 있는 좋은 방법이며 많은 기능에서 최선의 영구적인 해결책이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-242">This is a great way to explore a problem space, and for many features, it may be the best permanent solution.</span></span> <span data-ttu-id="908f6-243">카드에 대해 *익명 형식*을 사용했으며 각 카드는 문자열로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-243">You've leveraged *anonymous types* for the cards, and each card is represented by strings.</span></span>

<span data-ttu-id="908f6-244">*익명 형식*은 생산성 측면에서 여러 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-244">*Anonymous Types* have many productivity advantages.</span></span> <span data-ttu-id="908f6-245">저장소를 나타내기 위해 클래스를 직접 정의하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-245">You don't need to define a class yourself to represent the storage.</span></span> <span data-ttu-id="908f6-246">컴파일러가 형식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-246">The compiler generates the type for you.</span></span> <span data-ttu-id="908f6-247">컴파일러에서 생성된 형식은 단순 데이터 개체에 대한 많은 모범 사례를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-247">The compiler generated type utilizes many of the best practices for simple data objects.</span></span> <span data-ttu-id="908f6-248">이러한 형식은 *변경할 수 없습니다*. 즉, 생성된 후에는 해당 속성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-248">It's *immutable*, meaning that none of its properties can be changed after it has been constructed.</span></span> <span data-ttu-id="908f6-249">익명 형식은 어셈블리의 내부 형식이므로 해당 어셈블리에 대한 공용 API의 일부로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-249">Anonymous types are internal to an assembly, so they aren't seen as part of the public API for that assembly.</span></span> <span data-ttu-id="908f6-250">익명 형식은 또한 서식 문자열과 해당 값을 반환하는 `ToString()` 메서드의 재정의도 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-250">Anonymous types also contain an override of the `ToString()` method that returns a formatted string with each of the values.</span></span>

<span data-ttu-id="908f6-251">익명 형식에도 단점은 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-251">Anonymous types also have disadvantages.</span></span> <span data-ttu-id="908f6-252">액세스 가능한 이름이 없으므로 반환 값 또는 인수로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-252">They don't have accessible names, so you can't use them as return values or arguments.</span></span> <span data-ttu-id="908f6-253">이러한 익명 형식을 사용하는 모든 메서드는 제네릭 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-253">You'll notice that any methods above that used these anonymous types are generic methods.</span></span> <span data-ttu-id="908f6-254">응용 프로그램이 더 많은 기능으로 커지면 `ToString()`의 재정의가 사용자가 원하는 방식이 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-254">The override of `ToString()` may not be what you want as the application grows more features.</span></span> 

<span data-ttu-id="908f6-255">또한 이 샘플은 각 카드의 세트 및 순서로 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-255">The sample also uses strings for the suit and the rank of each card.</span></span> <span data-ttu-id="908f6-256">확장하기도 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-256">That's quite open ended.</span></span> <span data-ttu-id="908f6-257">C# 형식 시스템은 해당 값에 대해 `enum` 형식을 사용하여 더 나은 코드를 만드는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-257">The C# type system can help us make better code, by leveraging `enum` types for those values.</span></span>

<span data-ttu-id="908f6-258">세트부터 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="908f6-258">Start with the suits.</span></span> <span data-ttu-id="908f6-259">`enum`을 사용할 완벽한 시점입니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-259">This is a perfect time to use an `enum`:</span></span>

[!CODE-csharp[Suit enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet2)]

<span data-ttu-id="908f6-260">또한 `Suits()` 메서드는 형식 및 구현을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-260">The `Suits()` method also changes type and implementation:</span></span>

[!CODE-csharp[Suit IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet4)]

<span data-ttu-id="908f6-261">다음에는 카드 순서에 대해 같은 변경을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-261">Next, do the same change with the Rank of the cards:</span></span>

[!CODE-csharp[Rank enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet3)]

<span data-ttu-id="908f6-262">또한 순서를 생성하는 메서드도 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-262">And the method that generates them:</span></span>

[!CODE-csharp[Rank IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet5)]

<span data-ttu-id="908f6-263">최종 정리 과정으로, 익명 형식에 의존하는 대신 카드를 나타내는 형식을 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-263">As one final cleanup, let's make a type to represent the card, instead of relying on an anonymous type.</span></span> <span data-ttu-id="908f6-264">익명 형식은 간단한 로컬 형식으로 유용하지만 이 예제에서는 카드 게임을 하는 것이 주요 개념 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-264">Anonymous types are great for lightweight, local types, but in this example, the playing card is one of the main concepts.</span></span> <span data-ttu-id="908f6-265">따라서 구체적인 형식을 띠어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-265">It should be a concrete type.</span></span>

[!CODE-csharp[PlayingCard](../../../samples/csharp/getting-started/console-linq/playingcard.cs?name=snippet1)]

<span data-ttu-id="908f6-266">이 형식은 *자동 구현된 읽기 전용 속성*을 사용합니다. 이러한 속성은 생성자에서 설정되며 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-266">This type uses *auto-implemented read-only properties* which are set in the constructor, and then cannot be modified.</span></span> <span data-ttu-id="908f6-267">또한 문자열 출력 서식을 보다 쉽게 지정할 수 있도록 하는 [문자열 보간](../language-reference/tokens/interpolated.md) 기능도 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-267">It also makes use of the [string interpolation](../language-reference/tokens/interpolated.md) feature that makes it easier to format string output.</span></span>

<span data-ttu-id="908f6-268">시작 데크를 생성하는 쿼리가 새 형식을 사용하도록 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-268">Update the query that generates the starting deck to use the new type:</span></span>

```csharp
var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                    from r in Ranks().LogQuery("Value Generation")
                    select new PlayingCard(s, r))
                    .LogQuery("Starting Deck")
                    .ToArray();
```

<span data-ttu-id="908f6-269">컴파일하고 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-269">Compile and run again.</span></span> <span data-ttu-id="908f6-270">출력은 조금 더 간결해지며 코드는 좀 더 명확하고 보다 쉽게 확장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-270">The output is a little cleaner, and the code is a bit more clear and can be extended more easily.</span></span>

## <a name="conclusion"></a><span data-ttu-id="908f6-271">결론</span><span class="sxs-lookup"><span data-stu-id="908f6-271">Conclusion</span></span>

<span data-ttu-id="908f6-272">이 샘플에서는 LINQ에서 사용되는 일부 메서드를 통해 LINQ 지원 코드에서 쉽게 사용할 수 있는 자체 메서드를 만드는 방법을 보여 줬습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-272">This sample showed you some of the methods used in LINQ, how to create your own methods that will be easily used with LINQ enabled code.</span></span> <span data-ttu-id="908f6-273">또한 지연 계산과 즉시 계산 간의 차이점 그리고 이러한 결정이 성능에 미칠 수 있는 결과도 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-273">It also showed you the differences between lazy and eager evaluation, and the effect that decision can have on performance.</span></span>

<span data-ttu-id="908f6-274">마술사의 한 가지 기술에 대해서도 약간 배웠습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-274">You learned a bit about one magician's technique.</span></span> <span data-ttu-id="908f6-275">마술사들은 데크에서 모든 카드가 이동하는 위치를 제어할 수 있으므로 파로 셔플 기술을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-275">Magicians use the faro shuffle because they can control where every card moves in the deck.</span></span> <span data-ttu-id="908f6-276">일부 마술에서 마술사는 청중 중 한 명에게 데크 맨 위에 카드를 놓아 달라고 부탁한 후 몇 번 섞은 다음 해당 카드의 위치를 알아냅니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-276">In some tricks, the magician has an audience member place a card on top of the deck, and shuffles a few times, knowing where that card goes.</span></span> <span data-ttu-id="908f6-277">특정 방식으로 데크를 셋팅해야 하는 마술도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-277">Other illusions require the deck set a certain way.</span></span> <span data-ttu-id="908f6-278">마술사는 마술을 하기 전에 데크를 셋팅합니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-278">A magician will set the deck prior to performing the trick.</span></span> <span data-ttu-id="908f6-279">그런 후 내부 순서 섞기를 사용해서 데크를 5번 섞습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-279">Then she will shuffle the deck 5 times using an inner shuffle.</span></span> <span data-ttu-id="908f6-280">무대에서 무작위로 섞인 데크를 보여준 다음 3번 더 섞은 후 원하는 방식과 정확히 일치하게 데크를 셋팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="908f6-280">On stage, she can show what looks like a random deck, shuffle it 3 more times, and have the deck set exactly how she wants.</span></span>
