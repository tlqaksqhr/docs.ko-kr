---
title: "ICorDebugRegisterSet::GetThreadContext 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.GetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 910bb09aa011efc9f81cf5c62a58d39236d723de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregistersetgetthreadcontext-method"></a>ICorDebugRegisterSet::GetThreadContext 메서드
현재 스레드의 컨텍스트를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `contextSize`  
 [in] 를 바이트 단위로 크기의는 `context` 배열입니다.  
  
 `context`  
 [out에서] Win32를 구성 하는 바이트 배열을 `CONTEXT` 현재 플랫폼에 대 한 구조입니다.  
  
## <a name="remarks"></a>설명  
 디버거에서 Win32 대신이 함수를 호출 해야 `GetThreadContext` 스레드 컨텍스트에 일시적으로 변경 하는 "도용된" 상태에 있을 수 때문에 작동 합니다. 반환 되는 데이터는 Win32 `CONTEXT` 현재 플랫폼에 대 한 구조입니다.  
  
 리프가 아닌 프레임에 대 한 클라이언트를 사용 하 여 있는 레지스터 올바른지 확인 해야 [icordebugregisterset:: Getregistersavailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugRegisterSet 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [ICorDebugRegisterSet2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
