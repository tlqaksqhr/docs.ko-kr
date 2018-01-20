---
title: "IHostTaskManager::EnterRuntime 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.EnterRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 70c9e83311fd7427895e1957d3511a45c47434e6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="9182c-102">IHostTaskManager::EnterRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="9182c-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="9182c-103">관리 되지 않는 메서드를 호출 하는 플랫폼 호출 메서드를 같은 반환 되는지 실행 제어 공용 언어 런타임 (CLR)를 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9182c-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9182c-104">구문</span><span class="sxs-lookup"><span data-stu-id="9182c-104">Syntax</span></span>  
  
```  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9182c-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="9182c-105">Return Value</span></span>  
  
|<span data-ttu-id="9182c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9182c-106">HRESULT</span></span>|<span data-ttu-id="9182c-107">설명</span><span class="sxs-lookup"><span data-stu-id="9182c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9182c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9182c-108">S_OK</span></span>|<span data-ttu-id="9182c-109">`EnterRuntime`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9182c-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="9182c-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9182c-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9182c-111">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9182c-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9182c-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9182c-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9182c-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9182c-113">The call timed out.</span></span>|  
|<span data-ttu-id="9182c-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9182c-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9182c-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9182c-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9182c-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9182c-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9182c-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="9182c-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9182c-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9182c-118">E_FAIL</span></span>|<span data-ttu-id="9182c-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9182c-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9182c-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9182c-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9182c-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9182c-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9182c-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9182c-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9182c-123">메모리가 부족 하 여 요청 된 할당을 완료 하려면 사용할 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="9182c-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9182c-124">설명</span><span class="sxs-lookup"><span data-stu-id="9182c-124">Remarks</span></span>  
 <span data-ttu-id="9182c-125">`EnterRuntime`호스트에 알리기 위해 호출 됩니다는에 대 한 관리 되지 않는 함수를 호출 하 여 이전는 [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) 메서드, 실행이 끝나면를 만들었고 런타임에 실행 제어를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9182c-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9182c-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) 호스트에 알리기 위해 호출 하는에 대 한 관리 되지 않는 함수를 호출 하 여 이전 `LeaveRuntime` 만들어진, 관리 코드를 호출 하 고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9182c-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9182c-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9182c-127">Requirements</span></span>  
 <span data-ttu-id="9182c-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9182c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9182c-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9182c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9182c-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9182c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9182c-131">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9182c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9182c-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9182c-132">See Also</span></span>  
 [<span data-ttu-id="9182c-133">고급 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="9182c-133">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [<span data-ttu-id="9182c-134">방법: PInvoke를 사용하여 관리 코드로부터 네이티브 DLL 호출</span><span class="sxs-lookup"><span data-stu-id="9182c-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)  
 [<span data-ttu-id="9182c-135">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9182c-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="9182c-136">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9182c-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="9182c-137">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9182c-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="9182c-138">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9182c-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="9182c-139">LeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="9182c-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
