---
title: "ICorDebugManagedCallback3::CustomNotification 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback3.CustomNotification Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9c42443b0d1e355d4233909357c341763298160e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback3customnotification-method"></a>ICorDebugManagedCallback3::CustomNotification 메서드
사용자 지정 디버거 알림이 발생 했음을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pThread`  
 [in] 알림을 발생 하는 스레드에 대 한 포인터입니다.  
  
 `pAppDomain`  
 [in] 알림을 발생 하는 스레드를 포함 하는 응용 프로그램 도메인에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>설명  
 후속 호출에는 [icordebugthread4:: Getcurrentcustomdebuggernotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) 에 전달 된 스레드 개체를 검색 하는 메서드는 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> 메서드. 스레드 개체의 형식을 해야 이전에 설정한 호출 하 여는 [icordebugprocess3:: Setenablecustomnotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) 메서드. 디버거가는 thread 개체의 필드에서 특정 형식의 매개 변수를 읽을 수 있습니다 및 필드에 응답을 저장할 수 있습니다.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 인터페이스에서는 정책을 적용 하지 알림 나 내용 유형 및에서 알림의 의미 체계는 엄격 하 게 디버거, 응용 프로그램 및.NET Framework 사이의 계약입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugManagedCallback3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
