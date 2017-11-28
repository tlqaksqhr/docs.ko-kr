---
title: "CodeDOM 그래프에서 소스 코드 생성 및 컴파일"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- code compilers
- CodeDOM, generating source code
- Code Document Object Model, graphs
- templated code generation
- source code, generating
- dynamically representing source code
- generating CodeDOM graphs
- Code Document Object Model, generating source code
- translating language to language
- compiling assemblies
- generating source code in multiple languages
- graphing with CodeDOM
- dynamic compilation
- assemblies [.NET Framework], CodeDOM
- source code generation
- outputting source code by CodeDOM
- code generators
- compiling source code, multiple languages
- CodeDOM, graphs
ms.assetid: 6c864c8e-6dd3-4a65-ace0-36879d9a9c42
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 55ba7c1b9dd7e8c912903fb9827e0073a8329abb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="generating-and-compiling-source-code-from-a-codedom-graph"></a><span data-ttu-id="54d64-102">CodeDOM 그래프에서 소스 코드 생성 및 컴파일</span><span class="sxs-lookup"><span data-stu-id="54d64-102">Generating and Compiling Source Code from a CodeDOM Graph</span></span>
<span data-ttu-id="54d64-103"><xref:System.CodeDom.Compiler> 네임스페이스는 CodeDOM 개체 그래프에서 소스 코드를 생성하고 지원되는 컴파일러를 통한 컴파일을 관리하기 위한 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-103">The <xref:System.CodeDom.Compiler> namespace provides interfaces for generating source code from CodeDOM object graphs and for managing compilation with supported compilers.</span></span> <span data-ttu-id="54d64-104">코드 공급자는 CodeDOM 그래프에 따라 특정 프로그래밍 언어로 소스 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-104">A code provider can produce source code in a particular programming language according to a CodeDOM graph.</span></span> <span data-ttu-id="54d64-105"><xref:System.CodeDom.Compiler.CodeDomProvider>에서 파생되는 클래스는 일반적으로 공급자가 지원하는 언어의 코드를 생성 및 컴파일하기 위한 메서드를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-105">A class that derives from <xref:System.CodeDom.Compiler.CodeDomProvider> can typically provide methods for generating and compiling code for the language the provider supports.</span></span>  
  
## <a name="using-a-codedom-code-provider-to-generate-source-code"></a><span data-ttu-id="54d64-106">CodeDOM 코드 공급자를 사용하여 소스 코드 생성</span><span class="sxs-lookup"><span data-stu-id="54d64-106">Using a CodeDOM code provider to generate source code</span></span>  
 <span data-ttu-id="54d64-107">특정 언어로 소스 코드를 생성하려면 생성할 소스 코드의 구조를 나타내는 CodeDOM 그래프가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-107">To generate source code in a particular language, you need a CodeDOM graph that represents the structure of the source code to generate.</span></span>  
  
 <span data-ttu-id="54d64-108">다음 예제에서는 <xref:Microsoft.CSharp.CSharpCodeProvider> 인스턴스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-108">The following example demonstrate how to create an instance of a <xref:Microsoft.CSharp.CSharpCodeProvider>:</span></span>  
  
 [!code-cpp[CodeDomExample#21](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#21)]
 [!code-csharp[CodeDomExample#21](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#21)]
 [!code-vb[CodeDomExample#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#21)]  
  
 <span data-ttu-id="54d64-109">코드 생성 그래프는 일반적으로 <xref:System.CodeDom.CodeCompileUnit>에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-109">The graph for code generation is typically contained in a <xref:System.CodeDom.CodeCompileUnit>.</span></span> <span data-ttu-id="54d64-110">CodeDOM 그래프를 포함하는 **CodeCompileUnit**에 대한 코드를 생성하려면 코드 공급자의 <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-110">To generate code for a **CodeCompileUnit** that contains a CodeDOM graph, call the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method of the code provider.</span></span> <span data-ttu-id="54d64-111">이 메서드에는 소스 코드를 생성하는 데 사용하는 <xref:System.IO.TextWriter>에 대한 매개 변수가 있으므로 먼저 쓸 수 있는 **TextWriter**를 만들어야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-111">This method has a parameter for a <xref:System.IO.TextWriter> that it uses to generate the source code, so it is sometimes necessary to first create a **TextWriter** that can be written to.</span></span> <span data-ttu-id="54d64-112">다음 예제에서는 **CodeCompileUnit**에서 코드를 생성하고 생성된 소스 코드를 HelloWorld.cs라는 파일에 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-112">The following example demonstrates generating code from a **CodeCompileUnit** and writing the generated source code to a file named HelloWorld.cs.</span></span>  
  
 [!code-cpp[CodeDomExample#22](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#22)]
 [!code-csharp[CodeDomExample#22](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#22)]
 [!code-vb[CodeDomExample#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#22)]  
  
## <a name="using-a-codedom-code-provider-to-compile-assemblies"></a><span data-ttu-id="54d64-113">CodeDOM 코드 공급자를 사용하여 어셈블리 컴파일</span><span class="sxs-lookup"><span data-stu-id="54d64-113">Using a CodeDOM code provider to compile assemblies</span></span>  
 <span data-ttu-id="54d64-114">**컴파일 호출**</span><span class="sxs-lookup"><span data-stu-id="54d64-114">**Invoking compilation**</span></span>  
  
 <span data-ttu-id="54d64-115">CodeDom 공급자를 사용하여 어셈블리를 컴파일하려면 컴파일러가 있는 언어로 컴파일할 소스 코드나 컴파일할 소스 코드를 생성할 수 있는 CodeDOM 그래프가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-115">To compile an assembly using a CodeDom provider, you must have either source code to compile in a language for which you have a compiler, or a CodeDOM graph that source code to compile can be generated from.</span></span>  
  
 <span data-ttu-id="54d64-116">CodeDOM 그래프에서 컴파일하는 경우 그래프를 포함하는 <xref:System.CodeDom.CodeCompileUnit>을 코드 공급자의 <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A> 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-116">If you are compiling from a CodeDOM graph, pass the <xref:System.CodeDom.CodeCompileUnit> containing the graph to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A> method of the code provider.</span></span> <span data-ttu-id="54d64-117">컴파일러가 이해할 수 있는 언어의 소스 코드 파일이 있는 경우 소스 코드를 포함하는 파일의 이름을 CodeDom 공급자의 <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-117">If you have a source code file in a language that the compiler understands, pass the name of the file containing the source code to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> method of the CodeDom provider.</span></span> <span data-ttu-id="54d64-118">컴파일러가 이해할 수 있는 언어의 소스 코드를 포함하는 문자열을 CodeDom 공급자의 <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A> 메서드에 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-118">You can also pass a string containing source code in a language that the compiler understands to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A> method of the CodeDom provider.</span></span>  
  
 <span data-ttu-id="54d64-119">**컴파일 매개 변수 구성**</span><span class="sxs-lookup"><span data-stu-id="54d64-119">**Configuring compilation parameters**</span></span>  
  
 <span data-ttu-id="54d64-120">CodeDom 공급자의 모든 표준 컴파일 호출 메서드에는 컴파일에 사용할 옵션을 나타내는 <xref:System.CodeDom.Compiler.CompilerParameters> 형식의 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-120">All of the standard compilation-invoking methods of a CodeDom provider have a parameter of type <xref:System.CodeDom.Compiler.CompilerParameters> that indicates the options to use for compilation.</span></span>  
  
 <span data-ttu-id="54d64-121">**CompilerParameters**의 <xref:System.CodeDom.Compiler.CompilerParameters.OutputAssembly%2A> 속성에 출력 어셈블리에 대한 파일 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-121">You can specify a file name for the output assembly in the <xref:System.CodeDom.Compiler.CompilerParameters.OutputAssembly%2A> property of the **CompilerParameters**.</span></span> <span data-ttu-id="54d64-122">지정하지 않으면 기본 출력 파일 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-122">Otherwise, a default output file name will be used.</span></span>  
  
 <span data-ttu-id="54d64-123">기본적으로 새 **CompilerParameters**는 <xref:System.CodeDom.Compiler.CompilerParameters.GenerateExecutable%2A> 속성을 **false**로 설정하여 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-123">By default, a new **CompilerParameters** is initialized with its <xref:System.CodeDom.Compiler.CompilerParameters.GenerateExecutable%2A> property set to **false**.</span></span> <span data-ttu-id="54d64-124">실행 프로그램을 컴파일하는 경우 **GenerateExecutable** 속성을 **true**로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-124">If you are compiling an executable program, you must set the **GenerateExecutable** property to **true**.</span></span> <span data-ttu-id="54d64-125">**GenerateExecutable**이 **false**로 설정된 경우 컴파일러에서 클래스 라이브러리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-125">When the **GenerateExecutable** is set to **false**, the compiler will generate a class library.</span></span>  
  
 <span data-ttu-id="54d64-126">CodeDOM 그래프에서 실행 파일을 컴파일하는 경우 <xref:System.CodeDom.CodeEntryPointMethod>가 그래프에 정의되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-126">If you are compiling an executable from a CodeDOM graph, a <xref:System.CodeDom.CodeEntryPointMethod> must be defined in the graph.</span></span> <span data-ttu-id="54d64-127">코드 진입점이 여러 개 있을 경우 사용할 진입점을 정의하는 클래스의 이름으로 **CompilerParameters**의 <xref:System.CodeDom.Compiler.CompilerParameters.MainClass%2A> 속성을 설정해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-127">If there are multiple code entry points, it may be necessary to set the <xref:System.CodeDom.Compiler.CompilerParameters.MainClass%2A> property of the **CompilerParameters** to the name of the class that defines the entry point to use.</span></span>  
  
 <span data-ttu-id="54d64-128">생성된 실행 파일에 디버그 정보를 포함하려면 <xref:System.CodeDom.Compiler.CompilerParameters.IncludeDebugInformation%2A> 속성을 **true**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-128">To include debug information in a generated executable, set the <xref:System.CodeDom.Compiler.CompilerParameters.IncludeDebugInformation%2A> property to **true**.</span></span>  
  
 <span data-ttu-id="54d64-129">프로젝트가 어셈블리를 참조하는 경우 컴파일을 호출할 때 사용하는 **CompilerParameters**의 <xref:System.CodeDom.Compiler.CompilerParameters.ReferencedAssemblies%2A> 속성으로 <xref:System.Collections.Specialized.StringCollection>의 항목인 어셈블리 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-129">If your project references any assemblies, you must specify the assembly names as items in a <xref:System.Collections.Specialized.StringCollection> as the <xref:System.CodeDom.Compiler.CompilerParameters.ReferencedAssemblies%2A> property of the **CompilerParameters** you use when invoking compilation.</span></span>  
  
 <span data-ttu-id="54d64-130"><xref:System.CodeDom.Compiler.CompilerParameters.GenerateInMemory%2A> 속성을 **true**로 설정하면 디스크가 아니라 메모리에 기록되는 어셈블리를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-130">You can compile an assembly that is written to memory rather than disk by setting the <xref:System.CodeDom.Compiler.CompilerParameters.GenerateInMemory%2A> property to **true**.</span></span> <span data-ttu-id="54d64-131">어셈블리가 메모리에 생성되면 코드에서 <xref:System.CodeDom.Compiler.CompilerResults>의 <xref:System.CodeDom.Compiler.CompilerResults.CompiledAssembly%2A> 속성을 통해 생성된 어셈블리에 대한 참조를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-131">When an assembly is generated in memory, your code can obtain a reference to the generated assembly from the <xref:System.CodeDom.Compiler.CompilerResults.CompiledAssembly%2A> property of a <xref:System.CodeDom.Compiler.CompilerResults>.</span></span> <span data-ttu-id="54d64-132">어셈블리가 디스크에 기록되는 경우 **CompilerResults**의 <xref:System.CodeDom.Compiler.CompilerResults.PathToAssembly%2A> 속성에서 생성된 어셈블리의 경로를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-132">If an assembly is written to disk, you can obtain the path to the generated assembly from the <xref:System.CodeDom.Compiler.CompilerResults.PathToAssembly%2A> property of a **CompilerResults**.</span></span>  
  
 <span data-ttu-id="54d64-133">컴파일 프로세스를 호출할 때 사용할 사용자 지정 명령줄 인수 문자열을 지정하려면 <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> 속성에 문자열을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-133">To specify a custom command-line arguments string to use when invoking the compilation process, set the string in the <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> property.</span></span>  
  
 <span data-ttu-id="54d64-134">컴파일러 프로세스를 호출하는 데 Win32 보안 토큰이 필요한 경우 <xref:System.CodeDom.Compiler.CompilerParameters.UserToken%2A> 속성에 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-134">If a Win32 security token is required to invoke the compiler process, specify the token in the <xref:System.CodeDom.Compiler.CompilerParameters.UserToken%2A> property.</span></span>  
  
 <span data-ttu-id="54d64-135">Win32 리소스 파일을 컴파일된 어셈블리에 연결하려면 <xref:System.CodeDom.Compiler.CompilerParameters.Win32Resource%2A> 속성에서 Win32 리소스 파일의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-135">To link a Win32 resource file into the compiled assembly, specify the name of the Win32 resource file in the <xref:System.CodeDom.Compiler.CompilerParameters.Win32Resource%2A> property.</span></span>  
  
 <span data-ttu-id="54d64-136">컴파일을 중단할 경고 수준을 지정하려면 컴파일을 중단할 경고 수준을 나타내는 정수로 <xref:System.CodeDom.Compiler.CompilerParameters.WarningLevel%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-136">To specify a warning level at which to halt compilation, set the <xref:System.CodeDom.Compiler.CompilerParameters.WarningLevel%2A> property to an integer that represents the warning level at which to halt compilation.</span></span> <span data-ttu-id="54d64-137"><xref:System.CodeDom.Compiler.CompilerParameters.TreatWarningsAsErrors%2A> 속성을 **true**로 설정하여 경고가 발생할 경우 컴파일을 중단하도록 컴파일러를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-137">You can also configure the compiler to halt compilation if warnings are encountered by setting the <xref:System.CodeDom.Compiler.CompilerParameters.TreatWarningsAsErrors%2A> property to **true**.</span></span>  
  
 <span data-ttu-id="54d64-138">다음 코드 예제에서는 <xref:System.CodeDom.Compiler.CodeDomProvider> 클래스에서 파생된 CodeDom 공급자를 사용하여 소스 파일을 컴파일하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-138">The following code example demonstrates compiling a source file using a CodeDom provider derived from the <xref:System.CodeDom.Compiler.CodeDomProvider> class.</span></span>  
  
 [!code-cpp[CodeDomExample#23](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#23)]
 [!code-csharp[CodeDomExample#23](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#23)]
 [!code-vb[CodeDomExample#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#23)]  
  
## <a name="languages-with-initial-support"></a><span data-ttu-id="54d64-139">초기 지원 상태의 언어</span><span class="sxs-lookup"><span data-stu-id="54d64-139">Languages with Initial Support</span></span>  
 <span data-ttu-id="54d64-140">.NET Framework에서는 C#, Visual Basic, C++, JScript 언어에 대한 코드 컴파일러 및 코드 생성기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-140">The .NET Framework provides code compilers and code generators for the following languages: C#, Visual Basic, C++, and JScript.</span></span> <span data-ttu-id="54d64-141">언어별 코드 생성기 및 코드 컴파일러를 구현하면 CodeDOM 지원을 다른 언어로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54d64-141">CodeDOM support can be extended to other languages by implementing language-specific code generators and code compilers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54d64-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54d64-142">See Also</span></span>  
 <xref:System.CodeDom>  
 <xref:System.CodeDom.Compiler>  
 [<span data-ttu-id="54d64-143">동적 소스 코드 생성 및 컴파일</span><span class="sxs-lookup"><span data-stu-id="54d64-143">Dynamic Source Code Generation and Compilation</span></span>](../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)  
 [<span data-ttu-id="54d64-144">CodeDOM 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="54d64-144">CodeDOM Quick Reference</span></span>](http://msdn.microsoft.com/en-us/c77b8bfd-0a32-4e36-b59a-4f687f32c524)
