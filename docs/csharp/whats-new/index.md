---
title: "C#의 새로운 기능 - C# 가이드"
description: "C# 언어 진화 과정"
keywords: "C#, 최신 기능, 새로운 기능, Roslyn"
author: BillWagner
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.translationtype: HT
ms.sourcegitcommit: df0438dd742db802bb0f935d840006236d5d9bf9
ms.openlocfilehash: 0a328f62a02aea223340fcc00e839e841041a7d6
ms.contentlocale: ko-kr
ms.lasthandoff: 08/29/2017

---

# <a name="whats-new-in-c"></a><span data-ttu-id="0483c-104">C#의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="0483c-104">What's new in C#</span></span> #

<span data-ttu-id="0483c-105">이 페이지는 C# 언어의 각 주요 릴리스에서 새로운 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-105">This page provides a roadmap of new features in each major release of the C# language.</span></span> <span data-ttu-id="0483c-106">아래 링크는 각 릴리스에 추가된 주요 기능에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-106">The links below provide detailed information on the major features added in each release.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0483c-107">C# 언어는 일부 기능의 경우 *표준 라이브러리*의 형식 및 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-107">The C# language relies on types and methods in a *standard library* for some of the features.</span></span> <span data-ttu-id="0483c-108">한 가지 예는 예외 처리입니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-108">One example is exception processing.</span></span> <span data-ttu-id="0483c-109">모든 `throw` 문 또는 식은 throw된 개체가 @System.Exception에서 파생되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-109">Every `throw` statement or expression is checked to ensure the object being thrown is derived from @System.Exception.</span></span> <span data-ttu-id="0483c-110">마찬가지로 모든 `catch`는 발견되는 형식이 @System.Exception에서 파생되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-110">Similarly, every `catch` is checked to ensure that the type being caught is derived from @System.Exception.</span></span> <span data-ttu-id="0483c-111">각 버전은 새 요구 사항을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-111">Each version may add new requirements.</span></span> <span data-ttu-id="0483c-112">이전 환경에서 최신 언어 기능을 사용하려면 특정 라이브러리를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-112">To use the latest language features in older environments, you may need to install specific libraries.</span></span> <span data-ttu-id="0483c-113">이러한 내용은 각 특정 버전에 대한 페이지에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-113">These are documented in the page for each specific version.</span></span> <span data-ttu-id="0483c-114">이 종속성의 배경은 [언어 및 라이브러리 간 관계](relationships-between-language-and-library.md)에서 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-114">You can learn more about the [relationships between language and library](relationships-between-language-and-library.md) for background on this dependency.</span></span> 

* <span data-ttu-id="0483c-115">[C# 7.1](csharp-7-1.md):</span><span class="sxs-lookup"><span data-stu-id="0483c-115">[C# 7.1](csharp-7-1.md):</span></span>
    - <span data-ttu-id="0483c-116">이 페이지에서는 C# 언어의 최신 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-116">This page describes the latest features in the C# language.</span></span> <span data-ttu-id="0483c-117">여기서는 현재 [Visual Studio 2017 버전 15.3](https://www.visualstudio.com/vs/whatsnew/) 및 [.NET Core 2.0 SDK](../../core/whats-new/index.md)에서 사용 가능한 C# 7.1을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-117">This covers C# 7.1, currently available in [Visual Studio 2017 version 15.3](https://www.visualstudio.com/vs/whatsnew/), and in the [.NET Core 2.0 SDK](../../core/whats-new/index.md).</span></span>

* <span data-ttu-id="0483c-118">[C# 7](csharp-7.md):</span><span class="sxs-lookup"><span data-stu-id="0483c-118">[C# 7](csharp-7.md):</span></span>
    - <span data-ttu-id="0483c-119">이 페이지에서는 C# 7에 추가된 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-119">This page describes the features added in C# 7.</span></span> <span data-ttu-id="0483c-120">이러한 기능은 [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) 및 [.NET Core 1.0](../../core/whats-new/index.md) 이상에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-120">Theses were added in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) and [.NET Core 1.0](../../core/whats-new/index.md) and later</span></span>
     
* <span data-ttu-id="0483c-121">[C# 6](csharp-6.md):</span><span class="sxs-lookup"><span data-stu-id="0483c-121">[C# 6](csharp-6.md):</span></span>
    - <span data-ttu-id="0483c-122">이 페이지에서는 C# 6에 추가된 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-122">This page describes the features that were added in C# 6.</span></span> <span data-ttu-id="0483c-123">이러한 기능은 Windows 개발자를 위한 Visual Studio 2015와 macOS 및 Linux에서 C#을 사용하는 개발자를 위한 .NET Core 1.0에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-123">These features are available in Visual Studio 2015 for Windows developers, and on .NET Core 1.0 for developers exploring C# on macOS and Linux.</span></span>

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* <span data-ttu-id="0483c-124">[플랫폼 간 지원](../../core/index.md):</span><span class="sxs-lookup"><span data-stu-id="0483c-124">[Cross Platform Support](../../core/index.md):</span></span>
    - <span data-ttu-id="0483c-125">C#은 .NET Core 지원을 통해 여러 플랫폼에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-125">C#, through .NET Core support, runs on multiple platforms.</span></span> <span data-ttu-id="0483c-126">macOS 또는 지원되는 여러 Linux 배포판 중 하나에서 C#을 사용해보고 싶다면 .NET Core에 관해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="0483c-126">If you are interested in trying C# on macOS, or on one of the many supported Linux distributions, learn more about .NET Core.</span></span>

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a><span data-ttu-id="0483c-127">이전 버전</span><span class="sxs-lookup"><span data-stu-id="0483c-127">Previous Versions</span></span>
<span data-ttu-id="0483c-128">다음은 이전 버전의 C# 언어와 Visual Studio .NET에 추가된 주요 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-128">The following lists key features that were introduced in previous versions of the C# language and Visual Studio .NET.</span></span>  
  
 * <span data-ttu-id="0483c-129">Visual Studio .NET 2013:</span><span class="sxs-lookup"><span data-stu-id="0483c-129">Visual Studio .NET 2013:</span></span> 
     - <span data-ttu-id="0483c-130">이 버전의 Visual Studio에는 버그 수정, 성능 향상 및 <!--Link to ../roslyn/index.md-->.NET 컴파일러 플랫폼 SDK로 발전한 .NET 컴파일러 플랫폼(“Roslyn”)의 기술 미리 보기가 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0483c-130">This version of Visual Studio included bug fixes, performance improvements, and technology previews of .NET Compiler Platform ("Roslyn") which became the .NET Compiler Platform SDK<!--Link to ../roslyn/index.md-->.</span></span>

 * <span data-ttu-id="0483c-131">C# 5, Visual Studio .NET 2012:</span><span class="sxs-lookup"><span data-stu-id="0483c-131">C# 5, Visual Studio .NET 2012:</span></span> 
     - <span data-ttu-id="0483c-132">`Async` / `await` 및 [호출자 정보](../programming-guide/concepts/caller-information.md) 특성.</span><span class="sxs-lookup"><span data-stu-id="0483c-132">`Async` / `await`, and [caller information](../programming-guide/concepts/caller-information.md) attributes.</span></span>

 * <span data-ttu-id="0483c-133">C# 4, Visual Studio .NET 2010:</span><span class="sxs-lookup"><span data-stu-id="0483c-133">C# 4, Visual Studio .NET 2010:</span></span> 
     - <span data-ttu-id="0483c-134">`Dynamic`, [명명된 인수](../programming-guide/classes-and-structs/named-and-optional-arguments.md), 선택적 매개 변수, 제네릭 [공변성(Covariance) 및 반공변성(Contravariance)](../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="0483c-134">`Dynamic`, [named arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md), optional parameters, and generic [covariance and contra variance](../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

 * <span data-ttu-id="0483c-135">C# 3, Visual Studio .NET 2008:</span><span class="sxs-lookup"><span data-stu-id="0483c-135">C# 3, Visual Studio .NET 2008:</span></span> 
     - <span data-ttu-id="0483c-136">개체 및 컬렉션 이니셜라이저, 람다 식, 확장 메서드, 익명 형식, 자동 속성, 로컬 `var` 형식 유추 및 [LINQ(Language Integrated Query)](../programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="0483c-136">Object and collection initializers, lambda expressions, extension methods, anonymous types, automatic properties, local `var` type inference, and [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).</span></span>

 * <span data-ttu-id="0483c-137">C# 2, Visual Studio .NET 2005:</span><span class="sxs-lookup"><span data-stu-id="0483c-137">C# 2, Visual Studio .NET 2005:</span></span> 
     - <span data-ttu-id="0483c-138">무명 메서드, 제네릭, nullable 형식, 반복기/yield, `static` 클래스, 대리자의 공변성(Covariance) 및 반공변성(Contravariance).</span><span class="sxs-lookup"><span data-stu-id="0483c-138">Anonymous methods, generics, nullable types, iterators/yield, `static` classes, and covariance and contra variance for delegates.</span></span>

 * <span data-ttu-id="0483c-139">C# 1.1, Visual Studio .NET 2003:</span><span class="sxs-lookup"><span data-stu-id="0483c-139">C# 1.1, Visual Studio .NET 2003:</span></span> 
     - <span data-ttu-id="0483c-140">`#line` pragma 및 xml 문서 주석.</span><span class="sxs-lookup"><span data-stu-id="0483c-140">`#line` pragma and xml doc comments.</span></span>

 * <span data-ttu-id="0483c-141">C# 1, Visual Studio .NET 2002:</span><span class="sxs-lookup"><span data-stu-id="0483c-141">C# 1, Visual Studio .NET 2002:</span></span> 
     - <span data-ttu-id="0483c-142">[C#](../csharp.md)의 첫 번째 릴리스.</span><span class="sxs-lookup"><span data-stu-id="0483c-142">The first release of [C#](../csharp.md).</span></span>   

