---
title: "ICLRTask::RudeAbort 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.RudeAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df1f688ec3f58ae7317a4fed0dd70cffc1647045
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="80016-102">ICLRTask::RudeAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="80016-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="80016-103">공용 언어 런타임 (CLR)를 나타내는 현재 작업을 중단 하도록 지시 [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스 즉시 및 무조건 합니다.</span><span class="sxs-lookup"><span data-stu-id="80016-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80016-104">구문</span><span class="sxs-lookup"><span data-stu-id="80016-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="80016-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="80016-105">Return Value</span></span>  
  
|<span data-ttu-id="80016-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80016-106">HRESULT</span></span>|<span data-ttu-id="80016-107">설명</span><span class="sxs-lookup"><span data-stu-id="80016-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80016-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="80016-108">S_OK</span></span>|<span data-ttu-id="80016-109">`RudeAbort`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="80016-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="80016-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="80016-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="80016-111">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80016-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="80016-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="80016-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="80016-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80016-113">The call timed out.</span></span>|  
|<span data-ttu-id="80016-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="80016-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="80016-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80016-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="80016-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="80016-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="80016-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="80016-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="80016-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="80016-118">E_FAIL</span></span>|<span data-ttu-id="80016-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="80016-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="80016-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80016-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="80016-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="80016-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80016-122">설명</span><span class="sxs-lookup"><span data-stu-id="80016-122">Remarks</span></span>  
 <span data-ttu-id="80016-123">호출 하는 호스트 `RudeAbort` 즉시 작업을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="80016-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="80016-124">종료자 및 예외 처리 루틴 실행을 보장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80016-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80016-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="80016-125">Requirements</span></span>  
 <span data-ttu-id="80016-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="80016-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80016-127">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="80016-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80016-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="80016-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80016-129">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80016-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80016-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80016-130">See Also</span></span>  
 [<span data-ttu-id="80016-131">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80016-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="80016-132">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80016-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="80016-133">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80016-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="80016-134">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="80016-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
