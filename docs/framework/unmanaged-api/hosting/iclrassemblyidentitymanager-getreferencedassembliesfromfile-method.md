---
title: "ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.GetReferencedAssembliesFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferenceAssembliesFromFile method [.NET Framework hosting]
- GetReferenceAssembliesFromFile method [.NET Framework hosting]
ms.assetid: eed63d31-d977-4c7d-9443-f9d37a2a7d81
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: abd80676fe459bd779d5fad4cf2e9c41e140741b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="e1fbd-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="e1fbd-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>
<span data-ttu-id="e1fbd-103">가져옵니다는 [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) 지정 된 파일 경로에 있는 어셈블리에서 참조 어셈블리의 목록을 포함 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-103">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1fbd-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1fbd-104">Syntax</span></span>  
  
```  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1fbd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1fbd-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="e1fbd-106">[in] 평가할 어셈블리에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e1fbd-107">[in] 다음 버전의 확장을 위해 제공.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="e1fbd-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT은 공용 언어 런타임 (CLR)의 현재 버전에서는 지원 되는 유일한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="e1fbd-109">[in] 에 대 한 포인터는 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 에서 제외 해야 하는 어셈블리를 나타내는 개체 `ppReferenceEnum`합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="e1fbd-110">[out] 주소에 대 한 포인터는 `ICLRReferenceAssemblyEnum` 의 어셈블리에서 참조 하는 어셈블리에 대 한 어셈블리 id 데이터를 포함 하는 개체 `pwzFilePath`가 나타내는 어셈블리 제외 `pExcludeAssembliesList`합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1fbd-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="e1fbd-111">Return Value</span></span>  
  
|<span data-ttu-id="e1fbd-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e1fbd-112">HRESULT</span></span>|<span data-ttu-id="e1fbd-113">설명</span><span class="sxs-lookup"><span data-stu-id="e1fbd-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e1fbd-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e1fbd-114">S_OK</span></span>|<span data-ttu-id="e1fbd-115">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="e1fbd-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e1fbd-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e1fbd-117">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e1fbd-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e1fbd-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e1fbd-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-119">The call timed out.</span></span>|  
|<span data-ttu-id="e1fbd-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e1fbd-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e1fbd-121">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e1fbd-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e1fbd-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e1fbd-123">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e1fbd-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e1fbd-124">E_FAIL</span></span>|<span data-ttu-id="e1fbd-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e1fbd-126">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e1fbd-127">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1fbd-128">설명</span><span class="sxs-lookup"><span data-stu-id="e1fbd-128">Remarks</span></span>  
 <span data-ttu-id="e1fbd-129">호출자에 게 반환된 된 목록에서 어셈블리 참조의 집합을 제외 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="e1fbd-130">이 집합 정의한는 `pExcludeAssembliesList` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1fbd-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1fbd-131">Requirements</span></span>  
 <span data-ttu-id="e1fbd-132">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1fbd-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1fbd-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e1fbd-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1fbd-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e1fbd-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1fbd-135">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1fbd-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1fbd-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1fbd-136">See Also</span></span>  
 [<span data-ttu-id="e1fbd-137">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1fbd-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="e1fbd-138">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1fbd-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="e1fbd-139">ICLRReferenceAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1fbd-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
