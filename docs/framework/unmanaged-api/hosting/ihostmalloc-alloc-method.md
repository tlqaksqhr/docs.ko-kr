---
title: IHostMAlloc::Alloc 메서드
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Alloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Alloc
helpviewer_keywords:
- Alloc method, IHostMAlloc interface [.NET Framework hosting]
- IHostMAlloc::Alloc method [.NET Framework hosting]
ms.assetid: a3007f5e-d75d-4b37-842b-704e9edced5e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d67704aae80113bd41df5ea38acf2a794aacbac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439048"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="83beb-102">IHostMAlloc::Alloc 메서드</span><span class="sxs-lookup"><span data-stu-id="83beb-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="83beb-103">호스트 힙에서 지정된 된 양의 메모리를 할당 하는 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="83beb-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83beb-104">구문</span><span class="sxs-lookup"><span data-stu-id="83beb-104">Syntax</span></span>  
  
```  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83beb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="83beb-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="83beb-106">[in] 현재 메모리 할당 요청을 바이트 단위로 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="83beb-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="83beb-107">[in] 중 하나는 [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) 할당 오류의 영향을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="83beb-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="83beb-108">[out] 할당 된 메모리 또는 요청을 완료할 수 없으면 null에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="83beb-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83beb-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="83beb-109">Return Value</span></span>  
  
|<span data-ttu-id="83beb-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="83beb-110">HRESULT</span></span>|<span data-ttu-id="83beb-111">설명</span><span class="sxs-lookup"><span data-stu-id="83beb-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="83beb-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="83beb-112">S_OK</span></span>|<span data-ttu-id="83beb-113">`Alloc` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="83beb-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="83beb-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="83beb-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="83beb-115">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83beb-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="83beb-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="83beb-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="83beb-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83beb-117">The call timed out.</span></span>|  
|<span data-ttu-id="83beb-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="83beb-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="83beb-119">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83beb-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="83beb-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="83beb-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="83beb-121">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="83beb-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="83beb-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="83beb-122">E_FAIL</span></span>|<span data-ttu-id="83beb-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="83beb-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="83beb-124">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83beb-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="83beb-125">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="83beb-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="83beb-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="83beb-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="83beb-127">충분 한 메모리가 할당 요청을 완료 하는 사용할 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="83beb-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83beb-128">설명</span><span class="sxs-lookup"><span data-stu-id="83beb-128">Remarks</span></span>  
 <span data-ttu-id="83beb-129">CLR에 대 한 인터페이스 포인터를 가져옵니다는 `IHostMalloc` 호출 하 여 인스턴스는 [ihostmemorymanager:: Createmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="83beb-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83beb-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="83beb-130">Requirements</span></span>  
 <span data-ttu-id="83beb-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="83beb-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83beb-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="83beb-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83beb-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="83beb-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83beb-134">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83beb-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83beb-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83beb-135">See Also</span></span>  
 [<span data-ttu-id="83beb-136">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83beb-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="83beb-137">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83beb-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
