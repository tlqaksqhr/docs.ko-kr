---
title: "ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aae8c16430f8139601a5faa2bad42e285bceb84b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="14a67-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream 메서드</span><span class="sxs-lookup"><span data-stu-id="14a67-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>
<span data-ttu-id="14a67-103">에 대 한 포인터를 가져옵니다는 [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) 에 지정된 된 스트림에 있는 어셈블리에서 참조 하는 어셈블리에 대 한 어셈블리 id 데이터를 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14a67-104">구문</span><span class="sxs-lookup"><span data-stu-id="14a67-104">Syntax</span></span>  
  
```  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="14a67-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="14a67-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="14a67-106">[in] 에 대 한 인터페이스 포인터는 `IStream` 평가할 어셈블리가 포함 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="14a67-107">[in] 다음 버전의 확장을 위해 제공.</span><span class="sxs-lookup"><span data-stu-id="14a67-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="14a67-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT은 공용 언어 런타임 (CLR)의 현재 버전에서는 지원 되는 유일한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="14a67-109">[in] 에 대 한 포인터는 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 에서 제외할 어셈블리에 대 한 어셈블리 id 데이터를 포함 하는 개체 `ppReferenceEnum`합니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="14a67-110">[out] 주소에 대 한 포인터는 `ICLRReferenceAssemblyEnum` 에 있는 어셈블리에서 참조 하는 어셈블리에 대 한 어셈블리 id 데이터를 포함 하는 개체 `pStream`, 어셈블리를 제외 하 고 `pExcludeAssembliesList`합니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14a67-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="14a67-111">Return Value</span></span>  
  
|<span data-ttu-id="14a67-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14a67-112">HRESULT</span></span>|<span data-ttu-id="14a67-113">설명</span><span class="sxs-lookup"><span data-stu-id="14a67-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14a67-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="14a67-114">S_OK</span></span>|<span data-ttu-id="14a67-115">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="14a67-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="14a67-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="14a67-117">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="14a67-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="14a67-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="14a67-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-119">The call timed out.</span></span>|  
|<span data-ttu-id="14a67-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="14a67-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="14a67-121">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="14a67-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="14a67-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="14a67-123">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="14a67-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="14a67-124">E_FAIL</span></span>|<span data-ttu-id="14a67-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="14a67-126">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="14a67-127">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14a67-128">설명</span><span class="sxs-lookup"><span data-stu-id="14a67-128">Remarks</span></span>  
 <span data-ttu-id="14a67-129">호출자에 게 반환된 된 목록에서 어셈블리 참조의 집합을 제외 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="14a67-130">이 집합 정의한 `pExcludeAssembliesList`합니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14a67-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="14a67-131">Requirements</span></span>  
 <span data-ttu-id="14a67-132">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="14a67-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14a67-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="14a67-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14a67-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="14a67-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14a67-135">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14a67-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14a67-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14a67-136">See Also</span></span>  
 [<span data-ttu-id="14a67-137">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="14a67-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="14a67-138">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="14a67-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="14a67-139">ICLRReferenceAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="14a67-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
