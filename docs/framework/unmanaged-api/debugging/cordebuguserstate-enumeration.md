---
title: "CorDebugUserState 열거형"
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
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 57fd9df27b1911c90bd11712b67e6e64588c2b5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cordebuguserstate-enumeration"></a>CorDebugUserState 열거형
스레드의 사용자 상태를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a>멤버  
  
|값|설명|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|스레드 종료가 요청 되었습니다.|  
|`USER_SUSPEND_REQUESTED`|스레드 일시 중단을 요청 했습니다.|  
|`USER_BACKGROUND`|스레드는 백그라운드에서 실행 중입니다.|  
|`USER_UNSTARTED`|스레드 실행을 시작 되지 않았습니다.|  
|`USER_STOPPED`|스레드가 종료 되었습니다.|  
|`USER_WAIT_SLEEP_JOIN`|스레드가 다른 스레드에서 작업을 완료 대기 중입니다.|  
|`USER_SUSPENDED`|스레드가 일시 중단 되었습니다.|  
|`USER_UNSAFE_POINT`|스레드는 안전 하지 않은 시점입니다. 즉,는 스레드는 실행 지점에서 가비지 수집을 차단할 수 있는입니다.<br /><br /> 디버그 안전 하지 않은 지점에서 이벤트를 디스패치할 수 있습니다 있지만 안전 하지 않은 지점에서 스레드를 일시 중단 될 가능성이 매우 하면 교착 상태 스레드 재개 될 때까지 합니다. 안전 하 고 안전 하지 않은 지점 시간 (JIT) 및 가비지 수집 구현에서 결정 됩니다.|  
|`USER_THREADPOOL`|스레드의는 스레드 풀에서 됩니다.|  
  
## <a name="remarks"></a>설명  
 스레드의 사용자 상태는 디버거에서 검사할 때 스레드가 있는 상태입니다. 스레드가 여러 사용자 상태에 있을 수 있습니다.  
  
 사용 하 여는 [icordebugthread:: Getuserstate](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) 스레드의 사용자 상태를 검색 하는 메서드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
