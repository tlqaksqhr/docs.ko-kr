---
title: "동적 메서드 및 어셈블리 생성"
ms.custom: 
ms.date: 08/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 91b0cc4614834f2ad8f7b54d9364d484ca9a6990
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="emitting-dynamic-methods-and-assemblies"></a><span data-ttu-id="f585f-102">동적 메서드 및 어셈블리 생성</span><span class="sxs-lookup"><span data-stu-id="f585f-102">Emitting Dynamic Methods and Assemblies</span></span>
<span data-ttu-id="f585f-103">이 섹션에서는 컴파일러 또는 도구가 런타임에 메타데이터 및 MSIL(Microsoft Intermediate Language)을 내보내고 선택적으로 디스크에서 PE(이식 가능한 실행) 파일을 생성할 수 있게 해주는 <xref:System.Reflection.Emit> 네임스페이스의 관리되는 형식 집합을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-103">This section describes a set of managed types in the <xref:System.Reflection.Emit> namespace that allow a compiler or tool to emit metadata and Microsoft intermediate language (MSIL) at run time and optionally generate a portable executable (PE) file on disk.</span></span> <span data-ttu-id="f585f-104">스크립트 엔진과 컴파일러는 이 네임스페이스의 주 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-104">Script engines and compilers are the primary users of this namespace.</span></span> <span data-ttu-id="f585f-105">이 섹션에서는 <xref:System.Reflection.Emit> 네임스페이스에서 제공하는 기능을 리플렉션 내보내기라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-105">In this section, the functionality provided by the <xref:System.Reflection.Emit> namespace is referred to as reflection emit.</span></span>  
  
 <span data-ttu-id="f585f-106">리플렉션 내보내기는 다음 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-106">Reflection emit provides the following capabilities:</span></span>  
  
-   <span data-ttu-id="f585f-107">런타임에 <xref:System.Reflection.Emit.DynamicMethod> 클래스를 사용하여 간단한 전역 메서드를 정의하고 대리자를 사용하여 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-107">Define lightweight global methods at run time, using the <xref:System.Reflection.Emit.DynamicMethod> class, and execute them using delegates.</span></span>  
  
-   <span data-ttu-id="f585f-108">런타임에 어셈블리를 정의하고 실행하거나 디스크에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-108">Define assemblies at run time and then run them and/or save them to disk.</span></span>  
  
-   <span data-ttu-id="f585f-109">런타임에 어셈블리를 정의하고 실행한 다음 언로드하고 가비지 수집에서 해당 리소스를 회수할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-109">Define assemblies at run time, run them, and then unload them and allow garbage collection to reclaim their resources.</span></span>  
  
-   <span data-ttu-id="f585f-110">런타임에 새 어셈블리에서 모듈을 정의하고 실행하거나 디스크에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-110">Define modules in new assemblies at run time and then run and/or save them to disk.</span></span>  
  
-   <span data-ttu-id="f585f-111">런타임에 모듈에서 형식을 정의하고 이러한 형식의 인스턴스를 만든 다음 해당 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-111">Define types in modules at run time, create instances of these types, and invoke their methods.</span></span>  
  
-   <span data-ttu-id="f585f-112">디버거 및 코드 프로파일러와 같은 도구에서 사용할 수 있는 정의된 모듈에 대한 기호 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-112">Define symbolic information for defined modules that can be used by tools such as debuggers and code profilers.</span></span>  
  
 <span data-ttu-id="f585f-113"><xref:System.Reflection.Emit> 네임스페이스의 관리되는 형식 외에도 [메타데이터 인터페이스](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) 참조 설명서에서 설명하는 관리되지 않는 메타데이터 인터페이스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-113">In addition to the managed types in the <xref:System.Reflection.Emit> namespace, there are unmanaged metadata interfaces which are described in the [Metadata Interfaces](../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) reference documentation.</span></span> <span data-ttu-id="f585f-114">관리되는 리플렉션 내보내기는 관리되지 않는 메타데이터 인터페이스 보다 강력한 의미 체계 오류 검사 및 높은 수준의 메타데이터 추상화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-114">Managed reflection emit provides stronger semantic error checking and a higher level of abstraction of the metadata than the unmanaged metadata interfaces.</span></span>  
  
 <span data-ttu-id="f585f-115">메타데이터 및 MSIL 작업을 위한 다른 유용한 리소스는 CLI(공용 언어 인프라) 설명서, 특히 "Partition II: Metadata Definition and Semantics" 및 "Partition III: CIL Instruction Set"입니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-115">Another useful resource for working with metadata and MSIL is the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="f585f-116">이 설명서는 [MSDN](http://go.microsoft.com/fwlink/?LinkID=65555) 및 [Ecma 웹 사이트](http://go.microsoft.com/fwlink/?LinkId=116487)에서 온라인으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-116">The documentation is available online on [MSDN](http://go.microsoft.com/fwlink/?LinkID=65555) and at the [Ecma Web site](http://go.microsoft.com/fwlink/?LinkId=116487).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f585f-117">단원 내용</span><span class="sxs-lookup"><span data-stu-id="f585f-117">In This Section</span></span>
  
[<span data-ttu-id="f585f-118">리플렉션 내보내기의 보안 문제점</span><span class="sxs-lookup"><span data-stu-id="f585f-118">Security issues in reflection emit</span></span>](../../../docs/framework/reflection-and-codedom/security-issues-in-reflection-emit.md)  
<span data-ttu-id="f585f-119">리플렉션 내보내기를 사용하여 동적 어셈블리를 만드는 경우와 관련된 보안 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-119">Describes security issues related to creating dynamic assemblies using reflection emit.</span></span>  

<span data-ttu-id="f585f-120">[방법: 정의 및 동적 메서드를 실행 합니다.](how-to-define-and-execute-dynamic-methods.md) </span><span class="sxs-lookup"><span data-stu-id="f585f-120">[How to: Define and execute dynamic methods](how-to-define-and-execute-dynamic-methods.md) </span></span>  
<span data-ttu-id="f585f-121">간단한 동적 메서드 및 클래스의 인스턴스에 바인딩되어 동적 메서드를 실행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-121">Shows how to execute a simple dynamic method and a dynamic method bound to an instance of a class.</span></span>

<span data-ttu-id="f585f-122">[방법: 리플렉션 사용 하 여 제네릭 형식 정의 내보내기](how-to-define-a-generic-type-with-reflection-emit.md) </span><span class="sxs-lookup"><span data-stu-id="f585f-122">[How to: Define a generic type with reflection emit](how-to-define-a-generic-type-with-reflection-emit.md) </span></span>  
<span data-ttu-id="f585f-123">간단한 제네릭 형식을 두 형식 매개 변수를 만드는 방법, 형식 매개 변수에 클래스, 인터페이스 및 특수 제약 조건을 적용 하는 방법 및 만드는 memers 반환 형식 및 매개 변수 형식으로 클래스의 형식 매개 변수를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-123">Shows how to create a simple generic type with two type parameters, how to apply class, interface, and special constraints to the type parameters, and how to create memers that use the type parameters of the class as parameter types and return types.</span></span>

<span data-ttu-id="f585f-124">[방법: 리플렉션 사용 하 여 제네릭 메서드 정의 내보내기](how-to-define-a-generic-method-with-reflection-emit.md) </span><span class="sxs-lookup"><span data-stu-id="f585f-124">[How to: Define a generic method with reflection emit](how-to-define-a-generic-method-with-reflection-emit.md) </span></span>  
<span data-ttu-id="f585f-125">만들기, 내보내기 및 간단한 제네릭 메서드를 호출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-125">Shows how to create, emit, and invoke a simple generic method.</span></span>

<span data-ttu-id="f585f-126">[수집 가능한 어셈블리 동적 형식 생성](collectible-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="f585f-126">[Collectible assemblies for dynamic type generation](collectible-assemblies.md) </span></span>  
<span data-ttu-id="f585f-127">언로드할 수는 만든 응용 프로그램 도메인을 언로드하지 않고는 동적 어셈블리는 수집 가능한 어셈블리를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-127">Introduces collectible assemblies, which are dynamic assemblies that can be unloaded without unloading the application domain in which they were created.</span></span>
  
## <a name="reference"></a><span data-ttu-id="f585f-128">참조</span><span class="sxs-lookup"><span data-stu-id="f585f-128">Reference</span></span>  
 <xref:System.Reflection.Emit.OpCodes>  
 <span data-ttu-id="f585f-129">메서드 본문을 작성하는 데 사용할 수 있는 MSIL 명령 코드의 카탈로그를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-129">Catalogs the MSIL instruction codes you can use to build method bodies.</span></span>  
  
 <xref:System.Reflection.Emit>  
 <span data-ttu-id="f585f-130">동적 메서드, 어셈블리 및 형식을 내보내는 데 사용되는 관리되는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-130">Contains managed classes used to emit dynamic methods, assemblies, and types.</span></span>  
  
 <xref:System.Type>  
 <span data-ttu-id="f585f-131">관리되는 리플렉션 및 리플렉션 내보내기에서 형식을 나타내며 이러한 기술 사용의 핵심 요소인 <xref:System.Type> 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-131">Describes the <xref:System.Type> class, which represents types in managed reflection and reflection emit, and which is key to the use of these technologies.</span></span>  
  
 <xref:System.Reflection>  
 <span data-ttu-id="f585f-132">메타데이터와 관리 코드를 탐색하는 데 사용되는 관리되는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-132">Contains managed classes used to explore metadata and managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f585f-133">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f585f-133">Related Sections</span></span>  
 [<span data-ttu-id="f585f-134">리플렉션</span><span class="sxs-lookup"><span data-stu-id="f585f-134">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 <span data-ttu-id="f585f-135">메타데이터와 관리 코드를 탐색하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-135">Explains how to explore metadata and managed code.</span></span>  
  
 [<span data-ttu-id="f585f-136">공용 언어 런타임의 어셈블리</span><span class="sxs-lookup"><span data-stu-id="f585f-136">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 <span data-ttu-id="f585f-137">어셈블리.NET 구현에 대 한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f585f-137">Provides an overview of assemblies in .NET implementations.</span></span>
