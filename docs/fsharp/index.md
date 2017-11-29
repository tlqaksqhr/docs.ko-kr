---
title: "F# 가이드"
description: "F # 프로그래밍 언어에 대 한.NET 함수형 프로그래밍에 대 한 기본 지원을 제공 하는 오픈 소스 언어에 알아봅니다."
keywords: .NET, .NET Core
author: jackfoxy
ms.author: phcart
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: 4ddd77cef6cf70a63f1af81359d82eda27a01593
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="f-guide"></a><span data-ttu-id="e83f3-104">F# 가이드</span><span class="sxs-lookup"><span data-stu-id="e83f3-104">F# Guide</span></span>

<span data-ttu-id="e83f3-105">F#은 개체 지향 및 명령형 프로그래밍에 대한 지원과 함께 함수형 프로그래밍에 대한 최상의 지원을 제공하는 .NET용 플랫폼 간 오픈 소스 프로그래밍 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="e83f3-105">F# is a cross-platform, open source programming language for .NET which provides first-class support for functional programming, along with support of object-oriented and imperative programming.</span></span>  <span data-ttu-id="e83f3-106">Visual F# 컴파일러 및 도구는 F# 프로그래밍 언어에 대한 Microsoft의 구현 및 도구이며 F#을 .NET의 최고 구성원으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e83f3-106">The Visual F# compiler and tooling are Microsoft's implementation and tooling for the F# programming language, making F# a first-class member of .NET.</span></span>

## <a name="if-youre-new-to-f"></a><span data-ttu-id="e83f3-107">F #을 처음 접하는 경우</span><span class="sxs-lookup"><span data-stu-id="e83f3-107">If You're New to F#</span></span> #

<span data-ttu-id="e83f3-108">F #에 익숙하지 않다면로 시작는 [둘러보기의 F #](tour.md) 언어의 개요를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e83f3-108">If you're new to F#, begin with the [Tour of F#](tour.md) to get an overview of the language.</span></span>

<span data-ttu-id="e83f3-109">살펴보는 것이 좋습니다는 [고급 값으로 함수](introduction-to-functional-programming/functions-as-first-class-values.md) <!--[Introduction to Functional Progamming](introduction-to-functional-programming/index.md)--> F #을 사용한 작업에 필수적인 함수형 프로그래밍 개념에 알아보려면 합니다.</span><span class="sxs-lookup"><span data-stu-id="e83f3-109">It's also recommended that you go through the [Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Progamming](introduction-to-functional-programming/index.md)--> to learn Functional Programming concepts which are essential to working with F#.</span></span>

<span data-ttu-id="e83f3-110">[자습서](tutorials/getting-started/index.md)에서는 언어의 다양한 기술 수준 및 기능에 대한 단계별 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e83f3-110">The [Tutorials](tutorials/getting-started/index.md) also have step-by-step guides for various skill levels and features of the language.</span></span>

## <a name="if-youre-experienced-with-f"></a><span data-ttu-id="e83f3-111">F #을 사용한 경험이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="e83f3-111">If You're Experienced with F#</span></span> #

<span data-ttu-id="e83f3-112">F#에 대해 잘 알고 있는 경우 언어의 각 측면을 철저히 설명하고 다양한 코드 샘플로 보완하는 [언어 참조](language-reference/index.md)에서 많은 용례를 찾아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e83f3-112">If you know your way around F#, you'll find a lot of use in the [Language Reference](language-reference/index.md), which documents each aspect of the language thoroughly, supplemented by numerous code samples.</span></span>  <span data-ttu-id="e83f3-113">[F# 주요 라이브러리 참조](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)에서도 많은 용례를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e83f3-113">You'll also find a lot of use in the [F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference).</span></span>  <span data-ttu-id="e83f3-114">F # 핵심 라이브러리 참조가에 이러한 현재 문서와 MSDN 떨어진 곳에 결국 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e83f3-114">The F# Core Library Reference will eventually move away from MSDN and into these current docs.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="e83f3-115">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="e83f3-115">The F# Software Foundation</span></span>

<span data-ttu-id="e83f3-116">Microsoft가 F# 언어 및 Visual F# 도구의 주요 개발자이지만 독립 기관인 FSSF(F# Software Foundation)에서도 F#을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e83f3-116">Although Microsoft is the primary developer of the F# language and Visual F# Tooling, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="e83f3-117">F# Software Foundation의 임무는 F# 프로그래밍 언어를 홍보하고 보호하고 발전시키며, F# 프로그래머의 다양한 국제 커뮤니티의 성장을 지원하고 용이하게 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e83f3-117">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="e83f3-118">자세한 내용을 알아보고 참여하려면 [fsharp.org](http://fsharp.org)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e83f3-118">To learn more and get involved, check out [fsharp.org](http://fsharp.org).</span></span>

## <a name="documentation"></a><span data-ttu-id="e83f3-119">설명서</span><span class="sxs-lookup"><span data-stu-id="e83f3-119">Documentation</span></span>

* [<span data-ttu-id="e83f3-120">자습서</span><span class="sxs-lookup"><span data-stu-id="e83f3-120">Tutorials</span></span>](tutorials/getting-started/index.md)
* <span data-ttu-id="e83f3-121">[고급 값으로 함수](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span><span class="sxs-lookup"><span data-stu-id="e83f3-121">[Functions as First-Class Values](introduction-to-functional-programming/functions-as-first-class-values.md)<!--[Introduction to Functional Programming](introduction-to-functional-programming/index.md)--></span></span>
* [<span data-ttu-id="e83f3-122">언어 참조</span><span class="sxs-lookup"><span data-stu-id="e83f3-122">Language Reference</span></span>](language-reference/index.md)
* [<span data-ttu-id="e83f3-123">F# 주요 라이브러리 참조</span><span class="sxs-lookup"><span data-stu-id="e83f3-123">F# Core Library Reference</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference)

## <a name="online-reading-resources"></a><span data-ttu-id="e83f3-124">온라인으로 리소스 읽기</span><span class="sxs-lookup"><span data-stu-id="e83f3-124">Online Reading Resources</span></span>

* [<span data-ttu-id="e83f3-125">재미와 수익을 위한 F# Gitbook</span><span class="sxs-lookup"><span data-stu-id="e83f3-125">F# for Fun and Profit Gitbook</span></span>](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) 
* [<span data-ttu-id="e83f3-126">F# 프로그래밍 Wikibook</span><span class="sxs-lookup"><span data-stu-id="e83f3-126">F# Programming Wikibook</span></span>](https://en.wikibooks.org/wiki/F_Sharp_Programming)

## <a name="video-learning-resources"></a><span data-ttu-id="e83f3-127">동영상 학습 리소스</span><span class="sxs-lookup"><span data-stu-id="e83f3-127">Video Learning Resources</span></span>

* [<span data-ttu-id="e83f3-128">YouTube의 F# 시리즈 프로그래밍 소개</span><span class="sxs-lookup"><span data-stu-id="e83f3-128">Introduction to Programming with F# series on YouTube</span></span>](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC)
* [<span data-ttu-id="e83f3-129">FSharpTV의 F# 시리즈 소개</span><span class="sxs-lookup"><span data-stu-id="e83f3-129">Introduction to F# series on FSharpTV</span></span>](https://fsharp.tv/courses/fsharp-programming-intro/)

## <a name="further-resources"></a><span data-ttu-id="e83f3-130">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="e83f3-130">Further Resources</span></span>

* [<span data-ttu-id="e83f3-131">fsharp.org의 F# 학습 리소스</span><span class="sxs-lookup"><span data-stu-id="e83f3-131">F# Learning Resources on fsharp.org</span></span>](http://fsharp.org/learn.html)
* [<span data-ttu-id="e83f3-132">F# 코드 조각 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="e83f3-132">F# Snippets Website</span></span>](http://www.fssnip.net)
* [<span data-ttu-id="e83f3-133">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="e83f3-133">F# Software Foundation</span></span>](http://fsharp.org)
