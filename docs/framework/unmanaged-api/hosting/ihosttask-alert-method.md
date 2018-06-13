---
title: IHostTask::Alert 메서드
ms.date: 03/30/2017
api_name:
- IHostTask.Alert
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Alert
helpviewer_keywords:
- IHostTask::Alert method [.NET Framework hosting]
- Alert method, IHostTask interface [.NET Framework hosting]
ms.assetid: 5245d4b5-b6c3-48df-9cb9-8caf059f43fb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 057e2aafff726b187f36b8b52859b2f2e812e70e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442366"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="2e800-102">IHostTask::Alert 메서드</span><span class="sxs-lookup"><span data-stu-id="2e800-102">IHostTask::Alert Method</span></span>
<span data-ttu-id="2e800-103">현재 작업의 시작을 호스트 하는 요청 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스 작업을 중단할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e800-103">Requests that the host wake the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e800-104">구문</span><span class="sxs-lookup"><span data-stu-id="2e800-104">Syntax</span></span>  
  
```  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2e800-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="2e800-105">Return Value</span></span>  
  
|<span data-ttu-id="2e800-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e800-106">HRESULT</span></span>|<span data-ttu-id="2e800-107">설명</span><span class="sxs-lookup"><span data-stu-id="2e800-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e800-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e800-108">S_OK</span></span>|<span data-ttu-id="2e800-109">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e800-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="2e800-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2e800-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2e800-111">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e800-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2e800-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2e800-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2e800-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2e800-113">The call timed out.</span></span>|  
|<span data-ttu-id="2e800-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e800-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2e800-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e800-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2e800-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2e800-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2e800-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e800-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2e800-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2e800-118">E_FAIL</span></span>|<span data-ttu-id="2e800-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2e800-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2e800-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e800-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2e800-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e800-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e800-122">설명</span><span class="sxs-lookup"><span data-stu-id="2e800-122">Remarks</span></span>  
 <span data-ttu-id="2e800-123">CLR에서는 `Alert` 메서드 때 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 사용자 코드에서 호출할 경우 또는 <xref:System.AppDomain> 현재와 관련 된 <xref:System.Threading.Thread> 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e800-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="2e800-124">호스트는 호출이 비동기적 이므로 즉시 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e800-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="2e800-125">호스트 작업을 즉시 경고 수 없는 경우 다음에는 경고를 받을 수 상태가 될 때를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e800-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e800-126">`Alert` 런타임에 경과 하는 작업에만 영향을 미칩니다는 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 같은 메서드에 wait_alertable 값 [조인](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2e800-126">`Alert` affects only those tasks to which the runtime has passed a [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e800-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e800-127">Requirements</span></span>  
 <span data-ttu-id="2e800-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2e800-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e800-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2e800-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e800-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2e800-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e800-131">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e800-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e800-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e800-132">See Also</span></span>  
 [<span data-ttu-id="2e800-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e800-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="2e800-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e800-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="2e800-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e800-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="2e800-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e800-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
