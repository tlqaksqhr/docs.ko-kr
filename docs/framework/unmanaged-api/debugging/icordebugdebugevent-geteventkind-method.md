---
title: "ICorDebugDebugEvent::GetEventKind 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cf3296eafb3e3ff933092240f8f353b2b69a89c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdebugeventgeteventkind-method"></a>ICorDebugDebugEvent::GetEventKind 메서드
이 `ICorDebugDebugEvent` 개체가 나타내는 이벤트의 종류를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pDebugEventKind  
 에 대 한 포인터는 [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) 이벤트의 형식을 나타내는 열거형 멤버입니다.  
  
## <a name="remarks"></a>설명  
 `pDebugEventKind`의 값에 따라 `QueryInterface`를 호출하여 추가 데이터를 포함하는 보다 정확한 디버그 이벤트 인터페이스를 가져올 수 있습니다.  
  
> [!NOTE]
>  이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugDebugEvent 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
