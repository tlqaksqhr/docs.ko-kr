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
# <a name="corgcstats-structure"></a>COR_GC_STATS 구조체
공용 언어 런타임 (CLR)의 가비지 수집 메커니즘에 대 한 통계를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`Flags`|계산 고 반환 하는 필드 값을 나타냅니다.|  
|`ExplicitGCCount`|외부 요청에서 강제 된 가비지 컬렉션 횟수를 나타냅니다.|  
|`GenCollectionsTaken`|각 세대에 대해 수행 된 가비지 수집의 수를 나타냅니다.|  
|`CommittedKBytes`|커밋된 모든 힙의 (킬로바이트)의 총 수입니다.|  
|`ReservedKBytes`|모든 힙의 예약 (킬로바이트)의 총 수입니다.|  
|`Gen0HeapSizeKBytes`|0 세대 힙의 킬로바이트 단위로 크기입니다.|  
|`Gen1HeapSizeKBytes`|(킬로바이트)의 1 세대 힙의 크기입니다.|  
|`Gen2HeapSizeKBytes`|(킬로바이트) 2 세대 힙의 크기입니다.|  
|`LargeObjectHeapSizeKBytes`|큰 개체 힙 (킬로바이트)에서 크기입니다.|  
|`KBytesPromotedFromGen0`|(킬로바이트) 0 세대에서 1 세대로 수준이 올려진 개체의 크기입니다.|  
|`KBytesPromotedFromGen1`|(킬로바이트), 1 세대에서 2 세대로 수준이 올려진 개체의 크기입니다.|  
  
## <a name="remarks"></a>설명  
 [iclrgcmanager:: Getstats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) 메서드를 사용 하려면는 `Flags` 필드는 `COR_GC_STATS` 의 하나 이상의 값으로 설정 하는 구조는 [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) 열거형을 지정 합니다. 통계는 설정 해야 합니다.  
  
 다음 표에서이 구조를 두 개의에서 제공 하는 통계 [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) 열거형 값 `COR_GC_COUNTS` 및 `COR_GC_MEMORYUSAGE`합니다.  
  
|COR_GC_COUNTS로 지정 된|COR_GC_MEMORYUSAGE로 지정 된|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 사용의 예는 다음과 같습니다.  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** GCHost.idl  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 구조체](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [자동 메모리 관리](../../../../docs/standard/automatic-memory-management.md)  
 [가비지 수집](../../../../docs/standard/garbage-collection/index.md)
