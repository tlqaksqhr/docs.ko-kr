---
title: "CorDebugStepReason 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugStepReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugStepReason
helpviewer_keywords: CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 32892a14de820e8add38654cef92aa44930aec62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugstepreason-enumeration"></a>CorDebugStepReason 열거형
개별 단계의 결과를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`STEP_NORMAL`|단계별 실행는 동일한 함수 내에서 정상적으로 완료 합니다.|  
|`STEP_RETURN`|단계별 함수가 반환 후 정상적으로 계속 합니다.|  
|`STEP_CALL`|단계별 실행이 새로 호출 된 함수의 시작 부분에 정상적으로 계속 합니다.|  
|`STEP_EXCEPTION_FILTER`|예외가 발생 하 고 제어 예외 필터에 전달 되었습니다.|  
|`STEP_EXCEPTION_HANDLER`|예외가 발생 하 고 제어 예외 처리기에 전달 되었습니다.|  
|`STEP_INTERCEPT`|컨트롤은 인터셉터로 전달 되었습니다.|  
|`STEP_EXIT`|단계를 완료 하기 전에 스레드가 종료 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [StepComplete 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)  
 [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
