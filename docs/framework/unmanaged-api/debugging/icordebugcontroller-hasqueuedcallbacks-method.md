---
title: "ICorDebugController::HasQueuedCallbacks 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.HasQueuedCallbacks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03d52bb31a81876a00e1af33494b14fb99fee0fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>ICorDebugController::HasQueuedCallbacks 메서드
지정 된 스레드에 대 한 모든 관리 되는 콜백이 현재 대기 중인 있는지 여부를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pThread`  
 [in] 스레드를 나타내는 "ICorDebugThread" 개체에 대 한 포인터입니다.  
  
 `pbQueued`  
 [out] 값에 대 한 포인터 `true` 관리 되는 모든 콜백이 고, 그렇지 않으면 지정 된 스레드에 대 한 큐에 대기 중인 현재 경우 `false`합니다.  
  
 에 대 한 null을 지정 하는 경우는 `pThread` 매개 변수를 `HasQueuedCallbacks` 돌아갑니다 `true` 현재 스레드에 대 한 관리 되는 콜백이 대기 합니다.  
  
## <a name="remarks"></a>설명  
 콜백이 됩니다 발송 될 때마다 한 번에 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 호출 됩니다. 디버거는 동시에 발생 하는 여러 디버깅 이벤트를 보고 하려는 경우이 플래그를 확인할 수 있습니다.  
  
 디버깅 이벤트 큐에 대기 하는 경우 이러한 이미 발생 한, 디버거는 디버기에 상태의 내기 위해서는 전체 큐를 제거 해야 하므로 합니다. (호출 `ICorDebugController::Continue` 큐를 드레이닝 하도록 합니다.) 예를 들어, 큐 스레드에서 두 디버깅 이벤트를 포함 하는 경우 *X*, 디버거 스레드를 일시 중단 및 *X* 첫 번째 디버깅 이벤트 및 다음 호출 후 `ICorDebugController::Continue`에 대 한 두 번째 디버깅 이벤트 스레드 *X* 는 스레드가 일시 중단 된 더라도 디스패치 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 
