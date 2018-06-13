---
title: IHostTaskManager::BeginThreadAffinity 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginThreadAffinity
helpviewer_keywords:
- IHostTaskManager::BeginThreadAffinity method [.NET Framework hosting]
- BeginThreadAffinity method [.NET Framework hosting]
ms.assetid: fea3ab88-ce41-4c5a-847b-bb78cd748da6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a94797e6279a1f1d419b977c22d73ca41bbafc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443377"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="35fa4-102">IHostTaskManager::BeginThreadAffinity 메서드</span><span class="sxs-lookup"><span data-stu-id="35fa4-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="35fa4-103">현재 작업 이동 하지 말아야 다른 운영 체제 스레드에 마침표를 시작 하는 코드를 관리 하는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="35fa4-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35fa4-104">구문</span><span class="sxs-lookup"><span data-stu-id="35fa4-104">Syntax</span></span>  
  
```  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="35fa4-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="35fa4-105">Return Value</span></span>  
  
|<span data-ttu-id="35fa4-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35fa4-106">HRESULT</span></span>|<span data-ttu-id="35fa4-107">설명</span><span class="sxs-lookup"><span data-stu-id="35fa4-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="35fa4-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="35fa4-108">S_OK</span></span>|<span data-ttu-id="35fa4-109">`BeginThreadAffinity` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="35fa4-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="35fa4-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="35fa4-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="35fa4-111">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35fa4-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="35fa4-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="35fa4-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="35fa4-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35fa4-113">The call timed out.</span></span>|  
|<span data-ttu-id="35fa4-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="35fa4-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="35fa4-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35fa4-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="35fa4-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="35fa4-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="35fa4-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="35fa4-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="35fa4-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="35fa4-118">E_FAIL</span></span>|<span data-ttu-id="35fa4-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="35fa4-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="35fa4-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35fa4-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="35fa4-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="35fa4-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35fa4-122">설명</span><span class="sxs-lookup"><span data-stu-id="35fa4-122">Remarks</span></span>  
 <span data-ttu-id="35fa4-123">CLR은 일반적으로 호출 `IHostTaskManager::BeginThreadAffinity` 에 대 한 호출의 컨텍스트에서 <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="35fa4-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="35fa4-124">현재 작업에 해당 호출을 설정할 때까지 기본적 해야 [ihosttaskmanager:: Endthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="35fa4-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="35fa4-125">작업으로 전환 될 수 있습니다 하지만 다시 전환할 경우 올가 전환 된 동일한 운영 체제 스레드를 할당 받아야 합니다. 에 대 한 호출을 중첩 `BeginThreadAffinity` 효과가 없으며, 호출이 현재 작업에 참조 하기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35fa4-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35fa4-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35fa4-126">Requirements</span></span>  
 <span data-ttu-id="35fa4-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="35fa4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35fa4-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="35fa4-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35fa4-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="35fa4-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35fa4-130">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35fa4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35fa4-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35fa4-131">See Also</span></span>  
 [<span data-ttu-id="35fa4-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35fa4-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="35fa4-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35fa4-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="35fa4-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35fa4-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="35fa4-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35fa4-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
