---
title: "ICLRMetaHost 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost
helpviewer_keywords: ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type: apiref
caps.latest.revision: "28"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d271a69847e3bd4dc972ed8e697b8cd15f049fb9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahost-interface"></a><span data-ttu-id="e2edc-102">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2edc-102">ICLRMetaHost Interface</span></span>
<span data-ttu-id="e2edc-103">특정 버전의 공용 언어 런타임 (CLR) 버전 번호에 따라 반환, 모든 설치 된 Clr 목록, 지정된 된 프로세스에 로드 되는 모든 런타임 목록, 어셈블리로 컴파일, 프로세스를 종료 하는 데 사용 된 CLR 버전을 검색 하는 메서드를 제공 합니다. 정상적인 런타임 종료 및 레거시 API 바인딩을 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2edc-103">Provides methods that return a specific version of the common language runtime (CLR) based on its version number, list all installed CLRs, list all runtimes that are loaded in a specified process, discover the CLR version used to compile an assembly, exit a process with a clean runtime shutdown, and query legacy API binding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e2edc-104">메서드</span><span class="sxs-lookup"><span data-stu-id="e2edc-104">Methods</span></span>  
  
|<span data-ttu-id="e2edc-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e2edc-105">Method</span></span>|<span data-ttu-id="e2edc-106">설명</span><span class="sxs-lookup"><span data-stu-id="e2edc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e2edc-107">EnumerateInstalledRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="e2edc-107">EnumerateInstalledRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|<span data-ttu-id="e2edc-108">유효한를 포함 하는 열거형을 반환 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 하는 컴퓨터에 설치 되어 있는 각 CLR 버전에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e2edc-108">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR version that is installed on a computer.</span></span>|  
|[<span data-ttu-id="e2edc-109">EnumerateLoadedRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="e2edc-109">EnumerateLoadedRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|<span data-ttu-id="e2edc-110">유효한를 포함 하는 열거형을 반환 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 지정된 된 프로세스에 로드 된 각 CLR에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e2edc-110">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR that is loaded in a given process.</span></span> <span data-ttu-id="e2edc-111">이 메서드를 대체 [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e2edc-111">This method supersedes [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md).</span></span>|  
|[<span data-ttu-id="e2edc-112">ExitProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="e2edc-112">ExitProcess Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|<span data-ttu-id="e2edc-113">모든 로드 된 런타임을 정상적으로 종료 하 고 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2edc-113">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="e2edc-114">대체는 [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e2edc-114">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>|  
|[<span data-ttu-id="e2edc-115">GetRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="e2edc-115">GetRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|<span data-ttu-id="e2edc-116">가져옵니다는 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 특정 CLR 버전에 해당 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e2edc-116">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular CLR version.</span></span> <span data-ttu-id="e2edc-117">이 메서드를 대체는 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 사용한 함수는 [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e2edc-117">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>|  
|[<span data-ttu-id="e2edc-118">GetVersionFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="e2edc-118">GetVersionFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|<span data-ttu-id="e2edc-119">어셈블리의.NET Framework 컴파일 원본이 (메타 데이터에 저장 됨)을 지정 된 파일 경로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e2edc-119">Gets the assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="e2edc-120">이 메서드를 대체 [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e2edc-120">This method supersedes [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md).</span></span>|  
|[<span data-ttu-id="e2edc-121">QueryLegacyV2RuntimeBinding 메서드</span><span class="sxs-lookup"><span data-stu-id="e2edc-121">QueryLegacyV2RuntimeBinding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|<span data-ttu-id="e2edc-122">레거시 활성화 정책이 바인딩된, 예를 사용 하 여 런타임을 나타내는 인터페이스를 반환 된 `useLegacyV2RuntimeActivationPolicy` 특성에 [ \<시작 > 요소](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) 직접 사용 하 여 구성 파일 항목 레거시 활성화 Api 호출 하거나는 [iclrruntimeinfo:: Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="e2edc-122">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>|  
|[<span data-ttu-id="e2edc-123">RequestRuntimeLoadedNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="e2edc-123">RequestRuntimeLoadedNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|<span data-ttu-id="e2edc-124">CLR 버전은 처음 로드 되었지만 아직 시작 되지 않았을 때 지정 된 함수 포인터에 대 한 콜백을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2edc-124">Guarantees a callback to the specified function pointer when a CLR version is first loaded, but not yet started.</span></span> <span data-ttu-id="e2edc-125">이 메서드를 대체 [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)</span><span class="sxs-lookup"><span data-stu-id="e2edc-125">This method supersedes [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2edc-126">설명</span><span class="sxs-lookup"><span data-stu-id="e2edc-126">Remarks</span></span>  
 <span data-ttu-id="e2edc-127">유일한 방법은이 인터페이스의 인스턴스를 호출 하 여 것은 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) 다음과 같이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2edc-127">The only way to get an instance of this interface is by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as follows:</span></span>  
  
```  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e2edc-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e2edc-128">Requirements</span></span>  
 <span data-ttu-id="e2edc-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e2edc-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2edc-130">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e2edc-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e2edc-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e2edc-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2edc-132">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2edc-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2edc-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2edc-133">See Also</span></span>  
 [<span data-ttu-id="e2edc-134">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2edc-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="e2edc-135">호스팅</span><span class="sxs-lookup"><span data-stu-id="e2edc-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
