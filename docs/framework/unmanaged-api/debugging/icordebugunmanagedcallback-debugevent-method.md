---
title: ICorDebugUnmanagedCallback::DebugEvent 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback.DebugEvent
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51ccc7b1b50613f0d2b44a9e101314128782c412
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a>ICorDebugUnmanagedCallback::DebugEvent 메서드
네이티브 이벤트가 발생 했음을 디버거에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pDebugEvent`  
 [in] 네이티브 이벤트에 대 한 포인터입니다.  
  
 `fOutOfBand`  
 [in] `true`불가능 한 경우 관리 되는 프로세스 상태와 상호 작용 디버거 호출할 때까지 관리 되지 않는 이벤트가 발생 한 후, [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md), 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 디버깅 중인 스레드의 Win32 스레드 이면 디버깅 인터페이스는 Win32의 모든 멤버를 사용 하지 마십시오. 호출할 수 있습니다 `ICorDebugController::Continue` 밴드의 범위를 벗어난 이벤트 지 나 계속 하는 경우에 한 Win32 스레드에서 합니다.  
  
 `DebugEvent` 콜백 콜백에 대 한 표준 규칙을 따르지 않습니다. 호출 하는 경우 `DebugEvent`, 해당 프로세스에 원시 수, OS 디버그 상태를 중지 합니다. 프로세스 동기화 되지 않습니다. 중첩 된 다른 발생할 수 있습니다. 관리 코드에 대 한 정보에 대 한 요청을 충족 하기 위해 필요할 경우 동기화 된 상태로 자동 전환 됩니다 `DebugEvent` 콜백 합니다.  
  
 호출 [icordebugprocess:: Clearcurrentexception](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) 과정을 계속 하기 전에 예외 이벤트를 무시 하는 프로세스에 있습니다. 이 메서드를 호출 계속 요청에서 DBG_EXCEPTION_NOT_HANDLED 대신 DBG_CONTINUE 보내고 대역의 중단점 및 단일 단계 예외를 자동으로 지워집니다. 밴드의 범위를 벗어난 이벤트 및 디버깅 중인 응용 프로그램이 표시 중지 된 경우에 뛰어난 대역 이벤트 이미 있는 경우 언제 든 지 가져올 수 있습니다.  
  
 .NET Framework 버전 2.0에서에서 디버거 즉시 대역의 중단점 이벤트 지 나 계속 해야 합니다. 디버거를 사용 해야 합니다는 [icordebugprocess2:: Setunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) 및 [icordebugprocess2:: Clearunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) 메서드를 추가 하 고 중단점을 제거 합니다. 이러한 메서드는 자동으로 대역의 중단점을 통해 건너뜁니다. 따라서 밴드를만 중단점 디스패치되을 원시 중단점 이미 Win32 호출과 같은 명령 스트림의 해야 `DebugBreak` 함수입니다. 사용 하지 마십시오 `ICorDebugProcess::ClearCurrentException`, [icordebugprocess:: Getthreadcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [icordebugprocess:: Setthreadcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), 또는 다른 어떤 멤버도 [디버깅 API](../../../../docs/framework/unmanaged-api/debugging/index.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugUnmanagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
