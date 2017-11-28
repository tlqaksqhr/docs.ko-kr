---
title: Expression Trees
description: ".NET Core의 식 트리에 대해 알아본 다음 이를 사용하여 검사, 수정 및 실행할 수 있는 구조로 코드를 나타내는 방법을 알아봅니다."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: aceb4719-0d5a-4b19-b01f-b51063bcc54f
ms.openlocfilehash: 3935906d9fca81a094999eefdd49ae4ed56990bf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="expression-trees"></a><span data-ttu-id="09455-104">Expression Trees</span><span class="sxs-lookup"><span data-stu-id="09455-104">Expression Trees</span></span>

<span data-ttu-id="09455-105">LINQ를 사용했다면 `Func` 형식이 API 집합의 일부인 풍부한 라이브러리 경험이 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="09455-105">If you have used LINQ, you have experience with a rich library where the `Func` types are part of the API set.</span></span> <span data-ttu-id="09455-106">LINQ에 익숙하지 않은 경우 [LINQ 자습서](linq/index.md) 및 [람다 식](lambda-expressions.md)에 대한 자습서를 먼저 읽어보는 것이 좋습니다. *식 트리*에서는 함수인 인수를 사용하는 보다 풍부한 조작을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="09455-106">(If you are not familiar with LINQ, you probably want to read [the LINQ tutorial](linq/index.md) and the tutorial on [lambda expressions](lambda-expressions.md) before this one.) *Expression Trees* provide richer interaction with the arguments that are functions.</span></span>

<span data-ttu-id="09455-107">LINQ 쿼리를 만들 때 일반적으로 람다 식을 사용하여 함수 인수를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="09455-107">You write function arguments, typically using Lambda Expressions, when you create LINQ queries.</span></span> <span data-ttu-id="09455-108">일반적인 LINQ 쿼리에서 이러한 함수 인수는 컴파일러가 만드는 대리자로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="09455-108">In a typical LINQ query, those function arguments are transformed into a delegate the compiler creates.</span></span> 

<span data-ttu-id="09455-109">보다 풍부한 조작을 원하는 경우 *식 트리*를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09455-109">When you want to have a richer interaction, you need to use *Expression Trees*.</span></span>
<span data-ttu-id="09455-110">식 트리는 검사, 수정 또는 실행할 수 있는 구조로 코드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="09455-110">Expression Trees represent code as a structure that you can examine, modify, or execute.</span></span> <span data-ttu-id="09455-111">이러한 도구는 런타임에 코드를 조작할 수 있는 강력한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="09455-111">These tools give you the power to manipulate code during run time.</span></span> <span data-ttu-id="09455-112">실행 중인 알고리즘을 검사하고 새 기능을 삽입하는 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09455-112">You can write code that examines running algorithms, or injects new capabilities.</span></span> <span data-ttu-id="09455-113">보다 고급 시나리오에서는 실행 중인 알고리즘을 수정하고 C# 식을 다른 형태로 변환하여 다른 환경에서 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09455-113">In more advanced scenarios, you can modify running algorithms, and even translate C# expressions into another form for execution in another environment.</span></span>

<span data-ttu-id="09455-114">식 트리를 사용하는 코드를 이미 작성했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09455-114">You've likely already written code that uses Expression Trees.</span></span> <span data-ttu-id="09455-115">Entity Framework의 LINQ API는 LINQ 쿼리 식 패턴에 대한 인수로 식 트리를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="09455-115">Entity Framework's LINQ APIs accept Expression Trees as the arguments for the LINQ Query Expression Pattern.</span></span>
<span data-ttu-id="09455-116">따라서 [Entity Framework](http://docs.efproject.net/en/latest/)는 C#에서 작성된 쿼리를 데이터베이스 엔진에서 실행되는 SQL로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09455-116">That enables [Entity Framework](http://docs.efproject.net/en/latest/) to translate the query you wrote in C# into SQL that executes in the database engine.</span></span> <span data-ttu-id="09455-117">또 다른 예로 널리 사용되는 .NET 모의 프레임워크인 [Moq](https://github.com/Moq/moq)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09455-117">Another example is [Moq](https://github.com/Moq/moq), which is a popular mocking framework for .NET.</span></span>

<span data-ttu-id="09455-118">이 자습서의 나머지 섹션에서는 식 트리의 정의를 살펴보고, 식 트리를 지원하는 프레임워크 클래스를 검사하며, 식 트리로 작업하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="09455-118">The remaining sections of this tutorial will explore what Expression Trees are, examine the framework classes that support expression trees, and show you how to work with expression trees.</span></span> <span data-ttu-id="09455-119">식 트리를 읽는 방법, 식 트리를 만드는 방법, 수정된 식 트리를 만드는 방법, 식 트리로 표시되는 코드를 실행하는 방법 등을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="09455-119">You'll learn how to read expression trees, how to create expression trees, how to create modified expression trees, and how to execute the code represented by expression trees.</span></span> <span data-ttu-id="09455-120">자습서를 읽고 나면 이러한 구조를 사용하여 풍부한 적응 알고리즘을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09455-120">After reading, you will be ready to use these structures to create rich adaptive algorithms.</span></span>

1. [<span data-ttu-id="09455-121">식 트리 설명</span><span class="sxs-lookup"><span data-stu-id="09455-121">Expression Trees Explained</span></span>](expression-trees-explained.md)

    <span data-ttu-id="09455-122">*식 트리*의 구조와 개념을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="09455-122">Understand the structure and concepts behind *Expression Trees*.</span></span>
    
2. [<span data-ttu-id="09455-123">식 트리를 지원하는 프레임워크 형식</span><span class="sxs-lookup"><span data-stu-id="09455-123">Framework Types Supporting Expression Trees</span></span>](expression-classes.md)
    
    <span data-ttu-id="09455-124">식 트리를 정의하고 조작하는 구조 및 클래스에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="09455-124">Learn about the structures and classes that define and manipulate expression trees.</span></span>
    
3. [<span data-ttu-id="09455-125">식 실행</span><span class="sxs-lookup"><span data-stu-id="09455-125">Executing Expressions</span></span>](expression-trees-execution.md)

    <span data-ttu-id="09455-126">람다 식으로 표시되는 식 트리를 대리자로 변환하고 결과 대리자를 실행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="09455-126">Learn how to convert an expression tree represented as a Lambda Expression into a delegate and execute the resulting delegate.</span></span>

4. [<span data-ttu-id="09455-127">식 해석</span><span class="sxs-lookup"><span data-stu-id="09455-127">Interpreting Expressions</span></span>](expression-trees-interpreting.md)

    <span data-ttu-id="09455-128">*식 트리*를 트래버스하고 검사하여 식 트리가 나타내는 코드를 이해하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="09455-128">Learn how to traverse and examine *expression trees* to understand what code the expression tree represents.</span></span>

5. [<span data-ttu-id="09455-129">식 작성</span><span class="sxs-lookup"><span data-stu-id="09455-129">Building Expressions</span></span>](expression-trees-building.md)

    <span data-ttu-id="09455-130">식 트리에 대한 노드를 생성하고 식 트리를 작성하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="09455-130">Learn how to construct the nodes for an expression tree and build expression trees.</span></span>

6. [<span data-ttu-id="09455-131">식 변환</span><span class="sxs-lookup"><span data-stu-id="09455-131">Translating Expressions</span></span>](expression-trees-translating.md)

    <span data-ttu-id="09455-132">식 트리의 수정된 복사본을 작성하거나 식 트리를 다른 형식으로 변환하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="09455-132">Learn how to build a modified copy of an expression tree, or translate an expression tree into a different format.</span></span>

7. [<span data-ttu-id="09455-133">요약</span><span class="sxs-lookup"><span data-stu-id="09455-133">Summing up</span></span>](expression-trees-summary.md)

    <span data-ttu-id="09455-134">식 트리에 대한 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="09455-134">Review the information on expression trees.</span></span>
    
