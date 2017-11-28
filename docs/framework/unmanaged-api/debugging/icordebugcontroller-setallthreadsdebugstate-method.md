---
title: "ICorDebugController::SetAllThreadsDebugState 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.SetAllThreadsDebugState
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d5a033ef2efd8fa5e3b519e19b62ce2dfb84a5e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a>ICorDebugController::SetAllThreadsDebugState 메서드
프로세스에서 모든 관리 되는 스레드의 디버그 상태를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `state`  
 [in] 디버깅을 위한 스레드 상태를 지정 하는 "CorDebugThreadState" 열거형의 값입니다.  
  
 `pExceptThisThread`  
 [in] 디버그 상태 설정에서 제외 해야 하는 스레드를 나타내는 "ICorDebugThread" 개체에 대 한 포인터입니다. 이 값이 null 이면 없는 스레드는 제외 됩니다.  
  
## <a name="remarks"></a>설명  
 `SetAllThreadsDebugState` 메서드를 통해 표시 되지 않는 스레드 영향을 줄 수 [EnumerateThreads 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md),으로 일시 중단 된 스레드 등의 `SetAllThreadsDebugState` 메서드도 다시 시작 해야 합니다는 `SetAllThreadsDebugState` 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 
