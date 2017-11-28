---
title: "메타데이터 및 자동 기술 구성 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- runtime, metadata
- languages, interoperability
- portable executable files, metadata
- self-describing files
- metadata, about metadata
- common language runtime, metadata
- PE files, metadata
- components [.NET Framework], metadata
ms.assetid: 3dd13c5d-a508-455b-8dce-0a852882a5a7
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8fcb5ea90cc16d62fee5b8e95b03bfe53c3a6793
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="metadata-and-self-describing-components"></a><span data-ttu-id="e853b-102">메타데이터 및 자동 기술 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e853b-102">Metadata and Self-Describing Components</span></span>
<span data-ttu-id="e853b-103">이전에 한 가지 언어로 작성된 소프트웨어 구성 요소(.exe 또는 .dll)는 다른 언어로 작성된 소프트웨어 구성 요소를 쉽게 사용할 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-103">In the past, a software component (.exe or .dll) that was written in one language could not easily use a software component that was written in another language.</span></span> <span data-ttu-id="e853b-104">COM은 이러한 문제를 해결하기 위한 단계를 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-104">COM provided a step towards solving this problem.</span></span> <span data-ttu-id="e853b-105">.NET Framework는 컴파일러가 모든 모듈과 어셈블리에 추가 선언 정보를 내보낼 수 있도록 하여 구성 요소 상호 운용성을 훨씬 더 쉽게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-105">The .NET Framework makes component interoperation even easier by allowing compilers to emit additional declarative information into all modules and assemblies.</span></span> <span data-ttu-id="e853b-106">메타데이터라고 하는 이 정보는 구성 요소가 아무런 문제 없이 원만하게 상호 작용할 수 있도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-106">This information, called metadata, helps components to interact seamlessly.</span></span>  
  
 <span data-ttu-id="e853b-107">메타데이터는 프로그램을 기술하는 이진 정보이며 공용 언어 런타임 PE 파일 또는 메모리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-107">Metadata is binary information describing your program that is stored either in a common language runtime portable executable (PE) file or in memory.</span></span> <span data-ttu-id="e853b-108">코드를 PE 파일로 컴파일하면 메타데이터는 PE 파일의 한 부분에 삽입되고 해당 코드는 MSIL(Microsoft Intermediate Language)로 변환되어 파일의 다른 부분에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-108">When you compile your code into a PE file, metadata is inserted into one portion of the file, and your code is converted to Microsoft intermediate language (MSIL) and inserted into another portion of the file.</span></span> <span data-ttu-id="e853b-109">모듈 또는 어셈블리에서 정의되고 참조된 모든 형식과 멤버는 메타데이터 내에 기술됩니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-109">Every type and member that is defined and referenced in a module or assembly is described within metadata.</span></span> <span data-ttu-id="e853b-110">코드를 실행하면 런타임은 메타데이터를 메모리로 로드한 다음 참조하여 해당 코드의 클래스, 멤버, 상속 등에 대한 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-110">When code is executed, the runtime loads metadata into memory and references it to discover information about your code's classes, members, inheritance, and so on.</span></span>  
  
 <span data-ttu-id="e853b-111">메타데이터는 언어와 무관하게 코드에 정의된 모든 형식과 멤버를 기술하며</span><span class="sxs-lookup"><span data-stu-id="e853b-111">Metadata describes every type and member defined in your code in a language-neutral manner.</span></span> <span data-ttu-id="e853b-112">다음과 같은 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-112">Metadata stores the following information:</span></span>  
  
-   <span data-ttu-id="e853b-113">어셈블리 기술 내용</span><span class="sxs-lookup"><span data-stu-id="e853b-113">Description of the assembly.</span></span>  
  
    -   <span data-ttu-id="e853b-114">ID(이름, 버전, 문화권, 공개 키)</span><span class="sxs-lookup"><span data-stu-id="e853b-114">Identity (name, version, culture, public key).</span></span>  
  
    -   <span data-ttu-id="e853b-115">내보낸 형식</span><span class="sxs-lookup"><span data-stu-id="e853b-115">The types that are exported.</span></span>  
  
    -   <span data-ttu-id="e853b-116">이 어셈블리가 종속된 다른 어셈블리</span><span class="sxs-lookup"><span data-stu-id="e853b-116">Other assemblies that this assembly depends on.</span></span>  
  
    -   <span data-ttu-id="e853b-117">실행하는 데 필요한 보안 권한</span><span class="sxs-lookup"><span data-stu-id="e853b-117">Security permissions needed to run.</span></span>  
  
-   <span data-ttu-id="e853b-118">형식 기술 내용</span><span class="sxs-lookup"><span data-stu-id="e853b-118">Description of types.</span></span>  
  
    -   <span data-ttu-id="e853b-119">이름, 표시 여부, 기본 클래스 및 구현된 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e853b-119">Name, visibility, base class, and interfaces implemented.</span></span>  
  
    -   <span data-ttu-id="e853b-120">멤버(메서드, 필드, 속성, 이벤트, 중첩 형식)</span><span class="sxs-lookup"><span data-stu-id="e853b-120">Members (methods, fields, properties, events, nested types).</span></span>  
  
-   <span data-ttu-id="e853b-121">특성</span><span class="sxs-lookup"><span data-stu-id="e853b-121">Attributes.</span></span>  
  
    -   <span data-ttu-id="e853b-122">형식과 멤버를 수정하는 추가 설명적 요소</span><span class="sxs-lookup"><span data-stu-id="e853b-122">Additional descriptive elements that modify types and members.</span></span>  
  
## <a name="benefits-of-metadata"></a><span data-ttu-id="e853b-123">메타데이터의 이점</span><span class="sxs-lookup"><span data-stu-id="e853b-123">Benefits of Metadata</span></span>  
 <span data-ttu-id="e853b-124">메타데이터는 더욱 간편한 프로그래밍 모델의 주요 요소이며 IDL(인터페이스 정의 언어) 파일, 헤더 파일 또는 구성 요소 참조의 외부 메서드를 사용하지 않아도 되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-124">Metadata is the key to a simpler programming model, and eliminates the need for Interface Definition Language (IDL) files, header files, or any external method of component reference.</span></span> <span data-ttu-id="e853b-125">메타데이터를 사용하면 .NET Framework 언어는 개발자와 사용자 모두 알지 못한 채 언어와 무관하게 자동으로 자신을 기술할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-125">Metadata enables .NET Framework languages to describe themselves automatically in a language-neutral manner, unseen by both the developer and the user.</span></span> <span data-ttu-id="e853b-126">또한 특성을 사용하여 메타데이터를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-126">Additionally, metadata is extensible through the use of attributes.</span></span> <span data-ttu-id="e853b-127">메타데이터는 다음과 같은 중요한 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-127">Metadata provides the following major benefits:</span></span>  
  
-   <span data-ttu-id="e853b-128">자동 기술 파일</span><span class="sxs-lookup"><span data-stu-id="e853b-128">Self-describing files.</span></span>  
  
     <span data-ttu-id="e853b-129">공용 언어 런타임의 모듈과 어셈블리는 자동으로 기술됩니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-129">Common language runtime modules and assemblies are self-describing.</span></span> <span data-ttu-id="e853b-130">모듈의 메타데이터에는 다른 모듈과 상호 작용하는 데 필요한 모든 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-130">A module's metadata contains everything needed to interact with another module.</span></span> <span data-ttu-id="e853b-131">메타데이터는 하나의 파일만 사용하여 정의와 구현을 모두 수행할 수 있도록 COM의 IDL 기능을 자동으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-131">Metadata automatically provides the functionality of IDL in COM, so you can use one file for both definition and implementation.</span></span> <span data-ttu-id="e853b-132">런타임 모듈과 어셈블리를 운영 체제에 등록할 필요도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-132">Runtime modules and assemblies do not even require registration with the operating system.</span></span> <span data-ttu-id="e853b-133">결과적으로 런타임에 사용된 기술 내용은 항상 컴파일된 파일의 실제 코드를 반영하므로 응용 프로그램의 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-133">As a result, the descriptions used by the runtime always reflect the actual code in your compiled file, which increases application reliability.</span></span>  
  
-   <span data-ttu-id="e853b-134">언어 상호 운용성 및 간편해진 구성 요소 기반 디자인</span><span class="sxs-lookup"><span data-stu-id="e853b-134">Language interoperability and easier component-based design.</span></span>  
  
     <span data-ttu-id="e853b-135">메타데이터는 다른 언어로 작성된 PE 파일에서 클래스를 상속하기 위해 컴파일된 코드에 대해 필요한 모든 정보를 제공하므로</span><span class="sxs-lookup"><span data-stu-id="e853b-135">Metadata provides all the information required about compiled code for you to inherit a class from a PE file written in a different language.</span></span> <span data-ttu-id="e853b-136">명시적 마샬링을 고려하거나 사용자 지정 상호 운용성 코드를 사용할 필요 없이 관리되는 언어(공용 언어 런타임 기능이 있는 언어)로 작성된 클래스의 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-136">You can create an instance of any class written in any managed language (any language that targets the common language runtime) without worrying about explicit marshaling or using custom interoperability code.</span></span>  
  
-   <span data-ttu-id="e853b-137">특성</span><span class="sxs-lookup"><span data-stu-id="e853b-137">Attributes.</span></span>  
  
     <span data-ttu-id="e853b-138">.NET Framework에서는 특성이라고 하는 특정 종류의 메타데이터를 컴파일된 파일에 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-138">The .NET Framework lets you declare specific kinds of metadata, called attributes, in your compiled file.</span></span> <span data-ttu-id="e853b-139">특성은 .NET Framework 전체에서 선언할 수 있으며 프로그램이 런타임에 동작하는 방식을 좀 더 자세하게 제어하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-139">Attributes can be found throughout the .NET Framework and are used to control in more detail how your program behaves at run time.</span></span> <span data-ttu-id="e853b-140">또한 사용자 지정 특성을 사용하여 사용자 지정 메타데이터를 .NET Framework 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-140">Additionally, you can emit your own custom metadata into .NET Framework files through user-defined custom attributes.</span></span> <span data-ttu-id="e853b-141">자세한 내용은 [특성](../../docs/standard/attributes/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e853b-141">For more information, see [Attributes](../../docs/standard/attributes/index.md).</span></span>  
  
## <a name="metadata-and-the-pe-file-structure"></a><span data-ttu-id="e853b-142">메타데이터 및 PE 파일 구조</span><span class="sxs-lookup"><span data-stu-id="e853b-142">Metadata and the PE File Structure</span></span>  
 <span data-ttu-id="e853b-143">메타데이터는 .NET Framework PE 파일의 한 섹션에 저장되고 MSIL은 PE 파일의 다른 섹션에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-143">Metadata is stored in one section of a .NET Framework portable executable (PE) file, while Microsoft intermediate language (MSIL) is stored in another section of the PE file.</span></span> <span data-ttu-id="e853b-144">PE 파일의 메타데이터 부분에는 테이블과 힙 데이터 구조가 있으며</span><span class="sxs-lookup"><span data-stu-id="e853b-144">The metadata portion of the file contains a series of table and heap data structures.</span></span> <span data-ttu-id="e853b-145">MSIL 부분에는 MSIL 및 PE 파일의 메타데이터 부분을 참조하는 메타데이터 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-145">The MSIL portion contains MSIL and metadata tokens that reference the metadata portion of the PE file.</span></span> <span data-ttu-id="e853b-146">예를 들어 [MSIL 디스어셈블러(Ildasm.exe)](../../docs/framework/tools/ildasm-exe-il-disassembler.md) 같은 도구를 사용하여 코드의 MSIL을 보는 경우 메타데이터 토큰을 발견할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-146">You might encounter metadata tokens when you use tools such as the [MSIL Disassembler (Ildasm.exe)](../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view your code's MSIL, for example.</span></span>  
  
### <a name="metadata-tables-and-heaps"></a><span data-ttu-id="e853b-147">메타데이터 테이블 및 힙</span><span class="sxs-lookup"><span data-stu-id="e853b-147">Metadata Tables and Heaps</span></span>  
 <span data-ttu-id="e853b-148">각 메타데이터 테이블은 프로그램 요소에 대한 정보를 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-148">Each metadata table holds information about the elements of your program.</span></span> <span data-ttu-id="e853b-149">예를 들어, 한 메타데이터 테이블은 코드의 클래스를 나타내고 다른 테이블은 필드를 나타내는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-149">For example, one metadata table describes the classes in your code, another table describes the fields, and so on.</span></span> <span data-ttu-id="e853b-150">코드에 클래스가 10개 있는 경우 클래스 테이블은 각 클래스마다 행 하나씩, 모두 10개의 행을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-150">If you have ten classes in your code, the class table will have tens rows, one for each class.</span></span> <span data-ttu-id="e853b-151">메타데이터 테이블은 다른 테이블과 힙을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-151">Metadata tables reference other tables and heaps.</span></span> <span data-ttu-id="e853b-152">예를 들어, 클래스의 메타데이터 테이블은 메서드의 테이블을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-152">For example, the metadata table for classes references the table for methods.</span></span>  
  
 <span data-ttu-id="e853b-153">또한 메타데이터는 문자열, blob, 사용자 문자열 및 GUID라고 하는 네 가지 힙 구조에 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-153">Metadata also stores information in four heap structures: string, blob, user string, and GUID.</span></span> <span data-ttu-id="e853b-154">형식과 멤버의 이름을 지정하는 데 사용되는 모든 문자열은 문자열 힙에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-154">All the strings used to name types and members are stored in the string heap.</span></span> <span data-ttu-id="e853b-155">예를 들어, 메서드 테이블은 특정 메서드의 이름을 직접 저장하지 않지만 문자열 힙에 저장된 메서드의 이름을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-155">For example, a method table does not directly store the name of a particular method, but points to the method's name stored in the string heap.</span></span>  
  
### <a name="metadata-tokens"></a><span data-ttu-id="e853b-156">메타데이터 토큰</span><span class="sxs-lookup"><span data-stu-id="e853b-156">Metadata Tokens</span></span>  
 <span data-ttu-id="e853b-157">메타데이터 테이블의 각 행은 메타데이터 토큰에 의해 PE 파일의 MSIL 부분에서 고유하게 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-157">Each row of each metadata table is uniquely identified in the MSIL portion of the PE file by a metadata token.</span></span> <span data-ttu-id="e853b-158">메타데이터 토큰은 MSIL에 유지되고 특정 메타데이터 테이블을 참조하는 포인터와 개념적으로 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-158">Metadata tokens are conceptually similar to pointers, persisted in MSIL, that reference a particular metadata table.</span></span>  
  
 <span data-ttu-id="e853b-159">메타데이터 토큰은 4바이트 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-159">A metadata token is a four-byte number.</span></span> <span data-ttu-id="e853b-160">최상위 바이트는 특정 토큰이 참조하는 메타데이터 테이블(메서드, 형식 등)을 나타내고</span><span class="sxs-lookup"><span data-stu-id="e853b-160">The top byte denotes the metadata table to which a particular token refers (method, type, and so on).</span></span> <span data-ttu-id="e853b-161">나머지 3바이트는 메타데이터 테이블의 행 중에서 현재 나타내고 있는 프로그래밍 요소에 해당하는 행을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-161">The remaining three bytes specify the row in the metadata table that corresponds to the programming element being described.</span></span> <span data-ttu-id="e853b-162">C#에서 메서드를 정의하여 PE 파일로 컴파일하면 PE 파일의 MSIL 부분에 다음과 같은 메타데이터 토큰이 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-162">If you define a method in C# and compile it into a PE file, the following metadata token might exist in the MSIL portion of the PE file:</span></span>  
  
```  
0x06000004  
```  
  
 <span data-ttu-id="e853b-163">최상위 바이트(`0x06`)는 이 토큰이 **MethodDef** 토큰임을 나타내고,</span><span class="sxs-lookup"><span data-stu-id="e853b-163">The top byte (`0x06`) indicates that this is a **MethodDef** token.</span></span> <span data-ttu-id="e853b-164">하위 3바이트(`000004`)는 공용 언어 런타임이 **MethodDef** 테이블의 넷째 행에서 이 메서드 정의를 기술하는 정보를 찾도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-164">The lower three bytes (`000004`) tells the common language runtime to look in the fourth row of the **MethodDef** table for the information that describes this method definition.</span></span>  
  
### <a name="metadata-within-a-pe-file"></a><span data-ttu-id="e853b-165">PE 파일 내의 메타데이터</span><span class="sxs-lookup"><span data-stu-id="e853b-165">Metadata within a PE File</span></span>  
 <span data-ttu-id="e853b-166">프로그램이 공용 언어 런타임으로 컴파일되면 해당 프로그램은 세 부분으로 구성되는 PE 파일로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-166">When a program is compiled for the common language runtime, it is converted to a PE file that consists of three parts.</span></span> <span data-ttu-id="e853b-167">다음 표에서는 각 부분의 내용을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-167">The following table describes the contents of each part.</span></span>  
  
|<span data-ttu-id="e853b-168">PE 섹션</span><span class="sxs-lookup"><span data-stu-id="e853b-168">PE section</span></span>|<span data-ttu-id="e853b-169">PE 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e853b-169">Contents of PE section</span></span>|  
|----------------|----------------------------|  
|<span data-ttu-id="e853b-170">PE 헤더</span><span class="sxs-lookup"><span data-stu-id="e853b-170">PE header</span></span>|<span data-ttu-id="e853b-171">PE 파일의 주 섹션 인덱스 및 진입점 주소를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-171">The index of the PE file's main sections and the address of the entry point.</span></span><br /><br /> <span data-ttu-id="e853b-172">런타임은 이 정보를 사용하여 파일을 PE 파일로 식별하고 프로그램을 메모리로 로드하는 경우 실행 시작 위치를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-172">The runtime uses this information to identify the file as a PE file and to determine where execution starts when loading the program into memory.</span></span>|  
|<span data-ttu-id="e853b-173">MSIL 명령</span><span class="sxs-lookup"><span data-stu-id="e853b-173">MSIL instructions</span></span>|<span data-ttu-id="e853b-174">코드를 구성하는 MSIL 명령.</span><span class="sxs-lookup"><span data-stu-id="e853b-174">The Microsoft intermediate language instructions (MSIL) that make up your code.</span></span> <span data-ttu-id="e853b-175">대부분의 MSIL 명령은 메타데이터 토큰을 동반합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-175">Many MSIL instructions are accompanied by metadata tokens.</span></span>|  
|<span data-ttu-id="e853b-176">메타데이터</span><span class="sxs-lookup"><span data-stu-id="e853b-176">Metadata</span></span>|<span data-ttu-id="e853b-177">메타데이터 테이블과 힙.</span><span class="sxs-lookup"><span data-stu-id="e853b-177">Metadata tables and heaps.</span></span> <span data-ttu-id="e853b-178">런타임은 이 섹션을 사용하여 코드의 모든 형식과 멤버에 대한 정보를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-178">The runtime uses this section to record information about every type and member in your code.</span></span> <span data-ttu-id="e853b-179">또한 사용자 지정 특성과 보안 정보도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-179">This section also includes custom attributes and security information.</span></span>|  
  
## <a name="run-time-use-of-metadata"></a><span data-ttu-id="e853b-180">메타데이터 런타임 사용</span><span class="sxs-lookup"><span data-stu-id="e853b-180">Run-Time Use of Metadata</span></span>  
 <span data-ttu-id="e853b-181">공용 언어 런타임에서 메타데이터 및 메타데이터의 역할을 더 잘 이해하려면 간단한 프로그램을 만들어 메타데이터가 런타임 주기에 어떤 영향을 주는지 실제로 나타내 보면 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-181">To better understand metadata and its role in the common language runtime, it might be helpful to construct a simple program and illustrate how metadata affects its run-time life.</span></span> <span data-ttu-id="e853b-182">다음 코드 예제에서는 `MyApp`라는 클래스 내에서 두 가지 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-182">The following code example shows two methods inside a class called `MyApp`.</span></span> <span data-ttu-id="e853b-183">`Main` 메서드는 프로그램 진입점이고 `Add` 메서드는 두 정수 인수의 합계를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-183">The `Main` method is the program entry point, while the `Add` method simply returns the sum of two integer arguments.</span></span>  
  
```vb  
Public Class MyApp  
   Public Shared Sub Main()  
      Dim ValueOne As Integer = 10  
      Dim ValueTwo As Integer = 20  
      Console.WriteLine("The Value is: {0}", Add(ValueOne, ValueTwo))  
   End Sub  
  
   Public Shared Function Add(One As Integer, Two As Integer) As Integer  
      Return (One + Two)  
   End Function  
End Class  
```  
  
```csharp  
using System;    
public class MyApp  
{  
   public static int Main()  
   {  
      int ValueOne = 10;  
      int ValueTwo = 20;           
      Console.WriteLine("The Value is: {0}", Add(ValueOne, ValueTwo));  
      return 0;  
   }  
   public static int Add(int One, int Two)  
   {  
      return (One + Two);  
   }  
}  
```  
  
 <span data-ttu-id="e853b-184">코드를 실행하면 런타임은 모듈을 메모리로 로드하고 이 클래스의 메타데이터를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-184">When the code runs, the runtime loads the module into memory and consults the metadata for this class.</span></span> <span data-ttu-id="e853b-185">로드하고 나면 런타임은 메서드의 MSIL 스트림에 대해 광범위한 분석을 수행하여 이를 빠른 네이티브 기계어 명령으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-185">Once loaded, the runtime performs extensive analysis of the method's Microsoft intermediate language (MSIL) stream to convert it to fast native machine instructions.</span></span> <span data-ttu-id="e853b-186">런타임은 JIT(Just-In-Time) 컴파일러를 사용하여 MSIL 명령을 네이티브 기계어 코드 명령 메서드로 필요에 따라 한 번에 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-186">The runtime uses a just-in-time (JIT) compiler to convert the MSIL instructions to native machine code one method at a time as needed.</span></span>  
  
 <span data-ttu-id="e853b-187">다음 예제에서는 이전 코드의 `Main` 함수에서 생성된 MSIL 부분을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-187">The following example shows part of the MSIL produced from the previous code's `Main` function.</span></span> <span data-ttu-id="e853b-188">[MSIL 디스어셈블러(Ildasm.exe)](../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하여 .NET Framework 응용 프로그램에서 MSIL 및 메타데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-188">You can view the MSIL and metadata from any .NET Framework application using the [MSIL Disassembler (Ildasm.exe)](../../docs/framework/tools/ildasm-exe-il-disassembler.md).</span></span>  
  
```  
.entrypoint  
.maxstack  3  
.locals ([0] int32 ValueOne,  
         [1] int32 ValueTwo,  
         [2] int32 V_2,  
         [3] int32 V_3)  
IL_0000:  ldc.i4.s   10  
IL_0002:  stloc.0  
IL_0003:  ldc.i4.s   20  
IL_0005:  stloc.1  
IL_0006:  ldstr      "The Value is: {0}"  
IL_000b:  ldloc.0  
IL_000c:  ldloc.1  
IL_000d:  call int32 ConsoleApplication.MyApp::Add(int32,int32) /* 06000003 */  
```  
  
 <span data-ttu-id="e853b-189">JIT 컴파일러는 전체 메서드에 대한 MSIL을 읽고 이를 자세히 분석하여 해당 메서드에 대해 효과적인 네이티브 명령을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-189">The JIT compiler reads the MSIL for the whole method, analyzes it thoroughly, and generates efficient native instructions for the method.</span></span> <span data-ttu-id="e853b-190">`IL_000d`에 `Add` 메서드에 대한 메타데이터 토큰(`/*` `06000003 */`)이 있고 런타임은 이 토큰을 사용하여 **MethodDef** 테이블의 셋째 행을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-190">At `IL_000d`, a metadata token for the `Add` method (`/*` `06000003 */`) is encountered and the runtime uses the token to consult the third row of the **MethodDef** table.</span></span>  
  
 <span data-ttu-id="e853b-191">다음 표에서는 `Add` 메서드를 나타내는 메타데이터 토큰에서 참조하는 **MethodDef** 테이블의 부분을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-191">The following table shows part of the **MethodDef** table referenced by the metadata token that describes the `Add` method.</span></span> <span data-ttu-id="e853b-192">이 어셈블리에는 고유한 값을 가지는 다른 메타데이터 테이블도 있지만 여기서는 이 테이블에 대해서만 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-192">While other metadata tables exist in this assembly and have their own unique values, only this table is discussed.</span></span>  
  
|<span data-ttu-id="e853b-193">행</span><span class="sxs-lookup"><span data-stu-id="e853b-193">Row</span></span>|<span data-ttu-id="e853b-194">RVA(Relevant Virtual Address)</span><span class="sxs-lookup"><span data-stu-id="e853b-194">Relative Virtual Address (RVA)</span></span>|<span data-ttu-id="e853b-195">ImplFlags</span><span class="sxs-lookup"><span data-stu-id="e853b-195">ImplFlags</span></span>|<span data-ttu-id="e853b-196">플래그</span><span class="sxs-lookup"><span data-stu-id="e853b-196">Flags</span></span>|<span data-ttu-id="e853b-197">이름</span><span class="sxs-lookup"><span data-stu-id="e853b-197">Name</span></span><br /><br /> <span data-ttu-id="e853b-198">(문자열 힙을 가리킴)</span><span class="sxs-lookup"><span data-stu-id="e853b-198">(Points to string heap.)</span></span>|<span data-ttu-id="e853b-199">Signature(blob 힙을 가리킴)</span><span class="sxs-lookup"><span data-stu-id="e853b-199">Signature (Points to blob heap.)</span></span>|  
|---------|--------------------------------------|---------------|-----------|-----------------------------------------|----------------------------------------|  
|<span data-ttu-id="e853b-200">1</span><span class="sxs-lookup"><span data-stu-id="e853b-200">1</span></span>|<span data-ttu-id="e853b-201">0x00002050</span><span class="sxs-lookup"><span data-stu-id="e853b-201">0x00002050</span></span>|<span data-ttu-id="e853b-202">IL</span><span class="sxs-lookup"><span data-stu-id="e853b-202">IL</span></span><br /><br /> <span data-ttu-id="e853b-203">관리</span><span class="sxs-lookup"><span data-stu-id="e853b-203">Managed</span></span>|<span data-ttu-id="e853b-204">공용</span><span class="sxs-lookup"><span data-stu-id="e853b-204">Public</span></span><br /><br /> <span data-ttu-id="e853b-205">ReuseSlot</span><span class="sxs-lookup"><span data-stu-id="e853b-205">ReuseSlot</span></span><br /><br /> <span data-ttu-id="e853b-206">SpecialName</span><span class="sxs-lookup"><span data-stu-id="e853b-206">SpecialName</span></span><br /><br /> <span data-ttu-id="e853b-207">RTSpecialName</span><span class="sxs-lookup"><span data-stu-id="e853b-207">RTSpecialName</span></span><br /><br /> <span data-ttu-id="e853b-208">.ctor</span><span class="sxs-lookup"><span data-stu-id="e853b-208">.ctor</span></span>|<span data-ttu-id="e853b-209">.ctor (생성자)</span><span class="sxs-lookup"><span data-stu-id="e853b-209">.ctor (constructor)</span></span>||  
|<span data-ttu-id="e853b-210">2</span><span class="sxs-lookup"><span data-stu-id="e853b-210">2</span></span>|<span data-ttu-id="e853b-211">0x00002058</span><span class="sxs-lookup"><span data-stu-id="e853b-211">0x00002058</span></span>|<span data-ttu-id="e853b-212">IL</span><span class="sxs-lookup"><span data-stu-id="e853b-212">IL</span></span><br /><br /> <span data-ttu-id="e853b-213">관리</span><span class="sxs-lookup"><span data-stu-id="e853b-213">Managed</span></span>|<span data-ttu-id="e853b-214">공용</span><span class="sxs-lookup"><span data-stu-id="e853b-214">Public</span></span><br /><br /> <span data-ttu-id="e853b-215">정적</span><span class="sxs-lookup"><span data-stu-id="e853b-215">Static</span></span><br /><br /> <span data-ttu-id="e853b-216">ReuseSlot</span><span class="sxs-lookup"><span data-stu-id="e853b-216">ReuseSlot</span></span>|<span data-ttu-id="e853b-217">Main</span><span class="sxs-lookup"><span data-stu-id="e853b-217">Main</span></span>|<span data-ttu-id="e853b-218">문자열</span><span class="sxs-lookup"><span data-stu-id="e853b-218">String</span></span>|  
|<span data-ttu-id="e853b-219">3</span><span class="sxs-lookup"><span data-stu-id="e853b-219">3</span></span>|<span data-ttu-id="e853b-220">0x0000208c</span><span class="sxs-lookup"><span data-stu-id="e853b-220">0x0000208c</span></span>|<span data-ttu-id="e853b-221">IL</span><span class="sxs-lookup"><span data-stu-id="e853b-221">IL</span></span><br /><br /> <span data-ttu-id="e853b-222">관리</span><span class="sxs-lookup"><span data-stu-id="e853b-222">Managed</span></span>|<span data-ttu-id="e853b-223">공용</span><span class="sxs-lookup"><span data-stu-id="e853b-223">Public</span></span><br /><br /> <span data-ttu-id="e853b-224">정적</span><span class="sxs-lookup"><span data-stu-id="e853b-224">Static</span></span><br /><br /> <span data-ttu-id="e853b-225">ReuseSlot</span><span class="sxs-lookup"><span data-stu-id="e853b-225">ReuseSlot</span></span>|<span data-ttu-id="e853b-226">추가</span><span class="sxs-lookup"><span data-stu-id="e853b-226">Add</span></span>|<span data-ttu-id="e853b-227">int, int, int</span><span class="sxs-lookup"><span data-stu-id="e853b-227">int, int, int</span></span>|  
  
 <span data-ttu-id="e853b-228">테이블의 각 열에는 코드에 대한 중요한 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-228">Each column of the table contains important information about your code.</span></span> <span data-ttu-id="e853b-229">**RVA**열을 사용하여 런타임은 이 메서드를 정의하는 MSIL의 시작 메모리 주소를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-229">The **RVA** column allows the runtime to calculate the starting memory address of the MSIL that defines this method.</span></span> <span data-ttu-id="e853b-230">**ImplFlags** 및 **Flags** 열은 메서드를 나타내는 비트마스크(예: 해당 메서드가 공용인지 아니면 전용인지를 나타냄)를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-230">The **ImplFlags** and **Flags** columns contain bitmasks that describe the method (for example, whether the method is public or private).</span></span> <span data-ttu-id="e853b-231">**Name** 열은 문자열 힙에서 메서드의 이름을 인덱싱하고</span><span class="sxs-lookup"><span data-stu-id="e853b-231">The **Name** column indexes the name of the method from the string heap.</span></span> <span data-ttu-id="e853b-232">**Signature** 열은 blob 힙에서 메서드의 시그니처 정의를 인덱싱합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-232">The **Signature** column indexes the definition of the method's signature in the blob heap.</span></span>  
  
 <span data-ttu-id="e853b-233">런타임은 셋째 행의 **RVA** 열을 사용하여 원하는 오프셋 주소를 계산하고 이 주소를 JIT 컴파일러에 반환한 다음 새 주소로 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-233">The runtime calculates the desired offset address from the **RVA** column in the third row and returns this address to the JIT compiler, which then proceeds to the new address.</span></span> <span data-ttu-id="e853b-234">JIT 컴파일러는 다른 메타데이터 토큰을 발견할 때까지 새 주소에서 MSIL을 계속 처리하며 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-234">The JIT compiler continues to process MSIL at the new address until it encounters another metadata token and the process is repeated.</span></span>  
  
 <span data-ttu-id="e853b-235">메타데이터를 사용하면 런타임은 코드를 로드하여 네이티브 기계어 명령으로 처리하는 데 필요한 모든 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-235">Using metadata, the runtime has access to all the information it needs to load your code and process it into native machine instructions.</span></span> <span data-ttu-id="e853b-236">이런 방식으로 메타데이터는 공용 형식 시스템과 함께 자동 기술 파일 및 언어 간 상속을 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-236">In this manner, metadata enables self-describing files and, together with the common type system, cross-language inheritance.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="e853b-237">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e853b-237">Related Topics</span></span>  
  
|<span data-ttu-id="e853b-238">제목</span><span class="sxs-lookup"><span data-stu-id="e853b-238">Title</span></span>|<span data-ttu-id="e853b-239">설명</span><span class="sxs-lookup"><span data-stu-id="e853b-239">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e853b-240">특성</span><span class="sxs-lookup"><span data-stu-id="e853b-240">Attributes</span></span>](../../docs/standard/attributes/index.md)|<span data-ttu-id="e853b-241">특성을 적용하고, 사용자 지정 특성을 작성하고, 특성에 저장된 정보를 검색하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e853b-241">Describes how to apply attributes, write custom attributes, and retrieve information that is stored in attributes.</span></span>|
