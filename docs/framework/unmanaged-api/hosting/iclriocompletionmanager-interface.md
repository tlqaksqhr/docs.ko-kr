---
title: "ICLRIoCompletionManager 인터페이스"
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
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99dc183674abaff33047f070c14794150a8615f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="65985-102">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65985-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="65985-103">구현 상태를 지정 된 I/O의 공용 언어 런타임 (CLR)에 알리기 위해 호스트를 허용 하는 콜백 메서드를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="65985-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65985-104">메서드</span><span class="sxs-lookup"><span data-stu-id="65985-104">Methods</span></span>  
  
|<span data-ttu-id="65985-105">메서드</span><span class="sxs-lookup"><span data-stu-id="65985-105">Method</span></span>|<span data-ttu-id="65985-106">설명</span><span class="sxs-lookup"><span data-stu-id="65985-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65985-107">OnComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="65985-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="65985-108">에 대 한 호출을 사용 하 여 작성 된 I/O 요청의 상태 CLR 알립니다는 [ihostiocompletionmanager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="65985-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65985-109">설명</span><span class="sxs-lookup"><span data-stu-id="65985-109">Remarks</span></span>  
 <span data-ttu-id="65985-110">호스트를 사용 하 여 I/O 완료 추상화를 구현 하는 [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="65985-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="65985-111">이 인터페이스를 통해 CLR에서는 I/O 요청 하 고 호스트를 사용 하 여 이러한 요청의 결과 런타임에 알립니다는 `ICLRIoCompletionManager` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="65985-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65985-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="65985-112">Requirements</span></span>  
 <span data-ttu-id="65985-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="65985-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65985-114">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="65985-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65985-115">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="65985-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65985-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65985-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65985-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65985-117">See Also</span></span>  
 [<span data-ttu-id="65985-118">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65985-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="65985-119">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65985-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 [<span data-ttu-id="65985-120">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65985-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
