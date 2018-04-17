---
title: ICLRSyncManager 인터페이스
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 17a1e3073713b54cb7a68e6ba3ef2562d4fbcaeb
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="02c1f-102">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02c1f-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="02c1f-103">요청 된 작업에 대 한 정보를 가져오려면 호스트가 동기화 구현에서 교착 상태를 감지 하는 데 사용할 수 있는 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="02c1f-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02c1f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="02c1f-104">Methods</span></span>  
  
|<span data-ttu-id="02c1f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="02c1f-105">Method</span></span>|<span data-ttu-id="02c1f-106">설명</span><span class="sxs-lookup"><span data-stu-id="02c1f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="02c1f-107">CreateRWLockOwnerIterator 메서드</span><span class="sxs-lookup"><span data-stu-id="02c1f-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="02c1f-108">공용 언어 런타임 (CLR) 판독기 및 작성기 잠금에 대해 대기 중인 작업의 집합을 결정 하는 데 호스트에 대 한 반복기를 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="02c1f-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="02c1f-109">DeleteRWLockOwnerIterator 메서드</span><span class="sxs-lookup"><span data-stu-id="02c1f-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="02c1f-110">CLR로 호출 하 여 생성 된 반복기 손상 요청 `CreateRWLockOwnerIterator`합니다.</span><span class="sxs-lookup"><span data-stu-id="02c1f-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="02c1f-111">GetMonitorOwner 메서드</span><span class="sxs-lookup"><span data-stu-id="02c1f-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="02c1f-112">지정 된 모니터를 소유 하는 작업을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="02c1f-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="02c1f-113">GetRWLockOwnerNext 메서드</span><span class="sxs-lookup"><span data-stu-id="02c1f-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="02c1f-114">현재 판독기 / 작성기 잠금을 기다리고 있는 다음 작업을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="02c1f-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02c1f-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02c1f-115">Requirements</span></span>  
 <span data-ttu-id="02c1f-116">**플랫폼:** 참조 [시스템 요구 사항](../../get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="02c1f-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02c1f-117">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="02c1f-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02c1f-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="02c1f-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02c1f-119">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02c1f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c1f-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02c1f-120">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="02c1f-121">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02c1f-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)  
 <span data-ttu-id="02c1f-122">[관리 되는 관리 되지 않는 스레딩](https://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="02c1f-122">[Managed and Unmanaged Threading](https://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5(v=vs.100))</span></span>  
 [<span data-ttu-id="02c1f-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02c1f-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
