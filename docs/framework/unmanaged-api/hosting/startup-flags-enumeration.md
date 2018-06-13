---
title: STARTUP_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- STARTUP_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- STARTUP_FLAGS
helpviewer_keywords:
- STARTUP_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 4f043594-0c45-4bc6-988e-a6793f0d8d06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc1d3ffc34cd74d68bf10cb677b68f0a75bb7c67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444232"
---
# <a name="startupflags-enumeration"></a><span data-ttu-id="f428c-102">STARTUP_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="f428c-102">STARTUP_FLAGS Enumeration</span></span>
<span data-ttu-id="f428c-103">공용 언어 런타임 (CLR)의 시작 동작을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-103">Contains values that indicate the startup behavior of the common language runtime (CLR).</span></span> <span data-ttu-id="f428c-104">기본적으로 가비지 컬렉션은 비 동시 및 전용 기본 클래스 라이브러리는 도메인 중립적으로 영역에 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-104">By default, garbage collection is non-concurrent, and only the base class library is loaded into the domain-neutral area.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f428c-105">구문</span><span class="sxs-lookup"><span data-stu-id="f428c-105">Syntax</span></span>  
  
```  
typedef enum {  
    STARTUP_CONCURRENT_GC                         = 0x1,  
    STARTUP_LOADER_OPTIMIZATION_MASK              = 0x3<<1,  
    STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN     = 0x1<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN      = 0x2<<1,  
    STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST = 0x3<<1,  
  
    STARTUP_LOADER_SAFEMODE                       = 0x10,  
    STARTUP_LOADER_SETPREFERENCE                  = 0x100,  
  
    STARTUP_SERVER_GC                             = 0x1000,  
    STARTUP_HOARD_GC_VM                           = 0x2000,  
  
    STARTUP_SINGLE_VERSION_HOSTING_INTERFACE      = 0x4000,  
    STARTUP_LEGACY_IMPERSONATION                  = 0x10000,  
    STARTUP_DISABLE_COMMITTHREADSTACK             = 0x20000,  
    STARTUP_ALWAYSFLOW_IMPERSONATION              = 0x40000,  
    STARTUP_TRIM_GC_COMMIT                        = 0x80000,  
  
    STARTUP_ETW                                   = 0x100000,  
    STARTUP_ARM                                   = 0x400000  
} STARTUP_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="f428c-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f428c-106">Members</span></span>  
  
|<span data-ttu-id="f428c-107">멤버</span><span class="sxs-lookup"><span data-stu-id="f428c-107">Member</span></span>|<span data-ttu-id="f428c-108">설명</span><span class="sxs-lookup"><span data-stu-id="f428c-108">Description</span></span>|  
|------------|-----------------|  
|`STARTUP_CONCURRENT_GC`|<span data-ttu-id="f428c-109">동시 가비지 수집을 사용 해야 함을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-109">Specifies that concurrent garbage collection should be used.</span></span> <span data-ttu-id="f428c-110">호출자에 게 서버 빌드 및 동시 가비지 컬렉션은 단일 프로세서 컴퓨터에서을 요청 하는 경우 워크스테이션 빌드 및 비 동시 가비지 수집 대신 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-110">If the caller asks for the server build and concurrent garbage collection on a single-processor machine, the workstation build and non-concurrent garbage collection are run instead.</span></span> <span data-ttu-id="f428c-111">**참고:** 동시 가비지 수집 WOW64를 실행 중인 응용 프로그램에서 지원 되지 않습니다 x86 에뮬레이터 (이전의 ia-64) Intel Itanium 아키텍처를 구현 하는 64 비트 시스템에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-111">**Note:**  Concurrent garbage collection is not supported in applications that are running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="f428c-112">64 비트 Windows 시스템에서 w o w 64를 사용 하는 방법에 대 한 자세한 내용은 참조 [실행 중인 32 비트 응용 프로그램](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-112">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MASK`|<span data-ttu-id="f428c-113">해당 로더 최적화가 실행을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-113">Specifies that loader optimization shall occur.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_SINGLE_DOMAIN`|<span data-ttu-id="f428c-114">어셈블리가 없는 도메인 중립적으로 로드 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-114">Specifies that no assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN`|<span data-ttu-id="f428c-115">모든 어셈블리가 도메인 중립적으로 로드 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-115">Specifies that all assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_OPTIMIZATION_MULTI_DOMAIN_HOST`|<span data-ttu-id="f428c-116">도메인 중립적으로 로드 된 모든 강력한 이름의 어셈블리를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-116">Specifies that all strong-named assemblies are loaded as domain-neutral.</span></span>|  
|`STARTUP_LOADER_SAFEMODE`|<span data-ttu-id="f428c-117">CLR 버전 정책에 전달 된 버전에 적용 되지 않습니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-117">Specifies that CLR version policy will not be applied to the version passed in.</span></span> <span data-ttu-id="f428c-118">CLR의 지정 된 버전만 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-118">The exact version specified of the CLR will be loaded.</span></span> <span data-ttu-id="f428c-119">Shim 호환 되는 최신 버전을 확인 하기 위해 정책을 평가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-119">The shim does not evaluate policy to determine the latest compatible version.</span></span>|  
|`STARTUP_LOADER_SETPREFERENCE`|<span data-ttu-id="f428c-120">기본 런타임을 설정 하지만 실제로 시작 하지 수는 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-120">Specifies that the preferred runtime will be set, but not actually started.</span></span>|  
|`STARTUP_SERVER_GC`|<span data-ttu-id="f428c-121">서버 가비지 수집을 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-121">Specifies that the server garbage collection will be used.</span></span>|  
|`STARTUP_HOARD_GC_VM`|<span data-ttu-id="f428c-122">가비지 수집이 사용 되는 가상 주소를 유지 합니다를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-122">Specifies that garbage collection will keep the virtual address used.</span></span>|  
|`STARTUP_SINGLE_VERSION_HOSTING_INTERFACE`|<span data-ttu-id="f428c-123">호스팅 인터페이스 혼합 허용 되지 않습니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-123">Specifies that mixing a hosting interface will not be allowed.</span></span>|  
|`STARTUP_LEGACY_IMPERSONATION`|<span data-ttu-id="f428c-124">기본적으로 가장 비동기 지점 간에 전달 되지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-124">Specifies that impersonation should not flow across asynchronous points by default.</span></span>|  
|`STARTUP_DISABLE_COMMITTHREADSTACK`|<span data-ttu-id="f428c-125">전체 스레드 스택 하지 커밋되어야 함을 스레드 실행을 시작할 때 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-125">Specifies that the full thread stack should not be committed when the thread starts running.</span></span>|  
|`STARTUP_ALWAYSFLOW_IMPERSONATION`|<span data-ttu-id="f428c-126">관리 되는 가장 및 플랫폼을 통해 수행 호출을 지정 합니다. 비동기 지점에 가로로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-126">Specifies that managed impersonations and impersonations achieved through platform invoke will flow across asynchronous points.</span></span> <span data-ttu-id="f428c-127">기본적으로 관리 되는 가장만 비동기 지점 간에 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-127">By default, only managed impersonations will flow across asynchronous points.</span></span>|  
|`STARTUP_TRIM_GC_COMMIT`|<span data-ttu-id="f428c-128">시스템 메모리가 부족 한 경우 가비지 수집 커밋된 공간을 적게 사용 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-128">Specifies that garbage collection will use less committed space when system memory is low.</span></span> <span data-ttu-id="f428c-129">참조 `gcTrimCommitOnLowMemory` 에 [공유 웹 호스팅을 위한 최적화](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-129">See `gcTrimCommitOnLowMemory` in [Optimization for Shared Web Hosting](../../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md).</span></span>|  
|`STARTUP_ETW`|<span data-ttu-id="f428c-130">공용 언어 런타임 이벤트에 대 한 이벤트 추적에 대 한 ETW (Windows)을 사용할 수 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-130">Specifies that event tracing for Windows (ETW) is enabled for common language runtime events.</span></span> <span data-ttu-id="f428c-131">Windows Vista부터, 이벤트 추적 항상 사용 되므로이 플래그는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-131">Beginning with Windows Vista, event tracing is always enabled, so this flag has no effect.</span></span> <span data-ttu-id="f428c-132">참조 [.NET Framework 로깅 제어](../../../../docs/framework/performance/controlling-logging.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-132">See [Controlling .NET Framework Logging](../../../../docs/framework/performance/controlling-logging.md).</span></span>|  
|`STARTUP_ARM`|<span data-ttu-id="f428c-133">응용 프로그램 도메인 리소스 모니터링은 사용할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-133">Specifies that application domain resource monitoring is enabled.</span></span> <span data-ttu-id="f428c-134">참조는 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> 속성 및 [ \<appDomainResourceMonitoring > 요소](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-134">See the <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType> property and [\<appDomainResourceMonitoring> Element](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f428c-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f428c-135">Requirements</span></span>  
 <span data-ttu-id="f428c-136">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f428c-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f428c-137">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f428c-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f428c-138">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f428c-138">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f428c-139">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f428c-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f428c-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f428c-140">See Also</span></span>  
 [<span data-ttu-id="f428c-141">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="f428c-141">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
