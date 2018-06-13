---
title: ICorDebugManagedCallback::DebuggerError 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 436be84ad91bb20bfd88a51f2d6c2b760c4a4c3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420139"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a>ICorDebugManagedCallback::DebuggerError 메서드
공용 언어 런타임 (CLR)의 이벤트를 처리 하는 동안 오류가 발생 했습니다는 디버거에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pProcess`  
 [in] 이벤트가 발생 한 프로세스를 나타내는 "ICorDebugProcess" 개체에 대 한 포인터입니다.  
  
 `errorHR`  
 [in] 이벤트 처리기에서 반환 된 HRESULT 값입니다.  
  
 `errorCode`  
 [in] CLR 오류를 지정 하는 정수입니다.  
  
## <a name="remarks"></a>설명  
 프로세스 오류의 성격에 따라 통과 모드로 배치 될 수 있습니다.  
  
 `DebugError` 콜백은 있도록 오류 메시지 사용할 수 있는 사용자에 게 디버깅 서비스 오류로 인해 비활성화 되었음을 있는지를 나타냅니다. [Icordebugprocess:: Getid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) 호출을 포함 한 다른 모든 메서드를 안전한 [icordebug:: Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)를 호출할 수 없습니다. 디버거는 프로세스를 종료 하기 위해 운영 체제 기능을 사용 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugManagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
