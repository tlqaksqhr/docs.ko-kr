---
title: 동적 소스 코드 생성 및 컴파일
ms.date: 03/30/2017
helpviewer_keywords:
- Code Document Object Model
- System.CodeDom namespace
- language-independent source code modeling
- CodeDOM
- multiple languages supported by CodeDOM
- source code in multiple languages
- languages, multiple language support by CodeDOM
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41a3f729a6be1cf9e803af306d1d6015f0afbdc3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="dynamic-source-code-generation-and-compilation"></a><span data-ttu-id="7906c-102">동적 소스 코드 생성 및 컴파일</span><span class="sxs-lookup"><span data-stu-id="7906c-102">Dynamic Source Code Generation and Compilation</span></span>
<span data-ttu-id="7906c-103">.NET Framework에는 소스 코드를 내보내는 프로그램 개발자가 렌더링할 코드를 나타내는 단일 모델을 기반으로 런타임에 여러 가지 프로그래밍 언어로 소스 코드를 생성할 수 있는 CodeDOM(코드 문서 개체 모델) 메커니즘이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7906c-103">The .NET Framework includes a mechanism called the Code Document Object Model (CodeDOM) that enables developers of programs that emit source code to generate source code in multiple programming languages at run time, based on a single model that represents the code to render.</span></span>  
  
 <span data-ttu-id="7906c-104">소스 코드를 나타내기 위해 CodeDOM 요소는 서로 연결되어 일부 소스 코드의 구조를 모델링하는 CodeDOM 그래프라는 데이터 구조를 형성합니다.</span><span class="sxs-lookup"><span data-stu-id="7906c-104">To represent source code, CodeDOM elements are linked to each other to form a data structure known as a CodeDOM graph, which models the structure of some source code.</span></span>  
  
 <span data-ttu-id="7906c-105">`System.CodeDom` 네임스페이스는 특정 프로그래밍 언어에 관계없이 소스 코드의 논리 구조를 나타낼 수 있는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7906c-105">The `System.CodeDom` namespace defines types that can represent the logical structure of source code, independent of a specific programming language.</span></span> <span data-ttu-id="7906c-106">`System.CodeDom.Compiler` 네임스페이스는 CodeDOM 그래프에서 소스 코드를 생성하고 지원되는 언어로 소스 코드의 컴파일을 관리하기 위한 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7906c-106">The `System.CodeDom.Compiler` namespace defines types for generating source code from CodeDOM graphs and managing the compilation of source code in supported languages.</span></span> <span data-ttu-id="7906c-107">컴파일러 공급업체나 개발자는 지원되는 언어 집합을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7906c-107">Compiler vendors or developers can extend the set of supported languages.</span></span>  
  
 <span data-ttu-id="7906c-108">프로그램이 프로그램 모델에 대한 소스 코드를 여러 언어로 또는 확실하지 않은 대상 언어로 생성해야 하는 경우 언어 독립적 소스 코드 모델링이 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7906c-108">Language-independent source code modeling can be valuable when a program needs to generate source code for a program model in multiple languages or for an uncertain target language.</span></span> <span data-ttu-id="7906c-109">예를 들어 CodeDOM이 해당 언어를 지원하는 경우 일부 디자이너는 CodeDOM을 언어 추상 인터페이스로 사용하여 소스 코드를 올바른 프로그래밍 언어로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7906c-109">For example, some designers use the CodeDOM as a language abstraction interface to produce source code in the correct programming language, if CodeDOM support for the language is available.</span></span>  
  
 <span data-ttu-id="7906c-110">.NET Framework에는 <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider> 및 <xref:Microsoft.VisualBasic.VBCodeProvider>에 대한 코드 생성기 및 코드 컴파일러가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7906c-110">The .NET Framework includes code generators and code compilers for <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider>, and <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7906c-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="7906c-111">In This Section</span></span>  
 [<span data-ttu-id="7906c-112">CodeDOM 사용</span><span class="sxs-lookup"><span data-stu-id="7906c-112">Using the CodeDOM</span></span>](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)  
 <span data-ttu-id="7906c-113">일반적인 용도를 설명하고 CodeDOM을 사용하여 간단한 개체 그래프를 빌드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7906c-113">Describes common uses, and demonstrates building a simple object graph using the CodeDOM.</span></span>  
  
 [<span data-ttu-id="7906c-114">CodeDOM 그래프에서 소스 코드 생성 및 프로그램 컴파일</span><span class="sxs-lookup"><span data-stu-id="7906c-114">Generating Source Code and Compiling a Program from a CodeDOM Graph</span></span>](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)  
 <span data-ttu-id="7906c-115">소스 코드를 생성하고 `System.CodeDom.Compiler` 네임스페이스에 설명된 클래스를 사용하여 외부 컴파일러를 통해 생성된 코드를 컴파일하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7906c-115">Describes how to generate source code and compile the generated code with an external compiler using classes defined in the `System.CodeDom.Compiler` namespace.</span></span>  
  
 [<span data-ttu-id="7906c-116">방법: CodeDOM을 사용하여 XML 문서 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="7906c-116">How to: Create an XML Documentation File Using CodeDOM</span></span>](../../../docs/framework/reflection-and-codedom/how-to-create-an-xml-documentation-file-using-codedom.md)  
 <span data-ttu-id="7906c-117">CodeDOM을 사용하여 XML 문서 주석이 포함된 코드를 생성하고 XML 문서 출력을 만들도록 생성된 코드를 컴파일하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7906c-117">Describes how to use CodeDOM to generate code with XML documentation comments, and compile the generated code so that it creates the XML documentation output.</span></span>  
  
 [<span data-ttu-id="7906c-118">방법: CodeDOM을 사용하여 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="7906c-118">How to: Create a Class Using CodeDOM</span></span>](../../../docs/framework/reflection-and-codedom/how-to-create-a-class-using-codedom.md)  
 <span data-ttu-id="7906c-119">CodeDOM을 사용하여 필드, 속성, 메서드, 생성자, 진입점이 포함된 클래스를 생성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7906c-119">Describes how to use CodeDOM to generate a class containing fields, properties, a method, a constructor, and an entry point.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7906c-120">참조</span><span class="sxs-lookup"><span data-stu-id="7906c-120">Reference</span></span>  
 <xref:System.CodeDom>  
 <span data-ttu-id="7906c-121">공용 언어 런타임을 대상으로 하는 프로그래밍 언어로 코드 요소를 나타내는 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7906c-121">Defines elements that represent code elements in programming languages that target the common language runtime.</span></span>  
  
 <xref:System.CodeDom.Compiler>  
 <span data-ttu-id="7906c-122">런타임에 코드를 생성 및 컴파일하기 위한 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7906c-122">Defines interfaces for generating and compiling code at run time.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7906c-123">관련 단원</span><span class="sxs-lookup"><span data-stu-id="7906c-123">Related Sections</span></span>  
 [<span data-ttu-id="7906c-124">CodeDOM 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="7906c-124">CodeDOM Quick Reference</span></span>](http://msdn.microsoft.com/library/c77b8bfd-0a32-4e36-b59a-4f687f32c524)  
 <span data-ttu-id="7906c-125">개발자가 소스 코드 요소를 나타내는 CodeDOM 요소를 빠르게 찾을 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7906c-125">Provides a quick way for developers to find the CodeDOM elements that represent source code elements.</span></span>
