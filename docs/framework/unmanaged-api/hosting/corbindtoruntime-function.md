---
title: "CorBindToRuntime 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CorBindToRuntime
helpviewer_keywords: CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e6ce976961eedaa58ad265a133c15b2f27a8985
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corbindtoruntime-function"></a><span data-ttu-id="ea666-102">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="ea666-102">CorBindToRuntime Function</span></span>
<span data-ttu-id="ea666-103">관리 되지 않는 호스트 프로세스에 공용 언어 런타임 (CLR)를 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="ea666-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea666-105">구문</span><span class="sxs-lookup"><span data-stu-id="ea666-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,   
    [in]  LPCWSTR     pwszBuildFlavor,   
    [in]  REFCLSID    rclsid,   
    [in]  REFIID      riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea666-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ea666-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="ea666-107">[in] 로드 하려는 CLR의 버전을 설명 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-107">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="ea666-108">.NET Framework의 버전 번호는 마침표로 구분 된 4 개의 부분으로 구성 됩니다: *major.minor.build.revision*합니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="ea666-109">로 전달 되는 문자열 `pwszVersion` 문자 "v" 뒤에 버전 번호 (예: "나옵니다 v1.0.1529")의 처음 세 부분이로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="ea666-110">일부 버전의 CLR CLR의 이전 버전과 호환성을 지정 하는 정책 설명을 함께 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="ea666-111">기본적으로 시작 shim 평가 `pwszVersion` 정책 문을 부하에 대해 최신 버전의 런타임 호환 되는 요청 된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="ea666-112">호스트 정책 평가 건너뛰고에 지정 된 정확한 버전을 로드 하는 shim을 강제할 수 `pwszVersion` 의 값을 전달 하 여 `STARTUP_LOADER_SAFEMODE` 에 대 한는 `flags` 아래 설명 된 대로 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `flags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="ea666-113">호출자가 null을 지정 하는 경우 `pwszVersion`, 최신 버전의 런타임 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-113">If the caller specifies null for `pwszVersion`, the latest version of the runtime is loaded.</span></span> <span data-ttu-id="ea666-114">Null이 전달 사용 하면 호스트가 버전의 런타임 과부화 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-114">Passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="ea666-115">이 방법을 사용, 일부 시나리오에서 적절 한 수 있지만 호스트 로드 하는 특정 버전을 제공 합니다 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-115">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="ea666-116">[in] Clr 서버 또는 워크스테이션을 로드할지 여부를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-116">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="ea666-117">유효한 값은 `svr` 및 `wks`입니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-117">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="ea666-118">서버 빌드는 가비지 컬렉션에 대 한 여러 프로세서를 활용 하도록 최적화 하 고 단일 프로세서 컴퓨터에서 실행 되는 클라이언트 응용 프로그램에 대 한 워크스테이션 빌드 최적화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-118">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="ea666-119">경우 `pwszBuildFlavor` 로 설정 된 워크스테이션 빌드가 null 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-119">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="ea666-120">를 단일 프로세서 컴퓨터에서 실행 하는 경우 워크스테이션 빌드 항상 로드, 경우에 `pwszBuildFlavor` 로 설정 된 `svr`합니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-120">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="ea666-121">그러나 경우 `pwszBuildFlavor` 로 설정 된 `svr` 동시 가비지 컬렉션이 지정 되 고 (의 설명을 참조는 `flags` 매개 변수), 서버 빌드가 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-121">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `flags` parameter), the server build is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="ea666-122">[in] `CLSID` 중 하나를 구현 하는 coclass의는 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-122">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="ea666-123">지원 되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-123">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="ea666-124">[in] `IID` 에서 요청된 된 인터페이스의 `rclsid`합니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-124">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="ea666-125">지원 되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-125">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="ea666-126">[out] 반환 된 인터페이스 포인터를 `riid`합니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-126">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea666-127">설명</span><span class="sxs-lookup"><span data-stu-id="ea666-127">Remarks</span></span>  
 <span data-ttu-id="ea666-128">경우 `pwszVersion` 존재 하지 않는 런타임 버전을 지정 `CorBindToRuntimeEx` CLR_E_SHIM_RUNTIMELOAD HRESULT 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-128">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="ea666-129">실행 컨텍스트 및 Windows Id의 흐름</span><span class="sxs-lookup"><span data-stu-id="ea666-129">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="ea666-130">CLR의 버전 1에에서는 <xref:System.Security.Principal.WindowsIdentity> 개체가 새 스레드나 스레드 풀 타이머 콜백을 처럼 비동기 요소 간에 전달 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-130">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="ea666-131">CLR의 버전 2.0에에서는 <xref:System.Threading.ExecutionContext> 개체는 현재 실행 중인 스레드에 대 한 일부 정보를 래핑하고 비동기 지점 간에 하지만 응용 프로그램 도메인 경계를 넘어 하지 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-131">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="ea666-132">마찬가지로,는 <xref:System.Security.Principal.WindowsIdentity> 비동기 지점 간에 개체도 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-132">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="ea666-133">따라서 스레드의 현재 가장 있는 경우도 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-133">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="ea666-134">두 가지 방법으로 흐름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-134">You can alter the flow in two ways:</span></span>  
  
1.  <span data-ttu-id="ea666-135">수정 하 여는 <xref:System.Threading.ExecutionContext> 스레드 단위 별로 흐름을 억제할 수 설정 (참조는 <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, 및 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> 메서드).</span><span class="sxs-lookup"><span data-stu-id="ea666-135">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2.  <span data-ttu-id="ea666-136">버전 1 호환 모드를 프로세스 기본 모드를 변경 하 여 여기서는 <xref:System.Security.Principal.WindowsIdentity> 에 관계 없이 개체를 비동기 언제 든 간에 전달 되지 않습니다는 <xref:System.Threading.ExecutionContext> 현재 스레드에 대 한 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-136">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="ea666-137">기본 모드를 변경 하는 방식에서 CLR 로드 하는 관리 되는 실행 파일 또는 관리 되지 않는 호스팅 인터페이스 사용 되는 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-137">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1.  <span data-ttu-id="ea666-138">관리 되는 실행 파일에 대 한 설정 해야 합니다는 `enabled` 특성에는 [ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) 요소를 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-138">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2.  <span data-ttu-id="ea666-139">관리 되지 않는 호스팅 인터페이스를 설정는 `STARTUP_LEGACY_IMPERSONATION` 플래그는 `flags` 를 호출할 때 매개 변수는 `CorBindToRuntimeEx` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-139">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `flags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="ea666-140">버전 1 호환 모드에는 전체 프로세스와 프로세스에서 모든 응용 프로그램 도메인에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-140">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea666-141">설명</span><span class="sxs-lookup"><span data-stu-id="ea666-141">Remarks</span></span>  
 <span data-ttu-id="ea666-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 및 `CorBindToRuntime` 동일한 작업을 수행 하지만 `CorBindToRuntimeEx` 함수는 CLR의 동작을 지정 하는 플래그를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and `CorBindToRuntime` perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea666-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea666-143">Requirements</span></span>  
 <span data-ttu-id="ea666-144">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ea666-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea666-145">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ea666-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea666-146">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea666-146">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea666-147">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea666-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea666-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea666-148">See Also</span></span>  
 [<span data-ttu-id="ea666-149">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="ea666-149">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="ea666-150">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="ea666-150">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="ea666-151">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="ea666-151">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="ea666-152">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="ea666-152">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="ea666-153">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea666-153">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="ea666-154">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="ea666-154">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
