---
title: ICorDebugRegisterSet2::GetRegisters 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aca83a66520531074f376a47a7f2994cda237f9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugregisterset2getregisters-method"></a>ICorDebugRegisterSet2::GetRegisters 메서드
(코드가 현재 실행 중인 플랫폼)에 대 한 각 레지스터의 값을 가져옵니다는 지정 된 비트 마스크에 의해 지정 된 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `maskCount`  
 [in] 를 바이트 단위로 크기의는 `mask` 배열입니다.  
  
 `mask`  
 [in] 바이트 배열 인 각 비트를 레지스터에 해당합니다. 비트가 1 인 경우 해당 레지스터의 값이 검색 됩니다.  
  
 `regCount`  
 [in] 레지스터 값을 검색할 수 있습니다.  
  
 `regBuffer`  
 [out] 배열 `CORDB_REGISTER` 각각 수신 하는 레지스터의 값 개체입니다.  
  
## <a name="remarks"></a>설명  
 `GetRegisters` 메서드 마스크에 의해 지정 된 레지스터에서 값의 배열을 반환 합니다. 배열은 마스크 비트가 설정 되지 않은 레지스터의 값을 포함 하지 않습니다. 따라서의 크기는 `regBuffer` 배열 마스크에 1의 수가 동일 해야 합니다. 하는 경우의 값 `regCount` 수가 레지스터의 값 마스크에 의해 표시 되는 레지스터 집합에서 잘립니다에 대 한 너무 작습니다. 경우 `regCount` 너무 커서는 사용 하지 않는 `regBuffer` 요소를 수정 되지 것입니다.  
  
 / / 마스크에 사용할 수 없는 레지스터는 표시 된 경우 결정 되지 않은 값을 해당 레지스터에 대해 반환 됩니다.  
  
 `ICorDebugRegisterSet2::GetRegisters` 메서드는 64 개 이상의 레지스터가 플랫폼에 필요 합니다. 예를 들어 IA64에 128 일반 용도 레지스터와 부동 소수점 레지스터 128 비트 마스크에 64 비트 이상이 필요 하므로 있습니다.  
  
 X86, 같은 플랫폼의 경우와 마찬가지로 64 개 이상의 레지스터가 없는 경우는 `GetRegisters` 메서드 실제로 변환 하는 바이트는 `mask` 바이트 배열에는 `ULONG64` 를 호출 하는 [ICorDebugRegisterSet:: GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) 사용 메서드는 `ULONG64` 마스크입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugRegisterSet2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [ICorDebugRegisterSet 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
