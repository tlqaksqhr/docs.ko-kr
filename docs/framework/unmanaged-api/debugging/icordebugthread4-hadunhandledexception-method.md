---
title: "ICorDebugThread4::HadUnhandledException 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4.HadUnhandledException Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ea29fa02e74c204cde003b18520bf512b0d21d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread4hadunhandledexception-method"></a>ICorDebugThread4::HadUnhandledException 메서드
스레드가 처리 되지 않은 예외가 한 적이 있는지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppBlockingObjectEnum`  
 [out] 순서가 지정 된 열거형의 주소에 대 한 포인터 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|스레드가는 만들어진 이후 처리 되지 않은 예외가 발생 했습니다.|  
|S_FALSE|스레드가 처리 되지 않은 예외가 적입니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 스레드에서 처리 되지 않은 예외가 한 적이 있는지 여부를 나타냅니다. 예외로 인해 콜백 트리거될 때까지 또는 네이티브 JIT 연결가 시작 되 면이 메서드는 항상 S_OK를 반환 합니다. 하지만 다 하는 [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) 메서드는 처리 되지 않은 예외를 반환 하는 경우 프로세스 하지 아직 계속 된 예외로 인해 콜백을 받은 후 또는 시 됩니다; 네이티브 JIT 연결 합니다. 또한 것 가능 없지만 둘 이상의 스레드가 네이티브 JIT 연결 트리거될 때 처리 되지 않은 예외와 함께 있어야 합니다. 이러한 경우 JIT 연결을 트리거한 예외를 확인할 수 없습니다 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugThread4 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
