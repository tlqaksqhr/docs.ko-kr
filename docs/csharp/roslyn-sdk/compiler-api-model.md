---
title: .NET Compiler Platform SDK 개념 및 개체 모델
description: 이 개요는 .NET 컴파일러 SDK와 함께 효과적으로 작동해야 하는 배경 정보를 제공합니다. API 계층, 관련된 주요 형식 및 전체 개체 모델을 학습합니다.
ms.date: 10/10/2017
ms.custom: mvc
ms.openlocfilehash: a3104313efa0110699c45a4ce7bca99aab20542a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="understand-the-net-compiler-platform-sdk-model"></a><span data-ttu-id="778a2-104">.NET Compiler Platform SDK 모델 이해</span><span class="sxs-lookup"><span data-stu-id="778a2-104">Understand the .NET Compiler Platform SDK model</span></span>

<span data-ttu-id="778a2-105">컴파일러는 종종 사람이 코드를 읽고 이해하는 방식과 다른 구조적 규칙을 따라 작성하는 코드를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-105">Compilers process the code you write following structured rules that often differ from the way humans read and understand code.</span></span> <span data-ttu-id="778a2-106">컴파일러에서 사용되는 모델에 대한 기본적인 이해는 Roslyn 기반 도구를 빌드할 때 사용하는 API를 이해하는 데 반드시 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-106">A basic understanding of the model used by compilers is essential to understanding the APIs you use when building Roslyn-based tools.</span></span> 

## <a name="compiler-pipeline-functional-areas"></a><span data-ttu-id="778a2-107">컴파일러 파이프라인 기능 영역</span><span class="sxs-lookup"><span data-stu-id="778a2-107">Compiler pipeline functional areas</span></span>

<span data-ttu-id="778a2-108">.NET Compiler Platform SDK는 기존의 컴파일러 파이프라인을 미러링하는 API 계층을 제공하여 소비자로서 사용자에게 C# 및 Visual Basic 컴파일러의 코드 분석을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-108">The .NET Compiler Platform SDK exposes the C# and Visual Basic compilers' code analysis to you as a consumer by providing an API layer that mirrors a traditional compiler pipeline.</span></span>

![개체 코드로 소스 코드를 처리하는 컴파일러 파이프라인의 단계](media/compiler-api-model/compiler-pipeline.png)

<span data-ttu-id="778a2-110">이 파이프라인의 각 단계는 별도 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-110">Each phase of this pipeline is a separate component.</span></span> <span data-ttu-id="778a2-111">첫째로, 구문 분석 단계는 원본 텍스트를 언어 문법 뒤에 오는 구문으로 토큰화하고 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-111">First, the parse phase tokenizes and parses source text into syntax that follows the language grammar.</span></span> <span data-ttu-id="778a2-112">둘째로, 선언 단계는 원본 및 가져온 메타데이터를 분석하여 명명된 기호를 형성합니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-112">Second, the declaration phase analyzes source and imported metadata to form named symbols.</span></span> <span data-ttu-id="778a2-113">다음으로 바인딩 단계는 코드의 식별자를 기호와 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-113">Next, the bind phase matches identifiers in the code to symbols.</span></span> <span data-ttu-id="778a2-114">마지막으로 내보내기 단계는 컴파일러로 생성된 모든 정보와 함께 어셈블리를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-114">Finally, the emit phase emits an assembly with all the information built up by the compiler.</span></span>

![컴파일러 파이프라인 API는 컴파일러 파이프라인의 일부인 각 단계에 대한 액세스를 제공합니다.](media/compiler-api-model/compiler-pipeline-api.png)

<span data-ttu-id="778a2-116">이러한 각 단계에 해당하여 .NET Compiler Platform SDK는 해당 단계에서 정보에 액세스할 수 있는 개체 모델을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-116">Corresponding to each of those phases, the .NET Compiler Platform SDK exposes an object model that allows access to the information at that phase.</span></span> <span data-ttu-id="778a2-117">구문 분석 단계는 구문 트리를 노출하고, 선언 단계는 계층적 기호 테이블을 노출하고, 바인딩 단계는 컴파일러의 의미 체계 분석 결과를 노출하고, 내보내기 단계는 IL 바이트 코드를 생성하는 API입니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-117">The parsing phase exposes a syntax tree, the declaration phase exposes a hierarchical symbol table, the binding phase exposes the result of the compiler’s semantic analysis, and the emit phase is an API that produces IL byte codes.</span></span>

![컴파일러 파이프라인의 각 단계에서 컴파일러 API에 사용할 수 있는 언어 서비스](media/compiler-api-model/compiler-pipeline-lang-svc.png)

<span data-ttu-id="778a2-119">각 컴파일러는 단일 종단 간 전체로 이러한 구성 요소를 하나로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-119">Each compiler combines these components together as a single end-to-end whole.</span></span>

<span data-ttu-id="778a2-120">이러한 API는 Visual Studio에서 사용하는 API와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-120">These APIs are the same ones used by Visual Studio.</span></span> <span data-ttu-id="778a2-121">예를 들어 코드 개요 및 서식 지정 기능은 구문 트리를 사용하고, 개체 브라우저 및 탐색 기능은 기호 테이블을 사용하며, 리팩터링 및 정의로 이동은 의미 체계 모델을 사용하고, 편집하며 계속하기는 내보내기 API를 포함하여 이러한 모든 것을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-121">For instance, the code outlining and formatting features use the syntax trees, the Object Browser and navigation features use the symbol table, refactorings and Go to Definition use the semantic model, and Edit and Continue uses all of these, including the Emit API.</span></span> 

## <a name="api-layers"></a><span data-ttu-id="778a2-122">API 계층</span><span class="sxs-lookup"><span data-stu-id="778a2-122">API layers</span></span>

<span data-ttu-id="778a2-123">.NET 컴파일러 SDK는 두 개의 주요 API 계층인 컴파일러 API 및 작업 영역 API로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-123">The .NET compiler SDK consists of two main layers of APIs: compiler APIs and workspaces APIs.</span></span>

![컴파일러 파이프라인 API에 의해 표시되는 API 계층](media/compiler-api-model/api-layers.png)

### <a name="compiler-apis"></a><span data-ttu-id="778a2-125">컴파일러 API</span><span class="sxs-lookup"><span data-stu-id="778a2-125">Compiler APIs</span></span>

<span data-ttu-id="778a2-126">컴파일러 계층은 구문 및 의미 체계 모두의 컴파일러 파이프라인의 각 단계에서 노출되는 정보에 해당하는 개체 모델을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-126">The compiler layer contains the object models that correspond to information exposed at each phase of the compiler pipeline, both syntactic and semantic.</span></span> <span data-ttu-id="778a2-127">컴파일러 계층은 어셈블리 참조, 컴파일러 옵션 및 소스 코드 파일을 포함하는 컴파일러 단일 호출의 변경할 수 없는 스냅숏도 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-127">The compiler layer also contains an immutable snapshot of a single invocation of a compiler, including assembly references, compiler options, and source code files.</span></span> <span data-ttu-id="778a2-128">C# 언어 및 Visual Basic 언어를 나타내는 두 개의 고유한 API가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-128">There are two distinct APIs that represent the C# language and the Visual Basic language.</span></span> <span data-ttu-id="778a2-129">이러한 두 개의 API는 모양에서 유사하지만 각 개별 언어에 대한 충실도가 높도록 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-129">These two APIs are similar in shape but tailored for high-fidelity to each individual language.</span></span> <span data-ttu-id="778a2-130">이 계층에는 Visual Studio 구성 요소에 대한 종속성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-130">This layer has no dependencies on Visual Studio components.</span></span>

### <a name="diagnostic-apis"></a><span data-ttu-id="778a2-131">진단 API</span><span class="sxs-lookup"><span data-stu-id="778a2-131">Diagnostic APIs</span></span>

<span data-ttu-id="778a2-132">해당 분석의 일환으로 컴파일러는 구문, 의미 체계 및 확실한 할당 오류에서부터 다양한 경고 및 정보 진단까지 모든 것을 다루는 진단 집합을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-132">As part of its analysis the compiler may produce a set of diagnostics covering everything from syntax, semantic, and definite assignment errors to various warnings and informational diagnostics.</span></span> <span data-ttu-id="778a2-133">컴파일러 API 계층은 사용자 정의 분석기를 컴파일 프로세스에 연결할 수 있도록 하는 확장 가능한 API를 통해 진단을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-133">The Compiler API layer exposes diagnostics through an extensible API that allows user-defined analyzers to be plugged into the compilation process.</span></span> <span data-ttu-id="778a2-134">StyleCop 또는 FxCop과 같은 도구에서 만든 것과 같은 사용자 정의 진단을 컴파일러 정의 진단과 함께 생성되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-134">It allows user-defined diagnostics, such as those produced by tools like StyleCop or FxCop, to be produced alongside compiler-defined diagnostics.</span></span> <span data-ttu-id="778a2-135">이러한 방식으로 진단을 생성하면 정책에 기반한 빌드 중지 및 편집기에서 라이브 물결선 표시 및 코드 수정 사항 제안과 같은 환경에 대한 진단에 의존하는 MSBuild 및 Visual Studio와 같은 도구와 자연스럽게 통합하는 이점을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-135">Producing diagnostics in this way has the benefit of integrating naturally with tools such as MSBuild and Visual Studio which depend on diagnostics for experiences such as halting a build based on policy and showing live squiggles in the editor and suggesting code fixes.</span></span>

### <a name="scripting-apis"></a><span data-ttu-id="778a2-136">스크립팅 API</span><span class="sxs-lookup"><span data-stu-id="778a2-136">Scripting APIs</span></span>

<span data-ttu-id="778a2-137">호스팅 및 스크립팅 API는 컴파일러 계층의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-137">Hosting and scripting APIs are part of the compiler layer.</span></span> <span data-ttu-id="778a2-138">코드 조각을 실행하고 런타임 실행 컨텍스트를 누적하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-138">You can use them for executing code snippets and accumulating a runtime execution context.</span></span>
<span data-ttu-id="778a2-139">C# 대화형 REPL(읽기 평가 인쇄 루프)은 이러한 API를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-139">The C# interactive REPL (Read-Evaluate-Print Loop) uses these APIs.</span></span> <span data-ttu-id="778a2-140">REPL을 통해 작성함에 따라 대화형으로 코드를 실행하여 스크립팅 언어로 C#을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-140">The REPL enables you to use C# as a scripting language, executing the code interactively as you write it.</span></span>

### <a name="workspaces-apis"></a><span data-ttu-id="778a2-141">작업 영역 API</span><span class="sxs-lookup"><span data-stu-id="778a2-141">Workspaces APIs</span></span>

<span data-ttu-id="778a2-142">작업 영역 계층은 코드 분석을 수행하고 전체 솔루션을 통해 리팩터링하는 시작 지점인 작업 영역 API를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-142">The Workspaces layer contains the Workspace API, which is the starting point for doing code analysis and refactoring over entire solutions.</span></span> <span data-ttu-id="778a2-143">파일을 구문 분석하고, 옵션을 구성하거나 프로젝트 간 종속성을 관리하지 않고도 컴파일러 계층 개체 모델에 대한 직접 액세스를 제공하여 솔루션의 프로젝트에 대한 모든 정보를 단일 개체 모델로 구성하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-143">It assists you in organizing all the information about the projects in a solution into single object model, offering you direct access to the compiler layer object models without needing to parse files, configure options, or manage project-to-project dependencies.</span></span>

<span data-ttu-id="778a2-144">또한 작업 영역 계층은 코드 분석을 구현하고 Visual Studio IDE와 같은 호스트 환경 내에서 작동하는 도구를 리팩터링할 때 사용되는 API 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-144">In addition, the Workspaces layer surfaces a set of APIs used when implementing code analysis and refactoring tools that function within a host environment like the Visual Studio IDE.</span></span> <span data-ttu-id="778a2-145">모든 참조 찾기, 서식 지정 및 코드 생성 API를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-145">Examples include the Find All References, Formatting, and Code Generation APIs.</span></span>

<span data-ttu-id="778a2-146">이 계층에는 Visual Studio 구성 요소에 대한 종속성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="778a2-146">This layer has no dependencies on Visual Studio components.</span></span>
