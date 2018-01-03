---
title: "ICorDebugHeapSegmentEnum 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHealRegionEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapSegmentEnum
helpviewer_keywords: ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b477631b5920401127d34b2304485bd32c3d78f5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapsegmentenum-interface"></a>ICorDebugHeapSegmentEnum 인터페이스
관리되는 힙 메모리 영역에 대한 열거자를 제공합니다. 이 인터페이스는 ICorDebugEnum 인터페이스의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Next 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|지정된 된 수의 가져옵니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 관리 영역에 대 한 정보가 포함 된 인스턴스에 있습니다.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugHeapSegmentEnum` ICorDebugEnum 인터페이스를 구현 하는 인터페이스입니다.  
  
 `ICorDebugHeapSegmentEnum` 인스턴스 채워집니다 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 호출 하 여 인스턴스는 [icordebugprocess5:: Enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) 메서드. [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 호출 하 여 컬렉션의 개체를 열거할 수는 [icordebugheapsegmentenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) 메서드.  
  
 `ICorDebugHeapSegmentEnum` 컬렉션 개체에는 관리 되는 개체를 포함할 수 있는 모든 메모리 영역 열거 하지만 관리 되는 개체 실제로에 상주 하는 해당 영역 보장 하지 않습니다. 비어 있거나 예약 된 메모리 영역에 대 한 정보를 포함할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
