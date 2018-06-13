---
title: CorDebugExceptionCallbackType 열거형
ms.date: 03/30/2017
api_name:
- CorDebugExceptionCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionCallbackType
helpviewer_keywords:
- CorDebugExceptionCallbackType enumeration [.NET Framework debugging]
ms.assetid: 4d946ad4-3c19-42cb-bec9-8633325ba769
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fc0919a7c05bfcbfb4b54dd0b618564f019f3fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407822"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a>CorDebugExceptionCallbackType 열거형
수행 되는 콜백의 형식을 나타냅니다는 [icordebugmanagedcallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) 이벤트입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|예외가 throw 되었습니다.|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|예외 종료 프로세스가 사용자 코드를 입력 합니다.|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|찾을 예외 종료 프로세스가 `catch` 사용자 코드에서 차단 합니다.|  
|`DEBUG_EXCEPTION_UNHANDLED`|예외 처리 되지 않았습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
