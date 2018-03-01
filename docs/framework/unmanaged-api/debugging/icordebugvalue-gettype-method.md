---
title: "ICorDebugValue::GetType 메서드"
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
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a79ef332361fdaa3a23cc4e13daa8b4a8303d2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvaluegettype-method"></a>ICorDebugValue::GetType 메서드
이 "ICorDebugValue" 개체의 기본 형식을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pType`  
 [out] 값의 형식을 나타내는 "CorElementType" 열거형의 값에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 개체가 복잡 한 런타임 형식이의 적절 한 하위 클래스를 통해 해당 형식을 검사할 수 있습니다는 `ICorDebugValue` 인터페이스입니다. 예를 들어 "ICorDebugObjectValue"에서 상속 하는 `ICorDebugValue`, 복합 유형을 나타냅니다.  
  
 `GetType` 및 [icordebugobjectvalue:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) 메서드는 각각 값의 형식에 대 한 정보를 반환 합니다. 둘 다로 대체 되기 제네릭 인식 [icordebugvalue2:: Getexacttype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 
