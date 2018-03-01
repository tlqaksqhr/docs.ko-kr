---
title: "ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f13236c865f9a57d77ebf83ab48e010f06ef08e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode 메서드
[[!INCLUDE[net_v46](../../../../includes/net-v46-md.md)] 이상 버전에서 지원됨]  
  
 특정 유형의 사용할지 [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) 예외 콜백을 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `enableExceptionsOutsideOfJMC`  
 [in]  
  
## <a name="remarks"></a>설명  
 `enableExceptionsOutsideOfJMC`의 값이 `false`인 경우:  
  
-   DEBUG_EXCEPTION_FIRST_CHANCE 예외 디버거 콜백이 발생 하지 않습니다.  
  
-   DEBUG_EXCEPTION_CATCH_HANDLER_FOUND 예외가 발생 하지 것입니다 콜백에서 디버거는 예외가 사용자 코드로 이스케이프 되지 않는 경우 (즉, 예외 출처에서에서 예외 처리기로의 경로 JustMyCode 또는 JMC로 표시 된 메서드가 없음).  
  
 `enableExceptionsOutsideOfJMC`의 기본값은 `true`입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugProcess8 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
