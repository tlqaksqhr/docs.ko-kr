---
title: COR_GC_THREAD_STATS 구조체
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24a386fe82bbd004954924a573c090af7f58824a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431830"
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="3e55f-102">COR_GC_THREAD_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="3e55f-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="3e55f-103">가비지 수집에 관련 된 스레드 통계를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e55f-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e55f-104">구문</span><span class="sxs-lookup"><span data-stu-id="3e55f-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="3e55f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="3e55f-105">Members</span></span>  
  
|<span data-ttu-id="3e55f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="3e55f-106">Member</span></span>|<span data-ttu-id="3e55f-107">설명</span><span class="sxs-lookup"><span data-stu-id="3e55f-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="3e55f-108">연결 된 현재 스레드에 할당 된 메모리의 바이트 수가 `COR_GC_THREAD_STATS` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="3e55f-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="3e55f-109">이 번호는 0 세대 가비지 수집이 발생할 때마다를 0으로 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="3e55f-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="3e55f-110">바이트 수는 가장 최근의 가비지 수집을 상위 세대로 승격 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e55f-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e55f-111">설명</span><span class="sxs-lookup"><span data-stu-id="3e55f-111">Remarks</span></span>  
 <span data-ttu-id="3e55f-112">[Iclrtask:: Getmemstats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) 형식의 출력 매개 변수를 사용 `COR_GC_THREAD_STATS`합니다.</span><span class="sxs-lookup"><span data-stu-id="3e55f-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e55f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e55f-113">Requirements</span></span>  
 <span data-ttu-id="3e55f-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3e55f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e55f-115">**헤더:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="3e55f-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="3e55f-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3e55f-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e55f-117">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e55f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e55f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e55f-118">See Also</span></span>  
 [<span data-ttu-id="3e55f-119">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="3e55f-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="3e55f-120">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e55f-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
