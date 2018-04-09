---
title: 의미 체계 분석 시작
description: 이 자습서는 .NET Compiler SDK를 사용하여 의미 체계 분석으로 작업하는 방법의 개요를 제공합니다.
author: billwagner
ms.author: wiwagn
ms.date: 02/06/2018
ms.topic: conceptual
ms.prod: .net
ms.devlang: devlang-csharp
ms.custom: mvc
ms.openlocfilehash: b9921bc3621d6abfc37b1bf1fc4f481620ccc407
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2018
---
# <a name="get-started-with-semantic-analysis"></a><span data-ttu-id="2dcfb-103">의미 체계 분석 시작</span><span class="sxs-lookup"><span data-stu-id="2dcfb-103">Get started with semantic analysis</span></span>

<span data-ttu-id="2dcfb-104">이 자습서는 사용자가 구문 API에 익숙하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-104">This tutorial assumes you're familiar with the Syntax API.</span></span> <span data-ttu-id="2dcfb-105">[구문 분석 작업 시작](syntax-analysis.md) 아티클에서는 소개를 충분히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-105">The [get started with syntax analysis](syntax-analysis.md) article provides sufficient introduction.</span></span>

<span data-ttu-id="2dcfb-106">이 자습서에서는 **기호** 및 **바인딩 API**를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-106">In this tutorial, you explore the **Symbol** and **Binding APIs**.</span></span> <span data-ttu-id="2dcfb-107">이러한 API는 프로그램의 _의미 체계_에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-107">These APIs provide information about the _semantic meaning_ of a program.</span></span> <span data-ttu-id="2dcfb-108">이를 통해 프로그램에서 기호를 나타내는 형식에 대해 질문하고 대답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-108">They enable you to ask and answer questions about the types represented by any symbol in your program.</span></span>

<span data-ttu-id="2dcfb-109">**.NET Compiler Platform SDK**를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-109">You'll need to install the **.NET Compiler Platform SDK**:</span></span>

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

## <a name="understanding-compilations-and-symbols"></a><span data-ttu-id="2dcfb-110">컴파일 및 기호 이해</span><span class="sxs-lookup"><span data-stu-id="2dcfb-110">Understanding Compilations and Symbols</span></span>

<span data-ttu-id="2dcfb-111">.NET Compiler SDK에서 작업하게 되면 구문 API와 의미 체계 API 간의 차이점을 이해할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-111">As you work more with the .NET Compiler SDK, you become familiar with the distinctions between Syntax API and the Semantic API.</span></span> <span data-ttu-id="2dcfb-112">**구문 API**를 사용하면 프로그램의 _구조_를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-112">The **Syntax API** allows you to look at the _structure_ of a program.</span></span> <span data-ttu-id="2dcfb-113">그러나 프로그램의 의미 체계 또는 _의미_에 대해 더 다양한 정보가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-113">However, often you want richer information about the semantics or _meaning_ of a program.</span></span> <span data-ttu-id="2dcfb-114">느슨한 코드 파일 또는 VB 또는 C#의 코드 조각은 격리에서 구문을 분석할 수 있습니다. "이 변수의 형식이란?"과 같은 질문은 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-114">While a loose code file or snippet of VB or C# code can be syntactically analyzed in isolation, it's not meaningful to ask questions such as "what's the type of this variable" in a vacuum.</span></span> <span data-ttu-id="2dcfb-115">형식 이름의 의미는 어셈블리 참조, 네임스페이스 가져오기 또는 기타 코드 파일에 종속될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-115">The meaning of a type name may be dependent on assembly references, namespace imports, or other code files.</span></span> <span data-ttu-id="2dcfb-116">**의미 체계 API**, 특히 <xref:Microsoft.CodeAnalysis.Compilation?displayProperty=nameWithType> 클래스를 사용하여 해당 질문에 대답합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-116">Those questions are answered using the **Semantic API**, specifically the <xref:Microsoft.CodeAnalysis.Compilation?displayProperty=nameWithType> class.</span></span>

<span data-ttu-id="2dcfb-117"><xref:Microsoft.CodeAnalysis.Compilation>의 인스턴스는 컴파일러에서 보는 단일 프로젝트와 유사하고, Visual Basic 또는 C# 프로그램을 컴파일하는 데 필요한 모든 항목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-117">An instance of <xref:Microsoft.CodeAnalysis.Compilation> is analogous to a single project as seen by the compiler and represents everything needed to compile a Visual Basic or C# program.</span></span> <span data-ttu-id="2dcfb-118">**컴파일**에는 컴파일할 원본 파일, 어셈블리 참조 및 컴파일러 옵션의 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-118">The **compilation** includes the set of source files to be compiled, assembly references, and compiler options.</span></span> <span data-ttu-id="2dcfb-119">이 컨텍스트에서 다른 모든 정보를 사용하여 코드의 의미에 대해 추정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-119">You can reason about the meaning of the code using all the other information in this context.</span></span> <span data-ttu-id="2dcfb-120"><xref:Microsoft.CodeAnalysis.Compilation>을 사용하면 이름 및 다른 식이 참조하는 형식, 네임스페이스, 멤버 및 변수 등의 엔터티인 **기호**를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-120">A <xref:Microsoft.CodeAnalysis.Compilation> allows you to find **Symbols** - entities such as types, namespaces, members, and variables which names and other expressions refer to.</span></span> <span data-ttu-id="2dcfb-121">**기호**를 사용하여 이름 및 식을 연결하는 프로세스를 **바인딩**이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-121">The process of associating names and expressions with **Symbols** is called **Binding**.</span></span>

<span data-ttu-id="2dcfb-122"><xref:Microsoft.CodeAnalysis.SyntaxTree?displayProperty=nameWithType>과 마찬가지로 <xref:Microsoft.CodeAnalysis.Compilation>은 언어별 파생물을 포함하는 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-122">Like <xref:Microsoft.CodeAnalysis.SyntaxTree?displayProperty=nameWithType>, <xref:Microsoft.CodeAnalysis.Compilation> is an abstract class with language-specific derivatives.</span></span> <span data-ttu-id="2dcfb-123">컴파일의 인스턴스를 만들 때 <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation?displayProperty=nameWithType>(또는 <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicCompilation?displayProperty=nameWithType>) 클래스에서 팩터리 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-123">When creating an instance of Compilation, you must invoke a factory method on the <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation?displayProperty=nameWithType> (or <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicCompilation?displayProperty=nameWithType>) class.</span></span>

## <a name="querying-symbols"></a><span data-ttu-id="2dcfb-124">기호 쿼리</span><span class="sxs-lookup"><span data-stu-id="2dcfb-124">Querying symbols</span></span>

<span data-ttu-id="2dcfb-125">이 자습서에서는 "Hello World" 프로그램을 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-125">In this tutorial, you look at the "Hello World" program again.</span></span> <span data-ttu-id="2dcfb-126">이번에는 프로그램의 기호를 쿼리하여 해당 기호가 나타내는 형식을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-126">This time, you query the symbols in the program to understand what types those symbols represent.</span></span> <span data-ttu-id="2dcfb-127">네임스페이스의 형식에 대해 쿼리하고 형식에 사용할 수 있는 메서드를 찾는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-127">You query for the types in a namespace, and learn to find the methods available on a type.</span></span>

<span data-ttu-id="2dcfb-128">[GitHub 리포지토리](https://github.com/dotnet/docs/tree/master/samples/csharp/roslyn-sdk/SemanticQuickStart)에서 이 샘플의 완성된 코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-128">You can see the finished code for this sample in [our GitHub repository](https://github.com/dotnet/docs/tree/master/samples/csharp/roslyn-sdk/SemanticQuickStart).</span></span>

> [!NOTE]
> <span data-ttu-id="2dcfb-129">구문 트리 형식은 상속을 사용하여 프로그램의 여러 위치에서 유효한 다른 구문 요소를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-129">The Syntax Tree types use inheritance to describe the different syntax elements that are valid at different locations in the program.</span></span> <span data-ttu-id="2dcfb-130">종종 이러한 API를 사용하면 속성이나 컬렉션 멤버를 파생된 특정 형식에 캐스팅하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-130">Using these APIs often means casting properties or collection members to specific derived types.</span></span> <span data-ttu-id="2dcfb-131">다음 예제에서 할당 및 캐스팅은 명시적으로 형식화된 변수를 사용하는 별도의 문입니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-131">In the following examples, the assignment and the casts are separate statements, using explicitly typed variables.</span></span> <span data-ttu-id="2dcfb-132">API의 반환 형식 및 반환되는 개체의 런타임 형식을 확인하기 위해 코드를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-132">You can read the code to see the return types of the API and the runtime type of the objects returned.</span></span> <span data-ttu-id="2dcfb-133">이 연습에서는 암시적으로 형식화된 변수를 사용하고 API 이름을 사용하여 검사된 개체의 형식을 설명하는 것이 더 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-133">In practice, it's more common to use implicitly typed variables and rely on API names to describe the type of objects being examined.</span></span>

<span data-ttu-id="2dcfb-134">새 C# **독립 실행형 코드 분석 도구** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-134">Create a new C# **Stand-Alone Code Analysis Tool** project:</span></span>

* <span data-ttu-id="2dcfb-135">Visual Studio에서 **파일** > **새로 만들기** > **프로젝트**를 선택하여 새 프로젝트 대화 상자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-135">In Visual Studio, choose **File** > **New** > **Project** to display the New Project dialog.</span></span>
* <span data-ttu-id="2dcfb-136">**Visual C#** > **확장성** 아래에서 **독립 실행형 코드 분석 도구**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-136">Under **Visual C#** > **Extensibility**, choose **Stand-Alone Code Analysis Tool**.</span></span>
* <span data-ttu-id="2dcfb-137">프로젝트 이름을 "**SemanticQuickStart**"로 지정하고 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-137">Name your project "**SemanticQuickStart**" and click OK.</span></span>

<span data-ttu-id="2dcfb-138">앞에 표시된 기본 "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="2dcfb-138">You're going to analyze the basic "Hello World!"</span></span> <span data-ttu-id="2dcfb-139">프로그램을 분석하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-139">program shown earlier.</span></span>
<span data-ttu-id="2dcfb-140">Hello World 프로그램의 텍스트를 `Program` 클래스의 상수로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-140">Add the text for the Hello World program as a constant in your `Program` class:</span></span>

[!code-csharp[Declare the program test](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#1 "Declare a constant string for the program text to analyze")]

<span data-ttu-id="2dcfb-141">다음으로 `programText` 상수에서 코드 텍스트의 구문 트리를 빌드하는 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-141">Next, add the following code to build the syntax tree for the code text in the `programText` constant.</span></span>  <span data-ttu-id="2dcfb-142">`Main` 메서드에 다음 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-142">Add the following line to your `Main` method:</span></span>

[!code-csharp[Create the tree](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#2 "Create the syntax tree")]

<span data-ttu-id="2dcfb-143">다음으로 이미 만든 트리에서 <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation>을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-143">Next, build a <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation> from the tree you already created.</span></span> <span data-ttu-id="2dcfb-144">"Hello World" 샘플은 <xref:System.String> 및 <xref:System.Console> 형식으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-144">The "Hello World" sample relies on the <xref:System.String> and <xref:System.Console> types.</span></span> <span data-ttu-id="2dcfb-145">컴파일에서 두 가지 해당 형식을 선언하는 어셈블리를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-145">You need to reference the assembly that declares those two types in your compilation.</span></span> <span data-ttu-id="2dcfb-146">다음 줄을 `Main` 메서드에 추가하여 적절한 어셈블리에 대한 참조를 비롯한 구문 트리의 컴파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-146">Add the following line to your `Main` method to create a compilation of your syntax tree, including the reference to the appropriate assembly:</span></span>

[!code-csharp[Create the compilation](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#3 "Create the compilation for the semantic model")]

<span data-ttu-id="2dcfb-147"><xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation.AddReferences%2A?displayProperty=nameWithType> 메서드는 컴파일에 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-147">The <xref:Microsoft.CodeAnalysis.CSharp.CSharpCompilation.AddReferences%2A?displayProperty=nameWithType> method adds references to the compilation.</span></span> <span data-ttu-id="2dcfb-148"><xref:Microsoft.CodeAnalysis.MetadataReference.CreateFromFile%2A?displayProperty=nameWithType> 메서드는 어셈블리를 참조로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-148">The <xref:Microsoft.CodeAnalysis.MetadataReference.CreateFromFile%2A?displayProperty=nameWithType> method loads an assembly as a reference.</span></span> 

## <a name="querying-the-semantic-model"></a><span data-ttu-id="2dcfb-149">의미 체계 모델 쿼리</span><span class="sxs-lookup"><span data-stu-id="2dcfb-149">Querying the semantic model</span></span>

<span data-ttu-id="2dcfb-150"><xref:Microsoft.CodeAnalysis.Compilation>이 있다면 <xref:Microsoft.CodeAnalysis.SemanticModel>에 대해 해당 <xref:Microsoft.CodeAnalysis.Compilation>에 포함된 <xref:Microsoft.CodeAnalysis.SyntaxTree>를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-150">Once you have a <xref:Microsoft.CodeAnalysis.Compilation> you can ask it for a <xref:Microsoft.CodeAnalysis.SemanticModel> for any <xref:Microsoft.CodeAnalysis.SyntaxTree> contained in that <xref:Microsoft.CodeAnalysis.Compilation>.</span></span> <span data-ttu-id="2dcfb-151">일반적으로 모든 정보의 원본을 IntelliSense에서 가져오는 경우 의미 체계 모델을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-151">You can think of the semantic model as the source for all the information you would normally get from intellisense.</span></span> <span data-ttu-id="2dcfb-152"><xref:Microsoft.CodeAnalysis.SemanticModel>은 "이 위치에서 범위에 있는 이름은 무엇입니까?", "이 메서드에서 어떤 멤버에 액세스할 수 있습니까?", "이 텍스트의 블록에서 사용되는 변수는 무엇입니까?" 및 "이 이름/식은 무엇을 참조합니까?"와 같은 질문에 대답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-152">A <xref:Microsoft.CodeAnalysis.SemanticModel> can answer questions like "What names are in scope at this location?", "What members are accessible from this method?", "What variables are used in this block of text?", and "What does this name/expression refer to?"</span></span> <span data-ttu-id="2dcfb-153">의미 체계 모델을 만드는 이 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-153">Add this statement to create the semantic model:</span></span>

[!code-csharp[Create the semantic model](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#4 "Create the semantic model")]

## <a name="binding-a-name"></a><span data-ttu-id="2dcfb-154">이름 바인딩</span><span class="sxs-lookup"><span data-stu-id="2dcfb-154">Binding a name</span></span>

<span data-ttu-id="2dcfb-155"><xref:Microsoft.CodeAnalysis.Compilation>은 <xref:Microsoft.CodeAnalysis.SyntaxTree>에서 <xref:Microsoft.CodeAnalysis.SemanticModel>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-155">The <xref:Microsoft.CodeAnalysis.Compilation> creates the  <xref:Microsoft.CodeAnalysis.SemanticModel> from the <xref:Microsoft.CodeAnalysis.SyntaxTree>.</span></span> <span data-ttu-id="2dcfb-156">모델을 만든 후에 쿼리하여 첫 번째 `using` 지시문을 찾고 `System` 네임스페이스에 대한 기호 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-156">After creating the model, you can query it to find the first `using` directive, and retrieve the symbol information for the `System` namespace.</span></span> <span data-ttu-id="2dcfb-157">`Main` 메서드에 두 줄을 추가하여 의미 체계 모델을 만들고 첫 번째 using 문에 대한 기호를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-157">Add these two lines to your `Main` method to create the semantic model and retrieve the symbol for the first using statement:</span></span>

[!code-csharp[Find the namespace symbol for the first using](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#5 "Find the namespace symbol for the first using")]

<span data-ttu-id="2dcfb-158">위의 코드는 첫 번째 `using` 지시문의 이름을 바인딩하여 `System` 네임스페이스에서 <xref:Microsoft.CodeAnalysis.SymbolInfo?displayProperty=nameWithType>을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-158">The preceding code shows how to bind the name in the first `using` directive to retrieve a <xref:Microsoft.CodeAnalysis.SymbolInfo?displayProperty=nameWithType> for the `System` namespace.</span></span> <span data-ttu-id="2dcfb-159">또한 위의 코드에서는 **구문 모델**을 사용하여 코드의 구조를 찾는 것을 설명합니다. **의미 체계 모델**을 사용하여 해당 의미를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-159">The preceding code also illustrates that you use the **syntax model** to find the structure of the code; you use the **semantic model** to understand its meaning.</span></span> <span data-ttu-id="2dcfb-160">**구문 모델**은 using 문에서 `System` 문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-160">The **syntax model** finds the string `System` in the using statement.</span></span> <span data-ttu-id="2dcfb-161">**의미 체계 모델**에는 `System` 네임스페이스에서 정의된 형식에 대한 모든 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-161">The **semantic model** has all the information about the types defined in the `System` namespace.</span></span>

<span data-ttu-id="2dcfb-162"><xref:Microsoft.CodeAnalysis.SymbolInfo> 개체에서 <xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType> 속성을 사용하여 <xref:Microsoft.CodeAnalysis.ISymbol?displayProperty=nameWithType>를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-162">From the <xref:Microsoft.CodeAnalysis.SymbolInfo> object you can obtain the <xref:Microsoft.CodeAnalysis.ISymbol?displayProperty=nameWithType> using the <xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2dcfb-163">이 속성은 이 식에서 참조하는 기호를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-163">This property returns the symbol this expression refers to.</span></span> <span data-ttu-id="2dcfb-164">아무것도 참조하지 않은 식(예: 숫자 리터럴)의 경우 이 속성은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-164">For expressions that don't refer to anything (such as numeric literals) this property is `null`.</span></span> <span data-ttu-id="2dcfb-165"><xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType>이 null이 아니면 <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType>은 기호의 형식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-165">When the <xref:Microsoft.CodeAnalysis.SymbolInfo.Symbol?displayProperty=nameWithType> is not null, the <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType> denotes the type of the symbol.</span></span> <span data-ttu-id="2dcfb-166">다음 예제에서 <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType> 속성은 <xref:Microsoft.CodeAnalysis.SymbolKind.Namespace?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-166">In this example, the <xref:Microsoft.CodeAnalysis.ISymbol.Kind?displayProperty=nameWithType> property is a <xref:Microsoft.CodeAnalysis.SymbolKind.Namespace?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2dcfb-167">`Main` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-167">Add the following code to your `Main` method.</span></span> <span data-ttu-id="2dcfb-168">`System` 네임스페이스에 대한 기호를 검색한 다음, `System` 네임스페이스에 선언된 모든 자식 네임스페이스를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-168">It retrieves the symbol for the `System` namespace and then displays all the child namespaces declared in the `System` namespace:</span></span>

[!code-csharp[Display all the child namespaces](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#6 "Display all the child namespaces from this compilation")]

<span data-ttu-id="2dcfb-169">프로그램을 실행하고 다음과 같은 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-169">Run the program and you should see the following output:</span></span>

```
System.Collections
System.Configuration
System.Deployment
System.Diagnostics
System.Globalization
System.IO
System.Numerics
System.Reflection
System.Resources
System.Runtime
System.Security
System.StubHelpers
System.Text
System.Threading
Press any key to continue . . .
```

> [!NOTE]
> <span data-ttu-id="2dcfb-170">출력에는 `System` 네임스페이스의 자식 네임스페이스인 모든 네임스페이스가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-170">The output does not include every namespace that is a child namespace of the `System` namespace.</span></span> <span data-ttu-id="2dcfb-171">이 컴파일에서 나타나는 모든 네임스페이스가 표시됩니다. 여기서는 `System.String`이 선언하는 어셈블리만을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-171">It displays every namespace that is present in this compilation, which only references the assembly where `System.String` is declared.</span></span> <span data-ttu-id="2dcfb-172">다른 어셈블리에 선언된 모든 네임스페이스가 이 컴파일에 알려지지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-172">Any namespaces declared in other assemblies are not known to this compilation</span></span>

### <a name="binding-an-expression"></a><span data-ttu-id="2dcfb-173">식 바인딩</span><span class="sxs-lookup"><span data-stu-id="2dcfb-173">Binding an expression</span></span>

<span data-ttu-id="2dcfb-174">위의 코드에서는 이름에 바인딩하여 기호를 찾는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-174">The preceding code shows how to find a symbol by binding to a name.</span></span> <span data-ttu-id="2dcfb-175">바인딩될 수 있는 C# 프로그램에 이름이 아닌 다른 식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-175">There are other expressions in a C# program that can be bound that aren't names.</span></span> <span data-ttu-id="2dcfb-176">이 기능을 보여주기 위해 간단한 문자열 리터럴에 대한 바인딩에 액세스하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-176">To demonstrate this capability, let's access the binding to a simple string literal.</span></span>

<span data-ttu-id="2dcfb-177">"Hello World" 프로그램에는 콘솔에 표시된 <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LiteralExpressionSyntax?displayProperty=nameWithType>, "Hello, World!"</span><span class="sxs-lookup"><span data-stu-id="2dcfb-177">The "Hello World" program contains a <xref:Microsoft.CodeAnalysis.CSharp.Syntax.LiteralExpressionSyntax?displayProperty=nameWithType>, the "Hello, World!"</span></span> <span data-ttu-id="2dcfb-178">문자열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-178">string displayed to the console.</span></span>

<span data-ttu-id="2dcfb-179">프로그램에 단일 리터럴 문자열을 배치하여 "Hello, World!"</span><span class="sxs-lookup"><span data-stu-id="2dcfb-179">You find the "Hello, World!"</span></span> <span data-ttu-id="2dcfb-180">문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-180">string by locating the single string literal in the program.</span></span> <span data-ttu-id="2dcfb-181">그런 다음, 구문 노드를 찾으면 의미 체계 모델에서 노드의 형식 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-181">Then, once you've located the syntax node, get the type info for that node from the semantic model.</span></span> <span data-ttu-id="2dcfb-182">`Main` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-182">Add the following code to your `Main` method:</span></span>

[!code-csharp[Find the namespace symbol for the only using](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#7 "Find the namespace symbol for the only using")]

<span data-ttu-id="2dcfb-183"><xref:Microsoft.CodeAnalysis.TypeInfo?displayProperty=nameWithType> 구조체에는 리터럴 형식에 대한 의미 체계 정보에 액세스할 수 있는 <xref:Microsoft.CodeAnalysis.TypeInfo.Type?displayProperty=nameWithType> 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-183">The <xref:Microsoft.CodeAnalysis.TypeInfo?displayProperty=nameWithType> struct includes a <xref:Microsoft.CodeAnalysis.TypeInfo.Type?displayProperty=nameWithType> property that enables access to the semantic information about the type of the literal.</span></span> <span data-ttu-id="2dcfb-184">이 예제에서는 `string` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-184">In this example, that's the `string` type.</span></span> <span data-ttu-id="2dcfb-185">이 속성을 지역 변수에 할당하는 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-185">Add a declaration that assigns this property to a local variable:</span></span>

[!code-csharp[Find the semantic information about the string type](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#8 "Use the string literal to access the semantic information in the string type.")]

<span data-ttu-id="2dcfb-186">이 자습서를 완료하려면 `string`을 반환하는 `string` 형식에 선언된 모든 공용 메서드의 시퀀스를 생성하는 LINQ 쿼리를 빌드하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-186">To finish this tutorial, let's build a LINQ query that creates a sequence of all the public methods declared on the `string` type that return a `string`.</span></span> <span data-ttu-id="2dcfb-187">이 쿼리가 복잡해집니다. 따라서 한 줄씩 빌드한 다음, 단일 쿼리로 다시 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-187">This query gets complex, so let's build it line by line, then reconstruct it as a single query.</span></span> <span data-ttu-id="2dcfb-188">이 쿼리의 원본은 `string` 형식에 선언된 모든 멤버의 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-188">The source for this query is the sequence of all members declared on the `string` type:</span></span>

[!code-csharp[Access the sequence of members on the string type](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#9 "Access the sequence of members on the string type.")]

<span data-ttu-id="2dcfb-189">원본 시퀀스에는 해당 속성 및 필드를 비롯한 모든 멤버가 포함됩니다. 따라서 <xref:Microsoft.CodeAnalysis.IMethodSymbol?diplayProperty=nameWithType> 개체인 요소를 찾기 위해 <xref:System.Collections.Immutable.ImmutableArray%601.OfType%2A?displayProperty=nameWithType> 메서드를 사용하여 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-189">That source sequence conatins all members, including properties and fields, so filter it using the <xref:System.Collections.Immutable.ImmutableArray%601.OfType%2A?displayProperty=nameWithType> method to find elements that are <xref:Microsoft.CodeAnalysis.IMethodSymbol?diplayProperty=nameWithType> objects:</span></span>

[!code-csharp[Filter the sequence to only methods](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#10 "Find the subset of the collection that is the methods.")]

<span data-ttu-id="2dcfb-190">다음으로 공용이며 `string`을 반환하는 해당 메서드만을 반환하는 다른 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-190">Next, add another filter to return only those methods that are public and return a `string`:</span></span>

[!code-csharp[Filter on return type and accessibility](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#11 "Find only the public methods that return a string.")]

<span data-ttu-id="2dcfb-191">이름 속성만을 선택하고, 오버로드를 제거하여 고유 이름만을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-191">Select only the name property, and only distinct names by removing any overloads:</span></span>

[!code-csharp[find the distinct names.](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#12 "Use the string literal to access the semantic information in the string type.")]

<span data-ttu-id="2dcfb-192">LINQ 쿼리 구문을 사용하여 전체 쿼리를 빌드한 다음, 콘솔에서 모든 메서드 이름을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-192">You can also build the full query using the LINQ query syntax, and then display all the method names in  the console:</span></span>

[!code-csharp[build and display the results of this query.](../../../../samples/csharp/roslyn-sdk/SemanticQuickStart/Program.cs#12 "Build and display the results of the query.")]

<span data-ttu-id="2dcfb-193">프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-193">Build and run the program.</span></span> <span data-ttu-id="2dcfb-194">다음과 같은 내용이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-194">You should see the following output:</span></span>

```
Join
Substring
Trim
TrimStart
TrimEnd
Normalize
PadLeft
PadRight
ToLower
ToLowerInvariant
ToUpper
ToUpperInvariant
ToString
Insert
Replace
Remove
Format
Copy
Concat
Intern
IsInterned
Press any key to continue . . .
```
<span data-ttu-id="2dcfb-195">이 프로그램의 일부인 기호에 대한 정보를 찾고 표시하기 위해 의미 체계 API를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="2dcfb-195">You've used the Semantic API to find and display information about the symbols that are part of this program.</span></span>
