---
title: "IHostSecurityManager::SetThreadToken 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostSecurityManager.SetThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 35418907c2b3c75fef689e53b9d6b86ded1f2570
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="8407d-102">IHostSecurityManager::SetThreadToken 메서드</span><span class="sxs-lookup"><span data-stu-id="8407d-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="8407d-103">현재 실행 중인 스레드에 대 한 핸들을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8407d-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8407d-104">구문</span><span class="sxs-lookup"><span data-stu-id="8407d-104">Syntax</span></span>  
  
```  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8407d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8407d-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="8407d-106">[in] 현재 실행 중인 스레드에 대 한 설정 하는 토큰에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="8407d-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8407d-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="8407d-107">Return Value</span></span>  
  
|<span data-ttu-id="8407d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8407d-108">HRESULT</span></span>|<span data-ttu-id="8407d-109">설명</span><span class="sxs-lookup"><span data-stu-id="8407d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8407d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8407d-110">S_OK</span></span>|<span data-ttu-id="8407d-111">`SetThreadToken`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8407d-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="8407d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8407d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8407d-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8407d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8407d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8407d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8407d-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8407d-115">The call timed out.</span></span>|  
|<span data-ttu-id="8407d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8407d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8407d-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8407d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8407d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8407d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8407d-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="8407d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8407d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8407d-120">E_FAIL</span></span>|<span data-ttu-id="8407d-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8407d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8407d-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8407d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8407d-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8407d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8407d-124">설명</span><span class="sxs-lookup"><span data-stu-id="8407d-124">Remarks</span></span>  
 <span data-ttu-id="8407d-125">`IHostSecurityManager::SetThreadToken`동작 마찬가지로 동일한 이름 가진 해당 Win32 함수에 Win32 함수에서는 임의의 스레드에 대 한 핸들에 전달할 호출자를 허용 한다는 점을 제외 하는 동안 `IHostSecurityManager::SetThreadToken` 현재 실행 중인 스레드와에 토큰을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8407d-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="8407d-126">`HANDLE` 형식이 COM 호환; 즉, 해당 크기는 운영 체제에 적용 하 고 사용자 지정 마샬링 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8407d-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="8407d-127">따라서이 토큰은 CLR과 호스트 간에 프로세스 에서만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8407d-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8407d-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8407d-128">Requirements</span></span>  
 <span data-ttu-id="8407d-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8407d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8407d-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8407d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8407d-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8407d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8407d-132">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8407d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8407d-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8407d-133">See Also</span></span>  
 [<span data-ttu-id="8407d-134">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8407d-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="8407d-135">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8407d-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
