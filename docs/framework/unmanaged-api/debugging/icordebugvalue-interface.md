---
title: ICorDebugValue Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0fe53490014a2a7d9acc0a426613af54867599e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugvalue-interface1"></a>ICorDebugValue Interface1
디버깅 중인 프로세스에 값을 나타냅니다. 읽기 또는 쓰기 값 값일 수 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateBreakpoint 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|이 메서드가 현재 구현 되지 않습니다.|  
|[GetAddress 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|이 주소를 가져옵니다 `ICorDebugValue` 디버깅 중인 프로세스에 있는 개체입니다.|  
|[GetSize 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|이 바이트 단위로 크기를 가져옵니다 `ICorDebugValue` 개체입니다.|  
|[GetType 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|이 기본 형식을 가져옵니다 `ICorDebugValue` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 일반적으로 반환 될 때 값 개체의 소유권 전달 됩니다. 수신자는 개체와 함께 완료 되었을 때 개체에서 참조를 제거 합니다.  
  
 값이 검색 하는 위치에 따라 값 남아 있을 수 없습니다 유효한 프로세스를 다시 시작한 다음 합니다. 따라서 일반적으로 값 안 보유할 수의 호출 간에 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 메서드.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
    
    
    
    
 [ICorDebugValue3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
