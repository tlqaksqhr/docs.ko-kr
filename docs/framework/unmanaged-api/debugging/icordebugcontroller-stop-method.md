---
title: "ICorDebugController::Stop 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Stop
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4b92d07f8d162123d20c6861d204d73789060906
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerstop-method"></a>ICorDebugController::Stop 메서드
프로세스에서 관리 되는 코드를 실행 하는 모든 스레드에서 동시 중지를 수행 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwTimeoutIgnored`  
 사용되지 않습니다.  
  
## <a name="remarks"></a>설명  
 `Stop`프로세스의 코드가 관리 되는 실행 중인 모든 스레드에서 동시 중지를 수행 합니다. 관리 전용 디버깅 세션 중에 관리 되지 않는 스레드 계속 실행할 수 있습니다 (하지만 관리 코드를 호출 하려고 할 때 차단 됩니다). Interop 디버깅 세션 중 관리 되지 않는 스레드가 중지 됩니다. `dwTimeoutIgnored` 값은 현재 무시 되 고 무한 (-1)으로 처리 합니다. 동시 중지 교착 상태로 인해 실패 하면 모든 스레드가 일시 중단 되 고 E_TIMEOUT 반환 됩니다.  
  
> [!NOTE]
>  `Stop`디버깅 API의 동기 메서드입니다. 때 `Stop` 반환 s_ok이 고, 프로세스를 중지 합니다. 콜백이 없는 중지점의 수신기를 알리기 위해 제공 됩니다. 디버거를 호출 해야 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 프로세스가 다시 시작을 허용 하도록 합니다.  
  
 디버거 중지 카운터를 유지 관리합니다. 카운터가 0이 되 면 컨트롤러 다시 시작 됩니다. 호출할 때마다 `Stop` 또는 디스패치 된 콜백을 카운터를 증가 시킵니다. 호출할 때마다 `ICorDebugController::Continue` 감소 카운터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 
