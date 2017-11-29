---
title: "ICorDebugManagedCallback2::Exception 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.Exception
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a78900a6e37c3ae136489c35da7b0cd2931f24a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2exception-method"></a>ICorDebugManagedCallback2::Exception 메서드
예외 처리기에 대 한 검색이 시작 되었음을 디버거에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pAppDomain`  
 [in] 예외가 throw 된 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.  
  
 `pThread`  
 [in] 예외가 throw 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.  
  
 `pFrame`  
 [in] 프레임을 기준으로를 나타내는 ICorDebugFrame 개체에 대 한 포인터는 `dwEventType` 매개 변수입니다. 자세한 내용은 주의 섹션의 표를 참조 합니다.  
  
 `nOffset`  
 [in] 의해 결정 되는 오프셋을 지정 하는 정수는 `dwEventType` 매개 변수입니다. 자세한 내용은 주의 섹션의 표를 참조 합니다.  
  
 `dwEventType`  
 [in] 이 예외 콜백의 유형을 지정 하는 CorDebugExceptionCallbackType 열거형의 값입니다.  
  
 `dwFlags`  
 [in] 값은 [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) 예외에 대 한 추가 정보를 지정 하는 열거형  
  
## <a name="remarks"></a>설명  
 `Exception` 콜백은 예외 처리 프로세스의 검색 단계 동안 다양 한 시점에서 호출 됩니다. 즉,이 호출 될 수 동안 두 번 이상 예외를 해제 합니다.  
  
 처리 중인 예외를 참조 하는 ICorDebugThread 개체에서 검색할 수 있습니다는 `pThread` 매개 변수입니다.  
  
 특정 프레임 및 오프셋에 의해 결정 되는 `dwEventType` 다음과 같이 매개 변수:  
  
|`dwEventType`의 값|`pFrame`의 값|`nOffset`의 값|  
|----------------------------|-----------------------|------------------------|  
|DEBUG_EXCEPTION_FIRST_CHANCE|예외를 발생 시킨 프레임입니다.|프레임의 명령 포인터입니다.|  
|DEBUG_EXCEPTION_USER_FIRST_CHANCE|예외가 throw 된 지점과 가장 가까운 사용자 코드 프레임입니다.|프레임의 명령 포인터입니다.|  
|DEBUG_EXCEPTION_CATCH_HANDLER_FOUND|Catch 처리기가 포함 된 프레임입니다.|Catch 처리기를 시작 하는 Microsoft MSIL (intermediate language) 오프셋입니다.|  
|DEBUG_EXCEPTION_UNHANDLED|NULL|정의 되지 않았습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugManagedCallback2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [ICorDebugManagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
