---
title: "ICorDebugValue::GetSize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue.GetSize
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5cf99b35d45c1dda8f187e0206e068c128f347d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvaluegetsize-method"></a>ICorDebugValue::GetSize 메서드
이 "ICorDebugValue" 개체를 바이트 단위로 크기를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pSize`  
 [out] 이 값 개체를 바이트 단위로 크기입니다.  
  
## <a name="remarks"></a>설명  
 값의 형식이 참조 형식인 경우이 메서드는 개체의 크기 보다는 포인터의 크기를 반환 합니다.  
  
 `ICorDebugValue::GetSize` 메서드 반환 `COR_E_OVERFLOW` 64 비트 플랫폼에서 4GB 보다 큰 개체에 대 한 합니다. 사용 하 여 [icordebugvalue3:: Getsize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) 메서드 대신 개체 수 있는 4GB 보다 큰 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
    
 [GetSize64 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
