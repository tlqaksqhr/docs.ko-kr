---
title: ICorDebugChain Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32889a8e8867fc42b48413463095dda423f26b85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugchain-interface1"></a>ICorDebugChain Interface1
실제 또는 논리 호출 스택의 세그먼트를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumerateFrames 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|가장 최근의 프레임부터 체인에 있는 모든 관리 되는 스택 프레임을 포함 하는 열거자를 가져옵니다.|  
|[GetActiveFrame 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|활성 가져옵니다 (즉, 가장 최근의) 프레임 체인에 있습니다.|  
|[GetCallee 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|이 체인에 의해 호출 된 체인을 가져옵니다.|  
|[GetCaller 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|이 체인을 호출한 체인을 가져옵니다.|  
|[GetContext 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|구현되지 않았습니다.|  
|[GetNext 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|스레드 프레임의 다음 체인을 가져옵니다.|  
|[GetPrevious 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|스레드에 대 한 이전 프레임 체인을 가져옵니다.|  
|[GetReason 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|이 호출 체인이 발생 한 이유를 가져옵니다.|  
|[GetRegisterSet 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|레지스터를이 체인의 활성 부분에 대 한 집합을 가져옵니다.|  
|[GetStackRange 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|이 체인에 대 한 스택 세그먼트의 주소 범위를 가져옵니다.|  
|[GetThread 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|호출 체인은 실제 스레드에서의 부분을 가져옵니다.|  
|[IsManaged 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|이 체인 관리 되는 코드를 실행 하 고 있는지 여부를 나타내는 값을 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 스택 프레임 체인의 인접 한 스택 공간을 차지 하 고 동일한 스레드와 컨텍스트를 공유 합니다. 체인 관리 되거나 관리 되지 않는 코드 체인 중 하나를 나타낼 수 있습니다. 빈 `ICorDebugChain` 인스턴스는 비관리 코드 체인을 나타냅니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
