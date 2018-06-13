---
title: IHostTask::GetPriority 메서드
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 317223b1ce42924fcd20c44f791b0a24836a3ff8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442191"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="1c70f-102">IHostTask::GetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="1c70f-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="1c70f-103">현재 작업의 스레드 우선 순위 수준을 가져옵니다 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="1c70f-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c70f-104">구문</span><span class="sxs-lookup"><span data-stu-id="1c70f-104">Syntax</span></span>  
  
```  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c70f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1c70f-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="1c70f-106">[out] 현재 작업의 스레드 우선 순위 수준을 나타내는 정수에 대 한 포인터 `IHostTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="1c70f-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c70f-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="1c70f-107">Return Value</span></span>  
  
|<span data-ttu-id="1c70f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1c70f-108">HRESULT</span></span>|<span data-ttu-id="1c70f-109">설명</span><span class="sxs-lookup"><span data-stu-id="1c70f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1c70f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1c70f-110">S_OK</span></span>|<span data-ttu-id="1c70f-111">`GetPriority` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c70f-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="1c70f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1c70f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1c70f-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c70f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1c70f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1c70f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1c70f-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c70f-115">The call timed out.</span></span>|  
|<span data-ttu-id="1c70f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1c70f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1c70f-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c70f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1c70f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1c70f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1c70f-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c70f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1c70f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1c70f-120">E_FAIL</span></span>|<span data-ttu-id="1c70f-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c70f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1c70f-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c70f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1c70f-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c70f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c70f-124">설명</span><span class="sxs-lookup"><span data-stu-id="1c70f-124">Remarks</span></span>  
 <span data-ttu-id="1c70f-125">Win32 스레드 우선 순위 수준 값이 정의 된 `SetThreadPriority` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1c70f-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c70f-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c70f-126">Requirements</span></span>  
 <span data-ttu-id="1c70f-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c70f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c70f-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1c70f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c70f-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1c70f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c70f-130">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c70f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c70f-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c70f-131">See Also</span></span>  
 [<span data-ttu-id="1c70f-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c70f-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="1c70f-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c70f-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="1c70f-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c70f-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="1c70f-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c70f-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
