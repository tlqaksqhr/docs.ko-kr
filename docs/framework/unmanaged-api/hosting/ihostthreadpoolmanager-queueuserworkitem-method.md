---
title: "IHostThreadPoolManager::QueueUserWorkItem 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.QueueUserWorkItem
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::QueueUserWorkItem
helpviewer_keywords:
- IHostThreadPoolManager::QueueUserWorkItem method [.NET Framework hosting]
- QueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 41602053-8670-4827-9d61-cbfcba509b9c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9948673d6988de21c83c37538fb4d7c030296e58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagerqueueuserworkitem-method"></a><span data-ttu-id="bc75d-102">IHostThreadPoolManager::QueueUserWorkItem 메서드</span><span class="sxs-lookup"><span data-stu-id="bc75d-102">IHostThreadPoolManager::QueueUserWorkItem Method</span></span>
<span data-ttu-id="bc75d-103">실행을 위한 함수 큐 대기 하 고 해당 함수에서 사용할 데이터를 포함 하는 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-103">Queues a function for execution, and specifies an object containing data to be used by that function.</span></span> <span data-ttu-id="bc75d-104">스레드를 사용할 수 있게 되 면 함수가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-104">The function executes when a thread becomes available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc75d-105">구문</span><span class="sxs-lookup"><span data-stu-id="bc75d-105">Syntax</span></span>  
  
```  
HRESULT QueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID Context,  
    [in] ULONG Flags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc75d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bc75d-106">Parameters</span></span>  
 `Function`  
 <span data-ttu-id="bc75d-107">[in] 실행 하는 함수를 나타내는 함수 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-107">[in] A function pointer that represents the function to execute.</span></span>  
  
 `Context`  
 <span data-ttu-id="bc75d-108">[in] 사용할 데이터를 포함 하는 개체 `Function`합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-108">[in] An object that contains data to be used by `Function`.</span></span>  
  
 `Flags`  
 <span data-ttu-id="bc75d-109">[in] 값 중 하나는 플래그를 Win32에 대해 정의 된 대로 `QueueUserWorkItem` 실행을 제어 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-109">[in] One of the flags values, as defined for the Win32 `QueueUserWorkItem` method, that control execution.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc75d-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="bc75d-110">Return Value</span></span>  
  
|<span data-ttu-id="bc75d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bc75d-111">HRESULT</span></span>|<span data-ttu-id="bc75d-112">설명</span><span class="sxs-lookup"><span data-stu-id="bc75d-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bc75d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc75d-113">S_OK</span></span>|<span data-ttu-id="bc75d-114">`QueueUserWorkItem`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-114">`QueueUserWorkItem` returned successfully.</span></span>|  
|<span data-ttu-id="bc75d-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bc75d-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bc75d-116">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bc75d-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bc75d-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bc75d-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-118">The call timed out.</span></span>|  
|<span data-ttu-id="bc75d-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bc75d-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bc75d-120">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bc75d-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bc75d-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bc75d-122">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bc75d-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bc75d-123">E_FAIL</span></span>|<span data-ttu-id="bc75d-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bc75d-125">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bc75d-126">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc75d-127">설명</span><span class="sxs-lookup"><span data-stu-id="bc75d-127">Remarks</span></span>  
 <span data-ttu-id="bc75d-128">`QueueUserWorkItem`작업 항목을 스레드 풀에서 작업자 스레드가 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-128">`QueueUserWorkItem` queues a work item to a worker thread in the thread pool.</span></span> <span data-ttu-id="bc75d-129">시그니처 및 매개 변수 형식과 해당 Win32 함수 이름이 같은의 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-129">Its signature and parameter types are identical to those of the corresponding Win32 function, which has the same name.</span></span> <span data-ttu-id="bc75d-130">자세한 내용은 Windows 플랫폼 설명서를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc75d-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc75d-131">Requirements</span></span>  
 <span data-ttu-id="bc75d-132">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75d-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc75d-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bc75d-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bc75d-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="bc75d-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc75d-135">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc75d-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc75d-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc75d-136">See Also</span></span>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="bc75d-137">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc75d-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
