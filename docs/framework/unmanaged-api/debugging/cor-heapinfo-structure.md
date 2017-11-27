---
title: "COR_HEAPINFO 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_HEAPINFO
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_HEAPINFO
helpviewer_keywords: COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e316b964e3e983f50b81228709623e162529b05c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="corheapinfo-structure"></a>COR_HEAPINFO 구조체
가비지 컬렉션 힙에 대한 일반 정보(열거 가능 여부 포함)를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`areGCStructuresValid`|`true`가비지 수집 구조 유효 하 고 힙을 열거할 수 있는 경우 그렇지 않으면 `false`합니다.|  
|`pointerSize`|대상 아키텍처에 대 한 포인터의 바이트 크기입니다.|  
|`numHeaps`|프로세스에서 힙의 논리 가비지 수집의 수입니다.|  
|`concurrent`|`TRUE`동시 하는 경우 (백그라운드) 가비지 수집이 설정 되어 있습니다. 그렇지 않으면 `FALSE`합니다.|  
|`gcType`|멤버는 [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) 가비지 수집기는 워크스테이션 또는 서버에서 실행 되 고 있는지를 나타내는 열거형입니다.|  
  
## <a name="remarks"></a>설명  
 인스턴스는 `COR_HEAPINFO` 구조를 호출 하 여 반환 되는 [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) 메서드.  
  
 가비지 컬렉션 힙에서 개체를 열거 하기 전에 항상 체크는 `areGCStructuresValid` 필드 힙을 열거 가능한 상태 인지 확인 합니다. 자세한 내용은 참조는 [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
