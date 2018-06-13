---
title: COR_SEGMENT 구조체
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b816087f54e652f07dc791b7d66eb1af8f52f55e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406509"
---
# <a name="corsegment-structure"></a>COR_SEGMENT 구조체
관리되는 힙의 메모리 영역에 대한 정보를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`start`|시작 주소 메모리 영역입니다.|  
|`end`|메모리 영역의 끝 주소입니다.|  
|`gen`|A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) 메모리 영역 생성을 나타내는 열거형 멤버입니다.|  
|`heap`|메모리 영역 프로시저가 있는 힙 수입니다. 자세한 내용은 설명 부분을 참조하세요.|  
  
## <a name="remarks"></a>설명  
 `COR_SEGMENTS` 구조체의 관리 되는 힙의 메모리 영역을 나타냅니다.  `COR_SEGMENTS` 개체의 멤버인는 [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) 호출 하 여 되는 컬렉션 개체는[icordebugprocess5:: Enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) 메서드.  
  
 `heap` 필드는 보고 되 고 힙에 해당 하는 프로세서 수입니다. 워크스테이션 가비지 수집기에 대 한 해당 값은 항상 0 워크스테이션 가비지 수집 힙에서 하나만 포함 되어 있습니다. 서버 가비지 수집기에 대 한 해당 값에 연결 된 힙 프로세서에 해당 합니다. Note 있을 수 있음을 가비지 수집이 더 많거나 적은 실제 프로세서는 가비지 수집기의 구현 정보로 인해 보다 힙.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
