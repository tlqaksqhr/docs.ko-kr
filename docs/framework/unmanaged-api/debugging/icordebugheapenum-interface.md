---
title: "ICorDebugHeapEnum 인터페이스"
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
- ICorDebugHeapEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum
helpviewer_keywords:
- ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e317cb24e0eeaeaa38833433791eb546ee3c0478
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapenum-interface"></a>ICorDebugHeapEnum 인터페이스
관리되는 힙의 개체에 대한 열거자를 제공합니다. 이 인터페이스는 ICorDebugEnum 인터페이스의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Next 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)|지정된 된 수의 가져옵니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 관리 되는 힙의 개체에 대 한 정보가 포함 된 인스턴스.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugHeapEnum` ICorDebugEnum 인터페이스를 구현 하는 인터페이스입니다.  
  
 `ICorDebugHeapEnum` 인스턴스 채워집니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 호출 하 여 인스턴스는 [icordebugprocess5:: Enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) 메서드. 각 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 컬렉션의 인스턴스가 나타내는 힙에 대 한 활성 개체 또는 개체는 모든 개체에서 루트에서 시작 하지 않지만 아직 가비지 수집기가 수집 되지 않았습니다. [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 호출 하 여 컬렉션의 개체를 열거할 수는 [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
