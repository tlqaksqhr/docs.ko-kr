---
title: "ICLRRuntimeInfo::IsLoaded 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.IsLoaded
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ac7ed77dd4cb141257a1b73ccd433c7d17ee1f38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="591e8-102">ICLRRuntimeInfo::IsLoaded 메서드</span><span class="sxs-lookup"><span data-stu-id="591e8-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="591e8-103">공용 언어 런타임 (CLR)와 관련 된 있는지 여부를 나타냅니다는 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스는 프로세스에 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="591e8-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="591e8-104">시작 하지 않고 런타임에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="591e8-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="591e8-105">구문</span><span class="sxs-lookup"><span data-stu-id="591e8-105">Syntax</span></span>  
  
```  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="591e8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="591e8-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="591e8-107">[in] 프로세스에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="591e8-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="591e8-108">[out] `true` CLR이 고, 그렇지 않으면 프로세스에 로드 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="591e8-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="591e8-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="591e8-109">Return Value</span></span>  
 <span data-ttu-id="591e8-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="591e8-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="591e8-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="591e8-111">HRESULT</span></span>|<span data-ttu-id="591e8-112">설명</span><span class="sxs-lookup"><span data-stu-id="591e8-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="591e8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="591e8-113">S_OK</span></span>|<span data-ttu-id="591e8-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="591e8-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="591e8-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="591e8-115">E_POINTER</span></span>|<span data-ttu-id="591e8-116">`pbLoaded`가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="591e8-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="591e8-117">설명</span><span class="sxs-lookup"><span data-stu-id="591e8-117">Remarks</span></span>  
 <span data-ttu-id="591e8-118">이 메서드는 이전 버전과 호환성이 다음 기능 및 인터페이스:</span><span class="sxs-lookup"><span data-stu-id="591e8-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
-   <span data-ttu-id="591e8-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) (.NET Framework 버전 1 호스팅 API)의 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="591e8-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
-   <span data-ttu-id="591e8-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) (호스팅 API는.NET Framework 2.0)에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="591e8-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
-   <span data-ttu-id="591e8-121">사용 되지 않음 `CorBindTo*` 함수 (참조 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) 호스팅 API는.NET Framework 2.0에서).</span><span class="sxs-lookup"><span data-stu-id="591e8-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="591e8-122">호스트 사용 되지 않는 중 하나를 호출할 수 있습니다 `CorBindTo*` 와 같은 함수가 [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) 함수는 CLR의 특정 버전을 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="591e8-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="591e8-123">호스트 호출할 수는 [iclrmetahost:: Getruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) 메서드를 가져올 동일한 버전 번호를 지정 하 고는 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="591e8-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="591e8-124">호스트 한 다음 호출 하는 경우는 `IsLoaded` 메서드 반환 된 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스 `pbLoaded` 반환 `true`, 그렇지 않으면 반환 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="591e8-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="591e8-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="591e8-125">Requirements</span></span>  
 <span data-ttu-id="591e8-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="591e8-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="591e8-127">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="591e8-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="591e8-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="591e8-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="591e8-129">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="591e8-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="591e8-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="591e8-130">See Also</span></span>  
 [<span data-ttu-id="591e8-131">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="591e8-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="591e8-132">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="591e8-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="591e8-133">호스팅</span><span class="sxs-lookup"><span data-stu-id="591e8-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
