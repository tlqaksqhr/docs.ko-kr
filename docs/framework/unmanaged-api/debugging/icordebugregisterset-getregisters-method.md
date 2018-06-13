---
title: ICorDebugRegisterSet::GetRegisters 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: deaeb4e244a4f9c1e8582d9bea26c2ae5cfde818
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421352"
---
# <a name="icordebugregistersetgetregisters-method"></a>ICorDebugRegisterSet::GetRegisters 메서드
(현재 코드를 실행 하는 컴퓨터)에서 각 레지스터의 값을 가져옵니다는 비트 마스크에 의해 지정 된 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mask`  
 [in] 검색할 값은 어느 레지스터를 지정 하는 비트 마스크입니다. 각 비트를 레지스터에 해당합니다. 약간 1로 설정 되 면 레지스터의 값이 검색 됩니다. 그렇지 않으면 레지스터의 값은 검색 되지 않습니다.  
  
 `regCount`  
 [in] 레지스터 값을 검색할 수 있습니다.  
  
 `regBuffer`  
 [out] 배열 `CORDB_REGISTER` 각각 수신 하는 레지스터의 값 개체입니다.  
  
## <a name="remarks"></a>설명  
 배열의 크기는 비트 마스크에 1로 설정 된 비트 수와 동일 해야 합니다. `regCount` 매개 변수 레지스터 값을 받을 버퍼에서 요소 수를 지정 합니다. 경우는 `regCount` 값이 너무 작아서 마스크에 의해 지정 된 레지스터 수에 대 한, 레지스터 집합에서 잘립니다. 경우는 `regCount` 값이 너무 커서는 사용 하지 않는 `regBuffer` 요소를 수정 되지 것입니다.  
  
 비트 마스크를 사용할 수 있는 레지스터를 지정 하는 경우 `GetRegisters` 해당 레지스터에 대 한 비활성화 상태 값을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugRegisterSet 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [ICorDebugRegisterSet2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
