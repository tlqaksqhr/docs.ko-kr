---
title: "ICorDebugProcess5::EnableNGENPolicy 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5::EnableNGenPolicy
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dca0df7b0be643d53bb5b9a03bd3abbb186d69dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enablengenpolicy-method"></a>ICorDebugProcess5::EnableNGENPolicy 메서드
응용 프로그램에서 관리 되는 디버거가 실행 되는 동안 네이티브 이미지를 로드 하는 방식을 결정 하는 값을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ePolicy`  
 [in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) 응용 프로그램에서 관리 되는 디버거가 실행 되는 동안 네이티브 이미지를 로드 하는 방식을 결정 하는 상수입니다.  
  
## <a name="remarks"></a>설명  
 메서드가 반환 하는 경우에 정책이 성공적으로 설정 되 면 `S_OK`합니다. 경우 `ePolicy` 으로 정의 된 열거 값의 범위 밖에 [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), 메서드가 반환 `E_INVALIDARG` 메서드 호출이 영향을 주지 않습니다. 메서드가 반환 하는 경우 네이티브 이미지 생성기 (Ngen.exe)의 정책을 업데이트할 수 없습니다, `E_FAIL`합니다.  
  
 `ICorDebugProcess5::EnableNGenPolicy` 프로세스의 수명 동안 언제 든 지 메서드를 호출할 수 있습니다. 정책이 정책 설정 된 후 로드 되는 모든 모듈에 대 한 적용 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugProcess5 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
