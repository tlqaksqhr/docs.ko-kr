---
title: "COR_HEAPOBJECT 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_HEAPOBJECT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_HEAPOBJECT
helpviewer_keywords: COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 476d9dcb1c6700833b0a113028bdaaf0c5a375c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corheapobject-structure"></a>COR_HEAPOBJECT 구조체
관리되는 힙의 개체에 대한 정보를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`address`|메모리에 있는 개체의 주소입니다.|  
|`size`|전체 크기 (바이트)에서 개체입니다.|  
|`type`|A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 개체의 형식을 나타내는 토큰입니다.|  
  
## <a name="remarks"></a>설명  
 `COR_HEAPOBJECT`인스턴스를 열거 하 여 검색할 수는 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) 인터페이스 개체를 호출 하 여 채워지는 [icordebugprocess5:: Enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) 메서드.  
  
 A `COR_HEAPOBJECT` 인스턴스 또는 관리 되는 힙에 대 한 활성 개체에 대 한 모든 개체에서 루트에서 시작 하지 않지만 아직 가비지 수집기가 수집 되지 않았습니다 하는 개체에 대 한 정보를 제공 합니다.  
  
 성능 향상을 위해는 `COR_HEAPOBJECT.address` 필드는는 `CORDB_ADDRESS` 는 ICorDebugValue이 아닌 값 인터페이스 대부분의 디버깅 API에서 사용 되는 값입니다. 지정 된 개체 주소에 대 한 ICorDebugValue 개체를 가져오려면 전달할 수 있습니다는 `CORDB_ADDRESS` 값을 [icordebugprocess5:: Getobject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) 메서드.  
  
 성능 향상을 위해는 `COR_HEAPOBJECT.type` 필드는는 `COR_TYPEID` 는 ICorDebugType이 아닌 값 인터페이스 대부분의 디버깅 API에서 사용 되는 값입니다. ICorDebugType 개체 ID를 지정 된 형식에 대 한를 가져오려면 전달할 수 있습니다는 `COR_TYPEID` 값을 [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) 메서드.  
  
 `COR_HEAPOBJECT` 구조에는 참조 횟수가 계산 COM 인터페이스에 포함 됩니다. 검색 하는 경우는 `COR_HEAPOBJECT` 호출 하 여 열거자에서 인스턴스는 [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) 메서드를 이후에 대 한 참조를 해제 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
