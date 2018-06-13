---
title: LoggingLevelEnum 열거형
ms.date: 03/30/2017
api_name:
- LoggingLevelEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LoggingLevelEnum
helpviewer_keywords:
- LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 331065d4aae82c66b9ebd82e99427501c3ba8a98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435957"
---
# <a name="logginglevelenum-enumeration"></a>LoggingLevelEnum 열거형
관리되는 스레드가 이벤트를 기록할 때 이벤트 로그에 기록되는 설명 메시지의 보안 수준을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`LTraceLevel0`|메시지 추적 수준이 0입니다.|  
|`LTraceLevel1`|메시지는 추적 수준 1입니다.|  
|`LTraceLevel2`|메시지는 추적 수준 2입니다.|  
|`LTraceLevel3`|메시지는 추적 수준 3입니다.|  
|`LTraceLevel4`|메시지는 추적 수준 4입니다.|  
|`LStatusLevel0`|메시지는 상태 수준 0입니다.|  
|`LStatusLevel1`|메시지는 상태 수준 1입니다.|  
|`LStatusLevel2`|메시지는 상태 수준 2입니다.|  
|`LStatusLevel3`|메시지는 상태 수준 3입니다.|  
|`LStatusLevel4`|메시지는 상태 수준 4입니다.|  
|`LWarningLevel`|메시지는 경고 수준입니다.|  
|`LErrorLevel`|메시지 오류 수준입니다.|  
|`LPanicLevel`|메시지에는 심각한 오류 수준입니다.|  
  
## <a name="remarks"></a>설명  
 호출 하는 공용 언어 런타임 (CLR)는 [icordebugmanagedcallback:: Logmessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) 메서드 디버거에를 알리거나 관리 되는 스레드에서 이벤트를 기록 합니다. 값을 전달 하는 CLR의 `LoggingLevelEnum` 열거형을 관리 되는 스레드 이벤트 로그에 작성 하는 메시지의 심각도 수준을 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Diagnostics.EventLog>  
 [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
