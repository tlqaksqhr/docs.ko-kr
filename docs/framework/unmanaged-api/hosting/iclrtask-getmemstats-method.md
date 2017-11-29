---
title: "ICLRTask::GetMemStats 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.GetMemStats
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 11537989765d721830c33cb137d1814327b02e14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="43055-102">ICLRTask::GetMemStats 메서드</span><span class="sxs-lookup"><span data-stu-id="43055-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="43055-103">작업에 관련 된 메모리 통계 사용 정보를 가져옵니다는 현재 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스가 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="43055-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43055-104">구문</span><span class="sxs-lookup"><span data-stu-id="43055-104">Syntax</span></span>  
  
```  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43055-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="43055-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="43055-106">[out] 에 대 한 포인터는 [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) 할당 된 바이트 수를 포함 하 여 작업의 메모리 사용에 대 한 세부 정보가 포함 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="43055-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43055-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="43055-107">Return Value</span></span>  
  
|<span data-ttu-id="43055-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="43055-108">HRESULT</span></span>|<span data-ttu-id="43055-109">설명</span><span class="sxs-lookup"><span data-stu-id="43055-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43055-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="43055-110">S_OK</span></span>|<span data-ttu-id="43055-111">`GetMemStats`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="43055-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="43055-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="43055-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="43055-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43055-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="43055-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="43055-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="43055-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="43055-115">The call timed out.</span></span>|  
|<span data-ttu-id="43055-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="43055-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="43055-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="43055-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="43055-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="43055-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="43055-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="43055-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="43055-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="43055-120">E_FAIL</span></span>|<span data-ttu-id="43055-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="43055-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="43055-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43055-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="43055-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="43055-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43055-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43055-124">Requirements</span></span>  
 <span data-ttu-id="43055-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="43055-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43055-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="43055-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43055-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="43055-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43055-128">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43055-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43055-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43055-129">See Also</span></span>  
 [<span data-ttu-id="43055-130">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43055-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="43055-131">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43055-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="43055-132">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43055-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="43055-133">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43055-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
