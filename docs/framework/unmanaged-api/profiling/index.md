---
title: "프로파일링(관리되지 않는 API 참조)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- profiling [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], profiling
- unmanaged API reference [.NET Framework], profiling
ms.assetid: 14c68e84-657e-49c2-aa8b-4978dbaf4454
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5583a9b81d81acfca80368ca54d5f97899daa1d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="profiling-unmanaged-api-reference"></a><span data-ttu-id="a2283-102">프로파일링(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="a2283-102">Profiling (Unmanaged API Reference)</span></span>
<span data-ttu-id="a2283-103">프로 파일링 API를 사용 하면 공용 언어 런타임 (CLR) 하 여 프로그램 실행을 모니터링 하려면 프로파일러에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2283-103">The profiling API enables a profiler to monitor a program's execution by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a2283-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a2283-104">In This Section</span></span>  
 [<span data-ttu-id="a2283-105">프로파일링 개요</span><span class="sxs-lookup"><span data-stu-id="a2283-105">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
 <span data-ttu-id="a2283-106">서비스 및.NET Framework 환경에서 프로 파일링을 지원 하기 위해 CLR에서 제공 하는 인터페이스에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2283-106">Describes the services and interfaces that the CLR provides to support profiling in the .NET Framework environment.</span></span>  
  
 [<span data-ttu-id="a2283-107">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2283-107">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 <span data-ttu-id="a2283-108">프로파일링 API에서 사용하는 관리되지 않는 인터페이스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2283-108">Describes the unmanaged interfaces that the profiling API uses.</span></span>  
  
 [<span data-ttu-id="a2283-109">프로파일링 환경 설정</span><span class="sxs-lookup"><span data-stu-id="a2283-109">Setting Up a Profiling Environment</span></span>](../../../../docs/framework/unmanaged-api/profiling/setting-up-a-profiling-environment.md)  
 <span data-ttu-id="a2283-110">.NET Framework 응용 프로그램을 프로 파일링 하는 위해 수행 해야 하는 단계를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2283-110">Describes the steps you must take to profile a .NET Framework application.</span></span>  
  
 [<span data-ttu-id="a2283-111">CLR 프로파일러 및 Microsoft Azure Store 앱</span><span class="sxs-lookup"><span data-stu-id="a2283-111">CLR Profilers and Windows Store Apps</span></span>](../../../../docs/framework/unmanaged-api/profiling/clr-profilers-and-windows-store-apps.md)  
 <span data-ttu-id="a2283-112">Windows 스토어 앱에서는 성공적으로 작동 하는 CLR 프로 파일링 API를 사용 하는 진단 도구를 이식 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2283-112">Discusses how to port diagnostic tools that consume the CLR Profiling API to work successfully with Windows Store apps.</span></span>  
  
 [<span data-ttu-id="a2283-113">CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT</span><span class="sxs-lookup"><span data-stu-id="a2283-113">CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT</span></span>](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)  
 <span data-ttu-id="a2283-114">메서드 호출이 반환 되는 조건에 설명 된 `CORPROF_E_UNSUPPORTED_CALL_SEQUENCE` HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="a2283-114">Documents the conditions under which a method call returns the `CORPROF_E_UNSUPPORTED_CALL_SEQUENCE` HRESULT.</span></span>  
  
 [<span data-ttu-id="a2283-115">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="a2283-115">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
 <span data-ttu-id="a2283-116">프로파일링 API에서 사용하는 관리되지 않는 전역 정적 함수를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2283-116">Describes the unmanaged global static functions that the profiling API uses.</span></span>  
  
 [<span data-ttu-id="a2283-117">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="a2283-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
 <span data-ttu-id="a2283-118">프로파일링 API에서 사용하는 관리되지 않는 열거형을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2283-118">Describes the unmanaged enumerations that the profiling API uses.</span></span>  
  
 [<span data-ttu-id="a2283-119">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="a2283-119">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)  
 <span data-ttu-id="a2283-120">프로파일링 API에서 사용하는 관리되지 않는 구조체를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2283-120">Describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a2283-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="a2283-121">Related Sections</span></span>  
 [<span data-ttu-id="a2283-122">연습: 성능 문제 확인</span><span class="sxs-lookup"><span data-stu-id="a2283-122">Walkthrough: Identifying Performance Problems</span></span>](/visualstudio/profiling/walkthrough-identifying-performance-problems)  
 <span data-ttu-id="a2283-123">Microsoft Visual Studio 2005 Team System의 기본 제공 프로 파일링 도구를 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2283-123">Explains how to use the built-in profiling tools in the Microsoft Visual Studio 2005 Team System.</span></span> <span data-ttu-id="a2283-124">이러한 도구에는 프로 파일링 API를 사용 하는 대신을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2283-124">These tools provide an alternative approach to using the profiling API.</span></span>
