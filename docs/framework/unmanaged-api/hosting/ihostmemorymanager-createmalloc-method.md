---
title: "IHostMemoryManager::CreateMAlloc 메서드"
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
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 19b43ccf7cb2429c28c052ab8ab3a009ec4a30a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="11e9d-102">IHostMemoryManager::CreateMAlloc 메서드</span><span class="sxs-lookup"><span data-stu-id="11e9d-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="11e9d-103">한 인터페이스 포인터를 가져옵니다는 [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) 호스트에서 만든 힙에서 할당 요청을 만드는 사용 되는 인스턴스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e9d-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11e9d-104">구문</span><span class="sxs-lookup"><span data-stu-id="11e9d-104">Syntax</span></span>  
  
```  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11e9d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11e9d-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="11e9d-106">[in] 조합을 [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) 할당 되는 메모리의 특성을 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="11e9d-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="11e9d-107">[out] 주소에 대 한 포인터는 `IHostMAlloc` 인스턴스가 호스트에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="11e9d-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11e9d-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="11e9d-108">Return Value</span></span>  
  
|<span data-ttu-id="11e9d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11e9d-109">HRESULT</span></span>|<span data-ttu-id="11e9d-110">설명</span><span class="sxs-lookup"><span data-stu-id="11e9d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11e9d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="11e9d-111">S_OK</span></span>|<span data-ttu-id="11e9d-112">`CreateMAlloc`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="11e9d-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="11e9d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="11e9d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="11e9d-114">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11e9d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="11e9d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="11e9d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="11e9d-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="11e9d-116">The call timed out.</span></span>|  
|<span data-ttu-id="11e9d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="11e9d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="11e9d-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11e9d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="11e9d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="11e9d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="11e9d-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="11e9d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="11e9d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="11e9d-121">E_FAIL</span></span>|<span data-ttu-id="11e9d-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="11e9d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="11e9d-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11e9d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="11e9d-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="11e9d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="11e9d-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="11e9d-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="11e9d-126">실제 메모리가 부족 했습니다을 할당 요청을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11e9d-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11e9d-127">설명</span><span class="sxs-lookup"><span data-stu-id="11e9d-127">Remarks</span></span>  
 <span data-ttu-id="11e9d-128">`CreateMAlloc`CLR 표준 Win32 함수를 사용 하는 대신 호스트를 통해 할당 요청을 만드는 수 있는 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="11e9d-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11e9d-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11e9d-129">Requirements</span></span>  
 <span data-ttu-id="11e9d-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11e9d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11e9d-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="11e9d-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11e9d-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="11e9d-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11e9d-133">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11e9d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11e9d-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11e9d-134">See Also</span></span>  
 [<span data-ttu-id="11e9d-135">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11e9d-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [<span data-ttu-id="11e9d-136">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11e9d-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
