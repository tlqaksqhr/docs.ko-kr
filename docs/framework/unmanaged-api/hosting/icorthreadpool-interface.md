---
title: "ICorThreadpool 인터페이스"
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
- ICorThreadpool
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorThreadpool
helpviewer_keywords:
- ICorThreadpool interface [.NET Framework hosting]
ms.assetid: 18485a27-cae3-4c6a-baa8-f7df601122d5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d7b6ec470fae6adb76a9b78fdab9b871edc0ca49
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorthreadpool-interface"></a><span data-ttu-id="e7e48-102">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7e48-102">ICorThreadpool Interface</span></span>
<span data-ttu-id="e7e48-103">스레드 풀에 액세스 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e48-103">Provides methods for accessing the thread pool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7e48-104">이 인터페이스는 내부 용도로 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e48-104">This interface is reserved for internal use only.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7e48-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e7e48-105">Methods</span></span>  
  
|<span data-ttu-id="e7e48-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e7e48-106">Method</span></span>|<span data-ttu-id="e7e48-107">설명</span><span class="sxs-lookup"><span data-stu-id="e7e48-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e7e48-108">CorRegisterWaitForSingleObject 메서드</span><span class="sxs-lookup"><span data-stu-id="e7e48-108">CorRegisterWaitForSingleObject Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-corregisterwaitforsingleobject-method.md)|<span data-ttu-id="e7e48-109">내부용으로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e48-109">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="e7e48-110">CorUnregisterWait 메서드</span><span class="sxs-lookup"><span data-stu-id="e7e48-110">CorUnregisterWait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-corunregisterwait-method.md)|<span data-ttu-id="e7e48-111">내부용으로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e48-111">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="e7e48-112">CorQueueUserWorkItem 메서드</span><span class="sxs-lookup"><span data-stu-id="e7e48-112">CorQueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-corqueueuserworkitem-method.md)|<span data-ttu-id="e7e48-113">내부용으로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e48-113">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="e7e48-114">CorCreateTimer 메서드</span><span class="sxs-lookup"><span data-stu-id="e7e48-114">CorCreateTimer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-corcreatetimer-method.md)|<span data-ttu-id="e7e48-115">내부용으로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e48-115">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="e7e48-116">CorChangeTimer 메서드</span><span class="sxs-lookup"><span data-stu-id="e7e48-116">CorChangeTimer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-corchangetimer-method.md)|<span data-ttu-id="e7e48-117">내부용으로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e48-117">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="e7e48-118">CorDeleteTimer 메서드</span><span class="sxs-lookup"><span data-stu-id="e7e48-118">CorDeleteTimer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-cordeletetimer-method.md)|<span data-ttu-id="e7e48-119">내부용으로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e48-119">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="e7e48-120">CorBindIoCompletionCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="e7e48-120">CorBindIoCompletionCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-corbindiocompletioncallback-method.md)|<span data-ttu-id="e7e48-121">내부용으로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e48-121">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="e7e48-122">CorCallOrQueueUserWorkItem 메서드</span><span class="sxs-lookup"><span data-stu-id="e7e48-122">CorCallOrQueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-corcallorqueueuserworkitem-method.md)|<span data-ttu-id="e7e48-123">내부용으로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e48-123">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="e7e48-124">CorSetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="e7e48-124">CorSetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-corsetmaxthreads-method.md)|<span data-ttu-id="e7e48-125">내부용으로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e48-125">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="e7e48-126">CorGetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="e7e48-126">CorGetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-corgetmaxthreads-method.md)|<span data-ttu-id="e7e48-127">내부용으로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e48-127">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="e7e48-128">CorGetAvailableThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="e7e48-128">CorGetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-corgetavailablethreads-method.md)|<span data-ttu-id="e7e48-129">내부용으로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7e48-129">Reserved for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e7e48-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e7e48-130">Requirements</span></span>  
 <span data-ttu-id="e7e48-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7e48-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7e48-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e7e48-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7e48-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e7e48-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7e48-134">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7e48-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e48-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7e48-135">See Also</span></span>  
 [<span data-ttu-id="e7e48-136">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e7e48-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
