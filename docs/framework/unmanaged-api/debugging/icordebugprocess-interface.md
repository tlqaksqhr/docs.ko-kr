---
title: ICorDebugProcess Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess
helpviewer_keywords: ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ee526a79d89a9e4e3483daa07a512b6b7f920e70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess-interface1"></a>ICorDebugProcess Interface1
관리 코드를 실행하는 프로세스를 나타냅니다. 이 인터페이스는 ICorDebugController의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ClearCurrentException 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|지정 된 스레드에 대해 현재 관리 되지 않는 예외를 지웁니다.|  
|[EnableLogMessages 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|사용 하도록 설정 하 고 디버거에 로그 메시지를 보낼 수 없게 합니다.|  
|[EnumerateAppDomains 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|모든 프로세스에서 응용 프로그램 도메인을 열거합니다.|  
|[EnumerateObjects 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|구현되지 않았습니다.|  
|[GetHandle 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|프로세스에 대 한 핸들을 가져옵니다.|  
|[GetHelperThreadID 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|디버거의 내부 도우미 스레드가 대 한 운영 체제 (OS) 스레드 ID를 가져옵니다.|  
|[GetID 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|프로세스의 운영 체제 (OS) ID를 가져옵니다.|  
|[GetObject 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|구현되지 않았습니다.|  
|[GetThread 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|Id를 가져옵니다에 지정 된 운영 체제 스레드가 ICorDebugThread 인스턴스입니다.|  
|[GetThreadContext 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|지정 된 스레드의 컨텍스트를 가져옵니다.|  
|[IsOSSuspended 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|디버거가 프로세스를 중지의 결과 스레드가 일시 중단 된 있는지 여부를 결정 합니다.|  
|[IsTransitionStub 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|관리 코드에 전환 하는 스텁 내부 주소 인지 확인 합니다.|  
|[ModifyLogSwitch 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|지정 된 로그 스위치의 심각도 수준을 설정합니다.|  
|[ReadMemory 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|프로세스에서 메모리를 읽습니다.|  
|[SetThreadContext 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|지정 된 스레드에 대 한 컨텍스트를 설정합니다.|  
|[ThreadForFiberCookie 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|더 이상 사용되지 않습니다.|  
|[WriteMemory 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|프로세스의 메모리 영역에 데이터를 기록합니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
