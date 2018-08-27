---
title: SpawnInstance 함수 (관리 되지 않는 API 참조)
description: SpawnInstance 함수는 클래스의 새 인스턴스를 만듭니다.
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb187719ff502abe61ac5deb69c6427a4a64ab44
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930229"
---
# <a name="spawninstance-function"></a>SpawnInstance 함수
클래스의 새 인스턴스를 만듭니다.    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`  
[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.

`lFlags`  
[in] 예약 되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`ppNewInstance`  
[out] 클래스의 새 인스턴스에 대 한 포인터를 받습니다. 오류가 발생 하는 새 개체가 없는 경우 반환 및 `ppNewInstance` 왼쪽 수정 됩니다.

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | `ptr` 올바른 클래스 정의가 아닌 경우 및 새 인스턴스를 생성할 수 없습니다. 완료 되지 않은 또는 등록 되지 않은 Windows 관리를 사용 하 여 호출 하 여 [PutClassWmi](putclasswmi.md)합니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006(" | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
| `WBEM_E_INVALID_PARAMETER` | '(0x80041008 | `ppNewClass`가 `null`인 경우 |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) 메서드.

`ptr` 클래스 정의에서 받아야 Windows 관리 합니다. (인스턴스에서 인스턴스 생성은 지원 하지만 반환 된 인스턴스에만 비어 있습니다.) 그런 다음이 클래스 정의 사용 하 여 새 인스턴스를 만듭니다. 에 대 한 호출을 [PutInstanceWmi](putinstancewmi.md) 함수는 Windows 관리 인스턴스를 작성 하려는 경우에 필요 합니다.




반환 되는 새 개체 `ppNewClass` 현재 개체의 하위 클래스는 자동으로 됩니다. 이 동작을 재정의할 수 없습니다. 서브 클래스 (파생된 클래스)을 만들 수 있는 다른 메서드가 없는 합니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
