---
title: "EPolicyAction 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EPolicyAction
api_location: mscoree.dll
api_type: COM
f1_keywords: EPolicyAction
helpviewer_keywords: EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f2c3a4138adfa354de07bc6df4e51d7697598b67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="4f0e6-102">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="4f0e6-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="4f0e6-103">호스트에서 설명 하는 작업에 대해 설정할 수 정책 작업을 설명 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 에 정의 된 오류 [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f0e6-104">구문</span><span class="sxs-lookup"><span data-stu-id="4f0e6-104">Syntax</span></span>  
  
```  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a><span data-ttu-id="4f0e6-105">멤버</span><span class="sxs-lookup"><span data-stu-id="4f0e6-105">Members</span></span>  
  
|<span data-ttu-id="4f0e6-106">멤버</span><span class="sxs-lookup"><span data-stu-id="4f0e6-106">Member</span></span>|<span data-ttu-id="4f0e6-107">설명</span><span class="sxs-lookup"><span data-stu-id="4f0e6-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="4f0e6-108">공용 언어 런타임 (CLR) 스레드를 적절 하 게 중단 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="4f0e6-109">모든 실행 시도 포함 하는 정상적인 중단 `finally` 모든 차단 `catch` 스레드 중단 및 종료자와 관련 된 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="4f0e6-110">CLR에서 사용할 수 없는 상태를 입력 해야 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="4f0e6-111">영향을 받는 프로세스에 관리 되는 코드를 실행 하는 더 이상 및 clr에서 스레드는 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="4f0e6-112">CLR가 종료자를 실행 하 고 정리 및 로깅 작업 수행을 포함 하는 프로세스의 정상 종료를 시도해 야 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="4f0e6-113">CLR 프로세스를 종료 하도록 즉시 종료자를 실행 하거나 정리 및 로깅 작업을 수행 하지 않고 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="4f0e6-114">디버거에 디버거 알림이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-114">Nowever, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="4f0e6-115">아무 작업도 수행 해야 있는지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="4f0e6-116">CLR가 잘못 된 스레드 중단이 수행 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="4f0e6-117">항목만 `catch` 및 `finally` 블록으로 표시 된 <xref:System.EnterpriseServices.MustRunInClientContextAttribute> 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="4f0e6-118">CLR 종료자를 실행 하거나 작업을 기록 하지 않고 프로세스를 종료 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="4f0e6-119">CLR의 잘못 된 언로드를 수행 하도록 지정 된 <xref:System.AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="4f0e6-120">으로 표시 된 유일한 종료자 <xref:System.EnterpriseServices.MustRunInClientContextAttribute> 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="4f0e6-121">마찬가지로, 모든 스레드가이 <xref:System.AppDomain> 여 스택에 수신는 `ThreadAbortException`, 되지만 `catch` 및 `finally` 블록으로 표시 된 <xref:System.EnterpriseServices.MustRunInClientContextAttribute> 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="4f0e6-122">메모리 부족, 버퍼 오버플로 등과 같은 조건에 적합 한 예외가 발생 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="4f0e6-123">지정 하는 <xref:System.AppDomain> 로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="4f0e6-124">CLR은 종료자를 실행 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f0e6-125">설명</span><span class="sxs-lookup"><span data-stu-id="4f0e6-125">Remarks</span></span>  
 <span data-ttu-id="4f0e6-126">호스트의 메서드를 호출 하 여 정책을 실행 하도록 설정 하는 [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="4f0e6-127">강제 하 고 정상적으로 중단 하는 방법에 대 한 정보를 참조 하십시오.는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-127">For information about rude and graceful aborts, see the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f0e6-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f0e6-128">Requirements</span></span>  
 <span data-ttu-id="4f0e6-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0e6-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f0e6-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4f0e6-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f0e6-131">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f0e6-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f0e6-132">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f0e6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f0e6-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f0e6-133">See Also</span></span>  
 [<span data-ttu-id="4f0e6-134">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="4f0e6-134">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="4f0e6-135">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f0e6-135">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="4f0e6-136">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f0e6-136">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="4f0e6-137">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="4f0e6-137">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
