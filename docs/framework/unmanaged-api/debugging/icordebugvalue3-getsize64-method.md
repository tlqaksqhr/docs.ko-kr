---
title: "ICorDebugValue3::GetSize64 메서드"
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
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4eb0c4691b82bdfaecb97c5969a942c113987c04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvalue3getsize64-method"></a>ICorDebugValue3::GetSize64 메서드
이 바이트 단위로 크기를 가져옵니다 [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pSize  
 [out] 이 개체를 바이트 단위로 크기에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 값 형식이 참조 형식인 경우이 메서드는 개체의 크기 보다는 포인터의 크기를 반환 합니다.  
  
 `ICorDebugValue3::GetSize` 에서 다른 메서드는 [icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) 해당 출력 매개 변수 형식에서 메서드. [icordebugvalue:: Getsize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), 출력 매개 변수는 `ULONG32`, `ICorDebugValue3::GetSize`, 이기는 `ULONG64`합니다. 이 통해는 [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) 인터페이스를 2GB를 초과 하는 배열의 크기를 보고 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugValue3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
