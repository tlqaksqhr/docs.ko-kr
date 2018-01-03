---
title: "ICorDebugManagedCallback::ExitProcess 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.ExitProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::ExitProcess
helpviewer_keywords:
- ExitProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::ExitProcess method [.NET Framework debugging]
ms.assetid: 63a7d47a-0d54-4e29-9767-9f09feaa38b7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7be74520fff65b113f54d82305a84dd183286876
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackexitprocess-method"></a>ICorDebugManagedCallback::ExitProcess 메서드
프로세스가 종료 되었는지 디버거에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ExitProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pProcess`  
 [in] 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 계속할 수 없습니다는 `ExitProcess` 이벤트입니다. 이 이벤트는 프로세스를 중지할 표시 하는 동안 다른 이벤트에 비동기적으로 실행 될 수 있습니다. 프로세스가 종료 일반적으로 외부 요인으로 인해 중지 하는 동안 발생할 수 있습니다.  
  
 공용 언어 런타임 (CLR)을 이미 관리 되는 콜백을 전달 하 고, 해당 콜백이 반환 후이 이벤트까지 지연 됩니다.  
  
 `ExitProcess` 이벤트는 종료 시 호출 될 수만 종료/언로드 이벤트입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugManagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
