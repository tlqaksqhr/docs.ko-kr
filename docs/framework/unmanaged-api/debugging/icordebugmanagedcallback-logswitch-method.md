---
title: "ICorDebugManagedCallback::LogSwitch 메서드"
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
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: beb4dc25d634f64d8740005abf83e51ec1e3e731
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a>ICorDebugManagedCallback::LogSwitch 메서드
공용 언어 런타임 (CLR) 관리 되는 스레드에서의 메서드를 호출 했습니다 디버거에 알립니다는 <xref:System.Diagnostics.Switch> 클래스를 만들거나 수정 하거나 디버깅/추적 스위치를 삭제 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `PAppDomain`  
 [in] ICorDebugAppDomain 생성/수정 / 디버깅/추적 스위치를 삭제 하는 관리 되는 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 개체에 대 한 포인터입니다.  
  
 `pThread`  
 [in] 관리 되는 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.  
  
 `lLevel`  
 [in] 이벤트 로그에 작성 된 설명 하는 메시지의 심각도 수준을 나타내는 값입니다.  
  
 `ulReason`  
 [in] 값은 [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) 디버깅/추적 스위치에 수행 후 작업을 나타내는 열거형입니다.  
  
 `pLogSwitchName`  
 [in] 디버깅/추적 스위치의 이름에 대 한 포인터입니다.  
  
 `pParentName`  
 [in] 디버깅/추적 스위치에 대 한 부모 노드의 이름에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugManagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
