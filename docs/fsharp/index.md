---
title: "F# 가이드"
description: "F #,.NET에서 실행 되는 함수형 프로그래밍 언어에 알아봅니다."
keywords: .NET, .NET Core
author: jackfoxy
ms.author: phcart
ms.date: 12/01/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: 45f5d2ca794ccea7a35cf6c0bf9d58a3e6500453
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="f-guide"></a><span data-ttu-id="9ffae-104">F# 가이드</span><span class="sxs-lookup"><span data-stu-id="9ffae-104">F# Guide</span></span>

<span data-ttu-id="9ffae-105">F #은.NET에서 실행 되는 함수형 프로그래밍 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="9ffae-105">F# is a functional programming language which runs on .NET.</span></span>  <span data-ttu-id="9ffae-106">함수형 프로그래밍 구문을 지원 외에 개체 프로그래밍 기능을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ffae-106">In addition to supporting functional programming constructs, it also has object programming capabilities.</span></span>  <span data-ttu-id="9ffae-107">개체 지향 기능을 사용한 함수형 프로그래밍의이 하이브리드 하면 F # 모든 태스크에 대 한 실용적인 언어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ffae-107">This hybrid of functional programming with object-oriented capabilities makes F# a pragmatic language for accomplishing any task.</span></span>

## <a name="if-youre-new-to-f"></a><span data-ttu-id="9ffae-108">F #을 처음 접하는 경우</span><span class="sxs-lookup"><span data-stu-id="9ffae-108">If You're New to F#</span></span> #

<span data-ttu-id="9ffae-109">F #에 익숙하지 않다면로 시작는 [둘러보기의 F #](tour.md) 언어의 개요 및 그 프로그래밍 개념 중 일부를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9ffae-109">If you're new to F#, begin with the [Tour of F#](tour.md) to get an overview of the language and some of its programming concepts.</span></span>  <span data-ttu-id="9ffae-110">Visual Studio를 사용 하 여 자습서 프로젝트 템플릿에 동일한 콘텐츠를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ffae-110">If you're using Visual Studio, the Tutorial project template contains the same content.</span></span>

## <a name="if-youre-experienced-with-f"></a><span data-ttu-id="9ffae-111">F #을 사용한 경험이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="9ffae-111">If You're Experienced with F#</span></span> #

<span data-ttu-id="9ffae-112">F # 관련 방식을 하거나 특정 언어 구문에 대 한 자세한 참조는 [언어 참조](language-reference/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ffae-112">If you know your way around F#, or want to learn more about a specific language construct, see the [Language Reference](language-reference/index.md).</span></span>  <span data-ttu-id="9ffae-113">F # 언어의 모든 기능에 대 한 철저 한이 가이드가.입니다.</span><span class="sxs-lookup"><span data-stu-id="9ffae-113">It's a thorough guide of all F# language capabilities.</span></span>

<span data-ttu-id="9ffae-114">또한는 [F # 핵심 라이브러리 참조가](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) FSharp.Core, F #의 일부인 핵심 라이브러리에 대 한 학습을 위한 중요 한 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="9ffae-114">Additionally, the [F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) is a great resource for learning about FSharp.Core, the core library which is a part of F#.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="9ffae-115">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="9ffae-115">The F# Software Foundation</span></span>

<span data-ttu-id="9ffae-116">Microsoft 기본 개발자의 F # 언어와 해당 도구 이지만, F #는 또한 뒷받침 되며는 독립적인 foundation는 F # 소프트웨어 Foundation (FSSF).</span><span class="sxs-lookup"><span data-stu-id="9ffae-116">Although Microsoft is the primary developer of the F# language and its tooling, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="9ffae-117">F# Software Foundation의 임무는 F# 프로그래밍 언어를 홍보하고 보호하고 발전시키며, F# 프로그래머의 다양한 국제 커뮤니티의 성장을 지원하고 용이하게 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9ffae-117">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="9ffae-118">자세한 내용을 알아보고 참여하려면 [fsharp.org](http://fsharp.org)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ffae-118">To learn more and get involved, check out [fsharp.org](http://fsharp.org).</span></span>

## <a name="documentation"></a><span data-ttu-id="9ffae-119">설명서</span><span class="sxs-lookup"><span data-stu-id="9ffae-119">Documentation</span></span>

* [<span data-ttu-id="9ffae-120">자습서</span><span class="sxs-lookup"><span data-stu-id="9ffae-120">Tutorials</span></span>](tutorials/getting-started/index.md)
* <span data-ttu-id="9ffae-121">[고급 값으로 함수](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span><span class="sxs-lookup"><span data-stu-id="9ffae-121">[Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span></span>
* [<span data-ttu-id="9ffae-122">언어 참조</span><span class="sxs-lookup"><span data-stu-id="9ffae-122">Language Reference</span></span>](language-reference/index.md)
* [<span data-ttu-id="9ffae-123">F# 주요 라이브러리 참조</span><span class="sxs-lookup"><span data-stu-id="9ffae-123">F# Core Library Reference</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)

## <a name="online-reading-resources"></a><span data-ttu-id="9ffae-124">온라인으로 리소스 읽기</span><span class="sxs-lookup"><span data-stu-id="9ffae-124">Online Reading Resources</span></span>

* [<span data-ttu-id="9ffae-125">재미와 수익을 위한 F# Gitbook</span><span class="sxs-lookup"><span data-stu-id="9ffae-125">F# for Fun and Profit Gitbook</span></span>](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) 
* [<span data-ttu-id="9ffae-126">F# 프로그래밍 Wikibook</span><span class="sxs-lookup"><span data-stu-id="9ffae-126">F# Programming Wikibook</span></span>](https://en.wikibooks.org/wiki/F_Sharp_Programming)

## <a name="video-learning-resources"></a><span data-ttu-id="9ffae-127">동영상 학습 리소스</span><span class="sxs-lookup"><span data-stu-id="9ffae-127">Video Learning Resources</span></span>

* [<span data-ttu-id="9ffae-128">YouTube의 F# 시리즈 프로그래밍 소개</span><span class="sxs-lookup"><span data-stu-id="9ffae-128">Introduction to Programming with F# series on YouTube</span></span>](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC)
* [<span data-ttu-id="9ffae-129">FSharpTV의 F# 시리즈 소개</span><span class="sxs-lookup"><span data-stu-id="9ffae-129">Introduction to F# series on FSharpTV</span></span>](https://fsharp.tv/courses/fsharp-programming-intro/)

## <a name="further-resources"></a><span data-ttu-id="9ffae-130">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="9ffae-130">Further Resources</span></span>

* [<span data-ttu-id="9ffae-131">fsharp.org의 F# 학습 리소스</span><span class="sxs-lookup"><span data-stu-id="9ffae-131">F# Learning Resources on fsharp.org</span></span>](http://fsharp.org/learn.html)
* [<span data-ttu-id="9ffae-132">F# 코드 조각 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="9ffae-132">F# Snippets Website</span></span>](http://www.fssnip.net)
* [<span data-ttu-id="9ffae-133">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="9ffae-133">F# Software Foundation</span></span>](http://fsharp.org)