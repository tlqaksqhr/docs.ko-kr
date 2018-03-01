---
title: "SpawnDerivedClass 함수 (관리 되지 않는 API 참조)"
description: "SpawnDerivedClass 함수는 개체에서 파생 된 새 개체를 만듭니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 51a0dd0013b1bb3898bcc81ee2d64be20a5b6ecc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="spawnderivedclass-function"></a>SpawnDerivedClass 함수
지정된 된 개체에서 새로 파생된 클래스 개체를 만듭니다.    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`  
[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.

`lFlags`  
[in] 예약 되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`ppNewClass`  
[out] 새 클래스 정의 개체에 대 한 포인터를 받습니다. 오류가 발생 하는 경우 새 개체는 되지 반환 하 고 `ppNewClass` 은 왼쪽 수정 되지 않은 합니다. 해당 값은 수 없음 `null`합니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | 일반 오류가 발생이 했습니다. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | 클래스는 인스턴스를 생성 하는 등의 잘못 된 작업을 요청 했습니다. |
| `WBEM_E_INCOMPLETE_CLASS` | 완전히 분리 되지 않은 원본 클래스 정의 되었거나 Windows 관리 등록 되므로 새로 파생 된 클래스는 허용 되지 않습니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass`가 `null`인 경우 |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::SpawnDerivedClass](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) 메서드.

`ptr`생성 된 개체의 부모 클래스를 클래스 정의 해야 합니다. 반환 된 개체가 현재 개체의 하위 됩니다.

반환 되는 새 개체 `ppNewClass` 현재 개체의 하위 클래스는 자동으로 됩니다. 이 동작을 재정의할 수 없습니다. 서브 클래스 (파생된 클래스)을 만들 수 있는 다른 메서드가 없는 합니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
