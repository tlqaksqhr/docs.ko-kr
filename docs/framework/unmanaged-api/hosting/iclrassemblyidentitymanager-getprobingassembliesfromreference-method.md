---
title: "ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f255db046f4c7d698ad864723167e81952481519
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="65d04-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference 메서드</span><span class="sxs-lookup"><span data-stu-id="65d04-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="65d04-103">가져옵니다는 [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) 지정 된 id 유형 사용 하 여 어셈블리에서 참조 한 어셈블리 id에 대 한 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="65d04-103">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65d04-104">구문</span><span class="sxs-lookup"><span data-stu-id="65d04-104">Syntax</span></span>  
  
```  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65d04-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="65d04-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="65d04-106">[in] WinNT.h에 정의 된 프로세서 아키텍처를 지정 하는 유효한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="65d04-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="65d04-107">[in] 다음 버전의 확장을 위해 제공.</span><span class="sxs-lookup"><span data-stu-id="65d04-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="65d04-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT은 공용 언어 런타임 (CLR)의 현재 버전에서는 지원 되는 유일한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="65d04-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="65d04-109">[in] 일반적으로 호출에서 반환 되는 불투명 한 어셈블리 바인딩 id에는 [iclrassemblyidentitymanager:: Getbindingidentityfromfile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) 또는 [iclrassemblyidentitymanager:: Getbindingidentityfromstream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="65d04-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="65d04-110">[out] 에 대 한 인터페이스 포인터는 `ICLRProbingAssemblyEnum` 로 식별 되는 어셈블리에서 참조 하는 어셈블리에 대 한 참조를 포함 하는 열거자 `pwzReferenceIdentity`합니다.</span><span class="sxs-lookup"><span data-stu-id="65d04-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65d04-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="65d04-111">Return Value</span></span>  
  
|<span data-ttu-id="65d04-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65d04-112">HRESULT</span></span>|<span data-ttu-id="65d04-113">설명</span><span class="sxs-lookup"><span data-stu-id="65d04-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65d04-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="65d04-114">S_OK</span></span>|<span data-ttu-id="65d04-115">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d04-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="65d04-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="65d04-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="65d04-117">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65d04-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="65d04-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="65d04-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="65d04-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="65d04-119">The call timed out.</span></span>|  
|<span data-ttu-id="65d04-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="65d04-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="65d04-121">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65d04-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="65d04-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="65d04-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="65d04-123">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d04-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="65d04-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65d04-124">E_FAIL</span></span>|<span data-ttu-id="65d04-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="65d04-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="65d04-126">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65d04-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="65d04-127">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="65d04-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="65d04-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="65d04-128">Requirements</span></span>  
 <span data-ttu-id="65d04-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="65d04-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65d04-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="65d04-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65d04-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="65d04-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65d04-132">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65d04-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65d04-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65d04-133">See Also</span></span>  
 [<span data-ttu-id="65d04-134">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65d04-134">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="65d04-135">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65d04-135">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="65d04-136">ICLRProbingAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65d04-136">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
