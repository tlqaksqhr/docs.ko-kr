---
title: "IHostCrst 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst
helpviewer_keywords: IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 59485d7a642ba8b3233d5d077062e89fb2ac9b14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostcrst-interface"></a><span data-ttu-id="82a2a-102">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82a2a-102">IHostCrst Interface</span></span>
<span data-ttu-id="82a2a-103">스레딩에 대 한 임계 영역 호스트의 표시로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82a2a-103">Serves as the host's representation of a critical section for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="82a2a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="82a2a-104">Methods</span></span>  
  
|<span data-ttu-id="82a2a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="82a2a-105">Method</span></span>|<span data-ttu-id="82a2a-106">설명</span><span class="sxs-lookup"><span data-stu-id="82a2a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="82a2a-107">Enter 메서드</span><span class="sxs-lookup"><span data-stu-id="82a2a-107">Enter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|<span data-ttu-id="82a2a-108">임계 영역을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="82a2a-108">Enters the critical section.</span></span>|  
|[<span data-ttu-id="82a2a-109">Leave 메서드</span><span class="sxs-lookup"><span data-stu-id="82a2a-109">Leave Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|<span data-ttu-id="82a2a-110">임계 영역을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="82a2a-110">Leaves the critical section.</span></span>|  
|[<span data-ttu-id="82a2a-111">SetSpinCount 메서드</span><span class="sxs-lookup"><span data-stu-id="82a2a-111">SetSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|<span data-ttu-id="82a2a-112">임계 영역에 대 한 스핀 수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="82a2a-112">Sets the spin count for the critical section.</span></span>|  
|[<span data-ttu-id="82a2a-113">TryEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="82a2a-113">TryEnter Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|<span data-ttu-id="82a2a-114">임계 영역 및 보고서 성공 또는 실패를 즉시 입력 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a2a-114">Attempts to enter the critical section, and reports success or failure immediately.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82a2a-115">설명</span><span class="sxs-lookup"><span data-stu-id="82a2a-115">Remarks</span></span>  
 <span data-ttu-id="82a2a-116">`IHostCrst`공용 언어 런타임 임계 영역, 호스트의 표시와 직접 통신할 수 (CLR)와 같은 Win32 함수를 사용 하는 대신 허용 `EnterCriticalSection` 또는 `LeaveCriticalSection`합니다.</span><span class="sxs-lookup"><span data-stu-id="82a2a-116">`IHostCrst` allows the common language runtime (CLR) to communicate directly with the host's representation of a critical section, rather than using Win32 functions such as `EnterCriticalSection` or `LeaveCriticalSection`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82a2a-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82a2a-117">Requirements</span></span>  
 <span data-ttu-id="82a2a-118">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82a2a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82a2a-119">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="82a2a-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82a2a-120">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="82a2a-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82a2a-121">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82a2a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a2a-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82a2a-122">See Also</span></span>  
 [<span data-ttu-id="82a2a-123">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82a2a-123">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="82a2a-124">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82a2a-124">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="82a2a-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82a2a-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
