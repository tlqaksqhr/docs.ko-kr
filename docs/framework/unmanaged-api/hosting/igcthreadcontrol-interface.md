---
title: IGCThreadControl 인터페이스
ms.date: 03/30/2017
api_name:
- IGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCThreadControl
helpviewer_keywords:
- IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9296aedf24979624c3d7357a4d51be835716a16f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438030"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="30fa1-102">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30fa1-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="30fa1-103">가비지 컬렉션에 대 한 차단 될 수 있는 스레드 일정에 참여 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="30fa1-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="30fa1-104">메서드</span><span class="sxs-lookup"><span data-stu-id="30fa1-104">Methods</span></span>  
  
|<span data-ttu-id="30fa1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="30fa1-105">Method</span></span>|<span data-ttu-id="30fa1-106">설명</span><span class="sxs-lookup"><span data-stu-id="30fa1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="30fa1-107">SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="30fa1-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="30fa1-108">런타임 스레드를 다시 시작 가비지 컬렉션이 나 다른 일시 중단 작업 후 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="30fa1-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="30fa1-109">SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="30fa1-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="30fa1-110">가비지 수집 스레드 일시 중단 또는 기타 일시 중단 작업 런타임이 시작 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="30fa1-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="30fa1-111">ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="30fa1-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="30fa1-112">호출한 스레드가 차단 가비지 컬렉션이 나 다른 일시 중단 작업에 대 한를 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="30fa1-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="30fa1-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="30fa1-113">Requirements</span></span>  
 <span data-ttu-id="30fa1-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="30fa1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30fa1-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="30fa1-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30fa1-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="30fa1-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30fa1-117">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30fa1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30fa1-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30fa1-118">See Also</span></span>  
 [<span data-ttu-id="30fa1-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30fa1-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
