---
title: "ICLRPolicyManager::SetUnhandledExceptionPolicy 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 59ff5cfd93d8077388694ee2e155133a88319c47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="c7797-102">ICLRPolicyManager::SetUnhandledExceptionPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="c7797-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="c7797-103">처리 되지 않은 예외가 발생할 때 공용 언어 런타임 (CLR)의 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7797-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7797-104">구문</span><span class="sxs-lookup"><span data-stu-id="c7797-104">Syntax</span></span>  
  
```  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7797-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7797-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="c7797-106">[in] 중 하나는 [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) 동작은 CLR 또는 호스트에 의해 설정 되었는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c7797-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7797-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="c7797-107">Return Value</span></span>  
  
|<span data-ttu-id="c7797-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7797-108">HRESULT</span></span>|<span data-ttu-id="c7797-109">설명</span><span class="sxs-lookup"><span data-stu-id="c7797-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7797-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7797-110">S_OK</span></span>|<span data-ttu-id="c7797-111">`SetUnhandledExceptionPolicy`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7797-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="c7797-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c7797-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c7797-113">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7797-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c7797-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c7797-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c7797-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c7797-115">The call timed out.</span></span>|  
|<span data-ttu-id="c7797-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c7797-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c7797-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7797-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c7797-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c7797-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c7797-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7797-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c7797-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c7797-120">E_FAIL</span></span>|<span data-ttu-id="c7797-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c7797-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c7797-122">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7797-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c7797-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7797-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7797-124">설명</span><span class="sxs-lookup"><span data-stu-id="c7797-124">Remarks</span></span>  
 <span data-ttu-id="c7797-125">기본적으로 CLR은 모든 처리 되지 않은 예외에 대 한 최종 처리기 및 프로세스를 종료 하는 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="c7797-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="c7797-126">호스트 설정 하 여이 동작을 변경할 수는 `policy` 값 eHostDeterminedPolicy입니다.</span><span class="sxs-lookup"><span data-stu-id="c7797-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="c7797-127">이 값에는 이전 버전의 CLR과 마찬가지로 기본 동작을 구현 하는 호스트 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7797-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7797-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7797-128">Requirements</span></span>  
 <span data-ttu-id="c7797-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7797-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7797-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c7797-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7797-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c7797-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7797-132">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7797-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7797-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7797-133">See Also</span></span>  
 [<span data-ttu-id="c7797-134">EClrUnhandledException 열거형</span><span class="sxs-lookup"><span data-stu-id="c7797-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)  
 [<span data-ttu-id="c7797-135">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7797-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="c7797-136">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7797-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="c7797-137">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7797-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
