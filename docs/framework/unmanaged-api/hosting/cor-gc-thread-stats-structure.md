---
title: "COR_GC_THREAD_STATS 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_THREAD_STATS
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_THREAD_STATS
helpviewer_keywords: COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10366d183ed7fd7386609e4c5726df0cea4e29a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="a48ec-102">COR_GC_THREAD_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="a48ec-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="a48ec-103">가비지 수집에 관련 된 스레드 통계를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a48ec-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a48ec-104">구문</span><span class="sxs-lookup"><span data-stu-id="a48ec-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="a48ec-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a48ec-105">Members</span></span>  
  
|<span data-ttu-id="a48ec-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a48ec-106">Member</span></span>|<span data-ttu-id="a48ec-107">설명</span><span class="sxs-lookup"><span data-stu-id="a48ec-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="a48ec-108">연결 된 현재 스레드에 할당 된 메모리의 바이트 수가 `COR_GC_THREAD_STATS` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="a48ec-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="a48ec-109">이 번호는 0 세대 가비지 수집이 발생할 때마다를 0으로 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="a48ec-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="a48ec-110">바이트 수는 가장 최근의 가비지 수집을 상위 세대로 승격 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a48ec-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a48ec-111">설명</span><span class="sxs-lookup"><span data-stu-id="a48ec-111">Remarks</span></span>  
 <span data-ttu-id="a48ec-112">[Iclrtask:: Getmemstats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) 형식의 출력 매개 변수를 사용 `COR_GC_THREAD_STATS`합니다.</span><span class="sxs-lookup"><span data-stu-id="a48ec-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a48ec-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a48ec-113">Requirements</span></span>  
 <span data-ttu-id="a48ec-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a48ec-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a48ec-115">**헤더:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="a48ec-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="a48ec-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a48ec-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a48ec-117">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a48ec-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a48ec-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a48ec-118">See Also</span></span>  
 [<span data-ttu-id="a48ec-119">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="a48ec-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="a48ec-120">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a48ec-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
