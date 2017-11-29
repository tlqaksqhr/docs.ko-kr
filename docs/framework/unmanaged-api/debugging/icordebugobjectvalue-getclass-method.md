---
title: "ICorDebugObjectValue::GetClass 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue.GetClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dee9f110647230e54df527959651dc5b2fb73b3f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugobjectvaluegetclass-method"></a>ICorDebugObjectValue::GetClass 메서드
이 개체 값의 클래스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppClass`  
 [out] 개체 값이 "ICorDebugObjectValue" 개체가 나타내는 클래스를 나타내는 "ICorDebugClass" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `GetClass` 및 [icordebugvalue:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) 메서드는 각각 값의 형식에 대 한 정보를 반환 하며 둘 다로 대체 되기 제네릭 인식 [icordebugvalue2:: Getexacttype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
    
 
