---
title: ICorDebugThread Interface1
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
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2df43a35e510695d7af0c38cbb8fb3b051f5f354
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread-interface1"></a>ICorDebugThread Interface1
프로세스의 스레드를 나타냅니다. `ICorDebugThread` 인스턴스의 수명은 이 인스턴스가 나타내는 스레드의 수명과 같습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ClearCurrentException 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|이 메서드가 구현되지 않았습니다. 이 메서드를 사용하지 마십시오.|  
|[CreateEval 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|이 작동 하는 ICorDebugEval 개체를 만듭니다 `ICorDebugThread`합니다.|  
|[CreateStepper 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|이 활성 프레임을 단계별로 실행을 허용 하는 ICorDebugStepper 개체를 만듭니다 `ICorDebugThread`합니다.|  
|[EnumerateChains 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|이 스택 체인을 모두 포함 하는 ICorDebugChainEnum 열거자에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread`합니다.|  
|[GetActiveChain 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|이 활성 ICorDebugChain에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread`합니다.|  
|[GetActiveFrame 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|이 활성 ICorDebugFrame에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread`합니다.|  
|[GetAppDomain 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|이 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread` 현재 실행 합니다.|  
|[GetCurrentException 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|현재 관리 되는 코드에 의해 throw 되는 예외를 나타내는 ICorDebugValue 개체에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetDebugState 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|이 현재 디버그 상태를 설명 하는 CorDebugThreadState 값을 가져옵니다 `ICorDebugThread`합니다.|  
|[GetHandle 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|이의 활성 부분에 대 한 현재 핸들을 가져옵니다 `ICorDebugThread`합니다.|  
|[GetID 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|이의 활성 부분의 현재 운영 체제 식별자를 가져옵니다 `ICorDebugThread`합니다.|  
|[GetObject 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|공용 언어 런타임 (CLR) 스레드에서에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetProcess 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|이 프로세스에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread` 일부를 구성 합니다.|  
|[GetRegisterSet 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|이 연결 된 레지스터 세트에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugThread`합니다.|  
|[GetUserState 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|이 항목의 현재 상태를 설명 하는 CorDebugUserState 값의 비트 조합 가져옵니다 `ICorDebugThread`합니다.|  
|[SetDebugState 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|설정의 비트 조합 `CorDebugThreadState` 이 디버깅 상태를 설명 하는 값 `ICorDebugThread`합니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
