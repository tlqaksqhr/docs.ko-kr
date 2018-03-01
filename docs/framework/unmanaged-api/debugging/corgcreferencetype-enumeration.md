---
title: "CorGCReferenceType 열거형"
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
- CorGCReferenceType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorGCReferenceType
helpviewer_keywords:
- CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b314580f7628eca68a3996aaafb362081c6ed705
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corgcreferencetype-enumeration"></a>CorGCReferenceType 열거형
가비지가 수집될 개체의 소스를 식별합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a>멤버  
  
|멤버 이름|설명|  
|-----------------|-----------------|  
|`CorHandleStrong`|개체 참조 테이블의 강력한 참조에 대한 핸들입니다.|  
|`CorHandleStrongPinning`|개체 핸들 테이블의 고정 된 강력한 참조에 대 한 핸들입니다.|  
|`CorHandleWeakShort`|개체 핸들 테이블의 약한 참조에 대 한 핸들입니다.|  
|`CorHandleWeakRefCount`|개체 핸들 테이블의 약한 참조 횟수가 계산 개체에 대 한 핸들입니다.|  
|`CorHandleStrongRefCount`|개체 핸들 테이블의 참조 횟수가 계산 개체에 대 한 핸들입니다.|  
|`CorHandleStrongDependent`|개체 핸들 테이블의 종속 개체에 대 한 핸들입니다.|  
|`CorHandleStrongAsyncPinned`|개체 핸들 테이블의 비동기 고정된 개체입니다.|  
|`CorHandleStrongSizedByref`|가비지 컬렉션 시 모든 개체 및 개체 루트의 집합 클로저의 대략적인 크기를 유지하는 강력한 핸들입니다. |  
|`CorReferenceStack`|관리 되는 스택에서 대 한 참조입니다.|  
|`CorReferenceFinalizer`|종료자 큐의 참조입니다.|  
|CorHandleStrongOnly|핸들 테이블의 강력한 참조만를 반환 합니다. 이 값에서 사용 되는 [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) 메서드만 합니다.|  
|`CorHandleWeakOnly`|핸들 테이블의 약한 참조만를 반환 합니다. 이 값에서 사용 되는 [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) 메서드만 합니다.|  
|`CorHandleAll`|핸들 테이블의 모든 참조를 반환 합니다. 이 값에서 사용 되는 [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) 메서드만 합니다.|  
  
## <a name="remarks"></a>설명  
 `CorGCReferenceType` 열거형 다음과 같이 사용 됩니다.  
  
-   값으로는 `type` 필드는 [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) 구조, 참조 또는 핸들의 원본을 나타냅니다.  
  
-   로 `types` 인수에는 [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) 메서드를 열거에 포함 하는 핸들의 형식을 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
