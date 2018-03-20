---
title: "F# 가이드"
description: "이 가이드에서는 F #,.NET에서 실행 되는 함수형 프로그래밍 언어에 대 한 다양 한 교육 자료에 대 한 개요를 제공 합니다."
author: jackfoxy
ms.author: phcart
ms.date: 03/19/2018
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ea27fb37-dad1-4bd4-a3cc-4f5c70767ae9
ms.openlocfilehash: 8be5ac5090e10ae9270e7eec529bd9b7c3c663fb
ms.sourcegitcommit: 32172ca05d5dcce7ef3d327b9c8639c736e0fe2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2018
---
# <a name="f-guide"></a><span data-ttu-id="241d9-103">F# 가이드</span><span class="sxs-lookup"><span data-stu-id="241d9-103">F# Guide</span></span>

<span data-ttu-id="241d9-104">F #은.NET에서 실행 되는 함수형 프로그래밍 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-104">F# is a functional programming language that runs on .NET.</span></span> <span data-ttu-id="241d9-105">또한 blend 기능 및 개체 프로그래밍 문제에 대 한 실용적인 솔루션에 대 한 사용자에 게 알려주는 개체에 대 한 완전 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-105">It also has full support for objects, letting you blend functional and object programming for pragmatic solutions to any problem.</span></span>

```fsharp
open System // Get access to functionality in System namespace.

// Function: takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

// Use the EntryPoint attribute to run the program.
[<EntryPoint>]
let main args =
    // Define a list of names
    let names = [| "Don"; "Julia"; "Xi" |]
    
    // Print a fun greeting for each name!
    names
    |> Array.map getGreeting
    |> Array.iter (fun greeting -> printfn "%s" greeting)

    0
```

<span data-ttu-id="241d9-106">F #은 본래 생산성에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-106">F# is about productivity at its heart.</span></span> <span data-ttu-id="241d9-107">F #에 대 한 도구 지원을 유비쿼터스 이며 다양 한 고급 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-107">The tooling support for F# is ubiquitous and full of advanced features.</span></span>

## <a name="learning-f"></a><span data-ttu-id="241d9-108">F # 학습</span><span class="sxs-lookup"><span data-stu-id="241d9-108">Learning F#</span></span> #

<span data-ttu-id="241d9-109">[F # 둘러보기](tour.md) 코드 샘플은 주요 언어 기능의 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-109">[Tour of F#](tour.md) gives an overview of major language features with lots of code samples.</span></span> <span data-ttu-id="241d9-110">F #에 새로 고 언어의 작동 방식에 대해 하려고 할 경우에 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-110">This is recommended if you are new to F# and want to get a feel for how the language works.</span></span>

<span data-ttu-id="241d9-111">[Visual Studio에서 F #으로 시작 하려면](get-started/get-started-visual-studio.md) Windows에 속해 있으며 사용할 것 전체 Visual Studio IDE (Integraded 개발 환경) 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="241d9-111">[Get started with F# in Visual Studio](get-started/get-started-visual-studio.md) if you're on Windows and want the full Visual Studio IDE (Integraded Development Environment) experience.</span></span>

<span data-ttu-id="241d9-112">[Mac 용 Visual Studio에서 F #으로 시작](get-started/get-started-with-visual-studio-for-mac.md) macOS에 속해 있으며 Visual Studio IDE를 사용 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="241d9-112">[Get started with F# in Visual Studio for Mac](get-started/get-started-with-visual-studio-for-mac.md) if you're on macOS and want to use a Visual Studio IDE.</span></span>

<span data-ttu-id="241d9-113">[Visual Studio Code에서 F #으로 시작 하려면](get-started/get-started-vscode.md) 경우 플랫폼 간 경량 및 IDE 기능이 포함 된 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-113">[Get Started with F# in Visual Studio Code](get-started/get-started-vscode.md) if you want a lightweight, cross-platform, and feature-packed IDE experience.</span></span>

<span data-ttu-id="241d9-114">[F #으로.NET Core CLI 시작](get-started/get-started-command-line.md) 명령줄 도구를 사용 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="241d9-114">[Get started with F# with the .NET Core CLI](get-started/get-started-command-line.md) if you want to use command-line tools.</span></span>

## <a name="references"></a><span data-ttu-id="241d9-115">참조</span><span class="sxs-lookup"><span data-stu-id="241d9-115">References</span></span>

<span data-ttu-id="241d9-116">[F # 언어 참조](language-reference/index.md) 은 F # 언어의 모든 기능에 대 한 공식 하 고 포괄적인 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-116">[F# Language Reference](language-reference/index.md) is the official, comprehensive reference for all F# language features.</span></span> <span data-ttu-id="241d9-117">각 문서는 구문에 설명 하 고 코드 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-117">Each article explains the syntax and shows code samples.</span></span> <span data-ttu-id="241d9-118">특정 문서를 찾습니다는 목차에서 필터 표시줄을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-118">You can use the filter bar in the table of contents to find specific articles.</span></span>

<span data-ttu-id="241d9-119">[F # 핵심 라이브러리 참조가](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) F # 핵심 라이브러리에 대 한 API 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-119">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) is the API reference for the F# Core Library.</span></span>

## <a name="additional-guides"></a><span data-ttu-id="241d9-120">추가 가이드</span><span class="sxs-lookup"><span data-stu-id="241d9-120">Additional guides</span></span>

<span data-ttu-id="241d9-121">[F # 재미와 수익에 대 한](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) 는 종합적이 고 매우 자세한 र ् थ 학습 F #은 합니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-121">[F# for Fun and Profit](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) is a comprehensive and very detailed book on learning F#.</span></span> <span data-ttu-id="241d9-122">내용과 작성자는 F # 커뮤니티에서 사랑 합니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-122">Its contents and author are beloved by the F# community.</span></span> <span data-ttu-id="241d9-123">대상 사용자는 주로 개발자에 게 개체 지향 프로그래밍 배경.</span><span class="sxs-lookup"><span data-stu-id="241d9-123">The target audience is primarily developers with an object oriented programming background.</span></span>

<span data-ttu-id="241d9-124">[F # 프로그래밍 Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) 학습 F #에 대 한 wikibook 됩니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-124">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) is a wikibook about learning F#.</span></span> <span data-ttu-id="241d9-125">F # 커뮤니티의 제품 이기도합니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-125">It is also a product of the F# community.</span></span> <span data-ttu-id="241d9-126">대상 그룹은 F #을 사용 하면 약간의 개체 지향 프로그래밍 배경을 처음 접하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-126">The target audience is people who are new to F#, with a little bit of object oriented programming background.</span></span>

## <a name="learn-f-through-videos"></a><span data-ttu-id="241d9-127">F # 비디오를 통한 학습</span><span class="sxs-lookup"><span data-stu-id="241d9-127">Learn F# through videos</span></span>

<span data-ttu-id="241d9-128">[YouTube에서 F # 자습서](https://www.youtube.com/watch?v=c7eNDJN758U) F # Visual Studio를 사용 하 여, 1.5 시간의 과정 동안 다양 한 좋은 예를 보여 주는에 충분히 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-128">[F# tutorial on YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) is a great introduction to F# using Visual Studio, showing lots of great examples over the course of 1.5 hours.</span></span> <span data-ttu-id="241d9-129">대상 그룹에는 F #를 처음 접하는 Visual Studio 개발자입니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-129">The target audience is Visual Studio developers who are new to F#.</span></span>

<span data-ttu-id="241d9-130">[F #을 사용한 프로그래밍 소개](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) 훌륭한 비디오 일련의 기본 편집기로 Visual Studio 코드를 사용 하 여입니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-130">[Introduction to Programming with F#](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) is a great video series that uses Visual Studio Code as the main editor.</span></span> <span data-ttu-id="241d9-131">비디오 시리즈를 시작한 RPG 비디오 텍스트 기반 게임을 빌드하는 것과 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-131">The video series starts from nothing and ends with building a text-based RPG video game.</span></span> <span data-ttu-id="241d9-132">대상 사용자는 개발자 처음인 F # 및 Visual Studio Code (또는 간단한 IDE) 선호입니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-132">The target audience is developers who prefer Visual Studio Code (or a lightweight IDE) and are new to F#.</span></span>

<span data-ttu-id="241d9-133">[F #에 대 한 개발자를 위한 Visual Studio 2017의 새로운](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) 은 Visual Studio 2017에서 F #에 대 한 새로운 기능 중 일부를 보여 주는 비디오 과정입니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-133">[What's New in Visual Studio 2017 for F# For Developers](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) is a video course that shows some of the newer features for F# in Visual Studio 2017.</span></span> <span data-ttu-id="241d9-134">대상 그룹에는 F #를 처음 접하는 Visual Studio 개발자입니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-134">The target audience is Visual Studio developers who are new to F#.</span></span>

## <a name="other-useful-resources"></a><span data-ttu-id="241d9-135">기타 유용한 리소스</span><span class="sxs-lookup"><span data-stu-id="241d9-135">Other useful resources</span></span>

<span data-ttu-id="241d9-136">[F # 코드 조각 웹 사이트](http://www.fssnip.net) massive 완전 초보자를 위한에서 고급 코드 조각에 이르기까지 F #에서 모든 작업 하는 방법을 보여 주는 코드 조각 집합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-136">The [F# Snippets Website](http://www.fssnip.net) contains a massive set of code snippets showing how to do just about anything in F#, ranging from absolute beginner to highly advanced snippets.</span></span>

<span data-ttu-id="241d9-137">[F # 소프트웨어 Foundation Slack](http://fsharp.org/guides/slack/) 좋은 곳은 초보자를 위한 및 전문가 게 모두 매우 활성화가 있으며 프로그래머 세계에서 가장 F # 채팅에 사용할 수 있는의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-137">The [F# Software Foundation Slack](http://fsharp.org/guides/slack/) is a great place for beginners and experts alike, is highly active, and has some of world's best F# programmers available for a chat.</span></span> <span data-ttu-id="241d9-138">조인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-138">We highly recommend joining.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="241d9-139">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="241d9-139">The F# Software Foundation</span></span>

<span data-ttu-id="241d9-140">Microsoft 기본 개발자의 F # 언어와 Visual Studio에서 해당 도구 이지만, F #는 또한 뒷받침 되며는 독립적인 foundation는 F # 소프트웨어 Foundation (FSSF).</span><span class="sxs-lookup"><span data-stu-id="241d9-140">Although Microsoft is the primary developer of the F# language and its tools in Visual Studio, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="241d9-141">F# Software Foundation의 임무는 F# 프로그래밍 언어를 홍보하고 보호하고 발전시키며, F# 프로그래머의 다양한 국제 커뮤니티의 성장을 지원하고 용이하게 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="241d9-141">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="241d9-142">자세한 내용을 알아보고 참여하려면 [fsharp.org](http://fsharp.org)를 참조하세요. 조인, 무료 및 foundation의 F # 개발자의 네트워크를 포기 하 고치지 않을!</span><span class="sxs-lookup"><span data-stu-id="241d9-142">To learn more and get involved, check out [fsharp.org](http://fsharp.org). It's free to join, and the network of F# developers in the foundation is something you don't want to miss out on!</span></span>
