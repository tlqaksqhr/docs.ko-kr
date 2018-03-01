---
title: "ICorDebugProcess3::SetEnableCustomNotification 메서드"
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
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2ccd1f4b6be56202d5efea1d2e38dce554835218
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>ICorDebugProcess3::SetEnableCustomNotification 메서드
사용 하도록 설정 하 고 지정 된 형식의 사용자 지정 디버거 알림을 해제 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pClass`  
 [in] 사용자 지정 디버거 알림을 지정 하는 형식입니다.  
  
 `fEnable`  
 [in] `true` 사용자 지정 디버거 알림을;를 사용 하도록 설정 하려면 `false` 알림을 사용 하지 않으려면입니다. 기본값은 `false`입니다.  
  
## <a name="remarks"></a>설명  
 때 `fEnable` 로 설정 된 `true`에 대 한 호출이 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> 메서드 트리거는 [icordebugmanagedcallback3:: Customnotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) 콜백 합니다. 기본적으로 알림이 비활성화 되었습니다. 따라서 디버거에서 인식 하 고 처리 하는 알림 유형을 지정 해야 합니다. 때문에 [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 클래스의 응용 프로그램 도메인에서 범위가, 디버거가 호출 해야 `SetEnableCustomNotification` 전체 프로세스에서 알림을 받으려는 경우 프로세스에 있는 모든 응용 프로그램 도메인에 대 한 합니다.  
  
 부터는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], 지원 됩니다 크로스 스레드 종속성 알림입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugProcess3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
