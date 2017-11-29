---
title: "IGCThreadControl 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCThreadControl
helpviewer_keywords: IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 66afef7dec0637e98249838ae06ae6f1161df3f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="fb9fc-102">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb9fc-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="fb9fc-103">가비지 컬렉션에 대 한 차단 될 수 있는 스레드 일정에 참여 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb9fc-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fb9fc-104">메서드</span><span class="sxs-lookup"><span data-stu-id="fb9fc-104">Methods</span></span>  
  
|<span data-ttu-id="fb9fc-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fb9fc-105">Method</span></span>|<span data-ttu-id="fb9fc-106">설명</span><span class="sxs-lookup"><span data-stu-id="fb9fc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fb9fc-107">SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="fb9fc-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="fb9fc-108">런타임 스레드를 다시 시작 가비지 컬렉션이 나 다른 일시 중단 작업 후 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fb9fc-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="fb9fc-109">SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="fb9fc-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="fb9fc-110">가비지 수집 스레드 일시 중단 또는 기타 일시 중단 작업 런타임이 시작 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fb9fc-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="fb9fc-111">ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="fb9fc-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="fb9fc-112">호출한 스레드가 차단 가비지 컬렉션이 나 다른 일시 중단 작업에 대 한를 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fb9fc-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb9fc-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb9fc-113">Requirements</span></span>  
 <span data-ttu-id="fb9fc-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb9fc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb9fc-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fb9fc-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb9fc-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="fb9fc-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb9fc-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb9fc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb9fc-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb9fc-118">See Also</span></span>  
 [<span data-ttu-id="fb9fc-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb9fc-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
