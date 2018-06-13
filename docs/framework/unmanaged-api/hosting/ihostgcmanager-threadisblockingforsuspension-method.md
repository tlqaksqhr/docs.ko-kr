---
title: IHostGCManager::ThreadIsBlockingForSuspension 메서드
ms.date: 03/30/2017
api_name:
- IHostGCManager.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85921156860f52eb2a898e6be356e191c2a4f02d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439272"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="5a347-102">IHostGCManager::ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="5a347-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="5a347-103">메서드 호출이 만들어진 스레드는 호스트에 알려 줍니다 가비지 수집에 대 한 차단 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a347-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a347-104">구문</span><span class="sxs-lookup"><span data-stu-id="5a347-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5a347-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="5a347-105">Return Value</span></span>  
  
|<span data-ttu-id="5a347-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5a347-106">HRESULT</span></span>|<span data-ttu-id="5a347-107">설명</span><span class="sxs-lookup"><span data-stu-id="5a347-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a347-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a347-108">S_OK</span></span>|<span data-ttu-id="5a347-109">`ThreadIsBlockingForSuspension` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a347-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="5a347-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5a347-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5a347-111">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a347-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5a347-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5a347-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5a347-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5a347-113">The call timed out.</span></span>|  
|<span data-ttu-id="5a347-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5a347-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5a347-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a347-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5a347-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5a347-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5a347-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a347-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5a347-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5a347-118">E_FAIL</span></span>|<span data-ttu-id="5a347-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5a347-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5a347-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a347-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5a347-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a347-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a347-122">설명</span><span class="sxs-lookup"><span data-stu-id="5a347-122">Remarks</span></span>  
 <span data-ttu-id="5a347-123">CLR은 일반적으로 호출는 `ThreadIsBlockForSuspension` 메서드 호스트 관리 되지 않는 작업에 대 한 스레드를 다시 예약할 수 있도록 가비지 수집을 위해 준비에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a347-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5a347-124">호스트에 대 한 호출 후에 작업을 볼 수 `ThreadIsBlockingForSuspension`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a347-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="5a347-125">런타임 호출 후 [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)를 호스트 해야 작업 일정을 변경 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a347-125">After the runtime calls [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a347-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a347-126">Requirements</span></span>  
 <span data-ttu-id="5a347-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a347-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a347-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5a347-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a347-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5a347-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a347-130">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a347-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a347-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a347-131">See Also</span></span>  
 [<span data-ttu-id="5a347-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a347-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="5a347-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a347-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="5a347-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a347-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="5a347-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a347-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="5a347-136">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a347-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
