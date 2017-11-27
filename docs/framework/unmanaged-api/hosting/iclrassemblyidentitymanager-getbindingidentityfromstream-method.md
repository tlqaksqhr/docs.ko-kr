---
title: "ICLRAssemblyIdentityManager::GetBindingIdentityFromStream 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cd16f13bd77127953bdd17b258c7be518088f899
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="9a205-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream 메서드</span><span class="sxs-lookup"><span data-stu-id="9a205-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="9a205-103">지정한 스트림에 어셈블리에 대 한 정식 어셈블리 id 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a205-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a205-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a205-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9a205-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="9a205-106">[in] 평가할 어셈블리 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9a205-107">[in] 다음 버전의 확장을 위해 제공.</span><span class="sxs-lookup"><span data-stu-id="9a205-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="9a205-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT은 공용 언어 런타임 (CLR)의 현재 버전에서는 지원 되는 유일한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="9a205-109">[out] 불투명 한 어셈블리 id 데이터를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="9a205-110">[out에서] 크기 `pwzBuffer`합니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a205-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="9a205-111">Return Value</span></span>  
  
|<span data-ttu-id="9a205-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a205-112">HRESULT</span></span>|<span data-ttu-id="9a205-113">설명</span><span class="sxs-lookup"><span data-stu-id="9a205-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a205-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a205-114">S_OK</span></span>|<span data-ttu-id="9a205-115">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="9a205-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9a205-116">E_INVALIDARG</span></span>|<span data-ttu-id="9a205-117">제공 된 `pStream` null입니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="9a205-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9a205-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="9a205-119">크기 `pwzBuffer` 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="9a205-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9a205-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9a205-121">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9a205-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9a205-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9a205-123">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-123">The call timed out.</span></span>|  
|<span data-ttu-id="9a205-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a205-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9a205-125">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9a205-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9a205-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9a205-127">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9a205-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9a205-128">E_FAIL</span></span>|<span data-ttu-id="9a205-129">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9a205-130">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9a205-131">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a205-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a205-132">Requirements</span></span>  
 <span data-ttu-id="9a205-133">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a205-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a205-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9a205-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a205-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9a205-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a205-136">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a205-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a205-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a205-137">See Also</span></span>  
 [<span data-ttu-id="9a205-138">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a205-138">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="9a205-139">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a205-139">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
