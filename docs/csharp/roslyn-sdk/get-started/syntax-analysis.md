---
title: 구문 분석 시작(Roslyn API)
description: 구문 트리를 트래버스하고, 탐색하고, 쿼리하는 방법을 소개합니다.
author: billwagner
ms.author: wiwagn
ms.date: 02/05/2018
ms.topic: conceptual
ms.prod: .net
ms.technology: devlang-csharp
ms.custom: mvc
ms.openlocfilehash: 90d6542122dd8c579c63f5f003441ce63a7ca5e9
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2018
---
# <a name="get-started-with-syntax-analysis"></a><span data-ttu-id="5308b-103">구문 분석 시작</span><span class="sxs-lookup"><span data-stu-id="5308b-103">Get started with syntax analysis</span></span>

<span data-ttu-id="5308b-104">이 자습서에서는 **구문 API**를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-104">In this tutorial, you'll explore the **Syntax API**.</span></span> <span data-ttu-id="5308b-105">구문 API는 C# 또는 Visual Basic 프로그램을 설명하는 데이터 구조에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-105">The Syntax API provides access to the data structures that describe a C# or Visual Basic program.</span></span> <span data-ttu-id="5308b-106">이러한 데이터 구조에는 모든 규모의 프로그램을 완벽하게 나타낼 수 있는 충분한 세부 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-106">These data structures have enough detail that they can fully represent any program of any size.</span></span> <span data-ttu-id="5308b-107">이러한 구조는 컴파일하고 올바르게 실행하는 전체 프로그램을 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-107">These structures can describe complete programs that compile and run correctly.</span></span> <span data-ttu-id="5308b-108">또한 편집기에서 작성한 대로 불완전한 프로그램을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-108">They can also describe incomplete programs, as you write them, in the editor.</span></span>

<span data-ttu-id="5308b-109">다양한 식을 사용하도록 설정하려면 구문 API를 구성하는 데이터 구조 및 API는 복잡해질 수 밖에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-109">To enable this rich expression, the data structures and APIs that make up the Syntax API are necessarily complex.</span></span> <span data-ttu-id="5308b-110">일반적인 "Hello World" 프로그램에 있는 데이터 구조의 모양부터 시작하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-110">Let's start with what the data structure looks like for the typical "Hello World" program:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="5308b-111">이전 프로그램의 텍스트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-111">Look at the text of the previous program.</span></span> <span data-ttu-id="5308b-112">친숙한 요소를 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-112">You recognize familiar elements.</span></span> <span data-ttu-id="5308b-113">전체 텍스트는 단일 원본 파일 또는 **컴파일 단위**를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-113">The entire text represents a single source file, or a **compilation unit**.</span></span> <span data-ttu-id="5308b-114">해당 원본 파일의 처음 세 줄은 **using 지시문**입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-114">The first three lines of that source file are **using directives**.</span></span> <span data-ttu-id="5308b-115">나머지 원본은 **네임스페이스 선언**에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-115">The remaining source is contained in a **namespace declaration**.</span></span> <span data-ttu-id="5308b-116">네임스페이스 선언에는 자식 **클래스 선언**이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-116">The namespace declaration contains a child **class declaration**.</span></span> <span data-ttu-id="5308b-117">클래스 선언에는 하나의 **메서드 선언**이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-117">The class declaration contains one **method declaration**.</span></span>

<span data-ttu-id="5308b-118">구문 API는 컴파일 단위를 나타내는 루트를 사용하여 트리 구조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-118">The Syntax API creates a tree structure with the root representing the compilation unit.</span></span> <span data-ttu-id="5308b-119">트리의 노드는 using 지시문, 네임스페이스 선언 및 프로그램의 다른 모든 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-119">Nodes in the tree represent the using directives, namespace declaration and all the other elements of the program.</span></span> <span data-ttu-id="5308b-120">트리 구조는 가장 낮은 수준인 문자열 "Hello World!"까지 계속되고</span><span class="sxs-lookup"><span data-stu-id="5308b-120">The tree structure continues down to the lowest levels: the string "Hello World!"</span></span> <span data-ttu-id="5308b-121">**인수**의 하위 항목인 **문자열 리터럴 토큰**입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-121">is a **string literal token** that is a descendent of an **argument**.</span></span> <span data-ttu-id="5308b-122">구문 API는 프로그램의 구조에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-122">The Syntax API provides access to the structure of the program.</span></span> <span data-ttu-id="5308b-123">특정 코드 사례에 대해 쿼리하고, 전체 트리를 통해 코드를 이해하고, 기존 트리를 수정하여 새 트리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-123">You can query for specific code practices, walk the entire tree to understand the code, and create new trees by modifying the existing tree.</span></span>

<span data-ttu-id="5308b-124">간략한 설명을 통해 구문 API를 사용하여 액세스할 수 있는 정보의 종류에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-124">That brief description provides an overview of the kind of information accessible using the Syntax API.</span></span> <span data-ttu-id="5308b-125">구문 API는 C#에서 알아낸 친숙한 코드 구문을 설명하는 공식 API입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-125">The Syntax API is nothing more than a formal API that describes the familiar code constructs you know from C#.</span></span> <span data-ttu-id="5308b-126">줄 바꿈, 공백 및 들여쓰기를 비롯하여 코드의 형식을 지정하는 방법에 대한 정보가 포함된 완전한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-126">The full capabilities include information about how the code is formatted including line breaks, whitespace, and indenting.</span></span> <span data-ttu-id="5308b-127">이 정보를 사용하여 코드를 작성한 대로 완벽하게 나타내고 휴먼 프로그래머 또는 컴파일러가 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-127">Using this information, you can fully represent the code as written and read by human programmers or the compiler.</span></span> <span data-ttu-id="5308b-128">이 구조를 사용하면 의미 있는 수준에서 소스 코드와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-128">Using this structure enables you to interact with the source code on a deeply meaningful level.</span></span> <span data-ttu-id="5308b-129">더 이상 텍스트 문자열이 아니지만 C# 프로그램의 구조를 나타내는 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-129">It's no longer text strings, but data that represents the structure of a C# program.</span></span>

<span data-ttu-id="5308b-130">시작하려면 **.NET Compiler Platform SDK**를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-130">To get started, you'll need to install the **.NET Compiler Platform SDK**:</span></span>

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

## <a name="understanding-syntax-trees"></a><span data-ttu-id="5308b-131">구문 트리 이해</span><span class="sxs-lookup"><span data-stu-id="5308b-131">Understanding syntax trees</span></span>

<span data-ttu-id="5308b-132">C# 코드 구조의 분석에 구문 API를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-132">You use the Syntax API for any analysis of the structure of C# code.</span></span> <span data-ttu-id="5308b-133">**구문 API**는 구문 트리를 분석하고 생성하기 위한 파서, 구문 트리 및 유틸리티를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-133">The **Syntax API** exposes the parsers, the syntax trees, and utilities for analyzing and constructing syntax trees.</span></span> <span data-ttu-id="5308b-134">그렇게 특정 구문 요소에 대한 코드를 검색하거나 프로그램에 대한 코드를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-134">It's how you search code for specific syntax elements or read the code for a program.</span></span>

<span data-ttu-id="5308b-135">구문 트리는 C# 및 Visual Basic 프로그램을 이해하기 위해 C# 및 Visual Basic 컴파일러에서 사용하는 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-135">A syntax tree is a data structure used by the C# and Visual Basic compilers to understand C# and Visual Basic programs.</span></span> <span data-ttu-id="5308b-136">구문 트리는 프로젝트가 빌드되거나 개발자가 F5 키를 누를 때 실행되는 동일한 파서에서 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-136">Syntax trees are produced by the same parser that runs when a project is built or a developer hits F5.</span></span> <span data-ttu-id="5308b-137">구문 트리는 언어를 완전히 제공합니다. 코드 파일의 모든 정보가 트리에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-137">The syntax trees have full-fidelity with the language; every bit of information in a code file is represented in the tree.</span></span> <span data-ttu-id="5308b-138">텍스트에 대한 구문 트리를 작성하면 구문 분석된 정확한 원본 텍스트를 재현합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-138">Writing a syntax tree to text reproduces the exact original text that was parsed.</span></span> <span data-ttu-id="5308b-139">또한 구문 트리는 **변경할 수 없습니다**. 만들어진 구문 트리는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-139">The syntax trees are also **immutable**; once created a syntax tree can never be changed.</span></span> <span data-ttu-id="5308b-140">트리의 소비자는 잠금 또는 기타 동시성 조치 없이 여러 스레드에서 트리를 분석할 수 있으며 데이터가 바뀌지 않는다는 점을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-140">Consumers of the trees can analyze the trees on multiple threads, without locks or other concurrency measures, knowing the data never changes.</span></span> <span data-ttu-id="5308b-141">API를 사용하여 기존 트리를 수정한 결과로 나타난 새 트리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-141">You can use APIs to create new trees that are the result of modifying an existing tree.</span></span>

<span data-ttu-id="5308b-142">구문 트리의 네 가지 기본 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-142">The four primary building blocks of syntax trees are:</span></span>

* <span data-ttu-id="5308b-143"><xref:Microsoft.CodeAnalysis.SyntaxTree?displayProperty=nameWithType> 클래스는 전체 구문 분석 트리를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-143">The <xref:Microsoft.CodeAnalysis.SyntaxTree?displayProperty=nameWithType> class, an instance of which represents an entire parse tree.</span></span> <span data-ttu-id="5308b-144"><xref:Microsoft.CodeAnalysis.SyntaxTree>은 언어별 파생물을 포함하는 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-144"><xref:Microsoft.CodeAnalysis.SyntaxTree> is an abstract class that has language-specific derivatives.</span></span> <span data-ttu-id="5308b-145"><xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxTree?displayProperty=nameWithType>(또는 <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicSyntaxTree?displayProperty=nameWithType>) 클래스의 구문 분석 메서드를 사용하여 C# 또는 VB 텍스트를 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-145">You use the parse methods of the <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxTree?displayProperty=nameWithType> (or <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicSyntaxTree?displayProperty=nameWithType>) class to parse text in C# or VB.</span></span>
* <span data-ttu-id="5308b-146"><xref:Microsoft.CodeAnalysis.SyntaxNode?displayProperty=nameWithType> 클래스는 선언, 명령문, 절 및 식과 같은 구문 구조를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-146">The <xref:Microsoft.CodeAnalysis.SyntaxNode?displayProperty=nameWithType> class, instances of which represent syntactic constructs such as declarations, statements, clauses, and expressions.</span></span>
* <span data-ttu-id="5308b-147"><xref:Microsoft.CodeAnalysis.SyntaxToken?displayProperty=nameWithType> 구조는 개별 키워드, 식별자, 연산자 또는 문장 부호를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-147">The <xref:Microsoft.CodeAnalysis.SyntaxToken?displayProperty=nameWithType> structure, which represents an individual keyword, identifier, operator, or punctuation.</span></span>
* <span data-ttu-id="5308b-148">마지막으로 <xref:Microsoft.CodeAnalysis.SyntaxTrivia?displayProperty=nameWithType> 구조는 토큰 간의 공백, 전처리 지시문 및 주석 등의 구문상으로 중요하지 않은 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-148">And lastly the <xref:Microsoft.CodeAnalysis.SyntaxTrivia?displayProperty=nameWithType> structure, which represents syntactically insignificant bits of information such as the whitespace between tokens, preprocessing directives, and comments.</span></span>

<span data-ttu-id="5308b-149">퀴즈, 토큰 및 노드는 Visual Basic 또는 C# 코드의 일부에 있는 모든 항목을 완전치 나타내는 트리를 형성하기 위해 계층적으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-149">Trivia, tokens, and nodes are composed hierarchically to form a tree that completely represents everything in a fragment of Visual Basic or C# code.</span></span> <span data-ttu-id="5308b-150">**구문 시각화 도우미** 창을 사용하여 이 구조를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-150">You can see this structure using the **Syntax Visualizer** window.</span></span> <span data-ttu-id="5308b-151">Visual Studio에서 **보기** > **다른 창** > **구문 시각화 도우미**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-151">In Visual Studio, choose **View** > **Other Windows** > **Syntax Visualizer**.</span></span> <span data-ttu-id="5308b-152">예를 들어 **구문 시각화 도우미**를 사용하여 검사된 위의 C# 원본 파일은 다음 그림처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-152">For example, the preceding C# source file examined using the **Syntax Visualizer** looks like the following figure:</span></span>

<span data-ttu-id="5308b-153">**SyntaxNode**: 파랑 | **SyntaxToken**: 초록색 | **SyntaxTrivia**: 빨강 ![C# 코드 파일](media/walkthrough-csharp-syntax-figure1.png)</span><span class="sxs-lookup"><span data-stu-id="5308b-153">**SyntaxNode**: Blue | **SyntaxToken**: Green | **SyntaxTrivia**: Red ![C# Code File](media/walkthrough-csharp-syntax-figure1.png)</span></span>

<span data-ttu-id="5308b-154">이 트리 구조를 탐색하여 코드 파일에서 문, 식, 토큰 또는 공백을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-154">By navigating this tree structure, you can find any statement, expression, token, or bit of whitespace in a code file.</span></span>

<span data-ttu-id="5308b-155">구문 API를 사용하여 코드 파일에서 무언가 찾을 수 있지만 대부분의 시나리오에는 작은 코드 조각을 검사하거나 특정 문 또는 조각을 검색하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-155">While you can find anything in a code file using the Syntax APIs, most scenarios involve examining small snippets of code, or searching for particular statements or fragments.</span></span> <span data-ttu-id="5308b-156">이후의 두 가지 예제에서는 코드의 구조를 찾거나 단일 문을 검색하는 일반적인 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-156">The two examples that follow show typical uses to browse the structure of code, or search for single statements.</span></span>

## <a name="traversing-trees"></a><span data-ttu-id="5308b-157">트리 트래버스</span><span class="sxs-lookup"><span data-stu-id="5308b-157">Traversing trees</span></span>

<span data-ttu-id="5308b-158">두 가지 방법으로 구문 트리에서 노드를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-158">You can examine the nodes in a syntax tree in two ways.</span></span> <span data-ttu-id="5308b-159">트리를 트래버스하여 각 노드를 검사하거나 특정 요소 또는 노드에 대해 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-159">You can traverse the tree to examine each node, or you can query for specific elements or nodes.</span></span>

### <a name="manual-traversal"></a><span data-ttu-id="5308b-160">수동 트래버스</span><span class="sxs-lookup"><span data-stu-id="5308b-160">Manual traversal</span></span>

<span data-ttu-id="5308b-161">[GitHub 리포지토리](https://github.com/dotnet/docs/tree/master/samples/csharp/roslyn-sdk/SyntaxQuickStart)에서 이 샘플의 완성된 코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-161">You can see the finished code for this sample in [our GitHub repository](https://github.com/dotnet/docs/tree/master/samples/csharp/roslyn-sdk/SyntaxQuickStart).</span></span>

> [!NOTE]
> <span data-ttu-id="5308b-162">구문 트리 형식은 상속을 사용하여 프로그램의 여러 위치에서 유효한 다른 구문 요소를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-162">The Syntax Tree types use inheritance to describe the different syntax elements that are valid at different locations in the program.</span></span> <span data-ttu-id="5308b-163">종종 이러한 API를 사용하면 속성이나 컬렉션 멤버를 파생된 특정 형식에 캐스팅하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-163">Using these APIs often means casting properties or collection members to specific derived types.</span></span> <span data-ttu-id="5308b-164">다음 예제에서 할당 및 캐스팅은 명시적으로 형식화된 변수를 사용하는 별도의 문입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-164">In the following examples, the assignment and the casts are separate statements, using explicitly typed variables.</span></span> <span data-ttu-id="5308b-165">API의 반환 형식 및 반환되는 개체의 런타임 형식을 확인하기 위해 코드를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-165">You can read the code to see the return types of the API and the runtime type of the objects returned.</span></span> <span data-ttu-id="5308b-166">이 연습에서는 암시적으로 형식화된 변수를 사용하고 API 이름을 사용하여 검사된 개체의 형식을 설명하는 것이 더 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-166">In practice, it's more common to use implicitly typed variables and rely on API names to describe the type of objects being examined.</span></span>

<span data-ttu-id="5308b-167">새 C# **독립 실행형 코드 분석 도구** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-167">Create a new C# **Stand-Alone Code Analysis Tool** project:</span></span>

* <span data-ttu-id="5308b-168">Visual Studio에서 **파일** > **새로 만들기** > **프로젝트**를 선택하여 새 프로젝트 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-168">In Visual Studio, choose **File** > **New** > **Project** to display the New Project dialog.</span></span>
* <span data-ttu-id="5308b-169">**Visual C#** > **확장성** 아래에서 **독립 실행형 코드 분석 도구**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-169">Under **Visual C#** > **Extensibility**, choose **Stand-Alone Code Analysis Tool**.</span></span>
* <span data-ttu-id="5308b-170">프로젝트 이름을 "**SyntaxTreeManualTraversal**"이라고 지정하고 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-170">Name your project "**SyntaxTreeManualTraversal**" and click OK.</span></span>

<span data-ttu-id="5308b-171">앞에 표시된 기본 "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="5308b-171">You're going to analyze the basic "Hello World!"</span></span> <span data-ttu-id="5308b-172">프로그램을 분석하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-172">program shown earlier.</span></span>
<span data-ttu-id="5308b-173">Hello World 프로그램의 텍스트를 `Program` 클래스의 상수로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-173">Add the text for the Hello World program as a constant in your `Program` class:</span></span>

[!code-csharp[Declare the program text](../../../../samples/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#1 "Declare a constant string for the program text to analyze")]

<span data-ttu-id="5308b-174">다음으로 `programText` 상수에서 코드 텍스트의 **구문 트리**를 빌드하는 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-174">Next, add the following code to build the **syntax tree** for the code text in the `programText` constant.</span></span>  <span data-ttu-id="5308b-175">`Main` 메서드에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-175">Add the following line to your `Main` method:</span></span>

[!code-csharp[Create the tree](../../../../samples/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#2 "Create the syntax tree")]

<span data-ttu-id="5308b-176">해당 두 줄은 트리를 만들고 해당 트리의 루트 노드를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-176">Those two lines create the tree and retrieve the root node of that tree.</span></span> <span data-ttu-id="5308b-177">이제 트리에서 노드를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-177">You can now examine the nodes in the tree.</span></span> <span data-ttu-id="5308b-178">다음과 같은 줄을 `Main` 메서드에 추가하여 트리에서 루트 노드 속성 중 일부를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-178">Add these lines to your `Main` method to display some of the properties of the root node in the tree:</span></span>

[!code-csharp[Examine the root node](../../../../samples/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#3 "Examine the root node")]

<span data-ttu-id="5308b-179">응용 프로그램을 실행하여 코드가 이 트리에서 루트 노드에 대해 검색한 내용을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-179">Run the application to see what your code has discovered about the root node in this tree.</span></span>

<span data-ttu-id="5308b-180">일반적으로 코드에 대해 자세히 알아보려면 트리를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-180">Typically, you'd traverse the tree to learn about the code.</span></span> <span data-ttu-id="5308b-181">이 예제에서는 API를 탐색하기 위해 알아야 하는 코드를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-181">In this example, you're analyzing code you know to explore the APIs.</span></span> <span data-ttu-id="5308b-182">다음 코드를 추가하여 `root` 노드의 첫 번째 멤버를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-182">Add the following code to examine the first member of the `root` node:</span></span>

[!code-csharp[Find the first member](../../../../samples/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#4 "Find the first member")]

<span data-ttu-id="5308b-183">해당 멤버는 <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NamespaceDeclarationSyntax?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-183">That member is a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NamespaceDeclarationSyntax?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5308b-184">`namespace HelloWorld` 선언 범위에 있는 모든 항목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-184">It represents everything in the scope of the `namespace HelloWorld` declaration.</span></span> <span data-ttu-id="5308b-185">다음 코드를 추가하여 노드가 `HelloWorld` 네임스페이스 내에서 선언된 내용을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-185">Add the following code to examine what nodes are declared inside the `HelloWorld` namespace:</span></span>

[!code-csharp[Find the class declaration](../../../../samples/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#5 "Find the class declaration")]

<span data-ttu-id="5308b-186">배운 내용을 확인하기 위해 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-186">Run the program to see what you've learned.</span></span>

<span data-ttu-id="5308b-187">이제 선언이 <xref:Microsoft.CodeAnalysis.CSharp.Syntax.ClassDeclarationSyntax?displayProperty=nameWithType>임을 알았으므로 해당 형식의 새로운 변수를 선언하여 클래스 선언을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-187">Now that you know the declaration is a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.ClassDeclarationSyntax?displayProperty=nameWithType>, declare a new variable of that type to examine the class declaration.</span></span> <span data-ttu-id="5308b-188">이 클래스에는 `Main` 메서드라는 하나의 멤버만이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-188">This class only contains one member: the `Main` method.</span></span> <span data-ttu-id="5308b-189">다음 코드를 추가하여 `Main` 메서드를 찾고 <xref:Microsoft.CodeAnalysis.CSharp.Syntax.MethodDeclarationSyntax?displayProperty=nameWithType>로 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-189">Add the following code to find the `Main` method, and cast it to a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.MethodDeclarationSyntax?displayProperty=nameWithType>.</span></span>

[!code-csharp[Find the main declaration](../../../../samples/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#6 "Find the main declaration")]

<span data-ttu-id="5308b-190">메서드 선언 노드에는 메서드에 대한 모든 구문 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-190">The method declaration node contains all the syntactic information about the method.</span></span> <span data-ttu-id="5308b-191">`Main` 메서드의 반환 형식, 인수의 수와 형식 및 메서드의 본문 텍스트를 표시하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-191">Let's display the return type of the `Main` method, the number and types of the arguments, and the body text of the method.</span></span> <span data-ttu-id="5308b-192">다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-192">Add the following code:</span></span>

[!code-csharp[Examine the syntax of the main method](../../../../samples/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#7 "Display information about the main method")]

<span data-ttu-id="5308b-193">프로그램을 실행하여 이 프로그램에 대해 알게 된 모든 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-193">Run the program to see all the information you've discovered about this program:</span></span>

```text
The tree is a CompilationUnit node.
The tree has 1 elements in it.
The tree has 4 using statements. They are:
        System
        System.Collections
        System.Linq
        System.Text
The first member is a NamespaceDeclaration.
There are 1 members declared in this namespace.
The first member is a ClassDeclaration.
There are 1 members declared in the Program class.
The first member is a MethodDeclaration.
The return type of the Main method is void.
The method has 1 parameters.
The type of the args parameter is string[].
The body text of the Main method follows:
        {
            Console.WriteLine("Hello, World!");
        }
```

### <a name="query-methods"></a><span data-ttu-id="5308b-194">쿼리 메서드</span><span class="sxs-lookup"><span data-stu-id="5308b-194">Query methods</span></span>

<span data-ttu-id="5308b-195">트리를 트래버스하는 것 외에도 <xref:Microsoft.CodeAnalysis.SyntaxNode?displayProperty=nameWithType>에 정의된 쿼리 메서드를 사용하여 구문 트리를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-195">In addition to traversing trees, you can also explore the syntax tree using the query methods defined on <xref:Microsoft.CodeAnalysis.SyntaxNode?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5308b-196">이러한 메서드는 XPath에 익숙한 사용자라면 누구나 즉시 익숙해질 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-196">These methods should be immediately familiar to anyone familiar with XPath.</span></span> <span data-ttu-id="5308b-197">LINQ에서 이러한 메서드를 사용하여 트리에서 신속히 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-197">You can use these methods with LINQ to quickly find things in a tree.</span></span> <span data-ttu-id="5308b-198"><xref:Microsoft.CodeAnalysis.SyntaxNode>에는 <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantNodes%2A>, <xref:Microsoft.CodeAnalysis.SyntaxNode.AncestorsAndSelf%2A> 및 <xref:Microsoft.CodeAnalysis.SyntaxNode.ChildNodes%2A> 등의 쿼리 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-198">The <xref:Microsoft.CodeAnalysis.SyntaxNode> has query methods such as <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantNodes%2A>, <xref:Microsoft.CodeAnalysis.SyntaxNode.AncestorsAndSelf%2A> and <xref:Microsoft.CodeAnalysis.SyntaxNode.ChildNodes%2A>.</span></span>

<span data-ttu-id="5308b-199">이러한 쿼리 메서드를 사용하여 트리를 탐색하는 대신 `Main` 메서드에 대한 인수를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-199">You can use these query methods to find the argument to the `Main` method as an alternative to navigating the tree.</span></span> <span data-ttu-id="5308b-200">`Main` 메서드의 맨 아래에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-200">Add the following code to the bottom of your `Main` method:</span></span>

[!code-csharp[Query the tree for the arguments to Main](../../../../samples/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#8 "Query the tree for the arguments to Main")]

<span data-ttu-id="5308b-201">첫 번째 문은 LINQ 식 및 <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantNodes%2A> 메서드를 사용하여 앞의 예제와 동일한 매개 변수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-201">The first statement uses a LINQ expression and the <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantNodes%2A> method to locate the same parameter as in the previous example.</span></span>

<span data-ttu-id="5308b-202">프로그램을 실행하고, LINQ 식이 트리를 수동으로 탐색할 때와 동일한 매개 변수를 찾았는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-202">Run the program, and you can see that the LINQ expression found the same parameter as manually navigating the tree.</span></span>

<span data-ttu-id="5308b-203">이 샘플에서는 `WriteLine` 문을 사용하여 트래버스한 대로 구문 트리에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-203">The sample uses `WriteLine` statements to display information about the syntax trees as they are traversed.</span></span> <span data-ttu-id="5308b-204">디버거에서 완성된 프로그램을 실행하여 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-204">You can also learn much more by running the finished program under the debugger.</span></span> <span data-ttu-id="5308b-205">Hello World 프로그램에서 만든 구문 트리의 일부인 속성 및 메서드를 자세히 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-205">You can examine more of the properties and methods that are part of the syntax tree created for the hello world program.</span></span>

## <a name="syntax-walkers"></a><span data-ttu-id="5308b-206">구문 워커</span><span class="sxs-lookup"><span data-stu-id="5308b-206">Syntax walkers</span></span>

<span data-ttu-id="5308b-207">구문 트리에서 특정 종류의 모든 노드를 찾을 수도 있습니다(예: 파일의 모든 속성 선언).</span><span class="sxs-lookup"><span data-stu-id="5308b-207">Often you want to find all nodes of a specific type in a syntax tree, for example, every property declaration in a file.</span></span> <span data-ttu-id="5308b-208"><xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker?displayProperty=nameWithType> 클래스를 확장하고 <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitPropertyDeclaration(Microsoft.CodeAnalysis.CSharp.Syntax.PropertyDeclarationSyntax)> 메서드를 재정의하여 해당 구조를 미리 알지 못해도 구문 트리에서 모든 속성 선언을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-208">By extending the <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker?displayProperty=nameWithType> class and overriding the <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitPropertyDeclaration(Microsoft.CodeAnalysis.CSharp.Syntax.PropertyDeclarationSyntax)> method, you process every property declaration in a syntax tree without knowing its structure beforehand.</span></span> <span data-ttu-id="5308b-209"><xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker>는 노드와 해당 자식 항목을 재귀적으로 방문하는 특정 종류의 <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor>입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-209"><xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> is a specific kind of <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor> that recursively visits a node and each of its children.</span></span>

<span data-ttu-id="5308b-210">이 예제에서는 구문 트리를 검사하는 <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-210">This example implements a <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> that examines a syntax tree.</span></span> <span data-ttu-id="5308b-211">`System` 네임스페이스를 가져오지 않는 `using` 지시문을 찾아 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-211">It collects `using` directives it finds that aren't importing a `System` namespace.</span></span>

<span data-ttu-id="5308b-212">새 C# **독립 실행형 코드 분석 도구** 프로젝트를 만들고 이름을 "**SyntaxWalker**"로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-212">Create a new C# **Stand-Alone Code Analysis Tool** project; name it "**SyntaxWalker**."</span></span>

<span data-ttu-id="5308b-213">[GitHub 리포지토리](https://github.com/dotnet/docs/tree/master/samples/csharp/roslyn-sdk/SyntaxQuickStart)에서 이 샘플의 완성된 코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-213">You can see the finished code for this sample in [our GitHub repository](https://github.com/dotnet/docs/tree/master/samples/csharp/roslyn-sdk/SyntaxQuickStart).</span></span> <span data-ttu-id="5308b-214">GitHub의 샘플에는 이 자습서에 설명된 모든 프로젝트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-214">The sample on GitHub contains both projects described in this tutorial.</span></span>

<span data-ttu-id="5308b-215">앞의 예제와 같이 분석하려는 프로그램의 텍스트를 포함하도록 문자열 상수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-215">As in the previous sample, you can define a string constant to hold the text of the program you're going to analyze:</span></span>

[!code-csharp[Define the code text to analyzer](../../../../samples/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/Program.cs#1 "Define the program text to analyze")]

<span data-ttu-id="5308b-216">이 원본 텍스트에는 파일 수준, 최상위 네임스페이스 및 두 개의 중첩된 네임스페이스와 같은 네 가지 위치에 분산된 `using` 지시문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-216">This source text contains `using` directives scattered across four different locations: the file-level, in the top-level namespace, and in the two nested namespaces.</span></span> <span data-ttu-id="5308b-217">이 예제에서는 코드를 쿼리하는 <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> 클래스를 사용하는 핵심 시나리오를 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-217">This example highlights a core scenario for using the <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> class to query code.</span></span> <span data-ttu-id="5308b-218">using 선언을 찾기 위해 루트 구문 트리에서 모든 노드를 방문하기는 번거롭습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-218">It would be cumbersome to visit every node in the root syntax tree to find using declarations.</span></span> <span data-ttu-id="5308b-219">대신, 파생된 클래스를 만들고 트리의 현재 노드가 using 지시문인 경우에만 호출되는 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-219">Instead, you create a derived class and override the method that gets called only when the current node in the tree is a using directive.</span></span> <span data-ttu-id="5308b-220">방문자는 다른 노드 형식에서 작업을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-220">Your visitor does not do any work on any other node types.</span></span> <span data-ttu-id="5308b-221">이 단일 메서드는 각 `using` 문을 검사하고 `System` 네임스페이스에 위치하지 않는 네임스페이스의 컬렉션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-221">This single method examines each of the `using` statements and builds a collection of the namespaces that aren't in the `System` namespace.</span></span> <span data-ttu-id="5308b-222">모든 `using` 문이 아닌 `using` 문을 검사하는 <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker>를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-222">You build a <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> that examines all the `using` statements, but only the `using` statements.</span></span>

<span data-ttu-id="5308b-223">이제 프로그램 텍스트를 정의했으므로 `SyntaxTree`를 만들고 해당 트리의 루트를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-223">Now that you've defined the program text, you need to create a `SyntaxTree` and get the root of that tree:</span></span>

[!code-csharp[Create the Syntax tree and access the root](../../../../samples/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/Program.cs#2 "Create the Syntax tree and access the root node.")]

<span data-ttu-id="5308b-224">다음으로 새 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-224">Next, create a new class.</span></span> <span data-ttu-id="5308b-225">Visual Studio에서 **프로젝트** > **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-225">In Visual Studio, choose **Project** > **Add New Item**.</span></span> <span data-ttu-id="5308b-226">**새 항목 추가** 대화 상자에서 파일 이름으로 *UsingCollector.cs*를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-226">In the **Add New Item** dialog type *UsingCollector.cs* as the filename.</span></span>

<span data-ttu-id="5308b-227">`UsingCollector` 클래스에서 `using` 방문자 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-227">You implement the `using` visitor functionality in the `UsingCollector` class.</span></span> <span data-ttu-id="5308b-228"><xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker>에서 파생된 `UsingCollector` 클래스를 만들기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-228">Start by making the `UsingCollector` class derive from <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker>.</span></span>

[!code-csharp[Declare the base class for the using collector](../../../../samples/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/UsingCollector.cs#3 "Declare the base class for the UsingCollector")]

<span data-ttu-id="5308b-229">수집 중인 네임스페이스 노드를 포함하는 저장소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-229">You need storage to hold the namespace nodes that you're collecting.</span></span>  <span data-ttu-id="5308b-230">`UsingCollector` 클래스에서 공용 읽기 전용 속성을 선언합니다. 이 변수를 사용하여 찾은 <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax> 노드를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-230">Declare a public read-only property in the `UsingCollector` class; you use this variable to store the <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax> nodes you find:</span></span>

[!code-csharp[Declare storage for the using syntax nodes](../../../../samples/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/UsingCollector.cs#4 "Declare storage for the using syntax nodes")]

<span data-ttu-id="5308b-231"><xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> 기본 클래스는 구문 트리에서 각 노드를 방문하는 논리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-231">The base class, <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> implements the logic to visit each node in the syntax tree.</span></span> <span data-ttu-id="5308b-232">파생된 클래스는 관심이 있는 특정 노드에 호출되는 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-232">The derived class overrides the methods called for the specific nodes you're interested in.</span></span> <span data-ttu-id="5308b-233">이 경우에 `using` 지시문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-233">In this case, you're interested in any `using` directive.</span></span> <span data-ttu-id="5308b-234">즉, <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitUsingDirective(Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax)> 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-234">That means you must override the <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitUsingDirective(Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax)> method.</span></span> <span data-ttu-id="5308b-235">이 메서드에 대한 인수는 <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax?displayProperty=nameWithType> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-235">The one argument to this method is a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="5308b-236">방문자를 사용하는 중요한 장점은 특정 노드 형식에 캐스팅된 인수를 사용하여 재정의된 메서드를 호출한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-236">That's an important advantage to using the visitors: they call the overridden methods with arguments already cast to the specific node type.</span></span> <span data-ttu-id="5308b-237"><xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax?displayProperty=nameWithType> 클래스에는 가져온 네임스페이스의 이름을 저장하는 <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax.Name> 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-237">The <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax?displayProperty=nameWithType> class has a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax.Name> property that stores the name of the namespace being imported.</span></span> <span data-ttu-id="5308b-238"><xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-238">It is a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5308b-239"><xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitUsingDirective(Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax)> 재정의에서 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-239">Add the following code in the <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitUsingDirective(Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax)> override:</span></span>

[!code-csharp[Examine using nodes for the System namespace](../../../../samples/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/UsingCollector.cs#5 "Examine all using nodes for the System namespace.")]

<span data-ttu-id="5308b-240">이전 예제에서 다양한 `WriteLine` 문을 추가하여 이 메서드를 이해할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-240">As with the earlier example, you've added a variety of `WriteLine` statements to aid in understanding of this method.</span></span> <span data-ttu-id="5308b-241">호출할 시기 및 이 때 전달된 인수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-241">You can see when it's called, and what arguments are passed to it each time.</span></span>

<span data-ttu-id="5308b-242">마지막으로 `UsingCollector`를 만들고 루트 노드를 방문하게 만드는 두 개의 코드 줄을 추가해야 합니다. 그러면 모든 `using` 문을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-242">Finally, you need to add two lines of code to create the `UsingCollector` and have it visit the root node, collecting all the `using` statements.</span></span> <span data-ttu-id="5308b-243">그런 다음, `foreach` 루프를 추가하여 수집기에서 찾은 `using` 문을 모두 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-243">Then, add a `foreach` loop to display all the `using` statements your collector found:</span></span>

[!code-csharp[Create the UsingCollector and visit the root node.](../../../../samples/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/Program.cs#6 "Create the UsingCollector and visit the root node.")]

<span data-ttu-id="5308b-244">프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-244">Compile and run the program.</span></span> <span data-ttu-id="5308b-245">다음과 같은 내용이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-245">You should see the following output:</span></span>

```console
        VisitUsingDirective called with System.
        VisitUsingDirective called with System.Collections.Generic.
        VisitUsingDirective called with System.Linq.
        VisitUsingDirective called with System.Text.
        VisitUsingDirective called with Microsoft.CodeAnalysis.
                Success. Adding Microsoft.CodeAnalysis.
        VisitUsingDirective called with Microsoft.CodeAnalysis.CSharp.
                Success. Adding Microsoft.CodeAnalysis.CSharp.
        VisitUsingDirective called with Microsoft.
                Success. Adding Microsoft.
        VisitUsingDirective called with System.ComponentModel.
        VisitUsingDirective called with Microsoft.Win32.
                Success. Adding Microsoft.Win32.
        VisitUsingDirective called with System.Runtime.InteropServices.
        VisitUsingDirective called with System.CodeDom.
        VisitUsingDirective called with Microsoft.CSharp.
                Success. Adding Microsoft.CSharp.
Microsoft.CodeAnalysis
Microsoft.CodeAnalysis.CSharp
Microsoft
Microsoft.Win32
Microsoft.CSharp
Press any key to continue . . .
```

<span data-ttu-id="5308b-246">지금까지</span><span class="sxs-lookup"><span data-stu-id="5308b-246">Congratulations!</span></span> <span data-ttu-id="5308b-247">**구문 API**를 사용하여 C# 소스 코드에서 특정 종류의 C# 문 및 선언을 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="5308b-247">You've used the **Syntax API** to locate specific kinds of C# statements and declarations in C# source code.</span></span>
