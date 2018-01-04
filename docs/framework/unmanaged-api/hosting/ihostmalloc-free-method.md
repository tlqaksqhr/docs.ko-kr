---
title: "IHostMAlloc::Free 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMAlloc.Free
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4775b6ae00f34d7d046515f8700a35470b2f6650
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="faa89-102">IHostMAlloc::Free 메서드</span><span class="sxs-lookup"><span data-stu-id="faa89-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="faa89-103">사용 하 여 할당 된 메모리를 해제는 [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="faa89-103">Frees memory that was allocated by using the [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faa89-104">구문</span><span class="sxs-lookup"><span data-stu-id="faa89-104">Syntax</span></span>  
  
```  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="faa89-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="faa89-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="faa89-106">[in] 해제할 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="faa89-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="faa89-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="faa89-107">Return Value</span></span>  
  
|<span data-ttu-id="faa89-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="faa89-108">HRESULT</span></span>|<span data-ttu-id="faa89-109">설명</span><span class="sxs-lookup"><span data-stu-id="faa89-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="faa89-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="faa89-110">S_OK</span></span>|<span data-ttu-id="faa89-111">`Free`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa89-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="faa89-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="faa89-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="faa89-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faa89-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="faa89-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="faa89-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="faa89-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="faa89-115">The call timed out.</span></span>|  
|<span data-ttu-id="faa89-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="faa89-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="faa89-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa89-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="faa89-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="faa89-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="faa89-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa89-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="faa89-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="faa89-120">E_FAIL</span></span>|<span data-ttu-id="faa89-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="faa89-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="faa89-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="faa89-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="faa89-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa89-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="faa89-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="faa89-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="faa89-125">호스트를 통해 할당 되지 않은 메모리를 해제 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="faa89-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="faa89-126">설명</span><span class="sxs-lookup"><span data-stu-id="faa89-126">Remarks</span></span>  
 <span data-ttu-id="faa89-127">경우는 `pMem` 매개 변수 참조에 대 한 호출을 사용 하 여 할당 되지 않은 메모리 영역 `Alloc`, 호스트 HOST_E_INVALIDOPERATION 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa89-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faa89-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="faa89-128">Requirements</span></span>  
 <span data-ttu-id="faa89-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="faa89-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faa89-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="faa89-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="faa89-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="faa89-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="faa89-132">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faa89-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faa89-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="faa89-133">See Also</span></span>  
 [<span data-ttu-id="faa89-134">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="faa89-134">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="faa89-135">IHostMalloc 인터페이스</span><span class="sxs-lookup"><span data-stu-id="faa89-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
