---
title: "COR_GC_STATS 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_STATS
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_STATS
helpviewer_keywords: COR_GC_STATS structure [.NET Framework hosting]
ms.assetid: 8d4ff73e-739b-40f6-9349-359fbc99c2f9
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e7c620c4a33032711abc0d7b82af908018bd44cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="corgcstats-structure"></a><span data-ttu-id="ecdac-102">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="ecdac-102">COR_GC_STATS Structure</span></span>
<span data-ttu-id="ecdac-103">공용 언어 런타임 (CLR)의 가비지 수집 메커니즘에 대 한 통계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-103">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecdac-104">구문</span><span class="sxs-lookup"><span data-stu-id="ecdac-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_STATS {  
    ULONG   Flags;   
    SIZE_T  ExplicitGCCount;  
    SIZE_T  GenCollectionsTaken[3];  
    SIZE_T  CommittedKBytes;   
    SIZE_T  ReservedKBytes;  
    SIZE_T  Gen0HeapSizeKBytes;  
    SIZE_T  Gen1HeapSizeKBytes;  
    SIZE_T  Gen2HeapSizeKBytes;  
    SIZE_T  LargeObjectHeapSizeKBytes;  
    SIZE_T  KBytesPromotedFromGen0;  
    SIZE_T  KBytesPromotedFromGen1;  
} COR_GC_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="ecdac-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ecdac-105">Members</span></span>  
  
|<span data-ttu-id="ecdac-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ecdac-106">Member</span></span>|<span data-ttu-id="ecdac-107">설명</span><span class="sxs-lookup"><span data-stu-id="ecdac-107">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="ecdac-108">계산 고 반환 하는 필드 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-108">Indicates which field values should be calculated and returned.</span></span>|  
|`ExplicitGCCount`|<span data-ttu-id="ecdac-109">외부 요청에서 강제 된 가비지 컬렉션 횟수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-109">Indicates the number of garbage collections that were forced by external request.</span></span>|  
|`GenCollectionsTaken`|<span data-ttu-id="ecdac-110">각 세대에 대해 수행 된 가비지 수집의 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-110">Indicates the number of garbage collections performed for each generation.</span></span>|  
|`CommittedKBytes`|<span data-ttu-id="ecdac-111">커밋된 모든 힙의 (킬로바이트)의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-111">The total number of kilobytes committed in all heaps.</span></span>|  
|`ReservedKBytes`|<span data-ttu-id="ecdac-112">모든 힙의 예약 (킬로바이트)의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-112">The total number of kilobytes reserved in all heaps.</span></span>|  
|`Gen0HeapSizeKBytes`|<span data-ttu-id="ecdac-113">0 세대 힙의 킬로바이트 단위로 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-113">The size, in kilobytes, of the generation-zero heap.</span></span>|  
|`Gen1HeapSizeKBytes`|<span data-ttu-id="ecdac-114">(킬로바이트)의 1 세대 힙의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-114">The size, in kilobytes, of the generation-one heap.</span></span>|  
|`Gen2HeapSizeKBytes`|<span data-ttu-id="ecdac-115">(킬로바이트) 2 세대 힙의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-115">The size, in kilobytes, of the generation-two heap.</span></span>|  
|`LargeObjectHeapSizeKBytes`|<span data-ttu-id="ecdac-116">큰 개체 힙 (킬로바이트)에서 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-116">The size, in kilobytes, of the large object heap.</span></span>|  
|`KBytesPromotedFromGen0`|<span data-ttu-id="ecdac-117">(킬로바이트) 0 세대에서 1 세대로 수준이 올려진 개체의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-117">The size, in kilobytes, of the objects promoted from generation zero to generation one.</span></span>|  
|`KBytesPromotedFromGen1`|<span data-ttu-id="ecdac-118">(킬로바이트), 1 세대에서 2 세대로 수준이 올려진 개체의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-118">The size, in kilobytes, of the objects promoted from generation one to generation two.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecdac-119">설명</span><span class="sxs-lookup"><span data-stu-id="ecdac-119">Remarks</span></span>  
 <span data-ttu-id="ecdac-120">[iclrgcmanager:: Getstats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) 메서드를 사용 하려면는 `Flags` 필드는 `COR_GC_STATS` 의 하나 이상의 값으로 설정 하는 구조는 [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) 열거형을 지정 합니다. 통계는 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-120">The [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method requires the `Flags` field of the `COR_GC_STATS` structure to be set to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics are to be set.</span></span>  
  
 <span data-ttu-id="ecdac-121">다음 표에서이 구조를 두 개의에서 제공 하는 통계 [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) 열거형 값 `COR_GC_COUNTS` 및 `COR_GC_MEMORYUSAGE`합니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-121">The following table maps the statistics provided by this structure to the two [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration values, `COR_GC_COUNTS` and `COR_GC_MEMORYUSAGE`.</span></span>  
  
|<span data-ttu-id="ecdac-122">COR_GC_COUNTS로 지정 된</span><span class="sxs-lookup"><span data-stu-id="ecdac-122">Specified by COR_GC_COUNTS</span></span>|<span data-ttu-id="ecdac-123">COR_GC_MEMORYUSAGE로 지정 된</span><span class="sxs-lookup"><span data-stu-id="ecdac-123">Specified by COR_GC_MEMORYUSAGE</span></span>|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 <span data-ttu-id="ecdac-124">사용의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-124">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="ecdac-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ecdac-125">Requirements</span></span>  
 <span data-ttu-id="ecdac-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ecdac-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecdac-127">**헤더:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="ecdac-127">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="ecdac-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ecdac-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ecdac-129">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecdac-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecdac-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ecdac-130">See Also</span></span>  
 [<span data-ttu-id="ecdac-131">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="ecdac-131">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="ecdac-132">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="ecdac-132">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="ecdac-133">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="ecdac-133">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
