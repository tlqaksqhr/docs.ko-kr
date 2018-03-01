---
title: "EMemoryCriticalLevel 열거형"
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
- EMemoryCriticalLevel
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryCriticalLevel
helpviewer_keywords:
- EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4fb279402b2b677546f775b9a8badfbe2095fe4f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ememorycriticallevel-enumeration"></a><span data-ttu-id="0d928-102">EMemoryCriticalLevel 열거형</span><span class="sxs-lookup"><span data-stu-id="0d928-102">EMemoryCriticalLevel Enumeration</span></span>
<span data-ttu-id="0d928-103">특정 메모리 할당이 요청 되었으나 처리할 수 없는 경우 오류가 끼치는 영향을 표시 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-103">Contains values that indicate the impact of a failure when a specific memory allocation has been requested but cannot be satisfied.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d928-104">구문</span><span class="sxs-lookup"><span data-stu-id="0d928-104">Syntax</span></span>  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a><span data-ttu-id="0d928-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0d928-105">Members</span></span>  
  
|<span data-ttu-id="0d928-106">멤버</span><span class="sxs-lookup"><span data-stu-id="0d928-106">Member</span></span>|<span data-ttu-id="0d928-107">설명</span><span class="sxs-lookup"><span data-stu-id="0d928-107">Description</span></span>|  
|------------|-----------------|  
|`eAppDomainCritical`|<span data-ttu-id="0d928-108">할당 된 할당에서 요청한 도메인의 관리 되는 코드 실행에 대 한 중요 한 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-108">Indicates that the allocation is critical for executing managed code in the domain that has requested the allocation.</span></span> <span data-ttu-id="0d928-109">메모리를 할당할 수 없으면 CLR 도메인을 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-109">If memory cannot be allocated, the CLR cannot guarantee that the domain is still usable.</span></span> <span data-ttu-id="0d928-110">호스트에 할당할 수 없는 경우 수행할 작업을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-110">The host decides what action to take when the allocation cannot be satisfied.</span></span> <span data-ttu-id="0d928-111">중단 하는 CLR에 지시할 수 있습니다는 `AppDomain` 자동으로 하거나에서 메서드를 호출 하 여 계속 해 서 실행을 허용할 [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-111">It can instruct the CLR to abort the `AppDomain` automatically, or allow it to keep running by calling methods on [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>|  
|`eProcessCritical`|<span data-ttu-id="0d928-112">할당 프로세스에서 관리 코드의 실행에 매우 중요 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-112">Indicates that the allocation is critical to the execution of managed code in the process.</span></span> <span data-ttu-id="0d928-113">이 값은 종료자를 실행할 때 시작 하는 동안 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-113">This value is used during startup and when running finalizers.</span></span> <span data-ttu-id="0d928-114">메모리를 할당할 수 없으면 CLR 프로세스에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-114">If memory cannot be allocated, the CLR cannot operate in the process.</span></span> <span data-ttu-id="0d928-115">할당이 실패 하면 CLR 효과적으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-115">If the allocation fails, the CLR is effectively disabled.</span></span> <span data-ttu-id="0d928-116">모든 후속 호출을 CLR HOST_E_CLRNOTAVAILABLE 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-116">All subsequent calls into the CLR fail with HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`eTaskCritical`|<span data-ttu-id="0d928-117">할당 작업 할당 요청을 실행 하려면 반드시 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-117">Indicates that the allocation is critical to running the task that has requested the allocation.</span></span> <span data-ttu-id="0d928-118">메모리를 할당할 수 없으면 CLR 태스크가 실행 될 수 있도록 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-118">If memory cannot be allocated, the CLR cannot guarantee that the task can be executed.</span></span> <span data-ttu-id="0d928-119">CLR 장애가 발생 한 <xref:System.Threading.ThreadAbortException> 실제 운영 체제 스레드에서에 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-119">In the event of failure, the CLR raises a <xref:System.Threading.ThreadAbortException> on the physical operation system thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d928-120">설명</span><span class="sxs-lookup"><span data-stu-id="0d928-120">Remarks</span></span>  
 <span data-ttu-id="0d928-121">에 정의 된 메모리 할당 메서드는 [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) 및 [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) 인터페이스는이 형식의 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-121">The memory allocation methods defined in the [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) and [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) interfaces take a parameter of this type.</span></span> <span data-ttu-id="0d928-122">오류의 심각도에 따라, 호스트 여부를 결정할 수 즉시 할당 요청에 실패 하거나 수 충족 될 때까지 기다려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-122">Depending upon the severity of a failure, a host can decide whether to fail the allocation request immediately or to wait until it can be satisfied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d928-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d928-123">Requirements</span></span>  
 <span data-ttu-id="0d928-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0d928-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d928-125">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d928-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d928-126">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d928-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d928-127">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d928-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d928-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d928-128">See Also</span></span>  
 [<span data-ttu-id="0d928-129">ICLRMemoryNotificationCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d928-129">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [<span data-ttu-id="0d928-130">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="0d928-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
