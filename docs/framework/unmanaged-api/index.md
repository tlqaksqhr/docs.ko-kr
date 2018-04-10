---
title: 관리되지 않는 API 참조
ms.custom: ''
ms.date: 11/06/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- runtime, unmanaged APIs
- common language runtime, unmanaged APIs
- native API reference [.NET Framework]
- unmanaged API reference [.NET Framework]
ms.assetid: 9aa000ee-c04c-492c-ae4f-83ecdf4fdbbe
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d86cf65dfb3637dbacfeff0cf2b5f48b12c49212
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="unmanaged-api-reference"></a><span data-ttu-id="de272-102">관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="de272-102">Unmanaged API Reference</span></span>
<span data-ttu-id="de272-103">이 섹션에는 런타임 호스트, 컴파일러, 디스어셈블러, 난독 처리기, 디버거, 프로파일러 등의 관리 코드 관련 응용 프로그램에서 사용할 수 있는 관리되지 않는 API에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de272-103">This section includes information on unmanaged APIs that can be used by managed-code-related applications, such as runtime hosts, compilers, disassemblers, obfuscators, debuggers, and profilers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="de272-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="de272-104">In This Section</span></span>  
 [<span data-ttu-id="de272-105">공통 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="de272-105">Common Data Types</span></span>](../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)  
 <span data-ttu-id="de272-106">특히 관리되지 않는 프로파일링 및 디버깅 API에서 사용되는 공통 데이터 형식에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="de272-106">Lists the common data types that are used, particularly in the unmanaged profiling and debugging APIs.</span></span>  
  
 [<span data-ttu-id="de272-107">ALink</span><span class="sxs-lookup"><span data-stu-id="de272-107">ALink</span></span>](../../../docs/framework/unmanaged-api/alink/index.md)  
 <span data-ttu-id="de272-108">.NET Framework 어셈블리 및 바인딩되지 않은 모듈 만들기를 지원하는 ALink API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de272-108">Describes the ALink API, which supports the creation of .NET Framework assemblies and unbound modules.</span></span>  
  
 [<span data-ttu-id="de272-109">Authenticode</span><span class="sxs-lookup"><span data-stu-id="de272-109">Authenticode</span></span>](../../../docs/framework/unmanaged-api/authenticode/index.md)  
 <span data-ttu-id="de272-110">Authenticode XrML 라이센스 만들기 및 확인 모듈을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="de272-110">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
 [<span data-ttu-id="de272-111">상수</span><span class="sxs-lookup"><span data-stu-id="de272-111">Constants</span></span>](../../../docs/framework/unmanaged-api/constants-unmanaged-api-reference.md)  
 <span data-ttu-id="de272-112">CorSym.idl에 정의된 상수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de272-112">Describes the constants that are defined in CorSym.idl.</span></span>  
  
 [<span data-ttu-id="de272-113">사용자 지정 인터페이스 특성</span><span class="sxs-lookup"><span data-stu-id="de272-113">Custom Interface Attributes</span></span>](http://msdn.microsoft.com/library/940952f9-46ad-4a1a-920f-118dc0bdcd9f)  
 <span data-ttu-id="de272-114">COM(구성 요소 개체 모델) 사용자 지정 인터페이스 특성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de272-114">Describes component object model (COM) custom interface attributes.</span></span>  
  
 [<span data-ttu-id="de272-115">디버깅</span><span class="sxs-lookup"><span data-stu-id="de272-115">Debugging</span></span>](../../../docs/framework/unmanaged-api/debugging/index.md)  
 <span data-ttu-id="de272-116">디버거가 CLR(공용 언어 런타임) 환경에서 실행되는 코드를 디버그할 수 있도록 하는 디버깅 API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de272-116">Describes the debugging API, which enables a debugger to debug code that runs in the common language runtime (CLR) environment.</span></span>  
  
 [<span data-ttu-id="de272-117">진단 기호 저장소</span><span class="sxs-lookup"><span data-stu-id="de272-117">Diagnostics Symbol Store</span></span>](../../../docs/framework/unmanaged-api/diagnostics/index.md)  
 <span data-ttu-id="de272-118">컴파일러가 디버거에 사용되는 기호 정보를 생성할 수 있도록 하는 진단 기호 저장소 API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de272-118">Describes the diagnostics symbol store API, which enables a compiler to generate symbol information for use by a debugger.</span></span>  
  
 [<span data-ttu-id="de272-119">Fusion</span><span class="sxs-lookup"><span data-stu-id="de272-119">Fusion</span></span>](../../../docs/framework/unmanaged-api/fusion/index.md)  
 <span data-ttu-id="de272-120">런타임 호스트가 응용 프로그램 리소스의 속성에 액세스하여 응용 프로그램용으로 해당 리소스의 정확한 버전을 찾을 수 있도록 하는 Fusion API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de272-120">Describes the fusion API, which enables a runtime host to access the properties of an application's resources in order to locate the correct versions of those resources for the application.</span></span>  
  
 [<span data-ttu-id="de272-121">호스팅</span><span class="sxs-lookup"><span data-stu-id="de272-121">Hosting</span></span>](../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="de272-122">관리되지 않는 호스트가 CLR을 응용 프로그램에 통합할 수 있도록 하는 호스팅 API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de272-122">Describes the hosting API, which enables unmanaged hosts to integrate the CLR into their applications.</span></span>  
  
 [<span data-ttu-id="de272-123">메타데이터</span><span class="sxs-lookup"><span data-stu-id="de272-123">Metadata</span></span>](../../../docs/framework/unmanaged-api/metadata/index.md)  
 <span data-ttu-id="de272-124">컴파일러 등의 클라이언트가 CLR에 형식을 로드하지 않아도 구성 요소 메타데이터를 생성하거나 액세스할 수 있도록 하는 메타데이터 API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de272-124">Describes the metadata API, which enables a client such as a compiler to generate or access a component's metadata without the types being loaded by the CLR.</span></span>  
  
 [<span data-ttu-id="de272-125">프로파일링</span><span class="sxs-lookup"><span data-stu-id="de272-125">Profiling</span></span>](../../../docs/framework/unmanaged-api/profiling/index.md)  
 <span data-ttu-id="de272-126">프로파일러가 CLR에 의한 프로그램 실행을 모니터링할 수 있도록 하는 프로파일링 API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de272-126">Describes the profiling API, which enables a profiler to monitor a program's execution by the CLR.</span></span>  
  
 [<span data-ttu-id="de272-127">강력한 이름</span><span class="sxs-lookup"><span data-stu-id="de272-127">Strong Naming</span></span>](../../../docs/framework/unmanaged-api/strong-naming/index.md)  
 <span data-ttu-id="de272-128">클라이언트가 어셈블리에 대해 강력한 이름 서명을 관리할 수 있도록 하는 강력한 이름 API에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de272-128">Describes the strong naming API, which enables a client to administer strong name signing for assemblies.</span></span>  

 [<span data-ttu-id="de272-129">WMI 및 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="de272-129">WMI and Performance Counters</span></span>](wmi/index.md)  
 <span data-ttu-id="de272-130">Windows Management Instrumentation (WMI) 라이브러리에 대 한 호출을 래핑하는 Api에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="de272-130">Describes the APIs that wrap calls to Windows Management Instrumentation (WMI) libraries.</span></span>
  
 [<span data-ttu-id="de272-131">Tlbexp 도우미 함수</span><span class="sxs-lookup"><span data-stu-id="de272-131">Tlbexp Helper Functions</span></span>](../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 <span data-ttu-id="de272-132">어셈블리에서 형식 라이브러리로의 변환 프로세스 중 형식 라이브러리 내보내기(Tlbexp.exe)에서 사용하는 두 도우미 함수 및 인터페이스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de272-132">Describes the two helper functions and interface used by the Type Library Exporter (Tlbexp.exe) during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="de272-133">관련 단원</span><span class="sxs-lookup"><span data-stu-id="de272-133">Related Sections</span></span>  
 [<span data-ttu-id="de272-134">개발 가이드</span><span class="sxs-lookup"><span data-stu-id="de272-134">Development Guide</span></span>](../../../docs/framework/development-guide.md)  
  
 [<span data-ttu-id="de272-135">.NET Framework에 대한 고급 정보</span><span class="sxs-lookup"><span data-stu-id="de272-135">Advanced Reading for the .NET Framework</span></span>](http://msdn.microsoft.com/library/faae8083-fecb-4514-b133-b0a5a32a7c3c)
