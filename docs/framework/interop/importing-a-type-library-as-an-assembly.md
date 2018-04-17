---
title: 형식 라이브러리를 어셈블리로 가져오기
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing type library
- type metadata
- custom wrappers
- metadata
- exposing COM components to .NET Framework
- Type Library Importer
- interoperation with unmanaged code, importing type library
- interoperation with unmanaged code, exposing COM components
- type libraries
- TypeLibConverter class, importing type library as assembly
- COM interop, importing type library
- COM interop, exposing COM components
ms.assetid: d1898229-cd40-426e-a275-f3eb65fbc79f
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0299ef58d58318714b8f0eb8082928f8da565d2f
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="importing-a-type-library-as-an-assembly"></a><span data-ttu-id="b6dee-102">형식 라이브러리를 어셈블리로 가져오기</span><span class="sxs-lookup"><span data-stu-id="b6dee-102">Importing a Type Library as an Assembly</span></span>
<span data-ttu-id="b6dee-103">COM 형식 정의는 일반적으로 형식 라이브러리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-103">COM type definitions usually reside in a type library.</span></span> <span data-ttu-id="b6dee-104">반면 CLS 규격 컴파일러는 어셈블리에서 형식 메타데이터를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-104">In contrast, CLS-compliant compilers produce type metadata in an assembly.</span></span> <span data-ttu-id="b6dee-105">형식 정보의 두 가지 소스는 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-105">The two sources of type information are quite different.</span></span> <span data-ttu-id="b6dee-106">이 항목에서는 형식 라이브러리에서 메타데이터를 생성하기 위한 기술을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-106">This topic describes techniques for generating metadata from a type library.</span></span> <span data-ttu-id="b6dee-107">결과 어셈블리를 interop 어셈블리라고 하고 포함된 형식 정보를 통해 .NET Framework 응용 프로그램이 COM 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-107">The resulting assembly is called an interop assembly, and the type information it contains enables .NET Framework applications to use COM types.</span></span>  
  
 <span data-ttu-id="b6dee-108">이 형식 정보를 응용 프로그램에서 사용할 수 있도록 설정하는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-108">There are two ways to make this type information available to your application:</span></span>  
  
-   <span data-ttu-id="b6dee-109">디자인 타임 전용 interop 사용: [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터 interop 어셈블리의 형식 정보를 실행 파일에 포함하도록 컴파일러에 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-109">Using design-time-only interop assemblies: Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can instruct the compiler to embed type information from the interop assembly into your executable.</span></span> <span data-ttu-id="b6dee-110">컴파일러는 응용 프로그램에서 사용하는 형식 정보만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-110">The compiler embeds only the type information that your application uses.</span></span> <span data-ttu-id="b6dee-111">Interop 어셈블리를 응용 프로그램에 배포할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-111">You do not have to deploy the interop assembly with your application.</span></span> <span data-ttu-id="b6dee-112">이것이 권장되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-112">This is the recommended technique.</span></span>  
  
-   <span data-ttu-id="b6dee-113">Interop 어셈블리 배포: interop 어셈블리에 대한 표준 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-113">Deploying interop assemblies: You can create a standard reference to the interop assembly.</span></span> <span data-ttu-id="b6dee-114">이 경우 interop 어셈블리를 응용 프로그램에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-114">In this case, the interop assembly must be deployed with your application.</span></span> <span data-ttu-id="b6dee-115">이 방법을 적용하는데 전용 COM 구성 요소를 사용하지 않을 경우 관리 코드에 통합하려는 COM 구성 요소의 작성자가 게시한 PIA(주 interop 어셈블리)를 항상 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6dee-115">If you employ this technique, and you are not using a private COM component, always reference the primary interop assembly (PIA) published by the author of the COM component you intend to incorporate in your managed code.</span></span> <span data-ttu-id="b6dee-116">주 interop 어셈블리를 생성 및 사용하는 방법에 대한 자세한 내용은 [주 Interop 어셈블리](https://msdn.microsoft.com/library/b977a8be-59a0-40a0-a806-b11ffba5c080(v=vs.100))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6dee-116">For more information about producing and using primary interop assemblies, see [Primary Interop Assemblies](https://msdn.microsoft.com/library/b977a8be-59a0-40a0-a806-b11ffba5c080(v=vs.100)).</span></span>  
  
 <span data-ttu-id="b6dee-117">디자인 타임 전용 interop 어셈블리를 사용할 경우 COM 구성 요소의 작성자가 게시한 주 interop 어셈블리의 형식 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-117">When you use design-time-only interop assemblies, you can embed type information from the primary interop assembly published by the author of the COM component.</span></span> <span data-ttu-id="b6dee-118">그러나 주 interop 어셈블리를 응용 프로그램에 배포할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-118">However, you do not have to deploy the primary interop assembly with your application.</span></span>  
  
 <span data-ttu-id="b6dee-119">대부분의 응용 프로그램에서는 COM 구성 요소의 일부 기능을 사용하지 않으므로 디자인 타임 전용 interop 어셈블리를 사용하면 응용 프로그램 크기가 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-119">Using design-time-only interop assemblies reduces the size of your application, because most applications do not use all the features of a COM component.</span></span> <span data-ttu-id="b6dee-120">컴파일러가 형식 정보를 포함하면 매우 효율적으로 작동합니다. 응용 프로그램이 COM 인터페이스에서 일부 메서드만 사용할 경우 컴파일러는 사용되지 않는 메서드를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-120">The compiler is very efficient when it embeds type information; if your application uses only some of the methods on a COM interface, the compiler does not embed the unused methods.</span></span> <span data-ttu-id="b6dee-121">형식 정보가 포함된 응용 프로그램이 이와 같은 다른 응용 프로그램과 상호 작용하거나 주 interop 어셈블리를 사용하는 응용 프로그램과 상호 작용하면 공용 언어 런타임은 형식 동등성 규칙을 사용하여 같은 이름의 두 가지 형식이 동일한 COM 형식을 나타내는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-121">When an application that has embedded type information interacts with another such application, or interacts with an application that uses a primary interop assembly, the common language runtime uses type equivalence rules to determine whether two types with the same name represent the same COM type.</span></span> <span data-ttu-id="b6dee-122">COM 개체를 사용하기 위해 이러한 규칙을 알 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-122">You do not have to know these rules to use COM objects.</span></span> <span data-ttu-id="b6dee-123">그러나 규칙에 관심이 있다면 [형식 동등성 및 포함된 Interop 형식](../../../docs/framework/interop/type-equivalence-and-embedded-interop-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6dee-123">However, if you are interested in the rules, see [Type Equivalence and Embedded Interop Types](../../../docs/framework/interop/type-equivalence-and-embedded-interop-types.md).</span></span>  
  
## <a name="generating-metadata"></a><span data-ttu-id="b6dee-124">메타데이터 생성</span><span class="sxs-lookup"><span data-stu-id="b6dee-124">Generating Metadata</span></span>  
 <span data-ttu-id="b6dee-125">COM 형식 라이브러리는 확장명이 .tlb인 독립 실행형 파일일 수 있습니다(예: Loanlib.tlb).</span><span class="sxs-lookup"><span data-stu-id="b6dee-125">COM type libraries can be stand-alone files that have a .tlb extension, such as Loanlib.tlb.</span></span> <span data-ttu-id="b6dee-126">일부 형식 라이브러리는 .dll 또는 .exe 파일의 리소스 섹션에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-126">Some type libraries are embedded in the resource section of a .dll or .exe file.</span></span> <span data-ttu-id="b6dee-127">형식 라이브러리 정보의 기타 소스는 .olb 및 .ocx 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-127">Other sources of type library information are .olb and .ocx files.</span></span>  
  
 <span data-ttu-id="b6dee-128">대상 COM 형식의 구현이 포함된 형식 라이브러리를 찾은 후 다음 옵션을 사용하여 형식 메타데이터가 포함된 interop 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-128">After you locate the type library that contains the implementation of your target COM type, you have the following options for generating an interop assembly containing type metadata:</span></span>  
  
-   <span data-ttu-id="b6dee-129">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b6dee-129">Visual Studio</span></span>  
  
     <span data-ttu-id="b6dee-130">Visual Studio는 형식 라이브러리의 COM 형식을 어셈블리의 메타데이터로 자동으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-130">Visual Studio automatically converts COM types in a type library to metadata in an assembly.</span></span> <span data-ttu-id="b6dee-131">자세한 내용은 [방법: 형식 라이브러리에 참조 추가](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md) 및 [연습: Microsoft Office 어셈블리의 형식 정보 포함](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6dee-131">For instructions, see [How to: Add References to Type Libraries](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md) and [Walkthrough: Embedding Type Information from Microsoft Office Assemblies](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100)).</span></span>  
  
-   [<span data-ttu-id="b6dee-132">형식 라이브러리 가져오기(Tlbimp.exe)</span><span class="sxs-lookup"><span data-stu-id="b6dee-132">Type Library Importer (Tlbimp.exe)</span></span>](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
  
     <span data-ttu-id="b6dee-133">형식 라이브러리 가져오기는 결과 interop 파일에서 메타데이터를 조정하고, 기존 형식 라이브러리에서 형식을 가져오고, interop 어셈블리 및 네임스페이스를 생성하기 위한 명령줄 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-133">The Type Library Importer provides command-line options to adjust metadata in the resulting interop file, imports types from an existing type library, and generates an interop assembly and a namespace.</span></span> <span data-ttu-id="b6dee-134">자세한 내용은 [방법: 형식 라이브러리에서 Interop 어셈블리 생성](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6dee-134">For instructions, see [How to: Generate Interop Assemblies from Type Libraries](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
-   <span data-ttu-id="b6dee-135"><xref:System.Runtime.InteropServices.TypeLibConverter?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="b6dee-135"><xref:System.Runtime.InteropServices.TypeLibConverter?displayProperty=nameWithType> class</span></span>  
  
     <span data-ttu-id="b6dee-136">이 클래스는 형식 라이브러리의 coclass 및 인터페이스를 어셈블리 내의 메타데이터로 변환하기 위한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-136">This class provides methods to convert coclasses and interfaces in a type library to metadata within an assembly.</span></span> <span data-ttu-id="b6dee-137">이 클래스는 Tlbimp.exe와 동일한 메타데이터 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-137">It produces the same metadata output as Tlbimp.exe.</span></span> <span data-ttu-id="b6dee-138">그러나 Tlbimp.exe와 달리 <xref:System.Runtime.InteropServices.TypeLibConverter> 클래스는 메모리 내 형식 라이브러리를 메타데이터로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-138">However, unlike Tlbimp.exe, the <xref:System.Runtime.InteropServices.TypeLibConverter> class can convert an in-memory type library to metadata.</span></span>  
  
-   <span data-ttu-id="b6dee-139">사용자 지정 래퍼</span><span class="sxs-lookup"><span data-stu-id="b6dee-139">Custom wrappers</span></span>  
  
     <span data-ttu-id="b6dee-140">형식 라이브러리가 사용 불가능하거나 잘못된 경우 한 가지 옵션은 관리 소스 코드에서 클래스 또는 인터페이스에 대한 중복 정의를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-140">When a type library is unavailable or incorrect, one option is to create a duplicate definition of the class or interface in managed source code.</span></span> <span data-ttu-id="b6dee-141">그런 다음 런타임을 대상으로 하는 컴파일러로 소스 코드를 컴파일하여 어셈블리에서 메타데이터를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-141">You then compile the source code with a compiler that targets the runtime to produce metadata in an assembly.</span></span>  
  
     <span data-ttu-id="b6dee-142">COM 형식을 수동으로 정의하려면 다음 항목에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-142">To define COM types manually, you must have access to the following items:</span></span>  
  
    -   <span data-ttu-id="b6dee-143">정의되는 coclass 및 인터페이스에 대한 자세한 설명.</span><span class="sxs-lookup"><span data-stu-id="b6dee-143">Precise descriptions of the coclasses and interfaces being defined.</span></span>  
  
    -   <span data-ttu-id="b6dee-144">해당하는 .NET Framework 클래스 정의를 생성할 수 있는 컴파일러(예: C# 컴파일러).</span><span class="sxs-lookup"><span data-stu-id="b6dee-144">A compiler, such as the C# compiler, that can generate the appropriate .NET Framework class definitions.</span></span>  
  
    -   <span data-ttu-id="b6dee-145">형식 라이브러리-어셈블리 변환 규칙에 대한 이해.</span><span class="sxs-lookup"><span data-stu-id="b6dee-145">Knowledge of the type library-to-assembly conversion rules.</span></span>  
  
     <span data-ttu-id="b6dee-146">사용자 지정 래퍼를 작성하는 것은 고급 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="b6dee-146">Writing a custom wrapper is an advanced technique.</span></span> <span data-ttu-id="b6dee-147">사용자 지정 래퍼를 생성하는 방법에 대한 자세한 내용은 [표준 래퍼 사용자 지정](https://msdn.microsoft.com/library/c40d089b-6a3c-41b5-a20d-d760c215e49d(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6dee-147">For additional information about how to generate a custom wrapper, see [Customizing Standard Wrappers](https://msdn.microsoft.com/library/c40d089b-6a3c-41b5-a20d-d760c215e49d(v=vs.100)).</span></span>  
  
 <span data-ttu-id="b6dee-148">COM interop 가져오기 프로세스에 대한 자세한 내용은 [형식 라이브러리를 어셈블리로 변환 요약](https://msdn.microsoft.com/library/bf3f90c5-4770-4ab8-895c-3ba1055cc958(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6dee-148">For more information about the COM interop import process, see [Type Library to Assembly Conversion Summary](https://msdn.microsoft.com/library/bf3f90c5-4770-4ab8-895c-3ba1055cc958(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6dee-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6dee-149">See Also</span></span>  
 <xref:System.Runtime.InteropServices.TypeLibConverter>  
 [<span data-ttu-id="b6dee-150">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="b6dee-150">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 <span data-ttu-id="b6dee-151">[형식 라이브러리를 어셈블리로 변환 요약](https://msdn.microsoft.com/library/bf3f90c5-4770-4ab8-895c-3ba1055cc958(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b6dee-151">[Type Library to Assembly Conversion Summary](https://msdn.microsoft.com/library/bf3f90c5-4770-4ab8-895c-3ba1055cc958(v=vs.100))</span></span>  
 [<span data-ttu-id="b6dee-152">Tlbimp.exe(형식 라이브러리 가져오기)</span><span class="sxs-lookup"><span data-stu-id="b6dee-152">Tlbimp.exe (Type Library Importer)</span></span>](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
 <span data-ttu-id="b6dee-153">[표준 래퍼 사용자 지정](https://msdn.microsoft.com/library/c40d089b-6a3c-41b5-a20d-d760c215e49d(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b6dee-153">[Customizing Standard Wrappers](https://msdn.microsoft.com/library/c40d089b-6a3c-41b5-a20d-d760c215e49d(v=vs.100))</span></span>  
 <span data-ttu-id="b6dee-154">[관리 코드에서 COM 형식을 사용 하 여](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b6dee-154">[Using COM Types in Managed Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))</span></span>  
 [<span data-ttu-id="b6dee-155">Interop 프로젝트 컴파일</span><span class="sxs-lookup"><span data-stu-id="b6dee-155">Compiling an Interop Project</span></span>](../../../docs/framework/interop/compiling-an-interop-project.md)  
 [<span data-ttu-id="b6dee-156">Interop 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="b6dee-156">Deploying an Interop Application</span></span>](../../../docs/framework/interop/deploying-an-interop-application.md)  
 [<span data-ttu-id="b6dee-157">방법: 형식 라이브러리에 참조 추가</span><span class="sxs-lookup"><span data-stu-id="b6dee-157">How to: Add References to Type Libraries</span></span>](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md)  
 [<span data-ttu-id="b6dee-158">방법: 형식 라이브러리에서 Interop 어셈블리 생성</span><span class="sxs-lookup"><span data-stu-id="b6dee-158">How to: Generate Interop Assemblies from Type Libraries</span></span>](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md)  
 <span data-ttu-id="b6dee-159">[연습: Microsoft Office 어셈블리의 형식 정보 포함](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b6dee-159">[Walkthrough: Embedding Type Information from Microsoft Office Assemblies](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))</span></span>
