---
title: "대리자 소개"
description: "기본 개념을 소개하고 대리자에 대한 언어 디자인 목표를 설명하는 이 개요 항목에서 대리자에 대해 알아봅니다."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 59b61d77-84e5-457b-8da5-fb5f24ca6ed6
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: dd4c68fb4f960d0c2d5cbdc9e699650070cacaf1
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="introduction-to-delegates"></a><span data-ttu-id="696b4-104">대리자 소개</span><span class="sxs-lookup"><span data-stu-id="696b4-104">Introduction to Delegates</span></span>

[<span data-ttu-id="696b4-105">이전</span><span class="sxs-lookup"><span data-stu-id="696b4-105">Previous</span></span>](delegates-events.md)

<span data-ttu-id="696b4-106">대리자는 .NET에서 *런타임에 바인딩* 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-106">Delegates provide a *late binding* mechanism in .NET.</span></span> <span data-ttu-id="696b4-107">런타임에 바인딩은 호출자가 알고리즘의 일부를 구현하는 하나 이상의 메서드도 제공하는 알고리즘을 만든다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-107">Late Binding means that you create an algorithm where the caller also supplies at least one method that implements part of the algorithm.</span></span>

<span data-ttu-id="696b4-108">예를 들어 천문학 응용 프로그램에서 별 목록을 정렬한다는 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="696b4-108">For example, consider sorting a list of stars in an astronomy application.</span></span>
<span data-ttu-id="696b4-109">이러한 별은 지구로부터의 거리, 별의 크기, 인식된 밝기 등에 따라 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-109">You may choose to sort those stars by their distance from the earth, or the magnitude of the star, or their perceived brightness.</span></span>

<span data-ttu-id="696b4-110">모든 경우에 Sort() 메서드는 기본적으로 동일한 작업을 수행합니다. 즉, 몇 가지 비교를 통해 목록의 항목을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-110">In all those cases, the Sort() method does essentially the same thing: arranges the items in the list based on some comparison.</span></span> <span data-ttu-id="696b4-111">별 두 개를 비교하는 코드는 각 정렬 순서마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-111">The code that compares two stars is different for each of the sort orderings.</span></span>

<span data-ttu-id="696b4-112">이러한 종류의 솔루션이 반세기 동안 소프트웨어에서 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-112">These kinds of solutions have been used in software for half a century.</span></span>
<span data-ttu-id="696b4-113">C# 언어 대리자 개념은 최고 수준의 언어 지원 및 해당 개념 관련 형식 안정성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-113">The C# language delegate concept provides first class language support, and type safety around the concept.</span></span>

<span data-ttu-id="696b4-114">이 시리즈의 뒷부분에서 살펴보겠지만 이러한 알고리즘에 대해 작성하는 C# 코드는 형식이 안전하며 언어 및 컴파일러를 활용하여 형식이 인수 및 반환 형식과 일치하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-114">As you'll see later in this series, the C# code you write for algorithms like this is type safe, and leverages the language and the compiler to ensure that the types match for arguments and return types.</span></span>

## <a name="language-design-goals-for-delegates"></a><span data-ttu-id="696b4-115">대리자의 언어 디자인 목표</span><span class="sxs-lookup"><span data-stu-id="696b4-115">Language Design Goals for Delegates</span></span>

<span data-ttu-id="696b4-116">언어 디자이너는 결국 대리자가 된 기능에 대해 여러 가지 목표를 열거했습니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-116">The language designers enumerated several goals for the feature that eventually became delegates.</span></span>

<span data-ttu-id="696b4-117">팀은 런타임에 바인딩 알고리즘에 사용할 수 있는 공용 언어 구문을 원했습니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-117">The team wanted a common language construct that could be used for any late binding algorithms.</span></span> <span data-ttu-id="696b4-118">이를 통해 개발자는 하나의 개념을 익히고 여러 가지 다양한 소프트웨어 문제에서 동일한 개념을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-118">That enables developers to learn one concept, and use that same concept across many different software problems.</span></span>

<span data-ttu-id="696b4-119">두 번째로 팀은 단일 및 멀티캐스트 메서드 호출을 모두 지원하기를 원했습니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-119">Second, the team wanted to support both single and multi-cast method calls.</span></span> <span data-ttu-id="696b4-120">멀티캐스트 대리자는 여러 메서드가 함께 연결된 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-120">(Multicast delegates are delegates where multiple methods have been chained together.</span></span> <span data-ttu-id="696b4-121">예제는 [이 시리즈의 뒷부분](delegate-class.md)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-121">You'll see examples [later in this series](delegate-class.md).</span></span> 

<span data-ttu-id="696b4-122">팀은 개발자가 모든 C# 구문에서 기대하는 동일한 형식 안전성을 대리자가 지원하기를 원했습니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-122">The team wanted delegates to support the same type safety that developers expect from all C# constructs.</span></span> 

<span data-ttu-id="696b4-123">마지막으로 팀은 이벤트 패턴이 하나의 특정 패턴이며, 이 패턴에서는 대리자나 모든 런타임에 바인딩 알고리즘이 매우 유용함을 인식했습니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-123">Finally, the team recognized that an event pattern is one specific pattern where delegates, or any late binding algorithm) is very useful.</span></span> <span data-ttu-id="696b4-124">팀은 대리자에 대한 코드가 .NET 이벤트 패턴의 기반을 제공할 수 있도록 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-124">The team wanted to ensure that the code for delegates could provide the basis for the .NET event pattern.</span></span>

<span data-ttu-id="696b4-125">이러한 모든 작업의 결과가 C# 및 .NET의 대리자와 이벤트 지원이었습니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-125">The result of all that work was the delegate and event support in C# and .NET.</span></span> <span data-ttu-id="696b4-126">이 섹션의 나머지 문서에서는 언어 기능, 라이브러리 지원 및 대리자를 사용하여 작업할 때 일반적으로 사용되는 말에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-126">The remaining articles in this section will cover the language features, the library support, and the common idioms that are used when you work with delegates.</span></span>

<span data-ttu-id="696b4-127">`delegate` 키워드와 이 키워드에서 생성하는 코드에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-127">You'll learn about the `delegate` keyword and what code it generates.</span></span> <span data-ttu-id="696b4-128">`System.Delegate` 클래스의 기능 및 해당 기능을 사용하는 방법에 대해서도 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-128">You'll learn about the features in the `System.Delegate` class, and how those features are used.</span></span> <span data-ttu-id="696b4-129">형식이 안전한 대리자를 만드는 방법 및 대리자를 통해 호출할 수 있는 메서드를 만드는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-129">You'll learn how to create type safe delegates, and how to create methods that can be invoked through delegates.</span></span> <span data-ttu-id="696b4-130">또한 람다 식을 사용하여 대리자 및 이벤트로 작업하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-130">You'll also learn how to work with delegates and events by using Lambda expressions.</span></span> <span data-ttu-id="696b4-131">대리자가 LINQ 구성 요소 중 하나가 되는 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-131">You'll see where delegates become one of the building blocks for LINQ.</span></span> <span data-ttu-id="696b4-132">어떻게 대리자가 .NET 이벤트 패턴의 기반이 되는지와 어떻게 다른지도 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-132">You'll learn how delegates are the basis for the .NET event pattern, and how they are different.</span></span>

<span data-ttu-id="696b4-133">전반적으로 어떻게 대리자가 .NET의 프로그래밍과 프레임워크 API 작업의 필수적인 부분이 되는지를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-133">Overall, you'll see how delegates are an integral part of programming in .NET and working with the framework APIs.</span></span>

<span data-ttu-id="696b4-134">이제 시작해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="696b4-134">Let's get started.</span></span>

[<span data-ttu-id="696b4-135">다음</span><span class="sxs-lookup"><span data-stu-id="696b4-135">Next</span></span>](delegate-class.md)

