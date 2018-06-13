---
title: F# 가이드
description: 이 가이드에서는 F#, .NET에서 실행되는 함수형 프로그래밍 언어에 대한 다양한 교육 자료에 대한 개요를 제공합니다.
author: jackfoxy
ms.date: 03/19/2018
ms.openlocfilehash: cb829e904c006467e1470752b4fe8757ca694b05
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2018
ms.locfileid: "34312003"
---
# <a name="f-guide"></a><span data-ttu-id="6cbc7-103">F# 가이드</span><span class="sxs-lookup"><span data-stu-id="6cbc7-103">F# Guide</span></span>

<span data-ttu-id="6cbc7-104">F#은 .NET에서 실행되는 함수형 프로그래밍 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-104">F# is a functional programming language that runs on .NET.</span></span> <span data-ttu-id="6cbc7-105">또한 객체에 대한 완벽한 지원을 제공하므로, 실용적인 솔루션을 위해 함수형 및 객체지향 프로그래밍을 혼합하여 모든 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-105">It also has full support for objects, letting you blend functional and object programming for pragmatic solutions to any problem.</span></span>

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

<span data-ttu-id="6cbc7-106">F#의 핵심은 생산성입니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-106">F# is about productivity at its heart.</span></span> <span data-ttu-id="6cbc7-107">툴링 지원은 어디에서나 볼 수 있고 고급 기능으로 가득합니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-107">The tooling support for F# is ubiquitous and full of advanced features.</span></span>

## <a name="learning-f"></a><span data-ttu-id="6cbc7-108">F # 학습</span><span class="sxs-lookup"><span data-stu-id="6cbc7-108">Learning F#</span></span> #

<span data-ttu-id="6cbc7-109">[F# 둘러보기](tour.md)는 많은 코드 샘플과 함께 언어의 주요 기능에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-109">[Tour of F#](tour.md) gives an overview of major language features with lots of code samples.</span></span> <span data-ttu-id="6cbc7-110">F#을 처음 배우는 사람이거나 언어가 어떻게 작동하는지 알아보고 싶은 경우에 해당 문서를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-110">This is recommended if you are new to F# and want to get a feel for how the language works.</span></span>

<span data-ttu-id="6cbc7-111">[Visual Studio에서 F #으로 시작](get-started/get-started-visual-studio.md) Windows 환경에서 Visual Studio IDE(Integraded Development Environment) 사용을 원한다면 해당 문서를 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-111">[Get started with F# in Visual Studio](get-started/get-started-visual-studio.md) if you're on Windows and want the full Visual Studio IDE (Integraded Development Environment) experience.</span></span>

<span data-ttu-id="6cbc7-112">[Mac용 Visual Studio에서 F#으로 시작](get-started/get-started-with-visual-studio-for-mac.md) macOS 환경에서 Visual Studio IDE 사용을 원한다면 해당 문서를 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-112">[Get started with F# in Visual Studio for Mac](get-started/get-started-with-visual-studio-for-mac.md) if you're on macOS and want to use a Visual Studio IDE.</span></span>

<span data-ttu-id="6cbc7-113">[Visual Studio Code에서 F #으로 시작 하려면](get-started/get-started-vscode.md) 경우 플랫폼 간 경량 및 IDE 기능이 포함 된 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-113">[Get Started with F# in Visual Studio Code](get-started/get-started-vscode.md) if you want a lightweight, cross-platform, and feature-packed IDE experience.</span></span>

<span data-ttu-id="6cbc7-114">[F#으로 .NET Core CLI 시작](get-started/get-started-command-line.md) 커맨드 라인 도구 사용을 원한다면 해당 문서를 참고하십시오.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-114">[Get started with F# with the .NET Core CLI](get-started/get-started-command-line.md) if you want to use command-line tools.</span></span>

<span data-ttu-id="6cbc7-115">[F# 및 Xamarin 시작](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) F#을 이용한 모바일 프로그래밍에 대한 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-115">[Get started with F# and Xamarin](https://docs.microsoft.com/xamarin/cross-platform/platform/fsharp/) for mobile programming with F#.</span></span>

<span data-ttu-id="6cbc7-116">[F # Azure 노트북용](https://notebooks.azure.com/Microsoft/libraries/samples/html/FSharp%20for%20Azure%20Notebooks.ipynb) 학습 무료, 호스팅된 Jupyter 노트북에서 F #에 대 한 자습서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-116">[F# for Azure Notebooks](https://notebooks.azure.com/Microsoft/libraries/samples/html/FSharp%20for%20Azure%20Notebooks.ipynb) is a tutorial for learning F# in a free, hosted Jupyter Notebook.</span></span>

## <a name="references"></a><span data-ttu-id="6cbc7-117">참조</span><span class="sxs-lookup"><span data-stu-id="6cbc7-117">References</span></span>

<span data-ttu-id="6cbc7-118">[F # 언어 참조](language-reference/index.md) 은 F # 언어의 모든 기능에 대 한 공식 하 고 포괄적인 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-118">[F# Language Reference](language-reference/index.md) is the official, comprehensive reference for all F# language features.</span></span> <span data-ttu-id="6cbc7-119">각 문서는 구문에 설명 하 고 코드 샘플을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-119">Each article explains the syntax and shows code samples.</span></span> <span data-ttu-id="6cbc7-120">특정 문서를 찾습니다는 목차에서 필터 표시줄을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-120">You can use the filter bar in the table of contents to find specific articles.</span></span>

<span data-ttu-id="6cbc7-121">[F # 핵심 라이브러리 참조가](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) F # 핵심 라이브러리에 대 한 API 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-121">[F# Core Library Reference](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-core-library-reference) is the API reference for the F# Core Library.</span></span>


## <a name="additional-guides"></a><span data-ttu-id="6cbc7-122">추가 가이드</span><span class="sxs-lookup"><span data-stu-id="6cbc7-122">Additional guides</span></span>

<span data-ttu-id="6cbc7-123">[F # 재미와 수익에 대 한](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) 는 종합적이 고 매우 자세한 र ् थ 학습 F #은 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-123">[F# for Fun and Profit](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/) is a comprehensive and very detailed book on learning F#.</span></span> <span data-ttu-id="6cbc7-124">내용과 작성자는 F # 커뮤니티에서 사랑 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-124">Its contents and author are beloved by the F# community.</span></span> <span data-ttu-id="6cbc7-125">대상 사용자는 주로 개발자에 게 개체 지향 프로그래밍 배경.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-125">The target audience is primarily developers with an object oriented programming background.</span></span>

<span data-ttu-id="6cbc7-126">[F # 프로그래밍 Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) 학습 F #에 대 한 wikibook 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-126">[F# Programming Wikibook](https://en.wikibooks.org/wiki/F_Sharp_Programming) is a wikibook about learning F#.</span></span> <span data-ttu-id="6cbc7-127">F # 커뮤니티의 제품 이기도합니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-127">It is also a product of the F# community.</span></span> <span data-ttu-id="6cbc7-128">대상 그룹은 F #을 사용 하면 약간의 개체 지향 프로그래밍 배경을 처음 접하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-128">The target audience is people who are new to F#, with a little bit of object oriented programming background.</span></span>

## <a name="learn-f-through-videos"></a><span data-ttu-id="6cbc7-129">F # 비디오를 통한 학습</span><span class="sxs-lookup"><span data-stu-id="6cbc7-129">Learn F# through videos</span></span>

<span data-ttu-id="6cbc7-130">[YouTube에서 F # 자습서](https://www.youtube.com/watch?v=c7eNDJN758U) F # Visual Studio를 사용 하 여, 1.5 시간의 과정 동안 다양 한 좋은 예를 보여 주는에 충분히 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-130">[F# tutorial on YouTube](https://www.youtube.com/watch?v=c7eNDJN758U) is a great introduction to F# using Visual Studio, showing lots of great examples over the course of 1.5 hours.</span></span> <span data-ttu-id="6cbc7-131">대상 그룹에는 F #를 처음 접하는 Visual Studio 개발자입니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-131">The target audience is Visual Studio developers who are new to F#.</span></span>

<span data-ttu-id="6cbc7-132">[F #을 사용한 프로그래밍 소개](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) 훌륭한 비디오 일련의 기본 편집기로 Visual Studio 코드를 사용 하 여입니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-132">[Introduction to Programming with F#](https://www.youtube.com/watch?v=Teak30_pXHk&list=PLEoMzSkcN8oNiJ67Hd7oRGgD1d4YBxYGC) is a great video series that uses Visual Studio Code as the main editor.</span></span> <span data-ttu-id="6cbc7-133">비디오 시리즈를 시작한 RPG 비디오 텍스트 기반 게임을 빌드하는 것과 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-133">The video series starts from nothing and ends with building a text-based RPG video game.</span></span> <span data-ttu-id="6cbc7-134">대상 사용자는 개발자 처음인 F # 및 Visual Studio Code (또는 간단한 IDE) 선호입니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-134">The target audience is developers who prefer Visual Studio Code (or a lightweight IDE) and are new to F#.</span></span>

<span data-ttu-id="6cbc7-135">[F #에 대 한 개발자를 위한 Visual Studio 2017의 새로운](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) 은 Visual Studio 2017에서 F #에 대 한 새로운 기능 중 일부를 보여 주는 비디오 과정입니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-135">[What's New in Visual Studio 2017 for F# For Developers](https://www.linkedin.com/learning/what-s-new-in-visual-studio-2017-for-f-sharp-for-developers) is a video course that shows some of the newer features for F# in Visual Studio 2017.</span></span> <span data-ttu-id="6cbc7-136">대상 그룹에는 F #를 처음 접하는 Visual Studio 개발자입니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-136">The target audience is Visual Studio developers who are new to F#.</span></span>

## <a name="other-useful-resources"></a><span data-ttu-id="6cbc7-137">기타 유용한 리소스</span><span class="sxs-lookup"><span data-stu-id="6cbc7-137">Other useful resources</span></span>

<span data-ttu-id="6cbc7-138">[F # 코드 조각 웹 사이트](http://www.fssnip.net) massive 완전 초보자를 위한에서 고급 코드 조각에 이르기까지 F #에서 모든 작업 하는 방법을 보여 주는 코드 조각 집합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-138">The [F# Snippets Website](http://www.fssnip.net) contains a massive set of code snippets showing how to do just about anything in F#, ranging from absolute beginner to highly advanced snippets.</span></span>

<span data-ttu-id="6cbc7-139">[F # 소프트웨어 Foundation Slack](http://fsharp.org/guides/slack/) 좋은 곳은 초보자를 위한 및 전문가 게 모두 매우 활성화가 있으며 프로그래머 세계에서 가장 F # 채팅에 사용할 수 있는의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-139">The [F# Software Foundation Slack](http://fsharp.org/guides/slack/) is a great place for beginners and experts alike, is highly active, and has some of world's best F# programmers available for a chat.</span></span> <span data-ttu-id="6cbc7-140">조인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-140">We highly recommend joining.</span></span>

## <a name="the-f-software-foundation"></a><span data-ttu-id="6cbc7-141">F# Software Foundation</span><span class="sxs-lookup"><span data-stu-id="6cbc7-141">The F# Software Foundation</span></span>

<span data-ttu-id="6cbc7-142">Microsoft 기본 개발자의 F # 언어와 Visual Studio에서 해당 도구 이지만, F #는 또한 뒷받침 되며는 독립적인 foundation는 F # 소프트웨어 Foundation (FSSF).</span><span class="sxs-lookup"><span data-stu-id="6cbc7-142">Although Microsoft is the primary developer of the F# language and its tools in Visual Studio, F# is also backed by an independent foundation, the F# Software Foundation (FSSF).</span></span>

<span data-ttu-id="6cbc7-143">F# Software Foundation의 임무는 F# 프로그래밍 언어를 홍보하고 보호하고 발전시키며, F# 프로그래머의 다양한 국제 커뮤니티의 성장을 지원하고 용이하게 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6cbc7-143">The mission of the F# Software Foundation is to promote, protect, and advance the F# programming language, and to support and facilitate the growth of a diverse and international community of F# programmers.</span></span>

<span data-ttu-id="6cbc7-144">자세한 내용을 알아보고 참여하려면 [fsharp.org](http://fsharp.org)를 참조하세요. 조인, 무료 및 foundation의 F # 개발자의 네트워크를 포기 하 고치지 않을!</span><span class="sxs-lookup"><span data-stu-id="6cbc7-144">To learn more and get involved, check out [fsharp.org](http://fsharp.org). It's free to join, and the network of F# developers in the foundation is something you don't want to miss out on!</span></span>
