---
title: ICorDebugRegisterSet2::GetRegistersAvailable 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3a9cdb49c1a44dbc68cd4b7ccf4d4781ce5c539
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421894"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a>ICorDebugRegisterSet2::GetRegistersAvailable 메서드
사용 가능한 레지스터의 비트맵을 제공 하는 바이트의 배열을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `numChunks`  
 [in] `availableRegChunks` 배열의 크기입니다.  
  
 `availableRegChunks`  
 [out] 바이트 배열 인 각 비트를 레지스터에 해당합니다. 레지스터를 사용할 수 있는 레지스터의 해당 비트가 설정 됩니다.  
  
## <a name="remarks"></a>설명  
 CorDebugRegister 열거형의 값 다른 마이크로프로세서의 레지스터를 지정합니다. 각 값의 상위 5 개 비트에 대 한 인덱스는는 `availableRegChunks` 바이트 배열입니다. 각 값의 하위 3 비트 인덱싱된 바이트에서 비트 위치를 식별합니다. 지정 된 `CorDebugRegister` 특정 레지스터를 마스크의 레지스터의 위치를 지정 하는 값은 다음과 같이 결정 됩니다.  
  
1.  추출 정확한 바이트에 액세스 하는 데 필요한 인덱스는 `availableRegChunks` 배열:  
  
     `CorDebugRegister` 값 >> 3  
  
2.  인덱싱된 바이트에서 비트 위치 0 비트는 최하위 비트를 추출 합니다.  
  
     `CorDebugRegister` 값 및 7  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugRegisterSet2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [ICorDebugRegisterSet 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
