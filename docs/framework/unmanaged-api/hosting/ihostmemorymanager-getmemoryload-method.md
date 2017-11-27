---
title: "IHostMemoryManager::GetMemoryLoad 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.GetMemoryLoad
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7296790eb80fe90cd115150749e533ce1800834b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="260aa-102">IHostMemoryManager::GetMemoryLoad 메서드</span><span class="sxs-lookup"><span data-stu-id="260aa-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="260aa-103">현재 사용에서 되 고 따라서 호스트에서 보고 있는 실제 메모리의 양을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="260aa-104">구문</span><span class="sxs-lookup"><span data-stu-id="260aa-104">Syntax</span></span>  
  
```  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="260aa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="260aa-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="260aa-106">[out] 현재 사용 중인 총 실제 메모리의 대략적인 백분율에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="260aa-107">[out] 공용 언어 런타임 (CLR)를 사용할 수 있는 바이트 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="260aa-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="260aa-108">Return Value</span></span>  
  
|<span data-ttu-id="260aa-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="260aa-109">HRESULT</span></span>|<span data-ttu-id="260aa-110">설명</span><span class="sxs-lookup"><span data-stu-id="260aa-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="260aa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="260aa-111">S_OK</span></span>|<span data-ttu-id="260aa-112">`GetMemoryLoad`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="260aa-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="260aa-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="260aa-114">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="260aa-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="260aa-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="260aa-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-116">The call timed out.</span></span>|  
|<span data-ttu-id="260aa-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="260aa-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="260aa-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="260aa-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="260aa-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="260aa-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="260aa-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="260aa-121">E_FAIL</span></span>|<span data-ttu-id="260aa-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="260aa-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="260aa-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="260aa-125">설명</span><span class="sxs-lookup"><span data-stu-id="260aa-125">Remarks</span></span>  
 <span data-ttu-id="260aa-126">`GetMemoryLoad`Win32 래핑합니다 `GlobalMemoryStatus` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="260aa-127">값 `pMemoryLoad` 해당는 `dwMemoryLoad` 필드에 `MEMORYSTATUS` 에서 반환 된 구조 `GlobalMemoryStatus`합니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="260aa-128">런타임은은 가비지 수집기에 대 한 휴리스틱으로 반환 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="260aa-129">예를 들어 호스트에서 사용 중인 메모리의 대부분을 보고 가비지 수집기를 사용할 수 있는 상태가 될 수 있는 메모리 양을 늘리려면 여러 세대에서 수집 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="260aa-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="260aa-130">Requirements</span></span>  
 <span data-ttu-id="260aa-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="260aa-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="260aa-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="260aa-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="260aa-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="260aa-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="260aa-134">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="260aa-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="260aa-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="260aa-135">See Also</span></span>  
 <xref:System.GC?displayProperty=nameWithType>  
 [<span data-ttu-id="260aa-136">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="260aa-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
